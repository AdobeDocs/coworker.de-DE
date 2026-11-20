---
title: Externer Infobip Observe-Connector
description: Erfahren Sie, wie Sie den externen Connector von Infobip Observe in CX Enterprise Coworker für Ihr Unternehmen einrichten und sich mit Infobip anmelden, um Tools zur Beobachtung zu verwenden.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Dieser Connector befindet sich in der Betaphase."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 382a5f6fd629b8b10468c0cfe4d41f050a7f3725
workflow-type: tm+mt
source-wordcount: '1458'
ht-degree: 1%
---

# Externer Infobip-Observe-Connector {#infobip-observe}

Verwenden Sie den externen [!DNL Infobip Observe]-Connector, um Ihren [!DNL Infobip] Traffic und Ihre Kosten in Adobe CX Enterprise Coworker zu überprüfen. Fragen Sie nach der Einrichtung des Connectors den Kollegen nach Traffic-Metriken, der Abrechnungsnutzung, Nachrichtenprotokollen sowie Status- und Fehler-Codes. Der Connector ist der von [!DNL Infobip] gehostete [!DNL Observe] Model Context Protocol (MCP)-Server.

>[!AVAILABILITY]
>
>Der externe [!DNL Infobip Observe]-Connector befindet sich in der Beta-Phase. Die Dokumentation und die Funktionalität können sich ändern.

## Connector-Konfiguration {#connector-configuration}

Der Connector-Konfigurationsprozess besteht aus zwei separaten Teilen:

* **Einrichten der Organisation:** Ein Administrator konfiguriert den Connector einmal für die gesamte Organisation und genehmigt die Tools, die Mitglieder verwenden können.
* **Mitglied anmelden** Jedes Mitglied meldet sich mit seinem eigenen [!DNL Infobip] an. Mitglieder können nur auf die Daten zugreifen, zu deren Verwendung ihr [!DNL Infobip] berechtigt ist.

Der Connector hat keine Anmeldung bei einer freigegebenen Organisation. Jedes Mitglied, das den Connector verwendet, meldet sich separat an. Beim Speichern der Organisationskonfiguration werden keine Mitglieder angemeldet und es werden keine zusätzlichen [!DNL Infobip] gewährt.

## Voraussetzungen {#prerequisites}

Der Connector funktioniert nur mit dem [!DNL Infobip] [!DNL Observe] MCP-Server. Es stellt keine Verbindung zu den MCP-Servern für [!DNL Infobip]-Messaging, Bereitstellung oder Kontoverwaltung her.

Bevor Sie beginnen, stellen Sie Folgendes sicher:

* **Coworker access:** Ein Konto mit der Berechtigung zum Verwalten von Organisations-Connectoren in einer Organisation, in der der [!DNL Infobip Observe]-Connector verfügbar ist.
* **[!DNL Infobip]:** Ein genehmigtes [!DNL Infobip]-Konto mit Zugriff auf [!DNL Observe] im vorgesehenen Rechenzentrum. [!DNL Infobip] bietet [!DNL Observe] MCP als EARLY ACCESS-Funktion. Bestätigen Sie Ihre Berechtigung und Kontoeignung mit [!DNL Infobip].
* **Mitgliedsidentitäten:** Mitglieder mit eigenen [!DNL Infobip] und der Berechtigung zum Zugriff auf die beabsichtigten Daten.
* **Ein genehmigter Testbereich:** Ein genehmigter Testbereich und nicht vertrauliche Daten, bevor Sie Abrechnungs-, Traffic- oder Nachrichtenprotokolle abfragen.

