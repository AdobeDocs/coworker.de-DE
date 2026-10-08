---
title: Installieren von Adobe CX Coworker Gateway
description: Erfahren Sie, wie Sie MCP-kompatible Clients mit dem Adobe CX Coworker Gateway verbinden.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '1004'
ht-degree: 0%
---
# Installieren von Adobe CX Coworker Gateway {#mcp-install}

Lesen Sie dieses Handbuch, um zu erfahren, wie Sie einen MCP-kompatiblen Client mit Adobe CX Coworker Gateway verbinden.  CX Coworker Gateway verwendet einen Endpunkt für alle dokumentierten Produkt-Tools:

```
https://cx-coworker-gateway.adobe.io/mcp
```

Stellen Sie vor der Installation sicher, dass Ihr Unternehmen und Ihr Benutzerkonto auf die benötigten Produktwerkzeuge zugreifen können. Siehe [Zugriff auf CX Coworker Gateway-Tools](access.md).

## Funktionsweise der Installation {#mcp-install-how}

CX Coworker Gateway verwendet einen Remote-HTTP-Transport mit einem Browser-basierten Adobe-Anmeldefluss. In jedem unterstützten Client ist das Setup-Muster identisch:

1. Fügen Sie die Endpunkt-URL hinzu: `https://cx-coworker-gateway.adobe.io/mcp`.
2. Speichern oder aktivieren Sie die Verbindung.
3. Schließen Sie die browserbasierte Adobe-Anmeldung ab, wenn der Client zum ersten Mal ein Tool aufruft.
4. Legen Sie den Produktkontext für die Sitzung fest, wenn Ihre Tools dies erfordern - die Organisation für alle Produkte, die Sandbox für Experience Platform-basierte Tools und die Datenansicht für Customer Journey Analytics. Siehe [Produktkontext für Tool-](#mcp-connect-params).

>[!NOTE]
>
>In der MCP-Client-Konfiguration sind keine API-Schlüssel, Bearer-Token, Client-Geheimnisse oder zusätzlichen Header erforderlich. Die Authentifizierung wird bei der ersten Verwendung über den Adobe-Anmeldefluss durchgeführt.

## Unternehmensinstallation (vom Administrator verwaltet) {#mcp-install-enterprise}

Die meisten MCP-Client-Pläne für Teams und Unternehmen erfordern, dass ein Administrator benutzerdefinierte Connectoren für die Organisation hinzufügt. In diesen Umgebungen erfolgt die Installation in zwei Schritten:

1. Ein Administrator fügt den CX Coworker-Gateway-Endpunkt einmal für das Unternehmen hinzu.
2. Jeder Benutzer aktiviert den Connector und meldet sich mit seinen eigenen Adobe-Anmeldeinformationen an.

### Schritt 1: Ein Administrator fügt den Endpunkt hinzu {#mcp-install-enterprise-admin}

Der Administrator fügt `https://cx-coworker-gateway.adobe.io/mcp` als benutzerdefinierten Connector oder Remote-MCP-Server in den Unternehmenseinstellungen des Clients hinzu. Der genaue Standort hängt vom Client ab.

#### Claude Team und Enterprise {#mcp-install-enterprise-claude}

In [!DNL Claude] Team- und Unternehmensplänen werden Connectoren auf Organisationsebene von einem Workspace-**(**) oder **Primären Inhaber**.

1. Melden Sie sich bei [!DNL Claude] als **Inhaber** oder **Primärer Inhaber** an.
2. Navigieren Sie **Einstellungen** > **Administration** > **Connectoren**. Bei einigen Plänen wird dies als **Organisationseinstellungen** > **Connectoren** angezeigt.
3. Wählen Sie **Benutzerdefinierten Connector hinzufügen** aus.
4. Geben Sie `https://cx-coworker-gateway.adobe.io/mcp` als Server-URL ein und verwenden Sie einen erkennbaren Namen, z. B. &quot;Adobe for CX Coworker Gateway“.
5. Speichern Sie den Connector.

#### ChatGPT Team und Enterprise {#mcp-install-enterprise-chatgpt}

In [!DNL ChatGPT] Arbeitsbereichen von Teams und Unternehmen werden Connectoren von einem Arbeitsbereichadministrator hinzugefügt.

1. Melden Sie sich bei [!DNL ChatGPT] als Workspace-Administrator an.
2. Navigieren Sie **Einstellungen** > **Connectoren**. Bei einigen Plänen wird dies als **Einstellungen** > **Apps und Connectoren** angezeigt.
3. Wählen Sie **Connector hinzufügen** aus.
4. Geben Sie `https://cx-coworker-gateway.adobe.io/mcp` als Server-URL ein.
5. Speichern Sie den Connector. Abhängig von Ihrer Workspace-Konfiguration kann es erforderlich sein, für diesen Schritt den Entwicklermodus zu aktivieren oder eine Genehmigung auf Workspace-Ebene zu erteilen.

#### Andere vom Unternehmen verwaltete Clients {#mcp-install-enterprise-other}

Für andere Clients, die vom Unternehmen verwaltete Remote-Connectoren unterstützen, fügen Sie CX Coworker Gateway mithilfe von `https://cx-coworker-gateway.adobe.io/mcp` als Remote-HTTP-MCP-Server hinzu. Lassen Sie die optionalen Felder für Kopfzeilen, Bearer-Token, Client-ID und Client-Geheimnis leer, es sei denn, Ihr Client erfordert einen Platzhalterwert.

### Schritt 2: Benutzer aktivieren den Connector {#mcp-install-enterprise-user}

Nachdem ein Administrator das CX Coworker-Gateway hinzugefügt hat, wird es von jedem Benutzer für sein eigenes Konto aktiviert:

1. Öffnen Sie persönliche Connector-, App- oder MCP-Einstellungen im Client.
2. Suchen Sie den CX Coworker Gateway-Connector und aktivieren Sie ihn.
3. Starten Sie eine Konversation, rufen Sie eines der Adobe-Tools auf und schließen Sie die browserbasierte Adobe-Anmeldung ab, wenn Sie dazu aufgefordert werden.
4. Legen Sie den Produktkontext für die Sitzung fest, wenn Ihre Tools dies erfordern - die Organisation für alle Produkte, die Sandbox für Experience Platform-basierte Tools und die Datenansicht für Customer Journey Analytics. Siehe [Produktkontext für Tool-](#mcp-connect-params).

Benutzer müssen die URL nicht selbst eingeben, wenn ein Administrator den Connector für die Organisation bereits hinzugefügt hat.

## Individuelle Installation (Self-Service) {#mcp-install-individual}

Wenn Sie einen einzelnen Plan, einen lokal konfigurierten Entwickler-Client oder eine Organisation verwenden, in der Mitglieder ihre eigenen Connectoren hinzufügen können, fügen Sie den Endpunkt direkt in Ihren eigenen Client-Einstellungen hinzu.

### Claude Individual {#mcp-install-individual-claude}

Für `claude.ai` und [!DNL Claude] Desktop in einem individuellen Plan:

1. Öffnen Sie **Einstellungen** > **Connectoren**.
2. Wählen Sie **Benutzerdefinierten Connector hinzufügen** aus.
3. Geben Sie `https://cx-coworker-gateway.adobe.io/mcp` als Server-URL ein.
4. Speichern und aktivieren Sie den Connector und schließen Sie dann den Adobe-Anmeldevorgang bei der ersten Verwendung ab.

### ChatGPT-Kontakt {#mcp-install-individual-chatgpt}

1. Öffnen Sie **Einstellungen** > **Connectoren**. Bei einigen Plänen wird dies als **Einstellungen** > **Apps und Connectoren** angezeigt.
2. Wählen Sie **Connector hinzufügen** aus.
3. Geben Sie `https://cx-coworker-gateway.adobe.io/mcp` als Server-URL ein.
4. Speichern und aktivieren Sie den Connector und schließen Sie dann den Adobe-Anmeldevorgang bei der ersten Verwendung ab.

### Cursor {#mcp-install-individual-cursor}

1. Öffnen Sie **Einstellungen** > **MCP**.
2. Wählen Sie **Neuen Server hinzufügen** aus.
3. Geben Sie `https://cx-coworker-gateway.adobe.io/mcp` als Server-URL ein.
4. Wählen Sie **Verbinden** aus und schließen Sie den Anmeldevorgang für Adobe ab.

Nach dem Verbinden sind die Adobe für CX Coworker Gateway-Tools im Cursor Composer- und Agent-Modus verfügbar.

### Claude Code {#mcp-install-individual-claude-code}

Fügen Sie den Endpunkt vom Terminal aus hinzu:

```bash
claude mcp add --transport http cx-enterprise https://cx-coworker-gateway.adobe.io/mcp
```

Starten Sie dann [!DNL Claude Code] und führen Sie Folgendes aus:

```text
/mcp
```

Wählen Sie den `cx-enterprise` aus und schließen Sie den Adobe-Anmeldevorgang in Ihrem Browser ab.

### Codex {#mcp-install-individual-codex}

Fügen Sie den Endpunkt vom Terminal aus hinzu:

```bash
codex mcp add cx-enterprise --url https://cx-coworker-gateway.adobe.io/mcp
```

Authentifizieren:

```bash
codex mcp login cx-enterprise
```

Überprüfen Sie die Konfiguration:

```bash
codex mcp list
```

Sie können den Endpunkt auch direkt zu `~/.codex/config.toml` hinzufügen:

```toml
[mcp_servers.cx-enterprise]
url = "https://cx-coworker-gateway.adobe.io/mcp"
```

### Allgemeine JSON-Konfiguration {#mcp-install-individual-json}

Verwenden Sie für Clients, die eine JSON-basierte MCP-Server-Konfiguration akzeptieren, eines der folgenden Formate, je nachdem, ob Ihr Client natives Remote-HTTP unterstützt oder eine lokale Bridge benötigt.

**Über `mcp-remote` Brücke**

```json
{
  "mcpServers": {
    "cx-enterprise": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "https://cx-coworker-gateway.adobe.io/mcp"
      ]
    }
  }
}
```

**Natives Remote-HTTP**

```json
{
  "mcpServers": {
    "cx-enterprise": {
      "url": "https://cx-coworker-gateway.adobe.io/mcp",
      "transport": "http"
    }
  }
}
```

### Andere Clients {#mcp-install-individual-other}

Für andere Desktop- oder Webclients mit Remote-MCP-Unterstützung fügen Sie Adobe für CX Coworker Gateway als Remote-HTTP-Server mit `https://cx-coworker-gateway.adobe.io/mcp` hinzu. Lassen Sie die optionalen Felder für Kopfzeilen, Bearer-Token, Client-ID und Client-Geheimnis leer, es sei denn, Ihr Client erfordert einen Platzhalterwert.

## Produktkontext für Tool-Aufrufe {#mcp-connect-params}

Der MCP erfasst jeden Tool-Aufruf an eine aktive Adobe-Organisation. Darüber hinaus hängen die Kontextanforderungen vom Produkt ab:

- **Experience Platform-basierte Produkte** - Real-Time CDP-, Experience Platform- und Journey Optimizer-Tools werden innerhalb einer Experience Platform-Sandbox ausgeführt. Legen Sie die Sandbox einmal pro Sitzung fest. Alle drei geben sie frei.
- **Andere Produkte** — Produkte, die nicht auf Experience Platform basieren, verwenden keinen Sandbox-Kontext. Adobe Analytics-, Customer Journey Analytics-, Workfront-, Marketo- und Target-Tools werden gegen ihre eigenen Produktressourcen aufgelöst, z. B. Datenansichten für Customer Journey Analytics und Report Suites für Adobe Analytics.

Kontext einmal zu Beginn einer Sitzung festlegen - einzelne Produkt-Tools wechseln während der Sitzung nicht zwischen Organisationen, Sandboxes oder Datenansichten. Unter [Sitzungskontext-Tools](context-tools.md) finden Sie die Tools, die den Organisations-, Sandbox- und Datenansichtskontext festlegen.

Beispiel:

> „Verwenden Sie Organisations-`1234ABCD@AdobeOrg`, Sandbox-`prod` und Datenansichts-`My Company — Global` für diese Sitzung.“

Wenn Sie die erforderlichen Werte nicht kennen, bitten Sie Ihren MCP-Client, die Organisationen, Sandboxes oder Datenansichten aufzulisten, die für Ihre Adobe-Anmeldeinformationen verfügbar sind.