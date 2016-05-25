---
# required metadata

title: Registrieren von mobilen Geräten für die Evaluierung | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 47806f69-303d-41d9-9b0e-9b9445ea24ac

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Registrieren mobiler Geräte und Installieren einer App für die Evaluierung
Um die Verwaltung mobiler Geräte mit Intune einzurichten, müssen Sie zunächst die Autorität für die Verwaltung mobiler Geräte festlegen, die Verwaltung der Geräteplattformen aktivieren und Ihre Geräte anschließend bei der Unternehmensportal-App registrieren. Sie können dann die von Ihnen veröffentlichte Microsoft Skype-Anwendung bereitstellen.

## Vorbereiten des Diensts für die Geräteverwaltung

1.  **Festlegen von Intune als Verwaltungsstelle für mobile Geräte**

    Klicken Sie in der [Intune-Verwaltungskonsole](https://manage.microsoft.com/) auf **Verwaltung** &gt; **Verwaltung mobiler Geräte**. Wählen Sie **Aufgaben** > **MDM-Autorität festlegen** aus, und klicken Sie dann im Dialogfeld **MDM-Autorität** auf **Ja**.

2.  **Aktivieren von MDM für Ihre Geräteplattform**

    Aktivieren Sie die Verwaltung mobiler Geräte für die Geräteplattform, die Sie verwalten möchten. Je nach Plattform sind andere Anforderungen relevant:

    -   **iOS und Mac OS X**: Siehe [Einrichten der iOS- und Mac-Verwaltung mit Microsoft Intune](/Intune/Deploy-Use/set-up-ios-and-mac-management-with-microsoft-intune)..

    -   **Android**: Mobile Android-Geräte ermöglichen Benutzern die Registrierung über die Unternehmensportal-App, die in Google Play zur Verfügung steht. Es ist keine weitere Konfiguration in Intune erforderlich.

    -   **Windows Phone**: Siehe [Einrichten der Windows Phone-Verwaltung mit Microsoft Intune](/Intune/Deploy-Use/set-up-windows-phone-management-with-microsoft-intune)..

## Testgeräte registrieren

### iOS und Mac OS X
Installieren Sie die **Microsoft Intune-Unternehmensportal-App** der Microsoft Corporation, die im App Store verfügbar ist, und melden Sie sich mit den oben hinzugefügten Intune-Anmeldeinformationen an. Rufen Sie **Angemeldete Geräte** auf, um Ihr Gerät hinzuzufügen.

### Android
Installieren Sie die **Intune-Unternehmensportal-App** der Microsoft Corporation, die auf [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612) verfügbar ist, und melden Sie sich mit den oben hinzugefügten Intune-Anmeldeinformationen an.

### Windows Phone 8.1
Benutzer installieren die **Unternehmensportal-App** der Microsoft Corporation, die im Windows Phone Store verfügbar ist, und melden sich mit den oben hinzugefügten Intune-Anmeldeinformationen an.  Rufen Sie **Angemeldete Geräte** auf, um Ihr Gerät hinzuzufügen.

 ### Windows Phone 8.0
 Benutzer klicken auf **Systemeinstellungen** &gt; **Unternehmens-Apps** und registrieren sich mit den oben hinzugefügten Intune-Anmeldeinformationen. Die Unternehmensportal-App wird auf Ihrem Telefon bereitgestellt.

Wenn Sie zur Eingabe einer **Serveradresse**aufgefordert werden, geben Sie "manage.microsoft.com" ein.


## Installieren der zuvor bereitgestellten App
Öffnen Sie auf dem Gerät das Unternehmensportal, wählen Sie **Apps** aus, und installieren Sie dann **Microsoft Skype**..

Weitere Informationen zum Verwalten von mobilen Geräten mit Intune finden Sie unter [Vorbereiten der Registrierung von Geräten bei Microsoft Intune](/Intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)..

### Nächste Schritte
Gratulation! Sie habe soeben Schritt 5 der exemplarischen Vorgehensweise *Microsoft Intune-Evaluierung* ausgeführt.

>[!div class="step-by-step"]

>[&larr; **Erstellen von Richtlinien**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md)     [**Optionen und Extras** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md)  


<!--HONumber=May16_HO1-->


