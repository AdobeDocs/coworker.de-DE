---
title: Adobe Analytics-Tools in CX Coworker Gateway
description: Erfahren Sie, welche Adobe Analytics-Tools über Adobe CX Coworker Gateway verfügbar sind.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 5%
---
# Adobe Analytics-Tools in Adobe CX Coworker Gateway {#aa-mcp}

Sie können Adobe Analytics-Tools verwenden, um Report Suites zu untersuchen, Dimensionen und Metriken zu ermitteln, Berichte auszuführen und ausgewählte Analytics-Komponenten über einen MCP-kompatiblen Client zu verwalten. Diese Tools sind über das einheitliche [Adobe CX Coworker Gateway verfügbar](overview.md) wenn Ihr Konto über die erforderliche Adobe Analytics-Lizenz und -Berechtigungen verfügt.

>[!AVAILABILITY]
>
>Analytics-Tools stehen Kunden mit einer Adobe Analytics-Lizenz zur Verfügung. Der Zugriff wird in Adobe Admin Console durch die Berechtigung **MCP** Zugriff) gesteuert. Weitere Informationen finden Sie [Zugriff auf CX Coworker](access.md)Gateway-Tools“.

## Wichtigste Funktionen {#mcp-capabilities}

Adobe Analytics-Tools unterstützen Analyse-Discovery- und Reporting-Workflows von Ihrem MCP-Client aus. Sie haben folgende Möglichkeiten:

- Erkunden von Report Suites und Überprüfen ihrer Konfiguration
- Suchen Sie Dimensionen, Metriken, berechnete Metriken, Segmente, Datumsbereiche und Workspace-Projekte.
- Führen Sie Rang- und Trendberichte mit Dimensionen, Metriken, Datumsbereichen und Segmentfiltern aus.
- Erstellen und aktualisieren Sie ausgewählte wiederverwendbare Komponenten, z. B. Segmente und Datumsbereiche.
- Generieren Sie mithilfe natürlicher Sprache Insights aus Adobe Analytics-Daten.

>[!IMPORTANT]
>
>Einige Adobe Analytics-Tools können Analytics-Komponenten erstellen oder aktualisieren. Überprüfen und validieren Sie alle von MCP initiierten Änderungen, bevor Sie sich auf sie verlassen.

## Tool-Abdeckung {#mcp-tools}

| Bereich | Mögliche Optionen |
| --- | --- |
| Report Suites | Entdecken Sie die für Ihr Konto verfügbaren Report Suites und überprüfen Sie die Konfigurationsdetails. |
| Komponenten | Suchen und Beschreiben von Dimensionen, Metriken, berechneten Metriken, Segmenten und Datumsbereichen. |
| Berichterstellung | Führen Sie Rang- und Trendberichte mit ausgewählten Dimensionen, Metriken, Datumsbereichen und Segmentfiltern aus. |
| Segmente und Datumsbereiche | Erstellen und aktualisieren Sie wiederverwendbare Segmente und Datumsbereiche, in denen Ihre Produktberechtigungen dies zulassen. |
| Workspace-Projekte | Entdecken und Beschreiben von Analysis Workspace-Projekten. |

Die vollständige, aktuelle Liste der Tools finden Sie in der [Adobe Analytics MCP-Tool-Referenz](https://developer.adobe.com/analytics-mcp/docs/aa/reference){target="_blank"}.

## Beispiel-Prompts {#mcp-use-cases}

| Ziel | Prompt-Beispiel |
| --- | --- |
| Entdecken von Report Suites | „Listen Sie die Report Suites auf, auf die ich zugreifen kann.“ |
| Komponenten suchen | „Suchen Sie Metriken zum Umsatz.“ |
| Bericht ausführen | „Führen Sie einen Rangbericht für Seitenansichten nach Seite für die letzten 7 Tage aus.“ |
| Überprüfen eines Segments | „Beschreiben Sie die `[segment name]` und zeigen Sie mir ihre Definition an.“ |
| Projekte erkunden | „Listen Sie meine Analysis Workspace-Projekte im Zusammenhang mit der Akquise auf.“ |

## Produktkontext und Berechtigungen {#mcp-context}

Ihr Konto muss zu einem Adobe Analytics-Produktprofil gehören, das das Berechtigungselement **MCP-Zugriff** enthält, das von einem System- oder Produktadministrator in Adobe Admin Console gewährt wurde.

Produktberechtigungen sind weiterhin gültig. Ihr Konto muss in der Lage sein, die von Ihnen abgefragten Report Suites, Komponenten, Berichte und Projekte anzuzeigen, und muss über die entsprechenden Produktberechtigungen für Schreibvorgänge wie das Erstellen oder Aktualisieren wiederverwendbarer Komponenten verfügen.

## Weitere Informationen {#mcp-more}

Die vollständige Tool-Referenz und die ersten Schritte finden Sie in der [Adobe Analytics MCP-Dokumentation](https://developer.adobe.com/analytics-mcp/docs/aa/){target="_blank"}.