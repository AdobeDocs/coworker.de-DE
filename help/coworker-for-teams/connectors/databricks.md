---
description: Mit Coworker for Teams können Sie Unity-Katalogtabellen in Ihrem Datenblock-Arbeitsbereich verbinden und abfragen, um Zielgruppen in Kampagnen zu erstellen und zu aktivieren.
title: Verbindung zu Datenblöcken herstellen
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 1ec3a8bf6dff44df068529cf1f7ceb699a027d65
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%
---
# Verbindung zu Datenblöcken herstellen {#databricks}

Mit Coworker for Teams können Sie Unity-Katalogtabellen in Ihrem Datenblock-Arbeitsbereich verbinden und abfragen, um Zielgruppen in Kampagnen zu erstellen und zu aktivieren.

>[!PREREQUISITES]
>
>Um diesen Connector verwenden zu können, müssen Sie zunächst über Folgendes verfügen:
>
>* Ein aktives DataBricks-Konto
>* Ihr Databricks Workspace Host[SQL Warehouse Path](https://docs.databricks.com/aws/en/compute/sql-warehouse/create){target="_blank"}, [Personal Access Token](https://learn.microsoft.com/en-us/azure/databricks/dev-tools/auth/pat){target="_blank"} und [Unity Catalogs](https://learn.microsoft.com/en-us/azure/databricks/discover/database-objects){target="_blank"}.

## So verbinden Sie sich

1. Klicken Sie auf der [Startseite für Teams](https://coworker-campaigns.experience.adobe.com/){target="_blank"} auf **Kontext** und wählen Sie **Connectoren**.

   ![Mitarbeiter für Teams haben die Navigation verlassen, wobei Kontext erweitert und Connectoren hervorgehoben wurden](./assets/databricks-1.png)

1. Klicken Sie **Integration hinzufügen**.

   ![Schaltfläche „Integration hinzufügen“ im Bildschirm „Connectoren“](./assets/databricks-2.png)

   >[!NOTE]
   >
   >Wenn dies nicht Ihre erste Integration ist, lautet die Schaltfläche „Connector hinzufügen“.

1. Klicken Sie in der Zeile „Databricks“ auf **Verbinden**.

   ![Databricks-Connector-Kachel mit der Schaltfläche Verbinden](./assets/databricks-3.png)

1. Geben Sie Ihren Databricks **Workspace-Host**, **SQL-Warehouse-**, **Persönliches Zugriffstoken** und **Unity-Kataloge**. Klicken Sie auf **Verbinden**.

   >[!NOTE]
   >
   >Auf Ihrer Startseite von Databricks finden Sie den Workspace-Host direkt in der Adressleiste Ihres Browsers. Informationen zum Auffinden aller anderen Anmeldeinformationen finden Sie unter den Links **Voraussetzungen** oben in diesem Artikel.

   ![Verbinden des Dialogfelds „Datenblöcke“ mit Feldern für den Workspace-Host, den SQL-Warehouse-Pfad, das persönliche Zugriffstoken und die Unity-Kataloge](./assets/databricks-4.png)

Nach der Verbindung werden Datenblöcke in der Liste „Connectoren“ angezeigt.

**Verbindung trennen:**

1. Suchen Sie im Bildschirm „Connectoren“ die Kachel Datenblöcke und klicken Sie auf **Verwalten**.

1. Klicken Sie **Trennen** (Sie müssen Ihr persönliches Zugriffstoken jetzt nicht erneut eingeben).

1. Klicken Sie **zur Bestätigung erneut** Trennen“.
