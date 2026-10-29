---
title: Erkennen von Experience Platform-Anomalien mit einem Kollegen
description: Erfahren Sie, wie Sie mit dem Coworker Chat Anomalien in Adobe Experience Platform erkennen. Erkunden Sie Eingabeaufforderungen für Metriken zur Aufnahme, Segmentierung und Zielaktivierung.
feature: AI Tools
role: User
level: Intermediate
doc-type: Tutorial
jira: PLAT-313965
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 1ec3a8bf6dff44df068529cf1f7ceb699a027d65
workflow-type: tm+mt
source-wordcount: '1657'
ht-degree: 1%
---

# Experience Platform-Anomalien erkennen

Verwenden Sie [!DNL Adobe CX Enterprise Coworker] Chat, um in unterstützten Adobe Experience Platform-Metriken Spitzen und Rückgänge zu identifizieren. Fragen Sie nach Datenflüssen und Zielgruppen, um Abweichungen von einer Grundlinie zu finden.

Beginnen Sie mit einer allgemeinen Frage und konzentrieren Sie sich dann auf einen Fluss oder eine Zielgruppe, die Aufmerksamkeit erfordert. Überprüfen Sie die gemeldete Metrik und ihre Baseline, bevor Sie entscheiden, was untersucht werden soll.

>[!AVAILABILITY]
>
>Die Anomalieerkennung ist nur begrenzt verfügbar. Die allgemeine Verfügbarkeit ist für das erste Quartal 2027 geplant.

>[!NOTE]
>
>Die Anomalieerkennung liefert Informationen, ohne Ihre Daten oder Konfiguration zu ändern.

## Verfügbare Diagnosefähigkeiten

Verwenden Sie das `baseline-anomalies`-Plug-in, um Anomalien zu erkennen, Trends zu vergleichen und den Zustand des Flusses oder aktuelle Auftragsfehler zu überprüfen. Das Plug-in wird standardmäßig mit dem Experience Platform- und -Apps-Angebot in [!DNL Coworker] konfiguriert.

Wählen Sie die Art der Frage basierend auf den benötigten Informationen aus.

| Skill | Zweck |
| --- | --- |
| [!UICONTROL Grundlegende Anomalien bei der Suche nach Flussanomalien] | Erkennen von Spitzen oder Rückgängen des Datensatzvolumens und fehlgeschlagener Datensätze in der Aufnahme-, Segmentierungs-, Export- und Zielphase. |
| [!UICONTROL Grundlegende Anomalien bei der Suche nach Zielgruppen-Anomalien] | Erkennen Sie Spitzen oder Rückgänge bei der Anzahl realisierter Zielgruppenprofile und Spitzen bei der Anzahl ausgehender Profile. |
| [!UICONTROL Baseline-Anomalien fassen den Fluss-Trend zusammen] | Vergleich des aktuellen und des typischen Flussdurchsatzes ohne Anomaliebeurteilung. |
| [!UICONTROL Baseline-Anomalien fassen den Zielgruppen-Trend zusammen] | Vergleichen Sie die neuesten und typischen Anzahl qualifizierter und beendeter Profile für die Batch-Segmentierung, ohne Anomalie-Urteil oder erwarteten Bereich. |
| [!UICONTROL Grundlinien-Anomalien untersuchen die Flussintegrität] | Überprüfen Sie die Anzahl der deduplizierten erfolgreichen und fehlgeschlagenen Ausführungen sowie die Gesamtzahl der fehlgeschlagenen Datensätze nach Aktivität oder Fluss. |
| [!UICONTROL Baseline-Anomalien für fehlgeschlagene Suchvorgänge] | Überprüfen Sie derzeit fehlgeschlagene Aufträge und deren Fehlerursachen, mit Ausnahme von wiederhergestellten Fehlern und Details für einzelne Datensätze. |

Trendzusammenfassungen beschreiben Änderungen, ermitteln jedoch nicht, ob es sich um Anomalien handelt. Verwenden Sie Anomaliefragen, wenn Sie eine Spitzenbewertung oder eine Fallbewertung benötigen.

## Voraussetzungen

Das Plug-in ist standardmäßig konfiguriert. Gehen Sie wie folgt vor, um den Status vor dem Stellen von Diagnosefragen zu überprüfen.

1. Navigieren Sie zu **[!UICONTROL Anpassungen]**.

1. Wählen Sie **[!UICONTROL Plug-ins]** aus.

1. Öffnen Sie **[!UICONTROL Baseline-Anomalien]** und bestätigen Sie, dass der Status &quot;**[!UICONTROL &quot;]**.

Identifizieren Sie die Sandbox und den Bereich, den Sie überprüfen möchten. Für eine bestimmte Ressource den Fluss, das Segment, den Zielnamen oder die Kennung bereithalten.

