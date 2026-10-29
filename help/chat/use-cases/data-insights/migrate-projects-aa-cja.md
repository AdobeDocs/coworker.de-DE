---
title: Migrieren von Adobe Analytics-Projekten nach Customer Journey Analytics
description: Verwenden Sie einen Kollegen, um Adobe Analytics Workspace-Projekte und ihre Komponenten zu Customer Journey Analytics zu validieren, zuzuordnen und zu migrieren, und überprüfen Sie dann den Migrationsstatus.
feature: AI Tools
role: Admin
level: Intermediate
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 1ec3a8bf6dff44df068529cf1f7ceb699a027d65
workflow-type: tm+mt
source-wordcount: '1785'
ht-degree: 1%
---

# Migrieren von Adobe Analytics-Projekten nach Customer Journey Analytics mit Coworker

<!-- FLAG: Confidence: High for the conversation flow, which is sourced from screenshots of the Coworker UI (October 2026) and the aa-mcp tool descriptions. The component migration tools run through the aa-mcp integration; there's no dedicated skill yet. Medium for statements that Coworker shares mappings and migration rules with migrations in the Adobe Analytics user interface; the user believes this is likely. Confirm with engineering. -->

Verwenden Sie Adobe CX Enterprise Coworker, um Adobe Analytics-Projekte und ihre zugehörigen Komponenten in einer einzigen Konversation nach Customer Journey Analytics zu migrieren.

Der Mitarbeiter prüft, ob die Dimensionen und Metriken in Ihrem Projekt Ihrer Customer Journey Analytics-Datenansicht zugeordnet sind. Er unterstützt Sie beim Zuordnen von Dimensionen und Metriken, die dies nicht sind, und erstellt dann das Projekt in Customer Journey Analytics neu.

<!-- FLAG: Add the planned general availability date when it's confirmed. -->

>[!AVAILABILITY]
>
>Die in diesem Artikel beschriebene Funktion befindet sich in der eingeschränkten Testphase der Veröffentlichung und ist möglicherweise noch nicht in Ihrer Umgebung verfügbar. Dieser Hinweis wird entfernt, wenn die Funktion allgemein verfügbar ist.

