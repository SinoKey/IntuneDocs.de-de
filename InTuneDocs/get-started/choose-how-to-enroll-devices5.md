---
title: "Auswählen der Methode zum Registrieren mobiler Geräte | Microsoft-Dokumentation"
description: "Entscheiden Sie über die Registrierung mobiler Geräte in Intune durch Beantworten einiger einfacher Fragen"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/14/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed9250aa-e894-4eac-92b8-5f1a3748e255
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: f268cf29461447306d0f5c3ca06d541d9a03a49d
ms.openlocfilehash: f28c96328c915fdcd0a0cd263de9c4bb9181808f


---
# <a name="choose-how-to-enroll-mobile-devices"></a>Auswählen der Methode zum Registrieren mobiler Geräte

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Die Antworten auf die folgenden Fragen helfen Ihnen, die beste Registrierungsmethode für die von Ihnen verwalteten Geräte zu ermitteln.


## <a name="how-will-you-manage-shared-ios-devices"></a>**Wie werden Sie freigegebene iOS-Geräte verwalten?**

> [!div class="button"]
[DEP-Registrierung von iOS-Geräten >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
> [!div class="button"]
[Direkte Registrierung von iOS-Geräten >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)
> [!div class="button"]
[DEM-Registrierung >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Apple-Geräteregistrierungsprogramm (DEP)** – Mit DEP erworbene oder verwaltete iOS-Geräte können mit einem Anmeldungsprofil angesprochen werden. Wenn die Benutzer ihre Geräte zum ersten Mal einschalten, lädt das Gerät das DEP-Profil herunter und registriert sich beim Profil-DEP.

  - **Apple Configurator auf einem Mac** – Apple Configurator ist eine Apple-Anwendung, die auf einem Mac-Computer ausgeführt wird. Sie können die iOS-Geräte über ein USB-Kabel mit dem Mac-Computer verbinden, um ein Registrierungsprofil auf dem Gerät zu installieren. Wenn Sie die Geräte zur Registrierung auf die Werkseinstellungen zurücksetzen können, verwenden Sie die Registrierung mithilfe des Setup-Assistenten. Falls Sie die Geräte nicht auf die Werkseinstellungen zurücksetzen möchten, verwenden Sie die direkte Registrierung.

  - **Geräteregistrierungs-Manager** – Mit dem Geräteregistrierungs-Manager (Device Enrollment Manager, DEM) von Intune können Manager oder Administratoren eine Vielzahl mobiler Geräte bei einem einzelnen Benutzerkonto registrieren. Diese Geräte dürfen keine Benutzeraffinität (d. h. dedizierte Benutzer) aufweisen und müssen registriert werden, indem sie installiert und bei der Unternehmensportal-App angemeldet werden.

  > [!div class="button"]
  [< Zurück](choose-how-to-enroll-devices3.md)



<!--HONumber=Dec16_HO3-->


