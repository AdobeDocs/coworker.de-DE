---
description: Erfahren Sie mehr über Funktionsverbesserungen und -korrekturen in den Versionshinweisen zu Adobe CX Enterprise Coworker Campaign.
title: Versionshinweise zu CX Enterprise Coworker Campaign
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: ee66c1cc95ef1dd8c5e45c1fcb699547e63b9c8a
workflow-type: tm+mt
source-wordcount: '3590'
ht-degree: 0%
---
# Versionshinweise zu Adobe CX Enterprise Coworker Campaign {#release-notes}

Coworker Campaign-Versionen basieren auf einem kontinuierlichen Bereitstellungsmodell, das eine besser skalierbare, schrittweise Implementierung von Funktionen ermöglicht.

## September 2026 {#sep-2026}

**Veröffentlichungsdatum: 17. September 2026**

* Verbinden eines auf Azure, GCP oder einer benutzerdefinierten Domain gehosteten Databricks-Arbeitsbereichs
* Kampagnen können erst dann gestartet werden, wenn ihr Workflow vollständig eingerichtet ist
* Kampagnenvorlagen wurden mit aktualisierten Inhalten aktualisiert
* Direktes Auswählen eines Connectors beim Hochladen der CSV-Datei Ihrer Kontaktliste
* Es wurde ein Absturz behoben, der nach dem Scrollen durch eine lange Liste von Testanmeldungen auftreten konnte
* Fehlerkorrektur - Beim Hochladen einer Zielgruppen-CSV mit leeren oder doppelten Kopfzeilen kann die Seite jetzt abstürzen
* Es wurde ein Platzhaltertext in einer Kampagnenaufforderung korrigiert, der nach der Auflösung nicht ausgefüllt angezeigt wurde
* Es wurde ein Absturz auf der Seite Kenntnisse behoben, der durch einen fehlenden Farbverlauf verursacht wurde
* Es wurde ein Problem behoben, bei dem der Chat dieselbe Frage wiederholt, nachdem Sie sie bereits beantwortet hatten
* Chat-Antworten zeigen nicht mehr ein streunendes ID-Präfix vor der ausgewählten Antwort
* Der Chat schlägt jetzt schnelle Antworten für den nächsten Schritt vor, die Sie tippen können, um das Feld „Zusammenstellen“ auszufüllen
* Kampagnenvorlagen werden jetzt in einer optimierten Seitenansicht anstelle eines separaten Dialogfelds geöffnet
* Die erweiterte Fortschrittsleiste des Chats scrollt jetzt intern, anstatt Ihre Unterhaltung aus dem Blickfeld zu schieben
* Die Kampagneneinstellungen spiegeln jetzt die neuesten Board-Details genauer wider
* Das Dialogfeld für den Upgrade-Plan verwendet jetzt ein einheitlicheres Erscheinungsbild
* Redundante Statusanzeige aus der Kopfzeile des Kampagnenplans entfernt, um ein klareres Erscheinungsbild zu erzielen
* Schnelle E-Mail-Bearbeitungen werden jetzt als einzelner Eintrag im Versionsverlauf gespeichert, anstatt als viele
* Fehlerkorrektur - Markenkit-Titel werden gelegentlich ausgeblendet, während ein Entwurf generiert wird
* Bearbeiten eines Bildes mit Adobe Express direkt über die Bildsymbolleiste
* Grundlegende Daten der Agent-Zielgruppe bleiben jetzt ohne manuelle Aktualisierung auf dem Campaign-Board synchron
* Markenlogos auf dem Kampagnenboard werden passender für ihren Platz zugeschnitten
* Reibungslosere visuelle Übergabe, wenn ein Kampagnenplan auf das Kampagnenboard verschoben wird

**Veröffentlichungsdatum: 3. September 2026**

* Kopieren Sie alle Chat-Nachrichten und bewerten Sie KI-Antworten mit einem Daumen nach oben oder einem Daumen nach unten, direkt aus der Nachricht selbst
* Die Aufgabenliste für den Kampagnenplan bleibt während der Ausführung Ihrer Kampagne nun über der Chat-Eingabe angeheftet, sodass Sie den Fortschritt verfolgen können, ohne wegzuscrollen
* Verbinden eines DataBricks SQL Warehouse als neue Datenquelle für Ihre Kampagnen
* Der ältere chatbasierte E-Mail-Editor wurde zugunsten des neueren E-Mail-Asset-Editors eingestellt
* Testbenutzer-Admin ermöglicht jetzt den Ausschluss von Adobe-Benutzern, wodurch die Anzeige echter Testanmeldungen erleichtert wird
* Es wurde ein Problem behoben, bei dem ähnliche Kampagnenvorschläge nicht geladen werden konnten
* Chatnachrichten haben jetzt einen engeren, konsistenteren Abstand

