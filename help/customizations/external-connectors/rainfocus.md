---
title: RAINfocus externer Anschluss
description: Erfahren Sie, wie Sie den externen RainFocus-Connector in CX Enterprise Coworker für Ihr Unternehmen einrichten und sich mit RainFocus anmelden, um Ereignisdaten-Tools im Chat zu verwenden.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Dieser Connector befindet sich in der Betaphase."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: e65f811f1e9c27de372ce924301b68f20ab9c1a6
workflow-type: tm+mt
source-wordcount: '2116'
ht-degree: 0%
---

# Externer RainFocus-Connector {#rainfocus}

Verwenden Sie den externen Connector [!DNL RainFocus] , um mit Ihren [!DNL RainFocus] Ereignisdaten in Adobe CX Enterprise Coworker zu arbeiten. Fragen Sie nach der Einrichtung des Connectors einen Kollegen nach den Sitzungen, Teilnehmern und benutzerdefinierten Attributen, auf die Ihr [!DNL RainFocus]-Konto zugreifen kann. Der Connector verwendet ein [!DNL RainFocus] MCP-Profil, einen von [!DNL RainFocus] gehosteten MCP-Server (Model Context Protocol).

>[!AVAILABILITY]
>
>Der externe [!DNL RainFocus]-Connector befindet sich in der Beta-Phase. Die Dokumentation und die Funktionalität können sich ändern.

## Connector-Konfiguration {#connector-configuration}

Der Connector-Konfigurationsprozess besteht aus drei separaten Teilen:

* **[!DNL RainFocus]:** Ein [!DNL RainFocus] stellt ein MCP-Profil bereit, aktiviert die Tools und stellt die Profil-URL bereit. Jedes Mitglied benötigt ein [!DNL RainFocus] Konto mit der richtigen Rolle.
* **Einrichten der Organisation:** Ein Mitarbeiter-Administrator speichert die MCP-Profil-URL einmal für die gesamte Organisation. Der Connector ermöglicht eine feste Liste von Lesetools.
* **Mitglied anmelden** Jedes Mitglied meldet sich mit seinem eigenen [!DNL RainFocus] an. Mitglieder können nur auf die Daten zugreifen, die ihre [!DNL RainFocus] und das Profil zulassen.

Beim Speichern der Organisationskonfiguration werden keine Mitglieder angemeldet, [!DNL RainFocus] Berechtigungen erteilt oder ein [!DNL RainFocus] ausgeführt. Jedes Mitglied muss sich separat anmelden.

## Voraussetzungen {#prerequisites}

Bevor Sie beginnen, stellen Sie Folgendes sicher:

