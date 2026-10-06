---
title: Erstellen und Ausführen einer Quality Gate-Qualifikation in einem Kollegen
description: Erfahren Sie, wie Sie mit benutzerdefinierten Fähigkeiten von Kollegen Zielgruppenaktivierungen vor der Bereitstellung automatisch anhand von Unterdrückungslisten, Frequenzbegrenzungen und Benennungsstandards validieren können.
role: User
level: Beginner, Intermediate
doc-type: Feature Video
duration: 101
last-substantial-update: 2026-09-08
jira: KT-22379
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 1%
---

# Erstellen und Ausführen einer Quality Gate-Qualifikation mithilfe benutzerdefinierter KI-Fähigkeiten

Marketing-Teams verlassen sich auf Regeln und Governance-Prozesse, um sicherzustellen, dass Zielgruppen korrekt aktiviert werden. Bevor eine Zielgruppe an ein Ziel gesendet wird, müssen Teams häufig Unterdrückungslisten, Häufigkeitsbegrenzungen, Einverständnisanforderungen und Namenskonventionen überprüfen.
 
Die Herausforderung besteht darin, dass diese Kontrollen häufig auf dem Wissen der Stämme und manuellen Überprüfungen beruhen. Wenn Prozesse in den Köpfen der Menschen leben, können Fehler passieren.

In diesem Video erfahren Sie, wie benutzerdefinierte Kollegen als Aktivierungs-Gate fungieren und Zielgruppen automatisch anhand der Aktivierungsstandards Ihres Unternehmens validieren, bevor sie nachgelagert werden.

>[!VIDEO](https://video.tv.adobe.com/v/3503162/?learn=on&enablevpops)

## Beispiel-Aktivierungs-Qualitäts-Gate-Kenntnisse
 
Sie können Ihre eigene wiederverwendbare **Activation Quality Gate**-Kompetenz erstellen, indem Sie eine Eingabeaufforderung in den -Mitarbeiter einfügen. Die Fähigkeiten-Authoring-Funktionen von Kollegen konvertieren die Eingabeaufforderung in eine gespeicherte Kenntnis in **Ihrer eigenen Umgebung**. Es folgt ein Beispiel auf der Grundlage der Videodemonstration.
 
Entscheidend ist die Definition **Ihrer eigenen Pass/Fail-Standards** für die drei Governance-Akzeptanztests:
 
1. Unterdrückung/Einverständnis
2. Frequenzlimitierung
3. Namenskonvention
 
Der Rahmen bleibt für alle gleich. Passen Sie die mit **`[...]`** gekennzeichneten Abschnitte an die Standards Ihrer Organisation an.

## Master-Eingabeaufforderung

> **Speichern Sie dies als eine Fähigkeit namens „Activation Quality Gate“.**

```text
It's a governance gate that runs a pre-activation checklist before any audience is sent to a destination.

It is read-only. It never activates, mutates, or copies anything.

Resolve the named audience and destination from our Knowledge Graph, evaluate the three gates below, then render one visual scorecard containing:

- An Alert banner
- One MetricCard per gate
- A DataTable with:
- Gate
- Status
- Finding
- Required Fix

Provide a single verdict:

- CLEARED only if all three gates pass
- BLOCKED if any gate fails

For every failed gate, provide the specific remediation needed.
 
All gates fail closed:

- Missing data = BLOCKED
- Never assume success when information is unavailable
 
Trigger phrases:

- "run the activation gate"
- "is this audience ready to activate"
- "pre-activation checklist"
- "can I activate to ..."

The three gates are:
 
[Paste Gate 1, Gate 2, and Gate 3 definitions here]
```

## Tor 1: Unterdrückung/Einverständnis
 
> Bearbeiten Sie diesen Abschnitt entsprechend den Unterdrückungs- und Einverständnisanforderungen Ihrer Organisation.
 

```text
Gate 1 – Suppression List

Pass only if a recognized suppression, opt-out, or consent audience is applied alongside the target audience.

Discover eligible lists using name patterns such as:

- suppress
- opt-in
- opt out
- consent
- do not contact
 
Because suppression lists may live in destination dataflows rather than audience metadata, require the marketer to confirm one is attached.
 
If no suppression or consent list exists anywhere in the sandbox, fail hard.
 
Our standard:

[Example: A consent audience is mandatory for all email and SMS destinations. For direct mail destinations it is optional.]
```

## Gatter 2: Frequenzbegrenzung

> Bearbeiten Sie diesen Abschnitt entsprechend den Häufigkeitsanforderungen für Sendungen Ihrer Organisation.

```text
Gate 2 – Frequency Cap
 
Read the delivery frequency on the resolved destination.

Pass if:

- Frequency is present
- Frequency is bounded

Fail if:

- Frequency is blank
- Frequency is unbounded

Our standard:

[Example: Frequency must be DAILY or less frequent. Any hourly cadence or blank value is blocked.]
```

## Gatter 3: Namenskonvention
 
> Passen Sie diesen Abschnitt an die Benennungsregeln Ihrer Organisation an.
 

```text
Gate 3 – Naming Convention

Evaluate the audience name programmatically.

Any rule violation causes failure.

Block names that:

- Contain "test"
- Contain "copy"
- Contain an auto-copy suffix such as _[6-hex]
- Contain timestamps
- Contain 24-character object IDs
- Start with a bare number or cryptic short code
- Are entirely lowercase
- Are excessively short or unclear
- Use generic defaults such as:
- Save audience
- Email
- New Accounts
- Lack a category–qualifier separator

Our standard:

[Example: [Line of Business] – [Criteria] in title case]

Example:

Mortgage – High Propensity Prospects

When blocked on naming, always propose a compliant replacement name.
```

## Leitlinien

### &#x200B;1. Nur die in Klammern eingeschlossenen Abschnitte anpassen

Nur die in **`[...]`** enthaltenen Abschnitte aktualisieren.
 
In diesen Abschnitten werden die spezifischen Governance-Standards des Unternehmens definiert.
 
Alles andere sollte unverändert bleiben:

- Zielgruppenauflösung
- Gate-Auswertung
- Scorecard-Rendering
- Urteilslogik


### &#x200B;2. Voraussetzungen überprüfen
 
Diese Qualifikation hängt von Folgendem ab:
 
- Zugriff auf Wissensdiagramme
- Zielgruppenerkennung
- Zielerkennung
- Erkennung der Unterdrückungsliste
- Unterstützung visueller Artefakte
- Warnhinweis-Banner
- Metrikkarten
- DataTable-Rendering

Wenn diese Funktionen in der Umgebung des Kunden nicht verfügbar sind, kann die Kenntnisse nicht wie vorgesehen ausgeführt werden.

### &#x200B;3. Qualifikation schreibgeschützt beibehalten

Die Kenntnisse sollten immer schreibgeschützt bleiben.

Schließen Sie diese Anforderung explizit in die Eingabeaufforderung ein, um sicherzustellen, dass die Kenntnisse nie mit einem Aktivierungs-Workflow verwechselt werden.

Das Activation Quality Gate bewertet nur die Aktivierungsbereitschaft. Zielgruppen **nicht aktiviert** Konfigurationen geändert oder Daten kopiert.
