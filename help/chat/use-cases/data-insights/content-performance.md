---
title: Analysieren von Inhalten und der Creative-Leistung mit dem Coworker Chat
description: Verwenden Sie den Coworker Chat, um herauszufinden, welche Inhalte die Gewinner gemeinsam haben, weisen Sie den Bildern, die Kundinnen und Kunden sehen, Umsätze zu und vergleichen Sie kreative Inhalte über verschiedene Kanäle und Zielgruppen hinweg.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 312450e09d9252f17cb2b5d471ee33e1a22b9a05
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 1%
---

# Übersicht über die Inhaltsleistung

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions from the slides. -->

Verwenden Sie den Adobe CX Enterprise Coworker-Chat, um zu verstehen, welche Inhalte warum gewinnen und bis hin zu den Attributen der einzelnen Assets, damit Sie in das investieren können, was funktioniert. Gehen Sie darüber hinaus, welche Dateien Klicks erhalten haben, um zu sehen, welche Bilder, Messaging und Designs die Interaktion und den Umsatz über Kanäle und Zielgruppen hinweg steigern.

Die Inhaltsleistung ist eine von mehreren Analyse-Domains im Coworker Chat. Um alle Domains anzuzeigen, lesen Sie [Analysieren im Kollegen-Chat beginnen](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) unter Analysieren von Daten mit dem Kollegen-Chat.

**Am besten geeignet für:** Business-Anwender

## Voraussetzungen

<!-- FLAG: Confidence: High for the first two bullets (sourced from analytics-chat.md and the Skills and limitations table). High for the third bullet: attribute-level and asset analysis needs Content Analytics components, which are available only in data views that are configured for Content Analytics (report/report.md in analytics-platform.en). This applies whichever skill runs the analysis. It's a shared bullet rather than a table row because it applies to every use case on this page. The SME confirmed (October 2026) that the skill doesn't support paid media yet, so the paid channel use case was rewritten for web and mobile. Support is planned, either in this skill or in a separate add-on skill (not decided). When it ships, consider restoring paid channels to that row with an "Additional prerequisite" note: paid media needs the Paid Media channel enabled in Content Analytics through an Experience Platform paid media source connector, such as Meta Ads or Google Ads, and comparing paid creative with on-site revenue needs custom tracking-key mapping (config/paid-media.md in analytics-platform.en). -->

Um die Anwendungsfälle auf dieser Seite zu verwenden, benötigen Sie Folgendes:

* Mit dem Coworker Chat wurde eine Verbindung zu Ihren Customer Journey Analytics-Datenansichten oder zu Adobe Analytics Report Suites hergestellt. Siehe [Erste Schritte mit der Datenanalyse mit dem Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).
* Zugriff auf die Datenansichten oder Report Suites anzeigen, die Sie analysieren möchten. Der Coworker Chat übernimmt Ihre Berechtigungen von Customer Journey Analytics oder Adobe Analytics.
* Eine Datenansicht, die für Content Analytics konfiguriert ist. Siehe [Konfigurieren von Content Analytics](https://experienceleague.adobe.com/de/docs/analytics-platform/using/content-analytics/configuration/configuration) im Customer Journey Analytics-Handbuch.

## Anwendungsszenarien

| Anwendungsfall | Funktion |
| --- | --- |
| Finden Sie heraus, was die erfolgreichsten Inhalte gemeinsam haben<p>![Finden Sie heraus, was die erfolgreichsten Inhalte gemeinsam haben](assets/content-performance.png)</p> | Zeigt an, welche Bilder und Nachrichten auf Attributebene funktionieren und nicht nur, welche Dateien Klicks erhalten haben.<p>**Beispielaufforderungen:**</p><ul><li>„Was haben unsere Bilder mit der besten Leistung gemeinsam?“</li><li>„Welche Inhaltsattribute fördern die meiste Interaktion?“</li></ul> |
| Weisen Sie den Umsatz den Inhalten zu, die Kunden sehen | Verknüpft die Bildexponierung mit Umsatz, Konversionen und Interaktion mit algorithmischer Attribution.<p>**Am besten geeignet für:** Analyst, Business-Anwender</p><p>**Beispielaufforderungen:**</p><ul><li>„Welche Bilder haben im letzten Quartal den höchsten Umsatz erzielt?“</li><li>„Wie viel Umsatz ist an das Bild unter https://www.example.com/images/spring-sale.jpg gebunden?“</li></ul> |
| Vergleichen von kreativen Inhalten im Web und auf Mobilgeräten | Zeigt an, welche Visualisierungen und Designs auf Ihrer Site und in Ihrer Mobile App in einer Ansicht gewonnen werden.<p>**Beispielaufforderungen:**</p><ul><li>„Welche kreativen Themen gewinnen in unserer mobilen App und auf unserer Website?“</li><li>„Vergleichen Sie die Bildleistung in unserer Mobile App und auf unserer Website“</li></ul> |
| Ermitteln, welche Visualisierungen die einzelnen Zielgruppen bewegen | Zeigt an, welche Visualisierungen für jede Zielgruppe funktionieren, um Personalisierungs- und Kreativ-Briefs anzuleiten.<p>**Beispielaufforderungen:**</p><ul><li>„Welche Visualisierungen funktionieren am besten für jedes Segment?“</li><li>„Welche Bilder funktionieren für Erstbesucher?“</li></ul> |

## Verwendete Kenntnisse

<!-- FLAG: Confidence: Medium. The `analyze-content` skill is a foundational skill for content questions, so it's listed for every use case on this page. Confirm with the PM that it covers all four. -->

Der -Mitarbeiter verwendet die folgenden Fähigkeiten für die in diesem Artikel beschriebenen Anwendungsfälle. Eine Liste aller Analytics-Fähigkeiten, einschließlich der erforderlichen Berechtigungen und der nicht abgedeckten Bereiche, finden Sie unter [Fähigkeiten und Einschränkungen](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) in Analysieren von Daten mit dem Coworker Chat.

| Skill | Verwendet für |
| --- | --- |
| `cja`,`analyze-content` <br/> (begrenzte Verfügbarkeit) | Finden Sie heraus, was die erfolgreichsten Inhalte gemeinsam haben<br> weisen Sie den Inhalten, die Kunden sehen, <br> Sie Kreative im Web und auf Mobilgeräten <br>Erfahren Sie, welche Visualisierungen die einzelnen Zielgruppen bewegen<p>Weitere Informationen finden Sie unter [Fragen zu Ihrem Inhalt stellen](/help/chat/use-cases/data-insights/ask-content-questions.md).</p> |

## Tipps für bessere Ergebnisse

<!-- FLAG: Confidence: High for the first bullet (SME feedback, October 2026). Medium for the rest: the second and third bullets are adapted from the best practices in analytics-overview.md, and the fourth bullet is inferred from the row descriptions. -->

* Wenn Sie nach einem bestimmten Bild fragen, geben Sie dessen URL oder Asset-ID an. Ein Kollege kann ein Bild nicht anhand seiner Rolle auf der Seite identifizieren, z. B. anhand eines Hero-Bildes oder eines Banners.
* Benennen Sie die Metrik und den Datumsbereich, den Sie analysieren möchten, z. B. den Umsatz im letzten Quartal.
* Geben Sie die Segmente, Zielgruppen oder Kanäle an, die Sie vergleichen möchten.
* Fragen Sie nach Inhaltsattributen wie Bildern, Designs oder Nachrichten und nicht nach einzelnen Dateien, wenn Sie wissen möchten, warum Inhalte gut funktionieren.

## Nächste Schritte

* Informationen dazu, wie ein Mitarbeiter Inhaltsfragen beantwortet, finden Sie unter [Fragen zu Ihrem Inhalt stellen](/help/chat/use-cases/data-insights/ask-content-questions.md) (Eingeschränkte Verfügbarkeit).
* Einen Überblick über die Datenanalyse mit dem Coworker Chat, einschließlich der anderen Analyse-Domains und Best Practices, finden Sie unter [Analysieren von Daten mit dem Coworker Chat](/help/chat/use-cases/data-insights/analytics-overview.md).
* Informationen zum Einrichten von Coworker Chat und zum Durchführen eines Arbeitsbeispiels finden Sie unter [Erste Schritte mit der Analyse von Daten mit Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).
