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
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: 6fc98df3df19e8858e60427f3b0bfd44c4f4b17d
ms.openlocfilehash: dbdd2649ed565efffe50916c1dd661aac2ed38d8


---
# Auswählen der Methode zum Registrieren mobiler Geräte

Die Antworten auf die folgenden Fragen helfen Ihnen, die beste Registrierungsmethode für die von Ihnen verwalteten Geräte zu ermitteln.

## **Wie werden dedizierte, unternehmenseigene Geräte verwaltet?**

  > [!div class="button"]
[iOS-DEP >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)   [iOS-Setup-Assistent >](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Markieren mit IMEI >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Sie können unternehmenseigene Geräte mit dedizierten Benutzern wie folgt registrieren:

  - **Apple-Geräteregistrierungsprogramm (DEP)** – Mit DEP erworbene oder verwaltete iOS-Geräte können mit einem Anmeldungsprofil angesprochen werden. Wenn die Benutzer ihre Geräte zum ersten Mal einschalten, lädt das Gerät das DEP-Profil herunter und registriert sich bei Intune.

  - **Apple Configurator auf einem Mac** – Apple Configurator ist eine Apple-Anwendung, die auf einem Mac-Computer ausgeführt wird. Sie können die iOS-Geräte über ein USB-Kabel mit dem Mac-Computer verbinden, um ein Registrierungsprofil auf dem Gerät zu installieren. Wenn Sie die Geräte zur Registrierung auf die Werkseinstellungen zurücksetzen können, verwenden Sie die Registrierung mithilfe des Setup-Assistenten.

  - **Mit IMEI-Nummer markieren** – Durch das Importieren der IMEI-Nummern (International Mobile Equipment Identity) unternehmenseigener Geräte können Sie diese in Intune als unternehmenseigene Geräte markieren. Dies ist die einzige Möglichkeit, dedizierte Windows- und Android-Geräte („Einzelbenutzermodus“) als unternehmenseigen zu identifizieren. iOS-Geräte, die nicht über das Apple-Geräteregistrierungsprogramm oder den Apple Configurator registriert werden, können auch mit einer IMEI-Nummer gekennzeichnet werden. Nach dem Vordeklarieren von Geräten, damit diese als „unternehmenseigen“ markiert werden, können Sie die Geräte an Benutzer verteilen. Anschließend können die Benutzer ihre Geräte als dedizierte Geräte registrieren, indem sie das Unternehmensportal installieren, um den Zugriff auf Unternehmensressourcen wie E-Mail, Apps und Daten zu erhalten.

  > [!div class="button"]
  [< Zurück](choose-how-to-enroll-devices3.md)



<!--HONumber=Aug16_HO4-->