Um den Connector zu testen, können Sie sich für ein kostenloses Testkonto [!DNL Infobip]. Ein Testkonto garantiert keine Datenisolierung oder Null-Kosten. Weitere Informationen finden Sie unter [Verwenden von Infobip MCP](https://www.infobip.com/docs/mcp/using-mcp){target="_blank"}Servern und [MCP beobachten](https://www.infobip.com/docs/mcp/observe-mcp){target="_blank"} in der [!DNL Infobip].

>[!IMPORTANT]
>
>Geben Sie in Screenshots, Chats oder Support-Tickets niemals Passwörter, API-Schlüssel, Token, Autorisierungs-Codes oder Einverständnis- und Rückruf-URLs frei.

## Verbindungs- und Anmeldemodell {#connection-model}

Der -Mitarbeiter wendet die folgenden Einstellungen automatisch an. Sie erstellen keine OAuth-App und geben keine App-Anmeldeinformationen ein.

| Einstellung | Wert |
| --- | --- |
| Server-URL | `https://mcp.infobip.com/observe` |
| Transport | Streamable HTTP |
| Erkennung des Autorisierungs-Servers | `https://mcp.infobip.com/observe/.well-known/oauth-authorization-server` |
| Anmelden | Jedes Mitglied meldet sich mithilfe einer dynamischen Client-Registrierung mit OAuth an |
| OAuth-Konfiguration | Automatisch erkannt. Admins geben keine Client-ID, kein Client-Geheimnis, keine Bereiche und keine OAuth-Endpunkte ein. |
| Tool-Auswahl | Vier genehmigte Tools. Administratoren können die Auswahl einschränken. |

[!DNL Infobip] Entdeckung und das Einverständnis jedes Mitglieds bestimmen den Zugriff, den ein Mitarbeiter erhält. [!DNL Infobip] dokumentiert die `billing:usage:view`, `metrics:manage`, `messages-api:manage` und `error-codes:read` für [!DNL Observe] MCP. Überprüfen Sie den angeforderten Zugriff auf dem Zustimmungsbildschirm, bevor Sie ihn genehmigen.

[!DNL Infobip] unterstützt auch die API-Schlüsselauthentifizierung für [!DNL Observe] MCP in anderen MCP-Clients. Der Mitarbeiter verwendet keine API-Schlüssel für diesen Connector. Mitglieder melden sich nur mit OAuth an.

## Konfigurieren des Connectors für Ihre Organisation {#configure-organization}

Administratoren stellen den [!DNL Infobip Observe]-Connector für alle Personen in der Organisation zur Verfügung. Änderungen auf der Seite „Organisation“ gelten für alle Benutzer in Ihrer Organisation. Mitglieder können die Organisationsverbindung nicht konfigurieren.

1. Öffnen Sie **[!UICONTROL Anpassungen]**, wählen Sie **[!UICONTROL Organisation]** und dann **[!UICONTROL Externe Connectoren]** aus.

1. Suchen Sie **[!UICONTROL Infobip Observe]** und wählen Sie dann **[!UICONTROL Konfigurieren]** aus.

1. Überprüfen Sie im **[!UICONTROL Connect Infobip Observe]**-Dialogfeld die feste **[!UICONTROL Server URL]**, `https://mcp.infobip.com/observe`.

   Sie müssen keine OAuth-Client-ID, keinen geheimen Client-Schlüssel und keine Bereiche eingeben.

1. Überprüfen **[!UICONTROL unter „Tools für Benutzer verfügbar]** die vier ursprünglich ausgewählten Tools. Entfernen Sie alle Tools, die Mitglieder Ihrer Organisation nicht verwenden sollten. Es muss mindestens ein Tool vorhanden sein.

   Weitere Informationen finden Sie unter [Verfügbare Tools](#available-tools).

   ![Das Dialogfeld „Infobip-Observe verbinden“ mit der Server-URL, den vier für Benutzer verfügbaren Tools, dem Hinweis zu Zugriff und Berechtigungen sowie der OAuth-Authentifizierung, der HTTP-Verbindung und den Einstellungen für die Zeitüberschreitung des 60-Sekunden-Tools.](./assets/infobip-observe/org-configure.png){width="500" zoomable="yes"}

1. Wählen Sie **[!UICONTROL Verbindung speichern]**. Öffnen Sie dann die Konfiguration erneut, um sicherzustellen, dass die Tool-Auswahl weiterhin besteht.

Beim Speichern werden weder Sie noch ein Mitglied bei [!DNL Infobip] angemeldet. Um die Verbindung selbst zu überprüfen, melden Sie sich wie unter [Als Mitglied anmelden](#sign-in-as-a-member) beschrieben an.

Um alle vier Tools nach dem Entfernen erneut verfügbar zu machen, wählen Sie **[!UICONTROL Alle Tools wiederherstellen]** aus. Mit dieser Option werden nur die vier genehmigten Tools wiederhergestellt. Coworker aktiviert keine Tools, die später hinzugefügt [!DNL Infobip]. Sie können die Konfiguration nicht speichern, ohne dass Tools ausgewählt sind.

### Verfügbare Tools {#available-tools}

Der [!DNL Infobip Observe]-Connector bietet die folgenden Tools. [!DNL Infobip] können die Beschränkungen der einzelnen Tools ändern. Überprüfen Sie daher die [!DNL Infobip]-Dokumentation, bevor Sie sich auf sie verlassen.

| Tool | Zweck | Beschränkungen |
| --- | --- | --- |
| `get_traffic_performance_metrics` | Aggregierte Metriken für Traffic, Versand und Interaktion. | Bis zu 366 Tage Daten. Stündliche Fenster decken bis zu 14 Tage und tägliche Fenster bis zu 93 Tage ab. Gibt standardmäßig Daten für das angemeldete Konto zurück. Unterkonten explizit einbeziehen. |
| `get_billing_usage_costs` | Nutzung und Kosten, die Rechnungen entsprechen. | Der aktuelle und die vorherigen beiden Kalendermonate. Enthält standardmäßig die vollständige Kontenhierarchie. Die Daten für einen Monat sind vorläufig bis zum fünften Tag des folgenden Monats. |
| `get_message_logs` | Protokolle für einzelne Nachrichten. | Die letzten 48 Stunden. Protokolle können Empfängerkennungen, persönliche Informationen und Nachrichteninhalte enthalten. |
| `look_up_status_and_error_codes` | Beschreibungen bekannter Status- und Fehler-Code-Namen. | Bis zu 50 Namen pro Anfrage. [!DNL Infobip] können unbekannte Namen aus den Ergebnissen auslassen. |

Die Ergebnisse sind auf ein [!DNL Infobip] Rechenzentrum beschränkt. Die Tool-Auswahl steuert, welche Tools Member in Coworker verwenden können. Der [!DNL Infobip], den Mitglieder bei der Anmeldung gewähren, die Kontenhierarchie oder die Berechtigungen, die [!DNL Infobip] erzwingt, werden dadurch nicht eingeschränkt.

>[!IMPORTANT]
>
>Nachrichtenprotokolle können personenbezogene Daten enthalten, z. B. Empfängerkennungen und Nachrichteninhalte. Rechnungsinformationen sind vertraulich und decken standardmäßig die gesamte Kontenhierarchie ab. Aktivieren Sie diese Tools nur, wenn Ihr Unternehmen deren Verwendung genehmigt. Verwenden Sie explizite, genehmigte Kontofilter und eingeschränkte Abfragen.

## Als Mitglied anmelden {#sign-in-as-a-member}

Nachdem ein Administrator den Connector konfiguriert hat, meldet sich jedes Mitglied mit seinem eigenen [!DNL Infobip] an. Ihre Anmeldung gehört nur Ihnen. Andere Mitglieder verwenden Ihre Anmeldeinformationen nicht.

1. Öffnen Sie **[!UICONTROL Anpassungen]**, wählen Sie **[!UICONTROL Benutzer]** und dann **[!UICONTROL Externe Connectoren]** aus. Suchen Sie **[!UICONTROL Infobip Observe]**.

   Wenn die Karte **[!UICONTROL Nicht konfiguriert]** und &quot;**[!UICONTROL noch nicht verfügbar“ anzeigt. Ihr Administrator muss dies einrichten.]** bitten Sie Ihren Administrator, den [Connector konfigurieren](#configure-organization).

1. Wählen Sie **[!UICONTROL Anmelden]** und verwenden Sie das vorgesehene [!DNL Infobip]. Führen Sie die Schritte Single Sign-on (SSO), Multi-Faktor-Authentifizierung (MFA) und Einverständnisaufforderung selbst aus. Überprüfen Sie vor der Genehmigung den angeforderten Zugriff, das Konto und das Rechenzentrum.

1. Kehren Sie zu Mitarbeiter zurück und öffnen Sie die Connector-Details. Überprüfen Sie die Tools, die Ihr Administrator aktiviert hat.

   Mitglieder können die Tools anzeigen, aber die Organisationskonfiguration nicht ändern.

1. Wählen Sie **[!UICONTROL Verbindung testen]** aus.

   Ein erfolgreicher Test bestätigt, dass ein Mitarbeiter eine Verbindung herstellen und die Tools auflisten kann. Es bestätigt nicht, dass jedes Tool erfolgreich ausgeführt wird.

1. Wenn Sie autorisiert sind und Ihr Administrator das `look_up_status_and_error_codes`-Tool aktiviert hat, führen Sie die Suche in [Überprüfen Sie Ihre Verbindung](#check-connection) aus.

1. Um Ihr [!DNL Infobip]-Konto vom Connector zu trennen, wählen Sie **[!UICONTROL Abmelden]** aus.

   Die Abmeldung widerruft nicht unbedingt den Zugriff, den Sie in [!DNL Infobip] gewährt haben.

## Verbindung überprüfen {#check-connection}

Um zu bestätigen, dass der Connector mit Ihrem Konto funktioniert, führen Sie eine schreibgeschützte Suche aus. Stellen Sie sicher, dass der Administrator das `look_up_status_and_error_codes`-Tool aktiviert hat. Starten Sie dann einen Chat und geben Sie eine Eingabeaufforderung ein.

Beispielaufforderung:

* „Mit Infobip Observe suchen Sie den Status-Code NO_ERROR und beschreiben, was er bedeutet. Fragen Sie keine Traffic-Metriken, Rechnungsstellung oder Nachrichtenprotokolle ab.“

Bestätigen Sie, dass das Ergebnis eine Beschreibung der `NO_ERROR` ohne Fehlermeldung enthält. Bei einer erfolgreichen Suche wird nicht bestätigt, dass die Traffic-, Abrechnungs- oder Nachrichtenprotokoll-Tools für Ihr Konto funktionieren. Fragen Sie keine Abrechnungs- oder Nachrichtenprotokolle ab, nur um die Verbindung zu testen.

## Fehlerbehebung beim Zugriff {#troubleshoot-access}

Wenn Sie nicht auf Ihre [!DNL Infobip] zugreifen können, fragen Sie bei Ihrem Administrator nach:

| Problem | Was zu überprüfen ist |
| --- | --- |
| Der **[!UICONTROL Infobip Observe]**-Connector fehlt | Vergewissern Sie sich, dass der Connector für Ihre Organisation verfügbar ist und dass Sie über die Berechtigung zum Verwalten von Organisations-Connectoren verfügen. Wenden Sie sich bei Bedarf an den Adobe-Support. |
| Zustimmung oder Anmeldung schlägt fehl | Überprüfen Sie das verwendete [!DNL Infobip]-Konto, Ihre [!DNL Observe] und das Rechenzentrum. Teilen Sie nicht die Einverständnis-URL, Rückruf-URL oder Autorisierungs-Codes, wenn Sie um Hilfe bitten. |
| Anmeldung erfolgreich, aber ein Tool schlägt fehl | Überprüfen Sie die effektiven [!DNL Infobip], das Konto und das Rechenzentrum, mit dem Sie sich angemeldet haben, und den [!DNL Infobip] zurückgegebenen Fehler. Eine erfolgreiche Anmeldung bestätigt nicht, dass ein Tool erfolgreich ausgeführt wird. |
| Ein Tool ist nicht verfügbar | Überprüfen Sie die Tools, die Ihr Administrator aktiviert hat. Coworker aktiviert neue [!DNL Infobip] nicht automatisch. |
| Die Konfiguration kann nicht gespeichert werden | Mindestens ein Tool ausgewählt lassen. Um das Anbieten des Connectors zu beenden, entfernen Sie ihn stattdessen. |
| Rechnungsergebnisse enthalten unerwartete Konten | Die Fakturierungsergebnisse enthalten standardmäßig die vollständige Kontenhierarchie. Beenden Sie und überprüfen Sie dann die genehmigten Kontofilter und -berechtigungen. |
| Nachrichtenprotokolle zeigen vertrauliche Daten an | Beenden Sie die Abfrage und beschränken Sie spätere Abfragen auf genehmigte, nicht vertrauliche Daten. Fügen Sie keine Rohprotokolle in Chats oder Support-Tickets ein. |
| Die Status-Code-Suche ist erfolgreich, aber eine andere Anfrage schlägt fehl | Untersuchen Sie die fehlgeschlagene Anfrage separat. Eine erfolgreiche Suche bestätigt nicht, dass jedes Tool oder Konto funktioniert. |
