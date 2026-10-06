---
description: Beschreibung
title: Verbindung mit Salesforce herstellen
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 12ee914ed944c82694b9373f611e19cf040e2229
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 1%
---
# Verbindung mit Salesforce herstellen {#salesforce}

Mit Adobe Coworker-Kampagnen können Sie eine Verbindung zu Ihrem Salesforce-Konto herstellen, um auf Ihre Leads und Kontakte zuzugreifen.

>[!PREREQUISITES]
>
>Um diesen Connector verwenden zu können, müssen Sie zunächst über Folgendes verfügen:
>
>* Ein gültiges Salesforce-Konto
>* Die folgenden Berechtigungen in Salesforce: `api`, `sobjects.Contact.read`, `sobjects.Campaign.read`, `sobjects.CampaignMember.read`
>* Praktisch für die Salesforce[Instanz-URL, -Client-ID und -](https://help.salesforce.com/s/articleView?id=xcloud.remoteaccess_oauth_client_credentials_flow.htm&type=5#:~:text=DESCRIPTION-,client_id,-The%20consumer%20key)

## So verbinden Sie sich

1. Klicken Sie auf der [Startseite von ](https://coworker-campaigns.experience.adobe.com/)-Kampagnen auf **Anpassen** und wählen Sie **Connectoren**.

   ![Coworker-Kampagnen - linker Navigationsbereich mit hervorgehobener Option „Anpassen“ und „Connectoren“](./assets/salesforce-1.png)

1. Klicken Sie **Integration hinzufügen**.

   ![Schaltfläche „Integration hinzufügen“ im Bildschirm „Connectoren“](./assets/salesforce-2.png)

   >[!NOTE]
   >
   >Wenn dies nicht Ihre erste Integration ist, lautet die Schaltfläche „Connector hinzufügen“.

1. Klicken Sie in der Salesforce-Zeile auf **Verbinden**.

   ![](./assets/salesforce-3.png)

1. Geben Sie Ihre Salesforce **Instanz-**, **Client-ID** und **Client-Geheimnis** ein. Klicken Sie auf **Verbinden**.

   >[!NOTE]
   >
   >* In Salesforce: Client ID = Consumer Key und Client Secret = Consumer Secret.
   >
   >* In Ihrem Salesforce-Konto finden Sie Ihre Instanz-URL in der Adressleiste Ihres Browsers oder indem Sie zu **Setup** > **Unternehmenseinstellungen** > **Meine Domain** navigieren.

   ![](./assets/salesforce-4.png)

Nach dem Verbinden wird Salesforce in der Connectoren-Liste angezeigt und kann beim Verknüpfen einer Lead- oder Kontaktliste mit der Synchronisierung aus Salesforce ausgewählt werden.

**Verbindung trennen:**

1. Suchen Sie im Bildschirm „Connectoren“ die Kachel Salesforce und klicken Sie auf **Verwalten**.

   ![](./assets/salesforce-5.png)

1. Klicken Sie **Trennen** (Sie müssen Ihr Client-Geheimnis jetzt nicht erneut eingeben).

   ![](./assets/salesforce-6.png)

1. Klicken Sie **zur Bestätigung erneut** Trennen“.

   ![](./assets/salesforce-7.png)
