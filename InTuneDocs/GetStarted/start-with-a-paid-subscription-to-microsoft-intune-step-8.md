---
title: "Registrieren mobiler Geräte und Installieren einer App | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6cb729533107d511fa0cc863ec6ab842e7624982
ms.openlocfilehash: 78cf5472a6069e09b5072253635066d95094a89e


---

# Registrieren mobiler Geräte und Installieren einer App
Um die Verwaltung mobiler Geräte mit Intune einzurichten, müssen Sie zunächst die Autorität für die Verwaltung mobiler Geräte festlegen, die Verwaltung der Geräteplattformen aktivieren und Ihre Geräte anschließend bei der Unternehmensportal-App registrieren. Dann können Sie die Microsoft Skype-Anwendung bereitstellen, die Sie in Schritt 6 veröffentlicht haben.

## Aktivieren der Geräteverwaltung und Registrieren von Geräten

1.  **Festlegen von Intune als Verwaltungsstelle für mobile Geräte** Klicken Sie in der [Intune-Verwaltungskonsole](https://manage.microsoft.com/) auf **Verwaltung** > **Verwaltung mobiler Geräte**. Wählen Sie unter **Aufgaben** die Option **MDM-Autorität** festlegen.  Klicken Sie im Dialogfeld „MDM-Autorität“ auf **Ja**.
    ![Verwaltungskonsole – MDM auf „Intune“ festlegen](./media/mdmAuthority.png)

2.  **Aktivieren von MDM für Ihre Geräteplattform** Aktivieren Sie die Verwaltung mobiler Geräte für die Geräteplattform, die Sie verwalten möchten. Je nach Plattform sind andere Anforderungen relevant:

    -   **iOS und Mac OS X**: Siehe [Einrichten der iOS- und Mac-Verwaltung mit Microsoft Intune](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).

    -   **Windows Phone**: Siehe [Einrichten der Windows Phone-Verwaltung mit Microsoft Intune](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune).

    -   **Android**: Mobile Android-Geräte ermöglichen Benutzern die Registrierung über die Unternehmensportal-App, die in [Google Play](https://play.google.com/store/apps/details?id=com.skype.raider) zur Verfügung steht. Es ist keine weitere Konfiguration in Intune erforderlich.

3.  **Registrieren von Geräten**:

    -   **Android**: Installieren Sie die **Intune-Unternehmensportal**-App der Microsoft Corporation, die in [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612) verfügbar ist, und melden Sie sich mit den oben hinzugefügten Intune-Anmeldeinformationen an.

    -   **iOS und Mac OS X**: Installieren Sie die **Microsoft Intune-Unternehmensportal**-App der Microsoft Corporation, die im App Store verfügbar ist, und melden Sie sich mit den oben hinzugefügten Intune-Anmeldeinformationen an. Rufen Sie **Angemeldete Geräte** auf, um Ihr Gerät hinzuzufügen.

    -   **Windows Phone 8.1**: Benutzer installieren die **Unternehmensportal**-App der Microsoft Corporation, die im Windows Phone Store verfügbar ist, und melden sich mit den oben hinzugefügten Intune-Anmeldeinformationen an.  Rufen Sie **Angemeldete Geräte** auf, um Ihr Gerät hinzuzufügen.

    -   **Windows Phone 8.0**: Benutzer klicken auf **Systemeinstellungen** &gt; **Unternehmens-Apps**, und melden sich mit den oben hinzugefügten Intune-Anmeldeinformationen an. Die Unternehmensportal-App wird auf Ihrem Telefon bereitgestellt.

    Wenn Sie zur Eingabe einer **Serveradresse**aufgefordert werden, geben Sie "manage.microsoft.com" ein.

## Installieren einer App auf einem registrierten Gerät
In [Schritt 6](start-with-a-paid-subscription-to-microsoft-intune-step-6.md) dieser Kurzanleitung haben Sie die Skype-App für Ihre benutzerdefinierte Intune-Benutzergruppe veröffentlicht. Jetzt installieren Sie diese App auf einem neu registrierten Gerät.

Öffnen Sie das Unternehmensportal auf dem registrierten Gerät, wählen Sie **Apps** aus, und installieren Sie dann **Microsoft Skype**.

Weitere Informationen zum Verwalten von mobilen Geräten mit [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] finden Sie unter [Vorbereiten der Registrierung von Geräten in Microsoft Intune](/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune).


### Nächste Schritte
Gratulation! Sie haben den letzten Schritt der Kurzanleitung *Erste Schritte mit Intune* abgeschlossen. Ihre anfängliche Konfiguration ist jetzt abgeschlossen, und Sie können in Betracht ziehen, weitere MDM-Funktionen zu aktivieren.

>[!div class="step-by-step"]

>[&larr; **Registrieren von Geräten**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Aufgaben nach der Konfiguration** &rarr;](.\post-configuration-tasks.md)  



<!--HONumber=Jun16_HO4-->


