---
title: Planen der Implementierung von Customer Journey Analytics oder Streaming-Medien mit Kollegen
description: Erfahren Sie, wie die Fähigkeiten des Implementierungshandbuchs für Mitarbeiter ein Discovery-Gespräch in einen personalisierten, geordneten Implementierungsplan mit exportierbaren Checklisten verwandeln.
hold: true
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '1239'
ht-degree: 1%
---

# Implementierung mit Kollegen planen

Adobe CX Enterprise Coworker umfasst fünf Implementierungshandbücher, eine für jede Produktoberfläche: Customer Journey Analytics, ein Upgrade von Adobe Analytics auf Customer Journey Analytics, Content Analytics (ACA), Marketing Campaign Analytics (MCA) und Streaming Media. Jede Fähigkeit verwandelt ein kurzes Discovery-Gespräch in einen personalisierten, abhängigkeitsbewussten Implementierungsplan, komplett mit einer interaktiven Checkliste und einsatzbereiten Exporten, alles innerhalb eines einzigen Coworker Chat-Gesprächs.

Wenn Sie für eines dieser Produkte eintreten oder zu einem dieser Produkte migrieren, können Sie diese Kenntnisse nutzen, um einen geordneten, schrittweisen Plan zu erhalten, ohne die Implementierungsanforderungen von Adobe manuell zu untersuchen oder einen Projektplan von Grund auf neu zu erstellen.

>[!NOTE]
>
>Beachten Sie Folgendes:
>
>* Diese Implementierungshandbuch-Fähigkeiten sind Teil eines größeren, optionalen Workflows: Benutzerdefinierte Implementierungs- oder Upgrade-Schritte (diese Handbücher), Implementierung (siehe [Erstellen einer Implementierungs-Checkliste mit Coworker-Projekten](./intelligent-checklist.md)) und Validierung (z. B. [Validieren des Upgrades von Adobe Analytics auf Customer Journey Analytics](./data-validation-aa-cja.md) oder [Validieren der Implementierung von Streaming-Medien](./streaming-media-validation.md)). Sie brauchen nicht alle drei Stufen zu verwenden. Sie können beispielsweise Ihre Daten validieren, ohne jemals einen Plan oder eine Checkliste zu generieren.
>* Diese Kenntnisse greifen nicht auf Ihre Adobe-Systeme zu und nehmen keine Änderungen vor. Sie helfen Ihnen bei der Planung Ihrer Implementierung. Sie führen sie nicht durch und vergleichen sie auch nicht mit einem Live-Mandanten.

Diese Fähigkeiten verwenden, um:

* Hier erhalten Sie einen personalisierten, übersichtlichen Plan für das von Grund auf neue Customer Journey Analytics, einschließlich Eigentümern, Aufwandsschätzungen und Abhängigkeiten für jeden Schritt.

* Holen Sie sich einen Migrationsplan für die Aktualisierung von Adobe Analytics auf Customer Journey Analytics, einschließlich der Adobe Analytics-Funktionsgleichheitszuordnung, der historischen Aufstockungssequenzierung und eines Validierungstests, bevor Sie Adobe Analytics einstellen.

* Hier erhalten Sie einen Plan für die Implementierung von Content Analytics (ACA), einschließlich Lizenzierung, Datenschutz und PII-Scoping, sowie den Konfigurationsassistenten.

* Holen Sie sich einen Onboarding-Plan für Marketing Campaign Analytics (MCA), der sich an Ihren Aufnahmepfad anpasst, unabhängig davon, ob Sie Adobe-Quell-Connectoren, Ihren eigenen Datensatz oder einen hybriden Ansatz verwenden.

* Erhalten Sie einen Implementierungsplan für die Streaming-Mediensammlung in der Edge, einschließlich Datenstromkonfiguration, plattformübergreifender SDK-/API-Implementierung und des Medienereignismodells.

## Voraussetzungen

<!-- FLAG: Best guess, not confirmed by source docs. Requirements doc doesn't state explicit prerequisites for starting a discovery conversation — verify with skills-overview.md or SME before publishing. -->

### Erforderliche Informationen

Um eine Konversation mit einem Implementierungshandbuch zu beginnen, benötigen Sie Folgendes:

* Welcher der fünf Implementierungspfade gilt für Sie: Customer Journey Analytics (neu), ein Upgrade von Adobe Analytics auf Customer Journey Analytics, Content Analytics (ACA), Marketing Campaign Analytics (MCA) oder Streaming Media.

* Grundlegende Details zu Ihrer aktuellen Umgebung, z. B. ob Sie über eine bestehende Adobe Analytics-Implementierung, Ihren Lizenzstatus oder Ihren geplanten Datenaufnahmepfad verfügen. Das Discovery-Gespräch fragt nach diesen Details, aber sie bereit zu haben, beschleunigt den Prozess.

### Einschränkungen

Bevor Sie diese Fähigkeiten verwenden, beachten Sie die folgenden Einschränkungen:

* **Nur Planung**: Diese Kenntnisse greifen nicht auf Ihre Adobe-Systeme zu und nehmen keine Änderungen vor. Sie führen die Implementierung nicht durch und überprüfen sie auch nicht anhand eines Live-Mandanten.
* **Eine Produktoberfläche pro Qualifikation**: Jede Qualifikation deckt einen einzelnen Implementierungspfad ab. Wenn sich Ihre Anfrage auf eine andere Produktoberfläche bezieht, werden Sie von der Kenntnis zur richtigen geleitet, anstatt direkt zu antworten.
* **Allein kein Projekt-Tracking**: Diese Fähigkeiten generieren einen Plan und Exporte, verfolgen jedoch nicht den aktuellen Status, die Zusammenarbeit oder die Genehmigungen selbst. Um Ihren Plan im Laufe der Zeit zu verfolgen, wandeln Sie ihn mithilfe eines vordefinierten Playbooks in ein Co-Worker-Projekt um. Siehe [Generieren einer Implementierungs-Checkliste mit ](./intelligent-checklist.md).

## Starten einer Implementierungsplanungssitzung

1. Melden Sie sich bei einem Kollegen an.

1. Wählen Sie [!UICONTROL **Neuer Chat**] aus.

1. Beschreiben Sie im Textfeld die Implementierung oder Migration, die Sie planen möchten. Beispiel:

   **Eingabeaufforderung**

   > Hilfe bei der Planung meiner Implementierung von Customer Journey Analytics.

   Ihre Anfrage wird an das entsprechende Implementierungshandbuch weitergeleitet, das eine interaktive Discovery-Konversation startet.

1. (Bedingt) Wenn die Kenntnisse nicht bestimmen können, welcher Implementierungspfad für Sie gilt, beantworten Sie die klärende Frage, die sie stellen, und fahren Sie dann fort.

## Auswählen des Implementierungspfads

Jede Implementierungshandbuch-Qualifikation deckt eine Produktoberfläche ab.

### Customer Journey Analytics

Erhalten Sie einen personalisierten, geordneten Implementierungsplan für die vollständige Einrichtung von Customer Journey Analytics, ohne dass eine Adobe Analytics-Bereitstellung migriert werden muss. Ihr Plan enthält für jeden Schritt Eigentümer, Aufwandsschätzungen und Abhängigkeiten.

Beispiel-Eingabeaufforderungen:

* Hilfe bei der Planung meiner Implementierung von Customer Journey Analytics.
* Ich stehe von Grund auf auf auf Customer Journey Analytics. Erstellen Sie einen Implementierungsplan.

### Upgrade von Adobe Analytics auf Customer Journey Analytics

Holen Sie sich einen Migrationsplan, der die Adobe Analytics-Funktionsparität mit Customer Journey Analytics abbildet, historische Aufstockungen sequenziert und eine Validierung und einen parallel ausgeführten Gate-Vorgang enthält, bevor Sie Adobe Analytics stilllegen.

Beispiel-Eingabeaufforderungen:

* Hilfe bei der Planung meines Upgrades von Adobe Analytics auf Customer Journey Analytics.
* Erstellen Sie einen Migrationsplan von Adobe Analytics nach Customer Journey Analytics.

### Content Analytics (ACA)

Hier erhalten Sie einen Plan für die Implementierung von Content Analytics (ACA), einschließlich Lizenzierung, Datenschutz und PII-Scoping, sowie den Konfigurationsassistenten. Da ACA keine DULE-, CMK- oder HIPAA-Abdeckung hat, umfasst Ihr Plan Datenschutzgating-Schritte.

