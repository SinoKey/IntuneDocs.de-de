---
title: "Sammeln von Geräteprotokollen | Microsoft Intune"
description: 
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 06/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ac5c66f57194a84580aa495a58e5281683aa1cca
ms.openlocfilehash: 4fc08fcea6cea897b9ddc3d0c00f2d83069f639d


---

# Geräteprotokolle

Im Rahmen der Problembehandlung empfiehlt es sich, die Protokolle der Benutzergeräte zu erfassen und zu sammeln. Im Folgenden finden Sie Anleitungen zum Sammeln dieser Protokolle. In der Regel benötigen Sie Zugriff auf die jeweiligen Geräte, oder Sie müssen die Benutzer bitten, dass sie die Protokolle sammeln und Ihnen senden. 

### Protokollspeicherort in Android
Android-Protokolle befinden sich unter *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*. Die Benutzer können Ihnen Protokolldateien per E-Mail senden. Die entsprechende Vorgehensweise finden Sie unter [Senden von Android-Diagnosedatenprotokollen an Ihren IT-Administrator per E-Mail](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android).

### iOS-Protokolle

Die Benutzer können Ihnen Fehler beim Registrieren senden. Die entsprechende Vorgehensweise finden Sie unter [Senden von iOS-Registrierungsfehlern an Ihren IT-Administrator](/intune/enduser/send-errors-to-your-it-admin-ios).

### Mac OS X-Geräte

1. Öffnen Sie die App **Konsole**.
2. Wählen Sie unter **DATEIEN** die Datei **system.log**.
3. Wählen Sie oben auf der Menüleiste **Datei** > **Kopie speichern unter…** und speichern Sie die Datei.

### Windows Phone

Die Benutzer müssen in der **Unternehmensportal-App für Windows Phone** das Symbol mit den drei Punkten (**…**) auswählen, um auf das Menü zuzugreifen, und anschließend wählen sie **Protokolle senden**. Diese Option steht vor und nach der Anmeldung beim Portal zur Verfügung.

### Windows

Für das Windows-Unternehmensportal befinden sich die Protokolle unter *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.



<!--HONumber=Jun16_HO4-->


