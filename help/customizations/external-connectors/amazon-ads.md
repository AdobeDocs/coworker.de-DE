---
title: Externer Amazon Ads-Connector
description: Erfahren Sie, wie Sie den externen Amazon Ads-Connector in CX Enterprise Coworker für Ihr Unternehmen einrichten und sich mit Amazon anmelden, um Amazon Ads-Tools im Chat zu verwenden.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Dieser Connector befindet sich in der Betaphase."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 80dda0b442d6c7fe560c965b985f58173b73fe13
workflow-type: tm+mt
source-wordcount: '3078'
ht-degree: 1%
---

# Externer Amazon Ads-Connector {#amazon-ads}

Verwenden Sie den externen Connector [!DNL Amazon Ads] , um mit Ihren [!DNL Amazon Ads] in Adobe CX Enterprise Coworker zu arbeiten. Nachdem Sie den Connector eingerichtet haben, fragen Sie Ihren Kollegen, auf welche Werbekonten Sie zugreifen können, und prüfen Sie Kampagnen, Berichte, Abrechnungen und andere Kontoinformationen. Der Connector ist ein von [!DNL Amazon] gehosteter MCP-Server (Model Context Protocol).

>[!AVAILABILITY]
>
>Der externe [!DNL Amazon Ads]-Connector befindet sich in der Beta-Phase. Die Dokumentation und die Funktionalität können sich ändern.

## Connector-Konfiguration {#connector-configuration}

Der Connector-Konfigurationsprozess besteht aus drei separaten Teilen:

* **[!DNL Amazon]:** Ein [!DNL Amazon Ads]-Konto-Administrator gewährt jedem Mitglied Zugriff auf die Werbekonten, die es benötigt. Wenn Ihr Unternehmen seine eigene OAuth-App verwendet, bestätigt der App-Inhaber seine Genehmigung und registriert die Coworker-Umleitungs-URL.
* **Einrichten der Organisation:** Ein Mitarbeiter-Administrator konfiguriert den Connector einmal für die gesamte Organisation. Der Administrator wählt eine Region, eine OAuth-Anwendung und die Tools aus, die Mitglieder verwenden können.
* **Mitglied anmelden** Jedes Mitglied meldet sich mit seinem eigenen [!DNL Amazon] an. Mitglieder können nur auf die Werbekonten zugreifen, zu deren Nutzung ihr [!DNL Amazon]-Konto berechtigt ist.

Beim Speichern der Organisationskonfiguration werden weder Mitglieder angemeldet noch [!DNL Amazon Ads] Berechtigungen erteilt. Jedes Mitglied muss bereits über den erforderlichen Zugriff in [!DNL Amazon Ads] verfügen und sich separat anmelden.

## Voraussetzungen {#prerequisites}

Bevor Sie beginnen, stellen Sie Folgendes sicher:

