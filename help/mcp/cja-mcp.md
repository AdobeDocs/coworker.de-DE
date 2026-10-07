---
title: Customer Journey Analytics-Tools in CX Coworker Gateway
description: Erfahren Sie, welche Adobe Customer Journey Analytics-Tools über Adobe CX Coworker Gateway verfügbar sind.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 4%
---

# Customer Journey Analytics-Tools in Adobe CX Coworker Gateway {#cja-mcp}

Verwenden Sie die Customer Journey Analytics-Produkt-Tools, um Datenansichten zu untersuchen, Dimensionen und Metriken zu ermitteln, Berichte auszuführen und ausgewählte Analytics-Komponenten über einen MCP-kompatiblen Client zu verwalten. Diese Tools sind über das [CX Coworker-Gateway verfügbar](overview.md) wenn Ihr Konto über die erforderliche Customer Journey Analytics-Lizenz und -Berechtigungen verfügt.

>[!AVAILABILITY]
>
>Customer Journey Analytics-Tools stehen Kunden mit einer Customer Journey Analytics-Lizenz zur Verfügung. Der Zugriff wird in Adobe Admin Console durch die Berechtigung **MCP** Zugriff) gesteuert. Siehe [Zugriff auf CX Coworker Gateway-Tools](access.md).

## Wichtigste Funktionen {#mcp-capabilities}

Customer Journey Analytics-Tools unterstützen gesteuerte Analytics-Workflows von Ihrem MCP-Client aus. Sie haben folgende Möglichkeiten:

* Entdecken Sie Datenansichten und überprüfen Sie, wie sie konfiguriert sind.
* Suchen Sie Dimensionen, Metriken, berechnete Metriken, Segmente, Datumsbereiche, Zielgruppen und Projekte.
* Führen Sie Rang- und Trendberichte mit Dimensionen, Metriken, Datumsbereichen und Segmentfiltern aus.
* Überprüfen Sie die Komponentendefinitionen und die Komponentennutzung.
* Erstellen oder aktualisieren Sie ausgewählte Analytics-Komponenten und Workspace-Projekte.

>[!IMPORTANT]
>
>Im Gegensatz zu den schreibgeschützten [Real-Time CDP](rtcdp-mcp.md)-, [Experience Platform](aep-mcp.md)- und [Journey Optimizer](ajo-mcp.md)-Tools umfassen Customer Journey Analytics-Tools Schreibvorgänge. Sie können Segmente, berechnete Metriken, Datumsbereiche, Projekte und Zielgruppen erstellen und aktualisieren. Überprüfen und validieren Sie alle von MCP initiierten Änderungen, bevor Sie sich auf sie verlassen.

## Verfügbare Tools {#mcp-tools}

