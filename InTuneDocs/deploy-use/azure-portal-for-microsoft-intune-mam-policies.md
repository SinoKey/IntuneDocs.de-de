---
title: "Azure-Portal für MAM-Richtlinien | Microsoft-Dokumentation"
description: "Erstellen Sie Verwaltungsrichtlinien für mobile Apps mithilfe des Azure-Portals. Die Richtlinien, die Sie hier erstellen, können auf Geräte mit oder ohne Registrierung in Intune angewendet werden."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fe44466fbcef67d02b16d3d2d335f657251451d3
ms.openlocfilehash: fa8d839da1cf0b2d207edc0b28de8a714ba0df02


---

# <a name="azure-portal-for-microsoft-intune-mam-policies"></a>Azure-Portal für MAM-Richtlinien in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Das Azure-Portal wird verwendet, um Richtlinien zur Verwaltung mobiler Apps (mobile application management, MAM) für die folgenden zu erstellen und zu verwalten:

- Apps, die auf Geräten ausgeführt werden, die **in Intune registriert und verwaltet** werden.

- Apps, die auf Geräten ausgeführt werden, die **nicht** in einer MDM-Lösung registriert sind.
- Apps, die auf Geräten ausgeführt werden, die **in einer MDM-Lösung von Drittanbietern registriert sind**.

>[!IMPORTANT]
> Das Azure-Portal ist die neue Administratorkonsole für die Erstellung von MAM-Richtlinien. Sie können jedoch auch eine MAM-Richtlinie erstellen, die Apps für Geräte unterstützt, die bei Intune registriert sind, indem Sie die [Intune-Verwaltungskonsole](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) für MDM-Szenarios verwenden.

> Möglicherweise sind in der Intune-Verwaltungskonsole nicht alle MAM-Richtlinieneinstellungen verfügbar. Darüber hinaus werden die Richtlinien, die im Azure-Portal erstellt wurden, die in der Intune-Verwaltungskonsole überschreiben, wenn Sie MAM-Richtlinien sowohl in der Intune-Verwaltungskonsole als auch im Azure-Portal erstellen. In diesem Szenario werden die MAM-Richtlinien des Azure-Portals auf die Apps angewendet und für Benutzer bereitgestellt.


## <a name="sign-in-to-the-azure-portal-and-customize-your-start-page"></a>Melden Sie sich beim Azure-Portal an, und passen Sie Ihre Startseite an.

1.  Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Anmeldeinformationen an.

    ![Screenshot zur Anmeldeseite des Azure-Portals](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Sobald Sie erfolgreich angemeldet sind, wird das **Dashboard** angezeigt. Die Seite **Dashboard** kann angepasst werden.

    ![Screenshot zum Dashboard des Azure-Portals](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  Suchen Sie im Menü **Durchsuchen** die Option **Intune**.

    ![Screenshot des Menüs „Durchsuchen“ mit hervorgehobenem Intune](../media/AppManagement/MAM-Azure-Portal-1.png)

4.  Wählen Sie **Intune** > **Mobile Anwendungsverwaltung mit Intune** > **Einstellungen** aus.

    ![Screenshot des Blatts „Mobile Anwendungsverwaltung mit Intune“](../media/AppManagement/MAM-Azure-Portal-2.png)

5. (Optional:)Zum Anheften eines Blatts an die **Startseite** können Sie auf dem Blatt die Option zum **Anheften** verwenden. Klicken Sie auf dem Blatt **Mobile Anwendungsverwaltung mit Intune** auf das Stecknadelsymbol, um das Blatt an die **Startseite** anzuheften.

    ![Screenshot des Blatts „Mobile Anwendungsverwaltung mit Intune“ mit hervorgehobenem Pinsymbol](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Screenshot des Dashboards mit angehefteter Intune-Kachel](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)

## <a name="next-steps"></a>Nächste Schritte
[Vorbereiten der Konfiguration von Verwaltungsrichtlinien für mobile Apps](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Jan17_HO2-->


