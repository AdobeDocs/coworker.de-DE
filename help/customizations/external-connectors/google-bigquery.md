---
title: Externer Google BigQuery-Connector
description: Erfahren Sie, wie Sie den externen Google BigQuery-Connector in CX Enterprise Coworker mit Ihrer Google OAuth-App einrichten und sich im Chat anmelden, um BigQuery-Daten abzufragen.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Dieser Connector befindet sich in der Betaphase."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: a7c55df451e12b78e68050118f649952b705f4a9
workflow-type: tm+mt
source-wordcount: '2213'
ht-degree: 0%
---

# Externer Google BigQuery-Connector {#google-bigquery}

Verwenden Sie den externen Connector [!DNL Google BigQuery] , um Ihre [!DNL BigQuery] in Adobe CX Enterprise Coworker zu durchsuchen und abzufragen. Bitten Sie nach der Einrichtung des Connectors den Kollegen, Datensätze und Tabellen aufzulisten, ein Tabellenschema zu erklären und schreibgeschützte SQL-Abfragen auszuführen. Der Connector ist ein von [!DNL Google] unter `https://bigquery.googleapis.com/mcp` gehosteter MCP-Server (Model Context Protocol).

>[!AVAILABILITY]
>
>Der externe [!DNL Google BigQuery]-Connector befindet sich in der Beta-Phase. Die Dokumentation und die Funktionalität können sich ändern.

## Connector-Konfiguration {#connector-configuration}

Der Connector-Konfigurationsprozess besteht aus drei separaten Teilen:

* **[!DNL Google Cloud]:** Ein [!DNL Google Cloud] bereitet ein Abfrageprojekt vor, aktiviert die [!DNL BigQuery]-API und gewährt den Mitgliedern die erforderlichen Rollen für Identitäts- und Zugriffsverwaltung (IAM).
* **Einrichten der Organisation:** Ein Mitarbeiter-Administrator konfiguriert den Connector einmal für die gesamte Organisation. Der Administrator verbindet die [!DNL Google] OAuth-App der Organisation und wählt die Tools aus, die Mitglieder verwenden können.
* **Mitglied anmelden** Jedes Mitglied meldet sich mit seinem eigenen [!DNL Google] an. Mitglieder können nur auf die Projekte und Datensätze zugreifen, auf die ihre [!DNL Google] Identität zugreifen kann.

Der Connector verwendet eine OAuth-App, deren Eigentümer Ihr Unternehmen ist. Adobe stellt keine [!DNL Google] OAuth-App für diesen Connector bereit. Beim Speichern der Organisationskonfiguration werden weder Mitglieder angemeldet noch [!DNL BigQuery] Berechtigungen erteilt. Bei erfolgreicher [!DNL Google]-Anmeldung wird auch kein Datensatzzugriff gewährt, da [!DNL Google Cloud] IAM den Zugriff auf Ihre Daten steuert.

## Voraussetzungen {#prerequisites}

Bevor Sie beginnen, stellen Sie Folgendes sicher:

* **Zur [!DNL Google Cloud]:** Ein [!DNL Google Cloud], der APIs aktivieren, IAM-Rollen gewähren und einen OAuth-Client in der [!DNL Google Auth Platform] erstellen kann.
* **Für die Einrichtung einer Organisation:** Ein Konto mit der Berechtigung zum Verwalten von Organisations-Connectoren in einem Kollegen. Sie benötigen außerdem die Client-ID und das Client-Geheimnis eines [!DNL Google] OAuth-Web-Anwendungs-Clients oder vorhandene Unternehmensgeheimnisse, die diese enthalten.
* **Für die Anmeldung als Mitglied:** Eine [!DNL Google] Identität, die die Zielgruppe der OAuth-App zulässt und die über die erforderlichen IAM-Rollen verfügt.

Kenntnis der ID des Abfrageprojekts und der Datensätze, die Mitglieder lesen sollten. Das Abfrageprojekt führt Abfrageaufträge aus und bezahlt sie. Die Daten können in einem anderen Projekt vorhanden sein, und der OAuth-Client kann auch zu einem anderen Projekt gehören. Bei einem Pilotprojekt kann ein Projekt den OAuth-Client, die Abfrageaufträge und die Datensätze enthalten.

## [!DNL Google Cloud] vorbereiten {#prepare-google-cloud}

