---
title: Analyse der Kunden-Journey und Abbruch mit Coworker Chat
description: Verwenden Sie den Coworker Chat, um Trichter zu erstellen, herauszufinden, wo Kunden abbrechen, Konversionsrückgänge zu diagnostizieren und Journey über Zeiträume hinweg in Ihren Analytics-Daten zu vergleichen.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: b54085a497ca4bbf0003d5837d816206a4d40396
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 2%
---

# Journey-Analyse - Übersicht

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions from the slides. -->

Verwenden Sie den Adobe CX Enterprise Coworker-Chat, um herauszufinden, wo Kundinnen und Kunden die Journey zur Konvertierung abbrechen und warum, über Kanäle, Geräte und Segmente hinweg. Beschreiben Sie den Journey in verständlicher Sprache, und Coworker Chat erstellt die funnel, zeigt den Abbruch bei jedem Schritt und hilft Ihnen, die Ursache zu untersuchen.

Journey Analysis ist eine von mehreren Analyse-Domains im Coworker Chat. Um alle Domains anzuzeigen, lesen Sie [Analysieren im Kollegen-Chat beginnen](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) unter Analysieren von Daten mit dem Kollegen-Chat.

**Am besten geeignet für:** Analyst, Business-Anwender

## Voraussetzungen

Um die Anwendungsfälle auf dieser Seite zu verwenden, benötigen Sie Folgendes:

* Mit dem Coworker Chat wurde eine Verbindung zu Ihren Customer Journey Analytics-Datenansichten oder zu Adobe Analytics Report Suites hergestellt. Siehe [Erste Schritte mit der Datenanalyse mit dem Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).
* Zugriff auf die Datenansichten oder Report Suites anzeigen, die Sie analysieren möchten. Der Coworker Chat übernimmt Ihre Berechtigungen von Customer Journey Analytics oder Adobe Analytics.

## Anwendungsszenarien

