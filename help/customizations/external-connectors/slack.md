---
title: Externer Slack-Connector
description: Erfahren Sie, wie Sie den externen Slack-Connector in CX Enterprise Coworker mit Ihrer eigenen Slack-App einrichten und sich anmelden, um Ihre Slack-Unterhaltungen im Chat zu verwenden.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Dieser Connector befindet sich in der Betaphase."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 877954880bf6fda5151dcb343af92888db21cef4
workflow-type: tm+mt
source-wordcount: '2268'
ht-degree: 0%
---

# Externer Slack-Connector {#slack}

Verwenden Sie den externen [!DNL Slack]-Connector, um mit Ihren [!DNL Slack] in Adobe CX Enterprise Coworker zu arbeiten. Bitten Sie nach der Einrichtung des Connectors einen Kollegen, nach Nachrichten und Dateien zu suchen, Kanäle und Threads zu lesen und Personen zu finden. Sie können auch Nachrichten und Antworten senden, wenn Ihr Administrator diese Tools aktiviert hat. Der Connector verwendet den offiziellen MCP-Server (Remote Model Context Protocol), der von [!DNL Slack] gehostet wird.

>[!AVAILABILITY]
>
>Der externe [!DNL Slack]-Connector befindet sich in der Beta-Phase. Die Dokumentation und die Funktionalität können sich ändern.

## Connector-Konfiguration {#connector-configuration}

Der Connector-Konfigurationsprozess besteht aus drei separaten Teilen:

* **[!DNL Slack]-App-Vorbereitung** Der Eigentümer einer [!DNL Slack]-App bereitet eine geeignete App vor, registriert die CoWorker-Umleitungs-URL und legt die Benutzerbereiche fest. Adobe stellt keine verwaltete [!DNL Slack]-App bereit.
* **Einrichten der Organisation:** Ein Mitarbeiter-Administrator konfiguriert den Connector einmal für die gesamte Organisation. Der Administrator gibt die App-Anmeldeinformationen ein und wählt die OAuth-Bereiche des Benutzers und die Tools aus, die Mitglieder verwenden können.
* **Mitglied anmelden** Jedes Mitglied meldet sich mit seinem eigenen [!DNL Slack] an. Mitglieder können nur auf die Inhalte zugreifen, auf die ihr [!DNL Slack]-Konto zugreifen kann.

Der Connector verwendet keinen freigegebenen Bot oder keine freigegebene [!DNL Slack]. Der Kollege sendet Nachrichten und Antworten als das Mitglied, das angemeldet ist. Beim Speichern der Organisationskonfiguration werden keine Mitglieder angemeldet und es wird kein zusätzlicher [!DNL Slack] gewährt. Jedes Mitglied muss sich separat anmelden.

## Voraussetzungen {#prerequisites}

Bevor Sie beginnen, stellen Sie Folgendes sicher:

* **Coworker access:** Ein Konto mit der Berechtigung zum Verwalten von Organisations-Connectoren in einer Organisation, in der der [!DNL Slack]-Connector verfügbar ist.
* **Eine [!DNL Slack]-App:** Eine interne App oder eine [!DNL Slack Marketplace] App, die für Ihren Arbeitsbereich genehmigt wurde. Außerdem benötigen Sie einen App-Verantwortlichen, der die genehmigten Benutzerbereiche bestätigen und die App-Einstellungen bearbeiten kann.
* **App-Anmeldeinformationen:** Die Client-ID und das Client-Geheimnis der App, die über Ihren genehmigten Prozess zur Handhabung von Anmeldeinformationen freigegeben wurden.
* **Eine Tool- und Umfangsentscheidung** Die Lese-, Messaging- und Entwurfs-Tools, die Ihr Unternehmen aktivieren möchte, sowie die OAuth-Benutzerbereiche, die angefordert werden sollen.
* **Ein Testarbeitsbereich oder -kanal:** Ein Ort, an dem die Verbindung mit Mitgliedern überprüft werden kann, die zustimmen, sie zu testen. Senden Sie keine Testnachrichten in Kunden- oder Produktionskanälen.

>[!IMPORTANT]
>
>Geben Sie in Screenshots, Chats oder Support-Tickets niemals Kundengeheimnisse, Zugriffs-Token oder andere Anmeldeinformationen frei. Geben Sie die Anmeldeinformationen nur in die sicheren Felder des Einrichtungsdialogs ein.