**Veröffentlichungsdatum: 1. September 2026**

* Große Kampagnen-E-Mails werden jetzt vollständig im Editor angezeigt, anstatt abgeschnitten zu werden
* Die Launch-Schaltfläche des Kampagnen-Boards heißt jetzt aus Gründen der Klarheit „Überprüfen und starten“
* Beim Verbinden eines Salesforce-Kontos wird keine falsche Marketo-Fehlermeldung mehr angezeigt
* Salesforce verfügt jetzt über ein eigenes Logo in der Connector-Liste
* Verfügbare Connectoren werden jetzt vor den in Kürze erscheinenden aufgeführt
* Beim Onboarding wird jetzt eine Fortschrittsanzeige angezeigt, während Ihr Brand Kit geladen wird
* Die Vorschau von Zielgruppen und Wissensquellen verfügt jetzt über eine Schaltfläche zum Schließen und kann im Vollbildmodus geöffnet werden
* Kampagnenplankarten bleiben nach dem Start der Kampagne nicht mehr mit der Anzeige „Wird erstellt“ stecken
* Der Chat speichert keine temporären Fortschrittsmeldungen (wie „Erkunden…„) mehr in Ihrem Konversationsverlauf
* Symbolleistensteuerelemente werden jetzt beim Anwenden von KI-Bildern oder Textvorschlägen ordnungsgemäß gesperrt
* Es wurde ein Problem behoben, bei dem das Ersetzen eines Bildes im Asset-Editor nicht ordnungsgemäß funktionierte

## August 2026 {#aug-2026}

**Veröffentlichungsdatum: 26. August 2026**

* Wenn Sie auf eine beliebige Stelle auf einer Kampagnenvorlagenkarte klicken, wird jetzt deren Vorschau geöffnet, nicht nur der Titel
* Der Platzhalter für die Eingabeaufforderungsleiste in Campaign wird nach dem Löschen der Eingabe erneut korrekt angezeigt, mit klarerer Unterstützung durch die Sprachausgabe
* Der Vorschlag „Helfen Sie mir dabei“ ersetzt nun den vorhandenen Text in der Eingabeaufforderungsleiste der Kampagne korrekt
* Das Herunterladen von Abmeldungen als CSV-Datei spiegelt jetzt nur noch die angezeigte Kampagnenausführung wider
* Der Testplanvergleich zeigt jetzt Launch-Kampagnen und Kampagneneinblicke als integrierte Funktionen
* Zielgruppen, die ohne einen vollständigen Workflow erstellt wurden, werden jetzt korrekt auf der Zielgruppen -Karte des Kampagnen-Boards angezeigt
* Empty-State-Feedback fordert dazu auf, in der gesamten App natürlicher zu lesen

**Veröffentlichungsdatum: 25. August 2026**

* Wenn Sie sich auf einer Browser-Registerkarte anmelden, werden jetzt die anderen automatisch synchronisiert, was Kontoverwechslungen zwischen Registerkarten behebt
* Wenn Sie auf „Jetzt erstellen“ klicken, wird Ihr Plan zuverlässig vorwärts verschoben, anstatt ihn gelegentlich neu zu generieren
* Workflow-Diagramme im Chat zeigen mehr von der Arbeitsfläche an, sodass die Zoom-Steuerelemente die Schritte nicht mehr abdecken
* Die Registerkarten mit den Kampagnendetails haben ein aktualisiertes, konsistenteres Erscheinungsbild
* Das Speichern oder Entfernen einer Versand-Domain in Domains und Absender ist jetzt schneller und zuverlässiger

**Veröffentlichungsdatum: 24. August 2026**

