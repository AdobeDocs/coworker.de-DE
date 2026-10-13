---
source-git-commit: e5bf2a0a2ee55513b32442f70d01dc5825ac9d6a
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 5%
---
# Dokumentation zu CX Enterprise Coworker

Source für den Adobe CX Enterprise Coworker-Dokumentationssatz

## Veröffentlichungskonfiguration

Verwenden Sie die Workflows für die Validierung und Spiegelung freigegebener Artikel in `.github/workflows/`.
Der Validierungs-Workflow wird für Pull-Anfragen ausgeführt und per Push an `main` gesendet.
Der Spiegelungs-Workflow wird ausgeführt, wenn Sie auf `main` pushen.

Verwenden Sie `markdownlint_custom.json` für Überschreibungen und `linkcheckexclude.json` von Markdown-Regeln, z. B. URL-Ausschlüsse.
Die `pipeline.opts` folgt der Konfiguration der Link-Überprüfung in `cx-enterprise-ai.en`.
Fügen Sie URL-Umleitungen zu `redirects.csv` mithilfe der `source,dest` Spalten hinzu.