## Vorbereiten der Slack-App {#prepare-slack-app}

Bevor Sie den Connector in Coworker konfigurieren, bereitet der App-Inhaber die [!DNL Slack] App vor. Möglicherweise muss sie auch vom Administrator des Arbeitsbereichs oder der Organisation App genehmigt werden. Die [!DNL Slack] Anforderungen finden Sie unter [Slack MCP-Server](https://docs.slack.dev/ai/slack-mcp-server/) in der [!DNL Slack]-Entwicklerdokumentation.

### Wählen Sie eine geeignete App aus {#choose-eligible-app}

[!DNL Slack] unterstützt seinen MCP-Server nur für interne benutzerdefinierte Apps und Apps, die im [!DNL Slack Marketplace] veröffentlicht wurden. Nicht aufgelistete Apps, die außerhalb Ihres Unternehmens verteilt sind, können den [!DNL Slack] MCP-Server nicht verwenden. Das Einschalten der öffentlichen Verteilung allein macht eine App nicht geeignet.

1. Wählen Sie den Arbeitsbereich oder die Organisation aus, der bzw. die Eigentümer der App ist, und den App-Besitzer.
1. Erstellen Sie in der [Slack](https://api.slack.com/apps)App-Verwaltung eine neue App in diesem Arbeitsbereich. Um eine vorhandene geeignete App wiederzuverwenden, holen Sie sich zunächst die Genehmigung von ihrem Inhaber ein.
1. Wählen Sie in den App-Einstellungen **[!UICONTROL Grundlegende Informationen]** > **[!UICONTROL App-Anmeldeinformationen]** aus. Beachten Sie **[!UICONTROL Client-ID]** und **[!UICONTROL Client-Geheimnis]**.

   Geben Sie nur diese beiden Werte in „Mitarbeiter“ ein. Verwenden Sie nicht die App-ID, das Signaturgeheimnis, ein Bot-Token oder ein Token auf Programmebene.

### Registrieren der Umleitungs-URL {#register-redirect-url}

Registrieren Sie die Coworker-Umleitungs-URL in Ihrer [!DNL Slack]-App:

1. Öffnen Sie in der **[!UICONTROL das Dialogfeld &quot;Slack verbinden]** wie unter [Konfigurieren des Connectors für Ihr Unternehmen](#configure-organization) beschrieben. Kopieren Sie den vollständigen Wert der **[!UICONTROL Umleitungs-URL]**.

   Sie können das Dialogfeld öffnen, um die URL zu kopieren, bevor Sie die Konfiguration abschließen oder speichern.

1. Wählen Sie in den [!DNL Slack] App-Einstellungen **[!UICONTROL OAuth und Berechtigungen]** aus. Fügen **[!UICONTROL unter „Umleitungs]** URLs“ die vollständige Umleitungs-URL hinzu und speichern Sie dann.

Kopieren Sie immer die Umleitungs-URL aus dem Dialogfeld „Mitarbeiter“ in die Umgebung, die Sie einrichten. Registrieren Sie das genaue Schema, den Hostnamen, Port (sofern vorhanden) und den Pfad. Erstellen Sie die URL nicht selbst oder verwenden Sie eine Umleitungs-URL aus einer anderen Umgebung erneut. Wenn Sie mehr als eine Umgebung verwenden, registrieren Sie jede Umleitungs-URL separat.

### Festlegen der Benutzerbereiche {#set-user-scopes}

Der Connector verwendet Benutzer-OAuth-Bereiche, die das Konto jedes Mitglieds autorisieren. Es werden keine Bot-Bereiche verwendet.

1. Wählen Sie in den Einstellungen der [!DNL Slack] App **[!UICONTROL OAuth und Berechtigungen]** > **[!UICONTROL Bereiche]** > **[!UICONTROL Benutzer-Token-Bereiche]**.
1. Fügen Sie die von Ihrem Unternehmen genehmigten Benutzerbereiche hinzu. Vergleichen Sie sie mit den [Standardbereichen](#review-scopes) in Coworker und fügen Sie nur die Bereiche hinzu, die Sie anfordern möchten.

   Die Standardbereiche sind der Standardfunktionssatz von Coworker, nicht ein Minimum, das [!DNL Slack] benötigt. Verwenden Sie die granularen `search:read.*`, nicht den älteren `search:read`. In einem App-Manifest gehören Benutzerbereiche in `oauth_config.scopes.user`, nicht `oauth_config.scopes.bot`.

Der `chat:write` Benutzerbereich ermöglicht es Kollegen, Nachrichten als angemeldetes Mitglied zu senden. Wenn Ihr Unternehmen nicht plant, Nachrichten zu senden, lassen Sie es aus.

Ihr Arbeitsbereich oder [!DNL Slack] Unternehmen benötigt möglicherweise eine App-Genehmigung und eine Überprüfung des Umfangs. Die App-Genehmigung ersetzt nicht das Einverständnis jedes Mitglieds. Eine Richtlinie, die nur [!DNL Slack Marketplace] Apps zulässt, kann eine interne App blockieren. Weitere Informationen finden Sie unter [App-Genehmigung für Ihren Arbeitsbereich &#x200B;](https://slack.com/help/articles/222386767-Manage-app-approval-for-your-workspace).

Wenn Ihre App zulässige IP-Adressbeschränkungen verwendet, wendet [!DNL Slack] diese auch auf MCP-Anfragen an. Wenden Sie sich an den Adobe-Support, um die Adressen zu bestätigen, die zugelassen werden sollen. IP-Adressbereiche nicht raten. Einige Funktionen, z. B. die semantische Suche, können von Ihrem [!DNL Slack]-Plan abhängen.

### Überprüfen der irreversiblen App-Einstellungen {#review-irreversible-settings}

Coworker stellt eine Verbindung als vertraulicher OAuth-Client mit der Client-ID und dem Client-Geheimnis her. Einige [!DNL Slack]-App-Einstellungen können nicht rückgängig gemacht werden. Überprüfen Sie daher Folgendes, bevor Sie sie ändern:

* **Proof Key for Code Exchange (PKCE):** Sie die [!DNL Slack] PKCE-Einstellung für diesen Connector nicht ohne Bestätigung an. [!DNL Slack] dokumentiert, dass diese Einstellung die App in einen öffentlichen Client ändert und nur [!DNL Slack] Support sie rückgängig machen kann. Weitere Informationen finden Sie unter [Verwenden von PKCE](https://docs.slack.dev/authentication/using-pkce/).
* **Token-Rotation:** [!DNL Slack] Token-Rotation kann nach dem Einschalten nicht mehr deaktiviert werden. Wenden Sie sich an die Adobe-Kontaktperson, bevor Sie sie für diese App aktivieren. Weitere Informationen finden Sie unter [Verwenden der Tokenrotation](https://docs.slack.dev/authentication/using-token-rotation/).

### Bot-Funktionen nicht erforderlich {#bot-features-not-required}

Der Connector benötigt keine beiden Funktionen. Sie benötigen keine Token-Bereiche, eine [!DNL Events API]-URL, eine Interaktivitätsanfrage-URL, eingehende Webhooks, Slash-Befehle, [!DNL Socket Mode] oder Token auf App-Ebene. Wenn eine vorhandene App diese Funktionen für einen anderen Zweck verwendet, behalten Sie sie bei.

Der [!DNL Slack] MCP-Server unterstützt keine dynamische Client-Registrierung oder Server-SSE-Ereignisse (Server-sent events). Coworker verwendet Ihre registrierte App und den Streamable HTTP-Transport.

## Konfigurieren des Connectors für Ihre Organisation {#configure-organization}

Administratoren stellen den [!DNL Slack]-Connector für alle Personen in der Organisation zur Verfügung. Änderungen auf der Seite „Organisation“ gelten für alle Benutzer in Ihrer Organisation. Schließen Sie [Slack-App vorbereiten](#prepare-slack-app) ab, bevor sich Mitglieder anmelden.

1. Öffnen Sie **[!UICONTROL Anpassungen]**, wählen Sie **[!UICONTROL Organisation]** und dann **[!UICONTROL Externe Connectoren]** aus. Wählen Sie auf der Karte **&#x200B;**&#x200B;Slack **[!UICONTROL die Option „Konfigurieren]** aus.

   Das **[!UICONTROL Slack verbinden]**-Dialogfeld wird geöffnet. Der Connector verwendet die feste [!DNL Slack] MCP-Server-URL `https://mcp.slack.com/mcp`. Verwenden Sie den Organisationsbereich für diese Konfiguration, keine persönliche Verbindung.

1. Vergewissern Sie sich, dass die **[!UICONTROL Umleitungs-URL]** unter **[!UICONTROL Slack]** Programm in Ihrer App registriert ist, wie unter [Registrieren der Umleitungs-URL](#register-redirect-url) beschrieben. Geben Sie dann die **[!UICONTROL Client-ID]** und **[!UICONTROL Client-Geheimnis]** Ihrer App ein. Beide Felder sind erforderlich.

   Geben Sie weder die App-ID noch das Signiergeheimnis oder ein Bot-Token ein. Coworker speichert die Anmeldeinformationen als geheime Daten und nicht als Connector-Einstellungen im Klartext.

   ![Das Dialogfeld &quot;Slack verbinden“, das den Abschnitt &quot;Slack-Anwendung“ mit einer geschwärzten Umleitungs-URL, leeren Feldern für Client-ID und Client-Geheimnis, den standardmäßigen OAuth-Bereichen für Benutzer und den ersten Tools, die Benutzern zur Verfügung stehen, anzeigt.](./assets/slack/org-configure.png){width="500" zoomable="yes"}

1. Überprüfen Sie **[!UICONTROL Benutzer-OAuth-Bereiche]**. Weitere Informationen finden Sie unter [Überprüfen der OAuth-Benutzerbereiche](#review-scopes).

1. Entfernen **[!UICONTROL unter „Tools für Benutzer verfügbar]** alle Tools, die Mitglieder nicht verwenden sollten. Es muss mindestens ein Tool vorhanden sein. Weitere Informationen finden Sie unter [Verfügbare Tools](#available-tools).

1. Überprüfen Sie **[!UICONTROL Zugriff und Berechtigungen]** und wählen Sie dann **[!UICONTROL Verbindung speichern]** aus. Die Karte **[!UICONTROL Slack]** zeigt **[!UICONTROL Konfiguration gespeichert]**.

   Das Dialogfeld zeigt auch die **[!UICONTROL Authentifizierung]**-Methode, den **[!UICONTROL Connection]**-Typ und die **[!UICONTROL Tool-Zeitüberschreitung]**. Der Mitarbeiter speichert die Konfiguration nicht, wenn ein Berechtigungsfeld oder die Bereichsliste leer ist.

   Laden Sie die Seite neu, wählen Sie **[!UICONTROL Konfiguration anzeigen]** und bestätigen Sie, dass die Konfiguration und Ihre Tool-Auswahl gespeichert werden, bevor sich Mitglieder anmelden.

   ![Das Dialogfeld &quot;Slack verbinden“ mit den OAuth-Benutzerbereichen, allen 16 Tools, die für Benutzende verfügbar sind, dem Hinweis zu Zugriff und Berechtigungen sowie den Einstellungen für OAuth-Authentifizierung, HTTP-Verbindung und Zeitüberschreitung bei 60-Sekunden-Tools.](./assets/slack/org-scopes-tools.png){width="500" zoomable="yes"}

Beim Speichern werden weder Sie noch ein Mitglied bei [!DNL Slack] angemeldet. Um die Verbindung zu überprüfen, melden Sie sich wie unter [Als Mitglied anmelden](#sign-in-as-a-member).

### Überprüfen der OAuth-Bereiche des Benutzers {#review-scopes}

Das Feld **[!UICONTROL Benutzer-OAuth]** Bereiche“ ist erforderlich. Trennen Sie Bereiche durch Leerzeichen oder Kommas und passen Sie die Benutzerbereiche an, die für Ihre App genehmigt wurden. Standardmäßig enthält das Feld die folgenden 22 Bereiche:

```text
search:read.public search:read.private search:read.im search:read.mpim search:read.files search:read.users channels:history groups:history im:history mpim:history channels:read groups:read im:read mpim:read users:read users:read.email files:read canvases:read lists:read emoji:read reactions:read chat:write
```

Ihr Arbeitsbereich genehmigt möglicherweise nicht jeden Standardbereich. Überprüfen Sie die angeforderten Bereiche mit dem App-Inhaber.

>[!IMPORTANT]
>
>Die Standardbereiche umfassen private Inhalte wie private Kanäle, Gruppennachrichten und Direktnachrichten. Dazu gehören auch `chat:write`, mit denen -Mitarbeiter Nachrichten und Antworten als angemeldetes Mitglied senden können. Entscheiden Sie explizit, ob Ihr Unternehmen die Nachrichtenversand-Tools aktiviert. Beim Entfernen eines Tools werden dessen OAuth-Bereiche nicht entfernt. Wenn Sie nicht möchten, dass Mitglieder Nachrichten senden, entfernen Sie das `slack_send_message` und den `chat:write`.

Die Tool-Auswahl und OAuth-Bereiche sind unabhängig. Wenn Sie den Zugriff einschränken, überprüfen Sie sowohl die Toolliste als auch das Feld Umfang . Ein aktiviertes Tool gewährt einem Abonnenten nicht mehr [!DNL Slack] Zugriff als sein Konto.

### Verfügbare Tools {#available-tools}

Der [!DNL Slack]-Connector bietet die folgenden 16 Tools. Standardmäßig sind alle für Mitglieder verfügbar.

| Funktion | Tool |
| --- | --- |
| Suchen | `slack_search_public` |
| Suchen | `slack_search_public_and_private` |
| Suchen | `slack_search_channels` |
| Suchen | `slack_search_users` |
| Unterhaltungen lesen | `slack_read_channel` |
| Unterhaltungen lesen | `slack_read_thread` |
| Unterhaltungen lesen | `slack_list_channel_members` |
| Unterhaltungen lesen | `slack_list_user_channels` |
| Lesen von Inhalten und Profilen | `slack_read_canvas` |
| Lesen von Inhalten und Profilen | `slack_read_user_profile` |
| Lesen von Inhalten und Profilen | `slack_read_file` |
| Lesen von Inhalten und Profilen | `slack_read_list` |
| Emojis und Reaktionen | `slack_search_emojis` |
| Emojis und Reaktionen | `slack_get_reactions` |
| Nachrichten und Entwürfe | `slack_send_message` |
| Nachrichten und Entwürfe | `slack_send_message_draft` |

Der Connector ist nicht schreibgeschützt. Mitglieder können Nachrichten und Antworten senden, es sei denn, Sie entfernen das `slack_send_message`. Die Kanalerstellung, geplante Nachrichten, Datei-Uploads, das Hinzufügen von Reaktionen und Arbeitsflächen- oder Listenänderungen sind nicht enthalten.

## Als Mitglied anmelden {#sign-in-as-a-member}

Nachdem ein Administrator den Connector konfiguriert hat, meldet sich jedes Mitglied mit seinem eigenen [!DNL Slack] an. Sie benötigen das Client-Geheimnis nicht, um sich anzumelden.

1. Öffnen Sie **[!UICONTROL Anpassungen]**, wählen Sie **[!UICONTROL Benutzer]** und dann **[!UICONTROL Externe Connectoren]** aus.

1. Suchen Sie die Karte **[!UICONTROL Slack]**. Wenn die Karte **[!UICONTROL Nicht konfiguriert]** und &quot;**[!UICONTROL noch nicht verfügbar“ anzeigt. Ihr Administrator muss dies einrichten.]** bitten Sie Ihren Administrator, den [Connector konfigurieren](#configure-organization).

   Fragen Sie nicht nach dem Kundengeheimnis der Organisation oder kopieren Sie es nicht.

1. Nachdem der Administrator den Connector konfiguriert hat, wird auf der Karte **[!UICONTROL Slack]** angezeigt **[!UICONTROL Anmeldung erforderlich]**. Wählen **[!UICONTROL auf der Karte]** Anmelden“ aus.

   Sie können auch die Details des **[!UICONTROL Slack]**-Connectors öffnen. Vor der Anmeldung wird im Abschnitt **[!UICONTROL Verbindung]** **[!UICONTROL Nicht angemeldet]** mit einer Schaltfläche **[!UICONTROL Anmelden]** angezeigt.

   ![Slack-Connector-Details für ein Mitglied, die den Status „Anmeldung erforderlich“, die Schaltfläche „Verbindung testen“, die Server-URL, „Jeder Benutzer meldet sich an“, „Nicht angemeldet mit einer Anmeldeschaltfläche“ und die von Ihrem Administrator aktivierten Tools anzeigen.](./assets/slack/member-details.png){width="700" zoomable="yes"}

1. Schließen Sie die [!DNL Slack] Autorisierung mit dem [!DNL Slack] Konto und Arbeitsbereich ab, den Sie verwenden möchten. Überprüfen Sie die angeforderten Berechtigungen und alle Anforderungen für die Arbeitsbereich-Genehmigung.

   >[!IMPORTANT]
   >
   >Fahren Sie nur fort, wenn Sie die App erkennen und Ihr Unternehmen den angeforderten Zugriff genehmigt.

1. Kehren Sie zu Mitarbeiter zurück und überprüfen Sie den Verbindungsstatus. Wählen Sie **[!UICONTROL Verbindung testen]** und [Überprüfen Sie Ihren Slack-Zugriff](#check-access) bevor Sie die Verbindung verwenden.

1. Überprüfen Sie die Nachrichtenaktionen sorgfältig. Ein Mitarbeiter sendet Nachrichten und Antworten als Ihr [!DNL Slack].

Als Mitglied können Sie die Verbindung testen oder sich abmelden. Sie können die Unternehmenseinstellungen jedoch nicht ändern. Sie können nur auf die Inhalte zugreifen, die [!DNL Slack] und die gewährten Bereiche zulassen. Diese Inhalte umfassen private Konversationen nur, wenn Ihr eigenes [!DNL Slack] darauf zugreifen kann.

Um Ihr [!DNL Slack]-Konto vom Connector zu trennen, wählen Sie **[!UICONTROL Abmelden]** aus.

## Überprüfen des Slack-Zugriffs {#check-access}

Um zu bestätigen, dass der Connector Ihren [!DNL Slack]-Inhalt lesen kann, starten Sie einen Chat und geben Sie eine schreibgeschützte Eingabeaufforderung ein. Stellen Sie sicher, dass der Administrator das `slack_list_user_channels`-Tool aktiviert hat.

Beispielaufforderung:

* „Listen Sie mit Slack bis zu fünf Kanäle auf, zu denen ich gehöre. Nur die Kanalnamen anzeigen. Senden Sie keine Nachrichten, erstellen Sie keine Entwürfe und ändern Sie nichts.“

Wenn Ihr Unternehmen Messaging-Tools aktiviert, testen Sie den Versand nur in einem Kanal, der für Tests reserviert ist, und mit Genehmigung. Bitten Sie ein zweites Mitglied, sich separat anzumelden, und bestätigen Sie, dass jedes Mitglied nur seine eigenen [!DNL Slack] Inhalte sieht.

## Fehlerbehebung beim Zugriff {#troubleshoot-access}

Wenn die Einrichtung, Anmeldung oder der Zugriff fehlschlägt, wenden Sie sich an Ihren Administrator, um Folgendes zu überprüfen:

| Problem | Was zu überprüfen ist |
| --- | --- |
| Setup kann nicht gespeichert werden | Geben Sie sowohl die Client-ID als auch das Client-Geheimnis ein, behalten Sie mindestens einen Benutzer-OAuth-Bereich bei und behalten Sie mindestens ein Tool bei. Geben Sie keine App-ID, kein Signiergeheimnis oder Bot-Token ein. |
| Die **[!UICONTROL Umleitungs]** URL fehlt oder meldet [!DNL Slack] eine Umleitungs-Inkongruenz | Vergleichen Sie die vollständige Umleitungs-URL aus dem Dialogfeld „Mitarbeiter“, einschließlich Schema, Host, Port und Pfad, mit den **[!UICONTROL Umleitungs-URLs]**, die in der [!DNL Slack]-App gespeichert sind. Wenn die URL fehlt oder die Werte unterschiedlich sind, wenden Sie sich an den Adobe-Support. |
| [!DNL Slack] Anmeldung oder Anfragen schlagen fehl | Überprüfen Sie die App-Genehmigung, die gewährten Benutzerbereiche, das [!DNL Slack] Konto und den Arbeitsbereich, mit denen Sie sich angemeldet haben, sowie alle IP-Adressbeschränkungen für die App. Wenn Anfragen weiterhin fehlschlagen, melden Sie sich ab und wieder an. |
| Eine Lese- oder Sendeaktion ist nicht verfügbar | Überprüfen Sie die Toolauswahl Ihrer Organisation, die angeforderten und gewährten Bereiche und die [!DNL Slack] Berechtigungen des Mitglieds. Diese Einstellungen sind unabhängig. |
| Ein Mitglied kann die App-Einstellungen nicht ändern | Dieses Verhalten wird für eine Verbindung erwartet, die vom Unternehmen verwaltet wird. Fragen Sie den Administrator. Mitglieder geben das Kundengeheimnis der Organisation nie ein. |
