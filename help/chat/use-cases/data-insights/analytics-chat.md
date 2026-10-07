---
title: Erste Schritte mit dem Analysieren von Daten mit dem Coworker Chat
description: Erfahren Sie, wie Sie mit dem Adobe CX Enterprise Coworker-Chat Customer Journey Analytics-Daten analysieren, Trichter erstellen und herausfinden können, wo Kundinnen und Kunden auf der Journey abbrechen.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '2094'
ht-degree: 5%
---
# Erste Schritte mit der Datenanalyse mit dem Coworker Chat

Richten Sie Adobe CX Enterprise Coworker Chat ein, um Ihre Customer Journey Analytics-Datenansichten oder Adobe Analytics Report Suites zu analysieren, und folgen Sie dann einem Arbeitsbeispiel. Einen Überblick darüber, was Sie mit dem Coworker Chat tun können, einschließlich Anwendungsfällen, Fähigkeiten und Best Practices, finden Sie unter [Analysieren von Daten mit dem Coworker Chat](/help/chat/use-cases/data-insights/analytics-overview-v2.md).

Bevor Sie beginnen, machen Sie sich mit der Oberfläche und den Konfigurationsoptionen des Coworker Chat vertraut und stellen Sie dann sicher, dass Coworker mit Customer Journey Analytics oder Adobe Analytics und den relevanten Datenansichten oder Report Suites verbunden ist.

## Voraussetzungen

### Datenzugriff und Berechtigungen

Der Coworker Chat erbt Berechtigungen von Customer Journey Analytics oder Adobe Analytics. Sie können nur auf die Datenansichten, Report Suites, Dimensionen, Metriken und Segmente zugreifen, die Ihnen in Analysis Workspace zur Verfügung stehen.

### Schnittstellen- und Konfigurationsoptionen

Bevor Sie den Coworker Chat mit Ihren Customer Journey Analytics- oder Adobe Analytics-Daten verwenden, erfahren Sie, wie Sie sich anmelden und Konfigurationsoptionen für die folgenden Funktionen verwalten können:

* Chat-Eingaben
* Konversationen
* Marketplaces
* MCP-Server
* Speicher
* Plug-ins
* Skills
* Und mehr

Weitere Informationen finden Sie im [Handbuch zur Benutzeroberfläche für den Coworker-Chat](/help/chat/ui-guide.md).

## Überprüfen, ob der Coworker Chat mit Customer Journey Analytics verbunden ist

Stellen Sie im Coworker Chat sicher, dass Coworker mit Customer Journey Analytics verbunden ist:

1. Wählen Sie das MCP-Symbol in der linken Leiste aus und stellen Sie sicher, dass [!UICONTROL **cja-**]) in Ihrer Liste der verbundenen MCP-Server verfügbar ist.

   ![Das hervorgehobene MCP-Symbol in der linken Leiste „Mitarbeiter“](../../assets/coworker-mcp-cja.png)

1. (Bedingt) Wenn [!UICONTROL **cja-mcp**] noch nicht verbunden ist, wählen Sie [!UICONTROL **MCP-Server hinzufügen**], geben Sie cja im Feld [!UICONTROL **Server-Name**] an und wählen Sie es aus, wenn es angezeigt wird. Wählen Sie dann [!UICONTROL **Server hinzufügen**].

## Herstellen einer Verbindung zur richtigen Datenansicht oder Report Suite

Eine Datenansicht ist ein Container in Customer Journey Analytics, der bestimmt, wie Daten interpretiert werden. Eine Report Suite ist ein Container in Adobe Analytics, der die Daten enthält, die von Ihren Sites und Programmen erfasst werden.

Möglicherweise haben Sie Zugriff auf verschiedene Datenansichten in Customer Journey Analytics oder Report Suites in Adobe Analytics. Jeder Knoten kann verschiedene Dimensionen und Metriken enthalten, die Coworker bei der Datenanalyse verwenden kann.

### Festlegen, welche Datenansichten oder Report Suites Sie verwenden möchten