* Anzeige der erstellten Kampagnenstrategie direkt auf dem Kampagnenboard
* Ersetzen Sie Ihre Zielgruppe direkt im Dialogfeld für die Kampagnenvalidierung
* Die Campaign PDF- und Word-Exporte enthalten jetzt Ihr echtes Workflow-Diagramm
* Die Registerkarte „Einblicke“ bleibt direkt nach dem Start mit einem hilfreichen leeren Status sichtbar
* Hinzufügen oder Entfernen von Touchpoints bei der Überprüfung Ihrer Kampagnenfelder
* Die Symbolleiste des Campaign-Boards ist einfacher, da unnötige Schaltflächen entfernt wurden.
* Der Assistent „Domains und Absender“ bereinigt Subdomains und führt die Ersteinrichtung mit einem Coachmark durch.
* Der Assistent „Domains und Absender“ zeigt Fehler bei der Subdomain-Validierung inline während der Eingabe an.
* Die call-to-action für die Nachprüfungskampagne wurde aus Gründen der Sauberkeit entfernt
* Chinesische Sprachnamen werden jetzt korrekt in der Sprachauswahl angezeigt
* KI-generierte Variantenminiaturen werden zuverlässig ohne doppelte Beschriftungen geladen
* Neu erstellte Kampagnen werden jetzt sofort auf der Startseite in Ihrer Liste der letzten Kampagnen angezeigt
* Alle Kampagneneinblicke enthalten jetzt eine von KI generierte Zusammenfassung der Kampagnenleistung Ihrer Organisation
* Wenn Sie die angeforderte Eingabe in einer Workflow-Konversation eingeben, bleibt sie nicht mehr hängen
* Beim Onboarding von Testsendungen blinkt kein zusätzlicher Ladebildschirm mehr, wenn nach einem vorhandenen Marken-Kit gesucht wird
* Veraltete Beispiel-Zielgruppenquellen werden jetzt automatisch aus Ihrem Workflow gelöscht
* Layout, Design und Schriftarten werden nun innerhalb der einheitlichen Experience Cloud-Shell korrekt dargestellt
* Ähnliche Kampagnenvorschläge zeigen kein unnötiges Kanalfeld mehr an

**Veröffentlichungsdatum: 14. August 2026**

* Löschen von Entwurfs-Domains, die Sie in „Domains und Absender“ nicht mehr benötigen
* Siehe DNS-Verifizierungsstatus für jeden Datensatz während der Domain-Einrichtung
* Domain-Details zeigen jetzt Ihren konfigurierten E-Mail-Absender an
* DNS-Datensatzwerte mit einer QuickInfo für den Volltext sauber abschneiden
* Gleichzeitiges Formatieren mehrerer E-Mail-Textblöcke mit Mehrfachauswahl
* Abrufen ähnlicher Kampagnenvorschläge beim Erstellen einer neuen Kampagne
* Kampagneneinblicke auf eine einzelne Ausführung einer wiederkehrenden Kampagne beschränken
* Wählen Sie Ihre bevorzugte Sprache aus dem Profilmenü
* Erhalten Sie einen Hinweis, wenn die Beschreibungen der Kampagnenvorlagen detaillierter sein müssen
* Versionshinweise sind mit besserer Navigation und Paginierung einfacher zu durchsuchen
* Reduzieren Sie die Liste der letzten Kampagnen der Seitenleiste, um Platz zu sparen
* Die Ansicht des Kampagnenbestands bleibt jetzt so, wie Sie sie verlassen haben
* Ausführungsfilter neu anordnen und aus einer Kalenderauswahl in einen Datumsbereich springen
* Vorschau von Zielgruppendetails auch auf schreibgeschützten Zielgruppenkarten
* Der Onboarding-Bildschirm für Testflüsse blinkt nicht mehr und es tritt kein Problem mit der Anmeldungsverzögerung auf.
* Der Größenänderungsgriff der Chat-Leiste blockiert die Bildlaufleiste der Nachrichtenliste nicht mehr.
* Die Erstellung eines Brand Kit zeigt jetzt den wahren Grund für das Fehlschlagen des Speichervorgangs an

**Veröffentlichungsdatum: 6. August 2026**

* Campaign Insights zeigt jetzt Abmeldungen mit einer herunterladbaren CSV-Datei von Benutzern an, die sich abgemeldet haben
* Auf der Registerkarte „Insights“ wird jetzt eine Tabelle mit einer Leistungsaufschlüsselung pro E-Mail angezeigt
* Zeigen Sie Ihre Kampagnen-Journey-Zuordnung direkt auf der Registerkarte „Insights“ an.
* Die auf der Dauer basierenden Warteschritte sind jetzt in der Journey-Workflow-Ansicht sichtbar
* Die gewichteten Journey-Verzweigungen werden in der Bearbeitungsansicht des Workflows angezeigt
* Kontaktlisten sind jetzt mit Live-Daten verbunden
* Wiederkehrende Kampagnen zeigen 0 Sendungen sofort anstelle von „Einblicke ausstehend“ an
* Bearbeiten von Remix-Eingabeaufforderungstext direkt um Platzhalterchips
* Verbesserte Coachmark- und Cleaner-Platzhalter-Chips im Remix-Editor
* Campaign-Workflow-Karten zeigen jetzt einen hilfreichen leeren Status an, wenn nichts ausgeführt wird
* Die Schaltfläche „Upgrade-Plan“ verdeckt nicht mehr die Kopfzeile der Kampagnendetails
* Workflow-Karten haben ein einfacheres Layout mit entferntem Journey-Namen und Beschreibung

