---
description: Erfahren Sie mehr über Coworker-Kampagnen mit Best Practices - das CO-STAR-Framework, Aufgaben und Aufgaben, nicht unterstützte Inhalte und eine Qualitätsprüfliste für Eingabeaufforderungen.
title: Best Practices für das Prompting
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: ee66c1cc95ef1dd8c5e45c1fcb699547e63b9c8a
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 23%
---
# Best Practices bei der Eingabeaufforderung {#best-practices}

Die optimale Nutzung von Coworker-Kampagnen beginnt damit, wie Sie eine Eingabeaufforderung eingeben. Erfahren Sie mehr über die Praktiken, die die besten Ergebnisse erzielen: das CO-STAR-Framework zur Strukturierung Ihrer Eingabeaufforderungen, einzuschließende und zu vermeidende Maßnahmen sowie Szenario-basierte Beispiele, die der KI den Kontext geben, den sie benötigt, um relevante, zielgerichtete Inhalte zu generieren.

>[!NOTE]
>
>Derzeit können Sie nur eine Verbindung zu Integrationen herstellen, die von Adobe Campaign unterstützt werden. Wenn Sie bereits über Adobe Enterprise-Anwendungen verfügen, in denen Sie Zielgruppen speichern oder Journey erstellen, empfehlen wir Ihnen, stattdessen [CX Enterprise Coworker](/help/chat/use-cases/overview.md) zu verwenden.

## Verwenden des CO-STAR-Frameworks

Um optimale Ergebnisse zu erzielen, sollten Sie die Eingabeaufforderungen mit dem CO-STAR-Framework organisieren. Dieser strukturierte Ansatz stellt sicher, dass die KI genau versteht, was Sie benötigen.

| Komponente | Bedeutung | Warum dies wichtig ist |
|-|-|-|
| **C – Kontext** | Hintergrund zur Kampagne, zum Produkt oder zur Situation | Hilft der KI, das Gesamtbild zu verstehen |
| **O – Ziel** | Ihr spezifisches Marketing-Ziel | Gibt an, was mit dem Inhalt erreicht werden soll |
| **S – Stil** | Gewünschte Art der Kommunikation | Legt den Ansatz fest |
| **T – Ton** | Die Emotion von Stil und Sprache | Gestaltet das Gefühl Ihrer Nachricht |
| **A – Zielgruppe** | Die angesprochene Zielgruppe | Stellt sicher, dass die Nachricht bei den richtigen Personen Anklang findet |
| **R – Anforderungen** | Spezifische Einschränkungen oder unverzichtbare Komponenten | Definiert Grenzen und kritische Elemente |

## Grundlagen der KI-Eingabeaufforderung

### Worauf Sie achten müssen

<table style="table-layout: fixed; width: 100%; border: 0;">
<thead style="border: 0; background-color: #FFFFFF;">
<tr>
<th>Empfohlen</th>
<th>Zu vermeiden</th>
</tr>
</thead>
<tbody>
<tr style="border: 0;">
<td>
<p>CO-STAR-Framework zur Strukturierung verwenden</p>
<p>Fokus auf Marketing-Briefs mit spezifischer Extraktionsanleitung</p>
<p>Formulieren Sie Ihre Eingabeaufforderungen, um die gewünschte Absicht zu erreichen</p>
</td>
<td>
<p>In Prompts Strukturänderungen, Formate oder Bildbearbeitung anfordern</p>
<p>Verwenden Sie vage Anweisungen wie „unser Produkt bewerben“</p>
<p>Layout-Änderungen über Prompts erwarten</p>
</td>
</tr>
</tbody>
</table>

### In Eingabeaufforderungen unterstützte Inhalte

Verwenden Sie den **E-Mail-Editor** oder **Adobe Express** für Änderungen an visuellen Komponenten/Bildern. Die folgenden Anfragetypen werden unterstützt.

- **Geben Sie die Häufigkeit und die Kadenz Ihrer Kampagne an**: „Erstellen Sie eine E-Mail-Kampagne, die wöchentlich gesendet wird …“

- **Targeting einer bestimmten Zielgruppe aus einer größeren Liste**: „Erstellen Sie eine Kampagne nur für Teilnehmer mit Hunden für das _Rinde im Park_-Ereignis von &#39;all-attendees.csv&#39;&quot;

- **HTML-Datei hochladen**: „Verwenden Sie meine angehängte HTML-Datei als Grundlage für die Erstellung einer E-Mail-Kampagne.“

- **Änderungen während der Konversation vornehmen**: „Ändern Sie die Anzahl der Tage vor dem Start dieser Kampagne von zwei auf drei.“

### In Prompts nicht unterstützte Inhalte

Diese Anfragen werden **nicht** unterstützt und sollten über andere Tools verarbeitet werden:

<table style="table-layout: fixed; border: 0;">
<thead style="border: 0; background-color: #FFFFFF">
<tr>
<th>✗ Änderungen an der E-Mail-Struktur</th>
<th>✗ Änderungen am visuellen Stil</th>
<th>In-Editor-Vorgänge ✗</th>
</tr>
</thead>
<tbody>
<tr style="border: 0;">
<td>
<ul>
<li>Auswählen bestimmter zu ändernder Abschnitte</li>
<li>Löschen oder Klonen von Elementen</li>
<li>Bedingte Auswahlen</li>
<li>Hinzufügen oder Entfernen von Layout-Abschnitten</li>
</ul>
</td>
<td>
<ul>
<li>Benutzerdefinierte Schriftarten</li>
<li>Farbänderungen</li>
<li>Layout-Stile (Rahmen, Abstände, Ränder)</li>
<li>Visuelle Effekte (Schatten)</li>
</ul>
</td>
<td>
<ul>
<li>Hintergrundänderungen</li>
<li>Hinzufügen von Textüberlagerungen oder Logos</li>
<li>Beschneiden oder Ändern der Größe von Bildern</li>
<li>Farbkorrekturen</li>
</ul>
</td>
</tr>
</tbody>
</table>

### Qualitäts-Checkliste

Stellen Sie vor dem Generieren von Inhalten Folgendes sicher:

✓ **Eindeutiges Ziel**: Gibt die Aktion, das Produkt/die Dienstleistung, den Wert und den Kontext klar an.

✓ **Definierte Zielgruppe**: Gibt die Demografie, die Rolle oder das Segment an.

✓ **Die korrekte Markenbezeichnung ist**. Es werden die entsprechenden Markenrichtlinien ausgewählt.

✓ **Realistischer Umfang**: Vermeiden Sie Anfragen zu Layout-Änderungen, Stilen oder strukturellen Bearbeitungen.

## Szenariobasierte Eingabeaufforderungsbeispiele

Geben Sie immer den Kontext und das Wertversprechen an, damit die KI relevante Inhalte generieren kann.

>[!NOTE]
>
>Obwohl Sie derzeit nur E-Mail-Kampagnen generieren und starten können, können Sie Ihren Kollegen jederzeit bitten, eine Kopie für Social Media, WhatsApp oder SMS zu generieren.

<table style="table-layout: fixed; border-collapse: collapse; border: 0;">
<thead>
<tr style="border: 0;background-color: #FFFFFF;">
<th>Branche</th>
<th>Prompt-Beispiel</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>B2B-Technologie</strong></td>
<td>„Erstellen Sie eine Vier-Touch-E-Mail-Kampagne, um den ROI und technische Spezifikationen zu demonstrieren und gleichzeitig Sicherheitsbedenken für IT-Entscheidungsträger zu adressieren, die unsere Cloud-Infrastrukturlösung bewerten. Hervorgehoben werden 99,9 % Verfügbarkeit von SLA, SOC 2-Konformität und 40 % Kosteneinsparungen.“</td>
</tr>
<tr>
<td><strong>E-Commerce – Einzelhandel</strong></td>
<td>„Generieren Sie eine Single-Touch-Kampagne, um Dringlichkeit für Urlaubsartikel mit begrenztem Lagerbestand zu schaffen und gleichzeitig den kostenlosen Versand und die einfache Rückgabe für Last-Minute-Käufer hervorzuheben, wobei Sie begrenzte Mengen (weniger als 50 verbleibende) und den 24-Stunden-Versand-Stichtag betonen.“</td>
</tr>
<tr>
<td><strong>Allgemeine und berufliche Bildung</strong></td>
<td>„Erstellen Sie eine Kampagne mit zwei Kontakten, die auf Karriereverbesserungsergebnissen und Branchenzertifizierungen basiert und gleichzeitig das Know-how der Kursleiter präsentiert, eine Stellenbesetzungsquote von 92 % hervorhebt und einen projektbasierten Lehrplan erstellt.“</td>
</tr>
<tr>
<td><strong>Beratung</strong></td>
<td>„Erstellen Sie eine Drei-Touch-Kampagne zur Förderung von Unternehmensperspektiven, indem Sie drei Kundenerfolgsgeschichten mit detaillierten ROI-Metriken präsentieren (IBM: 45 % Kostensenkung, Accenture: 200 % Lead-Steigerung, Microsoft: 60 % Zeitersparnis), die sich an IT-Direktoren in Unternehmen mit mehr als 1000 Mitarbeitern richtet.“</td>
</tr>
</tbody>
</table>

## Ideen für allgemeine Marketing-Eingabeaufforderungen

### Content-Marketing

- „Generieren Sie 20 Blog-Themen, die häufig gestellte Fragen von Erstkäufern von Privathaushalten beantworten.“
- „Brainstorm über LinkedIn-Post-Ideen für ein B2B-Cybersecurity-Startup.“
- „Erstellen Sie einen dreimonatigen Inhaltskalender, der sich auf die Schulung von Neukunden konzentriert.“
- „Schlagen Sie Inhaltsthemen vor, die in Blogs, Videos, Newslettern und Social-Media-Beiträgen wiederverwendet werden können.“

### E-Mail-Marketing

- „Erstellen Sie eine Begrüßungs-E-Mail-Sequenz für neue Abonnentinnen und Abonnenten, die an nachhaltiger Mode interessiert sind.“
- „Brainstorming-Betreffzeilen, die Neugier erzeugen, ohne wie Klick-Köder zu klingen.“
- „Vorschläge für Kampagnentideen zur Rückgewinnung von Interaktionen für inaktive Kunden.“
- „Erstellen Sie Lebenszyklus-E-Mail-Ideen für Benutzer, die das Onboarding abgeschlossen haben.“

>[!MORELIKETHIS]
>
>Durchsuchen Sie mehr [Eingabeaufforderungsmuster](use-cases.md) für Kollegen-Kampagnen.
