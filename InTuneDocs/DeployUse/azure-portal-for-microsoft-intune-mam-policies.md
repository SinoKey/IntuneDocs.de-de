---
title: "Azure-Portal für MAM-Richtlinien | Microsoft Intune"
description: "Erstellen Sie Verwaltungsrichtlinien für mobile Apps im Azure-Portal. Die Richtlinien, die Sie hier erstellen, können auf Geräte mit oder ohne Registrierung in Intune angewendet werden."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: be1ebcdf2514e45d383dd49890e0e21acf6ede44
ms.openlocfilehash: 1ddb7a30a6f23a3f3d754bd18975c50f32662578


---

# Azure-Portal für MAM-Richtlinien in Microsoft Intune
## Zugreifen auf das Azure-Portal
Über das **Azure-Portal** können Sie Richtlinien zur Verwaltung mobiler Apps erstellen und verwalten.

Das Azure-Portal unterstützt das Erstellen von MAM-Richtlinien für:
- Apps, die auf Geräten ausgeführt werden, die von **Intune registriert und verwaltet werden**.
- Apps, die auf Geräten ausgeführt werden, die **nicht** in einer MDM-Lösung registriert sind.
- Apps, die auf Geräten ausgeführt werden, die **in einer MDM-Lösung von Drittanbietern registriert sind**.

>[!IMPORTANT]

> Wenn Sie derzeit Ihre Geräte mit der [Intune-Verwaltungskonsole](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) verwalten, können Sie mithilfe dieser Konsole eine MAM-Richtlinie erstellen, die Apps für die bei Intune registrierten Geräte unterstützt.

> Möglicherweise werden in der Intune-Verwaltungskonsole nicht alle MAM-Richtlinieneinstellungen angezeigt. Das Azure-Portal stellt die neue Verwaltungskonsole zum Erstellen von MAM-Richtlinien dar. Wenn Sie sowohl in der Intune-Verwaltungskonsole als auch im Azure-Portal MAM-Richtlinien erstellen, wird die im Azure-Portal erstellte Richtlinie auf die Apps angewendet und für die Benutzer bereitgestellt.

## Melden Sie sich beim Azure-Portal an, und passen Sie Ihre Startseite an.

1.  Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Anmeldeinformationen an.

    ![Screenshot zur Anmeldeseite des Azure-Portals](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Sobald Sie erfolgreich angemeldet sind, wird das **Dashboard** angezeigt. Die Seite **Dashboard** kann angepasst werden.

    ![Screenshot zum Dashboard des Azure-Portals](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  Über das Menü **Durchsuchen** finden Sie **Intune**.![Screenshot des Menüs „Durchsuchen“ mit hervorgehobenem Intune](../media/AppManagement/AzurePortal_MAM_Browse_Intune.png)

4.  Wählen Sie **Intune > Mobile Anwendungsverwaltung mit Intune > Einstellungen** aus.

    ![Screenshot des Blatts „Mobile Anwendungsverwaltung mit Intune“](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]
    > Zum Anheften eines Blatts an die **Startseite** können Sie auf dem Blatt die Option zum **Anheften** verwenden.  Klicken Sie auf dem Blatt **Intune-Verwaltung von mobilen Anwendungen**auf das Pinsymbol, um das Blatt an die **Startseite** anzuheften.

    ![Screenshot des Blatts „Mobile Anwendungsverwaltung mit Intune“ mit hervorgehobenem Pinsymbol](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Screenshot des Dashboards mit angehefteter Intune-Kachel](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)
## Nächste Schritte
[Vorbereiten der Konfiguration von Verwaltungsrichtlinien für mobile Apps](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Jul16_HO5-->


