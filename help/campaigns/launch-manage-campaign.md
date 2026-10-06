---
description: Erfahren Sie, wie Sie eine Kampagne starten, planen, wann und wie oft sie ausgeführt wird, und eine Live-Kampagne, die aktiv sendet, dauerhaft stoppen.
title: Starten und Verwalten einer Kampagne
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 2%
---
# Starten und Verwalten einer Kampagne {#launch-campaign}

Erfahren Sie nach der Erstellung Ihrer Kampagne, wie Sie sie starten, planen Sie den Ablauf und stoppen Sie sie bei Bedarf.

>[!AVAILABILITY]
>
>Launch Campaign ist derzeit nur für Benutzer in nordamerikanischen Regionen verfügbar.

## Starten einer Kampagne

1. Klicken Sie in Ihrer abgeschlossenen Kampagne auf **Überprüfen und starten**.

   >[!NOTE]
   >
   >Wenn etwas fehlt, wird ein Dialogfeld angezeigt, in dem Sie auflisten können, was Sie vervollständigen müssen. Nehmen Sie die Korrekturen vor und wählen Sie erneut **Überprüfen und starten** aus.

1. Nachdem die Kampagne die Bereitschaftsprüfung bestanden hat, wird das Launch-Dialogfeld geöffnet, in dem eine Vorschau der E-Mail und der Audience angezeigt wird.

1. Überprüfen Sie den im Dialogfeld angezeigten Zeitplan. Um sie zu ändern, verwenden Sie die Zeitplanoptionen, die unter [Bei Kampagnenstart planen](#schedule-when-a-campaign-launches) beschrieben sind, und klicken Sie dann auf **Speichern**.

1. Klicken Sie **abschließend auf** Kampagne starten“.

>[!NOTE]
>
>- Eine Kampagne kann nicht mit einer (nicht realen) Beispielzielgruppe, nicht geprüften E-Mail-Entwürfen oder nicht konfigurierten Versandeinstellungen gestartet werden.
>
>- Wenn Sie eine Kampagne planen, können Sie sie vor dem Launch dennoch bearbeiten. Es ist nicht erforderlich, in den Entwurfsmodus zu wechseln.

## Planen des Starts einer Kampagne {#schedule-when-a-campaign-launches}

Beim Start einer Kampagne können Sie genau den Zeitpunkt ihres Beginns auswählen: sofort, zu einem bestimmten Datum und zu einer bestimmten Uhrzeit in der Zukunft oder nach einem wiederkehrenden Zeitplan. Sie können auch zu einem späteren Zeitpunkt zurückkehren und den Zeitplan einer Kampagne ändern, die bereits gestartet oder geplant wurde.

### Voraussetzungen

Die Kampagne muss startbereit sein (alle erforderlichen Einstellungen sind abgeschlossen).

### Planen einer Kampagne beim Start

1. Klicken Sie in der Kampagne auf **Überprüfen und starten**.

1. Wählen Sie im Launch-Dialogfeld die Option Zeitplan aus:
   - **Jetzt**: Die Kampagne beginnt sofort nach dem Start mit dem Versand.
   - **Einmal planen** Wählen Sie ein künftiges **Startdatum** (Datum und Uhrzeit zusammen) aus.
   - **Wiederkehrend**: Wählen Sie eine **Häufigkeit** (täglich, wöchentlich oder monatlich) und eine Startzeit aus und legen Sie dann das Wiederholungsmuster fest (siehe Felder unten).

1. Wenn Wiederkehrend ausgewählt ist, wählen Sie aus, ob die Kampagne **Nie** oder **An einem Datum** endet, und wählen Sie gegebenenfalls ein Enddatum aus.

1. Bestätigen Sie, dass die Kampagne mit dem ausgewählten Zeitplan gestartet werden soll.

### Bearbeiten eines vorhandenen Zeitplans

1. Öffnen Sie die Kampagne und wechseln Sie zu ihren Einstellungen.

1. Suchen Sie den Abschnitt Zeitplan und wählen Sie die aktuelle Zeitplanübersicht aus.

1. Aktualisieren Sie den Zeitplan mithilfe der oben beschriebenen Optionen.

1. Speichern Sie die Änderung.

### Eingabefelder

| Feld | Beschreibung | Erforderlich? |
| --- | --- | --- |
| Zeitplanmodus | Auswahl von Jetzt, Zeitplan einmal oder Wiederkehrend | Ja |
| Startdatum | Datum und Uhrzeit des Starts der Kampagne (Zeitplanmodus) | Ja, einmal planen |
| Häufigkeit | Täglich, wöchentlich oder monatlich (wiederkehrender Modus) | Ja, für wiederkehrend |
| Startzeit | Tageszeit, zu der die wiederkehrende Kampagne sendet | Ja, für wiederkehrend |
| Wochentage | An welchen Tagen wird die Kampagne wiederholt? | Ja, für die wöchentliche Häufigkeit |
| Tag des Monats | An welchem Tag des Monats wird die Kampagne wiederholt | Ja, für die monatliche Häufigkeit |
| Kampagne beenden | Nie oder an einem bestimmten Enddatum | Ja, für wiederkehrend |

### Zu beachtende Punkte

- Wiederkehrende Kampagnen können so eingestellt werden, dass sie unbegrenzt oder bis zu einem bestimmten Enddatum ausgeführt werden. Einmalige und sofortige Kampagnen haben keine Enddatumsoption, da sie einmal ausgeführt werden.
- Die Planung unterstützt keine benutzerdefinierten Wiederholungsintervalle, wie „alle 2 Wochen“ oder „alle 3 Tage“. Auch relative monatliche Wiederholungen, wie „der zweite Montag des Monats“, werden nicht unterstützt.

## Stoppen einer Kampagne {#stop-campaign}

Sie können eine Kampagne, die aktiv sendet (eine „Live“-Kampagne), direkt über die Seite mit den Kampagnendetails stoppen.

>[!CAUTION]
>
>Das Stoppen einer Kampagne ist dauerhaft. Empfänger hören sofort auf, die Kampagne zu durchlaufen, und die Kampagne kann danach nicht fortgesetzt oder neu gestartet werden. Zum erneuten Senden müssen Sie eine neue Kampagne erstellen und diese starten.

<!--

### Prerequisites

- [NEEDS INPUT - to confirm with engineer: does stopping a campaign require a specific role or permission, or can any user with campaign access do this?]

-->

### Stoppen einer Kampagne

1. Öffnen Sie eine Kampagne, die derzeit live ist.

1. Klicken Sie in der Kopfzeile der Kampagnendetails auf **Kampagne stoppen**.

1. Klicken Sie zur Bestätigung auf **Stoppen**.