Allgemeine Chat-Anweisungen finden Sie unter [Erste Schritte mit dem Chat](/help/chat/ui-guide.md).

## Fragen zu Anomalien

Beschreiben Sie den Bereich oder die Ressource, die Sie überprüfen möchten, und den Zeitraum, den Sie untersuchen möchten.

Verwenden Sie die folgenden Beispielaufforderungen als Ausgangspunkt. Ersetzen Sie Beispielnamen durch Namen aus Ihrer Organisation.

| Ziel | Prompt-Beispiel |
| --- | --- |
| Überprüfen der unterstützten Bereiche | Gibt es Anomalien in den letzten 24 Stunden? |
| Aufnahme überprüfen | Gibt es Anomalien bei meiner Aufnahme in den letzten 24 Stunden? |
| Überprüfen eines bestimmten Flusses | Gibt es Anomalien beim Kundenimport im Aufnahmefluss in den letzten 24 Stunden? |
| Segmentierung überprüfen | Gibt es Anomalien bei meiner Segmentierung in den letzten 24 Stunden? |
| Überprüfen eines bestimmten Segments | Gibt es in den letzten 24 Stunden Anomalien bei Segment-Loyalty-Mitgliedern? |
| Zielaktivierung überprüfen | Gibt es Anomalien bei meiner Zielaktivierung in den letzten 24 Stunden? |
| Überprüfen realisierter Profilspitzen | Sehen irgendwelche Zielgruppen heute einen Anstieg der realisierten Profile? |
| Überprüfen von fehlgeschlagenen Datensatzanomalien | Sind fehlgeschlagene Datensätze bei Kundenimport ungewöhnlich hoch? |

Die allgemeine Frage prüft sowohl Datenflüsse als auch Zielgruppen. Bestätigen Sie die Sandbox und den in der Antwort angegebenen Zeitraum.

<!-- Author review: Confirm exact supported time windows, defaults, time zone handling, and data freshness. -->

## Anomalieergebnisse überprüfen

Vergleichen Sie den gemeldeten Wert mit seiner Baseline für die betroffene Ressource und den betroffenen Zeitraum. Verwenden Sie den Unterschied, um zu ermitteln, was weiter untersucht werden muss, anstatt eine Anomalie als bestätigte Ursache zu behandeln.

Ein Rückgang der Aufnahmeeingabedatensätze deutet beispielsweise auf eine Volumenänderung hin. Diese Änderung allein erklärt nicht, warum weniger Datensätze eintrafen.

Die Ergebnisse können in Tabellen oder in schriftlicher Zusammenfassung angezeigt werden. Tabellen können Anomalien unter dem Risiko [!UICONTROL Hohes Risiko] und dem Risiko [!UICONTROL Medium ].

![Anomalieergebnisse gruppieren Aufnahme- und Zielvolumenspitzen und -senkungen nach hohem und mittlerem Risiko, wobei Ressourcennamen und -werte geschwärzt sind.](assets/anomaly-detection/anomaly-detection-results.png){width="900" zoomable="yes"}

In diesem Beispiel werden Flussanomalien nach Risiko gruppiert und es wird empfohlen, Ausführungszahlen oder Trendverlauf zu untersuchen. Ressourcennamen und -werte werden geschwärzt.

| Ergebnisdetails | Was zu überprüfen ist |
| --- | --- |
| [!UICONTROL Wenn (UTC)] | Die Ereigniszeit oder das Zeitfenster in der koordinierten Weltzeit. |
| [!UICONTROL stage] | Die betroffene Verarbeitungsstufe, wie Aufnahme oder Ziel. |
| [!UICONTROL Fluss] | Der betroffene Fluss, identifiziert durch Name oder Kennung. |
| [!UICONTROL Was ist passiert] | Die erkannte Änderung, z. B. eine Lautstärkespitze oder ein Abfall. |
| [!UICONTROL Tatsächlich vs. erwartet] | Der beobachtete Wert im Vergleich zum Ausgangswert oder zum erwarteten Bereich. |

Überprüfen Sie die Erklärung zusammen mit der Risikogruppierung. Bei Zielgruppenanomalien bedeutet „Hoch“ eine große Abweichung vom Normalwert. Medium deutet auf einen deutlichen, aber gemäßigten Abschied hin. Nur Anomalien vom Typ Hoch und Medium werden zurückgegeben.

Zielgruppenergebnisse schließen Medium-Anomalien aus, wenn der Baseline-Verlauf sehr variabel ist. Jede zurückgegebene Anomalie mit stark variabler Vorgeschichte weist daher eine hohe Risikostufe auf.

Verwenden Sie Risikostufen, um Ermittlungen zu priorisieren, und nicht, um eine Grundursache zu ermitteln.

