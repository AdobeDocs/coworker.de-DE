---
title: Erstellen einer Implementierungs-Checkliste in Co-Worker-Projekten
description: Erfahren Sie, wie Coworker Projects aus Ihrem Plan für Implementierungshandbücher eine vorausgefüllte Implementierungsprüfliste mit Schritten generiert, die Sie zuweisen und verfolgen können.
hold: true
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 0%
---

# Erstellen einer Implementierungs-Checkliste mit Co-Worker-Projekten

Adobe CX Enterprise Coworker kann ein Projekt mit einer Implementierungs-Checkliste in Co-Worker-Projekten generieren, das vorab mit den in Ihrem Implementierungshandbuch für Customer Journey Analytics beschriebenen Schritten ausgefüllt wird, sowie ein Upgrade von Adobe Analytics auf Customer Journey Analytics, Content Analytics (ACA), Marketing Campaign Analytics (MCA) oder Streaming-Medien. Coworker automatisiert oder unterstützt so viele Schritte wie technisch möglich, sodass Sie und Ihr Team einen zentralen, nachverfolgbaren Ort für Ihre Implementierung haben.

Wenn Sie eine Implementierung leiten, technische Schritte ausführen oder nur Einblick in den Fortschritt benötigen, können Sie diese Checkliste verwenden, um Arbeit zuzuweisen, den Status zu verfolgen und mit Ihrem Team zusammenzuarbeiten, ohne den Kollegen zu verlassen.

>[!NOTE]
>
>Beachten Sie Folgendes:
>
>* Diese Funktion ist Teil eines größeren, optionalen Workflows: Benutzerdefinierte Implementierungs- oder Upgrade-Schritte (siehe [Planen der Implementierung mit Coworker](./implementation-guide.md)), Implementierung (diese Checkliste) und Validierung (z. B. [Validieren des Upgrades von Adobe Analytics auf Customer Journey Analytics](./data-validation-aa-cja.md) oder [Validieren der Implementierung von Streaming Media](./streaming-media-validation.md)). Sie müssen nicht alle drei Schritte verwenden. Für die Erstellung dieser Checkliste ist jedoch ein ausgefüllter Implementierungsplan erforderlich.
>* Schritte, die Coworker ausführt oder bei denen Coworker automatisch helfen, umfassen ein Konfidenz- oder Überprüfungssignal. Überprüfen Sie diese Schritte, bevor Sie sie als abgeschlossen markieren - Coworker zeigt keine automatisierten Ergebnisse als verifizierte Tatsache an.

Verwenden Sie diese Checkliste für Folgendes:

* Starten Sie eine Implementierung oder Migration mit einem geordneten, vorausgefüllten Satz von Schritten für Ihren Produktpfad, anstatt einen Plan manuell zusammenzustellen.

* Überprüfen Sie den Status während der Implementierung, einschließlich blockierter und nächster Schritte, ohne den Implementierungs-Lead direkt zu fragen.

* Planen Sie eine Implementierung mit mehreren Plattformen oder mehreren Regionen, bei der die Schritte parallel oder in Phasen anstatt einer einzelnen geraden Linie ausgeführt werden.

* Ermöglichen Sie es Kollegen, die Schritte nach Möglichkeit direkt auszuführen, z. B. eine Validierungsprüfung zwischen Ihren Adobe Analytics- und Customer Journey Analytics-Konfigurationen durchzuführen.

* Führen Sie Validierungs-Gates für Schritte ein, die genehmigt werden müssen, bevor Ihr Team fortfährt.


## Voraussetzungen

<!-- FLAG: Open question — release note confirms a "predefined playbook" transforms the guide plan into a Coworker Project, but it's unconfirmed whether Coworker runs that playbook automatically or the user has to trigger/follow it manually. Written below as if Coworker does it automatically; verify before publishing. Exact UI mechanics also unconfirmed since Coworker Projects platform documentation doesn't exist yet. -->

### Erforderliche Informationen

