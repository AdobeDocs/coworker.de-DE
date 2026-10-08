---
title: Journey Optimizer-Tools in CX Coworker Gateway
description: Erfahren Sie, welche Adobe Journey Optimizer-Tools über das CX Coworker-Gateway verfügbar sind.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 6%
---
# Adobe Journey Optimizer-Tools in CX Coworker Gateway {#ajo-mcp}

Verwenden Sie die Adobe Journey Optimizer-Produkt-Tools, um Kampagnen, Journey- und Kanalkonfigurationen von einem MCP-kompatiblen Client aus zu überprüfen. Diese Tools sind über das [CX Coworker-Gateway verfügbar](overview.md) wenn Ihr Unternehmen aktiviert ist und Ihr Benutzerkonto über die erforderlichen Journey Optimizer-Berechtigungen verfügt.

Weitere Informationen finden Sie unter [Arbeiten mit MCP](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/content-management/combine/ajo-mcp){target="_blank"}Clients in der Adobe Journey Optimizer-Dokumentation.

Ein konversatives, agentisches Erlebnis zum Erstellen, Analysieren und Simulieren von Journey finden Sie unter [Journey Agent](https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/agents/ajo-agent).

>[!AVAILABILITY]
>
>Die Journey Optimizer-Produkt-Tools befinden sich in Beta. Der Zugriff erfolgt nur auf Einladung und erfordert die Aktivierung durch die Adobe-Organisation. Siehe [Zugriff auf CX Coworker Gateway-Tools](access.md).

## Wichtigste Funktionen {#mcp-capabilities}

Journey Optimizer-Tools bieten eine schreibgeschützte Oberfläche für die Überprüfung der Kampagnen-, Journey- und Kanalkonfiguration. Sie haben folgende Möglichkeiten:

- Journey Optimizer-Kampagnen auflisten und nach Status filtern.
- Abrufen von Kampagnendetails, einschließlich Zielgruppenbestimmung, Zeitplan, Kanal und Inhaltskonfigurations-Metadaten.
- Listen Sie Journey in Ihrer Sandbox auf und untersuchen Sie sie, einschließlich Verzweigungen, Bedingungen und Aktionen.
- Listen Sie Kanalkonfigurationen für E-Mail-, SMS-, Push- und WhatsApp-Kanäle auf.
- Auflisten der für die Durchsetzung von Data Governance-Richtlinien verfügbaren Marketing-Aktionen
- Überprüfen Sie die Einrichtung von Kampagnen, Journey und Kanälen in natürlicher Sprache, ohne die Bildschirme der Produkte zu navigieren.

>[!IMPORTANT]
>
>Alle Journey Optimizer-Tools in der aktuellen Beta sind schreibgeschützt. Das Erstellen, Aktualisieren, Löschen, Starten, Beenden oder Veröffentlichen von Kampagnen oder Journey wird nicht unterstützt.

## Verfügbare Tools {#mcp-tools}

| Tool | Beschreibung |
| --- | --- |
| `ajo_campaign_list` | Durchsuchen Sie Journey Optimizer Marketing-Kampagnen. Unterstützt das Filtern nach Status wie `DRAFT`, `LIVE`, `STOPPED` und `COMPLETED`. |
| `ajo_campaign_get` | Abrufen von Details und Konfiguration für eine bestimmte Kampagne nach ID, einschließlich Zielgruppen-Targeting, Zeitplan, Kanal- und Inhaltseinstellungen und Metadaten. |
| `ajo_journey_list` | Durchsuchen Sie alle Journey in Ihrer Journey Optimizer-Sandbox. |
| `ajo_journey_get` | Rufen Sie alle Details für eine bestimmte Journey nach ID ab, einschließlich Verzweigungen, Bedingungen und Aktionen. |
| Journey-Visualisierung | Rendering einer Journey-Struktur und eines Flusses für interaktive, visuelle Exploration. |
| `ajo_channel_configuration_list`, `ajo_channel_configuration_get` | Anzeigen von Oberflächenvorgaben und Branding-Einstellungen für E-Mail-, SMS-, Push- oder [!DNL WhatsApp]. |
| `ajo_channel_configuration_resource_list`, `ajo_channel_configuration_resource_get` | Auflisten und Abrufen unterstützender Konfigurationsressourcen, auf die von Kanalkonfigurationen verwiesen wird, z. B. Push-Anmeldeinformationen, E-Mail-Subdomains, IP-Pools, SMS-Anmeldeinformationen und [!DNL WhatsApp]. |
| `ajo_marketing_action_list` | Listen Sie verfügbare Marketing-Aktionen zur Durchsetzung von Data-Governance-Richtlinien auf. |

## Beispiel-Prompts {#mcp-use-cases}

| Ziel | Prompt-Beispiel |
| --- | --- |
| Kampagnenüberblick | „Alle meine Journey Optimizer-Kampagnen anzeigen.“ |
| Statusprüfung | „Welche Kampagnen sind derzeit aktiv?“ |
| Kampagnendetails | „Vollständige Details zu Campaign `[campaign ID]`.“ |
| Journey-Überblick | „Zeig mir all meine Journey Optimizer Journey.“ |
| Journey-Details | „Erhalten Sie alle Details zu Journey `[journey ID]`, einschließlich Verzweigung und Bedingungen.“ |
| Zielgruppe und Zielgruppenbestimmung | „Welche Zielgruppe wird in Campaign `[campaign ID]` angesprochen?“ |
| Zeitplan und Zeitplan | „Wann soll Campaign `[campaign ID]` ausgeführt werden?“ |
| Fehlerbehebung | „Überprüfen Sie die Einrichtung von Campaign `[campaign ID]` und markieren Sie mögliche Probleme.“ |
| Kanalkonfiguration | „Welche E-Mail-Kanal-Konfigurationen sind verfügbar?“ |
| Kanalprüfung | „Welche Kanalkonfigurationen fehlen oder sind unvollständig?“ |
| Governance | „Welche Marketing-Aktionen sind in meiner Sandbox verfügbar?“ |

