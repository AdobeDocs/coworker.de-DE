---
title: Sitzungskontext-Tools in CX Coworker Gateway
description: Erfahren Sie mehr über die wichtigsten Tools, die den Organisations-, Sandbox- und Datenansichtskontext für alle CX Coworker Gateway-Tool-Aufrufe festlegen.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 1%
---
# Sitzungskontext-Tools in Adobe CX Coworker Gateway {#mcp-core}

Adobe CX Coworker Gateway enthält eine Reihe von Sitzungskontext-Tools, die die Adobe-Organisation, die Adobe Experience Platform-Sandbox und die Customer Journey Analytics-Datenansicht festlegen, in der alle anderen Produkttools ausgeführt werden. Es ist keine zusätzliche Lizenz oder Aktivierung erforderlich. Diese Tools stehen allen authentifizierten Benutzenden nach der Verbindung mit dem [CX Coworker Gateway Server](overview.md) zur Verfügung.

## Funktionsweise des Kontexts {#mcp-core-how}

CX Coworker Gateway erfasst jeden Tool-Aufruf an eine aktive Adobe-Organisation. Darüber hinaus hängen die Kontextanforderungen vom Produkt ab:

- **Experience Platform-basierte Produkte** - [Real-Time CDP](rtcdp-mcp.md)-, [Experience Platform](aep-mcp.md)- und [Journey Optimizer](ajo-mcp.md)-Tools werden innerhalb einer Experience Platform-Sandbox ausgeführt. Legen Sie die Sandbox einmal pro Sitzung mit `core-set_sandbox` fest. Alle drei geben sie frei.
- **Andere Produkte** — Produkte, die nicht auf Experience Platform basieren, verwenden keinen Sandbox-Kontext. Beispielsweise können [Customer Journey Analytics](cja-mcp.md)-Tools für eine Datenansicht und [Adobe Analytics](analytics-mcp.md)-Tools für Report Suites aufgelöst werden.

Kontext einmal zu Beginn einer Sitzung festlegen - einzelne Produkt-Tools wechseln während der Sitzung nicht zwischen Organisationen, Sandboxes oder Datenansichten.

## Verfügbare Tools {#mcp-core-tools}

| Tool | Beschreibung |
| --- | --- |
| `core-list_orgs` | Listet die Adobe-Organisationen auf, auf die die authentifizierten Benutzenden zugreifen können. Gibt den Anzeigenamen und die `@AdobeOrg` eines jeden Unternehmens zurück. Verwenden Sie diese Option, um die Organisations-ID nachzuschlagen, bevor Sie `core-switch_org` aufrufen. |
| `core-switch_org` | Legt die aktive Adobe-Organisation für die Sitzung fest. Alle nachfolgenden Tool-Aufrufe gehen auf diese Organisation über, bis die Sitzung beendet oder die Organisation erneut gewechselt wird. |
| `core-list_sandboxes` | Listet die in der aktiven Organisation verfügbaren Experience Platform-Sandboxes auf. Gibt den Namen, den Titel, den Typ (Produktion oder Entwicklung) und den Status jeder Sandbox zurück. Hier können Sie einen Sandbox-Namen suchen, bevor Sie `core-set_sandbox` aufrufen. |
| `core-set_sandbox` | Legt die aktive Experience Platform-Sandbox für die Sitzung fest. Die Tools Real-Time CDP, Experience Platform und Journey Optimizer wenden ihre Daten auf diese Sandbox an. |
| `core-list_dataviews` | Listet die Customer Journey Analytics-Datenansichten auf, die für den authentifizierten Benutzer im aktuellen Kontext verfügbar sind. Gibt Datenansichts-IDs und Anzeigenamen zurück. Verwenden Sie diese Option, um eine Datenansicht zu suchen, bevor Sie `core-set_dataview` aufrufen. |
| `core-set_dataview` | Legt die standardmäßige Customer Journey Analytics-Datenansicht für die Sitzung fest. Wenn dieser Wert festgelegt ist, verwenden CJA-Tools, die eine Datenansicht erfordern - z. B. `findDimensions`, `findMetrics` und `runReport` - diesen Wert automatisch, es sei denn, im jeweiligen Tool-Aufruf wird eine andere Datenansicht angegeben. |

