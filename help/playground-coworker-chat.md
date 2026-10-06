---
title: Erste Schritte mit dem Coworker Chat im Playground
description: Erfahren Sie, wie Sie den Coworker Chat in Playground verwenden können, um zu erkunden, wie Aufforderungen in natürlicher Sprache Ihnen dabei helfen können, Ihre Arbeit zu lernen, zu untersuchen und zu verfeinern.
hide: true
autotag-review: '2026-09-02T16:21:52.199Z'
TQID: 'https://experienceleague.adobe.com/a-9nJwwe4TFdi0ljwyyHfVfz-VqHL5lQbtmkU5P1Axw'
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
    internal-label: CX Enterprise
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
    internal-label: Experience Platform
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fdddec33-c9cb-4459-b8b6-2664395a6f10
    internal-label: Real-Time Customer Data Platform
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: 9c3a4e5f-6d7b-4c8a-8e9f-1b2c3d4e5f6a
    internal-label: Datasets
  - id: a4a9911c-3a92-4f17-a7f9-fe2eb3235fef
    internal-label: Monitoring
  - id: a50ad69b-1331-40e9-b634-531a085a6a54
    internal-label: Identities
  - id: a9eb38d5-9d89-492f-af4e-b968a07f2d91
    internal-label: Permissions
  - id: abc02dd6-664f-446a-9aaa-675bc0f2fe4a
    internal-label: Sources
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: ba929a52-9339-4154-9487-317dc875a3c7
    internal-label: Use cases
  - id: d21bd11d-08df-4cd6-ad8f-cb59a09de5c0
    internal-label: Sandboxes
  - id: d2a6cbf4-df32-480f-909e-b42f66dcb9f0
    internal-label: Places
  - id: de9975b2-c43a-4287-9698-4f4cad92b83f
    internal-label: Schemas
  - id: ebefeaba-efa6-45e2-ae01-f6171cdb8d1e
    internal-label: Tier
  - id: eec185bd-7d60-4193-ba3f-da427569936a
    internal-label: Destinations
  - id: f5a6b7c8-5003-4003-9003-500000000003
    internal-label: Services
topic_v2:
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
    internal-label: Data quality
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '1671'
ht-degree: 4%
---
# Erste Schritte mit dem Coworker Chat in Playground

Verwenden Sie den Coworker Chat auf Playground, um zu erkunden, wie Aufforderungen in natürlicher Sprache Ihnen helfen können, Ihre Arbeit zu lernen, zu untersuchen und zu verfeinern. Playground bietet Beispielmöglichkeiten, um eine Konversation zu beginnen, damit Sie schnell verstehen können, was der Coworker Chat tun kann.