| Anwendungsfall | Funktion |
| --- | --- |
| [Analysieren von Customer Journey Analytics- und Adobe Analytics-Daten](/help/chat/use-cases/data-insights/analytics-chat.md)<p>![Analysieren von Customer Journey Analytics- und Adobe Analytics-Daten](../../assets/coworker-funnel-response-card.png)</p> | Beantwortet Fragen in natürlicher Sprache zu Ihren Datenansichten oder Report Suites, erstellt Trichter und andere Visualisierungen und findet heraus, wo Kunden abbrechen. Sie können eine beliebige Visualisierung in Analysis Workspace zur weiteren Analyse öffnen.<p>**Beispielaufforderung:** „Anzeigen von Seitenansichten für die letzten 30 Tage“</p><p>Weitere Informationen finden Sie unter [Erste Schritte mit der Datenanalyse mit dem Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).</p> |
| [Finden Sie heraus, wo Kunden abbrechen](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Erstellt eine funnel aus einer verständlichen Frage, ordnet die größten Leaks an und schlägt die nächsten Schritte vor.<p>**Am besten geeignet für:** Business-Anwender</p><p>**Beispielaufforderungen:**</p><ul><li>„Wo verlieren wir Menschen auf dem Weg zum Kauf?“</li><li>„Führen Sie mich durch die Kasse funnel&quot;</li></ul><p>Weitere Informationen finden Sie unter [Kenntnisse und Einschränkungen](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |
| Konversionsrückgänge diagnostizieren | Untersucht, wo Kunden die Journey abbrechen, und bewertet, was zu der Änderung beigetragen hat.<p>**Beispielaufforderungen:**</p><ul><li>„Warum sind die Konversionen letzte Woche zurückgegangen?“</li><li>„Wo haben Kunden nach dem Site-Wechsel die Seite verlassen?“</li></ul> |
| Isolieren der Ursache eines Abfalls | Durch „Ausschließen“ werden Kanal, Gerät oder Segment hinter dem Problem einzeln isoliert.<p>**Beispielaufforderungen:**</p><ul><li>„Ist der Warenkorbabbruch auf Mobilgeräten oder Desktop-Computern schlimmer?“</li><li>„Welche Kanäle lecken am meisten zwischen Warenkorb und Kauf?“</li></ul> |
| Journey über Punkte hinweg vergleichen | Zeigt Schritt für Schritt an, ob die von Ihnen versandten Änderungen in die funnel verschoben wurden.<p>**Am besten geeignet für:** Business-Anwender</p><p>**Beispielaufforderungen:**</p><ul><li>„Checkout-Konversionsrate dieses Quartal mit dem letzten vergleichen“</li><li>„Wie hat sich mein funnel nach der Neugestaltung verändert?“</li></ul> |

## Beispiel: Finden Sie heraus, wo Kunden abbrechen

Ein vollständiges Beispielgespräch, von der ersten Frage bis hin zu einer Empfehlung, finden Sie unter [Beispiel: Finden Sie heraus, wo Kundinnen und Kunden abbrechen](/help/chat/use-cases/data-insights/analytics-chat.md#example-find-where-customers-drop-off) in Erste Schritte mit der Analyse von Daten mit dem Coworker Chat.

## Verwendete Kenntnisse

<!-- FLAG: Confidence: High for `cja` and `aa` (the Skills and limitations table lists funnel and fallout analysis and side-by-side comparison of time periods). Medium for the root cause analysis skills: workflows.md maps the prompt "Why did conversions drop last week?" to them, but the mapping to the slide rows "Diagnose conversion declines" and "Isolate the cause of a drop-off" is inferred. Confirm with the PM. -->

Der -Mitarbeiter verwendet die folgenden Fähigkeiten für die in diesem Artikel beschriebenen Anwendungsfälle. Eine Liste aller Analytics-Fähigkeiten, einschließlich der erforderlichen Berechtigungen und der nicht abgedeckten Bereiche, finden Sie unter [Fähigkeiten und Einschränkungen](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) in Analysieren von Daten mit dem Coworker Chat.

| Skill | Verwendet für |
| --- | --- |
| `cja`, `aa` | Analysieren von Customer Journey Analytics- und Adobe Analytics<br>Daten: Finden Sie heraus, wo Kunden abbrechen<br> vergleichen Sie Journey über Zeiträume hinweg. |
| `cja-root-cause-analysis`, `aa-root-cause-analysis` | Konversionsrückgänge diagnostizieren<br>Isolieren Sie die Ursache eines Abfalls |

## Tipps für bessere Ergebnisse

<!-- FLAG: Confidence: High, except the first bullet (Medium), which moved here from Prerequisites and is inferred from how funnel prompts work. The rest are adapted from the best practices in analytics-overview.md. -->

* Benennen Sie die Journey-Schritte, die Sie analysieren möchten, z. B. Produktseite, Warenkorb, Checkout und Kauf.
* Benennen Sie die Dimensionen, Metriken und den Datumsbereich, die Sie analysieren möchten, und referenzieren Sie Komponenten anhand ihres genauen Namens.
* Fragen Sie nach einer funnel- oder Fallout-Visualisierung, wenn Sie dies sehen möchten.
* Geben Sie die Segmente, Kanäle oder Geräte an, die Sie einbeziehen, ausschließen oder vergleichen möchten.
* Erwähnen Sie eine Hypothese, die Sie bereits haben, z. B. eine kürzlich vorgenommene Site-Änderung, sodass der Coworker Chat sie überprüfen oder ausschließen kann.
* Fragen Sie nach den empfohlenen nächsten Schritten, wenn Sie im Coworker Chat weitere Fragen vorschlagen möchten.
* Öffnen Sie eine beliebige Visualisierung in Analysis Workspace, wenn Sie mehr manuelle Kontrolle wünschen. Siehe [Analysieren in Customer Journey Analytics](/help/chat/use-cases/data-insights/analytics-chat.md#analyze-in-customer-journey-analytics).

## Nächste Schritte

* Einen Überblick über die Datenanalyse mit dem Coworker Chat, einschließlich der anderen Analyse-Domains und Best Practices, finden Sie unter [Analysieren von Daten mit dem Coworker Chat](/help/chat/use-cases/data-insights/analytics-overview.md).
* Informationen zum Einrichten von Coworker Chat und zum Durchführen eines Arbeitsbeispiels finden Sie unter [Erste Schritte mit der Analyse von Daten mit Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).
