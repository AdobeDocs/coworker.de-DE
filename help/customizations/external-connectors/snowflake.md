---
title: Snowflake Cortex AI External Connector
description: Erfahren Sie, wie Sie den externen Snowflake Cortex AI-Connector in CX Enterprise Coworker mit einem Service-Konto oder einer persönlichen Anmeldung zum Abfragen von Snowflake-Daten einrichten.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Dieser Connector befindet sich in der Betaphase."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 942f76a48eabbc9ac795d9e53aad1faceff31393
workflow-type: tm+mt
source-wordcount: '2057'
ht-degree: 0%
---

# Externer Snowflake Cortex AI-Connector {#snowflake}

Verwenden Sie den externen Connector von [!DNL Snowflake Cortex AI] , um Fragen zu Ihren [!DNL Snowflake] in Adobe CX Enterprise Coworker einfach zu stellen. Der Connector verknüpft Coworker mit einem [!DNL Snowflake] verwalteten MCP-Server (Model Context Protocol) in Ihrem [!DNL Snowflake]. Die Mitarbeiter können dann die Tools verwenden, die der Server bereitstellt, z. B. [!DNL Cortex Analyst]-, [!DNL Cortex Search]- und SQL-Tools.

>[!AVAILABILITY]
>
>Der externe [!DNL Snowflake Cortex AI]-Connector befindet sich in der Beta-Phase. Die Dokumentation und die Funktionalität können sich ändern.

## Connector-Konfiguration {#connector-configuration}

Der Connector-Konfigurationsprozess besteht aus zwei separaten Teilen:

* **Einrichten der Organisation:** Ein Administrator verbindet einen Mitarbeiter mit einem vorhandenen [!DNL Snowflake] MCP-Server, wählt aus, wie sich Personen anmelden, und wählt die Tools aus, die Mitglieder verwenden können.
* **Mitgliederzugriff:** Mitglieder verwenden die Verbindung entweder mit einer freigegebenen Organisationsidentität oder mit ihrer eigenen [!DNL Snowflake] Identität, je nach der Anmeldeoption.

Der Administrator wählt eine der folgenden Anmeldeoptionen aus:

| Option | Was der Administrator bereitstellt | Funktionsweise des Zugriffs |
| --- | --- | --- |
| **[!UICONTROL Organisations-Service-Konto]** | Ein [!DNL Snowflake] programmgesteuertes Zugriffstoken (PAT) für ein Service-Konto. | Alle Mitglieder verwenden die Berechtigungen des Service-Kontos. Token-Ablauf oder -Widerruf wirken sich auf alle Mitglieder aus. |
| **[!UICONTROL Jede Person meldet sich an]** | Die Client-ID und das Client-Geheimnis einer [!DNL Snowflake] OAuth-Integration sowie eine optionale [!DNL Snowflake]. | Jedes Mitglied meldet sich mit seiner eigenen [!DNL Snowflake] an und der Zugriff erfolgt entsprechend seinen [!DNL Snowflake]. |

Keine der Optionen gewährt [!DNL Snowflake] Berechtigungen, die die ausgewählte Identität noch nicht hat. [!DNL Snowflake] erzwingt Berechtigungen für jede Anfrage.

## Voraussetzungen {#prerequisites}

Coworker stellt eine Verbindung zu einem vorhandenen [!DNL Snowflake] MCP-Server her. Es erstellt weder den Server noch seine Tools. Bevor Sie beginnen, stellen Sie Folgendes sicher:

* **Für die Einrichtung einer Organisation:** Ein Konto mit der Berechtigung zum Verwalten von Organisations-Connectoren in einem Kollegen.
* **Für den [!DNL Snowflake] MCP-Server:** Die vollständige HTTPS-URL des Servers, einschließlich Datenbank, Schema und Servername.
* **Für die Option „Service-Konto“:** PAT für ein dediziertes Service-Konto. Die Dienstkontorolle sollte nur über die Berechtigungen verfügen, die für den MCP-Server und dessen Tools erforderlich sind.
* **Für die Option zur persönlichen Anmeldung:** Eine [!DNL Snowflake] OAuth-Integration mit ihrer Client-ID und ihrem Client-Geheimnis. Außerdem benötigen Sie einen [!DNL Snowflake] Administrator, der die Coworker-Umleitungs-URL registrieren und die Integration konfigurieren kann.