Beispiel-Eingabeaufforderungen:

* Hilfe bei der Planung meiner Implementierung von Content Analytics.
* Erstellen Sie einen ACA-Implementierungsplan.

### Marketing Campaign Analytics (MCA)

Holen Sie sich einen Onboarding-Plan für Marketing Campaign Analytics (MCA) Essentials, der sich an Ihren Aufnahmepfad anpasst, unabhängig davon, ob Sie Adobe-Quell-Connectoren, Ihren eigenen Datensatz oder einen hybriden Ansatz verwenden, sodass die funnel-Zuordnungs- und Datenausrichtungsschritte mit Ihrer Umgebung übereinstimmen.

Beispiel-Eingabeaufforderungen:

* Hilfe bei der Planung meiner Implementierung von Marketing Campaign Analytics.
* Erstellen Sie einen MCA-Onboarding-Plan mit meinem eigenen Datensatz.

### Streaming-Medien

Erhalten Sie einen Implementierungsplan für die Streaming-Mediensammlung in der Edge, der die Datenstromkonfiguration, die plattformübergreifende SDK-/API-Implementierung und das Medienereignismodell umfasst, damit Sie Sitzungen, Pings und Abschlüsse für Customer Journey Analytics- und/oder Adobe Analytics-Berichte korrekt instrumentieren können.

Beispiel-Eingabeaufforderungen:

* Hilfe bei der Planung meiner Implementierung von Streaming-Medien.
* Erstellen Sie einen Plan für die Instrumentierung von Streaming-Medien auf der Edge.

## Überprüfen der Ergebnisse

Ein Mitarbeiter gibt im selben Gespräch Ihren Implementierungsplan als interaktive Checkliste und Zusammenfassung zurück.

**Interaktive Checkliste**

Eine HTML-Checkliste , die Ihre Implementierungsschritte in Phasen und Meilensteine gruppiert. Für jeden Schritt enthält die Checkliste:

* Eine Aufwandsschätzung
* Einen primären Eigentümer und alle unterstützenden Eigentümer
* Harte Abhängigkeiten von anderen Schritten
* Ob der Schritt übersprungen werden kann
* einen Link zur entsprechenden Dokumentation zu Experience League oder developer.adobe.com

**Exporte**

Laden Sie Ihren Plan in dem Format herunter, das Ihrem Workflow entspricht:

| Exportieren | Was es enthält |
| --- | --- |
| CSV | Eine einfache Liste von Schritten |
| Jira-CSV importieren | Schritte formatiert mit Story-Punkten, Priorität und Beschriftungen für den Import nach Jira |
| WORKFRONT CSV | Mit Dauer und Vorgängern formatierte Schritte für den Import in Workfront |
| Markdown | Eine Checkliste, die Sie in Dokumentationen oder Wikis einfügen können |

**In-Chat-Zusammenfassung**

Zusammen mit der Checkliste bietet Coworker eine dreiteilige Zusammenfassung direkt in der Konversation:

1. Ein Überblick über Ihren Plan
1. Die vollständige Schritttabelle
1. Downloadlinks für jeden Export

## Erstellung des Plans

Jede Implementierungshandbuch-Qualifikation folgt demselben vierstufigen Prozess:

* **Discovery**: Bei einem gestaffelten Gespräch werden fünf bis neun Fragenkomplexe gestellt, die speziell auf Ihren Implementierungspfad zugeschnitten sind und Ihnen Informationen zu Ihrer Umgebung und Ihren Zielen vermitteln.
* **Berechnen** Ein LLM bestimmt, welche bedingten Schritte und Abhängigkeitsüberschreibungen auf Ihre Antworten angewendet werden. Es schreibt nicht den Plan selbst.
* **Zusammenführen und Rendern**: Ein deterministischer Prozess löst Abhängigkeiten zwischen Schritten auf, ordnet sie an, berechnet den kritischen Pfad (die längste Kette abhängiger Schritte) und generiert Ihre Checkliste und Exporte.
* **Versand**: Der Mitarbeiter stellt Download-Links und eine Zusammenfassung Ihres Plans im Chat bereit.

Diese Kombination aus geführter Entdeckung und deterministischer Anordnung bedeutet, dass Ihr Plan konsistent aus Ihren Antworten generiert wird, anstatt frei geschrieben zu werden.