Beispielsweise werden bei einer Antwort 10 Eingabedatensätze mit einer erwarteten Spanne von eins bis vier als Spitze mit mittlerem Risiko identifiziert. Normalerweise handelt es sich um einen Datensatz, sodass die Abweichung relativ zur Baseline groß ist. Das absolute Volumen bleibt klein.

Prüfen Sie die Ereigniszeiten, bevor Sie eine historische Anomalie als aktuelles Problem behandeln. Ein Ereignis außerhalb der letzten 24 Stunden stellt nicht fest, ob sich die zugrunde liegende Bedingung erholt hat.

<!-- Author review: Confirm flow risk tier definitions and whether persistence is reported. -->

### Baselines und erwartete Bereiche

Stündliche Anomalievergleiche verwenden dieselbe Stunde in den vorherigen 14 Tagen. Dies berücksichtigt stündliche typische Muster, aber keine breitere Saisonabhängigkeit.

Bei Anomalien der Zielgruppe konzentriert sich der erwartete Bereich auf den Median und erweitert sich entsprechend den Variationen in den historischen Zählungen. Wenn die berechnete untere Grenze negativ ist, verwendet der Bereich stattdessen die niedrigste historische Anzahl. Der Bereich kann sich daher weiter über den Median hinaus erstrecken als darunter.

Realisierte Profilzahlen oberhalb des erwarteten Bereichs sind Spitzen. Zahlen unterhalb des Bereichs werden abgesenkt. Wenn normalerweise Profile vorhanden sind, bedeutet dies einen Rückgang mit hohem Risiko.

Die Anzahl der ausgetretenen Profile führt nur zu Spitzenbewertungen. Weniger Austritte werden als normal behandelt, nicht als Tropfenanomalien.

### Keine Anomalien zurückgegeben

In einer Antwort kann berichtet werden, dass für die angeforderte Zielgruppe und den angeforderten Zeitraum keine Anomalien vom Typ Hoch oder Medium zurückgegeben wurden.

![Eine Zusammenfassung einer Zielgruppenanomalie meldet über einen Zeitraum von 168 Stunden keine Anomalien des Typs Hoch oder Medium und enthält eine Warnung zum Ausschlussverlauf.](assets/anomaly-detection/anomaly-detection-no-anomalies.png){width="900" zoomable="yes"}

Dieses Beispiel enthält eine Warnung vor unzureichendem oder größtenteils null Verlauf. Es bestätigt nicht, dass jede Stunde ausgewertet wurde oder dass diese Zielgruppe ausgeschlossen wurde. Der Zielgruppenname und die Kennung werden geschwärzt.

### Unzureichende Baseline-Historie

Der Baseline-Verlauf beeinflusst, ob eine Zielgruppe auf Anomalien ausgewertet werden kann.

Die Zielgruppenanomalieerkennung bewertet keine Zeilen mit einem Verlauf von weniger als fünf Tagen oder einem Verlauf, der überwiegend Nullen enthält.

>[!IMPORTANT]
>
>Keine gemeldeten Anomalien bedeuten nicht, dass jede Ressource ausgewertet wurde. Die Antwort bestätigt möglicherweise nicht, ob eine Zielgruppe ausgewertet oder übersprungen wurde.

<!-- Author review: Confirm flow minimum history requirements and whether audience evaluation status or excluded resources can be retrieved. -->

## Frage verfeinern

Konzentrieren Sie Ihre nächste Frage auf die betroffene Ressource. Fragen Sie beispielsweise nach einer breit angelegten Aufnahmeprüfung nach Anomalien für einen benannten Fluss.

Verlängern Sie den Zeitraum mit dieser Nachverfolgung, nachdem Sie nach den letzten 24 Stunden gefragt haben:

```text
What about in the past two weeks?
```

Die Antwort kann historische Anomalien identifizieren, selbst wenn in den letzten 24 Stunden keine aufgetreten sind.

Für eine genauere Untersuchung fragen Sie nach der Anzahl der Flussausführungen, Fluss-Trends, Zielgruppen-Trends oder derzeit fehlgeschlagenen Aufträgen. Sie können bei der Untersuchung auch nach einzelnen Aufträgen fragen.

Wählen Sie die nächste Frage anhand der benötigten Informationen aus. Trend- und Konsistenzzusammenfassungen liefern keine Anomaliebeurteilungen.

