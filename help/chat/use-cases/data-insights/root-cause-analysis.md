---
title: Analysieren von Grundursachen mit Adobe Analytics und Customer Journey Analytics
description: Verwenden Sie Adobe CX Enterprise Coworker, um Metrikänderungen zu untersuchen, beitragende Dimensionen und Segmente zu identifizieren und Hypothesen in Adobe Analytics und CJA zu testen.
feature: AI Tools
role: User
level: Beginner
doc-type: Feature Video
duration: 186
last-substantial-update: 2026-08-10T00:00:00.000Z
jira: KT-22082
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 7e096fc9cda2157c02501ee909a80bf4df9a2f32
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 0%
---

# Analyse der Grundursachen mit [!DNL Adobe Analytics] und [!DNL Customer Journey Analytics]

Verwenden Sie den Adobe CX Enterprise Coworker-Chat, um zu untersuchen, warum sich eine Metrik in Adobe Analytics oder Customer Journey Analytics (CJA) geändert hat. Coworker analysiert die von Ihnen angegebenen Flächen, die Dimensionen und Segmente beitragen, und hilft Ihnen, Hypothesen mit natürlicher Sprache zu testen.

## Verwenden von Customer Journey Analytics-Daten für die Ursachenanalyse

Das folgende Video zeigt, wie Coworker konversative KI mit Customer Journey Analytics kombiniert. Erfahren Sie, wie Sie Fragen in natürlicher Sprache stellen, Ergebnisse visualisieren, aussagekräftige Trends identifizieren und Faktoren entdecken, die die Leistung fördern, ohne manuelle Abfragen zu erstellen.

>[!VIDEO](https://video.tv.adobe.com/v/3496847/?learn=on&enablevpops)

### Voraussetzungen

Bevor Sie beginnen:

1. **Zugriff auf den Coworker Chat und Customer Journey Analytics verbinden.** Vergewissern Sie sich, dass Ihr Unternehmen die erforderliche Integration konfiguriert hat.
1. **Sie haben Ansichtszugriff auf die CJA-Datenansicht, die Sie analysieren möchten.** Ein Mitarbeiter kann nur die Datenansichten und Komponenten verwenden, die Ihnen zur Verfügung stehen.
1. **Wählen Sie die Datenansicht aus, die die relevante Metrik und Dimensionen enthält.** Wenn Sie auf mehrere Datenansichten zugreifen können, benennen Sie die Ansicht, die Coworker verwenden soll.
1. **Identifizieren Sie die Änderung, die untersucht werden soll.** Geben Sie die Metrik, den Datumsbereich und den Vergleichszeitraum an. Sie können auch Dimensionen, Segmente oder eine Hypothese bereitstellen, um die Analyse zu fokussieren.

### Beispielaufforderungen für Customer Journey Analytics

Ersetzen Sie den in Klammern gesetzten Text durch Komponentennamen und Zeiträume aus Ihrer Datenansicht.

* Warum hat sich in der **[Datenansichtsname]** Datenansicht **[Metrik]** im **[Datumsbereich]** im Vergleich zum **[Vergleichsdatumsbereich]**? Schlüsseln Sie die Änderung nach **[Dimension]** auf und zeigen Sie die Segmente an, die am meisten dazu beigetragen haben.
* Hat **[Datenansicht „Name der]**&quot; **[Dimension oder Segment]** zum Rückgang **[Metrik]** vom **[Datumsbereich A]** zum **[Datumsbereich B]** beigetragen? Vergleichen Sie die Werte für beide Zeiträume und erklären Sie, was sich geändert hat.
* Vergleichen Sie in der **[Datenansichtsname]** Datenansicht **[Metrik]** für **[Segment A]** und **[Segment B]** während **[Datumsbereich]**. Welche Dimensionen haben am meisten zu dem Unterschied beigetragen?
* Testen Sie in **[Datenansicht „Name der]**&quot; diese Hypothese: **[Geben Sie Ihre Hypothese an]**. Analysieren Sie **[Metrik]** für **[Datumsbereich]** und zeigen Sie die Dimensionen oder Segmente an, die sie unterstützen oder nicht unterstützen.

## Verwenden von Adobe Analytics-Daten für die Ursachenanalyse

Ein Mitarbeiter kann untersuchen, warum sich eine Metrik in einer Adobe Analytics Report Suite geändert hat. Es verwendet die `aa-root-cause-analysis` Fähigkeit, um eine Änderung zu analysieren, die Sie angeben, und um die Dimensionen und Segmente zu identifizieren, die zu ihr beigetragen haben.

### Voraussetzungen

Bevor Sie beginnen:

1. **Zugriff auf den Coworker Chat und Adobe Analytics verbinden.** Navigieren Sie in der **zu „Anpassungen“ > „Integrationen** und vergewissern Sie sich, dass die `aa-mcp`-Integration aufgeführt und verbunden ist. Wenn es nicht verfügbar ist, bitten Sie Ihren Administrator, die Einrichtung Ihres Unternehmens zu überprüfen. Siehe [Erste Schritte mit dem Analysieren von Daten mit dem Coworker Chat](https://experienceleague.adobe.com/en/docs/coworker/content/chat/use-cases/data-insights/analytics-chat) für eine Einrichtungsanleitung.
1. **Sie haben Ansichtszugriff auf die Adobe Analytics Report Suite, die Sie analysieren möchten.** Coworker erbt Ihre Adobe Analytics-Berechtigungen und kann nur die Report Suites und Komponenten verwenden, die Ihnen in Analysis Workspace zur Verfügung stehen.
1. **Wählen Sie die Report Suite aus, die die relevanten Daten enthält.** Wenn Sie auf mehrere Report Suites zugreifen können, benennen Sie die Report Suite, die der Mitarbeiter verwenden soll.
1. **Identifizieren Sie die Änderung, die untersucht werden soll.** Geben Sie die Metrik und den Zeitraum an. Für eine zielgerichtetere Analyse sollten Sie einen Vergleichszeitraum, relevante Dimensionen oder Segmente und jede Hypothese einschließen, die von einem Mitarbeiter getestet werden soll.

### Beispielaufforderungen für Adobe Analytics

Ersetzen Sie den in Klammern eingeschlossenen Text durch Komponentennamen und Zeiträume aus Ihrer Report Suite.

* Warum hat sich in **[Report Suite]** Name **[&quot;]**&quot; während des **[Datumsbereichs]** im Vergleich zum **[Vergleichsdatumsbereich]**? Schlüsseln Sie die Änderung nach **[Dimension]** auf und zeigen Sie die Segmente an, die am meisten dazu beigetragen haben.
* Hat **[Report Suite-]** (Dimension **[Segment)]** zum Rückgang **[Metrik]** vom **[Datumsbereich A]** zum **[Datumsbereich B]** beigetragen? Vergleichen Sie die Werte für beide Zeiträume und erklären Sie, was sich geändert hat.
* Vergleichen Sie in **[Report Suite-]** die Report **[Metrik]** für **[Segment A]** und **[Segment B]** im **[Datumsbereich]**. Welche Dimensionen haben am meisten zu dem Unterschied beigetragen?

## Verwandte Ressourcen

* [Analysieren von Daten mit dem Adobe CX Enterprise Coworker-Chat](https://experienceleague.adobe.com/en/docs/coworker/content/chat/use-cases/data-insights/analytics-overview)
* [Erste Schritte mit der Datenanalyse mit dem Coworker Chat](https://experienceleague.adobe.com/en/docs/coworker/content/chat/use-cases/data-insights/analytics-chat)
