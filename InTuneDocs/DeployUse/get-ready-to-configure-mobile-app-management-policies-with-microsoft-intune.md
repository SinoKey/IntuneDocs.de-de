---
# required metadata

title: Vorbereiten der Konfiguration von Verwaltungsrichtlinien für mobile Apps | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Vorbereiten der Konfiguration von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune
In diesem Thema erfahren Sie, welche Schritte Sie ausführen müssen, bevor Sie im Azure-Portal Richtlinien für die Verwaltung von mobilen Apps (MAM, Mobile App Management) erstellen können.

Das Azure-Portal ist die neue Verwaltungskonsole zum Erstellen von MAM-Richtlinien, und wir empfehlen, dass Sie Ihre MAM-Richtlinien in diesem Portal erstellen. Das Azure-Portal unterstützt die folgenden MAM-Szenarien:
- Bei Intune registrierte Geräte
- Geräte, die mithilfe einer MDM-Lösung eines Drittanbieters verwaltet werden
- Geräte, die gar keiner Verwaltung durch eine MDM-Lösung unterliegen (BYOD).

Wenn Sie Ihnen der Umgang mit dem Azure-Portal neu ist, sollten Sie sich im Artikel [Azure-Portal für MAM-Richtlinien in Microsoft Intune](azure-portal-for-microsoft-intune-mam-policies.md) einen kurzen Überblick verschaffen.

Wenn Sie derzeit Ihre Geräte mit der **Intune-Verwaltungskonsole** verwalten, können Sie mithilfe der **Intune-Verwaltungskonsole** MAM-Richtlinien erstellen, die Apps für die bei Intune registrierten Geräte unterstützen. Es wird jedoch empfohlen, dass Sie auch für bei Intune registrierte Geräte das Azure-Portal verwenden. Anweisungen zum Erstellen einer MAM-Richtlinie mithilfe der Intune-Verwaltungskonsole finden Sie [hier](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).

>[!IMPORTANT]
> Möglicherweise werden in der Intune-Verwaltungskonsole nicht alle MAM-Richtlinieneinstellungen angezeigt. Wenn Sie sowohl in der Intune-Verwaltungskonsole als auch im Azure-Portal MAM-Richtlinien erstellen, wird die im Azure-Portal erstellte Richtlinie auf die Apps angewendet und für die Benutzer bereitgestellt.


##  Unterstützte Plattformen
- iOS 8.1 oder höher

- Android 4 oder höher

