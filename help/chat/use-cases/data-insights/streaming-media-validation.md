---
title: Validieren der Implementierung von Streaming-Medien mit einem Kollegen
description: Erfahren Sie, wie die Streaming-Medien-Validierungsfertigkeit eines Mitarbeiters Ihre Konfiguration, Sitzungen und Protokolle überprüft, um zu bestätigen, dass Ihre Implementierung korrekt verfolgt wird.
hold: true
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 2%
---

# Validieren der Implementierung von Streaming-Medien mit einem Kollegen

Adobe CX Enterprise Coworker verfügt über eine Fähigkeit zur Validierung von Streaming-Medien, die Ihre Implementierung von Adobe-Streaming-Medien (Video- und Audioanalysen) auf der Edge Network überprüft und Customer Journey Analytics und/oder Adobe Analytics zuführt. Anstatt manuell auf Assurance, die Datensatzkonfiguration, XDM-Schemafeldgruppen, die Customer Journey Analytics-Datenansicht und Rohnetzwerkprotokolle zu verweisen, erhalten Sie einen einzigen Validierungsbericht.

Wenn Sie das Tracking von Streaming-Medien implementieren oder Fehler beheben, können Sie diese Fähigkeit verwenden, um zu bestätigen, dass Ihre Implementierung korrekt konfiguriert ist, indem Sie wie erwartet Daten erfassen und erfassen, was Sie verfolgen möchten - alles in einem einzigen Gespräch mit Kollegen im Chat.

>[!NOTE]
>
>Beachten Sie Folgendes:
>
>* Diese Kenntnisse sind Teil eines größeren, optionalen Workflows: benutzerdefinierte Implementierungs- oder Upgrade-Schritte (siehe [Planen der Implementierung mit Coworker](./implementation-guide.md)), Implementierung (siehe [Erstellen einer Implementierungsprüfliste mit Coworker-Projekten](./intelligent-checklist.md)) und Validierung (diese Kenntnisse). Sie brauchen nicht alle drei Stufen zu verwenden. Sie können beispielsweise Ihre Implementierung von Streaming-Medien validieren, ohne jemals einen Plan oder eine Checkliste zu generieren.
>* Diese Fähigkeit validiert und diagnostiziert Probleme. Es werden weder die Konfiguration noch die Daten behoben. Verwenden Sie die Ergebnisse als Anleitung für Ihre eigene Behebung.

Diese Kenntnisse verwenden, um:

* Führen Sie einen Konfigurationsaudit für Ihren Datenstrom, Ihr XDM-Schema, Ihren Datensatz und Ihre Customer Journey Analytics-Datenansicht aus, wobei der erste fehlerhafte Checkpoint als die wahrscheinliche Ursache markiert wurde.

  Diese Funktion ist derzeit nur eingeschränkt verfügbar.

* Überprüfen Sie eine bestimmte Video-Sitzungs-ID und sehen Sie genau, bei welchem Hop, welcher Datensatzaufnahme oder welcher Customer Journey Analytics-Zuordnung eine Diskrepanz aufgetreten ist.

* Validieren einer Sitzung über ein hochgeladenes Charles- oder HAR-Protokoll oder eine einfachere URL-Liste, ohne dass eine Live-Assurance-Sitzung erforderlich ist.

  Diese Funktion ist derzeit nur eingeschränkt verfügbar.

* Hier erhalten Sie eine allgemeine Konsistenzprüfung mit einer einzigen Eingabeaufforderung, ohne Sitzungs-ID oder Protokoll erforderlich, die Ihre Konfiguration und eine Stichprobe der letzten Sitzungen aggregiert.

## Voraussetzungen

<!-- FLAG: General access prerequisite is inferred, not stated explicitly in source docs. Per-mode inputs (session ID, log file) are directly sourced from Functional Requirements. -->

### Erforderliche Informationen

Zur Validierung Ihrer Implementierung von Streaming-Medien benötigen Sie Folgendes:

* Zugriff auf Coworker mit den verbundenen Adobe Experience Platform- und Customer Journey Analytics-Daten Ihres Unternehmens.

* Für eine Sitzungs-ID-Validierung die Video-Sitzungs-ID, die Sie überprüfen möchten.

* Für eine protokollbasierte Validierung, eine Charles- oder HAR-Protokolldatei oder eine einfachere URL-Liste im .txt-, .md- oder .json-Format.

Für einen Konfigurationsaudit oder eine allgemeine Konsistenzprüfung ist keine spezielle Eingabe erforderlich. Ein Mitarbeiter liest Ihre vorhandene Konfiguration und die Beispiele der letzten Sitzungen automatisch.

### Einschränkungen

