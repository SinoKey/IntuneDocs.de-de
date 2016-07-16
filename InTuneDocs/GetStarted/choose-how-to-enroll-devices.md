---
title: "Auswählen der Methode zum Registrieren mobiler Geräte | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 06/06/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466
translationtype: Human Translation
ms.sourcegitcommit: f1dc713099c982d6e32c87b814dd3f55b1656eda
ms.openlocfilehash: 5668a4d8a6cce15446201926b03d71ede174a299


---

# Auswählen der Methode zum Registrieren mobiler Geräte

Die Registrierung mobiler Geräte ist der Prozess, den Sie durchführen, damit Smartphones, Tablets und PCs von Microsoft Intune verwaltet werden können. Als Administrator müssen Sie anhand der folgenden Punkte bestimmen, wie Geräte am besten registriert werden:

 -  Eigentümerschaft (privat oder in Unternehmensbesitz)
 -  Nutzung (freigegeben oder persönlich)
 -  Plattform (iOS, Android, Windows Phone, Windows-PC, Mac-PC) – ausgewählt durch die Registrierungsmethode

Die Antworten auf die folgenden Fragen helfen Ihnen, die beste Registrierungsmethode für die von Ihnen verwalteten Geräte zu ermitteln.

## **Bringen die Mitarbeiter ihre eigenen Geräte mit, oder werden die Geräte von Ihrer Organisation bereitgestellt?**

  Bei der Registrierung **benutzereigener Geräte** (auch bekannt als BYOD, "Bring your own device") können Benutzer ihre Geräte registrieren, um auf Unternehmensressourcen wie E-Mail-, Unternehmens-Apps und -daten sowie Support zuzugreifen. **Unternehmenseigene Geräte** (Company-Owned Devices, COD) werden Mitarbeitern von der Organisation bereitgestellt, damit sie ihre geschäftlichen Aufgaben erledigen können.
  > [!div class="button"]
  [BYOD-Registrierung >](#byod-device-enrollment)   [COD-Registrierung >](#cod-device-enrollment)

### BYOD-Geräteregistrierung

Die BYOD-Registrierung erfordert, dass Benutzer die Intune-Unternehmensportal-App auf ihren Geräten installieren. Sie können dann die App starten und sich unter Angabe der Anmeldeinformationen ihres Geschäfts-, Schul- oder Unikontos registrieren. Vorausgesetzt, Intune findet eine Lizenz für diese Anmeldeinformationen, wird das Gerät der Intune-Verwaltungskonsole hinzugefügt. Es erhält eine Richtlinie von Intune, die Zugriff auf Unternehmensressourcen gewährt.

**Wählen Sie den Gerätetyp aus:**
> [!div class="button"]
[Android](..deploy-use/set-up-android-management-with-microsoft-intune) [iOS und Mac](..deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile und Windows Phone](..deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Windows-PCs](..deploy-use/set-up-windows-device-management-with-microsoft-intune)


### COD-Geräteregistrierung

Unternehmenseigene Geräte (company-owned devices; COD) können registriert werden, um dedizierte Benutzer zu unterstützen, oder sie können von vielen Benutzern gemeinsam genutzt werden.  **Gemeinsam genutzte Geräte** werden nicht nur von einem einzelnen Benutzer verwendet und sind meist nicht für den E-Mail-Zugriff konfiguriert. Dazu zählen beispielsweise Kioskgeräte oder aufgabenspezifische Geräte, die die Benutzer bei Bedarf einem Pool entnehmen und wieder zurückgeben. Die empfohlenen Registrierungsmethoden hängen von der Geräteplattform ab. **Dedizierte Geräte** werden an einzelne Benutzer ausgegeben und müssen als Unternehmensressourcen verfolgt werden. Sie ermöglichen Benutzern als personalisierte Geräte den Zugriff auf E-Mails und Daten. Die empfohlenen Registrierungsmethoden hängen von der Geräteplattform ab. [Nächste Frage...](Are your company-owned devices shared or do they have dedicated users?)

## **Werden Ihre unternehmenseigenen Geräte gemeinsam genutzt oder von dedizierten Benutzern verwendet?**

> [!div class="button"]
[Freigegeben >](#Shared-company-owned-devices)   [Dediziert >](..deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)


### Gemeinsam genutzte unternehmenseigene Geräte

Diese Geräte werden nicht nur von einem einzelnen Benutzer verwendet und sind meist nicht für den E-Mail-Zugriff konfiguriert. Dazu zählen beispielsweise Kioskgeräte oder aufgabenspezifische Geräte, die die Benutzer bei Bedarf einem Pool entnehmen und wieder zurückgeben. Die empfohlenen Registrierungsmethoden hängen von der Geräteplattform ab.

  - **Windows- und Android-Geräte** – Ein *Geräteregistrierungs-Manager* ist ein Intune-Konto, das verwendet werden kann, um viele gemeinsam genutzte Geräte mithilfe der Unternehmensportal-App zu registrieren.
  > [!div class="button"]
  [Windows >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#shared-ios-device-enrollment)

### Registrierung gemeinsam genutzter iOS-Geräte

Die bevorzugte Methode zur Registrierung gemeinsam genutzter iOS-Geräte hängt davon ab, wie Sie diese Geräte erwerben und verwalten:

  - **Apple-Geräteregistrierungsprogramm (DEP)** – Mit DEP erworbene oder verwaltete iOS-Geräte können mit einem Anmeldungsprofil angesprochen werden. Wenn die Benutzer ihre Geräte zum ersten Mal einschalten, lädt das Gerät das DEP-Profil herunter und registriert sich beim Profil-DEP.
  - **Apple Configurator auf einem Mac** – Apple Configurator ist eine Apple-Anwendung, die auf einem Mac-Computer ausgeführt wird. Sie können die iOS-Geräte über ein USB-Kabel mit dem Mac-Computer verbinden, um ein Registrierungsprofil auf dem Gerät zu installieren. Wenn Sie die Geräte zur Registrierung auf die Werkseinstellungen zurücksetzen können, verwenden Sie die Registrierung mithilfe des Setup-Assistenten. Falls Sie die Geräte nicht auf die Werkseinstellungen zurücksetzen möchten, verwenden Sie die direkte Registrierung.
  - **Keine der genannten Möglichkeiten** – Wenn Sie die Registrierungsmethoden mit Apple-DEP oder Apple Configurator nicht verwenden können oder möchten, verwenden Sie den Geräteregistrierungs-Manage von Intune.

  **Wählen Sie:**
    > [!div class="button"]
     [DEP-Registrierung >](../deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Mac >](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Direkte Registrierung >](../deploy-use/ios-direct-enrollment-in-microsoft-intune)  

  > [!div class="button"]
    [DEM-Registrierung >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

**Einzelne Benutzer** – Dem Unternehmen gehörende Geräte, die an einzelne Benutzer ausgegeben werden, müssen als Unternehmensressourcen verfolgt werden und den Benutzern gleichzeitig als persönliche Geräte den Zugriff auf E-Mails und Daten ermöglichen. Die empfohlenen Registrierungsmethoden hängen von der Geräteplattform ab.

  - **Windows- und Android-Geräte** – Durch das Importieren der IMEI-Nummern (International Mobile Equipment Identity) der unternehmenseigenen Geräte können Sie diese in Intune als dem Unternehmen gehörende Geräte markieren. Anschließend können die Benutzer ihre Geräte als persönliche Geräte registrieren, indem sie das Unternehmensportal installieren, um den Zugriff auf Unternehmensressourcen wie E-Mail, Apps und Daten zu erhalten.
  > [!div class="button"]
  [Das Tag mit der IMEI >](../deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  - **iOS-Geräte** – Gemeinsam genutzte iOS-Geräte können auf drei Arten verwaltet werden.  **Wie werden Sie die freigegebenen iOS-Geräte registrieren?**

    - **Apple-Geräteregistrierungsprogramm (DEP)** – Mit DEP erworbene oder verwaltete iOS-Geräte können mit einem Anmeldungsprofil angesprochen werden. Wenn die Benutzer ihre Geräte zum ersten Mal einschalten, lädt das Gerät das DEP-Profil herunter und wird dem Profil entsprechend registriert.
    > [!div class="button"]
    [DEP-Registrierung](../deploy-use/ios-device-enrollment-program-in-microsoft-intune).

    - **Apple Configurator auf einem Mac** – Apple Configurator ist eine Apple-Anwendung, die auf einem Mac-Computer ausgeführt wird. Sie können die iOS-Geräte über ein USB-Kabel mit dem Mac-Computer verbinden, um ein Registrierungsprofil auf dem Gerät zu installieren. Wenn Sie die Geräte zur Registrierung auf die Werkseinstellungen zurücksetzen können, verwenden Sie die Registrierung mithilfe des Setup-Assistenten.

    Falls Sie die Geräte nicht auf die Werkseinstellungen zurücksetzen möchten, verwenden Sie die direkte Registrierung.
    Wenn Sie die Geräte zur Registrierung auf die Werkseinstellungen zurücksetzen können, verwenden Sie die Registrierung mithilfe des Setup-Assistenten.
    > [!div class="button"][iOS Setup Assistant enrollment](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [!div class="button"][iOS direct enrollment](../deploy-use/ios-direct-enrollment-in-microsoft-intune).

    - **Keine der genannten Möglichkeiten** – Wenn Sie die Registrierungsmethoden mit Apple-DEP oder Apple Configurator nicht verwenden können oder möchten, können Sie durch das Importieren der IMEI-Nummern (International Mobile Equipment Identity) der unternehmenseigenen Geräte diese in Intune als dem Unternehmen gehörende Geräte markieren. Anschließend können die Benutzer ihre Geräte als persönliche Geräte registrieren, indem sie das Unternehmensportal installieren, um den Zugriff auf Unternehmensressourcen wie E-Mail, Apps und Daten zu erhalten.
    > [!div class="button"][Tag devices with IMEI numbers](../deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)



<!--HONumber=Jun16_HO5-->


