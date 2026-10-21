---
title: Analysieren von Customer Journey Analytics-Daten mit dem Coworker Chat
description: Erfahren Sie, wie Sie mit dem Adobe CX Enterprise Coworker-Chat Customer Journey Analytics-Daten analysieren, Trichter erstellen und herausfinden können, wo Kundinnen und Kunden auf der Journey abbrechen.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 5973a87d21b23d7621366108716cbd476e6f66ae
workflow-type: tm+mt
source-wordcount: '1281'
ht-degree: 2%
---

# Analysieren von Daten mit dem Kollegen-Chat

Die Informationen auf dieser Seite bieten einen Überblick über den Adobe CX Enterprise Coworker-Chat und wie er Ihnen bei der Analyse von Daten für Ihr Unternehmen helfen kann.

Der Coworker Chat ermöglicht es Teams, Adobe-Produktaufgaben mithilfe natürlicher Sprache zu automatisieren und Ideen schnell in Maßnahmen mit flexibler Planung, anpassbaren Fähigkeiten und intelligenter Ausführung zu verwandeln. Weitere allgemeine Informationen zu Kollegen finden Sie unter [Übersicht über CX Enterprise Coworker](/help/home.md).

## Funktionsweise der Datenanalyse

Coworker Chat kann erweiterte Datenanalysen durchführen, die zuvor nur in Analysis Workspace möglich waren. Der Coworker Chat greift auf Daten aus Ihren Customer Journey Analytics-Datenansichten oder Adobe Analytics-Report Suites zu, sodass Sie Daten untersuchen und Antworten mit Eingabeaufforderungen in natürlicher Sprache erhalten können.

Der Coworker Chat erbt Berechtigungen von Customer Journey Analytics oder Adobe Analytics. Sie können nur auf die Datenansichten, Report Suites, Dimensionen, Metriken und Segmente zugreifen, die Ihnen in Analysis Workspace zur Verfügung stehen.

Wenn Sie eine Visualisierung im Coworker Chat erstellen, können Sie sie jederzeit in Analysis Workspace öffnen, um eine manuelle Kontrolle zu erhalten.

## Schnelle Antworten und gründliche Arbeit

Sie können den Coworker Chat auf zwei Arten verwenden, je nachdem, wie viel Analyse Sie benötigen:

* **Schnelle Antworten** - Stellen Sie eine direkte, verständliche Frage und erhalten Sie eine sofortige Antwort. Business-Anwender nutzen den Coworker Chat oft auf diese Weise, und Analysten verwenden ihn auch, wenn sie eine schnelle Antwort für einen Stakeholder benötigen.
* **Tief durchdachte Arbeit** - Führen Sie ein ausgedehntes, mehrgängiges Gespräch mit Coworker Chat, um ein Geschäftsproblem zu untersuchen, Ursachen auszuschließen und eine Empfehlung zu erhalten. Analysten verwenden diesen Ansatz normalerweise, um Daten eingehend zu untersuchen, bevor sie eine Empfehlung abgeben.

## Analysieren im Kollegen-Chat beginnen

Beginnen Sie, indem Sie beschreiben, was Sie wissen möchten, in einfacher Sprache. Der Coworker Chat plant die Analyse, fragt Ihre Datenansichten oder Report Suites ab und erstellt Visualisierungen und Zusammenfassungen.

Die folgenden Anwendungsfälle sind nach Analyse-Domain gruppiert. Jede Domain verfügt über eine eigene Seite mit Anwendungsfällen, Beispielaufforderungen, Voraussetzungen und den verwendeten Fähigkeiten.

| Domain | Mögliche Optionen | Geeignet für |
| --- | --- | --- |
| [Intelligente Implementierung und Verwaltung](/help/chat/use-cases/data-insights/data-governance-and-validation.md) | Richten Sie Ihre Implementierung ein, migrieren und verwalten Sie sie und stellen Sie sicher, dass Sie den Daten hinter jeder Antwort vertrauen können. | Admin |
| [Journey-Analyse](/help/chat/use-cases/data-insights/journey-analysis.md) | Finden Sie heraus, wo Kunden die Journey zur Konvertierung abbrechen und warum, über Kanäle, Geräte und Segmente hinweg. | Analyst, Business-Anwender |
| [Zielgruppen- und Segmentanalyse](/help/chat/use-cases/data-insights/audience-and-segment-analysis.md) | Erfahren Sie, welche Kundengruppen sich anders verhalten und wie Sie sich verhalten, damit Sie sich auf die wichtigen konzentrieren können. | Analyst, Business-Anwender |
| [Business Performance](/help/chat/use-cases/data-insights/business-performance.md) | Verstehen, wie sich das Unternehmen entwickelt, warum sich eine Metrik bewegt, wohin sie sich bewegt und was als Nächstes zu tun ist. | Analyst, Business-Anwender |
| [Content-Performance](/help/chat/use-cases/data-insights/content-performance.md) | Erfahren Sie, welche Inhalte aus welchem Grund profitieren, bis hin zu den Attributen der einzelnen Assets, damit Sie in das investieren können, was funktioniert. | Geschäftskunde |
| [Marketing-Messung und -Attribution](/help/chat/use-cases/data-insights/marketing-measurement-and-attribution.md) | Machen Sie sich mit den inkrementellen Auswirkungen jedes Marketing-Kanals und jeder Kampagne vertraut, sodass Sie Ausgaben zuweisen können, um den ROI zu optimieren. | Analyst, Business-Anwender |

