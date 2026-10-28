---
title: Vergleichen von Zielgruppen und Kundensegmenten mit dem Coworker Chat
description: Verwenden Sie den Coworker Chat, um Kundengruppen zu vergleichen, übersehene Wachstumsmöglichkeiten zu finden, Zielgruppentrends zu verfolgen und Erkenntnisse in Zielgruppen zu verwandeln, die Sie erstellen können.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 312450e09d9252f17cb2b5d471ee33e1a22b9a05
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 2%
---

# Übersicht über die Zielgruppen- und Segmentanalyse

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions. -->

Verwenden Sie den Adobe CX Enterprise Coworker-Chat , um zu verstehen, welche Kundengruppen sich anders verhalten und wie, damit Sie sich auf die wichtigsten konzentrieren können. Vergleichen Sie Kanäle, Zeiträume und Segmente nebeneinander, verfolgen Sie, wie sich Zielgruppen im Laufe der Zeit ändern, und wandeln Sie Ihre Ergebnisse in eine Zielgruppe um, die Sie erstellen können.

Die Zielgruppen- und Segmentanalyse ist eine von mehreren Analyse-Domains im Coworker Chat. Um alle Domains anzuzeigen, lesen Sie [Analysieren im Kollegen-Chat beginnen](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) unter Analysieren von Daten mit dem Kollegen-Chat.

**Am besten geeignet für:** Analyst, Business-Anwender

## Voraussetzungen

<!-- FLAG: Confidence: High for the shared bullets (sourced from the Skills and limitations table and analytics-chat.md). Medium for the "Additional prerequisite" notes on the operational trends rows in the Use cases table: workflows.md lists the operational time-series skill as available for "All Eligible Applications" but doesn't state required permissions. Mapping Track audience size trends to the same requirement is inferred. Low for the "Additional prerequisite" note on the Take an insight into an audience row: inferred from the Audiences section of workflows.md, which lists Real-Time CDP as the application for audience creation. Confirm with the PM. -->

Um die Anwendungsfälle auf dieser Seite zu verwenden, benötigen Sie Folgendes:

* Mit dem Coworker Chat wurde eine Verbindung zu Ihren Customer Journey Analytics-Datenansichten oder zu Adobe Analytics Report Suites hergestellt. Siehe [Erste Schritte mit der Datenanalyse mit dem Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).
* Zugriff auf die Datenansichten oder Report Suites anzeigen, die Sie analysieren möchten. Der Coworker Chat übernimmt Ihre Berechtigungen von Customer Journey Analytics oder Adobe Analytics.

## Anwendungsszenarien

