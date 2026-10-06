---
title: Verwalten der Data Lake-Aufbewahrung
description: Erfahren Sie, wie Sie mit CX Coworker Erlebnisereignisdaten identifizieren, die optimiert werden sollten, die Auswirkungen auf die Datensatznutzung und -speicherung analysieren und Data-Lake-Aufbewahrungsrichtlinien verwalten können.
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '1316'
ht-degree: 1%
---
# Verwalten der Data Lake-Aufbewahrung

Verwenden Sie CX Coworker, um den Wert von Erlebnisereignisdaten in Ihrer Sandbox zu verstehen und Daten zu identifizieren, die von der Optimierung profitieren können. Sie können mit einer allgemeinen Anfrage beginnen, z. B. mit der Bitte an Kollegen, Ihre Sandbox-Daten zu optimieren oder Datensätze zu bereinigen. Ein Mitarbeiter nutzt den Data Management Agent, um Datensätze darzustellen, die es wert sind, untersucht zu werden, zu analysieren, wie aktiv ein Datensatz verwendet wird, die Auswirkungen einer Aufbewahrungsfrist zu modellieren und Sie bei Bedarf bei der Verwaltung seiner Data-Lake-Aufbewahrungsrichtlinie zu unterstützen.

## Voraussetzungen {#before-you-begin}