## Juli 2026 {#july-2026}

**Veröffentlichungsdatum: 30. Juli 2026**

* Alle Kampagnen-Insights entsprechen jetzt dem Layout der einzelnen Kampagnen-Insights sowie einem neuen täglichen Leistungsdiagramm
* Stoppen einer Live-Kampagne direkt über die Kampagnenseite
* Beim Duplizieren einer Kampagne wird jetzt nur noch nach einem neuen Namen gefragt
* E-Mail-Vorlagen direkt über die Vorlagenliste bearbeiten
* Filtern der Ansicht der wiederkehrenden Kampagnen-Journey nach Ausführung
* Hinzufügen eines Markenbilds direkt über das Campaign-Board
* Die Testadministratortabelle unterstützt jetzt E-Mail-Suche, Paginierung und vollständigen CSV-Export
* Die Schaltfläche „Überraschung mich“ reagiert jetzt sofort, ohne Animationsverzögerung
* Die Einstellungen für die Abmeldung von Kampagnen-E-Mails wurden entfernt, während wir diese Funktion überarbeiten
* Bearbeiten des Zeitplans einer Kampagne, nachdem er bereits festgelegt wurde, ohne von vorne zu beginnen
* Öffnen Sie den Schreibstileditor über das Menü Überlauf , um schneller darauf zuzugreifen
* Durch Drücken der Eingabetaste werden jetzt in allen Eingabeaufforderungsleisten in der App konsistent gesendet

**Veröffentlichungsdatum: 23. Juli 2026**

* Planen Sie Kampagnen, die sofort, einmal zu einem bestimmten Zeitpunkt oder wiederkehrend gesendet werden sollen
* Abmeldelisten aus Kontaktlisten verwalten und Abmeldeparameter in den E-Mail-Einstellungen der Kampagne festlegen
* Erstellen und Verwalten von Formularen mit einem neuen Formularinventar- und -editor
* Die Connector-Einrichtung zeigt klarere Anleitungen, wenn Anmeldeinformationen fehlschlagen, einschließlich beim Aktualisieren einer vorhandenen Verbindung
* Marketo-Verbindungen unterstützen jetzt Experience Cloud-URLs
* Der Assistent für Domains und Absender erfasst mehr Probleme mit DNS-Einträgen, bevor Ihre Domain live geschaltet wird
* Connectoren direkt über das Menü Hinzufügen der Kampagneneingabe hinzufügen
* Inventarseiten zeigen freundlichere illustrierte leere Status an, wenn es noch nichts zu zeigen gibt
* Einblicke in Campaign zeigen, welche Datenquelle den einzelnen Metriken zugrunde liegt
* Markeneditor sind jetzt in das Onboarding integriert, um eine reibungslosere Ersteinrichtung zu ermöglichen
* Vorschau einer Beispielzielgruppe vor der Übertragung auf die Kampagne
* Coworker Campaign ist jetzt in der einheitlichen Experience Cloud-Navigationsshell verfügbar
* Die unverankerte Feedback-Titelleiste für ein Cleaner-Campaign-Board wurde entfernt.
* Verschiedene Leistungs- und Zuverlässigkeitsverbesserungen in

**Veröffentlichungsdatum: 14. Juli 2026**

* Rollout von Domains und Absendern, Live-Workflow-Fortschritt und echte Kampagneneinblicke
* Die Einrichtung von Domains und Absendern ist jetzt vollständig verfügbar und die Absenderauswahl wird automatisch gespeichert
* Wählen oder aktualisieren Sie den Absender Ihrer Kampagne über die Kampagneneinstellungen
* Die Registerkarte Absender bleibt auch vor der Verifizierung einer Domain aufrufbar
* E-Mail-Entwürfe, die während der Konversation hinzugefügt wurden, werden jetzt zuverlässig im Kampagnenboard angezeigt
* Hilfe und Feedback werden in einem optimierten Popup kombiniert
* Beim Starten einer neuen Konversation werden keine Nachrichten mehr angezeigt, die von der letzten überliefert wurden
* Konversationen mit mehreren Kurven zeigen keine veralteten Eingabeaufforderungen mehr in der Antwortschublade an
* Nummerierte Listen in Chat-Nachrichten behalten ihre korrekte Reihenfolge
* Beim Einrichten des HubSpot-Connectors wird jetzt nach einem Service-Schlüssel gefragt, der mit der eigenen Terminologie von HubSpot übereinstimmt
* Die Tabelle Testversion-Admin zeigt eine Benutzeranzahl an und schneidet die letzte Zeile nicht mehr an
* Verschiedene Leistungs- und Zuverlässigkeitsverbesserungen in

