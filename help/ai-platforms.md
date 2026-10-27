---
title: Adobe CX Enterprise Coworker für KI-Plattformen
description: Informationen zu Adobe CX Enterprise Coworker für KI-Plattformen. Informieren Sie sich über unterstützte Plattformen, Einrichtungsanweisungen und Beispielaufforderungen, um Marketing-Erkenntnisse zu erhalten.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: cc2d5256952ce20cda57f7274a5dc1d879d4a6a0
workflow-type: tm+mt
source-wordcount: '1011'
ht-degree: 2%
---

# Adobe CX Enterprise Coworker für KI-Plattformen

Verwenden Sie Adobe CX Enterprise Coworker für KI-Plattformen, um Marketing-Einblicke in die bereits verwendeten KI-Tools zu erhalten. Stellen Sie Fragen in natürlicher Sprache, ohne das Werkzeug zu wechseln. Suchen Sie in jeder Plattform das Produkt, das als Adobe CX Enterprise Coworker aufgeführt ist.

Verfügbare Plattformen und deren Setup-Anweisungen finden Sie unter [Einrichten von ](#set-up-coworker)&quot;.

Die Verwendung von Coworker in KI-Plattformen verursacht keine zusätzlichen Kosten. Sie ist in Ihrer CX Enterprise Coworker-Lizenz enthalten und die Nutzung erfolgt über dieselben KI-Credits wie bei anderen Coworker-Funktionen. Weitere Informationen finden Sie unter [Nutzung von Adobe Experience Platform-Agentenvorgängen und KI-Guthaben](https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/overview/ai-credit-consumption){target="_blank"}.

<!-- TODO: architecture diagram pending from engineering. KT page notes "to be provided on 8/28"; still outstanding as of 8/31. Insert here once received. -->

## Voraussetzungen {#prerequisites}

Bevor Sie Coworker in einer KI-Plattform verwenden können, vergewissern Sie sich, dass Sie Folgendes tun.

* Adobe CX Enterprise Coworker für Ihr Unternehmen und Ihren eigenen Zugriff darauf in Adobe bereitgestellt.
* Adobe Experience Platform und mindestens eines von Adobe Real-Time CDP, Adobe Journey Optimizer oder Adobe Customer Journey Analytics.
* Zugriff auf eine KI-Plattform, die unter &quot;[ einrichten“ aufgeführt ](#set-up-coworker).

## Datenzugriff und Berechtigungen {#data-access-and-permissions}

Die Coworker in KI-Plattformen spiegeln dieselbe Daten- und Zugriffsebene wider, die mit Ihrer Adobe-Identität verknüpft ist. Was Sie abfragen und sehen können, stimmt mit dem überein, wozu Sie bereits in Experience Platform und den zugehörigen Lösungen berechtigt sind. Der -Kollege erbt diese Berechtigungen, sodass für die KI-Plattformintegration keine separaten Berechtigungen eingerichtet werden müssen. Der -Mitarbeiter gibt schreibgeschützte Einblicke zurück und ändert Ihre Kundendaten nicht. Überprüfen Sie alle generierten Zusammenfassungen und Analysen, bevor Sie sie für geschäftliche Entscheidungen verwenden.

<!-- Confirmed by PM (Siddhartha Srivastava) on 2026-09-02 for Microsoft 365 Copilot, Claude, and ChatGPT. Validate this permissions model for each additional platform before adding its setup tab. -->

## Wichtige Anwendungsfälle {#key-use-cases}

Verwenden Sie Coworker in KI-Plattformen, um gängige Marketing-Workflows zu beschleunigen, ohne Ihre alltäglichen Tools verlassen zu müssen.

| Anwendungsfall | Beschreibung |
| --- | --- |
| Kampagnen planen und überprüfen | Planen Sie Kampagnen, einschließlich Partnerkampagnen-Reviews und Zielgruppen-Prognosen. Vergleichen Sie die Leistung von Campaign im Zeitverlauf und ermitteln Sie, welche Touchpoints für Konversionen verantwortlich sind. |
| Überwachen der Bereitschaft von Journey und Kampagnen | Überprüfen und überwachen Sie aktive Kampagnen, analysieren Sie Journey von Kunden und bewerten Sie die Kampagnenbereitschaft. Verfolgen Sie die Journey-Performance und die Abbrüche, um Optimierungsmöglichkeiten zu identifizieren. |
| Abrufen operativer Einblicke | Identifizieren Sie, welche Zielgruppen am größten sind oder am stärksten interagieren, damit Sie Prioritäten setzen können, worauf Sie Ihre Bemühungen konzentrieren müssen, und verfolgen können, wie Ihre Segmente im Laufe der Zeit wachsen oder schrumpfen. |
| Workflows und Inhalte optimieren | Optimieren Sie Workflows und identifizieren Sie Asset- und Inhaltsanforderungen für CX-Kampagnen. Visuelle Berichte zur Kampagnenleistung generieren, ohne Abfragen oder Dashboards manuell zu erstellen. |
| Schnellere Zusammenarbeit und Entscheidung | Verwenden Sie empfohlene Eingabeaufforderungen, um Zielgruppen, Kampagnen und Web-Traffic zu untersuchen. Teilen Sie Einblicke mit Ihrem Team während Planungsbesprechungen und beantworten Sie Ad-hoc-Fragen in Echtzeit, während Sie Pläne oder Decks überprüfen. |

<!-- Use cases approved by PM Siddhartha Srivastava on 2026-08-31 and confirmed for Microsoft 365 Copilot, Claude, and ChatGPT on 2026-09-02. Validate applicability for each additional platform before adding its setup tab. -->

## Einrichten eines Kollegen {#set-up-coworker}

Eine verfügbare Plattform für Einrichtungsanweisungen auswählen. Nach dem Setup versuchen Sie Folgendes [Beispielaufforderungen](#example-prompts).

>[!BEGINTABS]

>[!TAB Microsoft 365-Kopilot]

Verwenden Sie [!DNL Adobe CX Enterprise Coworker for Copilot], um Marketing-Einblicke in [!DNL Microsoft 365 Copilot] zu erhalten.

Bevor Sie beginnen, bestätigen Sie, dass Sie Zugriff auf [!DNL Microsoft 365 Copilot] haben.

**Richten Sie einen Mitarbeiter für Ihre Organisation ein**

Ein Administrator muss diese Schritte ausführen, damit die Endbenutzer in [!DNL Microsoft 365 Copilot] auf die Rolle „Mitarbeiter“ zugreifen können.

1. Bestätigen Sie in der [!DNL Microsoft 365 admin center], dass Ihre Mandanteneinstellungen von externen Herausgebern erstellte Apps und Agenten zulassen.
1. Genehmigen Sie **[!UICONTROL Adobe CX Enterprise Coworker]** sowohl im [!DNL Microsoft 365 admin center] als auch im [!DNL Teams admin center]. Normalerweise finden Sie den Agenten über die [!DNL Microsoft Commercial Marketplace] oder die Liste **[!UICONTROL Integrierte Apps]** Ihres Unternehmens.
1. Stellen Sie den Agenten für Endbenutzer bereit. Sie können sie für bestimmte Benutzer oder Gruppen oder für Ihr gesamtes Unternehmen bereitstellen. Die Anzahl der aktivierten Benutzer hat keinen Einfluss auf die Einrichtung oder die Kosten.

>[!NOTE]
>
>Wenn [!DNL Microsoft] ein Update für Coworker veröffentlicht, das neue Berechtigungen erfordert, muss Ihr Administrator das Update in der [!DNL Agent Registry] genehmigen, bevor es an Ihre Benutzerinnen und Benutzer gesendet werden kann.

**Zugriff auf Mitarbeiter in[!DNL Copilot]**

Sobald Ihr Admin Coworker aktiviert hat, können Sie darauf über [!DNL Microsoft 365 Copilot] Oberflächen zugreifen, einschließlich [!DNL Teams], [!DNL Word], [!DNL Excel], [!DNL PowerPoint] und Webchat.

Wählen Sie [!DNL Microsoft 365 Copilot] die Option **[!UICONTROL Agenten]** und dann **[!UICONTROL Weitere Agenten]** aus.

![Microsoft 365 Copilot mit geöffnetem Agentenmenü und hervorgehobener Option „Weitere Agenten“.](./assets/ai-platforms/copilot/copilot-agents.png)

Wählen Sie anschließend **[!UICONTROL Adobe CX Enterprise Coworker]** im Agentenkatalog aus.

![Microsoft 365 Copilot-Agentenkatalog mit hervorgehobener Adobe CX Enterprise Coworker-Liste.](./assets/ai-platforms/copilot/copilot-select-agent.png)

Wählen Sie abschließend **[!UICONTROL Hinzufügen]** aus, um Ihren Agenten Kollegen hinzuzufügen.

![Adobe CX Enterprise Coworker-Details im Microsoft 365-Kopilot mit hervorgehobener Schaltfläche „Hinzufügen“.](./assets/ai-platforms/copilot/copilot-add-coworker.png)

>[!TAB ChatGPT]

Verwenden Sie [!DNL Adobe CX Enterprise Coworker for ChatGPT], um Marketing-Einblicke in [!DNL ChatGPT] zu erhalten.

Bevor Sie beginnen, bestätigen Sie, dass Sie Zugriff auf [!DNL ChatGPT] haben.

**Richten Sie einen Mitarbeiter für Ihre Organisation ein**

* Bitten Sie Ihren [!DNL ChatGPT], **[!UICONTROL Adobe CX Enterprise Coworker]** für ausgewählte Benutzer oder für Ihr gesamtes Unternehmen zu genehmigen.

**Zugriff auf Mitarbeiter in[!DNL ChatGPT]**

Wählen Sie [!DNL ChatGPT] die Option **[!UICONTROL Plug-ins]** aus.

![ChatGPT-Navigation mit hervorgehobenen Plug-ins.](./assets/ai-platforms/chatgpt/gpt-plugins.png)

Suchen Sie als Nächstes **[!UICONTROL Adobe CX Enterprise Coworker]** im Plug-in-Katalog und wählen Sie diese aus.

![ChatGPT-Plug-in-Katalog mit der unter den Suchergebnissen für Adobe hervorgehobenen Adobe CX Enterprise Coworker-Liste.](./assets/ai-platforms/chatgpt/gpt-select-plugins.png)

Wählen Sie abschließend **[!UICONTROL Plug-in installieren]**, um Coworker zu [!DNL ChatGPT] hinzuzufügen.

![Adobe CX Enterprise Coworker-Details in ChatGPT mit hervorgehobener Schaltfläche „Plug-in installieren“.](./assets/ai-platforms/chatgpt/gpt-install-coworker.png)

>[!TAB Claude]

Verwenden Sie einen Kollegen, um Marketing-Einblicke in [!DNL Claude] zu erhalten.

Bevor Sie beginnen, bestätigen Sie, dass Sie Zugriff auf [!DNL Claude] haben.

**Richten Sie einen Mitarbeiter für Ihre Organisation ein**

* Bitten Sie Ihren [!DNL Claude], **[!UICONTROL Adobe CX Enterprise Coworker]** für ausgewählte Benutzer oder für Ihr gesamtes Unternehmen zu genehmigen.

**Zugriff auf Mitarbeiter in[!DNL Claude]**

1. Wählen Sie [!DNL Claude] die Option **[!UICONTROL Anpassen]** aus.

   ![Claude-Navigation mit hervorgehobener Option „Anpassen“.](./assets/ai-platforms/claude/claude-customize.png)

1. Wählen Sie **[!UICONTROL Connectoren]**, dann **[!UICONTROL Entdecken]** aus und verwenden Sie **[!UICONTROL Suchen]**, um Adobe CX Enterprise Coworker zu finden.

   ![Claude-Seite anpassen mit hervorgehobener Registerkarte „Connectoren“ und geöffnetem Discover-Katalog.](./assets/ai-platforms/claude/claude-connectors.png)

1. Wählen Sie **[!UICONTROL Adobe CX Enterprise Coworker]** und dann **[!UICONTROL Mit Claude verbinden]** aus.

   ![Adobe CX Enterprise Coworker-Connector-Details in Claude mit hervorgehobener Option „Mit Claude verbinden“.](./assets/ai-platforms/claude/claude-connect-coworker.png)

1. Melden Sie sich mit Ihren Adobe-Anmeldeinformationen an, um eine Verbindung zwischen Coworker und [!DNL Claude] herzustellen.

>[!ENDTABS]

<!-- Setup steps above reflect the real customer-facing flow confirmed by PM (Siddhartha Srivastava) on 2026-09-02: an org admin approves the connector or plugin, then end users find and add it in their platform's catalog and sign in. The previous version of this file described a manual MCP-connector setup for ChatGPT (Settings > Connectors > paste server URL) -- PM clarified that flow is for internal testing only, not the customer path, so it was removed here. -->

## Beispiel-Prompts {#example-prompts}

Nachdem Sie Coworker in einer unterstützten Plattform eingerichtet haben, versuchen Sie diese Eingabeaufforderungen oder schreiben Sie Ihre eigene in natürlicher Sprache.

* Zeigen Sie Ihre fünf wichtigsten Zielgruppen.
* Eine Metrik für den letzten Monat anzeigen.
* Ihre aktiven Workfront-Projekte anzeigen.
* Journey mit Treueprogramm-Zielgruppen anzeigen.

## Bekannte Einschränkungen {#known-limitations}

Die Zusammenarbeit in KI-Plattformen unterstützt nicht alle Integrationsmuster.

* Sie können Coworker nicht mit Ihrem eigenen Agent-Kabelbaum über MCP verbinden.

## Fehlerbehebung bei Kollegen in KI-Plattformen {#troubleshoot}

Führen Sie diese Schritte aus, wenn Sie Probleme bei der Verwendung von Coworker in einer KI-Plattform haben.

* Wenn ein Fehler angezeigt wird, melden Sie sich ab und wieder mit Ihren Adobe-Anmeldeinformationen an. Durch eine erneute Authentifizierung werden die meisten Probleme behoben.
* Wenn Sie nicht auf Kollegen oder bestimmte Daten zugreifen können, wenden Sie sich an Ihren Adobe-Administrator, um den Produktzugriff und die Berechtigungen zu bestätigen.

<!--
Editorial maintenance, 2026-10-27:
Only approved platforms with validated setup guidance belong in the rendered tab set.
Remaining platforms to add: Gemini, Amazon Quick, IBM, and Databricks.

To add an approved platform:
* Confirm approval and obtain access to the customer flow.
* Validate prerequisites, organization approval, catalog discovery, listing name, installation, and Adobe sign-in.
* Confirm the shared licensing, permissions, use cases, prompts, limitations, and troubleshooting guidance applies.
* Add one tab before ENDTABS, following the existing order: introduction, platform prerequisites, organization setup, and user access.
* Document any platform-specific requirements or exceptions within that tab.
* Preview the tab and verify its links and image references.
Keep the introduction, metadata, and shared prerequisites free of platform lists so adding a tab does not require duplicate updates.

Gemini draft scope:
No setup steps are confirmed. Validate the complete customer flow and all shared guidance before adding the tab.
Do not infer the flow from another platform.
-->
