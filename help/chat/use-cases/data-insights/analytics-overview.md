---
title: Analysieren von Customer Journey Analytics-Daten mit dem Coworker Chat
description: Erfahren Sie, wie Sie mit dem Adobe CX Enterprise Coworker-Chat Customer Journey Analytics-Daten analysieren, Trichter erstellen und herausfinden können, wo Kundinnen und Kunden auf der Journey abbrechen.
hold: true
product_v2:
  internal-label: CX Enterprise Coworker
feature_v2:
  internal-label: CX Enterprise Coworker
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '2354'
ht-degree: 0%
---

Adobe CX Enterprise Coworker Chat ermöglicht es Teams, Adobe-Produktaufgaben mithilfe natürlicher Sprache zu automatisieren und Ideen schnell in Maßnahmen mit flexibler Planung, anpassbaren Fähigkeiten und intelligenter Ausführung zu verwandeln. Weitere allgemeine Informationen zu Kollegen finden Sie unter [Übersicht über CX Enterprise Coworker](/help/home.md).

## Datenanalyse mit Coworker Chat

Coworker Chat kann erweiterte Datenanalysen durchführen, die zuvor nur in Analysis Workspace möglich waren. Coworker Chat greift auf Daten aus Ihren Customer Journey Analytics-Datenansichten oder Adobe Analytics-Report Suites zu, sodass Sie diese Daten untersuchen und Antworten auf Eingabeaufforderungen in natürlicher Sprache erhalten können.

Wenn Sie eine Visualisierung im Coworker Chat erstellen, können Sie sie jederzeit in Analysis Workspace öffnen, um eine manuelle Kontrolle zu erhalten.

Die folgenden Informationen bieten einen Überblick darüber, wie Sie Daten im Coworker Chat analysieren können.

## Analysieren im Kollegen-Chat beginnen

Beginnen Sie, indem Sie beschreiben, was Sie wissen möchten, in einfacher Sprache. Der Coworker Chat plant die Analyse, fragt Ihre Datenansichten oder Report Suites ab und erstellt Visualisierungen und Zusammenfassungen.

Die folgenden Anwendungsfälle sind Beispiele. Sie können nach allen Daten fragen, für die Sie Zugriffsberechtigungen haben

### Häufige Anwendungsfälle

<!-- The following cards link to each of the stand-alone articles in this folder -->

<!--
CARDS

* https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat
  {title = Analyze Customer Journey Analytics and Adobe Analytics data}
  {description = Answers natural-language questions about your data views or report suites, builds funnels and other visualizations, and finds where customers drop off. You can open any visualization in Analysis Workspace for further analysis.}
  {cta = Read}
  {image = ../../assets/coworker-funnel-response-card.png}

