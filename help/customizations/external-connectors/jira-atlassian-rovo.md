---
title: Jira / Atlassian Rovo externer Stecker
description: Erfahren Sie, wie Sie den externen Jira / Atlassian Rovo-Connector in CX Enterprise Coworker einrichten und sich bei Atlassian anmelden, um Jira-Arbeitselemente zu lesen und zu durchsuchen.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Dieser Connector befindet sich in der Betaphase."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 92e7715a5eb7ab4f8feb7348384c94fabc1b78cf
workflow-type: tm+mt
source-wordcount: '1482'
ht-degree: 1%
---

# Externer Anschluss Jira / Atlassian Rovo {#jira-atlassian-rovo}

Verwenden Sie den externen Connector [!DNL Jira] / [!DNL Atlassian Rovo] , um Ihre [!DNL Jira] Arbeitselemente in Adobe CX Enterprise Coworker zu lesen und zu durchsuchen. Bitten Sie nach der Einrichtung des Connectors einen Kollegen, Arbeitselemente zu finden, ihre Details zu lesen und mit Jira Query Language (JQL) zu suchen. Der Connector ist ein von [!DNL Atlassian] gehosteter MCP-Server (Model Context Protocol).

>[!AVAILABILITY]
>
>Der externe [!DNL Jira]/[!DNL Atlassian Rovo]-Connector befindet sich in der Beta-Phase. Die Dokumentation und die Funktionalität können sich ändern.

## Connector-Konfiguration {#connector-configuration}

Der Connector-Konfigurationsprozess besteht aus drei separaten Teilen:

* **[!DNL Atlassian]:** Ein Administrator der [!DNL Atlassian] Organisation ermöglicht der Domain der CoWorker-Umleitungs-URL und überprüft die MCP-Zugriffsrichtlinien.
* **Einrichten der Organisation:** Ein Mitarbeiter-Administrator konfiguriert den Connector einmal für die gesamte Organisation. Der Administrator wählt die schreibgeschützten Tools aus, die Mitglieder verwenden können.
* **Mitglied anmelden** Jedes Mitglied meldet sich mit seinem eigenen [!DNL Atlassian] an. Mitglieder können nur auf die [!DNL Jira] Daten zugreifen, zu deren Anzeige ihr Konto berechtigt ist.

Beim Speichern der Organisationskonfiguration werden weder Mitglieder angemeldet noch [!DNL Jira] Berechtigungen erteilt. Jedes Mitglied muss sich separat anmelden.

Der Connector hat keine Option für ein freigegebenes Dienstkonto oder API-Token. Der -Mitarbeiter registriert die OAuth-Anwendung automatisch bei [!DNL Atlassian], sodass Sie keine Client-ID oder kein Client-Geheimnis eingeben.

Obwohl der Connector-Name [!DNL Atlassian Rovo] enthält, fordert der Connector nur Lese- [!DNL Jira] Suchzugriff an. Es wird kein [!DNL Confluence], [!DNL Rovo], kein Schreibzugriff oder destruktiver Zugriff angefordert. Andere [!DNL Atlassian] MCP-Funktionen sind nicht unbedingt über diesen Connector verfügbar.

## Voraussetzungen {#prerequisites}

Bevor Sie beginnen, stellen Sie Folgendes sicher:

* **Für die Einrichtung einer Organisation:** Ein Konto mit der Berechtigung zum Verwalten von Organisations-Connectoren in einer Organisation, in der der [!DNL Jira]-/[!DNL Atlassian Rovo]-Connector verfügbar ist.
* **Zur [!DNL Atlassian]:** Ein Administrator der [!DNL Atlassian] Organisation, der den MCP-Zugriff und die Domain der CoWorker-Umleitungs-URL genehmigen kann.
* **Für die Anmeldung als Mitglied:** [!DNL Atlassian] Konten mit Zugriff auf die vorgesehenen [!DNL Jira], Projekte und Arbeitselemente.
* **Für den Netzwerkzugriff:** [!DNL Atlassian] IP-Zulassungslisten und App-Richtlinien, die die Verbindung zulassen. Eine erfolgreiche Anmeldung bestätigt nicht, dass Tool-Anfragen zulässig sind.
* **[!DNL Rovo]aktiviert:** [!DNL Rovo] für Ihre [!DNL Atlassian] Organisation und die vorgesehenen [!DNL Jira] Sites aktiviert, bevor Mitglieder den Connector verwenden. Weitere Informationen finden Sie unter [Aktivieren von Rovo](https://www.atlassian.com/software/rovo/guides/admin-guide/rovo-activation) in der [!DNL Atlassian].

## Vorbereiten [!DNL Atlassian] Zugriffs {#prepare-atlassian}

Bevor sich Mitglieder anmelden, bereitet ein Administrator der [!DNL Atlassian] Organisation den Zugriff auf [!DNL Atlassian Administration] vor:

1. Öffnen Sie [!DNL Atlassian Administration] und wählen Sie die gewünschte Organisation aus.

1. Wählen Sie **[!UICONTROL Connectoren]** > **[!UICONTROL Atlassian MCP Server]** > **[!UICONTROL Domain hinzufügen]**.

1. Fügen Sie die Domain der **[!UICONTROL Umleitungs-URL]** hinzu, die im Dialogfeld „Worker-Setup“ angezeigt wird. Das Dialogfeld finden Sie unter [Konfigurieren des Connectors für Ihre Organisation](#configure-organization).

   Befolgen Sie die Formatierungsregeln für [!DNL Atlassian] Domains, anstatt die vollständige URL einzufügen. Weitere Informationen finden Sie unter [Verfügbare Atlassian MCP-Server](https://support.atlassian.com/security-and-access-policies/docs/available-atlassian-mcp-server-domains/) in der [!DNL Atlassian].

1. Überprüfen Sie die MCP-Berechtigungsgruppen, App-Richtlinien und IP-Zulassungslisten mit dem [!DNL Atlassian]. Weitere Informationen finden Sie in der folgenden [!DNL Atlassian]:

   * [Unterstützte Atlassian MCP-Tools](https://support.atlassian.com/atlassian-ai-gateway/docs/supported-tools/) für die Berechtigungsgruppen und Bereiche, die jedes Tool erfordert
   * [Control Atlassian MCP Server Settings](https://support.atlassian.com/security-and-access-policies/docs/control-atlassian-mcp-server-settings/), für Authentifizierung und IP-Zulassungsauflistung

Verwenden Sie immer die Umleitungs-URL, die im Dialogfeld „Mitarbeiter“ für die Umgebung angezeigt wird, die Sie einrichten. Kopieren Sie keine Umleitungs-URL aus einer anderen Umgebung.

## Konfigurieren des Connectors für Ihre Organisation {#configure-organization}

Administratoren stellen den [!DNL Jira]/[!DNL Atlassian Rovo]-Connector für alle Personen in der Organisation zur Verfügung. Änderungen auf der Seite „Organisation“ gelten für alle Benutzer in Ihrer Organisation.

1. Öffnen Sie **[!UICONTROL Anpassungen]**, wählen Sie **[!UICONTROL Organisation]** und dann **[!UICONTROL Externe Connectoren]** aus. Wählen Sie auf der **[!UICONTROL Jira / Atlassian Rovo]**-Karte **[!UICONTROL Konfigurieren]**. Mitglieder können diese Verbindung nicht konfigurieren oder entfernen.

1. Überprüfen Sie **[!UICONTROL Dialogfeld „Jira / Atlassian Rovo]**&quot; die feste **[!UICONTROL Server-URL]**, `https://mcp.atlassian.com/v2/mcp`.

   Überprüfen Sie die **[!UICONTROL Umleitungs-URL]** und stellen Sie sicher, dass ein [!DNL Atlassian]-Administrator seine Domain genehmigt, wie in [Atlassischen Zugriff vorbereiten](#prepare-atlassian) beschrieben. Sie geben keine OAuth-Anmeldeinformationen ein.

1. Wählen Sie unter **[!UICONTROL Tools, die Benutzern zur Verfügung stehen]** die Tools aus, die Mitglieder verwenden können. Weitere Informationen finden Sie unter [Verfügbare Tools](#available-tools).

   Das Tool zur `getAccessibleAtlassianResources` Site-Erkennung ist erforderlich und bleibt aktiviert. Die anderen fünf Tools sind optional. Um ein optionales Tool für alle Benutzer in Ihrer Organisation zu blockieren, entfernen Sie es. Um die entfernten Werkzeuge wieder anzuzeigen, wählen Sie **[!UICONTROL Alle Werkzeuge wiederherstellen]** aus. Sie können die Konfiguration speichern, wenn nur die Site-Erkennung aktiviert ist, aber die Mitglieder dann keine Arbeitselemente lesen oder suchen können.

   ![Das Dialogfeld Jira / Atlassian Rovo verbinden mit der Server-URL, einer redigierten Umleitungs-URL und sechs verfügbaren Tools für Benutzer sowie dem erforderlichen Tool getAccessibleAtlassianResources und fünf optionalen Tools.](./assets/jira-atlassian-rovo/org-configure.png){width="500" zoomable="yes"}

1. Wählen Sie **[!UICONTROL Verbindung speichern]** und überprüfen Sie dann die Verbindungsdetails.

   Der Connector fordert die folgenden OAuth-Bereiche an, wenn sich jedes Mitglied anmeldet:

   | Anwendungsbereich | Zweck |
   | --- | --- |
   | `read:me`, `read:account` | Support-Autorisierung mit dem [!DNL Atlassian] Konto des Mitglieds. |
   | `read:jira:agent-interface` | Lesen [!DNL Jira] Daten. |
   | `search:jira:agent-interface` | [!DNL Jira] suchen. |
   | `offline_access` | Aktualisieren Sie das Anmelde-Token. |

   Die maximale Wartezeit für das Tool beträgt 60 Sekunden. Die erste Verbindung und Tool-Erkennung kann länger dauern.

### Verfügbare Tools {#available-tools}

Der [!DNL Jira]-/[!DNL Atlassian Rovo]-Connector bietet die folgenden schreibgeschützten Tools:

| Tool | Beschreibung | Administratorkontrolle |
| --- | --- | --- |
| `getAccessibleAtlassianResources` | Suchen Sie die [!DNL Atlassian] Sites und Cloud-IDs, auf die Sie zugreifen können. Die [!DNL Jira] Tools benötigen dieses Tool. | Erforderlich |
| `atlassianUserInfo` | Rufen Sie die Kontoinformationen des angemeldeten Benutzers ab. | Optional |
| `getJiraIssue` | Rufen Sie ein [!DNL Jira] Arbeitselement nach ID oder Schlüssel ab. | Optional |
| `searchJiraIssuesUsingJql` | [!DNL Jira] nach Arbeitselementen mit JQL. | Optional |
| `discover` | Finden Sie zusätzliche Tool-Vorgänge und deren Eingabeschemata. | Optional |
| `executeRead` | Führen Sie über `discover` gefundene Lesevorgänge aus, z. B. das Lesen von Kommentaren, Änderungsprotokollen, Projekten, Boards und Sprints. | Optional |

>[!IMPORTANT]
>
>Die `discover`- und `executeRead`-Tools bieten Membern Zugriff auf zusätzliche zulässige Lesevorgänge als Gruppe. Einzelne Vorgänge können nicht deaktiviert werden. Wenn dieser Zugriff für Ihre Organisation nicht akzeptabel ist, entfernen Sie beide Tools. Der Connector umfasst keine Schreibvorgänge (`executeWrite`) oder destruktiven Vorgänge (`executeDestructive`).

Durch das Entfernen optionaler Tools wird deren Verfügbarkeit in Coworker eingeschränkt. Die OAuth-Bereiche, die der Connector bei der Anmeldung anfordert, werden dadurch nicht reduziert.

Für jedes Tool sind spezifische [!DNL Atlassian] und Bereiche erforderlich. Weitere Informationen finden Sie unter [Unterstützte Atlassian MCP-Tools](https://support.atlassian.com/atlassian-ai-gateway/docs/supported-tools/) in der [!DNL Atlassian].

## Als Mitglied anmelden {#sign-in-as-a-member}

Nachdem ein Administrator den Connector konfiguriert hat, meldet sich jedes Mitglied mit seinem eigenen [!DNL Atlassian] an. Sie benötigen keine Client-ID, kein Client-Geheimnis und kein Zugriffs-Token, um sich anzumelden.

1. Öffnen Sie **[!UICONTROL Anpassungen]**, wählen Sie **[!UICONTROL Benutzer]** und dann **[!UICONTROL Externe Connectoren]** aus.

1. Finden Sie die **[!UICONTROL Jira / Atlassian Rovo]** Karte. Wenn die Karte **[!UICONTROL Nicht konfiguriert]** und &quot;**[!UICONTROL noch nicht verfügbar“ anzeigt. Ihr Administrator muss dies einrichten.]** bitten Sie Ihren Administrator, den [Connector konfigurieren](#configure-organization). Mitglieder können den Connector nicht konfigurieren.

1. Wählen Sie **[!UICONTROL Anmelden]** aus und verwenden Sie das [!DNL Atlassian]-Konto, das Zugriff auf die vorgesehene [!DNL Jira] hat. Schließen Sie alle erforderlichen Single Sign-on (SSO), Multi-Faktor-Authentifizierung (MFA) und Einverständnisaufforderungen ab. Überprüfen Sie den angeforderten Lese- und Suchzugriff, bevor Sie zustimmen.

   >[!IMPORTANT]
   >
   >Fahren Sie nur fort, wenn Sie die App erkennen und Ihr Unternehmen den angeforderten Zugriff genehmigt.

1. Kehren Sie zu Mitarbeiter zurück und öffnen Sie die Connector-Details. Die Verbindung ist für Mitglieder schreibgeschützt und Sie können die Tools anzeigen, die Ihr Administrator aktiviert hat. Klicken Sie **[!UICONTROL Verbindung testen]**, um die Verbindung zu bestätigen.

1. Führen Sie optional eine kleine schreibgeschützte Prüfung durch, wie unter [Überprüfen des Jira-Zugriffs](#check-access) beschrieben.

Ein erfolgreicher Test bestätigt nicht, dass Sie auf jede [!DNL Jira] Site, jedes Projekt oder jedes Arbeitselement zugreifen können.

## Überprüfen des [!DNL Jira] {#check-access}

Um zu bestätigen, dass der Connector Ihre Daten lesen kann, starten Sie einen Chat und geben Sie eine schreibgeschützte Eingabeaufforderung ein.

Beispielaufforderung:

* „Suche in Jira nach bis zu fünf Arbeitselementen, die mir zugewiesen sind, sortiert nach der letzten Aktualisierung. Schließen Sie ihre Schlüssel und Links ein. Ändern Sie nichts.“

Damit diese Eingabeaufforderung funktioniert, muss Ihr Administrator ein Suchwerkzeug aktivieren, und Ihr [!DNL Jira]-Konto muss über die Berechtigung zum Anzeigen der Arbeitselemente verfügen.

## Fehlerbehebung beim Zugriff {#troubleshoot-access}

Wenn die Anmeldung oder der Zugriff fehlschlägt, wenden Sie sich an Ihren Administrator, um Folgendes zu überprüfen:

| Problem | Was zu überprüfen ist |
| --- | --- |
| Die Anmeldung für den Client oder die Domain ist blockiert | Vergewissern Sie sich, dass die Umleitungs-URL-Domain für Ihre Umgebung in [!DNL Atlassian Administration] unter den Einstellungen **[!UICONTROL Atlassian MCP Server]** genehmigt ist. |
| Einverständnis ist erfolgreich, aber Tool-Aufrufe werden verweigert | Überprüfen Sie Ihre [!DNL Jira], die [!DNL Atlassian] MCP-Berechtigungsgruppen, App-Richtlinien und IP-Zulassungslisten. Die für jedes Tool erforderlichen Berechtigungsgruppen finden Sie unter [Unterstützte Atlassian MCP-Tools](https://support.atlassian.com/atlassian-ai-gateway/docs/supported-tools/). |
| JQL-Suche schlägt fehl, aber andere Lesevorgänge funktionieren | Vergewissern Sie sich, dass Ihr Administrator `searchJiraIssuesUsingJql` aktiviert hat und dass die Verbindung den `search:jira:agent-interface` Bereich anfordert. |
| Einverständnis gibt `invalid_request` zurück | Bitten Sie Ihren Administrator, zu bestätigen, dass die Verbindungsanforderungen zusätzlich zu den [!DNL Jira] Bereichen `read:me` und `read:account`. |
| Nach einer Änderung werden immer noch ältere Bereiche angezeigt | Eine überholte Überschreibung des `jira_login`-Authentifizierungsanbieters auf Benutzerebene kann Vorrang vor der Organisationsverbindung haben. Bitten Sie einen Administrator, nur diese veraltete Überschreibung zu aktualisieren oder zu entfernen, und melden Sie sich dann erneut an. |
| Ein Tool fehlt | Bitten Sie Ihren Administrator, die Tool-Auswahl zu überprüfen. Zusätzliche Lesevorgänge benötigen sowohl `discover` als auch `executeRead`, die erforderlichen Bereiche und die richtigen Berechtigungen. |
| **[!UICONTROL Verbindung testen]** ist langsam oder Zeitüberschreitung | Die Tool-Erkennung kann länger als die 60-Sekunden-Tool-Zeitüberschreitung dauern. Überprüfen Sie, ob das Problem eine langsame Erkennung oder ein Anmeldefehler ist, bevor Sie die Anmeldeinformationen ändern. |

Wenn Sie um Hilfe bitten, geben Sie keine Passwörter, Token, Autorisierungs-Codes oder Einverständnis-URLs frei. Schließen Sie sie nicht in Screenshots oder Support-Tickets ein.