Bereiten Sie in [!DNL Google Cloud] den Projekt- und Memberzugriff vor, bevor Sie den Connector in Coworker konfigurieren. Das Erstellen der OAuth-App und das Gewähren des Datenzugriffs sind separate Aufgaben. Mitglieder, die den Connector verwenden, benötigen keine Berechtigung zum Bearbeiten der OAuth-App.

### Abfrageprojekt vorbereiten {#prepare-query-project}

Ein [!DNL Google Cloud] bereitet das Projekt vor, das Abfrageaufträge ausführt:

1. Wählen oder erstellen Sie in der {0](https://console.cloud.google.com/) Google Cloud-Konsole ein Projekt.[
1. Aktivieren Sie die [!DNL BigQuery]-API, falls sie noch nicht aktiviert ist. Durch Aktivierung der API wird auch der [!DNL BigQuery] Remote-MCP-Server aktiviert.
1. Wählen Sie Abrechnung oder die [BigQuery-Sandbox](https://docs.cloud.google.com/bigquery/docs/sandbox) und legen Sie dann die entsprechenden täglichen [benutzerdefinierten Abfragekontingente](https://docs.cloud.google.com/bigquery/docs/custom-quotas) für das Abfrageprojekt fest.

>[!IMPORTANT]
>
>Für schreibgeschützte Abfragen können weiterhin Gebühren anfallen. [!DNL BigQuery] Kosten hängen von den Bytes ab, die eine Abfrage scannt, und nicht von der Anzahl der zurückgegebenen Zeilen. Eine `LIMIT`-Klausel steuert die zurückgegebenen Zeilen, reduziert jedoch im Allgemeinen nicht die gescannten Bytes. Verwenden Sie Probeläufe, explizite Spalten, Partitionsfilter und tägliche Abfragekontingente, um die Kosten zu kontrollieren.

Weitere Informationen finden Sie unter [Verwenden des Remote-MCP-Servers BigQuery](https://docs.cloud.google.com/bigquery/docs/use-bigquery-mcp) in der [!DNL Google Cloud].

### IAM-Rollen erteilen {#grant-iam-roles}

Gewähren Sie den [!DNL Google] Identitäten Ihrer Mitglieder die folgenden Rollen. Verwenden Sie nach Möglichkeit eine verwaltete Gruppe und bevorzugen Sie den Datenzugriff auf Datensatzebene.

| Rolle | Wo sie gewährt wird | Zweck |
| --- | --- | --- |
| [!UICONTROL MCP Tool-Benutzer] (`roles/mcp.toolUser`) | Die für MCP-Aufrufe verwendeten Projekte | MCP-Tool-Aufrufe durchführen. |
| [!UICONTROL BigQuery Job-Benutzer] (`roles/bigquery.jobUser`) | Das Abfrageprojekt | Abfrageaufträge ausführen. |
| [!UICONTROL BigQuery Data Viewer] (`roles/bigquery.dataViewer`) | Die autorisierten Datensätze oder Datenprojekte | Lesen von Daten und Metadaten. |

Gewähren Sie nicht, [!UICONTROL BigQuery Data Editor], [!UICONTROL BigQuery Data Owner] oder [!UICONTROL BigQuery Admin] nur diesen schreibgeschützten Connector zu verwenden. Als zusätzliche Sicherheitsmaßnahme sollten Sie eine Richtlinie [Ablehnen“ für Lese-/Schreib-MCP-Tools ](https://docs.cloud.google.com/mcp/prevent-read-write-tool-use). Bitten Sie Ihren [!DNL Google Cloud], zunächst den Umfang der Ablehnungsrichtlinie zu überprüfen, da sie sich auf andere [!DNL Google] MCP-Clients und -Services auswirken kann. Weitere Informationen finden Sie unter [BigQuery IAM-Rollen und -](https://docs.cloud.google.com/bigquery/docs/access-control).

## Konfigurieren des Connectors für Ihre Organisation {#configure-organization}

Administratoren stellen den [!DNL Google BigQuery]-Connector für alle Personen in der Organisation zur Verfügung. Änderungen auf der Seite „Organisation“ gelten für alle Benutzer in Ihrer Organisation.

1. Öffnen Sie **[!UICONTROL Anpassungen]**, wählen Sie **[!UICONTROL Organisation]** und dann **[!UICONTROL Externe Connectoren]** aus. Wählen Sie auf der Karte **[!UICONTROL Google BigQuery]** die Option **[!UICONTROL Konfigurieren]** aus.

   Wenn der Connector bereits konfiguriert ist, zeigt die Karte stattdessen **[!UICONTROL Konfiguration anzeigen]** an.

1. Kopieren Sie **[!UICONTROL Dialogfeld &quot;Google BigQuery für Ihr]** konfigurieren“ die **[!UICONTROL Umleitungs-]** unter **[!UICONTROL Ihr Google-Programm]**.

   Die Umleitungs-URL unterscheidet sich zwischen Umgebungen und Regionen, sodass Sie immer den genauen Wert aus dem Dialogfeld kopieren müssen. Verwenden Sie nicht die URL der Coworker-Seite in Ihrem Browser oder die [!DNL BigQuery] MCP-Server-URL. Wenn ein OAuth-Client mehrere Umgebungen unterstützt, registrieren Sie jede erforderliche Umleitungs-URL separat.

1. Bereiten Sie in der [Google](https://console.cloud.google.com/auth/overview)Authentifizierungsplattform den OAuth-Client Ihrer Organisation vor:

   1. Konfigurieren von **[!UICONTROL Branding]** und **[!UICONTROL Audience]**. Fügen Sie für eine externe App in Testing die vorgesehenen Mitglieder als Testbenutzer hinzu. Vervollständigung der Veröffentlichungs- und Prüfanforderungen von [!DNL Google] vor einer umfassenderen Verwendung.
   1. Fügen **[!UICONTROL in &quot;]**&quot; den `https://www.googleapis.com/auth/bigquery` hinzu.
   1. Erstellen **[!UICONTROL unter]** einen OAuth-Client mit dem Anwendungstyp **[!UICONTROL Web-Anwendung]** oder wählen Sie einen aus.
   1. Fügen Sie die kopierte Umleitungs-URL zu **[!UICONTROL autorisierte Umleitungs-URIs)]**.
   1. Rufen Sie **[!UICONTROL Client-ID]** und **[!UICONTROL Client-Geheimnis]** durch den genehmigten Prozess zur Handhabung geheimer Daten in Ihrem Unternehmen ab.

   Mitglieder autorisieren diese App, der Ihr Unternehmen gehört, nicht eine von Adobe bereitgestellte App. Halten Sie das Client-Geheimnis aus Screenshots, Chats und der Dokumentation fern.

1. Wählen **[!UICONTROL unter „Woher die Anmeldeinformationen kommen]** eine der folgenden Optionen aus:

   * **[!UICONTROL Neu eingeben]:** Geben Sie die **[!UICONTROL Google OAuth-Client-ID]** und das **[!UICONTROL Google OAuth-Client-Geheimnis]**. Coworker speichert die Werte, die Sie als Organisationsgeheimnisse eingeben.
   * **[!UICONTROL Vorhandene geheime Daten verwenden]:** Wählen Sie die gespeicherten Unternehmensgeheimnisse aus, die die Client-ID und das Client-Geheimnis enthalten.

   Verwenden Sie keine persönlichen Geheimnisse für einen Organisations-Connector.

   ![Konfigurieren Sie Google BigQuery für Ihr Unternehmen. Daraufhin wird der Abschnitt „Verbindungsdetails“ mit einer redigierten Umleitungs-URL und den Feldern für die Anmeldeinformationen angezeigt, wobei alle sieben Erkunden- und Abfrage-Tools ausgewählt sind sowie die drei Hinweise zu Zugriff und Berechtigungen.](./assets/google-bigquery/org-configure.png){width="500" zoomable="yes"}

1. Erweitern Sie die **[!UICONTROL Erkunden und Abfragen]**-Toolgruppe. Lassen Sie alle sieben Tools ausgewählt oder wählen Sie nur die Tools aus, die Ihre Mitglieder benötigen. Sie müssen mindestens ein Tool auswählen. Weitere Informationen finden Sie unter [Verfügbare Tools](#available-tools).

   Lesen Sie die Hinweise unter **[!UICONTROL Zugriff und Berechtigungen]**:

   * **[!UICONTROL Schreibgeschützte Tools]:** Der OAuth-Umfang ist breit und verhindert Änderungen nicht von selbst. Lassen Sie die IAM-Rollen Ihrer Mitglieder schreibgeschützt.
   * **[!UICONTROL Schreibgeschützte Abfragen können Gebühren verursachen]:** Verwenden Sie Probeläufe und Abfragekontingente. Eine `LIMIT`-Klausel steuert die zurückgegebenen Zeilen, nicht unbedingt die gescannten Bytes.
   * **[!UICONTROL Jede Person meldet sich separat an]:** Jedes Mitglied benötigt die erforderlichen IAM-Rollen.

   Wählen Sie **[!UICONTROL Verbindung speichern]**. Die Organisationskarte zeigt **[!UICONTROL Konfiguration gespeichert]** und **[!UICONTROL Konfiguration anzeigen]**.

Beim Speichern der Konfiguration werden weder Sie noch ein Mitglied bei [!DNL Google] angemeldet. Das Speichern bestätigt auch nicht, dass jemand einen Datensatz abfragen kann. Um den Connector selbst zu verwenden, führen Sie die Schritte unter [Als Mitglied anmelden](#sign-in-as-a-member) aus.

### Verfügbare Tools {#available-tools}

Der [!DNL Google BigQuery]-Connector bietet die folgenden schreibgeschützten Tools:

| Tool | Beschreibung |
| --- | --- |
| `list_dataset_ids` | Auflisten der Datensätze in einem von Ihnen angegebenen Projekt. |
| `get_dataset_info` | Lesen der Metadaten eines Datensatzes. |
| `list_table_ids` | Auflisten der Tabellen und Ansichten in einem Datensatz. |
| `get_table_info` | Lesen des Schemas und der Metadaten einer Tabelle. |
| `execute_sql_readonly` | Führen Sie schreibgeschützte SQL-Abfragen aus oder versuchen Sie einen Probelauf, um die Bytes zu schätzen, die eine Abfrage scannt. |
| `get_query_results` | Rufen Sie die Ergebnisse einer Abfrage ab oder überprüfen Sie eine langwierige Abfrage. |
| `get_job` | Überprüfen Sie den Status, die Fehler und Statistiken eines Abfrageauftrags. |

Lassen Sie für Abfrage-Workflows `execute_sql_readonly`, `get_query_results` und `get_job` gemeinsam ausgewählt, damit ein Kollege einem lang laufenden Abfrageauftrag folgen kann. Coworker bietet keine `execute_sql`- und `cancel_job`-Tools vom [!DNL BigQuery] MCP-Server. Tools, die [!DNL Google] später zum Server hinzufügen, werden nicht automatisch aktiviert. Weitere Informationen zu Tools finden Sie in der [BigQuery MCP-Referenz](https://docs.cloud.google.com/bigquery/docs/reference/mcp).

Beachten Sie die folgenden Einschränkungen bei der Verwendung der Tools:

* [!DNL Google] dokumentiert eine Beschränkung von 3.000 Zeilen für Abfrageergebnisse und eine standardmäßige Zeitüberschreitung der Abfrage von drei Minuten. Verwenden Sie den Connector nicht, um vollständige Tabellen zu exportieren.
* Die Tools können keine Projekte auflisten. Geben Sie in Ihrer Anfrage eine bekannte Projekt-ID an.
* Schreibgeschütztes SQL unterstützt keine Anweisungen, die Daten oder Ressourcen ändern, oder Abfragen in [!DNL Google Drive] externen Tabellen.
* Abfrageergebnisse, Schemata, Zugriffslisten für Datensätze und SQL können im Chat angezeigt werden. Stellen Sie sicher, dass der Zugriff den Richtlinien Ihrer Organisation zur Datenverarbeitung entspricht.

## Als Mitglied anmelden {#sign-in-as-a-member}

Nachdem ein Administrator den Connector konfiguriert hat, meldet sich jedes Mitglied mit seinem eigenen [!DNL Google] an. Sie benötigen das OAuth-Client-Geheimnis nicht, um sich anzumelden.

1. Öffnen Sie **[!UICONTROL Anpassungen]**, wählen Sie **[!UICONTROL Benutzer]** und dann **[!UICONTROL Externe Connectoren]** aus. Wählen Sie auf der Karte **[!UICONTROL Google BigQuery]**, die **[!UICONTROL Nicht angemeldet]** anzeigt, **[!UICONTROL Anmelden]** aus.

   Wenn auf der Karte steht, dass ein Administrator den Connector einrichten muss, bitten Sie Ihren Administrator, den [ zu konfigurieren](#configure-organization).

1. Wählen Sie auf dem Bildschirm [!DNL Google] **[!UICONTROL Konto auswählen]** das Konto aus, das über den erforderlichen IAM-Zugriff verfügt, oder wählen Sie **[!UICONTROL Anderes Konto verwenden]** aus. Führen Sie dann alle für Ihr Unternehmen erforderlichen Anmeldeschritte aus, z. B. Single Sign-on (SSO) oder Multi-Faktor-Authentifizierung (MFA).

   Dieses Konto kann sich von dem Konto unterscheiden, das Sie für einen Kollegen verwenden.

   ![Google Wählen Sie einen Kontobildschirm mit drei geschwärzten Konten und die Option „Anderes Konto verwenden“.](./assets/google-bigquery/member-choose-account.png){width="500" zoomable="yes"}

1. Wenn [!DNL Google] anzeigt, dass **[!UICONTROL Google diese App nicht verifiziert hat]** bestätigen Sie die App und ihren Besitzer mit Ihrem Administrator. Fahren Sie nur fort, wenn Ihre Organisationsrichtlinie für Test-Apps dies zulässt. Wählen Sie andernfalls **[!UICONTROL Zurück zur Sicherheit]** aus und bitten Sie den App-Inhaber, die Zielgruppen-, Veröffentlichungs- oder Verifizierungsanforderungen zu klären.

   ![Google hat diese App-Warnung nicht mit einer E-Mail mit dem Besitzer der redigierten App, einem erweiterten Link und einer Schaltfläche „Zurück zur Sicherheit“ verifiziert.](./assets/google-bigquery/member-unverified-app.png){width="500" zoomable="yes"}

   Überprüfen Sie den App-Namen und den angeforderten Zugriff auf dem Einverständnisbildschirm. Wählen Sie dann **[!UICONTROL Weiter]** aus, um den Einverständnisfluss [!DNL Google] abzuschließen.

   [!DNL Google] bittet um Erlaubnis, Ihre [!DNL BigQuery]-Daten anzuzeigen und zu verwalten und die E-Mail-Adresse Ihres [!DNL Google]-Kontos zu sehen. Dies ist der standardmäßige [!DNL BigQuery], auch wenn Coworker nur schreibgeschützte Tools bietet.

   In den Screenshots heißt die App adobe.io. Die App Ihres Unternehmens zeigt einen eigenen Namen an. Dieser Name bedeutet nicht, dass Adobe die OAuth-App bereitstellt.

   >[!IMPORTANT]
   >
   >Fahren Sie nur fort, wenn Sie die App erkennen und Ihr Unternehmen den angeforderten Zugriff genehmigt.

   ![Google-Einverständnisbildschirm, auf dem eine Beispiel-App mit dem Namen adobe.io Zugriff anfordert, um Ihre Daten in Google BigQuery anzuzeigen und zu verwalten, mit einer nicht verifizierten App-Warnung, einem reduzierten Konto und den Schaltflächen Abbrechen und Fortfahren.](./assets/google-bigquery/member-consent.png){width="500" zoomable="yes"}

1. Kehren Sie zu Mitarbeiter zurück und überprüfen Sie **[!UICONTROL Tools, die von Ihrem Administrator aktiviert wurden]** in den Connector-Details. Mitglieder können die Werkzeuge anzeigen, aber die Werkzeugauswahl nicht ändern. Um die Verbindung zu überprüfen, wählen Sie **[!UICONTROL Test]** aus.

   ![Google-BigQuery-Connector-Details für ein Mitglied, die den Status „Verbunden“, die Quelle, die Authentifizierungsmethode, die Tool-Zeitüberschreitung, eine Anmeldung in Verbindung mit den Schaltflächen „Abmelden“ und „Tools neu laden“ und eine Meldung anzeigen, dass die Verbindung beendet wurde, sowie die ersten von Ihrem Administrator aktivierten Tools.](./assets/google-bigquery/member-details.png){width="700" zoomable="yes"}

Eine erfolgreiche Anmeldung, ein erfolgreicher Test oder eine Liste von Tools bestätigt nicht, dass Sie einen bestimmten Datensatz abfragen können. Um Ihren Zugriff zu bestätigen, [überprüfen Sie Ihren BigQuery-Zugriff](#check-bigquery-access). Wenn der Mitarbeiter sagt, dass die Verbindung beendet wurde, melden Sie sich erneut an.

## Überprüfen des [!DNL BigQuery] {#check-bigquery-access}

Um zu bestätigen, dass Sie Ihre Daten lesen können, starten Sie einen neuen Chat und geben Sie eine schreibgeschützte Eingabeaufforderung ein. Ersetzen Sie die Platzhalter durch Projekte und Tabellen, auf die Ihre [!DNL Google] zugreifen kann.

Beispiel-Eingabeaufforderungen:

* „Listen Sie die Datensätze in Projekt `YOUR_PROJECT_ID` auf.“
* „Überprüfen Sie mithilfe von `YOUR_QUERY_PROJECT_ID` für Abfrageaufträge das Schema der `YOUR_DATA_PROJECT.YOUR_DATASET.YOUR_TABLE`, schätzen Sie den Scan mit einem Probelauf ab und geben Sie dann eine aggregierte Zusammenfassung zurück.“

Bestätigen Sie, dass die Ergebnisse die erwarteten Datensätze oder Daten enthalten. Explizite Spalten, Aggregate und Partitionsfilter sollten Anforderungen für unformatierte Tabelleninhalte vorgezogen werden. Die Benennung eines Projekts in einer Anfrage ändert weder Ihre angemeldete Identität noch gewährt sie Zugriff auf dieses Projekt.

## Fehlerbehebung beim Zugriff {#troubleshoot-access}

Wenn die Anmeldung oder der Zugriff fehlschlägt, wenden Sie sich an Ihren Administrator, um Folgendes zu überprüfen:

| Problem | Was zu überprüfen ist |
| --- | --- |
| Auf der Karte wird angegeben, dass der Connector nicht konfiguriert ist oder dass ein Administrator ihn einrichten muss | Die Organisationskonfiguration wird für Ihre aktive Organisation gespeichert. |
| `redirect_uri_mismatch` | Die genaue **[!UICONTROL Umleitungs-URL]** aus dem Dialogfeld „Mitarbeiter“ wird unter **[!UICONTROL Autorisierte Umleitungs-URIs]** auf dem Webanwendungsclient registriert. |
| `invalid_client` | Die Client-ID und das Client-Geheimnis gehören zum Web-Anwendungs-Client und die ausgewählten Unternehmensgeheimnisse sind korrekt. |
| `access_denied` oder eine Warnung, dass [!DNL Google] die App nicht verifiziert hat | Der App-Inhaber prüft die Zielgruppe, die Berechtigung der Testbenutzer und den Verifizierungsstatus. Genehmigen Sie keine App, die Sie nicht erkennen. |
| Die Verbindung wurde beendet oder das Token ist abgelaufen | Melden Sie sich erneut als Mitglied an. |
| Berechtigung für `mcp.tools.call` verweigert | Die [!UICONTROL MCP Tool-Benutzer]-Rolle und alle geltenden IAM-Ablehnungsrichtlinien. |
| Berechtigung für `bigquery.jobs.create` verweigert | Die Rolle [!UICONTROL BigQuery-]&quot; im Abfrageprojekt. |
| Zugriff für eine Tabelle verweigert | Die [!UICONTROL BigQuery Data Viewer]-Rolle für den Datensatz und das [!DNL Google] Konto, mit dem Sie sich angemeldet haben. |
| `SERVICE_DISABLED` | Die [!DNL BigQuery]-API wird in dem Projekt aktiviert, das durch den Fehler identifiziert wird. |
| Das tägliche Abfragekontingent wurde überschritten | Das Abfragekontingent des Projekts mit dem Projektadministrator. |
| Eine Anfrage zum Einfügen, Aktualisieren, Löschen, Erstellen oder Löschen von Daten schlägt fehl | Der Connector ist schreibgeschützt und unterstützt keine Änderungen an Daten oder Ressourcen. |

Geben Sie bei der Kontaktaufnahme mit dem Support keine Kundengeheimnisse, Zugriffstoken, Autorisierungs-Codes oder Kundendaten frei.