**Veröffentlichungsdatum: 9. Juli 2026**

* Ein Wartungsbanner und ein Dialogfeld warnen Sie jetzt vor geplanten Ausfallzeiten
* Domains &amp; Senders verfügt über einen geführten Einrichtungsassistenten zum Überprüfen von Domains und Hinzufügen von Absendern
* In Kampagnenentwürfen werden Sie jetzt aufgefordert, die Einrichtung von E-Mail und Kanal abzuschließen, bevor Sie versenden
* Die Domain- und Absendervalidierung erfasst mehr Probleme, einschließlich Edge-Fällen von DNS-Einträgen
* Das Profilmenü wurde in die Seitenleiste verschoben, um schneller darauf zugreifen zu können
* Source PDF-Dokumente werden jetzt als Pille auf den Details des Brand Kits angezeigt
* Verschiedene Leistungs- und Zuverlässigkeitsverbesserungen in

**Veröffentlichungsdatum: 26. Juni 2026**

* Ein neues Insights-Dashboard zeigt KPIs der Kampagnenleistung an: Sendungen, Öffnungen, Klicks, Bounces und mehr
* Kampagnen zeigen auf der Pinnwand ein Live-Status-Badge, sodass Sie aktive Sendungen auf einen Blick sehen können
* Kontextuelle Tipps werden im Campaign-Board angezeigt, um Sie durch die nächsten Schritte zu führen
* Beim Onboarding von neuen Benutzern werden Ihre echten Markendaten verwendet, um das Setup-Erlebnis zu personalisieren
* Die Markenfarbauswahl verarbeitet kurze Hexadezimalcodes und wird in einem aufgeräumten Popover geöffnet
* UTM-Parameter und Nachrichtenbegrenzung können jetzt über die App-Einstellungen konfiguriert werden
* Hilfe-Links öffnen jetzt die neuesten Inhalte direkt in Experience League
* Verschiedene Leistungs- und Zuverlässigkeitsverbesserungen in

**Veröffentlichungsdatum: 24. Juni 2026**

* Durch den Start einer Kampagne wird jetzt eine Konfetti-Feier Trigger
* Kampagnen zeigen nach dem Start ein Status-Badge und das Board wird auf Schreibgeschützt gesperrt
* Die Markenübersicht passt mit leeren Eingabeaufforderungen und besserer Logoanzeige auf Ihren Bildschirm
* Die Validierung zeigt ein klares Dialogfeld an, selbst wenn ein unerwarteter Fehlertyp zurückgegeben wird
* Der generierte E-Mail-Inhalt verwendet Ihr Kampagnenziel für relevantere Ergebnisse

## Juni 2026 {#june-2026}

**Veröffentlichungsdatum: 23. Juni 2026**

* Vor dem Start wird in einem Validierungsschritt überprüft, ob Ihre Kampagne bereit ist
* Erfahren Sie, warum jede E-Mail-Variante mit einer neuen Variantenbegründung erstellt wurde
* Die Kampagnenplanansicht zeigt im Stream von Aufgaben eine Leiste mit dem Live-Meilenstein-Fortschritt an.
* Beim Onboarding von neuen Benutzern werden Ihre echten Markendaten verwendet, um das Setup-Erlebnis zu personalisieren
* Die Markenfarbauswahl verarbeitet kurze Hexadezimalcodes und wird in einem aufgeräumten Popover geöffnet
* UTM-Parameter und Nachrichtenbegrenzung können jetzt über die App-Einstellungen konfiguriert werden
* Hilfe-Links öffnen jetzt die neuesten Inhalte direkt in Experience League
* Verschiedene Leistungs- und Zuverlässigkeitsverbesserungen in

**Veröffentlichungsdatum: 19. Juni 2026**

* Überprüfen Sie vor dem Versand die Kompatibilität des E-Mail-Clients für jedes Element
* Durchsuchen und Wiederherstellen früherer Versionen Ihrer E-Mail mit einem neuen Bedienfeld Versionsverlauf
* Bearbeiten von Markenfarben mit einer Auswahl „Hex-First“ und Inline-Bearbeitung auf der Markenseite
* Die Markenbibliothek lädt beim Scrollen automatisch weitere Marken
* Das Profilmenü wurde in die Seitenleiste verschoben, um schneller darauf zugreifen zu können
* Source PDF-Dokumente werden jetzt als Pille auf den Details des Brand Kits angezeigt
* Verschiedene Leistungs- und Zuverlässigkeitsverbesserungen in

**Veröffentlichungsdatum: 12. Juni 2026**

