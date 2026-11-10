---
title: Zugriffssteuerung für Kollegen
description: Erfahren Sie mehr über die Zugriffssteuerung für Adobe CX Enterprise Coworker und Berechtigungen in kompatiblen Adobe-Produkten. Suchen Sie nach Admin-Steuerelementen und erhalten Sie Hilfe zum Zugriff.
last-substantial-update: 2026-11-04
level: beginner
role: Admin
jira: KT-22980
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 756748b585685de6cd0544a46014bc44a4cddc63
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 0%
---
# Zugriffssteuerung für Kollegen {#access-control}

Verwenden Sie die Adobe CX Enterprise Coworker-Zugriffssteuerung, um zu verwalten, wer Coworker verwenden kann und welche Funktionen sie verwenden können.

>[!NOTE]
>
>Die Zugriffssteuerung wird schrittweise für alle Kunden mit Coworker-Zugriff eingeführt. Möglicherweise wird [!UICONTROL Zugriffssteuerung] in Ihrer Organisation noch nicht angezeigt. Weiterführende Informationen finden Sie in der [Übersicht zum Coworker Chat](/help/chat/overview.md).

## Wie der Zugriff bestimmt wird {#how-access-is-determined}

Der Zugriff durch Kollegen wird durch eine organisationsweite Einstellung und optionale Benutzer- oder Gruppenüberschreibungen gesteuert. Die Einstellung Unternehmensweit ermöglicht oder deaktiviert den Zugriff durch Kollegen für Benutzende in Ihrer Organisation. Der Zugriff ist standardmäßig für alle aktiviert.

| Einstellung | Auswirkungen auf den Zugriff |
| --- | --- |
| Organisationsweite Einstellung | Aktivieren Sie den Zugriff durch Kollegen für alle oder deaktivieren Sie ihn für Ihre Organisation. |
| Außerkraftsetzung durch Benutzer oder Benutzergruppe | Überschreibungen geben Admins die Kontrolle über den Zugriff von Kollegen für bestimmte Benutzende oder Benutzergruppen. |
| Kompatible Anwendungsberechtigungen | Die Zugriffssteuerung für Mitarbeiter legt fest, ob Sie auf allgemein verfügbare Funktionen von Kollegen zugreifen können. Coworker erbt Ihre Benutzerberechtigungen von Coworker-kompatiblen CX Enterprise-Anwendungen und berücksichtigt die Berechtigungen, die jede Anwendung bereits erzwingt. |


## Mitarbeiter-Administratoren {#add-coworker-admins}

Ein Mitarbeiter-Administrator ist ein Benutzer, der entweder als **[!UICONTROL Systemadministrator]** für das Unternehmen oder als **[!UICONTROL Produktadministrator]** von [!DNL Adobe Experience Platform] in [!DNL Adobe Admin Console] zugewiesen ist.

## Verwalten des Benutzerzugriffs {#manage-user-access}

1. Öffnen Sie das Coworker-Erlebnis. Anweisungen finden Sie unter [Bei Kollegen anmelden](/help/chat/ui-guide.md#sign-in).
2. Öffnen Sie das Profilmenü und wählen Sie **[!UICONTROL Admin-Einstellungen]**.

   ![Startseite des Kollegen mit hervorgehobenem Profilmenü-Steuerelement.](./assets/access-control/coworker-home.png)

   ![Profilmenü „Mitarbeiter“ mit hervorgehobenen Administratoreinstellungen.](./assets/access-control/admin-settings.png)

3. Wählen Sie **[!UICONTROL Zugriffssteuerung]** aus.

   ![Admin-Einstellungen mit hervorgehobener Karte „Zugriffssteuerung“.](./assets/access-control/access-control.png)

   In diesem Video erfahren Sie, wie Sie Kollegen verwalten.

   >[!VIDEO](https://video.tv.adobe.com/v/3507151?learn=on){transcript=true}

4. Verwenden Sie in **[!UICONTROL Benutzer]**, um den Zugriff für Einzelpersonen zu verwalten, oder **[!UICONTROL Benutzergruppen]** um den Zugriff für Benutzergruppen zu verwalten. Eine Benutzergruppeneinstellung gilt für ihre Mitglieder.

   Die Benutzergruppen der Kollegen sind von den [!DNL Adobe Admin Console] Gruppen getrennt. Das Synchronisieren von Benutzergruppen von [!DNL Adobe Admin Console] mit einem Kollegen ist in Kürze verfügbar.

   Die Benutzerliste enthält Benutzer in Ihrer Organisation. Der Zugriff durch Kollegen ist für diese Benutzer standardmäßig aktiviert.

   * **Aktiviert:** Der Benutzer oder die Benutzergruppe ist aktiv.
   * **Deaktiviert:** Der Benutzer oder die Benutzergruppe ist inaktiv.

   Wenn der Zugriff für alle deaktiviert ist, aktivieren Sie **[!UICONTROL Überschreibungen zulassen]** und wählen Sie **[!UICONTROL Überschreibung hinzufügen]** aus, um Benutzer oder Gruppen hinzuzufügen, die weiterhin Zugriff haben sollten.

## Berechtigungen in Coworker-kompatiblen CX Enterprise-Anwendungen {#permissions-in-compatible-applications}

Mit Kollegen kompatible CX Enterprise-Anwendungen erzwingen weiterhin ihre eigenen Berechtigungen.

Der Mitarbeiter respektiert die Berechtigungen in kompatiblen Anwendungen. Wenn Sie beispielsweise nicht auf einen Datensatz in [!DNL Adobe Experience Platform] zugreifen können, kann ein Mitarbeiter diesen Datensatz nicht für Sie abrufen oder bearbeiten.

## Hilfe zum Zugriff {#get-help-with-access}

Wenn Sie &quot;[!UICONTROL &quot; nicht sehen] wenden Sie sich an Ihren Adobe-Administrator oder den Adobe-Support. Er kann bestätigen, ob die Funktion für Ihr Unternehmen aktiviert ist und ob Sie Zugriff auf die Einstellungen haben.

Wenn Ihnen der Zugriff verweigert wird, bitten Sie Ihren Administrator, die organisationsweite Standardeinstellung sowie alle Benutzer- oder Gruppeneinstellungen zu überprüfen. Bitten Sie die Mitarbeiter bei einem kompatiblen CX Enterprise-Programm, die für dieses Programm separat verwalteten Berechtigungen zu überprüfen.

## Weitere Hilfe zu diesem Thema {#more-help}

Verwenden Sie diese Ressourcen, um weitere Informationen über Mitarbeiter und Administration zu erhalten.

* [Coworker Chat - Übersicht](/help/chat/overview.md)
* [Erste Schritte mit dem Coworker Chat](/help/chat/ui-guide.md)
* [Verwalten von Plug-ins und Marketplaces](/help/customizations/plugins/manage-plugins-for-your-org.md)
