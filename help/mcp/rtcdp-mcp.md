---
title: Real-Time CDP-Tools in CX Coworker Gateway
description: Erfahren Sie, wie Sie Adobe Real-Time CDP mithilfe des MCP-Servers mit MCP-Clients verbinden.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 4%
---
# Real-Time CDP-Tools in CX Coworker Gateway {#rtcdp-mcp}

Sie können die Real-Time CDP MCP-Produkt-Tools verwenden, um Zielgruppen, Ziele, Quellen, Identity-Namespaces und den Aktivierungszustand von einem MCP-kompatiblen Client aus zu überprüfen. Diese Tools sind über das einheitliche [CX Coworker Gateway-Gateway verfügbar](overview.md) wenn Ihr Unternehmen aktiviert ist und Ihr Benutzerkonto über die erforderlichen Real-Time CDP-Berechtigungen verfügt.

>[!AVAILABILITY]
>
>Das Real-Time CDP-Produkt-Tool befindet sich in Beta. Der Zugriff erfolgt nur auf Einladung und erfordert die Aktivierung durch die Adobe-Organisation. Siehe [Zugriff auf CX Coworker Gateway-Tools](access.md).

## Wichtigste Funktionen {#mcp-capabilities}

Real-Time CDP-Tools bieten eine schreibgeschützte Überwachungs- und Triage-Oberfläche. Sie haben folgende Möglichkeiten:

* Audiences auflisten und überprüfen, einschließlich Lebenszyklusstatus, Herkunft und Identity-Namespace.
* Überprüfen Sie die Zielgruppenauswertung und die Exportvorgänge, um die jüngsten Fehler zu identifizieren.
* Überprüfen Sie die konfigurierten Zielkonten, Zielflüsse und den Ausführungsverlauf der Aktivierung.
* Überprüfen Sie Quell-Connectoren, Konten, Flüsse und den Ausführungsverlauf der Aufnahme.
* Auflisten von Identity-Namespaces und Zusammenführungsrichtlinien.

>[!IMPORTANT]
>
>Alle Real-Time CDP-Tools in der aktuellen Beta sind schreibgeschützt. Das Erstellen, Aktualisieren, Aktivieren oder Löschen von Zielgruppen, Zielen, Quellen oder Datenflüssen wird nicht unterstützt.

## Verfügbare Tools {#mcp-tools}

| Bereich | Tool | Beschreibung |
| --- | --- | --- |
| Zielgruppen | `search_audiences` | Audiences auflisten und nach Namen, Entitätstyp, Lebenszyklusstatus, Identity-Namespace oder Herkunft suchen. |
| Zielgruppen | `preview_audience_membership` | Schätzen Sie die Größe eines PQL- oder SDD-Segmentausdrucks, bevor Sie ihn als Zielgruppe speichern. |
| Zielgruppen | `inspect_audience_evaluation_jobs` | Rufen Sie Datensätze zu Segmentauswertungsaufträgen ab, um Probleme bei der Aktualisierung der Zielgruppe zu diagnostizieren oder den jüngsten Auswertungsverlauf zu bestätigen. |
| Zielgruppen | `inspect_audience_export_jobs` | Rufen Sie Audience-Exportauftragsdatensätze ab, um abgeschlossene Exporte oder Details zu Oberflächenfehlern zu bestätigen. |
| Ziele | `search_destination_connectors` | Auflisten der in der Plattform verfügbaren Ziel-Connector-Typen. |
| Ziele | `search_destination_accounts` | Auflisten authentifizierter Zielkonten. |
| Ziele | `search_destination_input_connections` | Rufen Sie die Experience Platform-seitige Eingabe eines Zielflusses ab. |
| Ziele | `search_destination_output_connections` | Rufen Sie den externen Endpunkt eines Zielflusses ab, einschließlich Zielpfad, Dateiformat und Versandkonfiguration. |
| Ziele | `search_destination_flows` | Auflisten und Überprüfen der konfigurierten Zielaktivierungsflüsse, einschließlich Status, Zuordnungen und Zeitplan. |
| Ziele und Quellen | `inspect_flow_runs` | Abrufen des Ausführungsverlaufs des Quell- und Zielflusses, einschließlich Status, Timing, Anzahl der Einträge und Fehlerdetails. |
| Quellen | `search_source_connectors` | Auflisten der in der Plattform verfügbaren Quell-Connector-Typen. |
| Quellen | `search_source_accounts` | Authentifizierte Quellkonten auflisten. |
| Quellen | `search_source_input_connections` | Abrufen, was ein Quellfluss von einem Konto abruft. |
| Quellen | `search_source_output_connections` | Abrufen des Experience Platform-Datensatzziels für einen Quellfluss. |
| Quellen | `search_source_flows` | Auflisten und Überprüfen der konfigurierten Quell-Aufnahme-Pipelines, einschließlich Status, Zuordnungen und Zeitplan. |
| Identität | `search_identity_namespaces` | Auflisten von Identity-Namespace-Definitionen in Ihrer Sandbox. |
| Identität | `search_merge_policies` | Listen Sie Zusammenführungsrichtlinien-Datensätze auf, die steuern, wie Echtzeit-Kundenprofile zusammengestellt werden. |