## Kenntnisse und Einschränkungen

Die folgenden Kenntnisse stehen für die Analyse von Customer Journey Analytics- oder Adobe Analytics-Daten zur Verfügung.

| Skill | Verwenden Sie sie für folgende Zwecke: | Erforderliche Berechtigungen | Außerhalb des Geltungsbereichs |
| --- | --- | --- | --- |
| `cja`, `aa` | Abfragen von Customer Journey Analytics-Datenansichten (`cja`) oder Adobe Analytics Report Suites (`aa`) in Echtzeit:<ul><li>Abrufen von Metriken, Dimensionen, Segmenten, Datenansichten und Report Suites</li><li>Kanäle, Zeiträume oder Segmente nebeneinander vergleichen</li><li>Ausführen einer mehrstufigen funnel- und Fallout-Analyse</li><li>Prognostizierte Metriken basierend auf historischen Trends</li></ul> | Anzeigen des Zugriffs auf die Datenansicht oder Report Suite, die Sie abfragen möchten | <ul><li>Erstellen oder Bearbeiten von Datenansichts- oder Report Suite-Komponenten</li><li>Daten außerhalb der Datenansichten oder Report Suites, auf die Sie Zugriff haben</li><li>Prädiktive Modellierung über Metrikvorhersagen hinaus</li></ul> |
| `cja-root-cause-analysis`, `aa-root-cause-analysis` | Finden Sie heraus, warum sich eine Metrik geändert hat, anstatt nur ihre Änderung zu melden:<ul><li>Untersuchen einer Änderung an einer bekannten Metrik über einen bekannten Zeitraum</li><li>Aufdecken der Dimensionen und Segmente, die zur Änderung beigetragen haben</li></ul> | Anzeigen des Zugriffs auf die zu analysierende Datenansicht oder Report Suite | <ul><li>Erkennen von Anomalien, nach denen Sie nicht gefragt haben (keine automatisierten oder Echtzeitwarnungen)</li><li>Ursachenanalyse für Metriken außerhalb einer Datenansicht oder Report Suite, auf die Sie Zugriff haben</li></ul> |
| `cja-executive-summary` | Zusammenfassungen Ihrer Daten für alle Beteiligten:<ul><li>Zusammenfassen der Leistung über einen bestimmten Zeitraum</li><li>Erstellen präskriptiver Empfehlungen auf Grundlage der Daten</li><li>Gliederungsinhalte für das Auslesen von Folien- oder Stakeholdern</li></ul> | Anzeigen des Zugriffs auf die Datenansichten oder Report Suites, die in der Zusammenfassung behandelt werden | <ul><li>Erstellen des endgültigen Foliendecks oder der Präsentationsdatei</li><li>Zusammenfassungen, die Datenansichten oder Report Suites umfassen, auf die Sie keinen Zugriff haben</li></ul> |
| `aa-cja-validation` | Vergleichen, Überprüfen und Abstimmung von Daten zwischen [!DNL Adobe Analytics] und Customer Journey Analytics:<ul><li>Metrikwerte zwischen einer Report Suite und einer Datenansicht vergleichen</li><li>Kennzeichnen von Diskrepanzen zwischen den beiden Datenquellen</li></ul> | Anzeigen des Zugriffs auf die [!DNL Adobe Analytics] Report Suite und die zu vergleichende Customer Journey Analytics-Datenansicht | <ul><li>Beheben der zugrunde liegenden Ursache einer Datendiskrepanz</li><li>Validieren von anderen Datenquellen als [!DNL Adobe Analytics] und Customer Journey Analytics</li></ul> |
| `cja-skill-creator` | Verwandeln Sie eine Analyse, die Sie bereits durchgeführt haben, in eine wiederverwendbare Fähigkeit:<ul><li>Konvertieren einer abgeschlossenen Analyse in eine benannte, wiederverwendbare Kenntnisse</li><li>Eine gespeicherte Kenntnis für zukünftige Chat-Sitzungen verfügbar machen</li></ul> | Kenntnisse verwalten | <ul><li>Automatisches Freigeben einer gespeicherten Qualifikation für andere Benutzer (Qualifikationsbibliotheken auf Unternehmensebene erfordern die Einrichtung durch Administratoren)</li><li>Bearbeiten der Datenansichts- oder Report Suite-Komponenten, auf die eine Qualifikation verweist</li></ul> |