Stellen Sie sicher, dass Sie in der Sandbox arbeiten, die die Datensätze enthält, die Sie überprüfen möchten. Sie benötigen außerdem Zugriff auf den Data Management Agent und die erforderlichen Adobe Experience Platform-Berechtigungen. Siehe [Voraussetzungen für den Data Management Agent](https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/agents/data-management#prerequisites).

## Optimieren von Daten in Ihrer Sandbox {#optimize-data-in-your-sandbox}

Verwenden Sie diese Fähigkeiten zusammen als Workflow. Beginnen Sie mit einem umfassenden Ziel für das Daten-Management, z. B. dem Verständnis des Werts Ihrer Daten oder der Optimierung der Daten in Ihrer Sandbox. Mit einem Kollegen können Sie Datensätze ermitteln, die es wert sind, untersucht zu werden, die aktive Verwendung eines Datensatzes zu überprüfen, die Auswirkungen einer potenziellen Aufbewahrungsfrist zu modellieren und dann eine Aufbewahrungsrichtlinie festzulegen, zu ändern oder zu entfernen, wenn Sie bereit sind zu handeln.

### Optimierungswürdige Daten finden {#find-data-worth-optimizing}

Um zu entscheiden, wo Sie anfangen sollen, bitten Sie Ihren Kollegen, Erlebnisereignis-Datensätze zu identifizieren, die es wert sind, untersucht zu werden. Sie können allgemein beginnen, indem Sie nach dem Wert Ihrer Daten, der Datenoptimierung oder der Bereinigung Ihres Datensatzes fragen. Verwenden Sie die Qualifikation Datensätze auflisten , um die Speichergröße, die Zeilenanzahl, den vorhandenen Aufbewahrungsstatus und die Profilaktivierung zu überprüfen. Sie können die Ergebnisse nach Kriterien wie Datensatzgröße, Zeilenanzahl oder letzter Zugriff filtern, um die Liste einzugrenzen. Die Qualifikation ist schreibgeschützt. Coworker gibt eine Tabelle zurück, die Sie scannen und vergleichen können, sowie Visualisierungen, die Datensätze nach Größe, Zeilenanzahl und Datenalter hervorheben.

![Ergebnisse der Zusammenarbeit, die Erlebnisereignis-Datensätze in einer Tabelle mit Speicherung, Zeilenanzahl, Aufbewahrungsinformationen und Visualisierungen der Datensatzgröße und des Datenalters zeigen.](../../assets/data-management/dataset-discovery-results.png)

Sobald Sie die Liste eingegrenzt haben, können Sie die Fähigkeit zur Analyse der Datensatznutzung verwenden, um herauszufinden, wie aktiv ein bestimmter Datensatz verwendet wird.

Nicht jeder ungenutzte oder aufgegebene Datensatz, auf den diese Kenntnisse zutreffen, ist ein guter Kandidat für eine Data-Lake-Aufbewahrungsrichtlinie. Wenn Sie einen ganzen Datensatz entfernen oder Daten in einem anderen Experience Platform-Store verwalten müssen, finden Sie weitere Informationen unter [Auswahl der richtigen Data Lifecycle Management-Funktion](https://experienceleague.adobe.com/de/docs/experience-platform/data-lifecycle/choose-a-capability). Bevor Sie eine Data-Lake-Aufbewahrungsrichtlinie festlegen, überprüfen Sie, ob der Datensatz ein Erlebnisereignis-Datensatz ist.

Beispiel-Eingabeaufforderungen:

- „Ich habe das Gefühl, dass meine Daten optimiert werden können.“
- „Helfen Sie mir, den Wert meiner Daten zu verstehen.“
- „Optimieren Sie meine Sandbox-Daten.“
- „Meine Sandbox-Datensätze bereinigen.“
- „Zeigen Sie mir meine größten Ereignisdatensätze.“
- „Anzeigen von Datensätzen mit mehr als 100 GB, für die kein Data-Lake-Aufbewahrungssatz festgelegt ist.“
- „Ich muss etwa 2 TB Daten entfernen. Wo soll ich anfangen?“
- „Können Sie mir helfen, Daten zu finden, die verwaist, verlassen oder ungenutzt sind?“
- „Priorisieren Sie Datensätze, auf die in den letzten 90 Tagen nicht zugegriffen wurde.“

### Überprüfen, wie aktiv ein Datensatz verwendet wird {#check-how-actively-a-dataset-is-used}

Bevor Sie entscheiden, ob ein Datensatz ein guter Kandidat für eine Data-Lake-Aufbewahrungsrichtlinie ist, sollten Sie herausfinden, wie aktiv der Datensatz verwendet wird. Verwenden Sie die Fähigkeit zur Datensatznutzung analysieren , um einen bestimmten Datensatz über mehrere Nutzungssignale hinweg zu bewerten. Zu diesen Signalen gehören die aktuelle Aufnahmeaktivität, die Abfrageaktivität, die Schemastabilität und die Frage, ob der Datensatz andere Adobe Experience Platform-Programme befüllt. Die Qualifikation ist schreibgeschützt. Der Coworker gibt eine allgemeine Nutzungsebene, eine Aufschlüsselung der Signale und eine einfache Zusammenfassung der Informationen zurück, die sie über den Datensatz angeben.

<!-- TODO: Confirm the final usage-tier thresholds with engineering after the planned update from a 7-day to a 30-day analysis window is complete. Update this section with the final definitions before publishing. -->

>[!NOTE]
>
>Die angezeigten Metriken sollen hilfreiche Signale geben und stellen möglicherweise nicht alle für Ihre Entscheidung relevanten Faktoren dar. Es wird empfohlen, die verfügbaren Details zu überprüfen und Ihren Geschäftskontext anzuwenden, bevor Sie Maßnahmen ergreifen.

![Analyse der Datensatznutzung durch Kollegen mit Nutzungsstufe, individuellen Nutzungssignalen und einer Zusammenfassung der Datensatzaktivität.](../../assets/data-management/dataset-usage-analysis.png)

Beispiel-Eingabeaufforderungen:

- „Wie aktiv wird mein Web-Ereignis-Datensatz verwendet?“

### Modellieren der Auswirkungen einer Aufbewahrungsfrist {#model-the-impact-of-a-retention-period}

Bevor Sie sich für eine bestimmte Aufbewahrungsfrist entscheiden, sollten Sie herausfinden, wie viele Daten aufbewahrt oder entfernt werden. Verwenden Sie die Fähigkeit zur Datensatzaufbewahrung analysieren , um die Speichermetriken eines Datensatzes und die Altersverteilung seiner Daten zu überprüfen. Anschließend wird anhand dieser Verteilung modelliert, wie viele Daten eine vorgeschlagene Aufbewahrungsfrist beibehalten oder entfernen würde. Kollege zeigt die geschätzte Auswirkung nach Zeilenanzahl und Speichergröße an.

![Kollege, der die Anzahl der Zeilen vergleicht, die für Aufbewahrungszeiträume von 30, 60 und 90 Tagen beibehalten und entfernt wurden.](../../assets/data-management/retention-period-comparison.png)

Die Qualifikation ist schreibgeschützt. Ein Mitarbeiter gibt die Daten- und Wirkungsanalyse direkt im Gespräch zurück, sodass Sie die Ergebnisse mit den aktuellen Aufbewahrungseinstellungen des Datensatzes vergleichen können, bevor Sie entscheiden, ob Sie sie ändern möchten.

Beispiel-Eingabeaufforderungen:

- „Was wären die Auswirkungen, wenn ich für diesen Datensatz eine Aufbewahrungsfrist von 60 Tagen festlegen würde?“

### Festlegen, Ändern oder Entfernen einer Aufbewahrungsrichtlinie {#set-change-or-remove-a-retention-policy}

>[!IMPORTANT]
>
>Die Aufbewahrungsfrist für den Data Lake beträgt mindestens 30 Tage. Kürzere Zeiträume werden nicht unterstützt.

Sobald Sie sich für eine Aufbewahrungsfrist entschieden haben, verwenden Sie die Fähigkeit zur Verwaltung der Datensatzaufbewahrung , um eine Data Lake-Aufbewahrungsrichtlinie für einen Datensatz festzulegen, zu ändern oder zu entfernen. Die Kenntnis zeigt Ihnen die vorgeschlagene Auswirkung, bevor eine Änderung angewendet wird. Die Richtlinie wird erst angewendet, nachdem Sie die Anfrage ausdrücklich genehmigt haben. Bei einer Beschreibung der gewünschten Änderung wird sie nicht angewendet.

![Mitarbeiter, der die vorgeschlagene Data-Lake-Aufbewahrungsrichtlinie, ihre Auswirkungen und die erforderliche Bestätigung anzeigt, bevor die Änderung angewendet wird.](../../assets/data-management/retention-impact-preview.png)

Nachdem Sie eine Aufbewahrungsrichtlinie bestätigt haben, kann es einige Zeit dauern, bis die Änderung in der Adobe Experience Platform-Benutzeroberfläche angezeigt wird. Die Aufbewahrungsrichtlinie löscht abgelaufene Daten nicht sofort. Der anfängliche Aufbewahrungsauftrag beginnt innerhalb von 24 Stunden nach der Anwendung der Richtlinie. Nach dem ersten Durchlauf bewertet und löscht ein geplanter Auftrag abgelaufene Datensätze alle 30 Tage. Weitere Informationen [&#x200B; Aufbewahrung und Bereinigung finden Sie &#x200B;](https://experienceleague.adobe.com/de/docs/experience-platform/catalog/datasets/experience-event-dataset-retention-ttl-guide) Handbuch zur Erlebnisereignis-Datensatzaufbewahrung (TTL) .

Jede Änderung der Aufbewahrungsrichtlinie wird in einem Audit-Protokoll aufgezeichnet, auch wenn eine Richtlinie festgelegt, geändert oder entfernt wird. Das Audit-Protokoll zeichnet auf, wer jede Änderung vorgenommen hat, wann sie stattgefunden hat und was geändert wurde. Sie können dem Link folgen, der von einem Kollegen bereitgestellt wurde, um diese Ereignisse auf der Registerkarte Administratorprotokoll des Datensatzes in Adobe Experience Platform zu überprüfen. Weitere Informationen finden Sie unter [Übersicht über Auditprotokolle](https://experienceleague.adobe.com/de/docs/experience-platform/landing/governance-privacy-security/audit-logs/overview).

![Adobe Experience Platform-Administratorprotokoll, das eine Aktualisierung der Data-Lake-Aufbewahrungsrichtlinie einschließlich Zeitstempel, Benutzer, Datensatz, Aktion und Status anzeigt.](../../assets/data-management/retention-audit-log.png)

Beispiel-Eingabeaufforderungen:

- „Legen Sie die Aufbewahrung für diesen Datensatz auf 60 Tage fest.“
- „Entfernen Sie die Aufbewahrungsrichtlinie für diesen Datensatz.“

## Best Practices {#best-practices}

Beachten Sie bei der Verwendung des Data Management-Agenten die folgenden Best Practices:

- **Beginnen Sie mit einem allgemeinen Ziel.** Wenn Sie nicht wissen, welcher Datensatz Aufmerksamkeit erfordert, bitten Sie Ihren Kollegen, den Wert Ihrer Daten zu verstehen oder Daten in Ihrer Sandbox zu optimieren. Verwenden Sie die Fähigkeit Datensätze auflisten , um Datensätze mit Signalen zu identifizieren, die auf eine niedrige oder keine aktuelle Nutzung hindeuten, bevor Sie einen einzelnen Datensatz analysieren.
- **Überprüfen Sie die Auswirkungsvorschau, bevor Sie bestätigen.** Überprüfen Sie, was beibehalten und entfernt wird, bevor Sie eine Aufbewahrungsänderung genehmigen.
- **Lassen Sie die Zeit zu, in der Änderungen angezeigt werden.** Nachdem Sie eine Aufbewahrungsänderung in CX Coworker bestätigt haben, gewähren Sie der Adobe Experience Platform-Benutzeroberfläche eine kurze Zeit, um die Änderung widerzuspiegeln.

## Nächste Schritte {#next-steps}

Weitere Informationen zu den Fähigkeiten, dem Umfang, dem Verhalten und den Einschränkungen des Datenverwaltungsagenten finden Sie unter [Übersicht über den Datenverwaltungsagenten](https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/agents/data-management). Weitere Informationen zur Funktionsweise von Data-Lake-Aufbewahrungsrichtlinien in Adobe Experience Platform finden Sie [&#x200B; Handbuch zur Erlebnisereignis-Datensatzaufbewahrung (Experience Event Dataset Retention, TTL)](https://experienceleague.adobe.com/de/docs/experience-platform/catalog/datasets/experience-event-dataset-retention-ttl-guide).