Bevor Sie diese Fähigkeit verwenden, beachten Sie Folgendes:

* **Nur Diagnose**: Diese Fähigkeit behebt weder Ihre Konfiguration noch Ihre Daten. Es identifiziert Probleme; Sie nehmen die Änderung vor.
* **Nur Streaming-Medien**: Diese Qualifikation umfasst Implementierungen von Streaming-Medien auf der Edge Network. Nicht-Medien-Datensätze und standardmäßige Web- oder App-Analytics-Implementierungen werden von anderen Validierungsfähigkeiten von Mitarbeitern abgedeckt.
* **Nur On-Demand**: Diese Fähigkeit bietet keine Echtzeit- oder kontinuierliche Überwachung. Führen Sie sie aus, wenn Sie eine Prüfung wünschen, anstatt als laufende Warnhinweise.
* **Keine integrierte Crawler**: Mit dieser Fähigkeit wird Ihre Site oder Ihr Programm nicht für Sie crawlen. Wenn Sie die Abdeckung wie crawlen überprüfen möchten, stellen Sie die Crawler- oder Headless-Browser-Ausgabe als Beweis bereit.
* Nur **Edge Network-Implementierungen**: Ältere Implementierungspfade für Media SDK und Analytics werden nicht unterstützt.
* **Umfassendere Funktionen sind noch nicht enthalten**: Für spätere Versionen sind die Validierung von Live-Ereignissen und Heartbeat-Streams, die Validierung von Kunden-Playbooks oder -Szenarien, eine plattformübergreifende historische Dashboard-Datenaggregation und die nachgelagerte Validierung der Real-Time CDP- oder Adobe Journey Optimizer-Aktivierung geplant.

## Starten einer Validierungssitzung

1. Melden Sie sich bei einem Kollegen an.

1. Wählen Sie [!UICONTROL **Neuer Chat**] aus.

1. Beschreiben Sie im Textfeld, was Sie validieren möchten. Beispiel:

   **Eingabeaufforderung**

   > Überprüfen Sie die #123 der Videositzung.

   Ihre Anfrage wird an die Validierungsfertigkeit für Streaming-Medien weitergeleitet, die den entsprechenden Validierungsmodus ausführt.

1. (Bedingt) Wenn für die Qualifikation weitere Informationen erforderlich sind, z. B. eine Sitzungs-ID oder eine Protokolldatei, geben Sie diese bei Aufforderung an.

## Validierungsmodus auswählen

Die Validierungsfertigkeit für Streaming-Medien umfasst vier Modi.

### Konfigurationsprüfung

Diese Funktion ist derzeit nur eingeschränkt verfügbar.

Validieren Sie den gesamten Adobe Experience Platform-Fluss vom Datenstrom bis zur Customer Journey Analytics-Datenansicht, einschließlich Ihres XDM-Schemas, Datensatzes und aller Datenvorbereitungsregeln oder von Customer Journey Analytics abgeleiteter Felder. Ein Mitarbeiter meldet eine Scorecard für Bestanden/Fehlschlagen pro Schritt und kennzeichnet den ersten fehlerhaften Checkpoint als die wahrscheinliche Ursache.

Beispiel-Eingabeaufforderungen:

* Überprüfen der Konfiguration von Streaming-Medien für Datenansicht, Datensatz und Datenstrom.
* End-to-End-Überprüfung der Konfiguration meiner Streaming-Medien
* Ist mein Media Analytics-Datenstrom für Customer Journey Analytics korrekt eingerichtet?

### Session-ID Validation

Überprüfen Sie die Adobe Experience Platform-Datensatzzeilen mit der Customer Journey Analytics-Datenansicht für eine bestimmte Videositzung und stellen Sie fest, ob eine Lücke ein Problem bei der Datensatzaufnahme oder ein Problem bei der Customer Journey Analytics-Zuordnung darstellt.

Beispiel-Eingabeaufforderungen:

* Überprüfen Sie die #123 der Videositzung.
* Warum wird die Sitzung abc-123 nicht in Customer Journey Analytics angezeigt?
* Vergleichen Sie Sitzung XYZ zwischen dem Datensatz und der Customer Journey Analytics-Datenansicht.

### Protokollbasierte Validierung

Diese Funktion ist derzeit nur eingeschränkt verfügbar.

Validieren Sie eine Sitzung über ein Charles- oder HAR-Protokoll, das Sie hochladen, oder über eine einfachere URL-Liste, ohne dass eine Live-Assurance-Sitzung erforderlich ist. Der Mitarbeiter validiert Endpunktmuster, Antwort-Codes, Ereignissequenzierung und Ping-Kadenz und gibt an, welche Prüfungen mit voller Konfidenz ausgeführt wurden, die Konfidenz verminderten oder übersprungen wurden.