>[!IMPORTANT]
>
>Geben Sie in Screenshots, Chats oder Support-Tickets niemals PATs, OAuth-Client-Geheimnisse oder andere Anmeldeinformationen frei. Verwenden Sie Organisationsgeheimnisse und eine [!DNL Snowflake] Identität mit den geringsten Rechten.

### Snowflake MCP-Server konfigurieren {#configure-snowflake-mcp-server}

Ein [!DNL Snowflake]-Administrator muss die folgenden Aufgaben in [!DNL Snowflake] ausführen, bevor Sie den Connector konfigurieren:

1. Erstellen Sie den MCP-Server und definieren Sie die verfügbaren Tools.
1. Gewähren Sie den erforderlichen Rollen Zugriff auf den MCP-Server, seine Tools und die zugrunde liegenden Objekte.

   Der Zugriff auf den MCP-Server gewährt nicht automatisch Zugriff auf alle Werkzeuge oder Objekte.

1. Richten Sie die Authentifizierung für die Anmeldeoption ein, die Sie verwenden möchten:

   * Erstellen Sie für die Option „Service-Konto“ einen Pfad für das Service-Konto.
   * Erstellen Sie für die Option für die persönliche Anmeldung eine OAuth-Integration, die Aktualisierungs-Token ausgibt.

Anweisungen finden Sie in der folgenden [!DNL Snowflake]-Dokumentation:

* [Snowflake-verwalteter MCP-Server](https://docs.snowflake.com/en/user-guide/snowflake-cortex/cortex-agents-mcp){target="_blank"}
* [MCP-Server erstellen](https://docs.snowflake.com/en/sql-reference/sql/create-mcp-server){target="_blank"}
* [Übersicht über die Zugriffskontrolle](https://docs.snowflake.com/en/user-guide/security-access-control-overview){target="_blank"}
* [Konfigurieren von Snowflake OAuth für benutzerdefinierte Clients](https://docs.snowflake.com/en/user-guide/oauth-custom){target="_blank"}
* [Erstellen der Sicherheitsintegration (Snowflake OAuth)](https://docs.snowflake.com/en/sql-reference/sql/create-security-integration-oauth-snowflake){target="_blank"}
* [Verwenden von programmgesteuerten Zugriffstoken für die Authentifizierung](https://docs.snowflake.com/en/user-guide/programmatic-access-tokens){target="_blank"}

## Konfigurieren des Connectors für Ihre Organisation {#configure-organization}

Administratoren stellen den [!DNL Snowflake Cortex AI]-Connector für alle Personen in der Organisation zur Verfügung. Änderungen auf der Seite „Organisation“ gelten für alle Benutzer in Ihrer Organisation.

1. Öffnen Sie **[!UICONTROL Anpassungen]**, wählen Sie **[!UICONTROL Organisation]** und dann **[!UICONTROL Externe Connectoren]** aus. Wählen Sie auf der Karte **[!UICONTROL Snowflake Cortex AI]** die Option **[!UICONTROL Konfigurieren]**.

1. Geben **[!UICONTROL im Dialogfeld &quot;Snowflake Cortex AI]**&quot; die vollständige URL Ihres [!DNL Snowflake] MCP-Servers unter „Server **[!UICONTROL URL“]**. Die URL muss HTTPS verwenden und diesem Muster folgen:

   ```text
   https://<account-host>/api/v2/databases/<database>/schemas/<schema>/mcp-servers/<server-name>
   ```

   Verwenden Sie die exakte URL für Ihr [!DNL Snowflake]-Konto und den MCP-Server. Der Konto-Hostname darf keinen Unterstrich enthalten, einschließlich eines kodierten Unterstrichs (`%5F`). Geben Sie in der URL keine Anmeldeinformationen an. Coworker prüft das HTTPS-Schema, den Host und den Pfad vor dem Speichern.

1. Wählen **[!UICONTROL unter „Wer meldet sich an?]** eine Anmeldeoption aus und vervollständigen Sie dann deren Einstellungen.

   * **[!UICONTROL Organisations-Service]Konto:** Anfragen verwenden die Berechtigungen des Service-Kontos über ein programmgesteuertes Zugriffstoken (PAT). Verwenden Sie diese Option für den zentral verwalteten Zugriff. Verwenden Sie ein dediziertes Service-Konto mit einer eng gefassten Rolle, kein persönliches Konto.

     ![Das Dialogfeld &quot;Snowflake verbinden“ mit dem ausgewählten Organisations-Service-Konto, das das Feld Server-URL, die Optionen für das Service-Konto-Token, das Feld für das programmgesteuerte Zugriffstoken und eine Warnung anzeigt, dass jeder mit den Berechtigungen des Token-Inhabers agiert.](./assets/snowflake/org-service-account.png){width="500" zoomable="yes"}

     | Einstellung | Beschreibung |
     | --- | --- |
     | **[!UICONTROL Service-Konto-Token]** | Wählen Sie aus, wo das Token herkommt. Wählen Sie **[!UICONTROL Neu eingeben]**, um einen Pfad einzugeben, oder **[!UICONTROL Vorhandene geheime Daten verwenden]**, um ein Organisationsgeheimnis wiederzuverwenden, das bereits das Token enthält. Ein vorhandenes Geheimnis muss den vollständigen Wert für die `Authorization`-Kopfzeile enthalten, nicht nur das Roh-Token. |
     | **[!UICONTROL Programmgesteuertes Zugriffstoken]** | Erforderlich, wenn Sie **[!UICONTROL Neu eingeben]** auswählen. Erstellen Sie das Token für ein dediziertes [!DNL Snowflake]-Service-Konto nur mit den erforderlichen Berechtigungen. Anweisungen finden Sie unter **[!UICONTROL Erstellen eines programmgesteuerten Zugriffstokens]** im Dialogfeld. Coworker speichert das Token als Organisationsgeheimnis. |

     >[!IMPORTANT]
     >
     >Jeder, der diese Verbindung verwendet, handelt mit den Berechtigungen des Token-Besitzers. Wenn das Token abläuft oder widerrufen wird, funktioniert die Verbindung für alle Mitglieder nicht mehr.

     Das Erstellen und Verwenden eines PATH kann [!DNL Snowflake] Netzwerk- und Authentifizierungsrichtlinien unterliegen. Wenn die Token-Erstellung oder -Authentifizierung blockiert ist, bitten Sie Ihren [!DNL Snowflake], diese Richtlinien zu überprüfen.

   * **[!UICONTROL Jede Person meldet sich an]:** Anfragen verwenden die [!DNL Snowflake] Berechtigungen jeder Person. Verwenden Sie diese Option für einen gesteuerten, benutzergesteuerten Zugriff.

     ![Dialogfeld &quot;Snowflake verbinden“ mit der Auswahl „Jede Person meldet sich an“ mit den Feldern „Umleitungs-URL“, „Anmeldedaten für die OAuth-Integration“, „Client-ID der OAuth-Integration“ und „Client-Geheimnis“ sowie „Optionales Rollenfeld von Snowflake&quot;.](./assets/snowflake/org-oauth.png){width="500" zoomable="yes"}

     | Einstellung | Beschreibung |
     | --- | --- |
     | **[!UICONTROL Umleitungs-URL]** | Schreibgeschützt. Kopieren Sie diese URL und registrieren Sie sie als Umleitungs-URI in Ihrer [!DNL Snowflake] OAuth-Sicherheitsintegration. Der Wert muss genau übereinstimmen. Anweisungen finden Sie unter **[!UICONTROL Erstellen einer Snowflake OAuth-Integration]** im Dialogfeld. Die Umleitungs-URL unterscheidet sich von Umgebung zu Umgebung, kopieren Sie sie daher immer aus dem Dialogfeld. |
     | **[!UICONTROL Anmeldeinformationen für die OAuth-Integration]** | Wählen Sie aus, woher die Anmeldeinformationen kommen sollen. Wählen Sie **[!UICONTROL Neu eingeben]**, um die Client-ID und das Client-Geheimnis einzugeben, oder **[!UICONTROL Vorhandene geheime Daten verwenden]**, um die jeweiligen Unternehmensgeheimnisse auszuwählen. |
     | **[!UICONTROL Client-ID der OAuth-Integration]** | Erforderlich, wenn Sie **[!UICONTROL Neu eingeben]** auswählen. Die Client-ID Ihrer kundenverwalteten [!DNL Snowflake] OAuth-Integration. |
     | **[!UICONTROL Client-Geheimnis der OAuth-Integration]** | Erforderlich, wenn Sie **[!UICONTROL Neu eingeben]** auswählen. Das Client-Geheimnis derselben OAuth-Integration. Mitglieder geben diese Anmeldeinformationen nie ein. |
     | **[!UICONTROL Snowflake-Rolle]** | Optional. Die Rolle, die jede Sitzung verwendet und über die OAuth-`session:role:ROLE_NAME` angefordert wird. Die Rolle muss Ihren Mitgliedern gewährt werden und Zugriff auf den MCP-Server haben. Lassen Sie das Feld leer, um die Standardrolle jedes Mitglieds zu verwenden. |

     Coworker leitet die OAuth-Endpunkte von der Konto-URL ab und fordert ein Aktualisierungs-Token an. Konfigurieren Sie die OAuth-Integration, um Aktualisierungstoken auszugeben. Der angeforderte Bereich allein überschreibt die Integrationskonfiguration nicht.

     Kollege konvertiert den Rollennamen in Großbuchstaben. Rollen, die mit einem in Kleinbuchstaben angegebenen Namen erstellt wurden, können nicht verwendet werden. Wenn die OAuth-Integration die Rolle blockiert oder ein Mitglied nicht über die Rolle verfügt, kann die Anmeldung oder der Zugriff fehlschlagen.

1. Wählen Sie unter **[!UICONTROL Tools, die Benutzern zur Verfügung stehen]** die Tools aus, die Mitglieder verwenden können. Jeder [!DNL Snowflake] MCP-Server definiert seine eigenen Tools, sodass das Dialogfeld keine feste Liste anzeigt. Geben Sie die Werkzeugnamen, wie sie in Ihrem MCP-Server definiert sind, ein, nicht Werkzeugtypen wie `CORTEX_ANALYST_MESSAGE`. Um die Tool-Namen anzuzeigen, führen Sie `DESCRIBE MCP SERVER` in [!DNL Snowflake] aus.

   ![Das Dialogfeld &quot;Snowflake verbinden“ mit dem Snowflake-Rollenfeld, dem Abschnitt „Tools für Benutzende“ mit den Feldern „Zulässige Tool-Namen“ und „Blockierte Tool-Namen“, dem Hinweis zu Zugriff und Berechtigungen und einer Zusammenfassung mit OAuth-Authentifizierung (Kundenintegration), HTTP-Verbindung und einer 300-Sekunden-Tool-Zeitüberschreitung.](./assets/snowflake/org-tools.png){width="500" zoomable="yes"}

   | Einstellung | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Zulässige Tool-Namen]** | Die Tools, die Mitglieder verwenden können. Trennen Sie Namen durch Kommas oder Leerzeichen. Lassen Sie das Feld leer, damit alle Tools, die der Server bereitstellt, mit Ausnahme von blockierten Tools, zulässig sind. |
   | **[!UICONTROL Blockierte Tool-Namen]** | Die Werkzeuge, die Mitglieder niemals benutzen können. Trennen Sie Namen durch Kommas oder Leerzeichen. Blockierte Tools sind nicht verfügbar, auch wenn Sie sie zulassen. |

   >[!IMPORTANT]
   >
   >Wenn Sie **[!UICONTROL Zulässige Tool-Namen]** leer lassen, können Mitglieder jedes Tool verwenden, einschließlich jedes beliebigen SQL-Ausführungs-Tools. SQL-Ausführungstools führen SQL als verbundene Identität aus. Überprüfen Sie die Tooldefinitionen auf Ihrem Server und lassen Sie nur die Tools zu, die Ihr Unternehmen benötigt.

   Toolbeschreibungen sind kein Ersatz für [!DNL Snowflake] Berechtigungen oder andere Zugriffssteuerungen. Richten Sie für [!DNL Cortex Analyst] Tools eine semantische Ansicht und die erforderlichen Gewährungen ein, einschließlich der Rolle `SNOWFLAKE.CORTEX_USER`-Datenbank. Konfigurieren Sie für [!DNL Cortex Agent] Tools schreibgeschützte Tools und deaktivieren Sie die Code-Ausführung in [!DNL Snowflake]. Mitglieder können die Werkzeugauswahl nicht ändern.

1. Überprüfen Sie **[!UICONTROL Zugriff und Berechtigungen]** und wählen Sie dann **[!UICONTROL Verbindung speichern]** aus. Die Karte **[!UICONTROL Snowflake Cortex AI]** zeigt **[!UICONTROL Konfiguration gespeichert]**.

   Wählen Sie **[!UICONTROL Konfiguration anzeigen]** aus, um die Server-URL, den Authentifizierungstyp und die Toolrichtlinie zu überprüfen. Wählen Sie dann **[!UICONTROL Verbindung testen]**, um den Zugriff zu überprüfen und die Server-Tools zu ermitteln.

   Bei neuen [!DNL Snowflake]-Verbindungen wird eine Zeitüberschreitung von 300 Sekunden verwendet. Bei einer älteren Verbindung ohne gespeicherte Zeitüberschreitung kann der Standardwert von 60 Sekunden verwendet werden. Überprüfen Sie die angezeigte Zeitüberschreitung für eine vorhandene Verbindung.

Ein erfolgreicher Test bestätigt nicht, dass jedes Tool oder [!DNL Snowflake] Objekt für jedes Mitglied verfügbar ist.

## Verwenden des Connectors als Mitglied {#use-as-member}

Nachdem ein Administrator den Connector konfiguriert hat, öffnen Sie ihn in Ihrer eigenen Ansicht **[!UICONTROL Anpassungen]**.

1. Öffnen Sie **[!UICONTROL Anpassungen]**, wählen Sie **[!UICONTROL Benutzer]** und dann **[!UICONTROL Externe Connectoren]** aus.

   Wenn die Karte **[!UICONTROL Snowflake Cortex AI]** angezeigt wird **[!UICONTROL Nicht konfiguriert]**, bitten Sie Ihren Administrator, den [Connector zu konfigurieren](#configure-organization).

1. Öffnen Sie **[!UICONTROL Snowflake Cortex AI]**. Die Connector-Details sind für Mitglieder schreibgeschützt. Sie können die Server-URL, die Anmeldeinformationen oder die Tool-Auswahl nicht ändern.

1. Wenn die Verbindung ein Organisations-Service-Konto verwendet, verwenden Anfragen die Identität der Organisation. Sie müssen sich nicht anmelden. Geben Sie niemals den Pfad ein oder teilen Sie ihn.

1. Wenn die Verbindung eine Pro-Person-Anmeldung verwendet, starten Sie die Anmeldung und authentifizieren Sie sich mit dem vorgesehenen [!DNL Snowflake]. Führen Sie alle erforderlichen Schritte für Single Sign-on (SSO) oder Multi-Faktor-Authentifizierung (MFA) aus. Bestätigen Sie ggf. die angeforderte Organisation, Anwendung und Rolle.

1. Wählen Sie bei Bedarf **[!UICONTROL Verbindung testen]** aus. Ein erfolgreicher Test zeigt **[!UICONTROL Verbindung erfolgreich]** und die Anzahl der verfügbaren Tools an.

   ![Details zum Snowflake-Connector, die einen Verbindungsstatus, eine Meldung über den Verbindungserfolg mit fünf verfügbaren Tools, einen Hinweis, dass der Administrator den Connector eingerichtet hat, sowie die Server-URL, die Anmeldungsoption, die Authentifizierung, die Verbindung und die Zeitüberschreitung des Tools anzeigen.](./assets/snowflake/member-details.png){width="700" zoomable="yes"}

   Vor einem erfolgreichen Test werden in den Details möglicherweise nur die Tool-Namen angezeigt, die Ihr Administrator zugelassen hat, oder Sie werden aufgefordert, den Test auszuführen. Nach dem Test wird jedes Tool mit der zugehörigen Beschreibung angezeigt.

   ![Details zum Snowflake-Connector, die den Verbindungstyp, die Tool-Zeitüberschreitung, den Anmeldestatus, die Schaltflächen „Abmelden“ und „Aktualisieren“ und fünf vom Administrator aktivierte Beispiel-Tools anzeigen.](./assets/snowflake/member-tools.png){width="700" zoomable="yes"}

Die Tools im Beispiel werden von einem [!DNL Snowflake] MCP-Server definiert. Welche Tools angezeigt werden, hängt von Ihrem Server und der Toolauswahl Ihres Administrators ab.

Die Authentifizierungsdetails der Verbindung zeigen an, ob sie einen PAT, ein maschinelles OAuth oder einen OAuth pro Person verwendet. Um Ihr [!DNL Snowflake]-Konto zu trennen, wählen Sie **[!UICONTROL Abmelden]** aus.

Ein **[!UICONTROL Verbunden]**-Status garantiert nicht den Zugriff auf ein bestimmtes Tool oder Datenobjekt. [!DNL Snowflake] Finanzhilfen, Richtlinien und die ausgewählte Rolle gelten weiterhin.

## Fehlerbehebung beim Zugriff {#troubleshoot-access}

Wenn die Einrichtung, Anmeldung oder der Zugriff fehlschlägt, wenden Sie sich an Ihren Administrator, um Folgendes zu überprüfen:

| Problem | Was zu überprüfen ist |
| --- | --- |
| Die Server-URL wurde abgelehnt | Die URL verwendet HTTPS und den vollständigen `/api/v2/databases/<database>/schemas/<schema>/mcp-servers/<server-name>`. Der Host-Name des Kontos enthält keine Unterstriche und die URL verfügt über keine Anmeldeinformationen. |
| Der Pfad kann nicht erstellt oder verwendet werden | Netzwerkrichtlinie, Authentifizierungsrichtlinie, Token-Ablauf und Rolle des Service-Kontos. Wenn Sie vorhandene geheime Daten verwenden, vergewissern Sie sich, dass sie den vollständigen Wert der `Authorization`-Kopfzeile enthalten. |
| Die OAuth-Umleitungs-URL stimmt nicht überein | Die [!DNL Snowflake] OAuth-Integration verfügt über die exakte Umleitungs-URL aus derselben Coworker-Umgebung. |
| Anmeldung erfolgreich, Anfragen schlagen fehl | Die Rolle wird dem Mitglied gewährt und ist durch die OAuth-Integration zulässig. Die Integration gibt Aktualisierungstoken aus, und die Client-ID und das Geheimnis gehören zur beabsichtigten Integration. |
| Ein Tool fehlt oder wird verweigert | Die Einstellungen **[!UICONTROL Zulässige Toolnamen]** und **[!UICONTROL Blockierte Toolnamen]**, die Toolverfügbarkeit auf dem MCP-Server und die [!DNL Snowflake] gewähren für den Server, das Tool und die zugrunde liegenden Objekte. |
| Zeitüberschreitung bei einem Tool-Aufruf | Die **[!UICONTROL Tool-Zeitüberschreitung]** in den Connector-Details. Neue Verbindungen benötigen 300 Sekunden. Ältere Verbindungen ohne gespeicherte Zeitüberschreitung benötigen möglicherweise 60 Sekunden. |
