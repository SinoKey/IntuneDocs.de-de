---
title: Senden von Diagnosedatenprotokollen an Ihren IT-Administrator per E-Mail | Microsoft Intune
description: 
keywords: 
author: staciebarker
manager: angrobe
ms.date: 05/31/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 85c868e7-8d63-480c-9770-4e99614a5c94
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d3a2daebdb781ce99aa103e7717ffa1b0297cb3a
ms.openlocfilehash: 7e90141f08cf029a005aad1ae0501fc1962eb958


---


# Senden von Diagnosedatenprotokollen an Ihren IT-Administrator per E-Mail

Wenn Sie auf Ihrem Android-Gerät eine Fehlermeldung erhalten, während Sie mit Ihren Geschäfts- bzw. Schul-Apps arbeiten oder sich in der Unternehmensportal-App befinden, können Sie Diagnosedatenprotokolle senden, um Ihrem IT-Administrator bei der Diagnose und Behebung des Fehlers zu helfen. Damit alle Details in die Protokolle aufgenommen werden, die Ihrem IT-Administrator die Diagnose des Problems erleichtern, aktivieren Sie die „Ausführliche Protokollierung“. Erfahren Sie mehr über die [ausführliche Protokollierung](use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android.md).

So aktivieren Sie die ausführliche Protokollierung:

1.  Öffnen Sie die Unternehmensportal-App.

2.  Tippen Sie auf **Menü** &gt; **Einstellungen**.

    > [!NOTE]
    > Je nach Typ des Android-Geräts, das Sie haben, kann **Menü** eine Schaltfläche in der Software oder Taste auf dem Gerät sein.

3.  Tippen Sie unter **Diagnosedaten** auf **Daten senden**.

    > [!NOTE]
    > **Bei ausschließlichem Verwenden von Android-Geräten ab Version 6.0:** Wenn Sie auf **Daten senden** klicken, wird die Meldung **Unternehmensportal den Zugriff auf Fotos, Medien und Dateien auf Ihrem Gerät erlauben?** angezeigt.

    Diese Meldung ist irreführend, da **Microsoft nie auf Fotos, Medien oder Dateien auf Ihrem Gerät zugreift!** Google steuert den Meldungstext, weshalb er von Microsoft nicht geändert werden kann.  Wenn Sie Zugriff gewähren, erlauben Sie Ihrem Gerät lediglich das Schreiben von Datenprotokollen auf die SD-Karte des Geräts, sodass Sie diese Protokolle mithilfe eines USB-Kabels woanders speichern können.

    Wenn Sie den Zugriff verweigern, wird die Meldung beim nächsten Tippen auf **Daten senden** angezeigt. Sie können künftige Meldungen jedoch deaktivieren, indem Sie das Kontrollkästchen **Nicht mehr nachfragen** aktivieren.  Wenn Sie den Zugriff später erlauben möchten, wechseln Sie zu **Einstellungen** &gt; **Apps** &gt; **Unternehmensportal** &gt; **Berechtigungen** &gt; **Speicher**, um die Berechtigung zu aktivieren.

4.  Befolgen Sie die Aufforderungen zum Auswählen einer E-Mail-App zum Senden der Protokolle an Ihren IT-Administrator. Die App erstellt eine voradressierte E-Mail, an die alle Protokolle angefügt sind.


### Weitere Informationen:
[Verwenden Ihres Android-Geräts mit Intune](using-your-android-device-with-intune.md)



<!--HONumber=Aug16_HO4-->


