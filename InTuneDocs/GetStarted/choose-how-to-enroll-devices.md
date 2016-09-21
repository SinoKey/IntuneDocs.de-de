---
title: "Auswählen der Methode zum Registrieren mobiler Geräte | Microsoft Intune"
description: "Entscheiden Sie über die Registrierung mobiler Geräte in Intune durch Beantworten einiger einfacher Fragen"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: 899f50cfec9e7c20d2981c077f93e0fccf37dc2b
ms.openlocfilehash: 0e516e3762dc5712a1b2d0f83016b51b15b7070f


---

# Auswählen der Methode zum Registrieren mobiler Geräte

Die Antworten auf die folgenden Fragen helfen Ihnen, die beste Registrierungsmethode für die von Ihnen verwalteten Geräte zu ermitteln.

## **Bringen die Mitarbeiter ihre eigenen Geräte mit, oder werden die Geräte von Ihrer Organisation bereitgestellt?**

  - **Benutzereigene Geräte** – BYOD-Registrierung („Bring Your Own Device“)
  - **Unternehmenseigene Geräte** – COD-Registrierung (Company-Owned Devices)

> [!div class="button"]
[BYOD-Registrierung >](#what-byod-devices-can-your-users-enroll)   
> [!div class="button"]
[COD-Registrierung >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## **Welche BYOD-Geräte können von Benutzern registriert werden?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS und Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile und Windows Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Windows-PCs](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## **Werden Ihre unternehmenseigenen Geräte gemeinsam genutzt oder von dedizierten Benutzern verwendet?**

> [!div class="button"]
[Gemeinsam genutzt >](#what-operating-system-are-your-shared-devices-running)   [Dediziert >](#how-will-you-manage-dedicated-ios-devices)


## **Welche Betriebssysteme werden auf den gemeinsam genutzten Geräten ausgeführt?**

  > [!div class="button"]
  [Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## **Wie werden Sie gemeinsam genutzte iOS-Geräte verwalten?**

  > [!div class="button"]
  [DEP-Registrierung von iOS-Geräten >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Direkte Registrierung von iOS-Geräten >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)  [DEM-Registrierung >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Apple-Geräteregistrierungsprogramm (DEP)** – Mit DEP erworbene oder verwaltete iOS-Geräte können mit einem Anmeldungsprofil angesprochen werden. Wenn die Benutzer ihre Geräte zum ersten Mal einschalten, lädt das Gerät das DEP-Profil herunter und registriert sich beim Profil-DEP.

  - **Apple Configurator auf einem Mac** – Apple Configurator ist eine Apple-Anwendung, die auf einem Mac-Computer ausgeführt wird. Sie können die iOS-Geräte über ein USB-Kabel mit dem Mac-Computer verbinden, um ein Registrierungsprofil auf dem Gerät zu installieren. Wenn Sie die Geräte zur Registrierung auf die Werkseinstellungen zurücksetzen können, verwenden Sie die Registrierung mithilfe des Setup-Assistenten. Falls Sie die Geräte nicht auf die Werkseinstellungen zurücksetzen möchten, verwenden Sie die direkte Registrierung.

  - **Geräteregistrierungs-Manager** – Mit dem Geräteregistrierungs-Manager (Device Enrollment Manager, DEM) von Intune können Manager oder Administratoren eine Vielzahl mobiler Geräte bei einem einzelnen Benutzerkonto registrieren. Diese Geräte dürfen keine Benutzeraffinität (d. h. dedizierte Benutzer) aufweisen und müssen registriert werden, indem sie installiert und bei der Unternehmensportal-App angemeldet werden.

## **Wie werden Sie dedizierte iOS-Geräte verwalten?**

  > [!div class="button"]
  [Markieren mit IMEI >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) [iOS-DEP](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [iOS-Setup-Assistent](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Markieren mit IMEI](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Sie können unternehmenseigene Geräte mit dedizierten Benutzern wie folgt registrieren:

  - **Apple-Geräteregistrierungsprogramm (DEP)** – Mit DEP erworbene oder verwaltete iOS-Geräte können mit einem Anmeldungsprofil angesprochen werden. Wenn die Benutzer ihre Geräte zum ersten Mal einschalten, lädt das Gerät das DEP-Profil herunter und registriert sich bei Intune.

  - **Apple Configurator auf einem Mac** – Apple Configurator ist eine Apple-Anwendung, die auf einem Mac-Computer ausgeführt wird. Sie können die iOS-Geräte über ein USB-Kabel mit dem Mac-Computer verbinden, um ein Registrierungsprofil auf dem Gerät zu installieren. Wenn Sie die Geräte zur Registrierung auf die Werkseinstellungen zurücksetzen können, verwenden Sie die Registrierung mithilfe des Setup-Assistenten.

  - **Mit IMEI-Nummer markieren** – Durch das Importieren der IMEI-Nummern (International Mobile Equipment Identity) unternehmenseigener Geräte können Sie diese in Intune als unternehmenseigene Geräte markieren. Anschließend können die Benutzer ihre Geräte als persönliche Geräte registrieren, indem sie das Unternehmensportal installieren, um den Zugriff auf Unternehmensressourcen wie E-Mail, Apps und Daten zu erhalten.



<!--HONumber=Sep16_HO2-->


