---
title: Marketing-Wirkung und Attribution mit Coworker Chat messen
description: Verwenden Sie den Kollegen-Chat, um die inkrementelle Wirkung jedes Kanals zu messen, um herauszufinden, wo die Ausgaben gesättigt sind, um Was-wäre-wenn-Budget-Szenarien zu erstellen und um die Qualität des Marketing-Modells zu überprüfen.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 5973a87d21b23d7621366108716cbd476e6f66ae
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 2%
---

# Marketing-Messung und Attribution - Übersicht

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions from the slides. -->

Verwenden Sie den Adobe CX Enterprise Coworker-Chat, um die inkrementelle Auswirkung jedes Marketing-Kanals und jeder Kampagne zu verstehen, sodass Sie Ausgaben zuweisen können, um den ROI zu optimieren. Erfahren Sie, wie die Kanäle zusammenarbeiten, wo zusätzliche Ausgaben nicht mehr rentabel sind und wie verschiedene Budgetzuweisungen vor der Mittelbindung aussehen.

Marketing-Messung und -Attribution ist eine von mehreren Analyse-Domains im Coworker Chat. Um alle Domains anzuzeigen, lesen Sie [Analysieren im Kollegen-Chat beginnen](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) unter Analysieren von Daten mit dem Kollegen-Chat.

**Am besten geeignet für:** Analyst, Business-Anwender

## Voraussetzungen

<!-- FLAG: Confidence: High for the shared bullets (sourced from analytics-chat.md and the Skills and limitations table). They're confirmed for Measure campaign performance only; whether the marketing mix modeling use cases also need a data view or report suite connection is unknown. Low for the "Additional prerequisite" notes on the four marketing mix modeling rows in the Use cases table: incremental impact, response curves, budget scenarios, and model retraining describe a marketing mix model, but no source names the product or data that these use cases need. It could be Adobe Mix Modeler or Marketing Campaign Analytics (listed as an implementation path in implementation-guide.md). Confirm with the PM before publishing. -->

Um die Anwendungsfälle auf dieser Seite zu verwenden, benötigen Sie Folgendes:

* Mit dem Coworker Chat wurde eine Verbindung zu Ihren Customer Journey Analytics-Datenansichten oder zu Adobe Analytics Report Suites hergestellt. Siehe [Erste Schritte mit der Datenanalyse mit dem Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).
* Zugriff auf die Datenansichten oder Report Suites anzeigen, die Sie analysieren möchten. Der Coworker Chat übernimmt Ihre Berechtigungen von Customer Journey Analytics oder Adobe Analytics.

## Anwendungsszenarien