Beispiel-Eingabeaufforderungen:

* Validieren der beigefügten Protokolle von Streaming-Mediendaten.
* In diesem Charles-Protokoll finden Sie die Sitzungs-ID #456.
* Validieren Sie diese URL-Liste anhand der erwarteten Medien-Pings.

### Validierungs-Dashboard

Abrufen einer allgemeinen Konsistenzprüfung mit einer einzigen Eingabeaufforderung. Ein Mitarbeiter aggregiert den Konfigurationsprüfungs- und einen schlanken, stichprobenartigen Sitzungscheck in einen Status und gibt explizit an, dass keine protokollbasierten Prüfungen ausgeführt wurden, wenn kein Protokoll bereitgestellt wurde.

Beispiel-Eingabeaufforderungen:

* Überprüfen Sie die Streaming-Mediendaten.
* Geben Sie mir einen Bericht über meine Implementierung von Streaming-Medien.
* Wie gesund ist meine Implementierung von Streaming-Medien insgesamt?

## Überprüfen der Ergebnisse

Jeder Modus gibt Ergebnisse in einem Format zurück, das für Ihre Validierung geeignet ist.

**Ergebnisse der Konfigurationsprüfung**

Eine Per-Hop-Pass/Fail-Scorecard, die Datenstrom, XDM-Schema, Datensatz, Customer Journey Analytics-Datenansicht und Datenvorbereitung oder abgeleitete Feldregeln abdeckt. Coworker identifiziert den ersten fehlgeschlagenen Sprung als wahrscheinliche Grundursache.

**Sitzungs-ID-Validierungsergebnisse**

Eine Zusammenfassung nur für Customer Journey Analytics, einschließlich Sitzungs-ID, Inhaltsmetadaten, Zeilenanzahl nach Ereignistyp, Schlüsselmetrikwerten und einer Integritätserklärung. Wenn eine Lücke besteht, identifiziert Coworker, ob es bei der Datensatzaufnahme oder beim Customer Journey Analytics-Zuordnungsschritt passiert ist.

>[!NOTE]
>
>Sitzungs-IDs und authentifizierte Identitätswerte sind standardmäßig aus jeder exportierten oder freigegebenen Zusammenfassung ausgeschlossen.

**Protokollbasierte Validierungsergebnisse**

Eine strukturelle und sequenzielle Validierung Ihres hochgeladenen Protokolls, die Endpunktmuster, Antwort-Codes, Ereignisreihenfolge und Ping-Kadenz umfasst. Der Mitarbeiter gibt an, welche Prüfungen mit voller Konfidenz ausgeführt wurden, welche mit reduzierter Konfidenz ausgeführt wurden und welche übersprungen wurden, je nachdem, ob Sie eine vollständige Protokollerfassung oder eine einfachere URL-Liste bereitgestellt haben.

**Dashboard-Ergebnisse**

Ein einziger konsolidierter Status mit der Bezeichnung „Konfiguration + verfügbare Daten“, der Ihre Ergebnisse der Konfigurationsprüfung mit einer Stichprobe von kürzlich durchgeführten Sitzungen kombiniert. Mitarbeiter benennen, welche Sitzungen abgefragt wurden, und geben explizit an, dass keine protokollbasierten Prüfungen ausgeführt wurden, da kein Protokoll bereitgestellt wurde.

## Funktionsweise der Validierung

Jeder Modus wird einer dedizierten Engine zugeordnet:

* **Konfigurationsvalidierungs-Engine**: Liest die Konfiguration Ihres Datenstroms, XDM-Schemas, Datensatzes und der Customer Journey Analytics-Datenansicht und wertet sie anhand eines festen Satzes von Checkpoints aus.
* **Session Cross-Check-Engine**: Bei einer Sitzungs-ID werden Ihr Datensatz und die Customer Journey Analytics-Datenansicht abgefragt, die erwartete Zeilenanzahl und der erwartete Typ für diese Sitzung berechnet und die tatsächlichen Ergebnisse bei jedem Sprung verglichen.
* **Log Parser und Validator**: Analysiert die hochgeladene Protokoll- oder URL-Liste, rekonstruiert die Anfragesequenz und das Timing und wendet Struktur-, Sequenzierungs- und Netzwerkschichtprüfungen an.
* **Dashboard Aggregation Engine**: Führt die Konfigurationsvalidierungs-Engine und einen Beispiellauf der Sitzungs-Cross-Check-Engine aus und kombiniert sie in einem einzigen Status, wenn Sie keine Sitzungs-ID, kein Protokoll oder kein Playbook angegeben haben.
