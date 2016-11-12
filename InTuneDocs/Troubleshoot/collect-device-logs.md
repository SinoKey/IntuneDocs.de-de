---
title: "Sammeln von Geräteprotokollen | Microsoft Intune"
description: "Erfahren Sie, wie Sie Protokolle Ihrer verwalteten Geräte sammeln können."
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3a081109cd499d3bdda75cb6c8a4dab9d9d28fab
ms.openlocfilehash: ec7d522e8dcff66d1b84fed3c4c0cc708e555e67


---

# <a name="device-logs"></a>Geräteprotokolle

Im Rahmen der Problembehandlung empfiehlt es sich, die Protokolle der Benutzergeräte zu erfassen und zu sammeln. Im Folgenden finden Sie Anleitungen zum Sammeln dieser Protokolle. In der Regel benötigen Sie Zugriff auf die jeweiligen Geräte, oder Sie müssen die Benutzer bitten, dass sie die Protokolle sammeln und Ihnen senden.

### <a name="android-log-location"></a>Protokollspeicherort in Android
Android-Protokolle befinden sich unter *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*. Die Benutzer können Ihnen Protokolldateien per E-Mail senden. Die entsprechende Vorgehensweise finden Sie unter [Senden von Android-Diagnosedatenprotokollen an Ihren IT-Administrator per E-Mail](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android).

### <a name="ios-logs"></a>iOS-Protokolle

Die Benutzer können Ihnen Fehler beim Registrieren senden. Die entsprechende Vorgehensweise finden Sie unter [Senden von iOS-Registrierungsfehlern an Ihren IT-Administrator](/intune/enduser/send-errors-to-your-it-admin-ios).

### <a name="mac-os-x-devices"></a>Mac OS X-Geräte

1. Öffnen Sie die App **Konsole**.
2. Wählen Sie unter **DATEIEN** die Datei **system.log**.
3. Wählen Sie oben auf der Menüleiste **Datei** > **Kopie speichern unter…** und speichern Sie die Datei.

### <a name="windows-phone"></a>Windows Phone

Die Benutzer müssen in der **Unternehmensportal-App für Windows Phone** das Symbol mit den drei Punkten (**…**) auswählen, um auf das Menü zuzugreifen, und anschließend wählen sie **Protokolle senden**. Diese Option steht vor und nach der Anmeldung beim Portal zur Verfügung.

### <a name="windows"></a>Windows

Für das Windows-Unternehmensportal befinden sich die Protokolle unter *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.



<!--HONumber=Oct16_HO3-->


