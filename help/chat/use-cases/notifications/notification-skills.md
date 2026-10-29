---
title: Benachrichtigungsfähigkeiten
description: Erfahren Sie, wie Sie Benachrichtigungen mit Adobe CX Enterprise Coworker überprüfen und verwalten können. Suchen Sie nach Aktionselementen, legen Sie Erinnerungen fest und wählen Sie aus, wie Sie Benachrichtigungen erhalten.
role: Admin,User,Developer,Leader
level: Beginner
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 1ec3a8bf6dff44df068529cf1f7ceb699a027d65
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 1%
---

# Benachrichtigungsfähigkeiten {#notification-skills}

Verwenden Sie Benachrichtigungsfähigkeiten in Adobe CX Enterprise Coworker, um Benachrichtigungen zu überprüfen, Aktionselemente zu identifizieren und Benachrichtigungseinstellungen über Konversationen zu verwalten. Arbeiten Sie mit den Benachrichtigungen, die Sie bereits im Benachrichtigungsbereich in Ihren Adobe CX Enterprise-Programmen erhalten.

Fassen Sie Benachrichtigungen zusammen, suchen Sie bestimmte Elemente und gruppieren Sie wiederholte Benachrichtigungen in verschiedene Probleme. Öffnen Sie eine Benachrichtigung in ihrer Anwendung, markieren Sie sie als gelesen oder ungelesen oder legen Sie eine Erinnerung fest.

>[!AVAILABILITY]
>
>Benachrichtigungsfähigkeiten stehen allen Kunden zur Verfügung, die Zugriff auf Adobe CX Enterprise Coworker haben. Es ist keine zusätzliche Einrichtung erforderlich, um die Fähigkeiten zu verwenden.
>
>Um Benachrichtigungen in [!DNL Slack] zu erhalten, muss Ihr Unternehmen über einen verbundenen [!DNL Slack]-Arbeitsbereich verfügen.

## Voraussetzungen {#before-you-begin}

Bevor Sie beginnen, stellen Sie Folgendes sicher:

* Zugriff auf Adobe CX Enterprise Coworker.
* Zugriff auf eine oder mehrere Adobe CX Enterprise-Anwendungen, die Ihnen Benachrichtigungen senden.
* Ein verbundener [!DNL Slack] Arbeitsbereich für Ihre Organisation, wenn Sie Benachrichtigungen in [!DNL Slack] erhalten möchten.

## Prüfen von Benachrichtigungen und Ausführen von Maßnahmen {#review-and-act}

Beginnen Sie mit einer Zusammenfassung, verfeinern Sie dann Ihre Anfrage und reagieren Sie auf eine bestimmte Benachrichtigung.

1. Öffnen Sie den Kollegen-Chat. Anweisungen finden Sie unter [Erste Schritte mit dem Coworker Chat](/help/chat/ui-guide.md).
1. Geben Sie eine Anfrage in das Feld **[!UICONTROL Mitarbeiter um alles bitten]** ein und wählen Sie dann **[!UICONTROL Senden]**. Beispiel:

   *„Was braucht heute meine Aufmerksamkeit?“*

1. Überprüfen Sie die Benachrichtigungen, die Maßnahmen erfordern, und die für die Sensibilisierung bereitgestellten Benachrichtigungen.

   ![Coworker Chat listet Benachrichtigungen auf, die als Reaktion auf eine Anfrage bearbeitet werden müssen, was heute beachtet werden muss.](./assets/review-needs-action.png)

1. Geben Sie eine Folgefrage ein, um die Ergebnisse einzugrenzen. Beispiel:

   *„Gibt es aufgrund dieser Benachrichtigungen Fehler in Experience Platform, die ich kennen sollte?“*

   ![Coworker Chat verfeinert die Benachrichtigungsergebnisse bei der Beantwortung einer Frage zu Fehlern in Experience Platform.](./assets/refine-platform-failures.png)

1. Um Details zu einer Benachrichtigung bitten oder sie in der Anwendung öffnen, um sie zu untersuchen.
1. Bitten Sie, eine Benachrichtigung als gelesen zu markieren oder eine Erinnerung festzulegen. Beispiel:

   *„Erinnere mich morgen an den Warnhinweis für die eingehende Ereignisrate mit hoher Priorität.“*

   ![Der Kollege-Chat bestätigt eine Erinnerung für morgen, nachdem Sie angegeben haben, welcher Warnhinweis mit der Rate eingehender Ereignisse verwendet werden soll.](./assets/reminder-confirmation.png)

Setzen Sie die Unterhaltung fort, ohne den Kontext früherer Anfragen zu wiederholen. Wenn Ihre Anfrage für mehrere Benachrichtigungen, Anwendungen oder Einstellungen gelten könnte, beantworten Sie die klärende Frage, bevor Sie fortfahren.

Sie erhalten vor einer Änderung, die über Ihre Anforderung hinausgeht, eine Bestätigungsanfrage.

## Unterstützte Anwendungsfälle {#supported-use-cases}

Verwenden Sie Benachrichtigungsfähigkeiten, um die an Sie gesendeten Benachrichtigungen zu überprüfen, darauf zu reagieren und zu verwalten, wie Sie sie erhalten.

>[!NOTE]
>
>Benachrichtigungsfähigkeiten senden, teilen oder löschen keine Benachrichtigungen.

### Identifizieren von Aktionselementen {#identify-action-items}

Fragen Sie, welche Benachrichtigungen in Ihren Adobe CX Enterprise-Programmen bearbeitet werden müssen.