Um eine Checkliste für die Implementierung zu erstellen, benötigen Sie Folgendes:

* Eine fertige Konversation mit dem Implementierungshandbuch für Ihren Produktpfad. Siehe [Planen der Implementierung mit Coworker](./implementation-guide.md). Coworker wandelt diesen Plan mithilfe eines vordefinierten Playbooks automatisch in ein Coworker-Projekt um - Sie müssen nichts selbst exportieren.

* Zugriff auf Mitarbeiter-Projekte in Ihrer Organisation.

### Einschränkungen

Beachten Sie Folgendes, bevor Sie diese Funktion verwenden:

* **Ist nicht Besitzer des Handbuchinhalts**: Diese Funktion nutzt Pläne aus den Fähigkeiten des Implementierungshandbuchs. Es erstellt und verwaltet diese zugrunde liegenden Inhalte nicht.
* **Das Synchronisierungsverhalten ist noch nicht vollständig definiert**: Die Checkliste soll mit Aktualisierungen Ihres Implementierungshandbuch-Plans synchronisiert bleiben, der genaue Synchronisierungsmechanismus wird jedoch noch definiert. Wenn Ihre Implementierung einen langen Zeitraum umfasst, suchen Sie manuell nach Updates für den Guide-Plan .
* **Erfordert**-Projekte: Diese Funktion hängt davon ab, ob die Plattform „Mitarbeiter-Projekte“ in Ihrer Organisation verfügbar ist.

## Checkliste erstellen

<!-- FLAG: Best guess, not confirmed by source docs. Coworker Projects UI isn't documented in this repo yet — verify exact navigation and UI labels once available. -->

1. Melden Sie sich bei einem Kollegen an.

1. Wählen [!UICONTROL **Projekte**] in der Navigationsleiste aus.

1. Wählen Sie [!UICONTROL **Neues Projekt**] und dann das vordefinierte Playbook aus, das Ihrem Implementierungshandbuch-Plan entspricht.

   Ein Mitarbeiter wandelt Ihren Plan in ein Projekt um, das mit den für Ihren Pfad sortierten Schritten vorausgefüllt ist.

## Überprüfen der Ergebnisse

Coworker generiert Ihre Implementierungs-Checkliste als Coworker-Projekt, aus dem Sie und Ihr Team arbeiten können.

**Projektansicht**

Ihr Projekt gruppiert die in Ihrem Plan angegebenen Implementierungsschritte. Für jeden Schritt haben Sie folgende Möglichkeiten:

* Zuweisen eines Inhabers
* Aktualisierungsstatus, z. B. in Bearbeitung oder abgeschlossen
* Markieren Sie einen Schritt als nicht anwendbar oder überspringen Sie ihn, wenn er nicht auf Ihre Implementierung zutrifft
* Kommentare hinzufügen und mit Ihrem Team zusammenarbeiten
* Genehmigung verlangen, bevor ein Schritt als abgeschlossen betrachtet wird, für Schritte, die genehmigt werden müssen

**Automatisierte und unterstützte Schritte**

Soweit technisch möglich, führt der Mitarbeiter einen Schritt direkt aus bzw. unterstützt ihn bei diesem, z. B. beim Anzeigen von Konfigurations- oder Statusdaten aus Adobe Analytics oder Customer Journey Analytics. Zu diesen Schritten gehört ein Konfidenz- oder Prüfsignal, wie oben beschrieben.

**Exporte**

Exportieren Sie Ihre Checkliste oder den Fortschritt auf Zusammenfassungsebene nach Jira, Workfront oder Excel, damit Sie sie in Ihren bestehenden Projektmanagement-Workflow einbinden können.

**Mehrere Checklisten**

Wenn Sie mehrere gleichzeitige Implementierungen verwalten, z. B. mehrere Report Suites, Regionen oder Marken, können Sie mehrere Projekte mit Implementierungs-Checkliste verwalten, anstatt auf ein Projekt beschränkt zu sein.
