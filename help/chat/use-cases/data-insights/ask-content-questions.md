---
title: Stellen Sie mit dem Coworker Chat Fragen zu Ihrem Inhalt
description: Fragen Sie Mitarbeiter-Chat zu Ihren Inhalten in einfacher Sprache, von allgemein bis spezifisch, und erhalten Sie genaue Content Analytics-Antworten ohne das Fachwissen von Analysten.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 312450e09d9252f17cb2b5d471ee33e1a22b9a05
workflow-type: tm+mt
source-wordcount: '1076'
ht-degree: 3%
---

# Stellen Sie Fragen zu Ihrem Inhalt

<!-- FLAG: Confirm with the PM: (1) availability (GA, beta, or experimental) and whether this page needs an AVAILABILITY note or `hide: true` until launch, and (2) any required Coworker entitlement. Content Analytics itself has no separate permission: users get access through data views that are configured for Content Analytics (Access control section of analytics-platform.en/help/content-analytics/config/configuration.md). -->

>[!AVAILABILITY]
>
>Die in diesem Artikel beschriebene Funktion befindet sich in der eingeschränkten Testphase der Veröffentlichung und ist möglicherweise noch nicht in Ihrer Umgebung verfügbar. Dieser Hinweis wird entfernt, wenn die Funktion allgemein verfügbar ist.

Verwenden Sie den Adobe CX Enterprise Coworker-Chat, um von Adobe Content Analytics präzise Antworten auf Ihre Inhalte zu erhalten. Stellen Sie eine spezifische Frage, z. B.: „Welche Bilder haben im letzten Quartal den höchsten Umsatz erzielt?“ oder eine allgemeine Frage, z. B.: „Welche Inhalte sollte ich priorisieren?“. Ein Kollege verwandelt Ihre Frage in eine fundierte Analyse.

Ein Mitarbeiter weiß, wie Content Analytics-Daten strukturiert sind, und wendet die Berichtsregeln an, die ein erfahrener Analyst anwenden würde, sodass Marketing-Experten und andere Geschäftsbenutzer ohne fundiertes Content Analytics-Fachwissen zuverlässige Ergebnisse erhalten.

Weitere Anwendungsfälle für die Content-Performance finden Sie unter [Content-Performance - Übersicht](/help/chat/use-cases/data-insights/content-performance.md).

**Am besten geeignet für:** Business-Anwender, Analyst

## Voraussetzungen

<!-- FLAG: Confidence: High. The first two bullets match the other data insights pages. The third bullet follows the Content Analytics docs in analytics-platform.en: Content Analytics components are available only in data views that are configured for Content Analytics (report/report.md), and there's no separate Content Analytics permission (config/configuration.md). -->

Um Fragen zu Ihrem Inhalt zu stellen, benötigen Sie Folgendes:

* Mit dem Coworker Chat wurde eine Verbindung zu Ihren Customer Journey Analytics-Datenansichten hergestellt. Siehe [Erste Schritte mit der Datenanalyse mit dem Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).
* Zugriff auf die Datenansichten anzeigen, die Sie analysieren möchten. Coworker Chat übernimmt Ihre Berechtigungen von Customer Journey Analytics.
* Eine Datenansicht, die für Content Analytics konfiguriert ist. Siehe [Konfigurieren von Content Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/configuration/configuration) im Customer Journey Analytics-Handbuch.

## Stellen einer Inhaltsfrage

1. Melden Sie sich bei einem Kollegen an.

1. Wählen Sie **[!UICONTROL Neuer Chat]** aus.

1. Stellen Sie im Textfeld eine Frage zu Ihrem Inhalt. Beispiel:

   **Eingabeaufforderung**

   > Welche Art von Inhalten sollte ich priorisieren?

   <!-- FLAG: The skill includes activation words and phrases, but they weren't provided. Confirm with the PM whether customers need to use specific words to trigger the skill, or whether any content question routes to it automatically. If specific words are needed, list them here. -->

   Ein Mitarbeiter verwendet die `analyze-content` Kenntnisse, um Inhaltsfragen zu beantworten.

1. (Bedingt) Wenn Ihre Frage für mehr als eine Interpretation offen ist, beantworten Sie die klärenden Fragen, die ein Mitarbeiter stellt, z. B. welcher Inhaltstyp, welcher Kanal oder welcher Datumsbereich Sie meinen.