## Content-Management-Tools {#mcp-content-management}

Zusätzlich zu den oben genannten schreibgeschützten Produkt-Tools können Journey Optimizer-Benutzende Inhaltselemente - Inhaltsvorlagen, Fragmente, Landingpages und Inline-Nachrichteninhalte von Journey- oder Kampagnen - direkt von CX Coworker aus über natürliche Sprachaufforderungen ermitteln und verwalten. Diese Funktion basiert auf einem separaten Satz von Lese- und Schreib-fähigen MCP-Tools für Journey Optimizer-Inhalte und steht allen Kunden zur Verfügung, die Zugriff auf CX Coworker haben.

Weitere Informationen finden Sie unter [Content-Management-Tools](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/get-started/essentials/ajo-coworker-skills#content-management){target="_blank"} in der Dokumentation zu Adobe Journey Optimizer.

Content-Management-Tools ermöglichen Ihnen Folgendes:

- Durchsuchen Sie Inhaltsvorlagen, Fragmente und Landingpages und rufen Sie deren Struktur, Metadaten und Status ab.
- Rufen Sie den Inline-Nachrichteninhalt ab, der auf einem Journey- oder Kampagnenaktionsknoten konfiguriert ist.
- Erstellen und aktualisieren Sie Inhaltsvorlagen für jeden Kanal.
- Erstellen, aktualisieren, klonen und veröffentlichen Sie Fragmente.
- Ersetzen Sie eine Kanalvariante in der Inline-Nachricht eines Journey- oder Kampagnenaktionsknotens.

>[!IMPORTANT]
>
>Im Gegensatz zu den oben genannten schreibgeschützten Produkttools unterstützen Content-Management-Tools Schreibvorgänge. Die Volltextsuche über Vorlagen oder Fragmente hinweg, die Validierung von Vorlagen oder Fragmenten, das Erstellen oder Veröffentlichen von Landingpages und das Löschen von Inhaltsvorlagen, Fragmenten oder Landingpages werden nicht unterstützt.

## Produktkontext und Berechtigungen {#mcp-context}

Ihr Benutzerkonto muss über die Berechtigung zum Anzeigen der von Ihnen abgefragten Journey Optimizer-Kampagnen, Journey- und Kanalkonfigurationen verfügen. Der MCP umgeht keine Produktberechtigungen.

Wenn Ihr Unternehmen mehrere Sandboxes verwendet, geben Sie die Sandbox oder den Umgebungskontext in der Eingabeaufforderung an, wenn Sie Ergebnisse aus einer bestimmten Sandbox benötigen.

## Bekannte Einschränkungen {#mcp-limitations}

| Einschränkung | Beschreibung | Problemumgehung |
| --- | --- | --- |
| Schreibgeschützte Oberfläche | Journey Optimizer-Tools machen nur Abrufvorgänge verfügbar. Sie können keine Kampagnen oder Journey erstellen, aktualisieren, löschen, starten, stoppen oder veröffentlichen. | Verwenden Sie die Journey Optimizer-Benutzeroberfläche oder APIs für Schreibvorgänge. |
| Keine Interaktion oder Leistungsmetriken | Tools geben keine Berichtsdaten wie Impressionen, Clickthrough-Raten, Konversionen oder Versandstatistiken zurück. | Verwenden Sie Journey Optimizer-Reporting, Customer Journey Analytics-Tools oder Adobe Analytics-Tools für Leistungsmetriken. |
| Die Paginierung der Kampagnenliste ist begrenzt | Die Kampagnenauflistung gibt die erste Ergebnisseite mit bis zu 50 alphabetisch sortierten Kampagnen zurück. Versatz- und Grenzwerte werden nicht angewendet. | Wenn die Kampagnen-ID bekannt ist, können Sie `Get Campaign` direkt verwenden. Verwenden Sie die Journey Optimizer-Benutzeroberfläche für das vollständige Durchsuchen und Filtern. |
| Keine Server-seitige Filterung nach Datum, Kanal oder Zeitplan | Die Kampagnenauflistung unterstützt die Statusfilterung, jedoch nicht die Filterung von Veröffentlichungsdatum, Zeitplandatum, Kanal oder Kampagnentyp. | Verwenden Sie die Kampagnenliste der Journey Optimizer-Benutzeroberfläche für die native Datums- und Kanalfilterung. |
| Abruf des Nachrichteninhalts über die Produkt-Tools nicht verfügbar | Nachrichten-HTML, Betreffzeilen, Personalisierungs-Token und Angebotsinhalte sind nicht über die oben genannten schreibgeschützten Produkt-Tools verfügbar. | Verwenden Sie die [Content-Management](#mcp-content-management)Tools, um Inline-Nachrichteninhalte abzurufen und zu aktualisieren oder direkt in der Journey Optimizer-Benutzeroberfläche anzuzeigen. |