---
title: Bereiten Sie den Verwaltungsrichtlinien für mobile Anwendung konfigurieren | Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
author: karthikaraman
---
# Bereiten Sie sich so konfigurieren Sie Richtlinien zur Verwaltung mobiler Apps mit Microsoft Intune
Sie können konfigurieren, dass mobile app-Verwaltungsrichtlinien für eine app, die unabhängig davon, ob die app auf einem verwalteten Gerät ausgeführt wird. Die MAM-Richtlinien, die über Intune-Konsole konfiguriert werden nur für Geräte unterstützt, die in Intune registriert sind.  

Für Geräte, die nicht in jedem MDM angemeldet, oder registriert in einer dritten Partei als Intune MDM, können Sie das Azure-Portal MAM-Richtlinien zu konfigurieren.  Azure-Portal unterstützt auch Konfigurieren von MAM-Richtlinien für Geräte, die registriert werden.

Diesem Thema erfahren Sie, was Sie tun, bevor Sie Richtlinien zur Verwaltung mobiler Apps (MAM) im Azure-Portal erstellen können.


Bevor Sie beginnen, benötigen Sie Folgendes:

-   Ein Abonnement für [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)].    Endbenutzer müssen [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Lizenzen apps mit MAM-Richtlinie abzurufen.
-   Die Autorität muss entweder Intune festgelegt sein, oder abhängig davon, ob Sie nur Intune oder Configuration Manager-Konfigurations-Manager in Intune zum Verwalten Ihrer Geräte integriert. Wenn Sie die Verwaltung von Office 365 integrierte mobiler Geräte verwenden, müssen Sie einem Intune-Abonnement erwerben und [Festlegen der Verwaltungsautorität für mobile Geräte von Intune](Set-mobile-device-management-authority-and-configure-Microsoft-Intune.md).
-   Ein Abonnement für Office 365 (Office 365) gehört und Azure Active Directory (Azure AD) Benutzer zu erstellen. Azure AD authentifiziert den Benutzer, wenn der Endbenutzer die App startet und seine geschäftlichen Anmeldeinformationen eingibt.

    > [!NOTE]
    > Wenn Sie Benutzer einrichten der [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] -Konsole, achten Sie darauf, dass die MAM-Richtlinienkonfiguration auf Azure-Portal vorwärts verschoben wurde und wenn dieses Portal verwenden möchten, Sie Azure AD-Benutzergruppen, die mit Office 365-Portal einrichten müssen.


## Erstellen von Benutzern und Zuweisen von Microsoft Intune-Lizenzen

1. Intune-Abonnement: bereits ein [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Abonnement, wenn Sie derzeit arbeiten [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] zum Verwalten Ihrer Geräte.  Sie haben auch eine [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Abonnement, wenn Sie eine EMS-Lizenz erworben haben. Wenn Sie versuchen, [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] checken Sie die MAM-Funktionen erhalten Sie ein Testkonto [hier](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/).

    Überprüft, ob Sie haben ein [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] im Office-Portal-Abonnement zur Abrechnung-Seite wechseln.  Daraufhin sollte [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] als **Active** unter den Abonnements.

2.  Melden Sie sich mit Ihren Administratoranmeldeinformationen beim   [Office-Portal](http://portal.office.com) an.

3.  Navigieren Sie zu der **aktive Benutzer** Seite Benutzer hinzufügen und [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Lizenzen.

    ![](../media/AppManagement/OfficePortal_AddUsers.png)

4.  So erteilen Sie einem Benutzer den Zugriff auf Office-Portal, Azure AD-Portal und Azure-Portal, weisen Sie der **globale Administratorrolle** für den Benutzer.

    ![](../media/AppManagement/OfficePortal_AddRoletoUser.png)

5.  MAM-Richtlinien werden für Benutzergruppen in Azure Active Directory bereitgestellt. Um Benutzergruppen erstellen Sie für Ihre Richtlinien MAM verwenden möchten, navigieren Sie zu der **Gruppen** Seite der **Office-Portal** und klicken Sie auf die **+** Symbol, um eine neue Sicherheitsgruppe zu erstellen.  Geben Sie einen Namen und eine Beschreibung ein, und klicken Sie auf **Erstellen**. Nachdem die Gruppe erstellt wurde, können Sie ihr Benutzer hinzufügen, indem Sie in der neu erstellten Sicherheitsgruppe auf **Mitglieder bearbeiten** klicken. Die Sicherheitsgruppe wird in Azure Active Directory erstellt.

    ![](../media/AppManagement/OfficePortal_CreateGroups.png)

Die folgende Tabelle enthält die Rolle und Berechtigungen, die Admin-Benutzern zugewiesen werden können.

|||
|-|-|
|**Rolle**|**Berechtigungen**|
|Globaler Administrator (Office 365-Portal)|Zugriff auf das Office 365-Portal<br /><br />Zugriff auf das Azure AD-Portal<br /><br />Zugriff auf das Azure-Portal (damit können sowohl Rollenverwaltungs- als auch Verwaltungsaufgaben für mobile Apps ausgeführt werden).|
|Besitzer (Azure-Portal)|Zugriff auf das Azure-Portal (damit können sowohl Rollenverwaltungs- als auch Verwaltungsaufgaben für mobile Apps ausgeführt werden).|
|Mitwirkender (Azure-Portal)|Zugriff auf das Azure-Portal (damit können nur Verwaltungsaufgaben für mobile Apps ausgeführt werden).|

## Zuweisen der Rolle „Mitwirkender“ zu einem Benutzer

**Globale Administratoren** haben Zugriff auf das Azure-Portal.  Wenn Sie möchten, dass andere Administratoren in der Lage sind, Richtlinien zu konfigurieren und andere Verwaltungsaufgaben für mobile Apps auszuführen, können Sie den jeweiligen Benutzern wie nachstehen beschrieben die Rolle **Mitwirkender** zuweisen:


1.  Klicken Sie auf dem Blatt **Einstellungen** im Abschnitt **Ressourcenverwaltung**auf **Benutzer**.

    ![](../media/AppManagement/AzurePortal_MAM_AddUsers.png)

2.  Klicken Sie auf **Hinzufügen** , um das Blatt **Zugriff hinzufügen** zu öffnen.

3.  Klicken Sie auf **Rolle auswählen**, und klicken Sie dann auf die Rolle **Mitwirkender**.

    ![](../media/AppManagement/AzurePortal_MAM_AddRole.png)

4.  Klicken Sie nach dem Auswählen der Rolle auf **Benutzer hinzufügen**, und suchen Sie anhand des Namens oder der E-Mail-Adresse nach dem Benutzer. Bei den in dieser Liste angezeigten Benutzern handelt es sich um die ersten 1.000 Benutzer, die Sie zuvor über das Office-Portal in Azure AD erstellt haben. Klicken Sie auf dem Blatt **Zugriff hinzufügen** auf **OK** , um den Vorgang zu speichern und dem Benutzer die Rolle zuzuweisen.

    ![](../media/AppManagement/AzurePortal_MAM_AddusertoRole.png)

    > [!IMPORTANT]
    > Wenn Sie einen Benutzer auswählen, die keine [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Lizenz zugewiesen werden, sie sind nicht in der Lage, auf das Portal zugreifen.

## Nächste Schritte
[Erstellen und Bereitstellen von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](Create-and-deploy-mobile-app-management-policies-with-Microsoft-Intune.md)


<!--HONumber=Mar16_HO4-->