| Bereich | Tool | Beschreibung |
| --- | --- | --- |
| Einrichtung und Handbücher | `describeCja` | Gibt Referenzhandbücher für Tools, Dimensionen, Metriken, Segmente, berechnete Metriken und Projektstrukturen zurück. |
| Einrichtung und Handbücher | `setDefaultSessionDataViewId` | Konfiguriert die standardmäßige Datenansicht auf Sitzungsebene für nachfolgende Tool-Aufrufe. |
| Entdeckung | `findDimensions` | Findet verfügbare Dimensionen mit Unterstützung für die semantische Suche. |
| Entdeckung | `findMetrics` | Ermittelt standardmäßige und benutzerdefinierte Metriken, ausschließlich berechneter Metriken. |
| Entdeckung | `findCalculatedMetrics` | Durchsucht von Benutzern erstellte und freigegebene berechnete Metriken. |
| Entdeckung | `findSegments` | Listet Segmente auf, auf die der aktuelle Benutzer zugreifen kann. |
| Entdeckung | `findDateRanges` | Ruft gespeicherte Datumsbereichskomponenten ab. |
| Entdeckung | `findDataViews` | Ermittelt verfügbare Datenansichten. |
| Entdeckung | `findProjects` | Sucht Workspace-Projekte. |
| Entdeckung | `findAudiences` | Listet verfügbare Zielgruppenkomponenten auf. |
| Reporting und Analysen | `runReport` | Führt Rangberichte mit Dimensionen, Metriken, Datumsbereichen und optionalen Segmentfiltern aus. |
| Reporting und Analysen | `searchDimensionItems` | Ruft die für Aufschlüsselungsberichte erforderlichen Dimensionswerte ab. |
| Komponentendetails | `describeDimension` | Zeigt detaillierte Metadaten für eine bestimmte Dimension an. |
| Komponentendetails | `describeMetric` | Gibt Metrikmetadaten und Messdetails zurück. |
| Komponentendetails | `describeSegment` | Zeigt Informationen zur Definition und Kompatibilität eines Segments an. |
| Komponentendetails | `describeCalculatedMetric` | Zeigt die verwendete Formel und die verwendeten Basismetriken. |
| Komponentendetails | `describeProject` | Beschreibt die Konfiguration eines Workspace-Projekts. |
| Komponentendetails | `describeAudience` | Gibt Zielgruppen-Metadaten und den Veröffentlichungsstatus zurück. |
| Komponentennutzung | `listComponentUsage` | Sortiert Komponenten nach Nutzungsfrequenz. |
| Komponentennutzung | `listFrequentlyUsedWith` | kennzeichnet Komponenten, die häufig miteinander gepaart sind. |
| Komponentennutzung | `listSimilarTo` | Findet alternative Komponenten für ähnliche Zwecke. |
| Erstellen und aktualisieren | `upsertSegment` | Erstellt ein neues Segment oder ändert ein vorhandenes. |
| Erstellen und aktualisieren | `upsertCalculatedMetric` | Erstellt eine neue berechnete Metrik oder ändert eine vorhandene. |
| Erstellen und aktualisieren | `createDateRange` | Erstellt eine wiederverwendbare Datumsbereichskomponente. |
| Erstellen und aktualisieren | `upsertProject` | Erstellt ein neues Workspace-Projekt oder ändert ein vorhandenes. |
| Erstellen und aktualisieren | `upsertAudience` | Erstellt eine neue Zielgruppendefinition oder ändert eine vorhandene. |

## Beispiel-Prompts {#mcp-use-cases}

| Ziel | Prompt-Beispiel |
| --- | --- |
| Auflisten von Datenansichten | „Listen Sie die Datenansichten auf, die mir in Customer Journey Analytics zur Verfügung stehen.“ |
| Entdecken von Komponenten | „Ermitteln Sie Metriken zum Umsatz in der `[data view name]`.“ |
| Bericht ausführen | „Trendbericht der Bestellungen nach Monat für das letzte Quartal ausführen.“ |
| Metrik aufschlüsseln | „Zeigen Sie mir die 10 beliebtesten Marketing-Kanäle nach Besuchen, aufgeschlüsselt nach Gerätetyp.“ |
| Überprüfen einer Komponente | „Beschreiben Sie die `[segment name]` und zeigen Sie mir ihre Definition an.“ |
| Audit-Nutzung | „Welche Dimensionen werden in meinen Projekten am häufigsten verwendet?“ |
| Erstellen eines Segments | „Erstellen Sie ein Segment für Benutzer, die die Preisseite in den letzten 30 Tagen aufgerufen haben.“ |

## Produktkontext und Berechtigungen {#mcp-context}

Ihr Konto muss zu einem Customer Journey Analytics-Produktprofil gehören, das das Berechtigungselement **MCP-Zugriff** enthält, das von einem System- oder Produktadministrator in Adobe Admin Console gewährt wurde.

Produktberechtigungen sind weiterhin gültig. Ihr Konto muss in der Lage sein, die von Ihnen abgefragten Datenansichten, Komponenten, Projekte und Zielgruppen anzuzeigen, und muss über die entsprechenden Produktberechtigungen für Schreibvorgänge wie das Erstellen oder Aktualisieren von Segmenten, berechneten Metriken, Datumsbereichen, Projekten oder Zielgruppen verfügen.

## In Aktion ansehen {#mcp-videos}

**Übersicht**

>[!VIDEO](https://video.tv.adobe.com/v/3486313/?learn=on&enablevpops)

**In Aktion**

>[!VIDEO](https://video.tv.adobe.com/v/3486314/?learn=on&enablevpops)

## Weitere Informationen {#mcp-more}

Die vollständige Tool-Referenz und die ersten Schritte finden Sie in der [Customer Journey Analytics MCP-Dokumentation](https://developer.adobe.com/analytics-mcp/docs/cja/){target="_blank"}.