| Ziel | Prompt-Beispiel | Was zu erwarten ist |
| --- | --- | --- |
| Audiences-Trends überprüfen | Wie haben sich meine Zielgruppen in der letzten Woche verändert? | Aktuelle und typische Anzahl qualifizierter und beendeter Profile für die Batch-Segmentierung ohne erwarteten Bereich. |
| Fluss-Trends überprüfen | Wie hat sich das Aufnahmevolumen in der letzten Woche verändert? | Neuer Durchsatz im Vergleich zum typischen Durchsatz, ohne Anomaliebeurteilung. |
| Flusszustand überprüfen | Wie viele Durchgänge sind in den letzten 24 Stunden für meine Aufnahmeflüsse erfolgreich oder fehlgeschlagen? | Deduplizierte Ausführungsanzahl und aggregierte fehlgeschlagene Datensatzsummen ohne Fehlerursachen. |
| Untersuchung fehlgeschlagener Aufträge | Welche Exportvorgänge sind in den letzten 24 Stunden fehlgeschlagen und warum? | Aufträge, deren letzter Status im angeforderten Bereich fehlgeschlagen ist, mit Ursachen für fehlgeschlagene Aufträge. |
| Untersuchen eines Flussfehlers | Was ist der Fehler beim Kundenimport-Fluss? | Fehlerursachen für derzeit fehlgeschlagene Aufträge, die mit dem Fluss verknüpft sind, ohne Details für einzelne Datensätze. |

Der Trend der Zielgruppe wird etwa zwei Wochen lang (336 Stunden) beibehalten. Der typische Wert ist der Median für diese Stunde über die letzten 14 Tage.

Bei derzeit fehlgeschlagenen Aufträgen bedeutet ein leeres Ergebnis, dass derzeit keine Aufträge im angeforderten Bereich fehlschlagen. Dies bedeutet nicht, dass im angeforderten Zeitraum keine Fehler aufgetreten sind. Aufträge, die fehlgeschlagen und später erfolgreich waren, werden ausgeschlossen.

Setzen Sie die Untersuchung mit den Kenntnissen zur Konsistenzprüfung fort, oder verwenden Sie Warnhinweise, um einen Warnhinweis für ein unterstütztes Asset zu aktivieren. Bei diesen Aktionen werden separate Fähigkeiten verwendet, nicht die Anomalieerkennung selbst.

Informationen zu entsprechenden Warnhinweis-Workflows finden Sie unter [Warnhinweise für Kunden](/help/chat/use-cases/customer-alerts/customer-alerts.md).

<!-- Author review: Validate a complete public example response and the supported alert assets and setup before adding an alert procedure. -->

## Metrikreferenz

Die eingeschränkte Version umfasst die folgenden sieben Metriken für die Aufnahme, Segmentierung und Zielaktivierung. Anhand dieser Referenz können Sie die jedem Bereich zugeordneten Zählungen ermitteln.

| Bereich | Metrikkennung | Anzahl gemessen |
| --- | --- | --- |
| Aufnahme | `input_record_count` | Anzahl der Eingabedatensätze für einen Aufnahmefluss. |
| Aufnahme | `failed_record_count` | Anzahl fehlgeschlagener Datensätze für einen Aufnahmefluss. |
| Segmentierung | `__segment_{segment_id}__realized_profiles` | Anzahl der Profile, die für ein Segment qualifiziert sind. |
| Segmentierung | `__segment_{segment_id}__exited_profiles` | Anzahl der Profile, die ein Segment verlassen. |
| Zielaktivierung | `{destination}_input_record_count` | Anzahl der Eingabedatensätze für ein Ziel. |
| Zielaktivierung | `{destination}_skipped_record_count` | Anzahl der übersprungenen Datensätze für ein Ziel. |
| Zielaktivierung | `{destination}_output_record_count` | Anzahl der Ausgabedatensätze für ein Ziel. |

<!-- Author review: Confirm metric aggregation intervals and identifier visibility. -->

## Umfang und Einschränkungen

Verwenden Sie die Anomalieerkennung, um Abweichungen zu identifizieren, aber nicht, um die Grundursache zu bestätigen oder eine Ressource zu reparieren.

Sie können nach Flüssen, Segmenten und Zielen anhand ihres Namens oder ihrer Kennung fragen. Die Erkennung von Flussanomalien umfasst die Aufnahme-, Segmentierungs-, Export- und Zielphasen.

Verwenden Sie die Qualifikation für fehlgeschlagene Aufträge für derzeit fehlgeschlagene Aufträge und deren Fehlerursachen. Behobene Fehler sind ausgeschlossen. Die Auftragsdiagnose enthält keine Details für einzelne Datensätze oder Anomalieurteile.

Die Flussdiagnose liefert aggregierte Zahlen, keine Fehlerursachen. Trendzusammenfassungen beschreiben aktuelle und typische Werte, keine Anomalieurteile. Die Zusammenfassungen der Zielgruppen-Trends decken nur die Batch-Segmentierung ab.

Die Anomalieerkennung ändert Ihre Daten oder Konfiguration nicht. Verwenden Sie separate Fähigkeiten für unterstützte Warnaktionen und tiefer greifende Gesundheitsuntersuchungen.

<!-- Author review: Confirm job identifier support and any recommendation capabilities before adding examples. -->
