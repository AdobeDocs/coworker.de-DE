---
title: Implementieren und Verwalten von Analytics mit dem Coworker Chat
description: Planen Sie Ihre Implementierung, verfolgen Sie sie in einer Checkliste und validieren Sie Adobe Analytics-, Customer Journey Analytics- und Experience Platform-Daten mit dem Coworker Chat.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 5973a87d21b23d7621366108716cbd476e6f66ae
workflow-type: tm+mt
source-wordcount: '1126'
ht-degree: 0%
---

# Intelligente Implementierung und Administration - Übersicht

Verwenden Sie den Adobe CX Enterprise Coworker-Chat, um Ihre Analytics-Implementierung einzurichten, zu migrieren und zu verwalten und sicherzustellen, dass Sie den Daten hinter jeder Antwort vertrauen können. Mitarbeiter können Ihre Implementierung planen und diesen Plan in eine Checkliste umwandeln, die Ihr Team verfolgen und Ihre Daten nach der Erfassung validieren kann.

Intelligente Implementierung und Verwaltung ist eine von mehreren Analyse-Domains im Coworker Chat. Um alle Domains anzuzeigen, lesen Sie [Analysieren im Kollegen-Chat beginnen](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) unter Analysieren von Daten mit dem Kollegen-Chat.

**Am besten geeignet für:** Admin

## So passt der Implementierungs-Workflow zusammen

Die Anwendungsfälle auf dieser Seite folgen einem optionalen, dreistufigen Workflow. Sie können jede Phase selbst verwenden. Beispielsweise können Sie Ihre Daten validieren, ohne zuerst einen Plan oder eine Checkliste zu generieren.