| Anwendungsfall | Funktion |
| --- | --- |
| Inkrementelle Auswirkungen der einzelnen Kanäle | Zeigt den inkrementellen Wert jedes Kanals, die gegenseitige Verstärkung der Kanäle und die Rolle externer Faktoren.<p>**Beispielaufforderungen:**</p><ul><li>„Welche Kanäle haben die meisten inkrementellen Konversionen bewirkt?“</li><li>„Wie verstärken sich Paid Search und Display?“</li></ul><p>**Zusätzliche Voraussetzung** Neben den [allgemeinen Voraussetzungen](#prerequisites) erfordert dieser Anwendungsfall auch ein trainiertes Marketing-Messmodell. *[Produkt- und Setup-Anforderungen müssen noch bestätigt werden.]*</p> |
| Finden Sie heraus, wo die Ausgaben zu sättigen beginnen<p>![Finden Sie heraus, wo die Ausgaben zu sättigen beginnen](assets/marketing-measurement.png)</p> | Zeigt Antwortkurven, die zeigen, wo sich zusätzliche Ausgaben nicht mehr auszahlen.<p>**Beispielaufforderungen:**</p><ul><li>„Wo fängt die Sättigung der Ausgaben für bezahlte Suche an?“</li><li>„Antwortkurven für jeden Kanal anzeigen“</li></ul><p>**Zusätzliche Voraussetzung** Neben den [allgemeinen Voraussetzungen](#prerequisites) erfordert dieser Anwendungsfall auch ein trainiertes Marketing-Messmodell. *[Produkt- und Setup-Anforderungen müssen noch bestätigt werden.]*</p> |
| Erstellen von Was-wäre-wenn-Budgetszenarien | Vergleicht Zuordnungsoptionen nebeneinander, um Planungsentscheidungen zu unterstützen.<p>**Am besten geeignet für:** Business-Anwender</p><p>**Beispielaufforderungen:**</p><ul><li>„Budgetszenarien für das nächste Quartal erstellen“</li><li>„Was passiert, wenn ich 10 % der Ausgaben von der Anzeige auf die Suche verlagere?“</li></ul><p>**Zusätzliche Voraussetzung** Neben den [allgemeinen Voraussetzungen](#prerequisites) erfordert dieser Anwendungsfall auch ein trainiertes Marketing-Messmodell. *[Produkt- und Setup-Anforderungen müssen noch bestätigt werden.]*</p> |
| Modellqualität und Zeitpunkt der Umschulung überprüfen | Überprüft Modellqualität, Trainingsdetails und Bewertungsmetriken, damit Sie wissen, wie viel Sie einer Antwort vertrauen können.<p>**Am besten geeignet für:** Analyst</p><p>**Beispielaufforderungen:**</p><ul><li>„Gibt es andere Faktoren, die wir für dieses Modell brauchen?“</li><li>„Muss dieses Modell neu trainiert werden?“</li></ul><p>**Zusätzliche Voraussetzung** Neben den [allgemeinen Voraussetzungen](#prerequisites) erfordert dieser Anwendungsfall auch ein trainiertes Marketing-Messmodell. *[Produkt- und Setup-Anforderungen müssen noch bestätigt werden.]*</p> |
| [Kampagnenleistung messen](/help/chat/use-cases/workflows.md#data-insights) | Sehen Sie, wie Kampagnen, Kanäle und Web-Eigenschaften über einen bestimmten Zeitraum ausgeführt wurden.<p>**Beispielaufforderung:** „Wie haben unsere Acrobat-Web-Kampagnen im letzten Monat funktioniert?“</p><p>Weitere Informationen finden Sie unter [Dateneinblicke](/help/chat/use-cases/workflows.md#data-insights) in Anwendungsfällen für den Coworker Chat.</p> |

## Verwendete Kenntnisse

<!-- FLAG: Confidence: High for Measure campaign performance (workflows.md lists `cja`, `aa`, `dx-api`, and `knowledge-graph` for "Campaign performance"). `dx-api` and `knowledge-graph` aren't in the Skills and limitations table on analytics-overview.md. Low for the other four use cases: no source names their skills. Get the skill IDs from the PM, replace the placeholder row, and add the skills to the Skills and limitations table. -->

Der -Mitarbeiter verwendet die folgenden Fähigkeiten für die in diesem Artikel beschriebenen Anwendungsfälle. Eine Liste aller Analytics-Fähigkeiten, einschließlich der erforderlichen Berechtigungen und der nicht abgedeckten Bereiche, finden Sie unter [Fähigkeiten und Einschränkungen](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) in Analysieren von Daten mit dem Coworker Chat.

| Skill | Verwendet für |
| --- | --- |
| `cja`, `aa`, `dx-api`, `knowledge-graph` | Kampagnenleistung messen |
| *[Kenntnisse müssen noch bestätigt werden]* | Ermitteln der inkrementellen Auswirkungen jedes Kanals<br> Ermitteln, wo die Ausgaben zu sättigen beginnen<br> Erstellen von Was-wäre-wenn-Budgetszenarien<br> Überprüfen der Modellqualität und wann eine Umschulung durchgeführt werden soll |

## Tipps für bessere Ergebnisse

<!-- FLAG: Confidence: Medium. The first two bullets are adapted from the best practices in analytics-overview.md. The third bullet is inferred from the sample prompts. -->

* Benennen Sie die Kanäle, Kampagnen und den Datumsbereich, die Sie analysieren möchten.
* Erwähnen Sie eine Hypothese, die Sie bereits haben, z. B. zwei Kanäle, die zusammenarbeiten, sodass der Coworker Chat sie überprüfen oder ausschließen kann.
* Geben Sie die spezifische Budgetverschiebung an, die Sie beim Erstellen von What-if-Szenarien testen möchten, z. B. das Verschieben von 10 % der Ausgaben von einem Kanal in einen anderen.

## Nächste Schritte

* Einen Überblick über die Datenanalyse mit dem Coworker Chat, einschließlich der anderen Analyse-Domains und Best Practices, finden Sie unter [Analysieren von Daten mit dem Coworker Chat](/help/chat/use-cases/data-insights/analytics-overview.md).
* Informationen zum Einrichten von Coworker Chat und zum Durchführen eines Arbeitsbeispiels finden Sie unter [Erste Schritte mit der Analyse von Daten mit Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).