* **Coworker access:** Ein Konto mit der Berechtigung zum Verwalten von Organisations-Connectoren in einer Organisation, in der der [!DNL Amazon Ads]-Connector verfügbar ist.
* **Advertising-Konten:** Die Werbekonten, die Sie verwenden möchten, und deren [!DNL Amazon Ads] Region sowie Mitglieder mit den erforderlichen Berechtigungen für diese Konten. Weitere Informationen finden Sie unter [Werbekontenzugriff gewähren](#grant-member-access).
* **Eine OAuth-Anwendungsentscheidung:** Sie zwischen den folgenden Optionen:
  * **Adobe-verwaltetes OAuth-Programm:** Adobe verwaltet die App-Registrierung und deren Anmeldeinformationen. Die verwaltete App muss in Ihrer Umgebung verfügbar sein.
  * **Ihre eigene OAuth-Anwendung:** Eine [!DNL Login with Amazon]-App, die für die [!DNL Amazon Ads]-API genehmigt wurde, deren OAuth-Client-ID und Client-Geheimnis sowie ein Administrator, der sein Sicherheitsprofil bearbeiten kann. Ein registriertes Sicherheitsprofil allein erteilt keine [!DNL Amazon Ads] API-Genehmigung.

Das geführte Setup unterstützt eine [!DNL Amazon Ads] und eine Region pro Organisation. Jedes Mitglied meldet sich mit seinem eigenen [!DNL Amazon] an. Die von Adobe verwaltete App ist eine Registrierung für eine freigegebene App, kein freigegebenes [!DNL Amazon].

## Amazon-Zugriff vorbereiten {#prepare-amazon}

Bereiten Sie vor dem Konfigurieren des Connectors in Coworker Ihre App und den Kontozugriff in [!DNL Amazon] vor. Der Zugriff auf die App-Einrichtung und der Zugriff auf die Werbedaten sind getrennt voneinander. Mitglieder, die den Connector verwenden, benötigen keine Berechtigung zum Bearbeiten der App.

### App-Genehmigung bestätigen {#confirm-app-approval}

Wenn Sie Ihre eigene OAuth-Anwendung verwenden, bitten Sie den App-Inhaber, das richtige [!DNL Login with Amazon]-Sicherheitsprofil und die [!DNL Amazon Ads]-API-Genehmigung zu bestätigen. Das Erstellen eines Sicherheitsprofils oder das Anzeigen der App in der [!DNL Amazon] Developer Console ersetzt nicht [!DNL Amazon Ads] API-Genehmigung. Weitere Informationen finden Sie unter [Amazon Ads MCP - Erste Schritte](https://advertising.amazon.com/API/docs/en-us/mcp/get-started) und [Herstellen einer Verbindung zum Ads MCP-Server mithilfe von OAuth](https://advertising.amazon.com/API/docs/en-us/mcp/oauth) in der [!DNL Amazon Ads].

Für Ihre eigene App wendet Coworker die folgenden Einstellungen automatisch an. Diese Werte werden nicht in das Dialogfeld „Setup“ eingegeben.

| Einstellung | Wert |
| --- | --- |
| Autorisierungs-URL | `https://lwa.amazon.com/ap/oa` |
| Token-URL | `https://api.amazon.com/auth/o2/token` |
| Angeforderter Umfang | `advertising::campaign_management` |
| Proof Key for Code Exchange (PKCE) | Aktiviert |
| Token-Endpunkt-Client-Authentifizierung | `client_secret_post` als vertraulicher Kunde |
| Dynamische Client-Registrierung | Nicht unterstützt |
| Transport- und Tool-Zeitüberschreitung | Streamable HTTP, 60 Sekunden |

Wenn Sie die von Adobe verwaltete OAuth-Anwendung verwenden, verwaltet Adobe die App-Registrierung und deren Anmeldeinformationen. Sie müssen diesen Schritt nicht ausführen oder Anmeldeinformationen für die App eingeben.

### Registrieren der Umleitungs-URL {#register-redirect-url}

Wenn Sie Ihre eigene OAuth-Anwendung verwenden, registrieren Sie die Coworker-Umleitungs-URL in Ihrer [!DNL Login with Amazon]-App:

1. Öffnen Sie in der **[!UICONTROL das Dialogfeld &quot;Amazon Ads für Ihr]** konfigurieren“, wie unter [Konfigurieren des Connectors für Ihr Unternehmen](#configure-organization) beschrieben. Wählen Sie **[!UICONTROL Eigene OAuth-Anwendung verwenden]** aus, um die **[!UICONTROL Umleitungs-URL]** anzuzeigen, und kopieren Sie dann den vollständigen Wert.
1. Suchen Sie in [Anmeldung mit der Amazon](https://developer.amazon.com/loginwithamazon/console/site/lwa/overview.html) das Sicherheitsprofil für Ihre App. Wählen Sie **[!UICONTROL Verwalten]** > **[!UICONTROL Web-Einstellungen]** und klicken Sie dann auf **[!UICONTROL Bearbeiten]**.
1. Fügen Sie die vollständige Umleitungs-URL unter **[!UICONTROL Zulässige Rückgabe-URLs]** hinzu und speichern Sie dann. Wenn andere Teams die App gemeinsam nutzen, behalten Sie die vorhandenen URLs bei und lassen Sie sich vom App-Inhaber genehmigen, bevor Sie die Einstellungen ändern.
1. Notieren Sie sich die OAuth-Client-ID und das Client-Geheimnis aus demselben Sicherheitsprofil. Sie werden beim Konfigurieren [ Connectors ](#configure-organization).

Kopieren Sie immer die Umleitungs-URL aus dem Dialogfeld „Mitarbeiter“ in die Umgebung, die Sie einrichten. Erstellen Sie die URL nicht selbst, verwenden Sie die URL der Coworker-Seite in Ihrem Browser oder verwenden Sie eine Umleitungs-URL aus einer anderen Umgebung oder einem MCP-Client. Weitere Informationen finden Sie unter [Registrieren bei Amazon](https://developer.amazon.com/docs/login-with-amazon/register-web.html) in der [!DNL Amazon].

>[!NOTE]
>
>Wenn in der **[!UICONTROL Umleitungs]** URL) nur der `/connectors/oauth/callback` Pfad angezeigt wird, unterstützt Ihre Umgebung noch nicht die Anmeldung für diesen Connector. Registrieren Sie keinen Teilpfad oder raten Sie den Host-Namen. Wenden Sie sich an den Adobe-Support.

### Werbekonto-Zugriff gewähren {#grant-member-access}

Ein Administrator des [!DNL Amazon Ads]-Kontos lädt jedes Mitglied zu den Werbekonten ein, die es benötigt:

1. Öffnen Sie die [Amazon Ads](https://advertising.amazon.com/)Konsole und wählen Sie dann **[!UICONTROL Konto ändern]** aus, um das Advertiser- oder Manager-Konto auszuwählen.
1. Wählen Sie **[!UICONTROL Administration]** > **[!UICONTROL Kontozugriff und Einstellungen]** > **[!UICONTROL Benutzer]** > **[!UICONTROL Benutzer einladen]**. Die genauen Optionen hängen vom Kontotyp ab. Laden Sie das [!DNL Amazon] Konto des Mitglieds mit den Mindestberechtigungen für die Aufgaben ein, die es ausführen möchte.
1. Überprüfen Sie für ein Manager-Konto, ob der Zugriff das gesamte Manager-Konto oder nur ausgewählte verknüpfte Werbetreibende abdeckt. Bitten Sie das Mitglied, die Einladung mit demselben [!DNL Amazon]-Konto anzunehmen, das es für einen Kollegen verwendet.
1. Bestätigen Sie, dass das Mitglied den Advertiser in [!DNL Amazon Ads] auswählen kann. Notieren Sie den erwarteten Kontonamen, die Region und die Advertiser-ID in einem genehmigten internen Datensatz, damit Sie den Zugriff später in der Co-Worker-Instanz bestätigen können.

Wählen Sie die am wenigsten privilegierte Rolle aus, die die von Ihnen geplanten Aufgaben unterstützt. Administratorzugriff nicht nur gewähren, um eine Zugriffsprüfung erfolgreich zu machen. Der Zugriff auf eine [!DNL Amazon Marketing Cloud]-Instanz ist getrennt vom Zugriff auf Advertiser-Kampagnen . Weitere Informationen finden Sie in der folgenden [!DNL Amazon Ads]:

* [Verwalten von Benutzern in einem Manager-Konto](https://advertising.amazon.com/help/G4M4JGKGV2VAY9JC)
* [Hinzufügen oder Entfernen von Benutzern aus Ihrem Konto](https://advertising.amazon.com/help/GDQVHVQMY9F88PCA)
* [Grundlegendes zu Kontoberechtigungen](https://advertising.amazon.com/help/GM4EFDQQPG9LGL3F)
* [Amazon Ads-API-Berechtigungen](https://advertising.amazon.com/API/docs/en-us/guides/account-management/permissions)

## Konfigurieren des Connectors für Ihre Organisation {#configure-organization}

Administratoren stellen den [!DNL Amazon Ads]-Connector für alle Personen in der Organisation zur Verfügung. Änderungen auf der Seite „Organisation“ gelten für alle Benutzer in Ihrer Organisation. Mitglieder können die Organisationsverbindung nicht über den Bereich **[!UICONTROL Benutzer]** konfigurieren.

1. Öffnen Sie **[!UICONTROL Anpassungen]**, wählen Sie **[!UICONTROL Organisation]** und dann **[!UICONTROL Externe Connectoren]** aus. Wählen Sie auf der Karte {0 ]**Amazon Ads**[!UICONTROL  die Option „Konfigurieren ]**aus.**[!UICONTROL 

   Das Dialogfeld **[!UICONTROL Amazon Ads für Ihr Unternehmen konfigurieren]** wird mit den Abschnitten **[!UICONTROL Verbindungsdetails]**, **[!UICONTROL Tools für Benutzer verfügbar]** und **[!UICONTROL Zugriff und Berechtigungen]** geöffnet. Nach dem Speichern der Konfiguration zeigt die Karte **[!UICONTROL Konfiguration gespeichert]** und **[!UICONTROL Konfigurieren]** Änderungen an **[!UICONTROL Konfiguration anzeigen]**.

1. Wählen Sie unter **[!UICONTROL Amazon Ads-]** die Region aus, die Ihren Werbekonten entspricht. Ein Mitarbeiter zeigt die MCP-Server-URL für die Region unter der Auswahl an.

   | Region | MCP Server URL |
   | --- | --- |
   | [!UICONTROL Nordamerika] (Standard) | `https://advertising-ai.amazon.com/mcp` |
   | [!UICONTROL Europa] | `https://advertising-ai-eu.amazon.com/mcp` |
   | [!UICONTROL Ferner Osten] | `https://advertising-ai-fe.amazon.com/mcp` |

   Die geführte Einrichtung spart eine Region. Um später Regionen zu wechseln, entfernen Sie die Verbindung und richten Sie sie erneut ein. Jedes Mitglied muss sich dann erneut anmelden. Planen Sie die Änderung also, bevor Sie eine funktionierende Verbindung unterbrechen.

1. Wählen Sie ein **[!UICONTROL OAuth-Programm]**:

   * **[!UICONTROL Adobe-verwaltetes OAuth-Programm]:** Adobe stellt die [!DNL Amazon Ads]-App bereit, sodass Sie keine App-Anmeldeinformationen eingeben müssen. Jedes Mitglied meldet sich mit seinem eigenen [!DNL Amazon] an und autorisiert die Adobe-App.

     ![Konfigurieren Sie Amazon Ads für Ihr Organisationsdialogfeld mit der Region Nordamerika, der ausgewählten von Adobe verwalteten OAuth-Anwendung und den reduzierten Toolgruppen.](./assets/amazon-ads/org-configure.png){width="500" zoomable="yes"}

   * **[!UICONTROL Eigene OAuth-Anwendung verwenden]:** Jedes Mitglied autorisiert Ihre Organisations-App mit seinem eigenen [!DNL Amazon]. Führen **[!UICONTROL unter „Ihr Amazon]** Programm“ die folgenden Schritte aus:

     1. Stellen Sie sicher, dass die **[!UICONTROL Umleitungs-URL]** in Ihrer App registriert ist. Weitere Informationen finden Sie unter &quot;[ der Umleitungs-URL](#register-redirect-url).
     1. Geben Sie die **[!UICONTROL Amazon-App]** ID und das **[!UICONTROL Geheimnis der Amazon-App]** ein. Das Feld **[!UICONTROL Amazon-App]** ID1 akzeptiert die OAuth-Client-ID, keine Advertiser-ID, keine Manager-Account-ID oder [!DNL Amazon] Anwendungs-ID. Coworker speichert die Werte, die Sie als Organisationsgeheimnisse eingeben.
     1. Um stattdessen gespeicherte Anmeldeinformationen wiederzuverwenden, wählen Sie **[!UICONTROL Vorhandene geheime Daten verwenden]** aus. Wählen Sie dann das **[!UICONTROL Geheimnis, das die App-ID]**, und das **[!UICONTROL Geheimnis, das das App-Geheimnis]**. Wenn Ihre Organisation noch keine Geheimnisse hat, fügen Sie sie in **[!UICONTROL Einstellungen]** > **[!UICONTROL Geheimnisse]** hinzu.

     Beide Anmeldeinformationen sind erforderlich. Geben Sie die Werte der Anmeldeinformationen nur in die sicheren Felder ein. Geben Sie keinen geheimen Verweis in ein unformatiertes Wertfeld ein.

1. Erweitern Sie unter **[!UICONTROL Tools für Benutzer verfügbar]** jede Toolgruppe und wählen Sie die Tools aus, die Ihr Unternehmen benötigt. Standardmäßig sind nur die `ads_accounts-list_ads_accounts`- und `ads_accounts-get_ads_account`-Tools ausgewählt. Um alle Tools auf einmal zu ändern, verwenden Sie **[!UICONTROL Alle auswählen]** oder **[!UICONTROL Alle löschen]**. Sie müssen mindestens ein Tool auswählen.

   Beginnen Sie mit den beiden Account-Tools für eine erste Zugriffsprüfung. Wählen Sie Kampagnen- und Reporting-Tools nur, wenn Ihre Organisation sie benötigt und genehmigt. Weitere Informationen finden Sie unter [Toolgruppen](#tool-groups).

1. Wählen Sie **[!UICONTROL Verbindung speichern]** und überprüfen Sie dann die gespeicherten **[!UICONTROL amazon-ads]**-Connector-Details.

   | Einstellung | Beschreibung |
   | --- | --- |
   | **[!UICONTROL Quelle]** | Die MCP Server URL für die ausgewählte Region. |
   | **[!UICONTROL Authentifizierung]** | Die Authentifizierungsmethode, `amazon-ads_login`. |
   | **[!UICONTROL Tool-Zeitüberschreitung]** | Die Zeit, die ein Kollege auf eine Tool-Antwort wartet. |
   | **[!UICONTROL Verbindung]** | Die verwendete OAuth-Anwendung und Ihr eigener Anmeldestatus. |
   | **[!UICONTROL Tools]** | Die für Mitglieder ausgewählten Werkzeuge mit den Steuerelementen **[!UICONTROL Alle auswählen]** und **[!UICONTROL Löschen]** und einer Anzahl ausgewählter Werkzeuge. |

   ![Amazon-Ads-Connector-Details gespeichert, die die Nordamerika-Quelle, die Authentifizierungsmethode, eine Signierte in Verbindung mit den Schaltflächen Abmelden und Aktualisieren und zwei von 47 ausgewählten Tools anzeigen.](./assets/amazon-ads/org-details.png){width="700" zoomable="yes"}

Beim Speichern werden weder Sie noch ein Mitglied bei [!DNL Amazon] angemeldet. Der **[!UICONTROL Verbindung]**-Status in den Connector-Details bezieht sich auf Ihre eigene Verbindung, nicht auf die Organisation. Um die Verbindung zu überprüfen, wählen Sie **[!UICONTROL Anmelden]** auf der Seite mit den Connector-Details aus, um sich mit Ihrem eigenen [!DNL Amazon]-Konto anzumelden, und wählen Sie dann **[!UICONTROL Testen]** aus. Das Ergebnis zeigt **[!UICONTROL Verbindung erfolgreich]** oder **[!UICONTROL Verbindung fehlgeschlagen]** mit den zurückgegebenen Tools oder Fehlern an. Ein erfolgreiches Ergebnis bestätigt nicht den Zugriff auf einen bestimmten Advertiser-Vorgang.

Um die Tools, die den Mitgliedern später zur Verfügung stehen, zu ändern, aktualisieren Sie die Auswahl unter **[!UICONTROL Verfügbare Tools]** mit **[!UICONTROL Alle auswählen]** oder **[!UICONTROL Löschen]** und wählen Sie dann **[!UICONTROL Werkzeugauswahl speichern]**. Mindestens ein Tool muss ausgewählt bleiben. Mitglieder können die Werkzeugauswahl nicht ändern.

Um den Connector nicht mehr für Ihre Organisation anzubieten, wählen Sie **[!UICONTROL Entfernen]** auf der Seite mit den Connector-Details aus.

### Tool-Gruppen {#tool-groups}

Der [!DNL Amazon Ads]-Connector gliedert seine Tools in die folgenden Gruppen:

| Tool-Gruppe | Tools | Funktionsweise der Tools |
| --- | --- | --- |
| [!UICONTROL Kampagnenverwaltung und Zielgruppenbestimmung] | 7 | Abfragen von Kampagnen, Anzeigengruppen, Anzeigen, Zielgruppen, Portfolios und deren Verknüpfungen und Überprüfen der Produkteignung. |
| [!UICONTROL Konten und Organisation] | 6 | Auflisten und Abrufen von Werbekonten und Abfragen von Advertiser- und Konto-Links, Manager-Konten und Testkonten. |
| [!UICONTROL Benutzerzugriff und Sicherheit] | 5 | Listen Sie Benutzer, Rollen, Berechtigungen und Einladungen auf und erhalten Sie eine Einladung. |
| [!UICONTROL Reporting und Analysen] | 1 | Abrufen eines Berichts. Die Berichterstellung ist nicht enthalten. |
| [!UICONTROL Amazon Marketing Cloud] | 6 | Lesen Sie Workflows und Datenquellen sowie den Status und die Download-URLs vorhandener Ausführungen. Die Ausführung des Workflows ist nicht enthalten. |
| [!UICONTROL Abrechnung und Finanzübersichten] | 4 | Lesen Sie Rechnungen, Rechnungszusammenfassungen, die Nutzung von Abrechnungsprofilen und Abrechnungsbenachrichtigungen. |
| [!UICONTROL Amazon Live] | 12 | Lesen Sie Kanal-, Broadcast-, Livestream-, Medien-, Karussell- und Promo-Code-Informationen. |
| [!UICONTROL Eignung und Angebote] | 6 | Lesen Sie Programm- und Produkteignung, Angebote und Prämien für Werbeaktionen sowie die Bedingungen und Token-Informationen. |

Die Tools in den einzelnen Gruppen können sich ändern, wenn [!DNL Amazon] den Connector aktualisiert. Das geführte Setup speichert die exakte Liste der ausgewählten Werkzeuge, auch wenn Sie jedes Werkzeug auswählen. Tools, die Sie nicht ausgewählt lassen, und Tools, die der Server später hinzufügt, stehen Mitgliedern erst dann zur Verfügung, wenn Sie sie auswählen.

>[!IMPORTANT]
>
>Die Liste der Einrichtungstools wird für das Lesen von Daten kuratiert, der Connector als Ganzes ist jedoch nicht schreibgeschützt. Mitglieder autorisieren den `advertising::campaign_management`, der breiter ist als die Einrichtungsliste. Beim Testen der Verbindung kann die Toolliste auch Tools enthalten, die der Server zurückgibt. Überprüfen Sie jede Tooldefinition und die [!DNL Amazon Ads] Ihrer Mitglieder, bevor Sie weitere Tools auswählen.

## Als Mitglied anmelden {#sign-in-as-a-member}

Nachdem ein Administrator den Connector konfiguriert hat, meldet sich jedes Mitglied mit seinem eigenen [!DNL Amazon] an. Sie benötigen kein App-Geheimnis oder Zugriffstoken, um sich anzumelden.

>[!NOTE]
>
>Wenn der Connector angibt, dass Anmeldung und **[!UICONTROL Test]** in Ihrer Umgebung noch nicht verfügbar sind, stoppen Sie hier. Die Organisationskonfiguration allein macht die Anmeldung als Mitglied nicht verfügbar. Wenden Sie sich an den Adobe-Support.

1. Öffnen Sie **[!UICONTROL Anpassungen]**, wählen Sie **[!UICONTROL Benutzer]** und dann **[!UICONTROL Externe Connectoren]** aus. Suchen Sie die Karte **[!UICONTROL Amazon Ads]**.

1. Wenn die Karte &quot;**[!UICONTROL konfiguriert“]**, bitten Sie Ihren Administrator, den [ zu konfigurieren](#configure-organization). Mitglieder können den Connector nicht konfigurieren.

1. Wenn die Karte **[!UICONTROL Nicht angemeldet“]**, wählen Sie **[!UICONTROL Anmelden]** aus. Lassen Sie das Anmelde-Popup zu und melden Sie sich dann mit dem [!DNL Amazon] Konto an, das Zugriff auf Ihre Werbekonten hat.

1. Füllen Sie die [!DNL Amazon] Authentifizierungsaufforderungen aus, z. B. Multifaktor-Authentifizierung (MFA), und danach die Einverständnisaufforderung. Überprüfen Sie den App-Namen und den angeforderten Zugriff, bevor Sie die Genehmigung erteilen.

   Bei der von Adobe verwalteten App autorisieren Sie die Adobe-App. Mit Ihrer eigenen Organisations-App autorisieren Sie diese App stattdessen.

   >[!IMPORTANT]
   >
   >Fahren Sie nur fort, wenn Sie die App erkennen und Ihr Unternehmen den angeforderten Zugriff genehmigt.

1. Kehren Sie zu Mitarbeiter zurück und bestätigen Sie, dass die Karte **[!UICONTROL Angemeldet]** angezeigt wird. Wählen Sie **[!UICONTROL Details anzeigen]** und überprüfen Sie dann **[!UICONTROL Tools, die von Ihrem Administrator aktiviert wurden]**. Mitglieder können die Tools anzeigen, sie jedoch nicht ändern oder die Organisationsverbindung entfernen.

1. Wählen Sie **[!UICONTROL Test]** aus, um die Tool-Erkennung und den Verbindungsstatus zu überprüfen.

Ein geschlossenes Popup bestätigt nicht, dass die Anmeldung erfolgreich war. Ein erfolgreicher Test bestätigt nicht den Zugriff auf alle Advertiser, Kampagnen, Berichte oder [!DNL Amazon Marketing Cloud]. Wenn sich ein Administrator anmeldet, werden andere Mitglieder nicht angemeldet.

Um Ihr [!DNL Amazon]-Konto vom Connector zu trennen, wählen Sie **[!UICONTROL Abmelden]** aus.

## Überprüfen des Zugriffs auf Ihr Werbekonto {#check-account-access}

Um zu bestätigen, welche Werbekonten Sie verwenden können, führen Sie eine schreibgeschützte Prüfung durch. Verwenden Sie ein genehmigtes Testkonto und stellen Sie sicher, dass Ihr Administrator die `ads_accounts-list_ads_accounts`- und `ads_accounts-get_ads_account`-Tools aktiviert hat. Starten Sie dann einen Chat und geben Sie eine Eingabeaufforderung ein.

Beispielaufforderung:

* „Mit Amazon Ads können Sie bis zu fünf Werbekonten auflisten, auf die ich in der konfigurierten Region zugreifen kann. Nur Kontonamen, Konto-ID und Region anzeigen, wenn diese Felder zurückgegeben werden. Keine Workflows erstellen, aktualisieren, löschen, starten, ausführen, Berichte erstellen oder Berechtigungen ändern. Wenn ein Listenlimit nicht unterstützt wird, fassen Sie nur fünf Ergebnisse zusammen und fordern Sie keine zusätzlichen Seiten an.“

Bestätigen Sie, dass das Ergebnis das erwartete Konto enthält. Um weitere Details anzuzeigen, bitten Sie den Mitarbeiter, die Details dieses Kontos unter Verwendung der Konto-ID aus dem Ergebnis abzurufen. Raten Sie keine Konto-IDs und fordern Sie keine Kampagnen an, nur um die Anmeldung zu testen.

Eine leere Kontoliste bedeutet nicht immer, dass der Connector nicht funktioniert. Überprüfen Sie das [!DNL Amazon] Konto, mit dem Sie sich angemeldet haben, Ihre akzeptierten Einladungen, die verknüpften Advertiser, die ein Manager-Konto abdeckt, und die konfigurierte Region. Ein Testkonto ohne Kampagnen kann auch eine leere Kampagnenliste zurückgeben. Wenn ein benötigtes Tool nicht aktiviert ist, fragen Sie Ihren Administrator. Verwenden Sie kein Werkzeug, das Daten als Ersatz ändert.

## Fehlerbehebung beim Zugriff {#troubleshoot-access}

Wenn Sie nicht auf Ihre [!DNL Amazon Ads] zugreifen können, fragen Sie bei Ihrem Administrator nach:

| Problem | Was zu überprüfen ist |
| --- | --- |
| Die Karte **[!UICONTROL Amazon Ads]** oder **[!UICONTROL Konfigurieren]** fehlt | Vergewissern Sie sich, dass der Connector für Ihre Organisation verfügbar ist und dass Sie über die Berechtigung zum Verwalten von Organisations-Connectoren verfügen. Mitglieder müssen auf die Einrichtung der Organisation warten. |
| Das von Adobe verwaltete Setup wird gespeichert, die Anmeldung schlägt jedoch fehl | Wenden Sie sich an den Adobe-Support, um zu bestätigen, dass die von Adobe verwaltete App in Ihrer Umgebung verfügbar ist. Eine erfolgreiche Speicherung bestätigt dies nicht. |
| Die Umleitungs-URL stimmt nicht überein | Vergleichen Sie die vollständige **[!UICONTROL Umleitungs-URL]** aus dem Dialogfeld „Mitarbeiter“ mit den **[!UICONTROL Zulässige Rückgabe-]** URLs) in [!DNL Login with Amazon], einschließlich Schema, Host und Pfad. Verwenden Sie keine Umleitungs-URL von einem anderen MCP-Client, einer anderen Region oder einer anderen Umgebung oder die URL der Coworker-Seite in Ihrem Browser. |
| Die **[!UICONTROL Umleitungs-URL]** zeigt nur `/connectors/oauth/callback` | Ihre Umgebung zeigt noch nicht die vollständige Umleitungs-URL an oder unterstützt die Anmeldung und den **[!UICONTROL Test]**. Registrieren Sie keinen Teilpfad oder raten Sie den Host-Namen. Wenden Sie sich an den Adobe-Support. |
| Sie können Ihre eigene OAuth-App-Einrichtung nicht speichern | Geben Sie sowohl die OAuth-Client-ID als auch das Client-Geheimnis ein und lassen Sie mindestens ein Tool ausgewählt. Stellen Sie sicher, dass die **[!UICONTROL Amazon App]** ID) die OAuth-Client-ID ist, keine Advertiser-ID oder [!DNL Amazon]. |
| Zustimmung oder App-Autorisierung schlägt fehl | Überprüfen Sie die [!DNL Amazon Ads]-API-Genehmigung, das Sicherheitsprofil, die Client-ID- und Geheimnis-Paarung, die Registrierung der Umleitungs-URL und die Mobile App, die auf dem Einverständnisbildschirm angezeigt wird. Teilen Sie nicht die Einverständnis-URL, den Autorisierungs-Code oder Token, wenn Sie um Hilfe bitten. |
| Sie melden sich an, aber Konten oder Tools werden verweigert oder sind leer | Überprüfen Sie das [!DNL Amazon] Konto, mit dem Sie sich angemeldet haben, Ihre akzeptierte Einladung, die verknüpften Advertiser, die ein Manager-Konto abdeckt, die konfigurierte Region und die für die Aufgabe erforderlichen Berechtigungen. Der Zugriff auf die App oder Partner-Tools bestätigt nicht den Advertiser-Zugriff. [!DNL Amazon Marketing Cloud] Zugriff ist separat. |
| [!DNL Amazon Ads] gibt an, dass das aktuelle Konto nicht auf eine Seite zugreifen kann | Wählen Sie **[!UICONTROL Konto ändern]** und wählen Sie das Advertiser- oder Manager-Konto aus. Wenn das Konto fehlt, bitten Sie seinen Administrator, zu überprüfen, ob Sie die Einladung angenommen haben und dass Sie dem Konto zugewiesen wurden. Wenn das Konto vorhanden, aber die Benutzerverwaltung nicht verfügbar ist, bitten Sie den Administrator, Ihre Rolle zu überprüfen. |
| Ein Tool fehlt oder ist nicht verfügbar | Überprüfen Sie die Tool-Auswahl für Ihre Organisation, die Tools, die der Server zurückgibt, und Ihre [!DNL Amazon Ads]. Tools, die der Server später hinzufügt, werden nicht automatisch ausgewählt. Standardmäßig sind nur die beiden Konto-Tools aktiviert. |
| **[!UICONTROL Test]** meldet einen persönlichen Connector mit demselben Namen | Ein persönlicher Connector mit demselben Namen kann Vorrang vor dem Organisations-Connector haben. Befolgen Sie die angezeigten Anweisungen, um nur den im Konflikt stehenden persönlichen Connector mit Zustimmung seines Besitzers zu entfernen oder umzubenennen. |
| Das Anmelde-Popup ist blockiert, wird nicht beendet oder der Status wird nicht aktualisiert | Lassen Sie das Popup zu, und kehren Sie dann zu Coworker zurück, um den Status und alle Fehlerdetails zu überprüfen. Gehen Sie nicht von Erfolg aus, da das Popup geschlossen oder eine Landingpage angezeigt wurde. |
| Zeitüberschreitung bei einem Tool oder wiederholte Anmeldung erforderlich | Überprüfen Sie die 60-Sekunden **[!UICONTROL Tool-Zeitüberschreitung]**, die Fehlerdetails, die Netzwerk- und [!DNL Amazon] sowie die App-Konfiguration. |
| Der Mitarbeiter sagt, dass die Einrichtung nicht aktiviert ist oder dass noch ein neuer geheimer Schlüssel eingerichtet wird | Überprüfen Sie den Status bei Ihrem Adobe-Support-Mitarbeiter. Erstellen Sie die Anmeldeinformationen nicht wiederholt und behandeln Sie eine fehlgeschlagene Speicherung nicht als erfolgreich. |

Geben Sie bei der Kontaktaufnahme mit dem Support nur den Fehlertext, den Zeitpunkt des Fehlers, Ihre Umgebung, die ausgewählte Region und die Option OAuth-Anwendung an. Geben Sie keine App-Geheimnisse, Zugriffstoken, Autorisierungs-Codes, die Autorisierungs-Kopfzeile, Einverständnis- oder Umleitungs-Abfrageparameter oder Kundenkontodaten frei.
