---
title: Adobe CX Coworker Gateway - Übersicht
description: Adobe CX Coworker Gateway ist das einheitliche MCP für Adobe CX Enterprise, das MCP-Clients eine einzige Verbindung zu unterstützten Produkt-Tools bietet.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 4%
---
# Adobe CX Coworker-Gateway {#mcp-overview}

Adobe CX Coworker Gateway ist das Unified Model Context Protocol (MCP) für Adobe CX Enterprise. Mit einer Verbindung können MCP-kompatible Clients auf die Adobe-Produkttools zugreifen, zu deren Verwendung Ihr Unternehmen und Ihr Konto berechtigt sind.

>[!IMPORTANT]
>
>Ihre Adobe-Organisation muss aktiviert sein, bevor Sie **CX Coworker Gateway**-Tools verwenden können.
>
>Wenn Ihre Organisation noch keinen Zugriff hat, senden Sie eine E-Mail an [cx-coworker-gateway-support@adobe.com](mailto:cx-coworker-gateway-support@adobe.com), um die Aktivierung für Ihre Organisation anzufordern.

Verwenden Sie den CX Coworker Gateway-Endpunkt für alle MCP-Client-Setups:

```
https://cx-coworker-gateway.adobe.io/mcp
```

Nachdem Sie eine Verbindung hergestellt haben, stellt der Endpunkt die für Ihre Adobe-Organisation verfügbaren Tools und Anmeldedaten bereit. Produktspezifische Seiten in diesem Handbuch beschreiben, was jedes Produkttool tun kann, auf welche Daten es zugreifen kann und welche produktspezifischen Einschränkungen es hat.

## Was ist das Modell-Kontextprotokoll? {#mcp-what-is}

MCP (Model Context Protocol) ist ein Open-Source-Standard für die Verbindung von KI-Anwendungen mit externen Systemen. MCP-kompatible Clients wie [!DNL Claude], [!DNL ChatGPT], [!DNL Cursor], [!DNL Claude Code], [!DNL Codex] und [!DNL VS Code] können diese Tools verwenden, um den Produktkontext abzurufen, unterstützte Vorgänge auszuführen und Antworten in natürlicher Sprache zurückzugeben.

CX Coworker Gateway bietet einen verwalteten Endpunkt für CX Coworker Gateway-Produktwerkzeuge. Anstatt separate Produkt-Server hinzuzufügen, stellen Sie eine Verbindung einmal mit dem Endpunkt her und verwenden Sie die Produkt-Tools, die für Ihre entsprechenden Lösungen angezeigt werden.

## Verfügbare Produktwerkzeuge {#available-product-tools}

Die folgenden Produkt-Tools sind in diesem Handbuch dokumentiert:


| Produkt-Tools | Was sie über den Endpunkt verfügbar macht | Verfügbarkeit | Dokumentation |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ------------ | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **Real-Time CDP** | Zielgruppen, Ziele, Quellen, Identity-Namespaces und Aktivierungszustand (schreibgeschützt) | Beta | [Real-Time CDP-Tools](rtcdp-mcp.md) |
| **Experience Platform** | Schemata, Datensätze, Data Governance, Query Service, Audit-Ereignisse, Observability-Metriken und Sandbox-Konsistenzprüfungen (schreibgeschützt) | Beta | [Experience Platform-Tools](aep-mcp.md) |
| **Journey Optimizer** | Kampagnen, Journey und Kanalkonfigurationen (schreibgeschützt); Inhaltsvorlagen, Fragmente, Landingpages und Inline-Nachrichteninhalte (Lesen und Schreiben) | Beta | [Journey Optimizer-Tools](ajo-mcp.md) |
| **Customer Journey Analytics** | Datenansichten, Dimensionen, Metriken, Berichte, Segmente, Datumsbereiche, Projekte und Zielgruppen (lesen und schreiben) | Verfügbar | [Customer Journey Analytics-Tools](cja-mcp.md) |
| **Adobe Analytics** | Report Suites, Dimensionen, Metriken, Berichte, Segmente, Datumsbereiche und Workspace-Projekte (Lesen und Schreiben für unterstützte Komponenten) | Verfügbar | [Adobe Analytics-Tools](analytics-mcp.md) |
| **Workfront** | Work-Management-Tools für Projekte, Aufgaben und Genehmigungs-Workflows | Vorschau | [Workfront MCP-Server](https://experienceleague.adobe.com/de/docs/workfront/using/basics/workfront-mcp-server/workfront-mcp-server-overview) |


>[!NOTE]
>
>Die Verfügbarkeit der Tools hängt von Ihren Produktlizenzen, der Aktivierung für Unternehmen, den Produktberechtigungen und den zur Authentifizierung verwendeten Adobe-Anmeldeinformationen ab. Das MCP zeigt nur Tools an, auf die Ihr Unternehmen und Ihr Benutzerkonto zugreifen dürfen. Siehe [Zugriff auf CX Coworker Gateway-Tools](access.md).



## Erste Schritte {#mcp-get-started}

1. Überprüfen Sie [Zugriff auf CX Coworker Gateway](access.md)Tools, um die Produktverfügbarkeit, -aktivierung und -berechtigungen zu bestätigen.
2. Folgen Sie [Adobe für CX Coworker Gateway installieren](install.md), um Ihren MCP-Client mit dem Endpunkt zu verbinden.
3. Lesen Sie die Produktseite für jedes Produkt-Tool, das Sie verwenden möchten.

