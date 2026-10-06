---
description: Beschreibung.
title: Grundlegendes zum E-Mail-Editor
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 94cf399a48d13ee83c702804b50fdccd4baa9d71
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%
---
# Grundlegendes zum E-Mail-Editor {#email-editor}

Mit dem E-Mail-Editor können Sie eine von KI generierte E-Mail direkt im Kampagnenboard einschränken. Bearbeiten Sie die Betreffzeile und den Preheader, formatieren Sie Text und Bilder inline oder tauschen Sie sie in einer anderen Vorlage aus.

Wenn Sie eine E-Mail-Karte auf dem Campaign-Board auswählen, wird der E-Mail-Editor als Seitenbereich geöffnet. Dort kann der Benutzer den Betreff und den Preheader bearbeiten (mit von KI vorgeschlagenen Alternativen), auf den E-Mail-Textkörper klicken, um Text oder Bilder auszuwählen und zu formatieren, zwischen KI-generierten Varianten wechseln, die HTML-Vorlage austauschen, die Kompatibilität mit dem E-Mail-Client überprüfen und eine Test-E-Mail an den eigenen Posteingang senden. Änderungen werden automatisch gespeichert und frühere Versionen können überprüft und wiederhergestellt werden.

## Zugriff

1. Öffnen Sie die gewünschte Kampagne und klicken Sie in der E-Mail-Karte auf Editor öffnen .

SCREENSHOT

1. Bearbeiten Sie die Felder **Betreff** und **Preheader** direkt oder klicken Sie **Smart-Vorschläge** neben für KI-generierte Alternativen.
1. Klicken Sie in den E-Mail-Textkörper, um einen Textblock oder ein Bild auszuwählen, und verwenden Sie dann die unverankerte Symbolleiste, die angezeigt wird, um den Text zu formatieren oder das Bild zu verwalten.
1. Verwenden Sie **HTML-Vorlage wechseln** um den E-Mail-Textkörper durch eine andere Vorlage zu ersetzen.
1. Verwenden Sie **Test-E** Mail senden), geben Sie eine Empfängeradresse ein und klicken Sie auf **Senden**, um eine Live-Vorschau an diese Adresse zu senden.
1. Verwenden Sie das Symbol Versionsverlauf , um eine frühere gespeicherte Version in der Vorschau anzuzeigen und wiederherzustellen.
1. Änderungen werden automatisch gespeichert - es ist kein manueller Speicherschritt erforderlich.

### Wichtigste Verhaltensweisen

- Bild-Uploads sind auf 10 MB begrenzt; Bilder über etwa 3 MB werden automatisch komprimiert, wobei ein Qualitätshinweis Bilder unter 3 MB empfiehlt.
- Die Felder „Betreff“ und „Preheader“ haben über dieses Symbol die Option für eine KI-generierte Alternative.
- Verwenden Sie Strg+Z (Befehlstaste+Z für Mac), um die letzte Aktion rückgängig zu machen und rückgängig zu machen. Verwenden Sie Strg+Y (Befehl+Y für Mac), um „Wiederholen“ auszuführen und das letzte Rückgängigmachen rückgängig zu machen. KEITH CHECK STANDARD
- Frühere gespeicherte Versionen können über dieses Symbol in einem Bedienfeld „Versionsverlauf“ in der Vorschau angezeigt und wiederhergestellt werden.
- Standardmäßig generieren wir zwei Varianten pro E-Mail. Die gewünschte Variante kann über die Miniaturansichten auf der rechten Seite ausgewählt werden.

## Was diese Funktion nicht tut

- Es handelt sich nicht um einen Drag-and-Drop-Block-Builder - es gibt keine Blockbibliothek. Inhaltsblöcke können nicht hinzugefügt, entfernt oder neu angeordnet werden. Die Bearbeitung erfolgt direkt auf der vorhandenen E-Mail-HTML.
- Das Einfügen von Personalisierungs-/Zusammenführungs-Tags wird derzeit nicht unterstützt.
- Es wird kein Feld für Alternativtext für Bilder bereitgestellt.
- Es werden keine Betreffzeile, kein Preheader oder andere Prüfungen auf Inhaltsebene erzwungen, bevor eine E-Mail als „bereit“ erachtet wird. Die einzigen Prüfungen vor dem Start sind auf Kampagnenebene (Sendeeinrichtung, gesendete Test-E-Mail, eine echte Zielgruppe), nicht auf den E-Mail-Inhalt selbst.
- Das Umschalten der Desktop-/Mobile-Vorschau ist in der standardmäßigen Bearbeitungsansicht von Kampagnen-E-Mails nicht verfügbar. [BENÖTIGT EINGABE zur Bestätigung des Umfangs]
- [EINGABE ERFORDERLICH - Bestätigung durch einen Techniker: Ob der Editor nach der Aktivierung/dem Start einer Kampagne vollständig schreibgeschützt ist (nicht nur das Feld „Absender„)]