| Anwendungsfall | Funktion |
| --- | --- |
| [Leistung vergleichen](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Vergleichen Sie Metriken kanalübergreifend, über Zeiträume hinweg oder segmentübergreifend.<p>**Beispielaufforderung:** „Umsatz nach Kanal und Monat vergleichen“</p><p>Weitere Informationen finden Sie unter [Kenntnisse und Einschränkungen](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |
| [Kundengruppen vergleichen](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Zeigt an, welche Gruppen sich anders verhalten, ohne dass Sie eine Segmentlogik schreiben müssen.<p>**Am besten geeignet für:** Business-Anwender</p><p>**Beispielaufforderungen:**</p><ul><li>„Konvertieren bezahlte Social-Media-Besucher anders als E-Mails?“</li><li>„Neue und wiederkehrende Besucher mit Umsatz vergleichen“</li></ul><p>Weitere Informationen finden Sie unter [Kenntnisse und Einschränkungen](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |
| Übersehene Wachstumschancen suchen | Erkunden Sie Zielgruppen, Journey und Kanäle, um Chancen zu identifizieren, die durch allgemeine Leistungszahlen verdeckt werden können.<p>**Beispielaufforderungen:**</p><ul><li>„Welche Zielgruppen konvertieren überdurchschnittlich gut, erhalten aber wenig Traffic?“</li><li>„Welche Kanäle werden für ihre Konversionsrate nicht ausreichend genutzt?“</li></ul> |
| [Analyse operativer Trends und Ursachen](/help/chat/use-cases/workflows.md#data-insights) | Abfragen historischer Zeitreihendaten für Zielgruppen, Datensätze und Journey und Identifizieren, was eine Änderung verursacht hat.<p>**Am besten geeignet für:** Admin, Analyst</p><p>**Beispielaufforderung:** „Entwicklung der Zielgruppengröße in den letzten 90 Tagen anzeigen“</p><p>**Zusätzliche Voraussetzung:** Zusätzlich zu den [allgemeinen Voraussetzungen](#prerequisites) erfordert dieser Anwendungsfall auch Zugriff auf die Zielgruppen, Datensätze oder Journey, die Sie analysieren möchten.</p><p>Weitere Informationen finden Sie unter [Dateneinblicke](/help/chat/use-cases/workflows.md#data-insights) in Anwendungsfällen für den Coworker Chat.</p> |
| Verfolgen von Trends der Zielgruppengröße | Zeigt Zielgruppen, die wachsen oder schrumpfen, und untersucht die Ursache.<p>**Am besten geeignet für:** Admin, Analyst</p><p>**Beispielaufforderung:** „Welche Zielgruppen sind in diesem Quartal am schnellsten gewachsen?“</p><p>**Zusätzliche Voraussetzung** Neben den [allgemeinen Voraussetzungen](#prerequisites) erfordert dieser Anwendungsfall auch den Zugriff auf die Zielgruppen, die Sie verfolgen möchten.</p> |
| Einbinden einer insight in eine Zielgruppe | Wechselt von einer insight zu einer Zielgruppe, die Sie erstellen können, ohne von vorn zu beginnen.<p>**Beispielaufforderungen:**</p><ul><li>„Diesen Vergleich in Analysis Workspace öffnen“</li><li>„Helfen Sie mir, eine Zielgruppe aus dieser Gruppe aufzubauen“</li></ul><p>**Zusätzliche Voraussetzung:** Für diesen Anwendungsfall sind neben [allgemeinen Voraussetzungen](#prerequisites) auch der Zugriff auf Real-Time Customer Data Platform und die Berechtigung zum Erstellen von Zielgruppen erforderlich.</p> |

## Verwendete Kenntnisse

<!-- FLAG: Confidence: High for Compare performance and Analyze operational trends and causes (skills listed for "Comparative analysis" and "Operational time-series & causal analysis" in workflows.md). Medium for Compare customer groups and Track audience size trends, which are mapped to the same skills based on their descriptions. Low for `audience-creation-flow`: inferred from the Audiences section of workflows.md. No skill is listed for Find overlooked growth opportunities because no source names one. Only `cja`, `aa`, and the root cause analysis skills currently appear in the Skills and limitations table on analytics-overview.md. -->

Der -Mitarbeiter verwendet die folgenden Fähigkeiten für die in diesem Artikel beschriebenen Anwendungsfälle. Eine Liste aller Analytics-Fähigkeiten, einschließlich der erforderlichen Berechtigungen und der nicht abgedeckten Bereiche, finden Sie unter [Fähigkeiten und Einschränkungen](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) in Analysieren von Daten mit dem Coworker Chat.

| Skill | Verwendet für |
| --- | --- |
| `cja`, `aa` | Leistung vergleichen<br>Kundengruppen vergleichen |
| `cja-root-cause-analysis`, `aa-root-cause-analysis` | Leistung vergleichen |
| `operational-stats-causal-analysis` | Analyse operativer Trends und Ursachen<br> Nachverfolgen von Trends der Zielgruppengröße |
| `audience-creation-flow` | Einbinden einer insight in eine Zielgruppe |

## Tipps für bessere Ergebnisse

* Geben Sie die Segmente, Zielgruppen, Kanäle oder Geräte an, die Sie einbeziehen, ausschließen oder vergleichen möchten.
* Referenzieren Sie Segmente und andere Komponenten anhand ihres genauen Namens.
* Benennen Sie die Metrik und den Datumsbereich, mit denen Sie vergleichen möchten, z. B. Umsatz Monat für Monat.
* Fragen Sie nach den beitragenden Dimensionen, wenn Sie wissen möchten, warum sich eine Gruppe anders verhält als eine andere.

## Nächste Schritte

* Einen Überblick über die Datenanalyse mit dem Coworker Chat, einschließlich der anderen Analyse-Domains und Best Practices, finden Sie unter [Analysieren von Daten mit dem Coworker Chat](/help/chat/use-cases/data-insights/analytics-overview.md).
* Informationen zum Erstellen von Zielgruppen direkt im Coworker Chat finden Sie unter [Bewerten der Experience Platform-Gesundheit und Erstellen von Zielgruppen in natürlicher Sprache mit Coworker](/help/chat/use-cases/audiences/create-audience-from-natural-language.md).
