---
title: Externer Connector für Google Cloud-Speicher
description: Erfahren Sie, wie Sie den externen Connector für Google Cloud Storage in CX Enterprise Coworker mit Ihrer Google OAuth-App einrichten und sich anmelden, um Bucket-Daten im Chat zu lesen.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Dieser Connector befindet sich in der Betaphase."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 70782269f48e3ff87ca95a1341ee74b02da1d7f4
workflow-type: tm+mt
source-wordcount: '2408'
ht-degree: 1%
---

# Externer Connector für Google Cloud Storage {#google-cloud-storage}

Verwenden Sie den externen [!DNL Google Cloud Storage]-Connector, um Ihre [!DNL Cloud Storage] in Adobe CX Enterprise Coworker zu lesen. Bitten Sie nach der Einrichtung des Connectors den Kollegen, die Buckets in einem bekannten Projekt aufzulisten, Objekte nach Präfix aufzulisten, Bucket- und Objektmetadaten zu überprüfen und genehmigte Dateien zu lesen. Der Connector ist ein von [!DNL Google] gehosteter MCP-Server (Model Context Protocol).

>[!AVAILABILITY]
>
>Der externe [!DNL Google Cloud Storage]-Connector befindet sich in der Beta-Phase. Die Dokumentation und die Funktionalität können sich ändern.

## Connector-Konfiguration {#connector-configuration}

Der Connector-Konfigurationsprozess besteht aus drei separaten Teilen:

* **[!DNL Google Cloud]:** Ein [!DNL Google Cloud] bereitet die Abrechnung, die [!DNL Cloud Storage]-API und die Identitäts- und Zugriffsverwaltung (IAM) für Mitglieder vor. Der Administrator bereitet auch einen OAuth-Client vor, dessen Eigentümer Ihr Unternehmen ist.
* **Einrichten der Organisation:** Ein Mitarbeiter-Administrator konfiguriert den Connector einmal für die gesamte Organisation. Der Administrator registriert die Coworker-Umleitungs-URL, gibt die OAuth-Client-Anmeldeinformationen ein und wählt die Tools aus, die Mitglieder verwenden können.
* **Mitglied anmelden** Jedes Mitglied meldet sich mit seinem eigenen [!DNL Google] an. Mitglieder können nur auf die Buckets und Objekte zugreifen, die [!DNL Google Cloud] IAM für ihr Konto zulässt.

Der Connector ist schreibgeschützt. Es fordert den `https://www.googleapis.com/auth/devstorage.read_only` Umfang an und bietet nur Lesetools. Ihr Unternehmen stellt eine eigene [!DNL Google] OAuth-Anwendung bereit. Es gibt keine von Adobe verwaltete OAuth-Anwendung für diesen Connector.

Beim Speichern der Organisationskonfiguration werden weder Mitglieder angemeldet noch [!DNL Cloud Storage] Berechtigungen erteilt. Jedes Mitglied muss bereits über den erforderlichen IAM-Zugriff verfügen und sich separat anmelden.

## Voraussetzungen {#prerequisites}

Bevor Sie beginnen, stellen Sie Folgendes sicher:

* **Zur [!DNL Google Cloud]:** Ein Projekt mit aktivierter Abrechnung und [!DNL Cloud Storage]-API, Buckets mit genehmigten Daten, IAM-Grants für Mitglieder und einem [!DNL Google] OAuth-Client vom Typ **[!UICONTROL Web-Anwendung]**.
* **Für die Einrichtung einer Organisation:** Ein Konto mit der Berechtigung zum Verwalten von Organisations-Connectoren in einem Kollegen. Sie benötigen außerdem die OAuth-Client-ID und das Client-Geheimnis oder vorhandene Unternehmensgeheimnisse, die diese enthalten.
* **Für die Anmeldung als Mitglied:** Ein [!DNL Google] Konto, das die Zielgruppe der OAuth-Anwendung und [!DNL Google Cloud] IAM beide zulassen.