* Durchsuchen von Produkthilfen und Handbüchern, ohne die App zu verlassen
* Kampagnenpläne werden bei ihrer Erstellung Abschnitt für Abschnitt angezeigt
* Nehmen Sie Kampagnenunterhaltungen auf, bei denen Sie zuverlässiger aufgehört haben
* Starten Sie Kampagnen über ein dediziertes Dialogfeld, wenn Ihr Plan startbereit ist.
* Beim Onboarding werden klarere Produktbezeichnungen und Hilfestellung bei der Startseite verwendet.
* Connector-Setup zeigt die richtigen Felder für API-Schlüssel und Anmeldeverbindungen an
* Aus den Chatantworten heraus wird vorgeschlagen, was Sie als Nächstes mit Eingabeaufforderungen mit einem Klick fragen sollten
* Campaign PDF-Exporte zeigen Symbole, Produkt-Branding und eine Markenbezeichnung zuverlässig an
* Sprechen Sie mit einem Experten und laden Sie Ihre Testdetails zuverlässiger
* Schriftstil-Tags werden erweitert, um Volltext und Link zur Markenseite anzuzeigen
* Eine Marke aus dem leeren Bibliotheksstatus mit hilfreichen Kategorien starten
* Melden Sie sich nach Ablauf Ihrer Sitzung wieder reibungslos an
* Die App lebt jetzt auf coworker-campaigns.adobe.com mit dem gleichen Erlebnis
* Die Testanmeldung leitet Sie nach der Erstellung Ihres Kontos zum nächsten Schritt weiter
* Verschiedene Leistungs- und Zuverlässigkeitsverbesserungen in

**Veröffentlichungsdatum: 11. Juni 2026**

* In Kürze erscheinende Seiten zeigen einen leeren Platzhalter ohne überfüllten Hintergrund
* E-Mail-Editor-Symbolleisten sehen im hellen Design aus
* Wenn Sie ein E-Mail-Bild löschen, wird die Auswahl gelöscht, sodass die Symbolleiste ausgeblendet wird
* CSV-Audience-Importe zeigen auf der Audience-Karte keine doppelte Liste mehr an
* Der Chateintrag in der Seitenleiste wird hervorgehoben, wenn Sie einen neuen Chat beginnen
* Die App-Kopfzeile zeigt jetzt beim Bearbeiten einer E-Mail nur noch den E-Mail-Betreff (oder „Entwurf„) an und entfernt das Präfix „E-Mail: N“ für einen aufgeräumteren Titel
* Das Profilmenü wurde in die Seitenleiste verschoben, um schneller darauf zugreifen zu können
* Source PDF-Dokumente werden jetzt als Pille auf den Details des Brand Kits angezeigt
* Verschiedene Leistungs- und Zuverlässigkeitsverbesserungen in

**Veröffentlichungsdatum: 10. Juni 2026**

* Die App heißt jetzt Coworker-Kampagnen mit aktualisierten Namen im gesamten
* Eine Onboarding-Tour führt Sie durch den Aufbau einer Demo-Marke
* Starten Sie Kampagnen über ein dediziertes Dialogfeld, wenn Ihr Plan startbereit ist.
* Verbinden von HubSpot mit einem API-Schlüssel aus dem Integrationskatalog
* Durchsuchen Sie Chats mit einer neu gestalteten Unterhaltungsliste und klareren leeren Status
* Rückgängigmachen und Wiederholen von E-Mail-Bearbeitungen mit bekannten Tastaturbefehlen
* Speichern erneut versuchen, wenn der E-Mail-Editor auf einen temporären Fehler stößt
* Ersetzen von E-Mail-Bildern durch die richtige Größe und Adobe Express-Abmessungen
* Hochladen von Audience-Listen aus CSV mithilfe eines klareren Importdialogfelds im Chat
* Schriftstil-Tags werden erweitert, um Volltext und Link zur Markenseite anzuzeigen
* Eine Marke aus dem leeren Bibliotheksstatus mit hilfreichen Kategorien starten
* Melden Sie sich nach Ablauf Ihrer Sitzung wieder reibungslos an
* Verschiedene Leistungs- und Zuverlässigkeitsverbesserungen in

**Veröffentlichungsdatum: 9. Juni 2026**

* Vergleich der Testnutzung und der Upgrade-Optionen in einem neu gestalteten Dialogfeld „Plan“
* Durchsuchen und Verwalten von Daten-Connectoren aus einem Live-Katalog in der App
* Füllen Sie die allgemeinen Einstellungen und Benachrichtigungseinstellungen in den Einstellungen aus.
* Ihre Anmeldung bleibt mit einer klaren Eingabeaufforderung erhalten, wenn Ihre Sitzung abläuft
* Ihre E-Mail-Adresse wird beim Senden einer Test-E-Mail automatisch angezeigt
* Bestätigen Sie dies, bevor Sie ein Marken-Kit als Standard festlegen
* Beim Hochladen von Brand Kit wird jetzt eine Dateigrößenbeschränkung von 100 MB eingehalten
* Bearbeiten des Kampagnennamens direkt auf dem Kampagnenboard
* Zeigen Sie Vorlagen in der Vorschau an und bestätigen Sie diese, bevor Sie eine Kampagne senden.
* Verschiedene Leistungs- und Zuverlässigkeitsverbesserungen in