Windows-Geräte werden momentan nicht unterstützt.
##  Unterstützte Apps
* **Microsoft-Apps**: Bei diesen Apps ist das Intune App SDK integriert, und vor der Anwendung von MAM-Richtlinien sind keine weiteren Schritte nötig.
Die vollständige Liste der unterstützten Microsoft-Apps finden Sie auf der Seite mit den Microsoft Intune-Anwendungspartnern im [Microsoft Intune-Katalog für mobile Anwendungen](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx). Klicken Sie auf eine App, um die unterstützten Szenarien und Plattformen anzuzeigen und zu erfahren, ob die App mehrere Identitäten unterstützt.
* Intern erstellte **branchenspezifische Apps**: Diese Apps müssen vorbereitet werden. Bevor Sie MAM-Richtlinien auf sie anwenden können, müssen Sie das Intune App SDK in sie integrieren.

  * Für Geräte, die mit Intune verwaltet werden, lesen Sie die Informationen unter [Auswählen der Vorbereitung von Apps für MAM](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).
  * Für nicht mit Intune verwaltete Geräte, z. B. für Geräte im Besitz der Mitarbeiter oder für Geräte, die mit einer Drittanbieterlösung zur Verwaltung mobiler Geräte verwaltet werden, lesen Sie die Informationen unter [Schützen von branchenspezifischen Apps und Daten auf nicht in Intune registrierten Geräten](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

**Bevor** Sie MAM-Richtlinien konfigurieren können, benötigen Sie Folgendes:

-   **Ein Abonnement von Microsoft Intune**.    Endbenutzer benötigen [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Lizenzen, um Apps mit MAM-Richtlinien erhalten zu können.

-   Ein **Office 365 (O365)**-Abonnement, das für die folgenden Punkte erforderlich ist:
  - Anwenden von MAM-Richtlinien auf Apps, die mehrere Identitäten unterstützen.
  - Erstellen von SharePoint Online- und Exchange Online-Arbeitskonten. Lokale Exchange- und SharePoint-Bereitstellungen werden nicht unterstützt.
-    **Aktivieren Sie die moderne Authentifizierung** für **Skype for Business Online**. Melden Sie sich bei Microsoft Connect an, und füllen Sie [dieses Formular](https://connect.microsoft.com/office/Survey/NominationSurvey.aspx?SurveyID=17299&ProgramID=8715) aus, um sich beim Programm für die moderne Authentifizierung zu registrieren.


- **Azure Active Directory (Azure AD)** zum Erstellen von Benutzern. Azure AD authentifiziert den Benutzer, wenn der Endbenutzer die App startet und seine geschäftlichen Anmeldeinformationen eingibt.

    > [!NOTE] Wenn Sie Benutzer mithilfe der [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Konsole einrichten, bedenken Sie, dass die MAM-Richtlinienkonfiguration in Zukunft in das Azure-Portal verlagert wird, und um dieses Portal verwenden zu können, müssen Sie Azure AD-Benutzergruppen mithilfe des Office 365-Portals einrichten.


## Erstellen von Benutzern und Zuweisen von Microsoft Intune-Lizenzen

1. Sie benötigen ein Intune-Abonnement: Sie verfügen bereits über ein [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Abonnement, wenn Sie aktuell [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] zum Verwalten Ihrer Geräte verwenden.  Sie sind ebenfalls im Besitz eines [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Abonnements, wenn Sie eine EMS-Lizenz erworben haben. Wenn Sie [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] testen, um die MAM-Fähigkeiten kennenzulernen, können Sie [hier](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/) ein Testkonto erhalten.

    Um zu überprüfen, ob Sie über ein [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Abonnement verfügen, navigieren Sie im Office-Portal auf die Seite „Abrechnung“.  Unter den Abonnements sollte [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] als **Aktiv** angezeigt werden.

2.  Melden Sie sich mit Ihren Administratoranmeldeinformationen beim   [Office-Portal](http://portal.office.com) an.

3.  Navigieren Sie zur Seite **Aktive Benutzer** , um Benutzer hinzuzufügen und [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] -Lizenzen zuzuweisen.

    ![Seite „Benutzer hinzufügen“ im Office-Portal](../media/AppManagement/OfficePortal_AddUsers.png)

4.  Um einem Benutzer Zugriff auf das Office-Portal, das Azure AD-Portal und das Azure-Portal zu gewähren, weisen Sie dem Benutzer die Rolle **Globaler Administrator** zu.

    ![Screenshot des Office-Portals mit der Seite „Aktive Benutzer“ ](../media/AppManagement/OfficePortal_AddRoletoUser.png)

5.  MAM-Richtlinien werden für Benutzergruppen in Azure Active Directory bereitgestellt. Um die Benutzergruppen zu erstellen, die Sie für Ihre MAM-Richtlinien verwenden möchten, navigieren Sie im **Office-Portal** zur Seite **Gruppen**, und klicken Sie auf das **+**-Symbol, um eine neue Sicherheitsgruppe zu erstellen.  Geben Sie einen Namen und eine Beschreibung ein, und klicken Sie auf **Erstellen**. Nachdem die Gruppe erstellt wurde, können Sie ihr Benutzer hinzufügen, indem Sie in der neu erstellten Sicherheitsgruppe auf **Mitglieder bearbeiten** klicken. Die Sicherheitsgruppe wird in Azure Active Directory erstellt.

    ![Screenshot der Seite mit der Auswahl der globalen Administratorrolle auf der Seite „Benutzerrollen bearbeiten“](../media/AppManagement/OfficePortal_CreateGroups.png)

In der folgenden Tabelle werden die Rollen und Berechtigungen aufgelistet, die Sie Administratoren zuweisen können.

|||
|--|----|
|**Rolle**|**Berechtigungen**|
|Globaler Administrator (Office 365-Portal)|Zugriff auf das Office 365-Portal und das Azure AD-Portal<br /><br />Zugriff auf das Azure-Portal (damit können sowohl Rollenverwaltungs- als auch Verwaltungsaufgaben für mobile Apps ausgeführt werden).|
|Besitzer (Azure-Portal)|Zugriff auf das Azure-Portal (damit können sowohl Rollenverwaltungs- als auch Verwaltungsaufgaben für mobile Apps ausgeführt werden).|
|Mitwirkender (Azure-Portal)|Zugriff auf das Azure-Portal (damit können nur Verwaltungsaufgaben für mobile Apps ausgeführt werden).|

## Zuweisen der Rolle „Mitwirkender“ an einen Benutzer

**Globale Administratoren** haben Zugriff auf das [Azure-Portal](https://portal.azure.com).  Wenn Sie möchten, dass andere Administratoren in der Lage sind, Richtlinien zu konfigurieren und andere Verwaltungsaufgaben für mobile Apps auszuführen, können Sie den jeweiligen Benutzern wie nachstehen beschrieben die Rolle **Mitwirkender** zuweisen:


1.  Klicken Sie auf dem Blatt **Einstellungen** im Abschnitt **Ressourcenverwaltung**auf **Benutzer**.

    ![Screenshot des Blatts „Benutzer“ im Azure-Portal](../media/AppManagement/AzurePortal_MAM_AddUsers.png)

2.  Klicken Sie auf **Hinzufügen** , um das Blatt **Zugriff hinzufügen** zu öffnen.

3.  Klicken Sie auf **Rolle auswählen**, und klicken Sie dann auf die Rolle **Mitwirkender**.

    ![Screenshot des Blatts „Rolle auswählen“ im Azure-Portal](../media/AppManagement/AzurePortal_MAM_AddRole.png)

4.  Klicken Sie nach dem Auswählen der Rolle auf **Benutzer hinzufügen**, und suchen Sie anhand des Namens oder der E-Mail-Adresse nach dem Benutzer. Bei den in dieser Liste angezeigten Benutzern handelt es sich um die ersten 1.000 Benutzer, die Sie zuvor über das Office-Portal in Azure AD erstellt haben. Klicken Sie auf dem Blatt **Zugriff hinzufügen** auf **OK** , um den Vorgang zu speichern und dem Benutzer die Rolle zuzuweisen.

    ![Screenshot des Blatts „Benutzer hinzufügen“ im Azure-Portal](../media/AppManagement/AzurePortal_MAM_AddusertoRole.png)

    > [!IMPORTANT] Wenn Sie einen Benutzer auswählen, dem keine [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Lizenz zugewiesen ist, kann dieser Benutzer nicht auf das Portal zugreifen.

## Nächste Schritte
[Erstellen und Bereitstellen von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)


<!--HONumber=Jun16_HO2-->