* https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis
  {title = Explore trends and root causes}
  {description = Identifies trends in your Customer Journey Analytics and Adobe Analytics data and the factors that drive changes in performance, without manual queries.}
  {cta = Read}
  {image = ../../assets/data-validation-aa-cja/trend-line-card.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Analyze Customer Journey Analytics and Adobe Analytics data">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" title="Analysieren von Customer Journey Analytics- und Adobe Analytics-Daten">
                        <img class="is-bordered-r-small" src="../../assets/coworker-funnel-response-card.png" alt="Analysieren von Customer Journey Analytics- und Adobe Analytics-Daten"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" title="Analysieren von Customer Journey Analytics- und Adobe Analytics-Daten">Analysieren von Customer Journey Analytics- und Adobe Analytics-Daten</a>
                    </p>
                    <p class="is-size-6">Beantwortet Fragen in natürlicher Sprache zu Ihren Datenansichten oder Report Suites, erstellt Trichter und andere Visualisierungen und findet heraus, wo Kunden abbrechen. Sie können eine beliebige Visualisierung in Analysis Workspace zur weiteren Analyse öffnen.</p>
                </div>
                <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lesen</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Explore trends and root causes">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" title="Trends und Grundursachen untersuchen">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aa-cja/trend-line-card.png" alt="Trends und Grundursachen untersuchen"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" title="Trends und Grundursachen untersuchen">Erkunden von Trends und Grundursachen</a>
                    </p>
                    <p class="is-size-6">Identifiziert Trends in Ihren Customer Journey Analytics- und Adobe Analytics-Daten und die Faktoren, die zu Leistungsänderungen führen, ohne manuelle Abfragen.</p>
                </div>
                <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lesen</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

<!--
CARDS

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/implementation-guide
  {title = Plan your implementation}
  {description = Creates a personalized, step-by-step plan for implementing Customer Journey Analytics, upgrading from Adobe Analytics, or setting up Content Analytics, Marketing Campaign Analytics, or Streaming Media collection on the Edge. Plans include details such as owners, effort estimates, dependencies, and validation steps.}
  {cta = Read}
  {image = ../../assets/ui-guide-6.png}

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/intelligent-checklist
  {title = Generate an implementation checklist}
  {description = Turns your Customer Journey Analytics implementation plan into a checklist in Coworker Projects, where your team can assign steps, track status, and add approval gates.}
  {cta = Read}
  {image = ../../assets/data-validation-aa-cja/date-detail.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Plan your implementation">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/implementation-guide" title="Implementierung planen">
                        <img class="is-bordered-r-small" src="../../assets/ui-guide-6.png" alt="Implementierung planen"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/implementation-guide" title="Implementierung planen">Implementierung planen</a>
                    </p>
                    <p class="is-size-6">Erstellt einen personalisierten, schrittweisen Plan für die Implementierung von Customer Journey Analytics, die Aktualisierung von Adobe Analytics oder die Einrichtung von Content Analytics, Marketing Campaign Analytics oder Streaming Media Collection auf der Edge. Die Pläne enthalten Details wie Eigentümer, Aufwandsschätzungen, Abhängigkeiten und Validierungsschritte.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/implementation-guide" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lesen</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Generate an implementation checklist">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/intelligent-checklist" title="Erstellen einer Checkliste für die Implementierung">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aa-cja/date-detail.png" alt="Erstellen einer Checkliste für die Implementierung"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/intelligent-checklist" title="Erstellen einer Checkliste für die Implementierung">Erstellen einer Checkliste für die Implementierung</a>
                    </p>
                    <p class="is-size-6">Wandelt Ihren Customer Journey Analytics-Implementierungsplan in eine Checkliste in Co-Worker-Projekten um, in der Ihr Team Schritte zuweisen, den Status verfolgen und Validierungs-Gates hinzufügen kann.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/intelligent-checklist" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lesen</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

<!--
CARDS

* https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja
  {title = Validate data when upgrading from Adobe Analytics to Customer Journey Analytics}
  {description = Compares dimensions, metrics, and trends between your Adobe Analytics report suites and Customer Journey Analytics data views, then recommends fixes to support your upgrade.}
  {cta = Read}
  {image = ../../assets/data-validation-aa-cja/trend-bar-card.png}

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/streaming-media-validation
  {title = Validate your Streaming Media implementation}
  {description = Checks your datastream, schema, dataset, data view, and session data to confirm that streaming media tracking is configured and collecting data correctly.}
  {cta = Read}
  {image = ../../assets/ui-guide-8.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate data when upgrading from Adobe Analytics to Customer Journey Analytics">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" title="Validieren von Daten beim Upgrade von Adobe Analytics auf Customer Journey Analytics">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aa-cja/trend-bar-card.png" alt="Validieren von Daten beim Upgrade von Adobe Analytics auf Customer Journey Analytics"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" title="Validieren von Daten beim Upgrade von Adobe Analytics auf Customer Journey Analytics">Validieren von Daten beim Upgrade von Adobe Analytics auf Customer Journey Analytics</a>
                    </p>
                    <p class="is-size-6">Vergleicht Dimensionen, Metriken und Trends zwischen Ihren Adobe Analytics Report Suites und Customer Journey Analytics-Datenansichten und empfiehlt dann Fehlerbehebungen, um Ihr Upgrade zu unterstützen.</p>
                </div>
                <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lesen</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate your Streaming Media implementation">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/streaming-media-validation" title="Validieren der Implementierung von Streaming-Medien">
                        <img class="is-bordered-r-small" src="../../assets/ui-guide-8.png" alt="Validieren der Implementierung von Streaming-Medien"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/streaming-media-validation" title="Validieren der Implementierung von Streaming-Medien">Validieren der Implementierung von Streaming-Medien</a>
                    </p>
                    <p class="is-size-6">Überprüft Ihren Datenstrom, Ihr Schema, Ihren Datensatz, Ihre Datenansicht und Ihre Sitzungsdaten, um sicherzustellen, dass das Tracking von Streaming-Medien konfiguriert ist und die Daten korrekt erfasst werden.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/streaming-media-validation" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lesen</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

<!--
CARDS

* https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja
  {title = Validate dataset quality for Customer Journey Analytics}
  {description = Identifies the datasets that feed your Customer Journey Analytics reporting, then checks schemas, identity quality, and field quality so you can resolve issues before you build dashboards.}
  {cta = Read}
  {image = ../../assets/data-validation-aep/dataset-validation.png}

* https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aep
  {title = Validate data after ingestion into Experience Platform}
  {description = Runs statistical and semantic checks on Experience Platform datasets and fields to find data quality issues, such as invalid values or mapping problems.}
  {cta = Read}
  {image = ../../assets/data-validation-aep/null-values.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate dataset quality for Customer Journey Analytics">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" title="Überprüfen der Datensatzqualität für Customer Journey Analytics">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aep/dataset-validation.png" alt="Überprüfen der Datensatzqualität für Customer Journey Analytics"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" title="Überprüfen der Datensatzqualität für Customer Journey Analytics">Validieren der Datensatzqualität für Customer Journey Analytics</a>
                    </p>
                    <p class="is-size-6">Identifiziert die Datensätze, die Ihre Customer Journey Analytics-Berichte unterstützen, prüft dann Schemata, Identitätsqualität und Feldqualität, damit Sie Probleme beheben können, bevor Sie Dashboards erstellen.</p>
                </div>
                <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lesen</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate data after ingestion into Experience Platform">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aep" title="Validieren von Daten nach der Aufnahme in Experience Platform">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aep/null-values.png" alt="Validieren von Daten nach der Aufnahme in Experience Platform"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aep" title="Validieren von Daten nach der Aufnahme in Experience Platform">Validieren von Daten nach der Aufnahme in Experience Platform</a>
                    </p>
                    <p class="is-size-6">Führt statistische und semantische Prüfungen für Experience Platform-Datensätze und -Felder durch, um Probleme mit der Datenqualität zu ermitteln, z. B. ungültige Werte oder Zuordnungsprobleme.</p>
                </div>
                <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aep" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lesen</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

Weitere Informationen zu diesen Anwendungsfällen, einschließlich der von ihnen verwendeten Fähigkeiten und Beispielaufforderungen, finden Sie unter [Anwendungsfälle für Dateneinblicke](/help/chat/use-cases/overview.md#data-insights).

### Erste Schritte

Der Coworker Chat kann Ihnen auch helfen:

* **Leistung vergleichen**: Metriken über Kanäle, Zeiträume oder Segmente hinweg nebeneinander vergleichen.
* **Kampagnenleistung messen**: Sehen Sie, wie Kampagnen, Kanäle und Web-Eigenschaften über einen bestimmten Zeitraum ausgeführt wurden.
* **Trichter analysieren**: Durchlaufen Sie mehrstufige Konversionstrichter und sehen Sie sich den Abbruch in jedem Stadium an.
* **Prognosemetriken**: Projizieren Sie zukünftige Metrikwerte aus historischen Customer Journey Analytics- oder Adobe Analytics-Daten, z. B. ob Sie auf dem richtigen Weg sind, um ein Umsatzziel zu erreichen.
* **Zusammenfassungen für Führungskräfte und KPI-Zusammenfassungen erstellen**: Erstellen Sie einsatzbereite Leistungszusammenfassungen, Empfehlungen und Folienübersichten.
* **Analysieren Sie operative Trends und**: Fragen Sie historische Zeitreihendaten nach Zielgruppen, Datensätzen und Journey ab und identifizieren Sie, was zu einer Änderung geführt hat.
* **Erstellen benutzerdefinierter Customer Journey Analytics-Kenntnisse**: Wandeln Sie eine Analyse, die Sie wiederholen, in eine wiederverwendbare Fähigkeit um, die sitzungsübergreifend persistent ist.

<!--
CARDS

* https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat
  {title = Analyze data with Coworker Chat}
  {description = Ask questions in natural language to build funnels, create visualizations, and find where customers drop off in the journey.}
  {cta = Read}
  {image = ../../assets/coworker-funnel-response-card.png}

* https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis
  {title = Explore trends and root causes}
  {description = Investigate changes in your Customer Journey Analytics data and uncover what drives them, without writing manual queries.}
  {cta = Read}
  {image = ../../assets/data-validation-aa-cja/trend-line-card.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Analyze data with Coworker Chat">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" title="Analysieren von Daten mit dem Kollegen-Chat">
                        <img class="is-bordered-r-small" src="../../assets/coworker-funnel-response-card.png" alt="Analysieren von Daten mit dem Kollegen-Chat"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" title="Analysieren von Daten mit dem Kollegen-Chat">Analysieren von Daten mit dem Kollegen-Chat</a>
                    </p>
                    <p class="is-size-6">Stellen Sie Fragen in natürlicher Sprache, um Trichter zu erstellen, Visualisierungen zu erstellen und herauszufinden, wo Kunden auf dem Journey abbrechen.</p>
                </div>
                <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lesen</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Explore trends and root causes">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" title="Trends und Grundursachen untersuchen">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aa-cja/trend-line-card.png" alt="Trends und Grundursachen untersuchen"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" title="Trends und Grundursachen untersuchen">Erkunden von Trends und Grundursachen</a>
                    </p>
                    <p class="is-size-6">Untersuchen Sie Änderungen an Ihren Customer Journey Analytics-Daten und entdecken Sie, was sie antreibt, ohne manuelle Abfragen zu schreiben.</p>
                </div>
                <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lesen</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

<!--
CARDS

* https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja
  {title = Validate Customer Journey Analytics data}
  {description = Check dataset quality with the data validation skill and resolve issues before you build dashboards.}
  {cta = Read}
  {image = ../../assets/data-validation-aep/dataset-validation.png}

* https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja
  {title = Validate data during your upgrade}
  {description = Compare Adobe Analytics and Customer Journey Analytics data to confirm that your upgrade is on track.}
  {cta = Read}
  {image = ../../assets/data-validation-aa-cja/trend-bar-card.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate Customer Journey Analytics data">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" title="Validieren von Customer Journey Analytics-Daten">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aep/dataset-validation.png" alt="Validieren von Customer Journey Analytics-Daten"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" title="Validieren von Customer Journey Analytics-Daten">Validieren von Customer Journey Analytics-Daten</a>
                    </p>
                    <p class="is-size-6">Überprüfen Sie die Datensatzqualität mit den Datenvalidierungsfähigkeiten und beheben Sie Probleme, bevor Sie Dashboards erstellen.</p>
                </div>
                <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lesen</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate data during your upgrade">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" title="Validieren von Daten während des Upgrades">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aa-cja/trend-bar-card.png" alt="Validieren von Daten während des Upgrades"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" title="Validieren von Daten während des Upgrades">Validieren von Daten während des Upgrades</a>
                    </p>
                    <p class="is-size-6">Vergleichen Sie Adobe Analytics- und Customer Journey Analytics-Daten, um zu bestätigen, dass Ihr Upgrade planmäßig verläuft.</p>
                </div>
                <a href="https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lesen</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->



## Tabellenlayout der wichtigsten Anwendungsfälle

<!-- The following table are links to each of the stand-alone articles in this folder -->

| Anwendungsfall | Beschreibung |
| --- | --- |
| [Analysieren von Customer Journey Analytics- und Adobe Analytics-Daten](/help/chat/use-cases/data-insights/analytics-chat.md) | Beantwortet Fragen in natürlicher Sprache zu Ihren Datenansichten oder Report Suites, erstellt Trichter und andere Visualisierungen und findet heraus, wo Kunden abbrechen. Sie können eine beliebige Visualisierung in Analysis Workspace zur weiteren Analyse öffnen. |
| [Erkunden von Trends und Grundursachen](/help/chat/use-cases/data-insights/root-cause-analysis.md) | Identifiziert Trends in Ihren Customer Journey Analytics- und Adobe Analytics-Daten und die Faktoren, die zu Leistungsänderungen führen, ohne manuelle Abfragen. |
| [Implementierung planen](/help/chat/use-cases/data-insights/implementation-guide.md) | Erstellt einen personalisierten, schrittweisen Plan für die Implementierung von Customer Journey Analytics, die Aktualisierung von Adobe Analytics oder die Einrichtung von Content Analytics, Marketing Campaign Analytics oder Streaming Media Collection auf der Edge. Die Pläne enthalten Details wie Eigentümer, Aufwandsschätzungen, Abhängigkeiten und Validierungsschritte. |
| [Erstellen einer Checkliste für die Implementierung](/help/chat/use-cases/data-insights/intelligent-checklist.md) | Wandelt Ihren Customer Journey Analytics-Implementierungsplan in eine Checkliste in Co-Worker-Projekten um, in der Ihr Team Schritte zuweisen, den Status verfolgen und Validierungs-Gates hinzufügen kann. |
| [Validieren von Daten beim Upgrade von Adobe Analytics auf Customer Journey Analytics](/help/chat/use-cases/data-insights/data-validation-aa-cja.md) | Vergleicht Dimensionen, Metriken und Trends zwischen Ihren Adobe Analytics Report Suites und Customer Journey Analytics-Datenansichten und empfiehlt dann Fehlerbehebungen, um Ihr Upgrade zu unterstützen. |
| [Validieren der Implementierung von Streaming-Medien](/help/chat/use-cases/data-insights/streaming-media-validation.md) | Überprüft Ihren Datenstrom, Ihr Schema, Ihren Datensatz, Ihre Datenansicht und Ihre Sitzungsdaten, um sicherzustellen, dass das Tracking von Streaming-Medien konfiguriert ist und die Daten korrekt erfasst werden. |
| [Validieren der Datensatzqualität für Customer Journey Analytics](/help/chat/use-cases/data-insights/validate-dataset-quality-for-cja.md) | Identifiziert die Datensätze, die Ihre Customer Journey Analytics-Berichte unterstützen, prüft dann Schemata, Identitätsqualität und Feldqualität, damit Sie Probleme beheben können, bevor Sie Dashboards erstellen. |
| [Validieren von Daten nach der Aufnahme in Experience Platform](/help/chat/use-cases/data-insights/data-validation-aep.md) | Führt statistische und semantische Prüfungen für Experience Platform-Datensätze und -Felder durch, um Probleme mit der Datenqualität zu ermitteln, z. B. ungültige Werte oder Zuordnungsprobleme. |

Weitere Informationen zu diesen Anwendungsfällen, einschließlich der von ihnen verwendeten Fähigkeiten und Beispielaufforderungen, finden Sie unter [Anwendungsfälle für Dateneinblicke](/help/chat/use-cases/overview.md#data-insights).

