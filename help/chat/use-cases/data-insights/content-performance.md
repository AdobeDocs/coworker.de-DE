---
title: Analysieren von Inhalten und der Creative-Leistung mit dem Coworker Chat
description: Verwenden Sie den Coworker Chat, um herauszufinden, welche Inhalte die Gewinner gemeinsam haben, weisen Sie den Bildern, die Kundinnen und Kunden sehen, Umsätze zu und vergleichen Sie kreative Inhalte über verschiedene Kanäle und Zielgruppen hinweg.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: e3d485f7cd1c45bf3fd1217ffcceeccfd4242c7b
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 1%
---

# Übersicht über die Inhaltsleistung

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions from the slides. -->

Verwenden Sie den Adobe CX Enterprise Coworker-Chat, um zu verstehen, welche Inhalte warum gewinnen und bis hin zu den Attributen der einzelnen Assets, damit Sie in das investieren können, was funktioniert. Gehen Sie darüber hinaus, welche Dateien Klicks erhalten haben, um zu sehen, welche Bilder, Messaging und Designs die Interaktion und den Umsatz über Kanäle und Zielgruppen hinweg steigern.

Die Inhaltsleistung ist eine von mehreren Analyse-Domains im Coworker Chat. Um alle Domains anzuzeigen, lesen Sie [Analysieren im Kollegen-Chat beginnen](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) unter Analysieren von Daten mit dem Kollegen-Chat.

**Am besten geeignet für:** Business-Anwender

## Voraussetzungen

<!-- FLAG: Confidence: High for the first two bullets (sourced from analytics-chat.md and the Skills and limitations table). Low for the third bullet: the attribute-level and image exposure descriptions suggest that these use cases rely on Content Analytics data in Customer Journey Analytics, and implementation-guide.md lists Content Analytics as an implementation path, but no source confirms this. It's a shared bullet rather than a table row because it would apply to every use case on this page. The paid channel row ("Compare Meta ad creative to our web banners") may need an additional data source, which would become an "Additional prerequisite" note on that row in the Use cases table. Confirm with the PM. -->

Um die Anwendungsfälle auf dieser Seite zu verwenden, benötigen Sie Folgendes:

* Mit dem Coworker Chat wurde eine Verbindung zu Ihren Customer Journey Analytics-Datenansichten oder zu Adobe Analytics Report Suites hergestellt. Siehe [Erste Schritte mit der Datenanalyse mit dem Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).
* Zugriff auf die Datenansichten oder Report Suites anzeigen, die Sie analysieren möchten. Der Coworker Chat übernimmt Ihre Berechtigungen von Customer Journey Analytics oder Adobe Analytics.
* Content Analytics in Customer Journey Analytics eingerichtet, damit der Coworker Chat Inhaltsattribute und die Belichtung von Bildern analysieren kann. Informationen zum Planen einer Content Analytics-Implementierung finden Sie [Planen der Implementierung mit Coworker](/help/chat/use-cases/data-insights/implementation-guide.md).

## Anwendungsszenarien

| Anwendungsfall | Funktion |
| --- | --- |
| Finden Sie heraus, was die erfolgreichsten Inhalte gemeinsam haben<p>![Finden Sie heraus, was die erfolgreichsten Inhalte gemeinsam haben](assets/content-performance.png)</p> | Zeigt an, welche Bilder und Nachrichten auf Attributebene funktionieren und nicht nur, welche Dateien Klicks erhalten haben.<p>**Beispielaufforderungen:**</p><ul><li>„Was haben unsere Bilder mit der besten Leistung gemeinsam?“</li><li>„Welche Inhaltsattribute fördern die meiste Interaktion?“</li></ul> |
| Weisen Sie den Umsatz den Inhalten zu, die Kunden sehen | Verknüpft die Bildexponierung mit Umsatz, Konversionen und Interaktion mit algorithmischer Attribution.<p>**Am besten geeignet für:** Analyst, Business-Anwender</p><p>**Beispielaufforderungen:**</p><ul><li>„Welche Hero-Bilder haben im letzten Quartal den höchsten Umsatz erzielt?“</li><li>„Wie viel Umsatz ist mit diesem Banner verbunden?“</li></ul> |
| Kreative Inhalte über bezahlte und eigene Kanäle vergleichen | Zeigt an, welche Visualisierungen und Designs über Web-, Mobile- und Paid-Kanäle hinweg in einer Ansicht gewonnen werden.<p>**Beispielaufforderungen:**</p><ul><li>„Welche kreativen Themen gewinnen in Paid und auf unserer Website?“</li><li>„Vergleichen Sie Meta und Creative mit unseren Webbannern“</li></ul> |
| Ermitteln, welche Visualisierungen die einzelnen Zielgruppen bewegen | Zeigt an, welche Visualisierungen für jede Zielgruppe funktionieren, um Personalisierungs- und Kreativ-Briefs anzuleiten.<p>**Beispielaufforderungen:**</p><ul><li>„Welche Visualisierungen funktionieren am besten für jedes Segment?“</li><li>„Welche Bilder funktionieren für Erstbesucher?“</li></ul> |

<!--
HIDDEN until the skills are confirmed. To publish, remove this comment wrapper.

## Skills used

FLAG: Confidence: Low. No source in the repo (workflows.md, the Skills and limitations table, or any data insights article) names the skills behind these use cases. Get the skill IDs from the PM, replace the placeholder rows, and add the skills to the Skills and limitations table on analytics-overview.md so that the link above the table covers them. When you unhide this section, wrap this FLAG note in its own HTML comment.

Coworker uses the following skills for the use cases described in this article. For a list of all analytics skills, including the permissions they require and what they don't cover, see [Skills and limitations](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) in Analyze data with Coworker Chat.

| Skill | Used for |
| --- | --- |
| *[Skill to be confirmed]* | Find what winning content has in common<br>Attribute revenue to the content customers see<br>Compare creative across paid and owned channels<br>Know which visuals move each audience |

-->

## Tipps für bessere Ergebnisse

<!-- FLAG: Confidence: Medium. The first two bullets are adapted from the best practices in analytics-overview.md. The third bullet is inferred from the row descriptions. -->

* Benennen Sie die Metrik und den Datumsbereich, den Sie analysieren möchten, z. B. den Umsatz im letzten Quartal.
* Geben Sie die Segmente, Zielgruppen oder Kanäle an, die Sie vergleichen möchten.
* Fragen Sie nach Inhaltsattributen wie Bildern, Designs oder Nachrichten und nicht nach einzelnen Dateien, wenn Sie wissen möchten, warum Inhalte gut funktionieren.

## Nächste Schritte

* Einen Überblick über die Datenanalyse mit dem Coworker Chat, einschließlich der anderen Analyse-Domains und Best Practices, finden Sie unter [Analysieren von Daten mit dem Coworker Chat](/help/chat/use-cases/data-insights/analytics-overview.md).
* Informationen zum Einrichten von Coworker Chat und zum Durchführen eines Arbeitsbeispiels finden Sie unter [Erste Schritte mit der Analyse von Daten mit Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).