**Veröffentlichungsdatum: 4. Juni 2026**

* Letzte Chats werden in der Seitenleiste angezeigt und können inline umbenannt werden
* Öffnen Sie die Seite Chats , um vergangene Unterhaltungen zu suchen und fortzusetzen
* Startseiten-Workflows sind jetzt Kampagnenvorlagen mit einem einfacheren Remix-Fluss
* Bibliotheksvorlagen verwenden eine klarere Tabelle mit Beschreibungen und Kanalfiltern
* Brand Kits zeigen die Standardwerte zuerst an und filtern nach „Veröffentlicht“ oder „Entwurf“
* Nach der Veröffentlichung eines Markenentwurfs landen Sie automatisch im Markenkit für Live-Inhalte
* Kampagnen- und Markendaten werden direkt nach der Anmeldung zuverlässiger geladen
* Verschiedene Leistungs- und Zuverlässigkeitsverbesserungen in

## Mai 2026 {#may-2026}

**Veröffentlichungsdatum: 29. Mai 2026**

* Generieren von Bildvarianten und Auswahl aus eigenen Bildern direkt im E-Mail-Editor
* Hinzufügen von Bildern vom Computer mithilfe einer lokalen Dateiauswahl in der Bildsymbolleiste
* Beschreiben Sie, was Sie möchten, und lassen Sie KI das perfekte Bild für Ihre E-Mail generieren
* Exportieren Sie die fertige E-Mail als HTML-Datei aus dem Menü Mehr .
* Vorschläge für Smart Copies werden jetzt in der E-Mail-Symbolleiste angezeigt, wenn Sie Text bearbeiten
* Klicken Sie auf eine Marke auf dem Campaign-Board, um die Markendetails sofort anzuzeigen
* Legen Sie Ihr standardmäßiges Marken-Kit direkt in der Bibliothek fest.
* E-Mails im Editor folgen nun der Workflow-Sequenz, um eine klarere Reihenfolge zu erreichen
* Dateianhänge auf dem Startbildschirm sind jetzt auf PDFs für eine zuverlässige Verarbeitung beschränkt
* Die Tastaturnavigation, die Unterstützung für Bildschirmlesehilfen und die Bewegungsvoreinstellungen sind in der gesamten App konsistenter
* In Kürze erscheinende Beschriftungen kennzeichnen Seiten, die aktiv erstellt werden
* Verschiedene Leistungs- und Zuverlässigkeitsverbesserungen in

**Veröffentlichungsdatum: 21. Mai 2026**

* Bearbeiten von E-Mail-Bildern mit Adobe Express, ohne den Editor zu verlassen
* Erstellen von Marken mit eindeutigem Fortschritt beim Extrahieren und Veröffentlichen von Assets
* Verwalten von Domains und Absendern über den Abschnitt Personen
* Kontaktlisten im Abschnitt Personen durchsuchen und verwalten
* Wechseln von Asset-Vorlagen beim Arbeiten mit Marketing-Assets
* Herunterladen von Kampagnenplänen als Word-Dateien mit Workflow-Diagrammen
* Die Listen der Kampagnen, Kompetenzen und Workflows sind jetzt übersichtlicher aufgebaut
* Verschiedene Leistungs- und Zuverlässigkeitsverbesserungen in

**Veröffentlichungsdatum: 14. Mai 2026**

* Die -Bibliothek vereint Assets, Vorlagen und Marken an einem Ort
* Seitenleiste und Navigation erleichtern das Erreichen von Zielgruppen und Ihrem Standard-Brand Kit
* Kampagnenplan direkt aus den Kampagnendetails als PDF herunterladen
* Die Markenbearbeitung öffnet klarere Bedienfelder für Übersicht, Schreibstil und Farben
* Der TestCountdown wird in der Kopfzeile angezeigt, sodass die verbleibenden Tage sichtbar bleiben
* Die Workflows für Sportmarketing sind bereit, wenn Ihr Brief in diese Kategorie passt
* Die manuelle Einrichtung der Testversion vereinfacht die Verwaltung der Website-Adressen des Unternehmens
* Verschiedene Leistungs- und Zuverlässigkeitsverbesserungen in