1. Überprüfen Sie die Ergebnisse.

1. (Optional) Stellen Sie in derselben Unterhaltung Folgefragen, um das Thema zu vertiefen, oder öffnen Sie eine Visualisierung in Analysis Workspace, um die manuelle Steuerung zu verbessern. Siehe [Öffnen einer Visualisierung in Analysis Workspace](/help/chat/use-cases/data-insights/analytics-chat.md#open-a-visualization-in-analysis-workspace).

## Beispiel-Prompts

Die folgende Tabelle zeigt Beispielaufforderungen für verschiedene Arten von Inhaltsfragen. Verwenden Sie sie als Ausgangspunkt und passen Sie sie an Ihre eigenen Inhalte an.

| Art der Frage | Beispiel-Prompts |
| --- | --- |
| Allgemein oder explorativ | <ul><li>„Welche Art von Inhalten sollte ich priorisieren?“</li><li>„Wie sieht die Performance unserer Inhalte aus?“</li></ul> |
| Attribut-level | <ul><li>„Was haben unsere Bilder mit der besten Leistung gemeinsam?“</li><li>„Welche Inhaltsattribute fördern die meiste Interaktion?“</li></ul> |
| Umsatz und Konversionen | <ul><li>„Welche Bilder haben im letzten Quartal den höchsten Umsatz erzielt?“</li><li>„Wie viel Umsatz ist an das Bild unter https://www.example.com/images/spring-sale.jpg gebunden?“</li></ul> |
| Kanäle und Zielgruppen | <ul><li>„Welche kreativen Themen gewinnen in unserer mobilen App und auf unserer Website?“</li><li>„Welche Bilder funktionieren für Erstbesucher?“</li></ul> |

## Wie ein Mitarbeiter Inhaltsfragen beantwortet

<!-- FLAG: Confidence: High for the list of what the skill includes, metric matching, filtering pages by Experience ID, and choosing an attribution model per question (sourced from the PM's skill description and feature summary). Medium for the remaining details, which combine the skill description with the Content Analytics component reference in the Customer Journey Analytics guide. The skill's specific query defaults, attribution models, and visualization rules weren't provided. Confirm with the PM before adding them. -->

Ein Mitarbeiter beantwortet Inhaltsfragen mit der `analyze-content`-Fähigkeit, die den folgenden Kontext und Leitplanken umfasst. Die Qualifikation verbindet sich mit der `cja` Qualifikation und führt alle Abfragen für Ihre Customer Journey Analytics-Datenansichten über dieselben Customer Journey Analytics-Tools aus.

### Standardeinstellungen für Abfragen und Klärung von Fragen

Wenn Ihre Frage ein Detail auslässt, wendet die Kenntnis einen sinnvollen Standardwert an. Wenn die Fähigkeit nicht sicher ist, was Sie meinen, stellt sie eine klärende Frage, anstatt zu erraten.

### Metrikabgleich für Assets und Erlebnisse

<!-- FLAG: The SME confirmed (October 2026) that the skill doesn't support paid media yet. Support is planned, either in this skill or in a separate add-on skill (not decided). When it ships, add paid media here: paid media content uses separate summary metrics, such as Impressions, Clicks, and Spend with a reporting-level suffix (for example, Clicks | Asset Summary), that can't be combined with event metrics such as Asset Views (config/paid-media.md in analytics-platform.en). -->

Content Analytics verfolgt zwei Inhaltstypen: Assets und Erlebnisse. Jeder hat seine eigenen Metriken. Die Qualifikation verknüpft die Metrik immer mit dem Typ des Inhalts, nach dem Sie fragen.

| Inhaltstyp | Was es ist | Metriken, die die Qualifikation verwendet |
| --- | --- | --- |
| Assets | Ein einzelner Inhalt, z. B. ein Bild | Asset-Ansichten, Asset-Klicks, Asset-Clickthrough-Rate (CTR) |
| Erlebnisse | Ein Container mit Inhalten, die Text und Assets enthalten, auf einer Web-Seite oder in einer Mobile App | Erlebnisansichten, Erlebnis-Klicks, Erlebnis-Clickthrough-Rate (CTR) |

### Content Analytics-Datenarchitektur

Die Fähigkeit versteht, wie Content Analytics-Daten strukturiert sind. Beispiel:

* **Erlebnis-IDs:** Wenn Sie nach einer bestimmten Seite fragen, filtert die Kenntnis nach der Content-Erlebnis-ID, die diese Seite identifiziert.
* **KI-generierte Attribute:** Jedes Asset und Erlebnis wird durch Attribute wie Fotografie, Stil, Farben, Ton und Überzeugungsstrategie beschrieben. Die Fähigkeit verwendet diese Attribute, um zu erklären, warum Inhalte gut funktionieren, und nicht nur, welche Inhalte gut abschneiden.

Eine vollständige Liste der Komponenten finden Sie unter [Content Analytics-Komponenten](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/report/components) im Customer Journey Analytics-Handbuch.

### Attribution

Die Qualifikation wählt das Attributionsmodell aus, das zu Ihrer Frage passt. Beispielsweise wird eine Frage über Klicks auf ein Bild anders beantwortet als eine Frage darüber, zu welchem Umsatz dieses Bild beigetragen hat. Weitere Informationen finden Sie unter [Attributionsmodelle](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/attribution/models#attribution-models) im Customer Journey Analytics-Handbuch.

### Allgemeine Analysen und Workflows

Die Qualifikation umfasst Anweisungen für allgemeine Inhaltsanalysen, z. B.:

* Ermitteln der Attribute, die Assets oder Erlebnisse mit den besten Leistungen gemeinsam haben.
* Verknüpfung der Bereitstellung von Inhalten mit Konversionen und Umsatz
* Vergleich von Inhalten über Web- und Mobile-Kanäle hinweg.
* Vergleichen, welche Inhalte für verschiedene Zielgruppen und Segmente funktionieren.
* Identifizieren von zu häufig oder zu wenig genutztem Inhalt.

### Visualisierungen

Die Kompetenz wählt Visualisierungen aus, die zu Ihrer Frage und den Daten passen, damit die Ergebnisse einfach zu lesen und zu teilen sind.

## Tipps für bessere Ergebnisse

* Beginne breit, wenn du nicht sicher bist, was du fragen sollst. Mitarbeiter können eine allgemeine Frage in eine fokussierte Analyse umwandeln und von dort aus verfeinern.
* Sagen Sie, ob Sie einzelne Assets wie Bilder oder ganze Erlebnisse wie Seiten meinen, wenn Sie wissen, welches Sie möchten.
* Wenn Sie nach einem bestimmten Bild fragen, geben Sie dessen URL oder Asset-ID an. Ein Kollege kann ein Bild nicht anhand seiner Rolle auf der Seite identifizieren, z. B. anhand eines Hero-Bildes oder eines Banners.
* Benennen Sie die Metrik und den Datumsbereich, den Sie analysieren möchten, z. B. den Umsatz im letzten Quartal.
* Geben Sie die Segmente, Zielgruppen oder Kanäle an, die Sie vergleichen möchten.
* Fragen Sie nach Inhaltsattributen wie Bildern, Designs oder Nachrichten und nicht nach einzelnen Dateien, wenn Sie wissen möchten, warum Inhalte gut funktionieren.
* Fügen Sie Ihre bevorzugte Datenansicht zum Arbeitsspeicher hinzu, wenn Sie immer dieselbe analysieren. Siehe [Hinzufügen einer Datenansicht oder Report Suite-Voreinstellung im Speicher](/help/chat/use-cases/data-insights/analytics-chat.md#add-a-data-view-or-report-suite-preference-in-memory).

## Nächste Schritte

* Weitere Anwendungsfälle für die Content-Performance finden Sie unter [Content-Performance - Übersicht](/help/chat/use-cases/data-insights/content-performance.md).
* Weitere Informationen zu Content Analytics finden Sie unter [Übersicht über Content Analytics](https://experienceleague.adobe.com/de/docs/analytics-platform/using/content-analytics/content-analytics) im Customer Journey Analytics-Handbuch.
* Einen Überblick über die Datenanalyse mit dem Coworker Chat, einschließlich Best Practices, finden Sie unter [Analysieren von Daten mit dem Coworker Chat](/help/chat/use-cases/data-insights/analytics-overview.md).