Teilen Sie Ihrem Mitarbeiter die Arten von Fragen mit, die Sie beantwortet haben möchten, und fragen Sie ihn, auf welche Datenansichten oder Report Suites Sie Zugriff haben, die diese Informationen bereitstellen. Sie können auch [Datenansicht oder Report Suite als Voreinstellung im Speicher festlegen](#add-a-data-view-or-report-suite-preference-in-memory).

**Sie:**

>[!BEGINSHADEBOX]

Ich bin daran interessiert zu erfahren, wo Kunden auf der Kunden-Journey abbrechen. Auf welche Datenansichten in Customer Journey Analytics habe ich Zugriff, die diese Frage für mich beantworten können?

>[!ENDSHADEBOX]

**Chat-Antwort eines Kollegen:**

>[!BEGINSHADEBOX]

Sie haben Zugriff auf drei Datenansichten. Die `Customer lifecycle` Datenansicht enthält die folgenden Dimensionen und Metriken, die am besten für die Beantwortung Ihrer Frage geeignet sind.

>[!ENDSHADEBOX]

**Sie:**

>[!BEGINSHADEBOX]

Toll, verwenden wir diese Datenansicht.

>[!ENDSHADEBOX]

**Chat-Antwort eines Kollegen:**

>[!BEGINSHADEBOX]

Okay, ich werde die `Customer lifecycle` Datenansicht verwenden, um zukünftige Fragen in dieser Chat-Sitzung zu beantworten.

>[!ENDSHADEBOX]

### Datenansicht oder Report Suite-Voreinstellung im Speicher hinzufügen

Der Coworker Chat enthält eine Speicherfunktion, mit der Sie Zugriff auf Informationen erhalten, die sich über alle Chats erstrecken. Es empfiehlt sich, die von Ihnen bevorzugten Datenansichten oder Report Suites als Voreinstellungen im Arbeitsspeicher des Kollegen hinzuzufügen.

1. Wählen Sie im Coworker Chat in der linken Navigationsleiste das Speichersymbol aus.

1. Geben Sie auf der Speicherseite im Abschnitt [!UICONTROL **Gespeicherte Voreinstellungen**] eine oder mehrere Datenansichten oder Report Suites an, die der Coworker Chat in Ihren Chats verwenden soll.

   ![Speicherabschnitt in der linken Leiste](../../assets/coworker-memory.png)

## Beispiel: Finden Sie heraus, wo Kunden abbrechen

Sie können Coworker Chat bitten, Ihre Daten zu verwenden, um geschäftliche Fragen zu analysieren.

Als Marketing-Manager, Merchandiser oder Wachstumsleiter möchten Sie vielleicht verstehen, wo Kundinnen und Kunden den Weg zum Kauf verlassen, warum sie ihn getan haben und was getan werden kann, um höhere Konversionsraten zu erzielen.

>[!NOTE]
>
>Die folgenden Abbildungen zeigen beispielhafte Daten für einen fiktiven retailer, [!DNL TechPulse Electronics], der verwendet wird, um die Form des Gesprächs zu zeigen.

### Die Arten von Fragen, die Sie stellen können

Sie müssen nicht wissen, was eine „Fallout-Visualisierung“ ist oder welche Metrik in welchen Slot passt. Beschreiben Sie stattdessen das Ergebnis, das Ihnen wichtig ist, in einfacher Sprache:

* „Wo verlieren wir Menschen auf dem Weg zum Kauf?“
* „Was ist meine vollständige Konversion von funnel, von der Produktansicht bis zum Checkout?“
* „Welche Marketing-Kanäle lecken am meisten zwischen Warenkorb und Kauf?“
* „Ist der Warenkorbabbruch auf Mobilgeräten oder Desktop-Computern schlimmer?“
* „Konvertieren Menschen aus Paid Social anders als Menschen aus E-Mails?“

### Das Gespräch

#### &#x200B;1. Beginnen Sie mit der Geschäftsfrage

**Sie:**

>[!BEGINSHADEBOX]

Wo verlieren wir Menschen auf dem Weg zum Kauf?

>[!ENDSHADEBOX]

**Chat-Antwort eines Kollegen:**

Beachten Sie, dass im Coworker Chat die richtige Visualisierung ausgewählt wird, die Touchpoints sequenziert und sogar empfohlene nächste Schritte hinzufügt.

>[!BEGINSHADEBOX]

![Funnel-Tabelle mit den Sitzungszahlen, Konversionsraten und Abbrüchen bei jedem Schritt von der Sitzung bis zum Kauf](../../assets/coworker-funnel-response.png)

Dies ist eine funnel-Frage. Lassen Sie mich die funnel-Konversion ausführen, um zu sehen, wo es auf dem Kaufpfad zu einer Abnahme kommt.

Hier verliert man Menschen:

| Funnel-Schritt | Anzahl | Konvertierung in nächste | Abbruch |
| --- | --- | --- | --- |
| Sessions | 137,476 | 45,0 % Produkt ansehen | 55% verlassen, ohne Produkte zu durchsuchen |
| Produktansichten | 61,845 | 55,0 % In den Warenkorb | 45 % durchsuchen, aber nicht hinzufügen |
| Hinzufügungen zum Warenkorb | 34,045 | 16,4 % Kauf | 83,6 % Warenkorbabbruch |
| Käufe | 5,582 | — | – |

**Die große Erkenntnis: Der zu kaufende Warenkorb ist Ihr größtes Leck**

28.463 Personen fügen Artikel zu ihrem Warenkorb hinzu, schließen den Kauf jedoch nie ab. Dies entspricht einer Abgaberate von 83,6 % bei Warenkorb - dem bei weitem größten Einzelfehler.

**Was dies über Prioritäten sagt:**

| Priorität | Problem | Opportunity-Umfang |
| --- | --- | --- |
| #1 | Warenkorbabbruch bei Kaufabbruch (Rückgang um 83,6 %) | 28.463 verlorene Käufer |
| #2 | Sitzung zur Produktansicht (55 % nie durchsuchen) | 75.631 Sitzungen ohne Produktinteraktion |
| #3 | Produktansicht zum Warenkorb (45 % fügen nicht hinzu) | 27.800 Interessierte, aber unverbindlich |

**Empfohlene nächste Schritte:**

1. Warenkorbabbruch nach Marketing-Kanal aufschlüsseln - Bringen bestimmte Kanäle Low-Intent-Traffic, der zum Warenkorb hinzukommt, aber nie kauft?
1. Betrachten Sie den Warenkorbabbruch nach Gerätetyp - Tötet die Reibung beim mobilen Checkout Konversionen?
1. Ermitteln Sie, welche Produkte am häufigsten aufgegeben werden - Preisproblem? Versand-Überraschung?

**Auf welche davon möchte ich als Nächstes eingehen?** Die Kanalaufschlüsselung würde Ihnen direkt mitteilen, welche Marketing-Aktionen Ihnen „fast-Käufer“ gegenüber tatsächlichen Käufern bringen.

>[!ENDSHADEBOX]

#### &#x200B;2. In das Leck bohren

**Sie:**

>[!BEGINSHADEBOX]

Okay, lassen Sie uns nach Marketing-Kanal aufschlüsseln

>[!ENDSHADEBOX]

**Chat-Antwort eines Kollegen:**

>[!BEGINSHADEBOX]

![Funnel-Tabelle mit den Konversionsraten und Abbrüchen aufgeschlüsselt nach Marketing-Kanal](../../assets/coworker-funnel-response2.png)

Es gibt eine benutzerdefinierte Dimension **Marketing** Kanal. Lassen Sie mich den funnel daran entnehmen, dann die Konversionsraten pro Kanal berechnen und feststellen, wo jeder Kanal undicht ist.

**Das Urteil: Das Leck ist nicht kanalspezifisch**

Das ist eine wirklich aufschlussreiche Erkenntnis. Hier finden Sie die Aufschlüsselung nach funnel pro Kanal:

| Kanal | Sessions | Zur Produktansicht | Zum Warenkorb hinzufügen | Zu erwerben | Konversion insgesamt | Umsatz/Sitzung |
| --- | --- | --- | --- | --- | --- | --- |
| Paid Search | 43,958 | 45.1% | 54.6% | 16.6% | 4.09% | $499.58 |
| Organische Suche | 31,492 | 44.9% | 54.9% | 16.9% | 4.17% | $494.76 |
| Direkt | 25,245 | 43.6% | 55.4% | 15.8% | 3.82% | $497.29 |
| E-Mail | 17,586 | 45.3% | 55.4% | 16.2% | 4.07% | $501.13 |
| Bezahlte Social Media | 12,684 | 45.4% | 55.7% | 16.0% | 4.03% | $512.17 |
| Anzeige | 6,511 | 45.3% | 55.7% | 16.2% | 4.09% | $501.45 |

**Wichtige Erkenntnisse:**

1. Die Abladung vom Warenkorb zum Kauf ist über alle Kanäle hinweg einheitlich schlecht (83-84 %). Das heißt, es geht nicht um die Traffic-Qualität, sondern darum, dass jeder Kanal die Leute ähnlich schnell in den Warenkorb konvertiert. Das Leck liegt in Ihrem Checkout-Erlebnis selbst, nicht in Ihrem Marketing.
1. Kein Kanal ist bei der Konvertierung signifikant besser oder schlechter. Die Gesamtkonversionsraten liegen dicht zwischen 3,8 % und 4,2 %, und der Umsatz pro Sitzung ist nahezu identisch (495 - 512 $).
1. Wo die Auswirkungen auf das Volumen am wichtigsten sind: Die bezahlte Suche verliert die meisten Menschen in absoluten Zahlen (9.015 Warenkorbabbrüche), gefolgt von der organischen Suche (6.449 verloren). Dies sind die größten Chancen in Bezug auf den Wert eines Dollars, da sie den meisten Traffic verursachen.

**Was sagt Ihnen das strategisch**

Die Marketing-Kanäle machen ihren Job - sie alle bringen die Leute dazu sich zu interessieren und fügen zum Warenkorb zu ähnlichen Preisen hinzu. Das Problem liegt im Downstream des Marketings: Ihr Checkout und Zahlungsfluss ist dort, wo das Geld durchsickert.

**Empfohlene nächste Untersuchungen:**

1. Aufschlüsselung des Verlassens des Warenkorbs auf Mobilgeräte nach Produktkategorie — Ist es bei teuren Artikeln (was auf Probleme mit dem Vertrauen in den mobilen Zahlungsverkehr hindeutet) schlechter?
1. Sehen Sie, welche Marketing-Kanäle den meisten mobilen Traffic verursachen - geben Sie dafür bezahlte Medienbudgets aus, um Leute in ein kaputtes mobiles funnel zu schicken?
1. Überprüfen Sie, ob ein Seiten- oder Site-Abschnittssignal vorliegt - können wir sehen, welche Checkout-Seiten mobile Benutzer zuletzt aufgerufen haben, bevor sie aufgeben?

**Welchen Blickwinkel möchten Sie als Nächstes untersuchen?**

>[!ENDSHADEBOX]

#### &#x200B;3. Weiter untersuchen

**Sie:**

>[!BEGINSHADEBOX]

Interessant. Versuchen wir, nach Gerätetyp aufzuschlüsseln.

>[!ENDSHADEBOX]

**Chat-Antwort eines Kollegen:**

>[!BEGINSHADEBOX]

![Funnel-Tabelle mit Konversionsraten und Abbrüchen aufgeschlüsselt nach Gerätetyp](../../assets/coworker-funnel-response3.png)

**Gefunden: Der mobile Checkout ist defekt**

Der funnel ist geräteübergreifend bis zum Checkout identisch - dann fällt Mobile von einer Klippe:

| Gerät | Sessions | Zur Produktansicht | Zum Warenkorb hinzufügen | Zu erwerben | Konversion insgesamt |
| --- | --- | --- | --- | --- | --- |
| Desktop | 70,172 | 44.9% | 54.8% | 23.2% | 5.70% |
| Tablet | 13,855 | 44.7% | 55.6% | 14.3% | 3.56% |
| Mobile | 53,449 | 44.9% | 55.3% | 8.1% | 2.02% |

**Die Raucherpistole**

| Metrik | Desktop | Mobile | Lücke |
| --- | --- | --- | --- |
| Warenkorb zur Kaufrate | 23.2% | 8.1% | 15 Prozentpunkte |
| Mobile ist | – | 2,8fach schlechter | – |
| Transaktionsabbrüche | 13,274 | 12,178 | Nahezu das gleiche absolute Volumen |

Das Browsen und Hinzufügen zum Warenkorb funktioniert auf Mobilgeräten einwandfrei (identische Browser-Rate von ~45 %, ~55 % Quote von Hinzufügungen zum Warenkorb). Die Menschen sind gleichermaßen interessiert und engagiert. Aber irgendetwas im mobilen Checkout-Fluss bringt Konversionen zum Erliegen.

**Die Umsatzmöglichkeit**

Wenn die Mobile-Kasse mit derselben Rate wie die Desktop-PCs konvertiert würde, würden Sie ca. 1.991 zusätzliche Käufe erzielen - eine Steigerung des gesamten Kaufvolumens um 35 % durch die Behebung eines Erlebnisses.

**Was passiert wahrscheinlich**

Das Datenmuster (gleiches Engagement, katastrophaler Checkout-Rückgang) ist ein klassisches Signal für:

* Reibungsloser Ablauf von Zahlungsformularen auf kleinen Bildschirmen (Probleme beim automatischen Ausfüllen, Formular-Layout)
* Unerwartete Kosten an der Kasse (Versand, Steuer), die Aufkleber-Schock verursachen
* Gast-Checkout nicht verfügbar oder Anmeldewand auf Mobilgerät
* Seitenladeprobleme oder Zeitüberschreitungsprobleme bei der Zahlungsverarbeitung auf Mobilgeräten

**Empfohlene nächste Schritte:**

1. Aufschlüsselung des Verlassens des Warenkorbs auf Mobilgeräte nach Produktkategorie — Ist es bei teuren Artikeln (was auf Probleme mit dem Vertrauen in den mobilen Zahlungsverkehr hindeutet) schlechter?
1. Sehen Sie, welche Marketing-Kanäle den meisten mobilen Traffic verursachen - geben Sie dafür bezahlte Medienbudgets aus, um Leute in ein kaputtes mobiles funnel zu schicken?
1. Überprüfen Sie, ob die Kampagne „Holiday_flash_sale“ eine bessere Checkout-Konversion hatte - dringengesteuerte Kampagnen könnten die Checkout-Reibung überwinden.

**Welche möchten Sie untersuchen, oder reicht dieser Beweis, um ihn zu Ihrem UX- und Checkout-Team zu bringen?**

>[!ENDSHADEBOX]

#### &#x200B;4. Aus ihr eine Entscheidung machen

**Sie:**

>[!BEGINSHADEBOX]

Was soll ich also tun?

>[!ENDSHADEBOX]

**Chat-Antwort eines Kollegen:**

>[!BEGINSHADEBOX]

Basierend auf dem, was die Daten zeigen, würde ich mich hier konzentrieren:

* **Reparieren Sie den mobilen Checkout - es ist kein Kanalproblem.** Jeder Kanal konvertiert Personen zu einem ähnlichen, gesunden Tempo in den Warenkorb, sodass die Anzeigenausgaben überall funktionieren. Der Umsatz geht insbesondere im Mobile-Checkout-Fluss verloren, in den die Fehlerbehebung gehört.
* **Beginnen Sie mit der Zahlung und Formularreibung.** Dies sind die häufigsten Gründe dafür, dass vorsätzliche Mobilkäufer ihren Warenkorb verlassen. Mobile Wallet-Optionen anzubieten und das Formular zu kürzen sind in der Regel die schnellsten Gewinne.
* **Überprüfen Sie nach der Behebung erneut.** Sobald die Checkout-Änderungen versendet werden, sollten Sie überprüfen, ob sich die Warenkorb-Kaufrate von Mobile auf die Desktop-Rate von 23,2 % zubewegt.

Soll ich das als Projekt speichern, damit Sie es verfolgen können, oder einen Warnhinweis einrichten, wenn der Kauf von Mobilgeräten per Warenkorb unter einen Schwellenwert fällt?

>[!ENDSHADEBOX]

### Was ist passiert?

Bei vier fremdsprachigen Fragen hat uns die Kollegin geholfen:

* Erstellen Sie eine mehrstufige Konversions-funnel und kennzeichnen Sie „Warenkorb-zu-Kauf“ als größtes Leck
* Marketing-Kanal als Ursache ausschließen - jeder Kanal sickerte fast mit der gleichen Rate durch
* Isolieren Sie das eigentliche Problem der mobilen Kasse und quantifizieren Sie die Fehlerbehebung bei einer Steigerung der Käufe um 35 %.
* Entscheiden Sie sich für eine Lösung, die Ihre Prioritäten setzt: mobiles Bezahlen und Formularkonflikte. Dies entspricht einer Konversionsrate von 23,2 % für Desktop-Computer

## Durchführen von Analysen in Customer Journey Analytics

Nachdem ein Kollege eine Visualisierung erstellt hat, können Sie sie in Analysis Workspace öffnen, um eine tiefere Analyse und granulare Steuerung zu ermöglichen. Die Visualisierung wird in einem neuen Analysis Workspace-Projekt in Customer Journey Analytics geöffnet.

Öffnen einer Visualisierung in einem neuen Analysis Workspace-Projekt:

1. Wählen Sie [!UICONTROL **Analysieren in CJA**] neben einer Visualisierung aus, die in Coworker erstellt wird.

1. Wenn die Visualisierung in Customer Journey Analytics geöffnet ist, können Sie die Analysis Workspace-Browser-Benutzeroberfläche per Drag-and-Drop verwenden, um Änderungen vorzunehmen, Ihre Analyse weiter zu erstellen, eine Zielgruppe zu erstellen und vieles mehr. Sie können Ihr Workspace-Projekt sogar für jeden freigeben, den Sie auswählen.

   Weitere Informationen zu Analysis Workspace finden Sie unter [Übersicht über Analysis Workspace](https://experienceleague.adobe.com/de/docs/analytics-platform/using/cja-workspace/home).

## Nächste Schritte

Weitere Anwendungsfälle, die Fähigkeiten, die Coworker Chat zur Analyse Ihrer Daten verwendet, und Best Practices für das Schreiben von Eingabeaufforderungen finden Sie unter [Analysieren von Daten mit dem Coworker Chat](/help/chat/use-cases/data-insights/analytics-overview-v2.md).
