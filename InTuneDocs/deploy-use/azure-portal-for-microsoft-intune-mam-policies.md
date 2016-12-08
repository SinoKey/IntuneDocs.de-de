---
title: "Azure-Portal für MAM-Richtlinien | Microsoft Intune"
description: "Erstellen Sie Verwaltungsrichtlinien für mobile Apps mithilfe des Azure-Portals. Die Richtlinien, die Sie hier erstellen, können auf Geräte mit oder ohne Registrierung in Intune angewendet werden."
keywords: 
author: karthikaraman
ms.author: karaman
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
ms.sourcegitcommit: 03410d1e82cfeb8d354ee1d010ada07ca86191bc
ms.openlocfilehash: e9d917401a8927099bdf8558e9f7e7185351f709


---

# <a name="azure-portal-for-microsoft-intune-mam-policies"></a>Azure-Portal für MAM-Richtlinien in Microsoft Intune

## <a name="use-the-azure-portal"></a>Verwenden des Azure-Portals
Über das Azure-Portal können Sie Richtlinien zur Verwaltung mobiler Apps (mobile application management, MAM) erstellen und verwalten.

Das Azure-Portal unterstützt das Erstellen von MAM-Richtlinien für:
- Apps, die auf Geräten ausgeführt werden, die **in Intune registriert und verwaltet** werden.

- Apps, die auf Geräten ausgeführt werden, die **nicht** in einer MDM-Lösung registriert sind.
- Apps, die auf Geräten ausgeführt werden, die **in einer MDM-Lösung von Drittanbietern registriert sind**.

>[!IMPORTANT]


> Wenn Sie die Intune-Verwaltungskonsole zum Verwalten Ihrer Geräte verwenden, können Sie mithilfe der [Intune-Verwaltungskonsole](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) eine MAM-Richtlinie erstellen, die Apps für die bei Intune registrierten Geräte unterstützt.

> Möglicherweise werden in der Intune-Verwaltungskonsole nicht alle MAM-Richtlinieneinstellungen angezeigt. Das Azure-Portal stellt die neue Verwaltungskonsole zum Erstellen von MAM-Richtlinien dar. Wenn Sie sowohl in der Intune-Verwaltungskonsole als auch im Azure-Portal MAM-Richtlinien erstellen, wird die im Azure-Portal erstellte Richtlinie auf die Apps angewendet und für die Benutzer bereitgestellt.


## <a name="sign-in-to-the-azure-portal-and-customize-your-start-page"></a>Melden Sie sich beim Azure-Portal an, und passen Sie Ihre Startseite an.

1.  Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Anmeldeinformationen an.

    ![Screenshot zur Anmeldeseite des Azure-Portals](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Sobald Sie erfolgreich angemeldet sind, wird das **Dashboard** angezeigt. Die Seite **Dashboard** kann angepasst werden.

    ![Screenshot zum Dashboard des Azure-Portals](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  Über das Menü **Durchsuchen** finden Sie **Intune**. ![Screenshot des Menüs „Durchsuchen“ mit hervorgehobenem Intune](../media/AppManagement/AzurePortal_MAM_Browse_Intune.png)

4.  Wählen Sie **Intune** > **Mobile Anwendungsverwaltung mit Intune** > **Einstellungen** aus.

    ![Screenshot des Blatts „Mobile Anwendungsverwaltung mit Intune“](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]

    > Zum Anheften eines Blatts an die **Startseite** können Sie auf dem Blatt die Option zum **Anheften** verwenden. Klicken Sie auf dem Blatt **Mobile Anwendungsverwaltung mit Intune** auf das Stecknadelsymbol, um das Blatt an die **Startseite** anzuheften.

    ![Screenshot des Blatts „Mobile Anwendungsverwaltung mit Intune“ mit hervorgehobenem Pinsymbol](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Screenshot des Dashboards mit angehefteter Intune-Kachel](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)
## <a name="next-steps"></a>Nächste Schritte
[Vorbereiten der Konfiguration von Verwaltungsrichtlinien für mobile Apps](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Nov16_HO2-->