## Best Practices bei der Datenanalyse mit dem Coworker Chat

### Best Practices auf Unternehmensebene

* Benennen Sie einen Analysten aus Ihrer Organisation als Champion einer Kollegin oder eines Kollegen.

* Erstellen Sie eine Bibliothek mit überprüften Eingabeaufforderungen und Kenntnissen, die mit den Daten und Komponenten korrelieren, die den Benutzern zur Verfügung stehen.

* Erstellen Sie eine oder mehrere Fähigkeiten, die den Coworker Chat anweisen, nur die Komponenten zu verwenden, die Sie in Analysen verwenden möchten. Dies hilft Coworker Chat, Benutzern in Ihrer Organisation die relevantesten Daten zu geben.

* Bringen Sie Benutzer in Erfahrung, wann sie den Coworker Chat um eine schnelle Antwort bitten sollten, anstatt ihn für eine gründliche Gedankenarbeit zu verwenden.

### Best Practices auf Benutzerebene

* Planmodus verwenden.

  Dieser Modus ist besonders für komplexe Aufgaben nützlich, kann aber auch bessere Ergebnisse für einfache Aufgaben liefern, da er es Mitarbeitern ermöglicht, Folgefragen zu stellen, bevor sie handeln. Weitere Informationen finden Sie unter [Planmodus](/help/chat/ui-guide.md#plan-mode).

* Achten Sie beim Erstellen einer Eingabeaufforderung auf eine möglichst präzise Vorgehensweise:

  * Benennen Sie die Dimensionen, Metriken und den Datumsbereich, die analysiert werden sollen.
  * Referenzieren Sie Komponenten anhand ihres genauen Namens.
  * Geben Sie alle Segmente, Zielgruppen, Kanäle oder Geräte an, die Sie einbeziehen, ausschließen oder vergleichen möchten.
  * Geben Sie an, ob Sie einen bestimmten Visualisierungstyp wünschen, z. B. eine funnel-, Trend- oder Kohortentabelle.
  * Fragen Sie nach den empfohlenen nächsten Schritten, wenn Sie im Coworker Chat weitere Fragen vorschlagen möchten.
  * Fordern Sie bei der Projektion von Metriken einen Prognosehorizont an, z. B. „Nächste 30 Tage“.
  * Erwähnen Sie jede Hypothese, die Sie bereits haben, sodass Coworker Chat sie validieren oder ausschließen kann.
  * Fragen Sie nach den beitragenden Dimensionen, wenn Sie eine Aufschlüsselung einer Metrikänderung wünschen.
  * Geben Sie die Zielgruppe für eine Zusammenfassung an, z. B. die Führung oder das Marketing-Team, und fordern Sie einen Folienüberblick an, wenn Sie die Ergebnisse präsentieren möchten.
  * Benennen Sie die spezifische Report Suite und Datenansicht, die Sie bei der Datenvalidierung vergleichen möchten.
  * Führen Sie zuerst eine Analyse durch und bitten Sie dann den Coworker Chat, diese als Qualifikation zu speichern, ihr einen klaren, beschreibenden Namen zu geben und zu notieren, wie oft Sie sie wiederverwenden möchten.

* Fügen Sie Standardanweisungen zum Arbeitsspeicher des Kollegen-Chats hinzu. Wenn Sie beispielsweise immer Daten aus denselben Datenansichten oder Report Suites verwenden, fügen Sie diese dem Speicher hinzu. Weitere Informationen finden Sie unter [Datenansicht oder Report Suite-Voreinstellung im Speicher hinzufügen](/help/chat/use-cases/data-insights/analytics-chat.md#add-a-data-view-or-report-suite-preference-in-memory) in Erste Schritte mit der Analyse von Daten mit dem Coworker Chat.

## Nächste Schritte

* Informationen zum Einrichten von Coworker Chat und zum Durchführen eines Arbeitsbeispiels finden Sie unter [Erste Schritte mit der Analyse von Daten mit Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).
* Informationen zu allen Workflows für den Coworker-Chat und den dahinter stehenden Fähigkeiten finden Sie unter [Workflows für den Coworker-Chat](/help/chat/use-cases/workflows.md).


