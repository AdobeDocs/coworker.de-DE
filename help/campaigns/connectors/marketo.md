---
description: Erfahren Sie, wie Sie Ihr Marketo Engage-Konto mit Coworker Campaign verbinden, damit Sie Smart- und Static-Listen von Marketo synchronisieren können.
title: Verbindung mit Marketo Engage herstellen
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%
---
# Verbindung mit Marketo Engage herstellen {#marketo}

Mit Adobe Coworker-Kampagnen können Sie Ihr Marketo Engage-Konto verbinden, um intelligente und statische Listen abzurufen.

>[!PREREQUISITES]
>
>Um diesen Connector verwenden zu können, müssen Sie zunächst über Folgendes verfügen:
>
>* Ein gültiges Marketo Engage-Konto
>* Ihre Marketo **Instanz-URL**
>* Ein [benutzerdefinierter Service](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/custom-services#custom-services-1) der für Coworker-Kampagnen in Marketo erstellt wurde, mit [Client-ID und ](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/authentication#creating-an-access-token) Client-Geheimnis)

## So verbinden Sie sich

1. Klicken Sie auf der [Startseite von ](https://coworker-campaigns.experience.adobe.com/)-Kampagnen auf **Anpassen** und wählen Sie **Connectoren**.

   ![Coworker-Kampagnen - linker Navigationsbereich mit hervorgehobener Option „Anpassen“ und „Connectoren“](./assets/marketo-1.png)

1. Klicken Sie **Integration hinzufügen**.

   ![Schaltfläche „Integration hinzufügen“ im Bildschirm „Connectoren“](./assets/marketo-2.png)

   >[!NOTE]
   >
   >Wenn dies nicht Ihre erste Integration ist, lautet die Schaltfläche „Connector hinzufügen“.

1. Klicken Sie in der Marketo-Zeile auf **Verbinden**.

   ![Marketo-Connector-Kachel mit der Schaltfläche „Verbinden“](./assets/marketo-3.png)

1. Geben Sie Ihre Marketo **Instanz-**, **Client-ID** und **Client-Geheimnis** ein. Klicken Sie auf **Verbinden**.

   >[!NOTE]
   >
   >Sie finden Ihre Marketo-Instanz-URL in der Adressleiste Ihres Browsers, wenn Sie Ihre Seite „Mein Marketo&quot; aufrufen.

   ![Marketo-Dialogfeld mit Feldern wie URL, Client-ID und Client-Geheimnis verbinden](./assets/marketo-4.png)

Nach dem Verbinden wird Marketo in der Connectoren-Liste angezeigt und kann beim Verknüpfen einer Kontaktliste mit Marketo ausgewählt werden.

**Verbindung trennen:**

1. Suchen Sie im Bildschirm „Connectoren“ die Kachel Marketo und klicken Sie auf **Verwalten**.

   ![Bildschirm „Connectoren“ mit der Kachel &quot;Marketo&quot;, die den Status „Verbunden“ und die Schaltfläche „Verwalten“ anzeigt](./assets/marketo-5.png)

1. Klicken Sie **Trennen** (Sie müssen Ihr Client-Geheimnis jetzt nicht erneut eingeben).

   ![Dialogfeld &quot;Marketo verwalten“ mit den Feldern „Instanz-URL“ und „Client-ID“ sowie einer Schaltfläche „Trennen“](./assets/marketo-6.png)

   >[!NOTE]
   >
   >Nachdem die Instanz-URL zum ersten Mal hinzugefügt wurde, wird standardmäßig die REST-Endpunkt-URL verwendet, die auf `*.mktorest.com` endet.

1. Klicken Sie **zur Bestätigung erneut** Trennen“.

   ![Bestätigungsdialogfeld zum Trennen der Verbindung](./assets/marketo-7.png)