Machen Sie sich mit der Projekt-ID und den Buckets vertraut, die die Mitglieder lesen möchten. Der Connector verfügt über kein Tool zum Auflisten von Projekten. Der OAuth-Client kann zu einem anderen Projekt gehören als die Buckets.

## Vorbereiten von Google Cloud {#prepare-google-cloud}

Bereiten Sie vor dem Konfigurieren des Connectors in Coworker Ihr [!DNL Google Cloud]-Projekt und den Mitgliederzugriff vor. Bei erfolgreicher [!DNL Google] Anmeldung werden keine Speicherberechtigungen erteilt.

### Projekt und IAM vorbereiten {#prepare-project-iam}

Ein [!DNL Google Cloud] führt die folgenden Schritte aus:

1. Wählen oder erstellen Sie ein Projekt in der [Google Cloud-Konsole](https://console.cloud.google.com/).
1. Verknüpfen Sie für jedes Projekt, das Buckets enthält, ein Abrechnungskonto.

   Der schreibgeschützte Zugriff ist nicht kostenlos. Es können weiterhin Speicher-, Betriebs-, Abruf- und Netzwerkgebühren anfallen. Weitere Informationen finden Sie unter [Cloud-Speicherpreise](https://cloud.google.com/storage/pricing).

1. Aktivieren Sie **[!UICONTROL Cloud-Speicher-API]** in jedem relevanten Projekt. Wenn der OAuth-Client zu einem separaten Projekt gehört, aktivieren Sie die API auch in diesem Projekt.
1. Gewähren Sie Mitgliedern in der folgenden Tabelle die am wenigsten privilegierten Rollen. Eine verwaltete Gruppe ist Einzelkonten vorzuziehen.

| Rolle | Wohin gewähren | Zweck |
| --- | --- | --- |
| [!UICONTROL MCP Tool-Benutzer] (`roles/mcp.toolUser`) | Das für MCP-Aufrufe verwendete Projekt | MCP-Tool-Aufrufe durchführen (`mcp.tools.call`). |
| [!UICONTROL Storage Bucket Viewer] (`roles/storage.bucketViewer`) oder eine benutzerdefinierte schreibgeschützte Rolle | Das Projekt, das die Buckets enthält | Auflisten von Buckets und Lesen von Bucket-Metadaten (`storage.buckets.list` und `storage.buckets.get`). |
| [!UICONTROL Speicherobjekt-Viewer] (`roles/storage.objectViewer`) | Jeder autorisierte Bucket oder die Projektmitglieder können alle zugehörigen Buckets lesen | Listenobjekte, Metadaten von Objekten lesen und Objektinhalte lesen (`storage.objects.list` und `storage.objects.get`). |

Gewähren Sie &quot;[!UICONTROL &#x200B; Admin“ nicht &#x200B;] Listeneinträgen. Mitglieder ohne Berechtigung zum Auflisten von Buckets können weiterhin einen autorisierten Bucket lesen, wenn sie dessen Namen angeben. Weitere Informationen finden Sie unter [Cloud-Speicher-IAM](https://docs.cloud.google.com/storage/docs/access-control/iam-roles) in der [!DNL Google Cloud].

[!DNL Google] bietet außerdem eine optionale IAM-Ablehnungsrichtlinie, die Lese- und Schreib-MCP-Tools für andere MCP-Clients blockiert. Der Coworker -Connector verwendet bereits eine schreibgeschützte Tool-Auswahl und einen schreibgeschützten Bereich. Überprüfen Sie die projektweiten Auswirkungen mit Ihrem [!DNL Google Cloud], bevor Sie die Richtlinie anwenden. Weitere Informationen finden Sie unter [Verhindern der Verwendung des Lese-/Schreib-MCP-](https://docs.cloud.google.com/mcp/prevent-read-write-tool-use).

### Verbindungseinstellungen {#connection-settings}

Der -Kollege verwendet die folgenden Verbindungseinstellungen. Diese Werte werden nicht in das Dialogfeld „Setup“ eingegeben.

| Einstellung | Wert |
| --- | --- |
| MCP Server URL | `https://storage.googleapis.com/storage/mcp` (nur globaler Endpunkt) |
| Transport | Streamable HTTP |
| Autorisierungs-Server | `https://accounts.google.com/` |
| Angeforderter Umfang | `https://www.googleapis.com/auth/devstorage.read_only` |

Weitere Informationen finden Sie unter [Verwenden des Remote-MCP-Servers von Cloud Storage](https://docs.cloud.google.com/storage/docs/use-cloud-storage-mcp) und [Authentifizieren bei Google-MCP](https://docs.cloud.google.com/mcp/authenticate-mcp) in der [!DNL Google Cloud].

## Konfigurieren des Connectors für Ihre Organisation {#configure-organization}

Administratoren stellen den [!DNL Google Cloud Storage]-Connector für alle Personen in der Organisation zur Verfügung. Änderungen auf der Seite „Organisation“ gelten für alle Mitglieder Ihrer Organisation.

1. Öffnen Sie **[!UICONTROL Anpassungen]**, wählen Sie **[!UICONTROL Organisation]** und dann **[!UICONTROL Externe Connectoren]** aus. Wählen Sie auf der Karte &lbrace;0 **Google Cloud Storage**&#x200B;[!UICONTROL &#x200B; die Option „Konfigurieren &#x200B;]&#x200B;**aus.**

   Wenn der Connector bereits konfiguriert ist, öffnen Sie stattdessen die gespeicherte Konfiguration.

1. Kopieren Sie **[!UICONTROL Dialogfeld &quot;Google Cloud-Speicher für Ihr]** konfigurieren“ unter **[!UICONTROL Ihr Google-Programm]** die vollständige **[!UICONTROL Umleitungs-URL]**.

   Die Umleitungs-URL unterscheidet sich je nach Umgebung und Region. Kopieren Sie immer den genauen Wert aus dem Dialogfeld. Verwenden Sie nicht die URL der Coworker-Seite in Ihrem Browser, die MCP-Server-URL oder eine Umleitungs-URL aus einer anderen Umgebung.

1. Bereiten Sie den OAuth-Client für Ihr Unternehmen in der [Google-Authentifizierungsplattform vor](https://console.cloud.google.com/auth/overview):

   1. Konfigurieren Sie **[!UICONTROL Branding]** und **[!UICONTROL Audience]** für Ihr Unternehmen. Fügen Sie für eine externe App in Testing die vorgesehenen Mitglieder als Testbenutzer hinzu. Vervollständigen Sie die [!DNL Google] Veröffentlichungs- und Verifizierungsanforderungen, die vor einer breiteren Verwendung gelten.
   1. Fügen **[!UICONTROL in &quot;]**&quot; den `https://www.googleapis.com/auth/devstorage.read_only` ein. Der Connector benötigt keine Lese-/Schreib- oder Vollsteuerungsumfänge.
   1. Erstellen **[!UICONTROL unter]** Clients) einen OAuth-Client, dessen **[!UICONTROL Anwendungstyp]** auf &quot;**[!UICONTROL &quot;]**.
   1. Fügen Sie die kopierte Umleitungs-URL zu **[!UICONTROL autorisierte Umleitungs-URIs)]**. Wenn ein Client mehrere Umgebungen betreut, registrieren Sie die Umleitungs-URL jeder Umgebung.
   1. Rufen Sie **[!UICONTROL Client-ID]** und **[!UICONTROL Client-Geheimnis]** durch den genehmigten Prozess zur Handhabung geheimer Daten in Ihrem Unternehmen ab.

   Mitglieder autorisieren diese OAuth-Anwendung, deren Eigentümer Ihre Organisation ist. Halten Sie die Anmeldeinformationen von Chats, Tickets und Dokumentationen fern.

1. Wählen **[!UICONTROL unter „Woher die Anmeldeinformationen kommen]** eine der folgenden Optionen aus:

   * **[!UICONTROL Neu eingeben]:** Geben Sie die **[!UICONTROL Google OAuth-Client-ID]** und das **[!UICONTROL Google OAuth-Client-Geheimnis]**. Coworker speichert die Werte, die Sie als Organisationsgeheimnisse eingeben.
   * **[!UICONTROL Vorhandene geheime Daten verwenden]:** Wählen Sie die gespeicherten Unternehmensgeheimnisse aus, die die Client-ID und das Client-Geheimnis enthalten.

   Verwenden Sie keine persönlichen Geheimnisse für einen Organisations-Connector.

   ![Konfigurieren Sie den Google-Cloud-Speicher für Ihr Unternehmen. Im Dialogfeld werden eine redigierte Umleitungs-URL, die Optionen Neu eingeben und Vorhandenes Geheimnis verwenden, die Felder Google OAuth-Client-ID und Client-Geheimnis sowie der Hinweis Bevor sich anmelden kann angezeigt.](./assets/google-cloud-storage/org-configure.png){width="500" zoomable="yes"}

1. Erweitern Sie **[!UICONTROL Durchsuchen und lesen (5 von 5)]**. Lassen Sie alle fünf Tools ausgewählt oder wählen Sie nur die Tools aus, die die Mitglieder benötigen. Sie müssen mindestens ein Tool auswählen. Weitere Informationen finden Sie unter [Verfügbare Tools](#available-tools).

   Überprüfen Sie unter **[!UICONTROL Zugriff und]**) die **[!UICONTROL Schreibgeschützter Zugriff]** und **[!UICONTROL Jede Person meldet sich separat]**. Wählen Sie dann **[!UICONTROL Verbindung speichern]**.

   ![Im Abschnitt Für Benutzer verfügbare Tools sind alle fünf Tools zum Durchsuchen und Lesen ausgewählt, gefolgt vom schreibgeschützten Zugriff und der separaten Anmeldung durch jede Person.](./assets/google-cloud-storage/org-tools.png){width="500" zoomable="yes"}

1. Überprüfen Sie die gespeicherten **[!UICONTROL google-cloud-storage]**-Connector-Details.

   | Einstellung | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Quelle]** | Die MCP-Server-URL, `https://storage.googleapis.com/storage/mcp`. |
   | **[!UICONTROL Authentifizierung]** | Die Authentifizierungsmethode, `google-cloud-storage_login`. |
   | **[!UICONTROL Verbindung]** | Ihr eigener Anmeldestatus. |
   | **[!UICONTROL Tools]** | Die für Mitglieder ausgewählten Werkzeuge mit den Steuerelementen **[!UICONTROL Alle auswählen]** und **[!UICONTROL Löschen]** und einer Anzahl ausgewählter Werkzeuge. |

   ![Gespeicherte Google-Cloud-Storage-Connector-Details, die die Quelle, die Authentifizierungsmethode, eine Nicht signiert in Verbindung mit einer Anmeldeschaltfläche und fünf von fünf ausgewählten Tools anzeigen.](./assets/google-cloud-storage/org-details.png){width="700" zoomable="yes"}

Der Status **[!UICONTROL Nicht angemeldet]** in den Connector-Details bezieht sich auf Ihre eigene Verbindung, nicht auf die Organisation. Beim Speichern der Organisations-Setup werden Sie oder ein anderes Mitglied nicht angemeldet und der Zugriff auf einen Bucket wird nicht bestätigt. Um den Connector selbst zu verwenden, führen Sie die Schritte unter [Als Mitglied anmelden](#sign-in-as-a-member) aus.

Um die Tools, die den Mitgliedern später zur Verfügung stehen, zu ändern, aktualisieren Sie die Auswahl auf der Seite mit den Connector-Details und wählen Sie dann **[!UICONTROL Werkzeugauswahl speichern]** aus. Mitglieder können die Werkzeugauswahl nicht ändern.

Um den Connector nicht mehr für Ihre Organisation anzubieten, wählen Sie **[!UICONTROL Entfernen]** auf der Seite mit den Connector-Details aus.

### Verfügbare Tools {#available-tools}

Der [!DNL Google Cloud Storage]-Connector bietet die folgenden schreibgeschützten Tools in der Gruppe **[!UICONTROL Durchsuchen und lesen]**:

| Tool | Beschreibung | Erforderliche Berechtigung |
| --- | --- | --- |
| `list_buckets` | Auflisten der Buckets in einem bekannten [!DNL Google Cloud] mit Präfixfilterung und Paginierung. | `storage.buckets.list` zum Projekt |
| `list_objects` | Listen Sie Objekte und Präfixe in einem autorisierten Bucket auf. Die Auflistung ist standardmäßig nicht rekursiv. | `storage.objects.list` auf den Bucket |
| `get_bucket_metadata` | Lesen der Bucket-Konfiguration, z. B. Speicherort, Speicherklasse, Aufbewahrung und Versionierung. | `storage.buckets.get` |
| `get_object_metadata` | Objektgröße lesen, Inhaltstyp, Zeitstempel, Generierung und benutzerdefinierte Metadaten. | `storage.objects.get` |
| `read_object` | Text oder unterstützte binäre Inhalte lesen, bis zu 8 MiB pro Objekt. | `storage.objects.get` |

Für jeden Tool-Aufruf ist außerdem die Berechtigung `mcp.tools.call` erforderlich, normalerweise über die Rolle [!UICONTROL MCP Tool User] für das entsprechende Projekt.

Der Connector bietet weder das veraltete `read_text`-Tool noch die Tools `write_text`, `create_bucket`, `delete_object` und `delete_bucket`. Es gibt keine Option zum Aktivieren der Schreib-Tools. Tools, die [!DNL Google] später zum Server hinzufügt, werden nicht automatisch verfügbar, selbst wenn Sie alle fünf Tools auswählen.

## Als Mitglied anmelden {#sign-in-as-a-member}

Nachdem ein Administrator den Connector konfiguriert hat, meldet sich jedes Mitglied mit seinem eigenen [!DNL Google] an. Sie benötigen das OAuth-Client-Geheimnis nicht, um sich anzumelden.

1. Öffnen Sie **[!UICONTROL Anpassungen]**, wählen Sie **[!UICONTROL Benutzer]** und dann **[!UICONTROL Externe Connectoren]** aus. Wählen Sie auf der Karte **[!UICONTROL Google Cloud-]** Speicher **[!UICONTROL die Option „Anmelden]** aus.

   Vor der Anmeldung wird auf der Karte **[!UICONTROL Nicht angemeldet]** angezeigt. Wenn die Karte &quot;**[!UICONTROL konfiguriert“]**, bitten Sie Ihren Administrator, den [&#x200B; zu konfigurieren](#configure-organization).

1. Wählen Sie auf dem Bildschirm [!DNL Google] **[!UICONTROL Konto auswählen]** das Konto aus, das über den erforderlichen IAM-Zugriff verfügt, oder wählen Sie **[!UICONTROL Anderes Konto verwenden]** aus. Führen Sie alle für Ihr Unternehmen erforderlichen Anmeldeschritte aus, z. B. Single Sign-on (SSO) oder Multifaktor-Authentifizierung (MFA).

   Dieses Konto kann sich von dem Konto unterscheiden, das Sie für einen Kollegen verwenden.

   ![Google Wählen Sie einen Kontobildschirm mit geschwärzten Konten und die Option „Anderes Konto verwenden“.](./assets/google-cloud-storage/member-choose-account.png){width="500" zoomable="yes"}

1. Wenn [!DNL Google] anzeigt, dass **[!UICONTROL Google diese App nicht verifiziert hat]** bestätigen Sie die App und ihren Besitzer mit Ihrem Administrator.

   Wenn Ihr Unternehmen die Verwendung dieser App genehmigt, wählen Sie **[!UICONTROL Weiter]**. Wählen Sie andernfalls **[!UICONTROL Zurück zur Sicherheit]** aus und bitten Sie den App-Inhaber, die Zielgruppen-, Veröffentlichungs- oder Verifizierungsanforderungen zu klären.

   ![Der Google-Bildschirm gibt an, dass Google diese App nicht verifiziert hat, da sie getestet wird. Die Optionen „Weiter“ und „Zurück zu Sicherheitsoptionen“ sind verfügbar.](./assets/google-cloud-storage/member-unverified-app.png){width="500" zoomable="yes"}

   Überprüfen Sie den App-Namen und den angeforderten Zugriff auf dem Einverständnisbildschirm und wählen Sie dann **[!UICONTROL Weiter]** aus. Der Connector fordert **[!UICONTROL Anzeigen Ihrer Daten im Google Cloud-]**) an, was dem schreibgeschützten Bereich entspricht.

   In den Screenshots heißt die App adobe.io. Die App Ihres Unternehmens zeigt einen eigenen Namen an. Dieser Name bedeutet nicht, dass Adobe die OAuth-App bereitstellt.

   >[!IMPORTANT]
   >
   >Fahren Sie nur fort, wenn Sie die App erkennen und Ihr Unternehmen den angeforderten Zugriff genehmigt.

   ![Google-Einverständnisbildschirm, auf dem eine Beispiel-App mit dem Namen adobe.io Zugriff anfordert, um Ihre Daten im Google Cloud-Speicher mit einem geschwärzten Konto und den Schaltflächen „Abbrechen“ und „Fortfahren“ anzuzeigen.](./assets/google-cloud-storage/member-consent.png){width="500" zoomable="yes"}

1. Kehren Sie zu Mitarbeiter zurück und bestätigen Sie, dass die Anmeldung abgeschlossen ist. Überprüfen Sie **[!UICONTROL Tools, die von Ihrem Administrator aktiviert]**, in den Connector-Details. Sie können nur die Tools verwenden, die Ihr Administrator aktiviert hat.

Wenn Ihre Verbindung beendet wird oder Ihre Sitzung abläuft, melden Sie sich erneut an. Wenn sich ein Administrator anmeldet, werden andere Mitglieder nicht angemeldet.

## Überprüfen des Bucket-Zugriffs {#check-bucket-access}

Eine erfolgreiche Anmeldung oder Toolliste bestätigt nicht, dass Sie auf einen bestimmten Bucket zugreifen können. [!DNL Google] erfordert keine Authentifizierung, um die Server-Tools aufzulisten. Um Ihren Zugriff zu bestätigen, starten Sie einen neuen Chat und geben Sie eine schreibgeschützte Eingabeaufforderung ein. Ersetzen Sie die Platzhalter durch genehmigte Ressourcen.

Beispiel-Eingabeaufforderungen:

* „Auflisten der Buckets in Projekt `YOUR_PROJECT_ID`.“
* „Listen Sie bis zu 25 Objekte unter `reports/` in Bucket `YOUR_BUCKET` auf. Überprüfen Sie Größe und Inhaltstyp des `reports/example.txt`, lesen Sie dann die ersten 4096 Byte und fassen Sie sie zusammen.“

Vergewissern Sie sich, dass das Ergebnis den erwarteten Behälter oder das erwartete Objekt enthält. Um Objekte in verschachtelten Präfixen aufzulisten, fordern Sie explizit eine rekursive Auflistung an. Überprüfen Sie die Objektmetadaten, bevor Sie ein Objekt lesen.

## Beschränkungen und Datenverarbeitung {#limits-data-handling}

Beachten Sie bei der Verwendung des -Connectors die folgenden Einschränkungen und Überlegungen zur Datenverarbeitung:

* **Projekt-ID** Geben Sie in Ihrer Anfrage eine Projekt-ID an. Der Connector kann keine Projekte auflisten.
* **Präfixe:** Objektpräfixe sind literale Namen, keine echten Ordner. Listeneinträge sind standardmäßig nicht rekursiv und geben Ergebnisse in -Seiten zurück.
* **Seitengröße:** Eine Listenseite kann bis zu 1.000 Elemente enthalten. Verwenden Sie eine kleine Seitengröße, z. B. 25 bis 100, und ein schmales Präfix.
* **Objektgröße:** Die maximale Objektgröße für einen Lesevorgang beträgt 8 MiB. Das Lesen nur eines Teils eines größeren Objekts umgeht diese Grenze nicht. Die Unterstützung für Binärdateien hängt vom Modell und Client ab.
* **Kosten und Kontingente:** Es können Speicherungs-, Anfrage-, Abruf- und Netzwerkgebühren anfallen. [!DNL Google] gilt auch für den MCP-Server. Weitere Informationen finden Sie unter [Cloud Storage MCP-Kontingente](https://docs.cloud.google.com/storage/quotas#gcs-mcp).
* **Datenverarbeitung:** Objektinhalte, Namen und benutzerdefinierte Metadaten treten in Ihre Konversation mit einem Kollegen ein. Nur genehmigte Daten verwenden.
* **Auditprotokolle:** [!DNL Cloud Storage] werden nur dann in [!DNL Cloud Audit Logs] angezeigt, wenn die entsprechenden Datenzugriffsprotokolle aktiviert sind.

Der Connector kann keine Dateien oder Buckets hochladen, überschreiben, erstellen oder löschen. Außerdem können keine Zusammenfassungen in [!DNL Cloud Storage] gespeichert werden.

## Fehlerbehebung beim Zugriff {#troubleshoot-access}

Wenn die Anmeldung oder der Zugriff fehlschlägt, wenden Sie sich an Ihren Administrator, um Folgendes zu überprüfen:

| Problem | Was zu überprüfen ist |
| --- | --- |
| Die Karte zeigt &quot;**[!UICONTROL konfiguriert]** | Speichern Sie die Organisationsverbindung für die aktive Organisation. |
| `redirect_uri_mismatch` | Registrieren Sie die exakte **[!UICONTROL Umleitungs-URL]** im Dialogfeld „Mitarbeiter“ auf **[!UICONTROL OAuth-Client (]**). |
| `invalid_client` | Überprüfen Sie den Client-Typ, die Client-ID und das Client-Geheimnis sowie die ausgewählten Unternehmensgeheimnisse. |
| `access_denied` oder eine nicht verifizierte App-Warnung | Überprüfen Sie die App-Zielgruppe, die Testbenutzerberechtigung und den Verifizierungsstatus beim App-Besitzer. Keine unbekannte App genehmigen. |
| HTTP 401, oder Ihre Sitzung beendet | Melden Sie sich erneut an. |
| `mcp.tools.call` wird verweigert | Überprüfen Sie die [!UICONTROL MCP Tool-Benutzer]-Rolle und alle geltenden IAM-Ablehnungsrichtlinien. |
| Bucket-Auflistung wird verweigert, aber ein bekannter Bucket ist lesbar | Überprüfen Sie die `storage.buckets.list` für das Projekt. Mit Objektberechtigungen allein können Sie keine Buckets in einem Projekt auflisten. |
| Bucket-Metadaten werden abgelehnt | Überprüfen Sie die Berechtigung `storage.buckets.get` . |
| Objektauflistung oder Lesen wird verweigert | Überprüfen Sie die [!UICONTROL Storage Object Viewer]-Rolle auf dem Bucket und das [!DNL Google] Konto, mit dem Sie sich angemeldet haben. |
| `SERVICE_DISABLED` | Aktivieren Sie die [!DNL Cloud Storage]-API in dem Projekt, das im Fehler genannt wurde. |
| HTTP 403, für das Abrechnung erforderlich ist | Prüfen Sie die Fakturierung für das Projekt, das die Buckets enthält, einschließlich des Projekts in Ihrer `list_buckets`. |
| Beim Lesen `OutOfRange` | Das -Objekt überschreitet das Limit von 8 MB. Verwenden Sie eine genehmigte Alternative außerhalb dieses Connectors. |
| Ein Tool fehlt | Aktivieren Sie die Tool-Auswahl, die Ihr Administrator gespeichert hat. Veraltete und Schreib-Tools sind nicht verfügbar. |
| Eine Anfrage zum Hochladen, Überschreiben, Erstellen oder Löschen schlägt fehl | Der Connector ist schreibgeschützt und unterstützt diese Aktionen nicht. |
