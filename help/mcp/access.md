---
title: Zugriff auf CX Coworker Gateway-Tools
description: Überprüfen Sie die Produktverfügbarkeit, die Aktivierung des Unternehmens und die Berechtigungen, bevor Sie die Adobe CX Coworker Gateway-Tools verwenden.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 4%
---
# Zugriff auf CX Coworker Gateway-Tools {#mcp-access}

Adobe CX Enterprise stellt Produkt-Tools über einen einzigen MCP bereit. Der Zugriff wird von Produkt-Tools bewertet: Ihr Adobe-Unternehmen muss für die entsprechenden Produkt-Tools aktiviert sein und Ihr Benutzerkonto muss über die erforderlichen Produktberechtigungen verfügen, um die von diesen Tools bereitgestellten Produktdaten anzeigen oder ändern zu können.

>[!IMPORTANT]
>
>Ihre Adobe-Organisation muss aktiviert sein, damit Sie die CX Coworker-Gateway-Tools verwenden können. Wenn Ihr Unternehmen noch keinen Zugriff hat, wenden Sie sich an Ihr Adobe Account Team , um die Aktivierung für Ihr Unternehmen anzufordern.

## Zugriffsanforderungen {#mcp-requirements}


| Produkt-Tools | Verfügbarkeit | Zugriffsanforderungen |
| --- | --- | --- |
| Real-Time CDP | Beta | Active Real-Time CDP-Lizenz, Beta-Aktivierung für Ihr Adobe-Unternehmen und Berechtigungen zum Anzeigen der von Ihnen abgefragten Zielgruppen, Ziele, Quellen, Identitäten und Aktivierungsressourcen. |
| Experience Platform | Beta | Aktive Experience Platform-Lizenz, Beta-Aktivierung für Ihr Adobe-Unternehmen und Berechtigungen zum Anzeigen der von Ihnen abgefragten Schemata, Datensätze, Governance, Abfrage-Service, Audit und Sandbox-Ressourcen. |
| Journey Optimizer | Beta | Aktive Journey Optimizer-Lizenz, Beta-Aktivierung für Ihr Adobe-Unternehmen und Berechtigungen zum Anzeigen von Kampagnen, Journey und Kanalkonfigurationen. |
| Customer Journey Analytics | Verfügbar | Aktive Customer Journey Analytics-Lizenz und ein Produktprofil, das das Berechtigungselement **MCP-Zugriff** in Adobe Admin Console enthält. Produktberechtigungen steuern weiterhin, auf welche Datenansichten, Komponenten, Berichte, Projekte und Zielgruppen Sie zugreifen oder sie ändern können. |
| Adobe Analytics | Verfügbar | Aktive Adobe Analytics-Lizenz und ein Produktprofil, das das Berechtigungselement **MCP-Zugriff** in Adobe Admin Console enthält. Produktberechtigungen steuern weiterhin, auf welche Report Suites, Komponenten, Berichte, Segmente, Datumsbereiche und Projekte Sie zugreifen oder sie ändern können. |
| Workfront | Vorschau | Aktive Workfront-Lizenz und Aktivierung von Workfront MCP. Siehe die [Workfront MCP-Dokumentation](https://experienceleague.adobe.com/de/docs/workfront/using/basics/workfront-mcp-server/workfront-mcp-server-overview). |
| Target | Beta | Active Target-Lizenz mit einer Adobe Experience Platform-Organisation. Siehe die [Target MCP-Dokumentation](https://experienceleague.adobe.com/de/docs/target/using/mcp/target-mcp-get-started). |



>[!NOTE]
>
>Der MCP zeigt nur die Tools an, zu deren Verwendung Ihr Unternehmen und Ihre Anmeldedaten berechtigt sind. Wenn nach der Anmeldung ein Produkt-Tool fehlt, bestätigen Sie die Produktlizenzierung, die Aktivierung für das Unternehmen und die Benutzerberechtigungen.

## Zugriff anfordern {#mcp-request}

Wenden Sie sich bei Beta- oder Limited-Release-Produkt-Tools an Ihren Adobe-Kundenbetreuer und geben Sie an, welche Adobe für CX Coworker Gateway-Produkt-Tools Sie verwenden möchten. Ihr Ansprechpartner kann die Produktaktivierung koordinieren und bestätigen, wenn Ihr Adobe-Unternehmen bereit ist.

Bitten Sie bei allgemein verfügbaren Produkt-Tools, die das Berechtigungselement **MCP-Zugriff** verwenden, einen System- oder Produktadministrator, Ihr Konto zu einem Produktprofil hinzuzufügen, das MCP-Zugriff enthält.

## Produktinterne Aktivierung {#mcp-product-enablement}

Einige Produkte erfordern zusätzlich zum MCP-Zugriff eine produktinterne Aktivierung oder produktspezifische Berechtigungen. Beispiel:

- Adobe Analytics und Customer Journey Analytics erfordern das Berechtigungselement **MCP** Zugriff) in Adobe Admin Console.
- Workfront MCP-Tools werden in den Workfront-Einstellungen aktiviert.
- Beta-Produkt-Tools erfordern die Aktivierung der Adobe-Organisation, bevor ihre Tools über den MCP angezeigt werden.

Überprüfen Sie die Produktseite für das Produkt-Tool, das Sie für produktspezifische Berechtigungen, Kontextanforderungen und Einschränkungen verwenden möchten.

## Vor der Installation {#mcp-prerequisites}

Bevor Sie Ihren MCP-Client verbinden, überprüfen Sie Folgendes:

- Ihre Adobe-Organisation verfügt über die erforderlichen Produkt-Tools.
- Ihr Benutzerkonto verfügt über die erforderlichen Produktberechtigungen für die Daten und Vorgänge, die Sie verwenden möchten.
- Sie haben Zugriff auf einen unterstützten MCP-Client wie [!DNL Claude], [!DNL ChatGPT], [!DNL Cursor], [!DNL Claude Code], [!DNL Codex] oder [!DNL VS Code].
- Bei einer Unternehmensinstallation können Sie oder ein Kollege Connectoren oder benutzerdefinierte Apps in den Unternehmenseinstellungen Ihres MCP-Clients verwalten.

Weiter: [Adobe CX Coworker Gateway installieren](install.md).