---
title: "Sammeln von Geräteprotokollen | Microsoft-Dokumentation"
description: "Erfahren Sie, wie Sie Protokolle Ihrer verwalteten Geräte sammeln können."
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b068da7685792757825a4bc0d555e28ee0168cb1
ms.openlocfilehash: 7009cf7626008124e4c8a71198e21ae6def93581


---

# <a name="device-logs"></a>Geräteprotokolle

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Im Rahmen der Problembehandlung empfiehlt es sich, die Protokolle der Benutzergeräte zu erfassen und zu sammeln. Im Folgenden finden Sie Anleitungen zum Sammeln dieser Protokolle. In der Regel benötigen Sie Zugriff auf das Gerät, um diese Protokolle abzurufen, oder Sie müssen die Benutzer bitten, dass sie die Protokolle sammeln und Ihnen senden.

### <a name="android-logs"></a>Android-Protokolle
Android-Protokolle befinden sich unter *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*.

Manchmal – insbesondere bei neueren Android-Geräten – werden die Dateien nicht angezeigt. In diesem Fall bitten Sie die Benutzer, die Unternehmensportal-App für Android zu öffnen. Anschließend sollen sie **Einstellungen**>**Protokolle kopieren** auswählen und ihr Gerät neu starten.

Weitere Informationen dazu, wie Ihre Benutzer Ihnen Datenprotokolle senden können, finden Sie in folgenden Artikeln:

- [Verwenden der ausführlichen Protokollierung zur Unterstützung Ihres IT-Administrators bei der Behebung von Geräteproblemen](/intune/enduser/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android): Beschreibt, wie Benutzer die ausführliche Protokollierung aktivieren, die Ihnen automatisch ihre sämtlichen Datenprotokolle sendet. Die ausführliche Protokollierung ist standardmäßig aktiviert.

- [Senden von Diagnosedatenprotokollen an Ihren IT-Administrator per E-Mail](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)

- [Senden von Diagnosedatenprotokollen an Ihren IT-Administrator über ein USB-Kabel](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)

### <a name="ios-logs"></a>iOS-Protokolle

Benutzer können Ihnen Fehler beim Registrieren senden. Die entsprechende Vorgehensweise finden Sie unter [Senden von iOS-Registrierungsfehlern an Ihren IT-Administrator](/intune/enduser/send-errors-to-your-it-admin-ios).

### <a name="mac-os-x-logs"></a>Mac OS X-Protokolle

1. Öffnen Sie die App **Konsole**.
2. Wählen Sie unter **DATEIEN** die Datei **system.log** aus.
3. Wählen Sie oben auf der Menüleiste **Datei** > **Kopie speichern unter…** aus. Speichern Sie die Datei dann.

### <a name="windows-phone"></a>Windows Phone

In der Windows Phone-Unternehmensportal-App klicken Benutzer auf die drei Punkte (**...**), um das Menü zu öffnen, und wählen dann **Protokolle senden** aus. Diese Option steht vor und nach der Anmeldung bei der Unternehmensportal-App zur Verfügung.

### <a name="windows"></a>Windows

Für das Windows-Unternehmensportal befinden sich die Protokolle unter *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.



<!--HONumber=Dec16_HO3-->