## Beispiel-Prompts {#mcp-use-cases}

| Ziel | Prompt-Beispiel |
| --- | --- |
| Audiences auflisten | „Listen Sie meine Zielgruppen in der `prod` Sandbox auf.“ |
| Überprüfen einer Zielgruppe | „Zeigen Sie mir die Details und den Lebenszyklusstatus für die Zielgruppen-ID `abc123`.“ |
| Diagnose von Auswertungsproblemen | „Zeigen Sie mir die neuesten Aufträge zur Zielgruppenbewertung und markieren Sie Fehler.“ |
| Exportaufträge überprüfen | „Listen Sie die letzten Audience-Exportaufträge auf und zeigen Sie mir den Status der einzelnen Aufträge an.“ |
| Zielgruppengröße schätzen | „Schätzen Sie die Größe dieses PQL-Ausdrucks, bevor ich ihn speichern: `homeAddress.country = 'US'`.“ |
| Überprüfen der Zieleinrichtung | „Listen Sie meine Zielaktivierungsflüsse auf und zeigen Sie an, welche aktiviert oder deaktiviert sind.“ |
| Untersuchen eines fehlgeschlagenen Aktivierungsdurchgangs | „Anzeigen des Ausführungsverlaufs für Fluss-ID `xyz789` und Zusammenfassung etwaiger Fehler“ |
| Überprüfen der Quellaufnahme | „Aktuelle Ausführungsverläufe für Quellfluss-ID-`src456` und Markierungsfehler anzeigen“ |
| Prüfen der Identitätskonfiguration | „Welche Identity-Namespaces werden in meiner Sandbox konfiguriert?“ |

## Berechtigungen {#mcp-context}

Ihre Adobe-Organisation und Ihr Sandbox-Kontext werden einmal auf der Gateway-Verbindungsebene eingerichtet und gelten für jede Toolfamilie, sodass Sie keine Organisationen oder Sandboxes aus den Real-Time CDP-Tools wechseln. Informationen zum Festlegen dieses Kontexts für eine Sitzung finden Sie [Produktkontext für Tool-Aufrufe](install.md#mcp-connect-params).

Ihr Benutzerkonto muss über die Berechtigung zum Anzeigen der von Ihnen abgefragten Real-Time CDP-Ressourcen verfügen. Das Gateway umgeht keine Produktberechtigungen.

## Bekannte Einschränkungen {#mcp-limitations}

| Einschränkung | Beschreibung | Problemumgehung |
| --- | --- | --- |
| Schreibgeschützte Oberfläche | Real-Time CDP-Tools machen nur APIs zum Abrufen verfügbar. Zielgruppen, Ziele, Quellen oder Datenflüsse können nicht erstellt, aktualisiert, aktiviert oder gelöscht werden. | Verwenden Sie die Real-Time CDP-Benutzeroberfläche oder Experience Platform-APIs für Schreibvorgänge. |
| Keine Interaktions- oder Versandmetriken | Die Tools geben keine nachgelagerten Versandstatistiken, Interaktions- oder Konversionsmetriken von Zielplattformen zurück. | Verwenden Sie die Reporting-Tools der Zielplattform, Customer Journey Analytics-Tools oder Adobe Analytics-Tools für Interaktions- und Konversionsdaten. |
| Segmentabfrage muss extern erstellt werden | `preview_audience_membership` erfordert einen gültigen PQL- oder SDD-Ausdruck. Das Tool erstellt die Abfrage nicht für Sie. | Erstellen Sie den Ausdruck in Segment Builder oder in der Segmentierungs-Service-API und fügen Sie ihn dann in Ihre Eingabeaufforderung ein. |
| Paginierung über Fortsetzungs-Token | Listen-Tools geben paginierte Ergebnisse zurück. Für die vollständige Auflistung über sehr große Sandboxes sind Verkettungs-Fortsetzungstoken erforderlich. | Engen Sie Abfragen mithilfe von Filtern wie Name, Status, Verbindungsspezifikation oder Zeitbereich ein. |
| Die Filterung des Aktivierungsdurchgangs ist nur zeitbasiert | Die Prüfung des Aktivierungsdurchgangs unterstützt das Filtern nach Status und Abschlusszeitstempel, jedoch nicht direkt nach Fehlertyp oder Zielplattform. | Filtern Sie nach `flowId` ersten Umfangsausführungen, die auf einen bestimmten Zielfluss angewendet werden. |