## Typisches Sitzungssetup {#mcp-core-setup}

Legen Sie den Kontext zu Beginn einer Sitzung fest, bevor Sie die Produkt-Tools aufrufen:

1. **Organisation** - Rufen Sie `core-list_orgs` auf, um Ihre Organisationen aufzulisten, auf die Sie zugreifen können, und `core-switch_org` Sie dann mit der Zielgruppen-Organisations-ID.
2. **Sandbox** - Wenn Sie planen, Real-Time CDP-, Experience Platform- oder Journey Optimizer-Tools zu verwenden, rufen Sie `core-list_sandboxes` auf, um die verfügbaren Sandboxes aufzulisten, und `core-set_sandbox` Sie dann mit dem Ziel-Sandbox-Namen.
3. **Datenansicht** (nur CJA) - Wenn Sie planen, Customer Journey Analytics-Tools zu verwenden, rufen Sie `core-list_dataviews` auf, um verfügbare Datenansichten aufzulisten, und `core-set_dataview` Sie dann mit Ihrer ausgewählten Datenansicht.

Sie können Ihren MCP-Client bitten, diese Einrichtung in einer einzigen Anfrage in natürlicher Sprache abzuschließen:

> „Verwenden Sie Organisations-`1234ABCD@AdobeOrg`, Sandbox-`prod` und Datenansichts-`My Company — Global` für diese Sitzung.“

Der Client ruft die entsprechenden Tools auf und bestätigt, sobald der Kontext festgelegt ist.

>[!TIP]
>
>Wenn Ihre Adobe-Anmeldeinformationen nur zu einer Organisation gehören, funktionieren `core-list_orgs` und `core-switch_org` weiterhin, aber die effektive Organisation bleibt unverändert. Sie müssen weiterhin `core-set_sandbox` aufrufen, wenn Sie Real-Time CDP-, Experience Platform- oder Journey Optimizer-Tools verwenden möchten, und `core-set_dataview`, wenn Sie Customer Journey Analytics-Tools verwenden möchten.

## Beispiel-Prompts {#mcp-core-examples}

| Ziel | Prompt-Beispiel |
| --- | --- |
| Verfügbare Organisationen entdecken | „Auf welche Adobe-Organisationen habe ich Zugriff?“ |
| Festlegen des Organisationskontexts | „Zu Organisation `My Org (1234ABCD@AdobeOrg)` wechseln.“ |
| Verfügbare Sandboxes entdecken | „Listen Sie die in meiner aktuellen Organisation verfügbaren Sandboxes auf.“ |
| Festlegen des Sandbox-Kontexts | „Verwenden Sie die `prod` Sandbox für diese Sitzung.“ |
| Verfügbare Datenansichten entdecken | „Auf welche Customer Journey Analytics-Datenansichten kann ich zugreifen?“ |
| Festlegen des Datenansichtskontexts | &quot;`My Company — Global` als Standard-Datenansicht festlegen.“ |
| Vollständige Sitzungseinrichtung | „Richten Sie eine Sitzung mithilfe von Organisations-`1234ABCD@AdobeOrg`, Sandbox-`prod` und Datenansichts-`My Company — Global` ein.“ |

## Verwandte Seiten {#mcp-core-related}

- [Installieren von Adobe CX Coworker Gateway](install.md) - Anleitung zum Verbinden Ihres MCP-Clients, einschließlich des Abschnitts „Produktkontext-Setup“.
- [Zugriff auf CX Coworker Gateway-Tools](access.md) - Zugriffsanforderungen nach Produkt.