>[!IMPORTANT]
>
>Bevor Sie Projekte migrieren, lesen Sie [Vorbereiten der Migration von Komponenten und Projekten von Adobe Analytics nach Customer Journey Analytics](https://experienceleague.adobe.com/de/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration) in der Dokumentation zu Adobe Analytics. Es wird erläutert, wie Sie sich auf eine Migration vorbereiten, was enthalten ist, welche Elemente Fehler verursachen und wie sich Zuordnungen auf Ihr gesamtes Unternehmen auswirken. Diese Informationen gelten für Migrationen in Kollegen.

## Unterschiede zur Migration in der Benutzeroberfläche von Adobe Analytics

<!-- FLAG: Add rows as differences are confirmed. Who can migrate and How you migrate: SME Scott Tomko (October 2026); Coworker matches the Analytics 2.0 Component Migration APIs, and functionally both methods do much the same thing. Project owner: Coworker behavior is from a test conversation (October 2026); the Adobe Analytics user interface behavior is from component-migration.md in the Adobe Analytics docs. Mapping dimensions and metrics: Confidence Medium for the Coworker column, which is based on the aa-mcp tool descriptions and a test conversation, not on an observed failed validation. Confirm that Coworker suggests and updates mappings, and whether it asks for confirmation before it updates a mapping. The Adobe Analytics user interface behavior is from component-migration.md in the Adobe Analytics docs. -->

Das Migrieren von Projekten mit Coworker unterscheidet sich wie folgt von der Migration in der Adobe Analytics-Benutzeroberfläche:

| | Coworker | Benutzeroberfläche von Adobe Analytics |
| --- | --- | --- |
| **Wer kann Projekte migrieren** | Adobe Analytics-Administratoren und Anwender mit der Berechtigung [!UICONTROL **Komponentenmigration**] | Nur Adobe Analytics-Administratoren |
| **Projektbesitzer** | Der Benutzer, der die Migration durchführt | Der Benutzer, den Sie im Feld [!UICONTROL **Projektbesitzer**] angeben |
| **Zuordnen von Dimensionen und** | Ein Mitarbeiter validiert das Projekt und listet auf, wie jede Dimension und Metrik zugeordnet wird. Für alle Metriken, die nicht automatisch zugeordnet werden können, schlägt ein Mitarbeiter eine Dimension oder Metrik in Ihrer Datenansicht vor und aktualisiert die Zuordnung. | Im Abschnitt [!UICONTROL **Zuordnungsschema**] wählen Sie jede Dimension oder Metrik mit dem Status [!UICONTROL **Nicht zugeordnet**] aus und ordnen sie manuell zu. |
| **Wie Sie migrieren** | Beschreiben Sie in einer Eingabeaufforderung, was Sie möchten. Ein Kollege erledigt die Arbeit und stellt dabei ein paar Fragen. Beispielsweise kann ein Mitarbeiter ein Projekt mit den von Ihnen benannten Komponenten erstellen und es dann migrieren. Siehe [Mit bestimmten Komponenten beginnen](#start-from-specific-components). | Erstellen Sie ein Projekt in Analysis Workspace, fügen Sie die zu migrierenden Komponenten hinzu und speichern Sie das Projekt. Wählen Sie dann [!UICONTROL **Komponentenmigration**] das Projekt aus, geben Sie einen Projektbesitzer an, ordnen Sie das Schema für jede Report Suite zu und wählen Sie [!UICONTROL **Migrieren**] aus. |

## Voraussetzungen

<!-- FLAG: Confidence: High for the Adobe Analytics MCP and permission bullets, which come from the release announcement and SME Scott Tomko (October 2026): like the Analytics 2.0 Component Migration APIs, Coworker lets non-admins with the Component Migration permission migrate projects, while the Adobe Analytics UI is admin-only. Open question: Coworker makes the user who runs the migration the owner of the new project, but the aa-mcp tool description says the owner "should be an admin" and the Adobe Analytics component migration docs say the owner must be a Customer Journey Analytics administrator. Confirm whether a non-admin who runs a migration needs Customer Journey Analytics admin rights, or whether Coworker assigns a different owner. -->

Um Projekte mit Coworker zu migrieren, benötigen Sie Folgendes:

* Zugriff auf das Adobe Analytics MCP. Die Tools zur Komponentenmigration werden automatisch für Kunden aktiviert, die Zugriff auf Adobe Analytics MCP haben. Um zu bestätigen, dass [!UICONTROL **aa-mcp**] verbunden ist, lesen Sie [Erste Schritte mit der Datenanalyse mit dem Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).

* Adobe Analytics-Administratorrechte oder die Berechtigung [!UICONTROL **Komponentenmigration**] in der Admin Console. Sie müssen kein Administrator sein.

* Die [Voraussetzungen](https://experienceleague.adobe.com/de/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#prerequisites) für die Komponentenmigration finden Sie in der Dokumentation zu Adobe Analytics .

* Ein Projekt, das zugrunde liegende Report Suites verwendet. Virtual Report Suites können nicht migriert werden.<!-- FLAG: Sourced from Coworker's response in the UI. The Adobe Analytics component migration docs don't mention virtual report suites. Confirm, and consider adding it to those docs. -->

## Überprüfen der Report Suite-Zuordnungen vor der Migration

<!-- FLAG: Confidence: Medium. The recommendation to review mappings before the first migration from a report suite is inferred from the Adobe Analytics guidance to decide mappings as an organization; Coworker also validates mappings during each migration. Confirm with Scott. -->

Erwägen Sie, vor Ihrer ersten Migration aus dieser Report Suite zu überprüfen, wie die Dimensionen und Metriken einer Report Suite zugeordnet werden. Zuordnungen gelten für jedes Projekt, das Ihre Organisation migriert. Daher hilft es später Projekten, die Validierung zu bestehen, wenn sie zuerst festgelegt werden. Anleitungen für die Auswahl von Zuordnungen finden Sie unter [Entscheidung, wie Sie Komponenten zuordnen](https://experienceleague.adobe.com/de/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#decide-as-an-organization-how-you-will-map-components) in der Dokumentation zu Adobe Analytics.

Um Zuordnungen zu überprüfen, wählen Sie [!UICONTROL **Nur Zuordnungen überprüfen**] auf der Registerkarte [!UICONTROL **Umfang**] aus oder fragen Sie den Kollegen direkt:

**Eingabeaufforderungen**

* „Mir zeigen, wie die Dimensionen und Metriken in meiner Report Suite meiner Datenansicht zugeordnet sind“
* „Welche Dimensionen und Metriken in meiner Report Suite werden meiner Datenansicht nicht zugeordnet?“

Sie können Ihre Kollegen auch bitten, die Zuordnungen zu aktualisieren.

Wenn Sie diese Überprüfung überspringen, prüft [&#x200B; die Zuordnungen für jedes Projekt, das Sie migrieren](#review-the-validation-results-and-mappings).

## Starten einer Migration

<!-- FLAG: Confidence: High that migration works at the project level and that components migrate with their project (component-migration.md in the Adobe Analytics docs), and that components that already exist in Customer Journey Analytics aren't re-created (prepare-component-migration.md). Medium-low for when to use each method and for combining them; this guidance is inferred and isn't in the Adobe Analytics docs. Confirm with Scott. Also confirm whether Coworker creates a project automatically when you ask it to migrate only components (for example, "Migrate my Spring sale segments to CJA"), or whether you must ask it to create the project. -->

Ein Mitarbeiter migriert immer ein Projekt und die zugehörigen Komponenten. Um bestimmte Komponenten zu migrieren, bitten Sie einen Kollegen, sie einem neuen Projekt hinzuzufügen, und migrieren Sie dann dieses Projekt.

Komponenten, die bereits in Customer Journey Analytics vorhanden sind, werden nicht neu erstellt, sodass Sie beide Methoden verwenden können. Migrieren Sie beispielsweise zuerst Ihre wichtigsten Projekte und dann alle verbleibenden Komponenten. Wählen Sie in Customer Journey Analytics aus, wo Sie beginnen möchten:

* **Migrieren eines Projekts** wenn Sie die Bedienfelder und Visualisierungen des Projekts in Customer Journey Analytics behalten möchten. Siehe [Von einem Projekt starten](#start-from-a-project).
* **Migrieren Sie bestimmte**, wenn Sie Komponenten wie Segmente, berechnete Metriken oder Datumsbereiche in Customer Journey Analytics benötigen, aber keines der Projekte benötigen, in denen sie verwendet werden. Sie können beispielsweise planen, neue Projekte in Customer Journey Analytics zu erstellen, die diese enthalten. Siehe [Mit bestimmten Komponenten beginnen](#start-from-specific-components).

### Von einem Projekt starten

So migrieren Sie ein Projekt und seine zugehörigen Komponenten:

1. Melden Sie sich bei einem Kollegen an.

1. Wählen Sie **[!UICONTROL Neuer Chat]** aus.

1. Fordern Sie im Textfeld einen Mitarbeiter auf, Ihr Projekt zu migrieren. Beispiel:

   **Eingabeaufforderung**

   > Ich möchte Komponenten von Adobe Analytics zu Customer Journey Analytics migrieren.

   Ein Mitarbeiter beschreibt, was migriert werden kann, und startet eine Umfrage.

1. Wählen Sie auf [!UICONTROL **Registerkarte**] Umfang“ eine der folgenden Optionen aus und klicken Sie dann auf [!UICONTROL **Weiter**]:

   <!-- FLAG: Confidence: Medium for the "Plan a full upgrade" description. It likely hands off to the implementation guide skill and leaves the migration flow. Confirm with engineering. Also confirm what the Source & target tab asks; it was skipped in the screenshots. The Next and Submit buttons on the first questionnaire's Source & target and Review tabs are assumed to work like the second questionnaire. -->

   | Option | Beschreibung |
   | --- | --- |
   | [!UICONTROL **Ein bestimmtes AA-Projekt**] | Migrieren Sie ein Projekt, das Sie benennen. Führen Sie die restlichen Schritte in diesem Abschnitt aus. |
   | [!UICONTROL **Nur Zuordnungen überprüfen**] | Überprüfen Sie, wie die Metriken und Dimensionen einer Report Suite einer Datenansicht zugeordnet sind, ohne etwas zu migrieren. Siehe [Report Suite-Zuordnungen vor der Migration überprüfen](#review-report-suite-mappings-before-you-migrate). |
   | [!UICONTROL **Planen eines vollständigen Upgrades**] | Holen Sie sich einen End-to-End-Plan für den Wechsel von Adobe Analytics zu Customer Journey Analytics. Siehe [Planen der Implementierung mit Coworker](/help/chat/use-cases/data-insights/implementation-guide.md). |

1. (Optional) Beantworten Sie die Fragen auf der Registerkarte [!UICONTROL **Source und Target**] und klicken Sie dann auf [!UICONTROL **Weiter**].

1. Bestätigen Sie [!UICONTROL **der Registerkarte**] Ihre Antworten und klicken Sie auf [!UICONTROL **Senden**].

   Anschließend prüft Coworker, auf welche Adobe Analytics-Unternehmen Sie Zugriff haben und wie viele zugrunde liegende Report Suites jede hat. Dann startet ein zweiter Fragebogen.

1. Beantworten Sie die folgenden Fragen, indem Sie [!UICONTROL **Weiter**] nach jeder Frage auswählen:

   | Tab | Question | Zusätzlicher Kontext |
   | --- | --- | --- |
   | [!UICONTROL **Projekt**] | Wie heißt das AA-Projekt, das Sie migrieren möchten? | Ein Teilname ist in Ordnung. |
   | [!UICONTROL **Report Suite**] | Welche Report Suite verwendet das Projekt? | Wählen Sie eine Report Suite aus der Liste aus oder geben Sie den Namen einer anderen Report Suite ein. |
   | [!UICONTROL **Datenansicht**] | Zu welcher CJA-Datenansicht soll sie migriert werden? | (Optional) Geben Sie den Namen einer Datenansicht ein, oder lassen Sie es leer, und ein Mitarbeiter schlägt übereinstimmende Datenansichten vor. |

1. Bestätigen Sie [!UICONTROL **der Registerkarte**] Ihre Antworten und klicken Sie auf [!UICONTROL **Senden**].

   Um den Fragebogen zu überspringen, wählen Sie [!UICONTROL **Fragebogen überspringen**] und beschreiben Sie stattdessen im Chat, was Sie möchten.

1. Fahren Sie mit [Überprüfen der Validierungsergebnisse und Zuordnungen](#review-the-validation-results-and-mappings) fort.

### Mit bestimmten Komponenten beginnen

<!-- FLAG: Sourced from a prompt that SME Scott Tomko ran in Coworker (October 2026). The example is generalized; the original prompt named a customer. Coworker may ask a few questions along the way. Confirm what happens to the project that Coworker creates in Adobe Analytics, and to its migrated copy in Customer Journey Analytics, if you only wanted the components. -->

So migrieren Sie bestimmte Komponenten:

1. Bitten Sie Ihre Kollegen, ein Projekt mit diesen Komponenten zu erstellen und es dann zu migrieren. Beispiel:

   **Eingabeaufforderung**

   > Ich möchte alle meine Analytics-Segmente mit „Frühjahrsverkauf“ im Namen nach CJA migrieren. Erstellen Sie ein neues Workspace-Projekt mit all diesen Segmenten und migrieren Sie dieses Projekt dann zu CJA.

   Ein Mitarbeiter erstellt das Projekt in Adobe Analytics.

1. Fahren Sie mit dem folgenden Abschnitt fort[&#x200B; „Überprüfen Sie die Validierungsergebnisse und Zuordnungen](#review-the-validation-results-and-mappings).

## Überprüfen der Validierungsergebnisse und -zuordnungen

<!-- FLAG: Confidence: Medium for the steps that fix a failed validation. They're based on the aa-mcp tool descriptions and on a test conversation where validation passed only after the project's panel was switched to a base report suite. Confirm how Coworker presents a failed validation, and whether it asks for confirmation before it updates a mapping. -->

Ein Mitarbeiter vergleicht das Projekt mit der ausgewählten Datenansicht und meldet dann, ob das Projekt migriert werden kann. In den Ergebnissen werden alle Dimensionen und Metriken im Projekt sowie die Customer Journey Analytics-Dimension oder -Metrik aufgelistet, der bzw. der sie zugeordnet sind. Beispiel:

* **Metrik:** Vorfälle werden zu Ereignissen
* **Dimension:** Stunde bleibt Stunde

Informationen zu den migrierten Komponenten und Projektelementen finden Sie unter [Was bei einer Migration enthalten ist](https://experienceleague.adobe.com/de/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#understand-what-is-included-in-a-migration) in der Dokumentation zu Adobe Analytics.

Wenn die Validierung nicht erfolgreich ist:

* **Dimensionen oder Metriken, die nicht automatisch zugeordnet werden können:** Mitarbeiter schlägt eine Dimension oder Metrik in Ihrer Datenansicht vor, der sie jeweils zugeordnet werden soll, aktualisiert die Zuordnung und validiert das Projekt erneut. Sie können Coworker auch mitteilen, welcher Dimension oder Metrik sie zugeordnet werden soll, z. B. „Mapping Page Views to web.webPageDetails.pageViews.value“.

* **Nicht unterstützte Elemente:** Entfernen Sie alle nicht unterstützten Elemente aus dem Projekt in Adobe Analytics. Stellen Sie beispielsweise sicher, dass jedes Bedienfeld eine zugrunde liegende Report Suite statt einer Virtual Report Suite verwendet. Bitten Sie dann den Kollegen, das Projekt erneut zu überprüfen. Eine Liste der nicht unterstützten Elemente finden Sie unter [Wissenswertes zu nicht unterstützten Elementen, die Fehler verursachen](https://experienceleague.adobe.com/de/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#understand-unsupported-elements-that-cause-errors) in der Dokumentation zu Adobe Analytics.

Informationen zum Überprüfen von Zuordnungen für eine ganze Report Suite vor der Migration finden Sie unter [Überprüfen von Report Suite-Zuordnungen vor der Migration](#review-report-suite-mappings-before-you-migrate).

## Migrieren des Projekts

1. Nach erfolgreicher Validierung fragt Coworker, ob die Customer Journey Analytics-Version Ihres Projekts in der ausgewählten Datenansicht erstellt werden soll. Wählen Sie [!UICONTROL **Ja, migrieren**] und dann [!UICONTROL **Senden**] aus.

   Um zu stoppen, ohne zu migrieren, wählen Sie [!UICONTROL **Nein, hier stoppen**].

   Der Mitarbeiter erstellt das Projekt in Customer Journey Analytics neu, wobei Sie der Projektbesitzer sind. Das ursprüngliche Adobe Analytics-Projekt ändert sich nicht.

1. Fahren Sie mit dem folgenden Abschnitt fort: [Überprüfen des Migrationsstatus](#check-the-migration-status).

## Überprüfen des Migrationsstatus

Migrationen werden im Hintergrund ausgeführt, sodass das neue Projekt möglicherweise nicht sofort bereit ist.

1. Mitarbeiter auffordern, den Status der Migration zu überprüfen:

   **Eingabeaufforderung**

   > Status prüfen

   <!-- FLAG: The Failed row links to Retry a failed migration in the Adobe Analytics docs, but those steps use the Component migration page in the Adobe Analytics UI, which is admin-only. A non-admin with the Component Migration permission can't follow them. Confirm with Scott whether Coworker can retry a failed migration (for example, "Retry the migration"). If so, replace the link with a prompt. -->

   Coworker meldet einen der folgenden Status:

   | Status | Bedeutung |
   | --- | --- |
   | In Warteschlange | Die Migration wartet auf den Start. |
   | Gestartet | Die Migration wird durchgeführt. |
   | Abgeschlossen | Die Migration wurde abgeschlossen. Der -Mitarbeiter bietet eine Zusammenfassung dessen, was migriert wurde, einschließlich des Projektnamens und der Datenansicht. |
   | Fehlgeschlagen | Die Migration ist fehlgeschlagen. Sie können die Migration wiederholen. Siehe [Wiederholen einer fehlgeschlagenen Migration](https://experienceleague.adobe.com/de/docs/analytics/admin/admin-tools/component-migration/component-migration#retry-a-failed-migration) in der Dokumentation zu Adobe Analytics. |

1. Wenn die Migration abgeschlossen ist, öffnen Sie das neue Projekt über Ihre Projektliste in Customer Journey Analytics Workspace.

1. (Optional) Übertragen Sie das Eigentum an dem Projekt an einen beliebigen Benutzer in Customer Journey Analytics. Weitere Informationen finden Sie unter [Assets übertragen](https://experienceleague.adobe.com/de/docs/analytics-platform/using/tools/asset-transfer/transfer-assets).

Nach Abschluss der Migration kann ein Mitarbeiter ein anderes Projekt vorschlagen, das als Nächstes migriert werden soll.

## Tipps für bessere Ergebnisse

* Lassen Sie die Datenansicht im Fragebogen leer, wenn Sie sich nicht sicher sind, welche verwendet werden soll. Mitarbeiter schlägt Datenansichten vor, die mit der Report Suite übereinstimmen.
* Vergleichen Sie nach der Migration Ihre Adobe Analytics- und Customer Journey Analytics-Daten, um zu bestätigen, dass Ihre Berichte übereinstimmen. Siehe [Validieren von Daten mit einem Kollegen beim Upgrade von Adobe Analytics auf Customer Journey Analytics](/help/chat/use-cases/data-insights/data-validation-aa-cja.md).

## Nächste Schritte

* Informationen zum Migrieren von Projekten in der Adobe Analytics-Benutzeroberfläche finden Sie [Migrieren von Komponenten und Projekten von Adobe Analytics nach Customer Journey Analytics](https://experienceleague.adobe.com/de/docs/analytics/admin/admin-tools/component-migration/component-migration) in der Dokumentation zu Adobe Analytics.
* Weitere Anwendungsfälle für Implementierung und Administration finden Sie unter [Intelligente Implementierung und Administration - Übersicht](/help/chat/use-cases/data-insights/data-governance-and-validation.md).
