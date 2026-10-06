---
description: Erfahren Sie, wie Coworker Campaign C2PA-Metadaten automatisch an Bilder anhängt und speichert, von der Generierung bis zum E-Mail-Versand.
title: C2PA-Metadaten in Coworker-Kampagnen
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 27%
---
# C2PA-Metadaten in Coworker-Kampagnen {#overview}

In Bezug auf Transparenz generativer KI entstehen ständig neue Gesetze und Adobe arbeitet daran, die geltenden Anforderungen in allen Gerichtsbarkeiten zu erfüllen. [C2PA-Metadaten](https://c2pa.org/) ist das Herkunftstool, das Adobe verwendet, um die Anforderungen dieser Gesetze zu erfüllen.

C2PA-Metadaten sind dauerhafte, unsichtbare Metadaten, die aufzeichnen, wie ein Inhaltselement erstellt oder bearbeitet wurde. Wenn Sie ein Bild mit Tools für generative KI in Coworker-Kampagnen generieren oder bearbeiten, werden C2PA-Metadaten automatisch an dieses Bild angehängt. Es ist keine Aktion Ihrerseits erforderlich.

## C2PA-Metadaten in E-Mail-Kampagnen {#c2pa-metadate-email}

Bilder, die in Ihren E-Mail-Kampagnen gesendet werden, behalten ihre C2PA-Metadaten intakt, sodass Empfängerinnen und Empfänger die Herkunft und Authentizität eines Bildes direkt aus der zugestellten E-Mail überprüfen können.

## Aktionen, die C2PA-Metadaten anhängen {#actions}

In der folgenden Tabelle wird zusammengefasst, wann C2PA-Metadaten angehängt werden, basierend auf der Bildaktion, die bei der Bildgenerierung in Co-Worker-Kampagnen durchgeführt wurde.

| Aktion | Beschreibung | C2PA-Metadaten angehängt? | Anwendungsbeispiel |
| --- | --- | --- | --- |
| **Bild generieren** | Erstellen Sie ein neues Bild aus einer Textaufforderung oder einem Referenzbild oder generieren Sie ein ähnliches Bild aus einem vorhandenen. | Immer. Das Bild wird durch generative KI generiert, sodass es immer neue C2PA-Metadaten enthält. | Ein Bannerbild für eine E-Mail-Kampagne wird aus einem Text-Prompt generiert, der das gewünschte visuelle Element beschreibt. |

## Inhaltstypen und ihr Umfang {#content-types}

* **Bilder**: Abgedeckt. C2PA-Metadaten werden angehängt, wenn Bilder mit generativer KI generiert werden, und bleiben durch Zuschneiden, Textüberlagerung und Bildüberlagerung erhalten, die von der Bildgenerierung in Coworker-Kampagnen ausgeführt werden.
* **Text:** Nicht anwendbar. Reine Textausgaben in Coworker-Kampagnen, wie z. B. Kopiergenerierung, Übersetzung und Vorschläge für die Markenausrichtung, erfordern keine C2PA-Metadaten.

## Was beim Verschieben von Inhalten passiert {#content-moves}

Coworker Campaign behält C2PA-Metadaten bei, die mit unterstützten Bild-Assets verknüpft sind. Wenn ein Bild C2PA-Metadaten enthält, wenn es in Coworker Campaign importiert wird, bleiben diese Anmeldeinformationen erhalten, wenn das Asset in generierten Kampagneninhalten und in ausgehenden E-Mail-Erlebnissen verwendet wird.

## Zusätzliche Ressourcen {#resources}

* [Transparenz von Inhalt generativer KI](https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/overview/content-transparency){target="_blank"}
* [Benutzerrichtlinien für generative KI in Adobe Experience Cloud](https://www.adobe.com/de/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html){target="_blank"}
* [Leitlinien und Einschränkungen](https://experienceleague.adobe.com/de/docs/journey-optimizer/using/content-management/generate-content/gs-generative#generative-guardrails){target="_blank"}