* **Coworker access:** Ein Coworker-Administratorkonto mit aktivierten Organisationseinstellungen in einer Organisation, in der der [!DNL RainFocus]-Connector verfügbar ist.
* **Ein MCP-Profil:** Ein bereitgestelltes [!DNL RainFocus] MCP-Profil und dessen vollständige HTTPS-Profil-URL, bereitgestellt von Ihrem [!DNL RainFocus]. Weitere Informationen finden Sie unter [Abrufen der MCP-Profil-URL](#get-profile-url).
* **Mitgliederkonten:** Für jedes Mitglied ein [!DNL RainFocus] Konto mit einer Sicherheitsrolle, die Zugriff auf die benötigten Daten gewährt.

Sie geben keine Client-ID, keinen geheimen Client-Schlüssel und kein Zugriffs-Token in Coworker ein. Jedes Mitglied meldet sich mit seinem eigenen Konto bei [!DNL RainFocus] an.

## Vorbereiten [!DNL RainFocus] Zugriffs {#prepare-rainfocus}

Bereiten Sie in [!DNL RainFocus] den Zugriff auf MCP-Profile und -Mitglieder vor, bevor Sie den Connector in Coworker konfigurieren. [!DNL RainFocus] steuert das Profil, seine aktivierten Tools, die Mitgliederrollen und alle Gebühren. Coworker speichert die Profil-URL und die Tool-Liste für Ihre Organisation und die Anmeldung jedes Mitglieds.

### Abrufen der MCP-Profil-URL {#get-profile-url}

[!DNL RainFocus] konfiguriert normalerweise MCP-Profile für seine Kunden auf Grundlage ihrer Anforderungen. Wenn Ihr [!DNL RainFocus]-Administrator das Profil einrichtet, läuft der Prozess wie folgt ab:

1. Öffnen Sie [!DNL RainFocus] **[!UICONTROL Integrationssuite]** > **[!UICONTROL Aktive Profile]** > **[!UICONTROL MCP-Profile]** und erstellen Sie dann ein Profil.
1. Aktivieren Sie nur die Tools, die für Ihren Anwendungsfall erforderlich sind, und lassen Sie die anderen Tools deaktiviert.
1. Kopieren Sie die generierte MCP Server URL. Die URL ist profilspezifisch.

Geben Sie die vollständige URL dem Co-Worker-Administrator, der den Connector konfiguriert. Raten Sie nicht über einen Profilnamen oder erstellen Sie die URL selbst. Weitere Informationen finden Sie in der Ankündigung [RainFocus MCP Profiles](https://www.rainfocus.com/company/news-press/rainfocus-launches-ai-agent-connectivity-for-event-data-with-mcp-profiles/).

### Bestätigen des Mitgliederzugriffs {#confirm-member-access}

Jedes Mitglied meldet sich mit seinem eigenen [!DNL RainFocus] an. Die Sicherheitsrolle des Kontos und die im Profil aktivierten Tools steuern, auf welche Daten ein Mitglied zugreifen kann. Bitten Sie Ihren [!DNL RainFocus], zu bestätigen, dass jedes Mitglied die am wenigsten privilegierte Rolle für seine Aufgaben hat.

## Konfigurieren des Connectors für Ihre Organisation {#configure-organization}

Administratoren stellen den [!DNL RainFocus]-Connector für alle Personen in der Organisation zur Verfügung. Änderungen auf der Seite „Organisation“ gelten für alle Benutzer in Ihrer Organisation. Der **[!UICONTROL Org]**-Bereich wird nur für Administratoren angezeigt, bei denen die Unternehmenseinstellungen aktiviert sind.

1. Öffnen Sie **[!UICONTROL Anpassungen]**, wählen Sie **[!UICONTROL Organisation]** und dann **[!UICONTROL Externe Connectoren]** aus.
1. Suchen Sie die Karte **[!UICONTROL RainFocus]**, die über eine Beta-Kennzeichnung verfügt und &quot;**[!UICONTROL konfiguriert“]**. Wählen Sie **[!UICONTROL Konfigurieren]** aus.

1. Geben **[!UICONTROL im Dialogfeld „RainFocus einrichten]** die **[!UICONTROL Entwicklungsprofil-URL“]**. Verwenden Sie die vollständige MCP-Profil-URL, die von Ihrem [!DNL RainFocus] bereitgestellt wurde.

   Die URL muss mit `https://` beginnen. Sie darf keine Leerzeichen, umgekehrte Schrägstriche, eine Abfragezeichenfolge (`?`), ein Fragment (`#`), einen Benutzernamen oder ein Kennwort, einen nicht standardmäßigen Port oder `.`- oder `..` enthalten. Wenn die URL nicht mit einer Regel übereinstimmt, zeigt der Kollege eine Meldung an, die die Regel beschreibt. Der Mitarbeiter prüft nur das Format der URL. Es wird nicht geprüft, ob das Profil vorhanden ist oder ob Sie es verwenden können.

1. Lesen Sie die Abschnitte **[!UICONTROL Zugriff]** Berechtigungen und **[!UICONTROL Feste Lesetool-Zulassungsliste]**. Der Connector aktiviert alle 10 Lesetools, und Sie können sie in diesem Dialogfeld nicht hinzufügen, entfernen oder bearbeiten. Einige Tools geben personenbezogene Daten der Teilnehmer oder Massenexporte zurück. Weitere Informationen finden Sie unter [Verfügbare Tools](#available-tools).

   ![RainFocus-Dialogfeld einrichten, in dem das leere Feld für die Entwicklungsprofil-URL, der Abschnitt „Zugriff und Berechtigungen“, die feste Zulassungsliste des Lesetools mit 10 Tools und die Schaltfläche „Verbindung speichern“ angezeigt werden.](./assets/rainfocus/org-configure.png){width="500" zoomable="yes"}

1. Wählen Sie **[!UICONTROL Verbindung speichern]**. Während Coworker die Verbindung speichert, können Sie das Formular nicht bearbeiten oder abbrechen.

Wenn das Speichern fehlschlägt, wird im Dialogfeld **[!UICONTROL Verbindung konnte nicht gespeichert werden]** und die eingegebene URL wird beibehalten. Einige Einstellungen werden möglicherweise gespeichert, selbst wenn das Speichern fehlschlägt. Öffnen Sie die Konfiguration erneut und überprüfen Sie sie, bevor Sie es erneut versuchen. Um widersprüchliche Änderungen zu vermeiden, stellen Sie sicher, dass jeweils nur ein Administrator den Connector konfiguriert.

### Überprüfen der gespeicherten Konfiguration {#verify-configuration}

Nachdem Sie die Verbindung gespeichert haben, überprüfen Sie die Konfiguration:

1. Nach dem Speichern werden im Dialogfeld die gespeicherten Connector-Details geöffnet. Kehren Sie zur Liste **[!UICONTROL Externe Connectoren]** zurück und vergewissern Sie sich, dass auf der **[!UICONTROL RainFocus]**-Karte **[!UICONTROL Konfiguration gespeichert]** und **[!UICONTROL Konfiguration anzeigen]**.
1. Laden Sie die Seite neu und wählen Sie dann **[!UICONTROL Konfiguration anzeigen]** aus.
1. Bestätigen Sie die folgenden Details:

   * **[!UICONTROL Source]** zeigt die eingegebene Profil-URL an.
   * **[!UICONTROL Authentifizierung]** ist vorhanden.
   * **[!UICONTROL Toolrichtlinie]** > **[!UICONTROL Zulässige Toolnamen oder -muster]** listet dieselben 10 Tools auf wie der Abschnitt [Verfügbare Tools](#available-tools).

1. Um Ihre eigene Verbindung zu überprüfen, wählen Sie **[!UICONTROL Test]** aus. Wenn Sie von einem Mitarbeiter aufgefordert werden, sich anzumelden, verwenden Sie Ihr eigenes [!DNL RainFocus], wie unter [Als Mitglied anmelden](#sign-in-as-a-member) beschrieben.

   **[!UICONTROL Test]** listet die Tools des Servers auf und aktualisiert die Anzahl **[!UICONTROL Tools]**. Wenn der Server keine Tools zurückgibt, werden in den Details **[!UICONTROL 0 verfügbare Tools]** angezeigt. Wenn der Test fehlschlägt, werden die Details angezeigt **[!UICONTROL Verbindung fehlgeschlagen]**.

   ![Gespeicherte Details zum Regenfokus-Connector, in denen eine redigierte Quelle, die Authentifizierungsmethode „rainfocus_login“, eine Nicht signiert in Verbindung mit einer Anmeldeschaltfläche und die Schaltflächen „Testen“ und „Entfernen“ angezeigt werden.](./assets/rainfocus/org-details.png){width="700" zoomable="yes"}

Die Steuerelemente **[!UICONTROL Verbindung]**, **[!UICONTROL Test]** und Anmeldung für die Connector-Details gelten nur für Ihre eigene Verbindung. Wenn Sie sich als Administrator anmelden, werden keine Mitglieder angemeldet. Bei einem erfolgreichen Test werden nur Tools aufgelistet. Der Test führt kein [!DNL RainFocus]-Tool aus und bestätigt auch nicht, dass ein Mitglied auf bestimmte Daten zugreifen kann.

Die Connector-Details haben keine Option zum Bearbeiten der Profil-URL. **[!UICONTROL Entfernen]** öffnet eine Bestätigung und entfernt dann die Verbindung für die gesamte Organisation. Behandeln Sie das Entfernen als absichtliche Admin-Entscheidung und nicht als Schritt zur Fehlerbehebung.

### Verfügbare Tools {#available-tools}

Der [!DNL RainFocus]-Connector ermöglicht eine feste Liste von 10 Lesetools:

| Tool | Datenbereich |
| --- | --- |
| `get_attendeeInfo` | Teilnehmende |
| `get_attendee_load` | Teilnehmende |
| `get_attendee_search` | Teilnehmende |
| `get_attribute_load` | Benutzerdefinierte Attribute |
| `get_attribute_search` | Benutzerdefinierte Attribute |
| `get_attributevalue_load` | Benutzerdefinierte Attribute |
| `get_entityDataDump_attendee` | Teilnehmer, Massenexport |
| `get_entityDataDump_session` | Sitzungen, Massenexport |
| `get_session_load` | Sessions |
| `get_session_search` | Sessions |

Tools, die nicht in dieser Liste enthalten sind, einschließlich Tools, die später hinzugefügt [!DNL RainFocus], werden nicht automatisch aktiviert. Die Liste ersetzt nicht [!DNL RainFocus] Sicherheitsrollen oder die Tool-Einstellungen des Profils, die weiterhin den Zugriff auf Daten steuern.

>[!IMPORTANT]
>
>Verschiedene Tools können persönliche Daten und Kontaktinformationen über die Teilnehmer zurückgeben. Zwei Tools exportieren Daten in großen Mengen und es können große Ergebnisse erzielt werden. Leserinnen und Leser können auch Kosten nach Ihren [!DNL RainFocus] Bedingungen verursachen. Überprüfen Sie diese Tools mit Ihren Data Governance-Verantwortlichen, bevor sich Mitglieder anmelden.

## Als Mitglied anmelden {#sign-in-as-a-member}

Nachdem ein Administrator den Connector konfiguriert hat, meldet sich jedes Mitglied mit seinem eigenen [!DNL RainFocus] an. Sie benötigen keine Client-ID, kein Client-Geheimnis und kein Zugriffs-Token, um sich anzumelden.

1. Öffnen Sie **[!UICONTROL Anpassungen]** und wählen Sie dann **[!UICONTROL Externe Connectoren]** aus. Mitglieder verwenden standardmäßig den **[!UICONTROL User]**-Bereich. Suchen Sie die **[!UICONTROL RainFocus]**-Karte.
1. Wenn die Karte **[!UICONTROL Noch nicht verfügbar“ anzeigt. Ihr Administrator muss dies einrichten.]** bitten Sie Ihren Administrator, den [Connector konfigurieren](#configure-organization). Mitglieder können keine eigene Profil-URL eingeben.
1. Überprüfen Sie den Status auf der Karte. Auf der Karte wird **[!UICONTROL Anmeldung erforderlich]**, **[!UICONTROL Verbunden]**, **[!UICONTROL Von Ihrem Administrator eingerichtet]** oder ein **[!UICONTROL Verbindung fehlgeschlagen]** angezeigt.

   **[!UICONTROL Von Ihrem Administrator eingerichtet]** bedeutet, dass ein Mitarbeiter Ihren Anmeldestatus nicht bestätigen kann. Dies bedeutet nicht, dass Sie angemeldet oder abgemeldet sind.

1. Wählen Sie **[!UICONTROL Anmelden]** aus. Sie können auch die Kartendetails öffnen und im Abschnitt **[!UICONTROL Verbindung]** die Option **[!UICONTROL Anmelden]** auswählen. Vervollständigen Sie im [!DNL RainFocus] die Eingabeaufforderungen für Anmelden, einmaliges Anmelden (SSO), mehrstufige Authentifizierung (MFA) und Einverständnis. Überprüfen Sie den von Ihnen genehmigten Zugriff.

   Wenn **[!UICONTROL Discover Authorization]** angezeigt wird, liest Coworker die Anmeldedetails des Servers, nicht seiner Tools. Wenn die Erkennung fehlschlägt oder das Bedienfeld nach einer **[!UICONTROL Client-ID]** oder einem **[!UICONTROL Client-Geheimnis]** fragt, stoppen und wenden Sie sich an Ihren Administrator. Geben Sie keine Anmeldeinformationen ein oder erraten Sie sie.

   ![RainFocus-Connector-Details für ein Mitglied, mit dem Status „Anmeldung erforderlich“, einer geschwärzten Server-URL, „Jeder Benutzer meldet sich an“, „Nicht angemeldet“ in Verbindung mit der Schaltfläche „Autorisierung suchen“ und den 10 von Ihrem Administrator aktivierten Tools.](./assets/rainfocus/member-details.png){width="700" zoomable="yes"}

1. Kehren Sie zu Mitarbeiter zurück und bestätigen Sie, dass der Status **[!UICONTROL Verbunden]** angezeigt wird. Ein geschlossenes Anmeldefenster allein bestätigt nicht den Erfolg. Wenn Sie das Fenster frühzeitig schließen, ändert sich nichts und Sie können es erneut versuchen.
1. Öffnen Sie die Kartendetails, um die Einrichtung von Ihrem Administrator zu überprüfen. Sie können die **[!UICONTROL Server-URL]**, **[!UICONTROL Wer meldet sich an]**, **[!UICONTROL Authentifizierung]** und **[!UICONTROL Tools anzeigen, die von Ihrem Administrator aktiviert wurden]**.
1. Wählen Sie **[!UICONTROL Test]** auf der Karte oder **[!UICONTROL Verbindung testen]** in den Details aus, um die Verbindung mit Ihrem Konto zu überprüfen.

   Ein erfolgreicher Test zeigt an, dass [!DNL RainFocus] mit Ihrem -Konto und der Anzahl der verfügbaren Tools geantwortet hat. Der Test listet nur Tools auf. Es führt kein Daten-Tool aus und bestätigt auch nicht den Zugriff auf bestimmte Ereignisse oder Datensätze. Um Ihre Anmeldung zu verlängern und die Tools erneut aufzulisten, wählen Sie **[!UICONTROL Aktualisieren]** aus. Wenn ein Mitarbeiter die Anmeldung nicht verlängern kann, wird stattdessen die Schaltfläche **[!UICONTROL Tools erneut laden]** angezeigt, in der die Tools nur erneut aufgeführt werden.

1. Wenn der Test fehlschlägt, zeigt der **[!UICONTROL „Konnte keine Verbindung zu RainFocus herstellen]** mit **[!UICONTROL Erneut versuchen]** und **[!UICONTROL Technische Details]**. Wenn Sie abgemeldet sind, melden Sie sich erneut an. Wenn das Problem weiterhin besteht, wenden Sie sich an Ihren Administrator.

Mitglieder können sich anmelden, sich abmelden, testen, aktualisieren und die aktivierten Tools anzeigen. Mitglieder können die Organisationsverbindung nicht ändern oder entfernen, die Profil-URL nicht bearbeiten oder die Tools nicht ändern. Jedes Mitglied, das die Details öffnet, kann die Profil-URL anzeigen. Wenn sich ein Administrator anmeldet, werden andere Mitglieder nicht angemeldet.

Um Ihr [!DNL RainFocus]-Konto vom Connector zu trennen, wählen Sie **[!UICONTROL Abmelden]** aus. Sie können sich jederzeit erneut anmelden.

## Überprüfen des Zugriffs auf Ereignisdaten {#check-event-access}

Um zu bestätigen, dass Sie [!DNL RainFocus] Daten verwenden können, führen Sie eine schreibgeschützte Prüfung mit einer eingeschränkten Anfrage aus. Verwenden Sie ein Ereignis, für das Sie eine Genehmigung erhalten haben, und vermeiden Sie Tools, die für diese Prüfung Teilnehmer-Daten oder Massenexporte zurückgeben. Starten Sie einen Chat und geben Sie eine Eingabeaufforderung ein.

Beispielaufforderung:

* „Mit RainFocus finde ich bis zu fünf Sitzungen, auf die ich zugreifen kann. Nur den Sitzungstitel und die ID anzeigen, wenn diese Felder zurückgegeben werden. Exportieren Sie keine Daten, geben Sie keine Teilnehmerinformationen zurück oder ändern Sie nichts.“

Bestätigen Sie, dass das Ergebnis die erwarteten Sitzungen enthält. Ein leeres Ergebnis bedeutet nicht immer, dass der Connector nicht funktioniert. Überprüfen Sie das [!DNL RainFocus] Konto, mit dem Sie sich angemeldet haben, Ihre Sicherheitsrolle und die im Profil aktivierten Tools. Wenn ein Ergebnis unerwartet groß ist oder vertrauliche Daten enthält, stoppen und grenzen Sie Ihre Anfrage ein.

## Fehlerbehebung beim Zugriff {#troubleshoot-access}

Wenn Sie nicht auf Ihre [!DNL RainFocus] zugreifen können, fragen Sie bei Ihrem Administrator nach:

| Problem | Was zu überprüfen ist |
| --- | --- |
| Die **[!UICONTROL RainFocus]**-Karte fehlt | Vergewissern Sie sich bei Ihrem Adobe-Support-Mitarbeiter, dass der Connector für Ihr Unternehmen verfügbar ist. |
| Der **[!UICONTROL org]**-Bereich fehlt | Vergewissern Sie sich, dass Sie Administrator sind und dass die Unternehmenseinstellungen für Ihre Organisation aktiviert sind. |
| Mitarbeiter lehnt Profil-URL ab | Befolgen Sie die Regel in der Nachricht. Verwenden Sie die vollständige Profil-URL von Ihrem [!DNL RainFocus] und raten Sie nicht über einen Profilnamen. |
| **[!UICONTROL Verbindung konnte nicht gespeichert werden]** wird angezeigt | Einige Einstellungen werden möglicherweise gespeichert. Öffnen Sie die Konfiguration erneut und überprüfen Sie sie, bevor Sie es erneut versuchen. Stellen Sie sicher, dass jeweils nur ein Administrator den Connector konfiguriert. |
| Die Karte zeigt **[!UICONTROL Noch nicht verfügbar. Ihr Administrator muss dies einrichten.]** | Die Einrichtung der Organisation fehlt. Bitten Sie Ihren Administrator, den [&#x200B; zu konfigurieren](#configure-organization). |
| Bei der Anmeldung wird nach einer **[!UICONTROL Client-ID]** oder einem **[!UICONTROL Client-Geheimnis]** gefragt oder die Erkennung schlägt fehl | Beenden Sie den Vorgang und wenden Sie sich an Ihren Administrator. Geben Sie keine Anmeldeinformationen ein, raten Sie nicht, und registrieren Sie keine App. |
| Die Anmeldung schlägt nach der Genehmigung des Zugriffs in [!DNL RainFocus] fehl | Überprüfen Sie das verwendete [!DNL RainFocus]- und Sicherheitskonto. Bitten Sie Ihren Adobe-Support-Mitarbeiter und [!DNL RainFocus], die Anmeldeeinstellungen für Ihre Umgebung zu überprüfen. Geben Sie die Anmelde-URL nicht frei. |
| **[!UICONTROL Test]** ist erfolgreich, aber Datenanfragen schlagen fehl | **[!UICONTROL Test]** listet nur Tools auf. Überprüfen Sie Ihre [!DNL RainFocus] Sicherheitsrolle, die im Profil aktivierten Tools und die für das Tool erforderlichen Filter. |
| **[!UICONTROL Konnte keine Verbindung zu RainFocus herstellen]** wird angezeigt, wenn Sie angemeldet sind | Wählen Sie **[!UICONTROL Erneut versuchen]** aus. Wenn das Problem weiterhin besteht, wenden Sie sich an Ihren Administrator. |
| Ein Ergebnis ist unerwartet groß oder enthält vertrauliche Daten | Beenden und begrenzen Sie Ihre Anfrage. Fügen Sie keine rohen Ereignisdaten in Tickets oder Chats ein. |

Geben Sie bei der Kontaktaufnahme mit dem Support nur den Fehlertext, den Zeitpunkt des Fehlers und Ihre Umgebung an. Geben Sie keine technischen Details, Profil-URLs, Anmeldungserfassungen, Kennwörter, Token oder Autorisierungs-Codes weiter.