1. **Plan:** Erhalten Sie einen personalisierten, geordneten Implementierungs- oder Upgrade-Plan. Siehe [Planen der Implementierung mit Coworker](/help/chat/use-cases/data-insights/implementation-guide.md).
1. **Implementieren:** Verwandeln Sie Ihren Plan in eine Checkliste mit Coworker-Projekten, die Ihr Team zuweisen und verfolgen kann. Siehe [Generieren einer Implementierungs-Checkliste mit &#x200B;](/help/chat/use-cases/data-insights/intelligent-checklist.md).
1. **Validieren** Vergewissern Sie sich, dass Ihre Daten korrekt konfiguriert und erfasst wurden. Siehe die Anwendungsfälle für die Validierung in der Tabelle [Anwendungsfälle](#use-cases).

## Voraussetzungen

<!-- FLAG: Confidence: Medium for the shared bullets. They differ from the other domain pages on purpose: planning doesn't query your data, and Experience Platform validation uses Experience Platform datasets rather than data views or report suites. The permission inheritance for Experience Platform is inferred. High for the "Additional prerequisite" notes in the Use cases table, which are sourced from the "Before you begin" section of each linked article. Some of those articles flag their own prerequisites as unconfirmed (implementation-guide.md, intelligent-checklist.md, streaming-media-validation.md), so verify those rows when those flags are resolved. Validate dataset quality for Customer Journey Analytics is a video page with no stated prerequisites, so it isn't listed. -->

Um die Anwendungsfälle auf dieser Seite zu verwenden, benötigen Sie Folgendes:

* Zugriff auf den Coworker Chat. Siehe [Erste Schritte mit der Datenanalyse mit dem Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).
* Zeigen Sie den Zugriff auf die Daten an, die Sie validieren möchten. Der Coworker Chat übernimmt Ihre Berechtigungen von den Adobe-Programmen, mit denen er eine Verbindung herstellt.

## Anwendungsszenarien

| Anwendungsfall | Funktion |
| --- | --- |
| [Implementierung planen](/help/chat/use-cases/data-insights/implementation-guide.md)<p>![Implementierung planen](../../assets/ui-guide-6.png)</p> | Erstellt einen personalisierten, schrittweisen Plan für die Implementierung von Customer Journey Analytics, die Aktualisierung von Adobe Analytics oder die Einrichtung von Content Analytics, Marketing Campaign Analytics oder Streaming Media Collection auf der Edge. Die Pläne enthalten Details wie Eigentümer, Aufwandsschätzungen, Abhängigkeiten und Validierungsschritte.<p>**Beispielaufforderung:** „Helfen Sie mir, meine Implementierung von Customer Journey Analytics zu planen“</p><p>**Zusätzliche Voraussetzung:** Zusätzlich zu den [allgemeinen Voraussetzungen](#prerequisites) erfordert dieser Anwendungsfall auch, dass Sie wissen, welcher Implementierungspfad für Sie gilt, sowie grundlegende Details zu Ihrer aktuellen Umgebung, wie z. B. Ihren Lizenzstatus oder Ihren geplanten Datenaufnahmepfad.</p><p>Weitere Informationen finden Sie unter [Implementierung mit Coworker planen](/help/chat/use-cases/data-insights/implementation-guide.md).</p> |
| [Erstellen einer Checkliste für die Implementierung](/help/chat/use-cases/data-insights/intelligent-checklist.md)<p>![Erstellen einer Checkliste für die Implementierung](../../assets/data-validation-aa-cja/date-detail.png)</p> <p>experimentell</p> | Wandelt Ihren Customer Journey Analytics-Implementierungsplan in eine Checkliste in Co-Worker-Projekten um, in der Ihr Team Schritte zuweisen, den Status verfolgen und Validierungs-Gates hinzufügen kann.<p>**Zusätzliche Voraussetzung** Zusätzlich zu den [allgemeinen Voraussetzungen](#prerequisites) erfordert dieser Anwendungsfall auch ein ausgefülltes Implementierungshandbuch, eine Konversation und den Zugriff auf Mitarbeiter-Projekte in Ihrer Organisation.</p><p>Weitere Informationen finden Sie unter [Generieren einer Implementierungsprüfliste mit Co-Worker-Projekten](/help/chat/use-cases/data-insights/intelligent-checklist.md).</p> |
| [Validieren von Daten beim Upgrade von Adobe Analytics auf Customer Journey Analytics](/help/chat/use-cases/data-insights/data-validation-aa-cja.md)<p>![Validieren von Daten beim Upgrade von Adobe Analytics auf Customer Journey Analytics](../../assets/data-validation-aa-cja/trend-bar-card.png)</p> | Vergleicht Dimensionen, Metriken und Trends zwischen Ihren Adobe Analytics Report Suites und Customer Journey Analytics-Datenansichten, kennzeichnet Diskrepanzen und empfiehlt dann Fehlerbehebungen, um Ihr Upgrade zu unterstützen.<p>**Am besten geeignet für:** Admin, Analyst</p><p>**Beispielaufforderungen:**</p><ul><li>„Meine AA Report Suite mit meiner CJA-Datenansicht vergleichen“</li><li>„Welche Metriken stimmen zwischen AA und CJA nicht überein?“</li></ul><p>**Zusätzliche Voraussetzung** Neben den [allgemeinen Voraussetzungen](#prerequisites) erfordert dieser Anwendungsfall auch die zu validierende Adobe Analytics Report Suite und die Customer Journey Analytics-Datenansicht, die dieselben Daten enthält.</p><p>Weitere Informationen finden Sie unter [Validieren von Daten mit einem Kollegen beim Upgrade von Adobe Analytics auf Customer Journey Analytics](/help/chat/use-cases/data-insights/data-validation-aa-cja.md).</p> |
| [Validieren der Implementierung von Streaming-Medien](/help/chat/use-cases/data-insights/streaming-media-validation.md)<p>![Validieren der Implementierung von Streaming-Medien](../../assets/ui-guide-8.png)</p> <p>experimentell</p> | Überprüft Ihren Datenstrom, Ihr Schema, Ihren Datensatz, Ihre Datenansicht und Ihre Sitzungsdaten, um sicherzustellen, dass das Tracking von Streaming-Medien konfiguriert ist und die Daten korrekt erfasst werden.<p>**Beispielaufforderung:** „Wie gesund ist meine Implementierung von Streaming-Medien insgesamt?“</p><p>**Zusätzliche Voraussetzung:** Zusätzlich zu den [allgemeinen Voraussetzungen](#prerequisites) erfordert dieser Anwendungsfall auch, dass die Experience Platform- und Customer Journey Analytics-Daten Ihres Unternehmens mit der -Mitarbeiterin bzw. dem -Mitarbeiter verbunden sind. Bei einigen Validierungsmodi benötigen Sie auch eine Video-Sitzungs-ID oder eine Protokolldatei.</p><p>Weitere Informationen finden Sie unter [Validieren der Implementierung von Streaming-Medien mit Coworker](/help/chat/use-cases/data-insights/streaming-media-validation.md).</p> |
| [Validieren der Datensatzqualität für Customer Journey Analytics](/help/chat/use-cases/data-insights/validate-dataset-quality-for-cja.md)<p>![Validieren der Datensatzqualität für Customer Journey Analytics](../../assets/data-validation-aep/dataset-validation.png)</p> <p>Experimentell (nächste Woche)</p> | Identifiziert die Datensätze, die Ihre Customer Journey Analytics-Berichte unterstützen, prüft dann Schemata, Identitätsqualität und Feldqualität, damit Sie Probleme beheben können, bevor Sie Dashboards erstellen.<p>Weitere Informationen finden Sie unter [Validieren von Customer Journey Analytics-Daten mit der Datenvalidierungsfertigkeit in Coworker](/help/chat/use-cases/data-insights/validate-dataset-quality-for-cja.md).</p> |
| [Validieren von Daten nach der Aufnahme in Experience Platform](/help/chat/use-cases/data-insights/data-validation-aep.md)<p>![Validieren von Daten nach der Aufnahme in Experience Platform](../../assets/data-validation-aep/null-values.png)</p> | Führt statistische und semantische Prüfungen für Experience Platform-Datensätze und -Felder durch, um Probleme mit der Datenqualität, z. B. ungültige Werte oder Zuordnungsprobleme, nach einer neuen Implementierung oder im Rahmen der laufenden Datenverwaltung zu ermitteln.<p>**Beispielaufforderungen:**</p><ul><li>„Überprüfen des Datensatzes [Datensatzname]&quot;</li><li>„Validieren des [Datenfelds] aus dem Datensatz [Datensatzname]&quot;</li></ul><p>**Zusätzliche Voraussetzung** Neben den [allgemeinen Voraussetzungen](#prerequisites) erfordert dieser Anwendungsfall auch den Namen oder die ID des Datensatzes, den Sie validieren möchten. Optional können Sie den Namen eines bestimmten Felds angeben, das validiert werden soll.</p><p>Weitere Informationen finden Sie unter [Validieren Ihrer Experience Platform-Daten mit Coworker](/help/chat/use-cases/data-insights/data-validation-aep.md).</p> |
| [Beschleunigen von Dateneinblicken](/help/chat/use-cases/data-insights/accelerate-data-insights.md) | In einem Video wird gezeigt, wie Coworker Ihre Implementierung plant, unterstützte Aktionen ausführt und Produkt- und Entwicklungsschritte in Adobe Experience Manager, Experience Platform, Web SDK und Customer Journey Analytics anleitet, bis Ihre Website-Interaktionsdaten bereit zur Analyse sind.<p>Weitere Informationen finden Sie unter [Beschleunigen von Dateneinblicken mit Coworker, AEM und CJA](/help/chat/use-cases/data-insights/accelerate-data-insights.md).</p> |

## Verwendete Kenntnisse

<!-- FLAG: Confidence: High for `aa-cja-validation` (listed in the Skills and limitations table and in workflows.md). Medium for `data-validation`: workflows.md lists it, but with a TODO to confirm the skill ID with engineering. Medium for the implementation guide skills and the Streaming Media Validation skill: the articles name them but don't give technical skill IDs, so they're listed by display name. Only `aa-cja-validation` currently appears in the Skills and limitations table on analytics-overview.md. Add the others there so the link below covers them. -->

Der -Mitarbeiter verwendet die folgenden Fähigkeiten für die in diesem Artikel beschriebenen Anwendungsfälle. Eine Liste aller Analytics-Fähigkeiten, einschließlich der erforderlichen Berechtigungen und der nicht abgedeckten Bereiche, finden Sie unter [Fähigkeiten und Einschränkungen](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) in Analysieren von Daten mit dem Coworker Chat.

| Skill | Verwendet für |
| --- | --- |
| Implementierungshandbuch-Kenntnisse (jeweils eine für Customer Journey Analytics, ein Upgrade von Adobe Analytics auf Customer Journey Analytics, Content Analytics, Marketing Campaign Analytics und Streaming-Medien) | Implementierung planen |
| `aa-cja-validation` | Validieren von Daten beim Upgrade von Adobe Analytics auf Customer Journey Analytics |
| Validierungsfähigkeiten für Streaming-Medien | Validieren der Implementierung von Streaming-Medien |
| Qualifikation zur Datenvalidierung (`data-validation`) | Validieren der Datensatzqualität für Customer Journey Analytics<br>Validieren von Daten nach der Aufnahme in Experience Platform |

## Tipps für bessere Ergebnisse

* Benennen Sie die spezifische Report Suite und Datenansicht, die Sie bei der Datenvalidierung vergleichen möchten.
* Verwenden Sie Validierungsergebnisse als Anleitung für Ihre eigenen Änderungen. Die Fähigkeiten zur Validierung und Datenvalidierung von Streaming-Medien identifizieren Probleme, ändern jedoch nicht Ihre Konfiguration oder Daten.
* Führen Sie die Validierung von Streaming-Medien nach jeder Implementierungsänderung erneut aus. Er wird bei Bedarf ausgeführt und bietet keine kontinuierliche Überwachung.
* Verwenden Sie die Implementierungshandbuch-Fähigkeiten nur für die Planung. Sie greifen nicht auf Ihre Adobe-Systeme zu und führen die Implementierung nicht durch.

## Nächste Schritte

* Einen Überblick über die Datenanalyse mit dem Coworker Chat, einschließlich der anderen Analyse-Domains und Best Practices, finden Sie unter [Analysieren von Daten mit dem Coworker Chat](/help/chat/use-cases/data-insights/analytics-overview.md).
* Informationen zum Einrichten von Coworker Chat und zum Durchführen eines Arbeitsbeispiels finden Sie unter [Erste Schritte mit der Analyse von Daten mit Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).