>[!IMPORTANT]
>
>Verwenden Sie Folgendes, um diese Übung abzuschließen:
>
>- Link: [ao.adobe.io](https://ao.adobe.io/)
>- Instanz: AEP GenAI - VA7
>- Sandbox: `fsi-box`

## KI-Coworker-Demo: [!DNL weBank] Kampagne zur Kreditkarten-Aktualisierung

In dieser Übung werden Real-Time CDP und Adobe Journey Optimizer behandelt.

Sie sind ein CX Enterprise-Stratege bei **[!DNL weBank]**, einem Unternehmen, das Finanzdienstleistungen nach dem Motto „Digital First“ anbietet. Verwenden Sie den KI-Mitarbeiter, um von Rohdaten zu einer Live-Kampagne zu wechseln - vollständig durch Konversation.

## Teil 1: Grundlegendes zu Ihrem Unternehmen

### 1.1 — Erhalten Sie die Lage des Landes

**Eingabeaufforderung**

> Geben Sie mir einen Überblick über meine Sandbox - wie viele Zielgruppen, Datensätze und Ziele habe ich?

**Erwartetes Ergebnis**

Worker gibt ein vollständiges Sandbox-Inventar in Sekunden zurück:

| Ressource | Anzahl |
| --- | --- |
| Zielgruppen | 21 |
| Datensätze | 30 |
| Schemata | 28 |
| Quellen | 3 |
| Ziele | 1 (Amazon S3) |
| Journeys | 0 |

### 1.2 — Welche Zielgruppen gibt es bereits?

**Eingabeaufforderung**

> Alle meine Audiences nach Größe sortieren

**Erwartetes Ergebnis**

Coworker listet 21 Zielgruppen nach Größe auf, von 8.012 Profilen bis 0:

| Kategorie | Zielgruppe | Profile |
| --- | --- | --- |
| Neigungswerte | Kreditkarten-Upgrade hoch | 1,195 |
| Neigungswerte | Mittel | 4,113 |
| Neigungswerte | Niedrig | 8,012 |
| Neigung zur Hypothek | Hoch | 1,233 |
| Neigung zur Hypothek | Mittel | 4,141 |
| Neigung zur Hypothek | Niedrig | 7,946 |
| Kontowertstufen | +500 K | 4,377 |
| Kontowertstufen | 250-500 K | 4,537 |
| Kontowertstufen | 100-250 K | 2,666 |
| Kontowertstufen | 50-100 K | 894 |
| Kontowertstufen | &lt;50K | 846 |
| Demografie | Weiblich | 6,719 |
| Demografie | Männlich | 6,601 |
| Geografie | Ostküste | 2,260 |
| Geografie | Westküste | 1,740 |
| Kanal-Opt-in | E-Mail | 6,597 |
| Kanal-Opt-in | SMS | 6,675 |
| Geburtstag | Geburtstag diesen Monat | 0 |
| Geburtstag | Innerhalb von 7 Tagen | 0 |
| Geburtstag | Heute | 0 |
| Geburtstag | Nächste 30 Tage | 0 |

Alle Geburtstags-Zielgruppen zeigen derzeit den Wert 0 an, da sie zeitabhängig sind.

### 1.3 — Welche Daten werden für diese Zielgruppen genutzt?

**Eingabeaufforderung**

> Welche Datensätze habe ich, die Kundendaten enthalten?

**Erwartetes Ergebnis**

Coworker identifiziert zwei wichtige Geschäftsdatensätze und zugehörige Systemdatensätze:

| Datensatz | Beschreibung |
| --- | --- |
| **weBank: CRM** | Kundenprofil-/Kontodaten (Profil + Identität aktiviert) |
| **weBank: Kundenaktionen** | Verhaltensereignisdaten (Profil + Identität aktiviert) |

Journey Optimizer-Systemdatensätze für Interaktionssignale umfassen E-Mail-Tracking, Push-Tracking, Einverständnis und Nachrichten-Feedback.

## Teil 2: Die richtigen Felder entdecken

### 2.1 — Kontowertfelder suchen

**Eingabeaufforderung**

> Welche Felder sind für den Kontowert oder Kontostand verfügbar?

**Erwartetes Ergebnis**

Der Mitarbeiter zeigt das Primärfeld und die zugehörigen Felder im Datensatz **weBank: CRM** an:

| Feld | Anmerkungen |
| --- | --- |
| `_aepgenai_va7.fsiBankAccountDetails.totalAccountValue` | Primäres Feld; wird in allen fünf Zielgruppen der Kontowertstufe verwendet |
| `numberOfAccounts` | Verwandtes Feld |
| `accountType` | Verwandtes Feld |
| `currentStatement` | Verwandtes Feld |
| `actionAmount` | Verwandtes Feld |

### 2.2 — Kreditkartenfelder suchen

**Eingabeaufforderung**

> Suchen nach Feldern, die sich auf den Kreditkarten- oder Kartentyp beziehen

**Erwartetes Ergebnis**

Der Mitarbeiter identifiziert diese Felder im Schema **weBank: CRM**:

| Feld | Beschreibung |
| --- | --- |
| `_aepgenai_va7.fsiBankAccountDetails.creditcardType` | Speichert den Kartentyp (Visa, MasterCard, AMEX) |
| `_aepgenai_va7.fsiBankAccountDetails.creditcardHolder` | Name des Karteninhabers |

### 2.3 — Geografische Felder

**Eingabeaufforderung**

> Gibt es ein Feld für das Heimatland oder die Region?

**Erwartetes Ergebnis**

Kollege identifiziert geografische Felder im Datensatz **weBank: CRM**:

| Feld | Anmerkungen |
| --- | --- |
| `homeAddress.state` | Abkürzung für US-Bundesstaat; wird verwendet in Lives on East Coast und Lives on West Coast |
| `homeAddress.stateProvince` | Auch gefunden |
| `homeAddress.region` | Auch gefunden |
| `placeContext.geo.stateProvince` | Auch gefunden |

## Teil 3: Finden der richtigen Zielgruppe für eine Reaktivierungskampagne

### 3.1 - Bitten Sie die KI, Ihnen bei der Suche nach der richtigen Zielgruppe zu helfen

**Eingabeaufforderung**

> Helfen Sie mir, die richtige Zielgruppe für eine Kreditkarten-Reaktivierungskampagne zu finden oder zu erstellen. Ich möchte Kunden ansprechen, die eine hohe oder mittlere Neigung zu einem Kreditkarten-Upgrade hatten, aber noch keine Maßnahmen ergriffen haben

**Erwartetes Ergebnis**

Coworker findet zwei mögliche Zielgruppen, die noch nie in einer Journey oder einem Ziel angesprochen wurden:

| Zielgruppe | Profile |
| --- | --- |
| Kreditkarten-Upgrade hoch | 1,195 |
| Kreditkarten-Upgrade Medium | 4,113 |

Empfohlene Optionen:

| Option | Ansatz |
| --- | --- |
| **A** | Beide direkt mit Journey-Verzweigung verwenden - aggressives Angebot für High, Nurture für Medium |
| **B** | Erstellen abgeleiteter Segmentsegmente mit Upgrade-Ausschlusslogik für ein saubereres Management |

Kombinierte Größe: ca. 5.308 Profile

### 3.2 — Zielgruppe mit hoher Genauigkeit erstellen

**Eingabeaufforderung**

> Erstellen Sie eine Zielgruppe von Kunden, die der Zielgruppe „Tendenzen: Kreditkarten-Upgrade - Hoch“ angehören UND einen Kontowert von über 250.000 USD haben UND für die E-Mail-Zustellung optiert sind.

Benennen Sie ihn **Platin-Upgrade - E-Mail mit hohem Wert geeignet** → wählen Sie einen Batch aus → genehmigen Sie einen Plan

**Erwartetes Ergebnis**

Mitarbeiter-Ebenen - ML-Neigung, finanzieller Wert und Kanaleignung in ein Präzisionssegment - Arbeit, für die normalerweise ein Daten-Team-Ticket erforderlich wäre.

### 3.3 — Geschätzte Größe und Wasserfall

**Eingabeaufforderung**

> Wie groß ist dieses Publikum? Zeigen Sie mir die Wasserfall-Aufschlüsselung.

**Erwartetes Ergebnis**

Coworker gibt eine Schätzung der Echtzeit-Profilanzahl und ein visuelles Wasserfalldiagramm zurück:

| Filterschritt | Ergebnis |
| --- | --- |
| Kreditkarten-Upgrade - Hohe Tendenz | Ca. 1.195 Profile |
| + Kontowert über 250.000 $ | Engt weiter ein |
| + E-Mail-Opt-in | Endgültige adressierbare Zählung |

Dies zeigt genau an, welche Bedingung der größte Filter ist und ob die Kriterien gelockert werden sollen.

### 3.4 — Auf ähnliche Zielgruppen prüfen

**Eingabeaufforderung**

> Gibt es bereits Audiences, die der soeben erstellten ähnlich sind?

**Erwartetes Ergebnis**

Mitarbeiter bestätigt, dass keine einzelne kombinierte Zielgruppe vorhanden ist, aber alle Bausteine bereits vorhanden sind:

| Baustein | Details |
| --- | --- |
| Tendenzen: Kreditkarten-Upgrade hoch | Ergebnis ≥ 90 |
| Kontowert: 250-500K | Vorhandene Zielgruppe |
| Kontowert: +500K | Vorhandene Zielgruppe |
| E-Mail-Opt-in | `consents.marketing.email.val = "y"` |

Mitarbeiter bestätigt, dass kein Duplikationsrisiko besteht, und empfiehlt, fortzufahren.

## Teil 4: Erstellen der Journey

### 4.1 - Journey-Ideen in Ihren Daten verankern

**Eingabeaufforderung**

> Basierend auf gängigen Anwendungsfällen in Finanzdienstleistungen, schlagen einige schnell gewinnende Journey vor, die ich mit den Zielgruppen erstellen kann, die ich habe

**Erwartetes Ergebnis**

Coworker schlägt fünf konkrete Journey-Ideen vor, die auf tatsächlichen Zielgruppen basieren:

| Journey Idee | Zielgruppen |
| --- | --- |
| Geburtstags-Treuekonzept | Geburtstag innerhalb von 7 Tagen + Kontowertstufen |
| Kreditkarten-Upgrade Nurture | CC-Upgrade hoch + E-Mail-Opt-in |
| Regionale Hypothekenkredite | Hypothek hoch + ost/westküste |
| Beratung zur Wealth Tier-Aktualisierung | Kontowert: +500K |
| Opt-in-Cross-Channel-Aktivierung | E-Mail-Opt-in ohne SMS-Opt-in |

### 4.2 — Erstellen der Kreditkarten-Upgrade-Journey

**Eingabeaufforderung**

> Erstellen Sie eine Journey mit der Zielgruppe „Platin-Upgrade - E-Mail mit hohem Wert geeignet“. Senden Sie eine Push-Benachrichtigung, in der die Vorteile der WeBank Platinum Card vorgestellt werden. Warte 3 Tage. Wenn der Kunde sich nicht beworben hat, senden Sie eine SMS mit einem zeitlich begrenzten Angebot von 0% APR für 12 Monate auf Saldoübertragungen. Noch 5 Tage warten. Wenn Sie immer noch keine Anwendung haben, senden Sie eine endgültige Push-Benachrichtigung mit einer persönlichen Bankeinladung.

Plan prüfen → Plan genehmigen → Berechtigungen erteilen

**Erwartetes Ergebnis**

Coworker erstellt eine vollständige 3-Touch-Journey mit zwei Kanälen aus einer einzigen natürlichen Sprachbeschreibung, einschließlich Wartezeiten, Zustandsprüfungen und eskalierenden Angeboten.

### 4.3 — Bonus: Erstellen einer Journey aus einem Bild

**Eingabeaufforderung**

> Erstellen Sie diese Journey aus dem hochgeladenen Bild

**Erwartetes Ergebnis**

Coworker liest das hochgeladene Bild - einschließlich Knoten, Kanälen, Wartezeiten und Bedingungen - und generiert die vollständige Journey in Journey Optimizer. Dadurch wird aus einem Planungsartefakt direkt eine bereitstellbare Journey.

### 4.4 — Prüfung auf Konflikte

**Eingabeaufforderung**

> Gibt es aktive Journey, die mit der soeben erstellten Journey in Konflikt stehen könnten?

**Erwartetes Ergebnis**

Der -Mitarbeiter prüft automatisch alle aktiven Journey auf Zielgruppenüberschneidungen, Zeitplankollisionen und Kanalsättigung.

## Teil 5: Verwandeln von Journey-Abbrüchen in eine neue Zielgruppe

### 5.1 — Angabe des Rückfallpunktes

**Eingabeaufforderung**

> Zeigen Sie mir die Journey, die ich gerade erstellt habe, und identifizieren Sie, welcher Schritt den größten Abbruch hat

**Erwartetes Ergebnis**

Der Mitarbeiter analysiert Journey-Schrittereignisse und zeigt den Knoten mit der höchsten Abbruchrate an. Beispiel:

> 68 % der Profile, die die erste E-Mail erhalten haben, haben sie nie geöffnet und sind vor dem SMS-Schritt gegangen.

### 5.2 — Erstellen einer Ablagezielgruppe

**Eingabeaufforderung**

> Machen Sie aus diesen Journey-Abbrüchen eine neue Zielgruppe - Personen, die die Platinum Upgrade Journey betreten, aber nie den SMS-Schritt erreicht haben

Benennen Sie ihn **Platin-Upgrade - E-Mail-** - → wählen Sie Batch → genehmigen Plan

**Erwartetes Ergebnis**

Ein Mitarbeiter erstellt auf der Grundlage von Journey-Verhaltensdaten eine neue Zielgruppe - Profile, die auf die Journey gelangt sind, aber nicht zum SMS-Schritt weitergeleitet wurden. Diese Zielgruppe kann sofort für eine Folgekampagne verwendet werden.

### 5.3 — Reaktivieren der Abgänge

**Eingabeaufforderung**

> Erstellen Sie eine Reaktivierungs-Journey für die Zielgruppe „Platinum Upgrade - E-Mail Non-Responders“. Probieren Sie einen anderen Ansatz aus: Beginnen Sie mit einer Push-Benachrichtigung, die ein zeitlich begrenztes Angebot von 75.000 Bonuspunkten hervorhebt, warten Sie 2 Tage und senden Sie dann eine Briefpost-Einladung, um die lokale Filiale zu besuchen.

Plan prüfen → Plan genehmigen → Berechtigungen erteilen

**Erwartetes Ergebnis**

Coworker erstellt eine dedizierte Recovery-Journey mit verschiedenen Kanälen und Messaging für Non-Responder. Sie haben nun den Kreislauf geschlossen wegen eines Konversionslecks — komplett durch Konversation.

## Teil 6: Automatisierte QS und Validierung

### 6.1 — Prüfung der Datenfrische und des Aufnahmezustands

**Eingabeaufforderung**

> Gibt es Probleme mit der Datenqualität bei den Datensätzen, die meine Zielgruppen befüllen? Prüfen des Aufnahmestatus für WeBank: CRM und WeBank: Kundenaktionen

**Erwartetes Ergebnis**

Worker meldet den Aufnahmestatus für jeden Datensatz:

| Datensatz | Status | Details |
| --- | --- | --- |
| **weBank: CRM** | Fehlerfrei | 39 Datensätze aufgenommen, 32 in Profil, keine Fehler |
| **weBank: Kundenaktionen** | Nebenflagge | 441 Datensätze wurden aufgenommen, 35 waren abgelaufen, ca. 8 % aufgrund des TTL-Fensters ausgeschlossen |

Empfehlung: Überprüfen Sie die TTL-Einstellungen oder überprüfen Sie das Quellsystem auf veraltete Datensätze.

### 6.2 — Journey vor der Veröffentlichung validieren

**Eingabeaufforderung**

> Überprüfen Sie die Platin-Upgrade-Journey auf Fehler oder Qualitätsprobleme - prüfen Sie auf fehlende Wartezeiten, Sackgassen-Pfade, fehlende Kanalkonfigurationen und Lücken in der Zielgruppenberechtigung.

**Erwartetes Ergebnis**

Der Mitarbeiter überprüft die Journey-Struktur und kennzeichnet beispielsweise folgende Probleme:

| Anfragetyp | Beispiel |
| --- | --- |
| Sackgassen-Pfade | Pfade, die nicht mit einem Endknoten enden |
| Kanalkonfiguration | Aktionen ohne Konfigurationen der Kanaloberfläche |
| Wartezeiten | Zeitgeber, die SLA-Probleme verursachen können |
| Inhalte | Knoten mit fehlendem Inhalt |

## Teil 7: Überwachung und Governance

### 7.1 - Verfolgen der Zielgruppenkonsistenz im Zeitverlauf

**Eingabeaufforderung**

> Zeigen Sie mir, wie sich die Zielgruppe „Tendenzen: Kreditkarten-Upgrade - Hoch“ in den letzten 30 Tagen geändert hat

**Erwartetes Ergebnis**

Ein Mitarbeiter gibt mithilfe der Trendanalyse eine Zeitreihenansicht des Zielgruppenwachstums oder -rückgangs zurück, mit der Sie ermitteln können, ob die Bewertung des ML-Modells nachlässt oder ob sich vorgelagerte Datenänderungen auf die Qualifizierung auswirken.

### 7.2 — Diagnose einer Änderung

**Eingabeaufforderung**

> Warum ist die Zielgruppe „Kontowert: +500K“ in letzter Zeit gesunken?

**Erwartetes Ergebnis**

Ein Mitarbeiter führt eine Kausalanalyse durch, indem er die Änderung wie folgt aufteilt:

| Faktor | Question |
| --- | --- |
| Aktualität der Daten | Gab es eine Aufnahmelücke? |
| Änderungen an Zusammenführungsrichtlinien | Hat sich die Profilzuordnung geändert? |
| Upstream-Quelländerungen | Haben CRM-Daten aufgehört zu fließen? |
| Tatsächliches Kundenverhalten | Sind die Kontowerte wirklich gesunken? |

Dies ersetzt 1-2 Tage Analyst-Triage.

