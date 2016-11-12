---
title: "Auswählen der Methode zum Registrieren mobiler Geräte | Microsoft Intune"
description: "Entscheiden Sie über die Registrierung mobiler Geräte in Intune durch Beantworten einiger einfacher Fragen"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 178df739-d3b9-43cb-8440-c5c110b1276b
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: f4e6c17624f509b83ca594750c0db8931bc54b35


---

# Auswählen der Methode zum Registrieren mobiler Geräte

Die Registrierung mobiler Geräte ist der Prozess, den Sie durchführen, damit Smartphones, Tablets und PCs von Microsoft Intune verwaltet werden können. Als Administrator müssen Sie anhand der folgenden Punkte bestimmen, wie Geräte am besten registriert werden:

 -  Eigentümerschaft (privat oder in Unternehmensbesitz)
 -  Nutzung (freigegeben oder persönlich)
 -  Plattform (iOS, Android, Windows Phone, Windows-PC, Mac-Computer)

Die Antworten auf die folgenden Fragen helfen Ihnen, die beste Registrierungsmethode für die von Ihnen verwalteten Geräte zu ermitteln.

## **Bringen die Mitarbeiter ihre eigenen Geräte mit, oder werden die Geräte von Ihrer Organisation bereitgestellt?**

  - **Geräte von Benutzern** – „BYOD“-Registrierung (Bring Your Own Device) – Benutzer können die Intune-Unternehmensportal-App auf ihrem Gerät installieren und dieses dann registrieren, um Zugriff auf Unternehmensressourcen wie E-Mail, Unternehmens-Apps, Unternehmensdaten und Support zu erhalten.  

  - **Dem Unternehmen gehörende Geräte** – Für die Registrierung von dem Unternehmen gehörenden Geräten (Company-Owned Device, COD) gibt es eine Vielzahl von Möglichkeiten, je nach den Anforderungen der Organisation und den Typen der zu verwaltenden Geräte.

> [!div class="button"]
[BYOD-Registrierung >](#what-byod-devices-can-your-users-enroll)   [COD-Registrierung >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## **Welche BYOD-Geräte können von Benutzern registriert werden?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS und Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile und Windows Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Windows-PCs](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## **Werden Ihre unternehmenseigenen Geräte gemeinsam genutzt oder von dedizierten Benutzern verwendet?**

- **Gemeinsam genutzte unternehmenseigene Geräte** – Diese Geräte werden nicht nur von einem einzelnen Benutzer verwendet und sind in der Regel nicht für den E-Mail-Zugriff konfiguriert. Dazu zählen beispielsweise Kiosk-Geräte oder aufgabenspezifische Geräte, die die Benutzer bei Bedarf einem Pool entnehmen und dann zurückgeben. Die empfohlenen Registrierungsmethoden hängen von der Geräteplattform ab.

- **Dedizierte Benutzer** – Unternehmenseigene Geräte, die an einzelne Benutzer ausgegeben werden, müssen als Unternehmensressourcen nachverfolgt werden. Gleichzeitig muss der Benutzerzugriff auf E-Mails und Daten in der Form gewährleistet werden, als würde es sich um persönliche Geräte handeln. Die empfohlenen Registrierungsmethoden hängen von der Geräteplattform ab.

> [!div class="button"]
[Gemeinsam genutzt >](#what-operating-system-are-your-shared-devices-running)   [Dediziert >](#how-will-you-manage-dedicated-ios-devices)


## **Welche Betriebssysteme werden auf den gemeinsam genutzten Geräten ausgeführt?**

  > [!div class="button"]
  [Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## **Wie werden Sie gemeinsam genutzte iOS-Geräte verwalten?**

- **Apple-Geräteregistrierungsprogramm (DEP)** – Mit DEP erworbene oder verwaltete iOS-Geräte können mit einem Anmeldungsprofil angesprochen werden. Wenn die Benutzer ihre Geräte zum ersten Mal einschalten, lädt das Gerät das DEP-Profil herunter und registriert sich beim Profil-DEP.

- **Apple Configurator auf einem Mac** – Apple Configurator ist eine Apple-Anwendung, die auf einem Mac-Computer ausgeführt wird. Sie können die iOS-Geräte über ein USB-Kabel mit dem Mac-Computer verbinden, um ein Registrierungsprofil auf dem Gerät zu installieren. Wenn Sie die Geräte zur Registrierung auf die Werkseinstellungen zurücksetzen können, verwenden Sie die Registrierung mithilfe des Setup-Assistenten. Falls Sie die Geräte nicht auf die Werkseinstellungen zurücksetzen möchten, verwenden Sie die direkte Registrierung.

- **Geräteregistrierungs-Manager** – Mit dem Geräteregistrierungs-Manager (Device Enrollment Manager, DEM) von Intune können Manager oder Administratoren eine Vielzahl mobiler Geräte bei einem einzelnen Benutzerkonto registrieren. Diese Geräte dürfen keine Benutzeraffinität (d. h. dedizierte Benutzer) aufweisen und müssen registriert werden, indem sie installiert und bei der Unternehmensportal-App angemeldet werden.

  > [!div class="button"]
  [DEP-Registrierung von iOS-Geräten >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Direkte Registrierung von iOS-Geräten >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)  [DEM-Registrierung >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

## **Wie werden Sie dedizierte iOS-Geräte verwalten?**

Sie können unternehmenseigene Geräte mit dedizierten Benutzern wie folgt registrieren:

- **Apple-Geräteregistrierungsprogramm (DEP)** – Mit DEP erworbene oder verwaltete iOS-Geräte können mit einem Anmeldungsprofil angesprochen werden. Wenn die Benutzer ihre Geräte zum ersten Mal einschalten, lädt das Gerät das DEP-Profil herunter und registriert sich bei Intune.

- **Apple Configurator auf einem Mac** – Apple Configurator ist eine Apple-Anwendung, die auf einem Mac-Computer ausgeführt wird. Sie können die iOS-Geräte über ein USB-Kabel mit dem Mac-Computer verbinden, um ein Registrierungsprofil auf dem Gerät zu installieren. Wenn Sie die Geräte zur Registrierung auf die Werkseinstellungen zurücksetzen können, verwenden Sie die Registrierung mithilfe des Setup-Assistenten.

- **Mit IMEI-Nummer markieren** – Durch das Importieren der IMEI-Nummern (International Mobile Equipment Identity) unternehmenseigener Geräte können Sie diese in Intune als unternehmenseigene Geräte markieren. Anschließend können die Benutzer ihre Geräte als persönliche Geräte registrieren, indem sie das Unternehmensportal installieren, um den Zugriff auf Unternehmensressourcen wie E-Mail, Apps und Daten zu erhalten.

  > [!div class="button"]
  [Markieren mit IMEI >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) [iOS-DEP](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [iOS-Setup-Assistent](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Markieren mit IMEI](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)



<!--HONumber=Oct16_HO4-->


