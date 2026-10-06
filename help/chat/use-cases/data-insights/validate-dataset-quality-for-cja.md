---
title: Validieren von Customer Journey Analytics-Daten mit Datenvalidierungskenntnissen in einem Kollegen
description: Erfahren Sie, wie Sie Customer Journey Analytics-Daten mithilfe der Datenvalidierungsfertigkeit in Coworker validieren und Probleme lösen können, bevor Sie Dashboards erstellen.
feature: AI Tools
role: User
level: Beginner, Intermediate
doc-type: Feature Video
duration: 330
last-substantial-update: 2026-09-16
jira: KT-22622
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 0%
---
# Validieren von Customer Journey Analytics-Daten mit Datenvalidierungsfähigkeiten in [!DNL Coworker]

Die Datenqualität ist die Grundlage für präzise Berichte in Adobe Customer Journey Analytics (CJA). Bevor Sie Metriken, Dashboards, Segmente oder Kunden-Journey erstellen, müssen Sie unbedingt wissen, ob die zugrunde liegenden Adobe Experience Platform (AEP)-Daten vertrauenswürdig sind.

In diesem Video erfahren Sie, wie Sie mit der **Datenvalidierungsfertigkeit in**) schnell die Qualität der Datensätze für Ihre Customer Journey Analytics-Implementierung bewerten können, ohne Abfragen zu schreiben oder Daten manuell zu überprüfen.

>[!VIDEO](https://video.tv.adobe.com/v/3503519/?learn=on&enablevpops)

## Erfahren Sie mehr über die Datensätze hinter Ihren CJA-Berichten

So kann ein Mitarbeiter Folgendes identifizieren:

- Welche Datensätze mit Customer Journey Analytics verbunden sind
- Die mit einer bestimmten Sandbox verknüpften Verbindungen und Datenansichten
- Die Datensätze, die das Reporting aktiv unterstützen
- Wichtige Datensatzmerkmale wie Streaming-Status und Identity-Namespaces

Indem Sie genau verstehen, welche Datensätze Ihre Berichte bedienen, können Sie die Validierung auf die wichtigsten Bereiche konzentrieren.

## Erkunden von Datensatzschemata und verfügbaren Feldern

Erfahren Sie, wie Sie Datensatzschemata direkt in Adobe Experience Platform überprüfen.

Die Kollegin ruft Schemadetails und -oberflächen ab:

- Commerce- und Transaktionsfelder
- Produktinformationen
- Web-Interaktionsdaten
- Identitätsfelder
- Kampagnen- und Marketing-Attribute
- Geräte- und geografische Dimensionen

Dies bietet ein Inventar der für die Analyse verfügbaren Felder und hebt den Unterschied zwischen Feldern hervor, die in einem Schema vorhanden sind, und Feldern, die verwendbare Daten enthalten.

## Validieren der Identitätsqualität

Identitätsdaten sind für Customer Journey Analytics von entscheidender Bedeutung, da sie das Reporting auf Personenebene und die kanalübergreifende Journey-Analyse unterstützen.

In diesem Video erfahren Sie, wie Sie mit einem Kollegen arbeiten können:

- Validiert Identitätsfelder
- Prüft auf Nullwerte und Datenvollständigkeit
- Wertet die Kennungsqualität aus
- Oberflächen fehlen oder sind nicht verfügbar Identitätsattribute

Die Beispielvalidierung zeigt, dass ECID- und E-Mail-Identitäten im Beispiel vollständig ausgefüllt und gültig sind, während die Analytics-ID nicht abgerufen werden konnte. Dies ist ein nützliches Signal, wenn Sie entscheiden, welche Kennungen die Profilzuordnung und das Reporting unterstützen können.

## Analysieren der individuellen Feldqualität

Ein Feld kann in einem Datensatz vorhanden, aber weiterhin für das Reporting nicht geeignet sein.

Validiert ein Kampagnen-Tracking-Feld und erstellt Berichte durch einen Kollegen:

- Populationsraten
- Null-Prozentsätze
- Datenkonsistenz
- Erkennung ungültiger Werte

Im Beispiel sind die vorhandenen Trackingcode-Werte sauber und konsistent, aber ca. 85 % der Zeilen sind null. Dies offenbart einen großen blinden Fleck bei der Berichterstellung, bevor eine CJA-Dimension oder Kampagnenmetrik auf dem Feld erstellt wird.

## KI-gestützte Datensatzvalidierung durchführen

Anstatt einzelne Felder einzeln zu validieren, kann ein Kollege einen ganzen Datensatz auswerten.

Sie erfahren, wie die Fähigkeit zur Datenvalidierung funktioniert:

- Wählt wichtige Felder für die Validierung aus
- Bewertung der Vollständigkeit und Qualität
- Vergleicht die Datenkonsistenz über verschiedene Felder hinweg
- Stärken und potenzielle Berichtsrisiken hervorheben

Die Validierungsergebnisse liefern eine Viabilitätskarte für CJA. Saubere Felder wie Web-Seitenname und E-Mail-Code können für das Reporting bereit sein, während spärliche Felder wie Kaufwert, Kampagnenname und Trackingcode eine Untersuchung erfordern.

## Identifizieren von Umsatz- und Attributionsrisiken

Das Video zeigt auch, wie die Datenvalidierung Probleme aufdecken kann, die sich auf die Berichtsgenauigkeit auswirken, darunter:

- Wenig Kampagnendaten
- Fehlende Attributionsinformationen
- Unvollständige Transaktionswerte
- Messlücken bei Einnahmen

Im angezeigten Datensatz sind die Bestellzahlen verfügbar, die Bestellbeträge werden jedoch nicht zuverlässig ausgefüllt. Dies ist ein Problem, das untersucht werden muss, bevor Umsatzberichte als vertrauenswürdig eingestuft werden.

## Warum Datenvalidierung für Customer Journey Analytics wichtig ist

Customer Journey Analytics ist nur so zuverlässig wie die Daten dahinter.

Die Validierung von Datensätzen vor dem Erstellen von Berichten hilft Teams bei Folgendem:

- Erhöhen des Vertrauens in Analyseergebnisse
- Verbessern der Data Governance-Verfahren
- Reduzieren von Berichtsfehlern
- Implementierungsprobleme früher identifizieren
- Effizientere Fehlerbehebung bei unerwarteten Metriken

Mit Coworker können diese Prüfungen mit Eingabeaufforderungen in natürlicher Sprache initiiert werden, was die Datenvalidierung für technische und nicht-technische Benutzende leichter zugänglich macht.

