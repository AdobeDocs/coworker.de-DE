---
title: Onboarding von Daten mit Kollegen
description: Erfahren Sie, wie Sie die Data Onboarding-Kenntnisse in CX Coworker nutzen, um neue Datenquellen mithilfe eines konversativen Workflows in Adobe Experience Platform zu integrieren.
hide: true
source-git-commit: 8f7d5307b1928c052f020ca5e7aae3feee7af03e
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 3%
---

# Onboarding von Daten mit Kollegen

>[!AVAILABILITY]
>
>Die Data Onboarding-Kenntnisse befinden sich in der Beta-Phase. Dokumentation und Funktionalitäten können sich ändern.
>
>Die Data Onboarding-Kenntnisse stehen Kunden mit Zugriff auf Adobe CX Enterprise Coworker zur Verfügung, wobei diese auch für Ihr Unternehmen aktiviert werden müssen. <!-- VERIFY BEFORE PUBLISH: confirm exact permission/entitlement name with Umesh Gohil, PLAT-296546. -->

Verwenden Sie die Kenntnisse zum Daten-Onboarding in CX Coworker, um neue Daten mithilfe eines einzigen Konversations-Workflows in Adobe Experience Platform zu integrieren. Anstatt in mehreren Bildschirmen zu navigieren, um eine Quelle zu verbinden und ein Schema manuell zu erstellen, beschreiben Sie Ihre Absicht und Ihr Kollege führt Sie durch die Quellenauswahl, die Datenqualität, die semantische Anreicherung, die Schemazuordnung, die Schemaerstellung und die Datenflusserstellung.

<!-- VERIFY BEFORE PUBLISH: confirm the loaded skill name ("Onboard Data to Experience Platform") and the exact post-landing prompt/flow with Umesh Gohil once flag access is arranged. -->

## Voraussetzungen {#prerequisites}

Bevor Sie beginnen, stellen Sie Folgendes sicher:

- Zugriff auf Adobe Experience Platform und die entsprechende Organisation und Sandbox.
- Zugriff auf Adobe CX Enterprise Coworker mit aktiviertem Data Onboarding für Ihr Unternehmen.
- Berechtigung zum Erstellen von Schemata in Adobe Experience Platform.

Anweisungen zum Installieren von Plug-ins finden Sie im [Handbuch zur Coworker-Benutzeroberfläche](https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/ui-guide).

## Verwenden der Data Onboarding-Kenntnisse {#use-the-data-onboarding-skill}

Heute beginnt das Daten-Onboarding mit der Schemaerstellung in der Experience Platform-Benutzeroberfläche, die Coworker mit Ihren bereits ausgefüllten Absichten öffnet.

So verwenden Sie die Data Onboarding-Kenntnisse:

1. Navigieren Sie in Adobe Experience Platform zu **[!UICONTROL Schemata]** und wählen Sie dann **[!UICONTROL Schema erstellen]** aus.
1. Wählen **[!UICONTROL Dialogfeld „Schema erstellen]** die Option **[!UICONTROL Daten mit KI]** und dann **[!UICONTROL Auswählen]**.

   ![Das Dialogfeld „Schema erstellen“ mit ausgewählter Option „Daten integrieren“.](./assets/data-onboarding-skill/create-a-schema-dialog.png)

1. CX Coworker wird in einer neuen Browser-Registerkarte geöffnet, auf der eine Eingabeaufforderung mit der Absicht der Schemaerstellung vorausgefüllt ist. Sie müssen es also nicht erneut angeben.
1. Wählen Sie eine Quelle aus, von der aus Sie sich anmelden möchten, wenn Sie dazu aufgefordert werden, z. B. [!DNL Amazon S3], [!DNL Data Landing Zone], [!DNL Delta Share] oder [!DNL Marketo].

   <!-- VERIFY BEFORE PUBLISH: screenshot of the Coworker landing/session-start state does not exist yet anywhere. Capture once flag access is confirmed. -->

1. Setzen Sie das Gespräch mit Ihrem Kollegen fort, indem Sie die Datenqualität, die semantische Anreicherung, die Schemazuordnung und die Schemaerstellung überprüfen und jeden Schritt bei der Durchführung bestätigen.

Weitere Informationen zur Verwendung von CX Coworker finden Sie im [Handbuch zur Benutzeroberfläche für Kollegen](https://experienceleague.adobe.com/de/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/ui-guide).

## Unterstützte Anwendungsfälle {#supported-use-cases}

Erkunden Sie die Teile des Onboarding-Workflows, zu dessen Abschluss Sie die Data Onboarding-Kenntnisse benötigen.

### Quelle auswählen und verbinden

Anstatt einen Quell-Connector manuell zu finden und zu konfigurieren, beschreiben Sie die Daten, die Sie einbringen möchten, und lassen Sie Kollegen dabei helfen, die richtige Quelle zu identifizieren.

### Überprüfen der Datenqualität

Der Mitarbeiter zeigt Datenqualitätssignale für die ausgewählte Quelle an, bevor Sie sich zu einem Schema bekennen, damit Sie Probleme früher im Prozess erkennen können.

### Daten semantisch anreichern

Coworker schlägt semantische Bedeutung für eingehende Felder vor, reduziert den manuellen Aufwand beim Zuordnen von Rohfeldern zu Standarddefinitionen.

### Zuordnen und Erstellen eines Schemas

Ein Mitarbeiter ordnet überprüfte Felder einem neuen oder vorhandenen Schema zu und erstellt sie direkt in Adobe Experience Platform im Rahmen derselben Konversation.

### Erstellen eines Datenflusses

Ein Mitarbeiter schließt das Onboarding ab, indem er den Datenfluss erstellt, der erforderlich ist, um die Daten laufend einzubringen.

## Nächste Schritte {#next-steps}

Nach dem Lesen dieses Handbuchs sollten Sie verstehen, wie Sie mit der Schemaerstellung beginnen und was Sie damit in CX Coworker erreichen können.

Informationen zum Verfahren der Experience Platform-Benutzeroberfläche und zu Zugriffs-/Eignungsszenarien finden Sie [Onboarding von Daten mit KI](https://experienceleague.adobe.com/de/docs/experience-platform/xdm/ui/resources/schemas#data-onboarding-skill) im Handbuch zur Benutzeroberfläche für Schemata .