Beispiel-Eingabeaufforderungen:

* „Worauf muss ich mich heute konzentrieren?“
* „Fangen Sie mich auf.“
* „Irgendetwas ausstehend für mich?“

### Zusammenfassen von Benachrichtigungen {#summarize-notifications}

Anfordern einer Zusammenfassung für einen Zeitraum oder eine Anwendung. Überprüfen Sie Aktionselemente getrennt von Benachrichtigungen, die zur Sensibilisierung bereitgestellt werden. Wiederholte Benachrichtigungen werden in verschiedenen Problemen gruppiert und nicht einzeln aufgeführt.

Beispiel-Eingabeaufforderungen:

* „Fassen Sie meine Benachrichtigungen der letzten Woche zusammen.“
* „Geben Sie mir einen Überblick über meine Benachrichtigungen vom letzten Tag.“
* „Zusammenfassen meiner Adobe Journey Optimizer-Benachrichtigungen.“

![Im Kollegen-Chat wird eine Benachrichtigungszusammenfassung in Elemente gruppiert, für die Aktionen erforderlich sind, und in Elemente, die zur Sensibilisierung bereitgestellt werden.](./assets/notification-summary.png)

### Spezifische Benachrichtigungen suchen {#find-specific-notifications}

Filtern Sie Benachrichtigungen nach Kriterien wie ungelesener Status, Genehmigungsanfragen, Fehlern, Fehlern oder Produktversionen.

Beispiel-Eingabeaufforderungen:

* „Nur ungelesene Benachrichtigungen anzeigen.“
* „Meine Genehmigungsanfragen anzeigen.“
* „Gibt es Warnhinweise zu kritischen Fehlern, die ich kennen sollte?“
* „Anzeigen von Versionshinweisen für Experience Platform&quot;

### Überprüfen der Benachrichtigungsdetails {#review-notification-details}

Fragen Sie nach den vollständigen Details einer Benachrichtigung, wie sie gesendet wurde. Wenn mehrere Benachrichtigungen Ihrer Anfrage entsprechen, geben Sie an, welche Sie meinen.

Beispiel-Eingabeaufforderungen:

* „Erzählen Sie mir mehr über die Journey-Benachrichtigung.“
* „Was bedeutet dieser Warnhinweis für mich?“

### Aktiv bei Benachrichtigungen {#act-on-notifications}

Öffnen Sie eine Benachrichtigung in ihrer Anwendung, markieren Sie Benachrichtigungen als gelesen oder ungelesen oder legen Sie eine Erinnerung fest. Wählen Sie eine Erinnerung für fünf Minuten, 15 Minuten, eine Stunde oder morgen.

Beispiel-Eingabeaufforderungen:

* „Markieren Sie diese Benachrichtigung als gelesen.“
* „Markiert diese Benachrichtigung als ungelesen.“
* „Erinnere mich in einer Stunde an diese Benachrichtigung.“
* „Markieren Sie alle meine Benachrichtigungen als gelesen.“

### Verwalten von Benachrichtigungseinstellungen {#manage-notification-preferences}

Fragen Sie nach Ihren aktuellen Einstellungen, bevor Sie ändern, wie Sie Benachrichtigungen erhalten. Geben Sie die Anwendungs- oder Benachrichtigungskategorie an, die Sie aktualisieren möchten.

| Voreinstellung | Verfügbare Änderungen |
| --- | --- |
| Versandkanäle | Aktivieren oder Deaktivieren von Benachrichtigungen innerhalb der Anwendung, E-Mail-Benachrichtigungen oder [!DNL Slack]-Benachrichtigungen für eine Anwendung oder Kategorie. |
| E-Mail-Häufigkeit | Wählen Sie Sofortiger E-Mail-Versand oder eine tägliche oder wöchentliche Zusammenfassung. |
| Kategoriepriorität | Wählen Sie aus, welche Benachrichtigungskategorien hohe Priorität haben. |
| Warnfenster einblenden | Wählen Sie aus, welche Benachrichtigungskategorien eingeblendete Warnfenster anzeigen sollen. |

Beispiel-Eingabeaufforderungen:

* „Was sind meine Benachrichtigungseinstellungen für Adobe Journey Optimizer?“
* „Deaktivieren Sie [!DNL Slack] Benachrichtigungen für Experience Platform.“
* „Meine tägliche Zusammenfassung auf wöchentlich umstellen.“
* „Benachrichtigungen zu Versionsaktualisierungen stummschalten.“
* „Senden Sie Adobe Journey Optimizer-Benachrichtigungen nur per E-Mail.“

Wenn Sie im Coworker Chat nach Planungsdetails gefragt werden, geben Sie den Tag, die Uhrzeit und die Zeitzone für Ihren wöchentlichen Auszug an.

![Im Coworker Chat wird gefragt, an welchem Tag die wöchentliche Zusammenfassung eintreffen soll, mit zusätzlichen Registerkarten für Zeit, Zeitzone und Überprüfung.](./assets/digest-schedule.png)

## Weitere Hilfe zu diesem Thema {#more-help}

Verwenden Sie diese Handbücher, um mit dem Coworker Chat zu beginnen oder die Experience Platform-Warnmeldungsaktivität zu untersuchen.

* [Erste Schritte mit dem Coworker Chat](/help/chat/ui-guide.md)
* [Warnhinweise für Kunden](/help/chat/use-cases/customer-alerts/customer-alerts.md)
