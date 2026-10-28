---
description: Erfahren Sie, wie Sie Coworker for Teams mit Ihrem Salesforce-Konto verbinden, um auf Ihre Leads und Kontakte zuzugreifen.
title: Verbindung mit Salesforce herstellen
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 312450e09d9252f17cb2b5d471ee33e1a22b9a05
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%
---
# Verbindung mit Salesforce herstellen {#salesforce}

Ein Mitarbeiter für Teams ermöglicht es Ihnen, Ihr Salesforce-Konto zu verbinden, um auf Ihre Leads und Kontakte zuzugreifen.

>[!PREREQUISITES]
>
>Um diesen Connector verwenden zu können, müssen Sie zunächst über Folgendes verfügen:
>
>* Ein gültiges Salesforce-Konto
>* Die folgenden Berechtigungen in Salesforce: `api`, `sobjects.Contact.read`, `sobjects.Campaign.read`, `sobjects.CampaignMember.read`
>* Praktisch für die Salesforce[Instanz-URL, -Client-ID und -](https://help.salesforce.com/s/articleView?id=xcloud.remoteaccess_oauth_client_credentials_flow.htm&type=5#:~:text=DESCRIPTION-,client_id,-The%20consumer%20key){target="_blank"}

## So verbinden Sie sich

1. Klicken Sie auf der [Startseite für Teams](https://coworker-campaigns.experience.adobe.com/){target="_blank"} auf **Kontext** und wählen Sie **Connectoren**.

   ![Mitarbeiter für Teams haben die Navigation verlassen, wobei Kontext erweitert und Connectoren hervorgehoben wurden](./assets/salesforce-1.png)

1. Klicken Sie **Integration hinzufügen**.

   ![Schaltfläche „Integration hinzufügen“ im Bildschirm „Connectoren“](./assets/salesforce-2.png)

   >[!NOTE]
   >
   >Wenn dies nicht Ihre erste Integration ist, lautet die Schaltfläche „Connector hinzufügen“.

1. Klicken Sie in der Salesforce-Zeile auf **Verbinden**.

   ![Salesforce-Connector-Kachel mit der Schaltfläche „Verbinden“](./assets/salesforce-3.png)

1. Geben Sie Ihre Salesforce **Instanz-**, **Client-ID** und **Client-Geheimnis** ein. Klicken Sie auf **Verbinden**.

   >[!NOTE]
   >
   >* In Salesforce: Client ID = Consumer Key und Client Secret = Consumer Secret.
   >
   >* In Ihrem Salesforce-Konto finden Sie Ihre Instanz-URL in der Adressleiste Ihres Browsers oder indem Sie zu **Setup** > **Unternehmenseinstellungen** > **Meine Domain** navigieren.

   ![Salesforce-Dialogfeld mit Feldern wie URL, Client-ID und Client-Geheimnis verbinden](./assets/salesforce-4.png)

Nach dem Verbinden wird Salesforce in der Connectoren-Liste angezeigt und kann beim Verknüpfen einer Lead- oder Kontaktliste mit der Synchronisierung aus Salesforce ausgewählt werden.

**Verbindung trennen:**

1. Suchen Sie im Bildschirm „Connectoren“ die Kachel Salesforce und klicken Sie auf **Verwalten**.

   ![Connectoren-Bildschirm mit hervorgehobener Schaltfläche „Verwalten“ für Salesforce verbunden](./assets/salesforce-5.png)

1. Klicken Sie **Trennen** (Sie müssen Ihr Client-Geheimnis jetzt nicht erneut eingeben).

   ![Dialogfeld &quot;Salesforce verwalten“ mit hervorgehobener Schaltfläche „Trennen“](./assets/salesforce-6.png)

1. Klicken Sie **zur Bestätigung erneut** Trennen“.

   ![Bestätigungsdialogfeld zum Trennen der Verbindung mit hervorgehobener Schaltfläche „Trennen“](./assets/salesforce-7.png)
