---
description: Verbinden Sie Ihr HubSpot-Konto mit Coworker Campaign, indem Sie einen Service-Schlüssel verwenden, um Kontaktlisten zu synchronisieren und dann die Integration jederzeit zu verwalten oder zu trennen.
title: Mit HubSpot verbinden
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 0%
---
# Mit HubSpot verbinden {#hubspot}

Mit Adobe Coworker Campaign können Sie Ihr HubSpot-Konto verbinden, um Kontaktlisten abzurufen.

>[!PREREQUISITES]
>
>Um diesen Connector verwenden zu können, müssen Sie zunächst über Folgendes verfügen:
>
>* Ein aktives HubSpot-Konto
>* Ein [Dienstschlüssel](https://developers.hubspot.com/docs/apps/developer-platform/build-apps/authentication/account-service-keys#create-a-service-key) der mit den folgenden hinzugefügten Bereichen erstellt wurde: `crm.objects.contacts.read`, `crm.objects.leads.read`, `crm.schemas.contacts.read`, `crm.lists.read`, `crm.export`

## So verbinden Sie sich

1. Klicken Sie auf der [Startseite von &#x200B;](https://coworker-campaigns.experience.adobe.com/)-Kampagnen auf **Anpassen** und wählen Sie **Connectoren**.

   ![Das Menü „Anpassen“ wurde in der Seitenleiste erweitert, wobei Connectoren ausgewählt sind](./assets/hubspot-1.png)

1. Klicken Sie **Integration hinzufügen**.

   ![Schaltfläche „Integration hinzufügen“ auf dem Bildschirm „Connectoren“](./assets/hubspot-2.png)

   >[!NOTE]
   >
   >Wenn dies nicht Ihre erste Integration ist, lautet die Schaltfläche „Connector hinzufügen“.

1. Klicken Sie in der HubSpot-Zeile auf **Verbinden**.

   ![HubSpot-Kachel mit hervorgehobener Schaltfläche „Verbinden“](./assets/hubspot-3.png)

1. Es wird ein Modal mit den erforderlichen Berechtigungen angezeigt (aufgeführt in den Voraussetzungen oben in diesem Artikel). Klicken Sie auf **Fortfahren**.

1. Geben Sie Ihren HubSpot **Service-Schlüssel** ein und klicken Sie auf **Verbinden**.

   ![HubSpot-Dialogfeld mit dem Dienstschlüsselfeld und der Schaltfläche „Verbinden“](./assets/hubspot-4.png)

Nach der Verbindung wird HubSpot in der Connectoren-Liste angezeigt und kann beim Verknüpfen einer Kontaktliste mit HubSpot zur Synchronisierung ausgewählt werden.

**Verbindung trennen:**

1. Suchen Sie im Bildschirm „Connectoren“ die Kachel HubSpot und klicken Sie auf **Verwalten**.

   ![Connectoren-Bildschirm mit hervorgehobenem HubSpot in Verbindung mit der Schaltfläche „Verwalten“](./assets/hubspot-5.png)

1. Klicken Sie **Trennen** (Sie müssen Ihren Service-Schlüssel jetzt nicht erneut eingeben).

   ![Das Dialogfeld „HubSpot verwalten“ mit der hervorgehobenen Schaltfläche „Trennen“](./assets/hubspot-6.png)

1. Klicken Sie **zur Bestätigung erneut** Trennen“.

   ![Bestätigungsdialogfeld zum Trennen der Verbindung mit hervorgehobener Schaltfläche „Trennen“](./assets/hubspot-7.png)