**Veröffentlichungsdatum: 8. Mai 2026**

* Der Campaign-Chat bietet einen klaren Wiederholungsversuch, wenn eine Hintergrundaufgabenprüfung fehlschlägt
* Aktualisierungen des Aufgabenstatus und Vollbild-Layout auf Kampagnenboards
* Die App startet schneller, indem Routen und Übersetzungen nach Bedarf geladen werden
* Kampagnen- und Markendaten bleiben in der gesamten App konsistent
* E-Mail-Bearbeitungen rückgängig machen und wiederholen funktionieren vorhersehbarer
* Speichern erneut versuchen, wenn der E-Mail-Editor auf einen temporären Fehler stößt
* Ersetzen von E-Mail-Bildern durch die richtige Größe und Adobe Express-Abmessungen
* Hochladen von Audience-Listen aus CSV mithilfe eines klareren Importdialogfelds
* Schriftstil-Tags werden erweitert, um Volltext und Link zur Markenseite anzuzeigen
* Verschiedene Leistungs- und Zuverlässigkeitsverbesserungen in

**Veröffentlichungsdatum: 6. Mai 2026**

* Campaign-Dashboards und -Listen bleiben bei Ihrer Arbeit stets auf dem neuesten Stand
* In Campaign Chat und Agent Builder wird ein eindeutiger Haftungsausschluss für generative KI angezeigt.
* Die Kontaktdaten des Supports verwenden jetzt die dedizierte E-Mail-Adresse von CX Coworker Campaign
* Auf der Marketing-Startseite wird der Wartelistenabschnitt entfernt und das Hero-Video wird klarer angezeigt
* Mehr Bildschirme berücksichtigen Ihre Sprache und Ihre lokalen Datumsformate automatisch
* Verschiedene Leistungs- und Zuverlässigkeitsverbesserungen in

## April 2026 {#apr-2026}

**Veröffentlichungsdatum: 28. April 2026**

* Kampagnenlisten und -boards bleiben synchron und fühlen sich beim Öffnen oder Aktualisieren einer Kampagne besser an
* Startseiten-Workflows sind jetzt Kampagnenvorlagen mit einem einfacheren Remix-Fluss
* Dunkle und helle Designs verwenden aktualisiertes Spektrum-Styling, um einen konsistenteren Look in der App zu erzielen
* Der Chat behandelt leere Assistenteninhalte elegant, mit gleichmäßigeren Statusanimationen und klareren Statusanimationen
* Wiederhergestellte Unterhaltungen öffnen ohne leere Chat-Leiste blinken, und das Wechseln von E-Mail-Varianten flackert nicht mehr in der Leiste
* Steuerelemente für den Datei-Upload entfernen sich aus dem Weg, nachdem Sie die Konversation gesendet oder fortgesetzt haben
* „Helfen Sie mir beim Schreiben“ ruft erst dann Ideen für eine Eingabeaufforderung ab, wenn Sie das Popover öffnen
* Statusaktualisierungen zeigen ein Erweiterungssteuerelement nur an, wenn eine Liste zum Anzeigen vorhanden ist
* Karten in Kampagnen, Fertigkeiten und Workflows verwenden ein einheitlicheres Layout
* Campaign-Listen und Markendaten werden direkt nach der Anmeldung zuverlässiger geladen
* Verschiedene Leistungs- und Zuverlässigkeitsverbesserungen in

**Veröffentlichungsdatum: 19. April 2026**

* Die App-Kopfzeile zeigt jetzt beim Bearbeiten einer E-Mail nur noch den E-Mail-Betreff (oder „Entwurf„) an und entfernt das Präfix „E-Mail: N“ für einen aufgeräumteren Titel
* Das Profilmenü wurde in die Seitenleiste verschoben, um schneller darauf zugreifen zu können
* Source PDF-Dokumente werden jetzt als Pille auf den Details des Brand Kits angezeigt
* Das Profilmenü wurde in die Seitenleiste verschoben, um schneller darauf zugreifen zu können
* Verschiedene Leistungs- und Zuverlässigkeitsverbesserungen in

**Veröffentlichungsdatum: 18. April 2026**

* Die Eingabe für die -Startseiten-Kampagne hat jetzt einen animierten Glühring und einen höheren, helleren Heldengradient
* „Surprise me“ Trigger Ein bunter Verlauf schimmert am Eingangsrand
* Die App unterstützt jetzt ein konsistenteres Layout über Produktseiten hinweg
* Dokumentations-Links öffnen jetzt die neuesten Inhalte direkt in einer neuen Registerkarte
* Verschiedene Leistungs- und Zuverlässigkeitsverbesserungen in
