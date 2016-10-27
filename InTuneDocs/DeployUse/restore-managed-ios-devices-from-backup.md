---
title: "Wiederherstellen von durch Intune verwalteten iOS-Geräten aus einer Sicherung | Microsoft Intune"
description: "Stellen Sie einen Leitfaden für Endbenutzer bereit, der erklärt, wie sie ihre Geräte nach der Wiederherstellung aus einer Sicherung erneut registrieren können."
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 10/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a19e5612-8805-4bd7-a86a-b734bde293ae
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 612b0954a81de1ee8d4a1e96c7440239437dec14
ms.openlocfilehash: 5fc4423f8fd0c5829be5fe6c96949e126991e430


---

# Wiederherstellen von durch Intune verwalteten iOS-Geräten aus einer Sicherung

Es werden Fälle auftreten, in denen Sie oder Ihre Benutzer ein iOS-Gerät aus einer Sicherung wiederherstellen müssen, z.B. wenn ein Benutzer ein neues Gerät erhält. In diesem Thema werden zusätzliche Schritte erläutert, die Sie möglicherweise durchführen müssen, um die Intune-Verwaltung nach dem Wiederherstellen eines Geräts einzurichten.

## Wiederherstellen von Sicherungen auf dem gleichen Gerät

Wenn die Sicherung auf dem gleichen Gerät wiederhergestellt wird, wird auch der Registrierungsstatus auf diesem Gerät wiederhergestellt. Es sind keine weiteren Aktionen erforderlich.

## Wiederherstellen von Sicherungen auf verschiedenen Geräten

Wenn die Sicherung auf einem anderen Gerät wiederhergestellt wird, wird der Registrierungsstatus nicht automatisch auf dem neuen Gerät wiederhergestellt. Benutzer müssen die Standardregistrierungsschritte in der Unternehmensportal-App Version 2.1.22 oder höher durchführen, um [ihr iOS-Gerät bei Intune zu registrieren](/Intune/EndUser/enroll-your-device-in-intune-ios).

> [!NOTE]
> Wenn Sie für Ihre Benutzer Richtlinien für den bedingten Zugriff verwenden, können sie nicht auf die Unternehmens-E-Mails zugreifen, bis sie sich erneut registriert haben.

> [!TIP]
> Eine Beispielmitteilung für Ihre Benutzer könnte wie folgt lauten: Um sich auf Ihrem neuen Gerät zu registrieren, vergewissern Sie sich, dass die Version der Unternehmensportal-App Version 2.1.22 oder höher ist. Um die Version zu überprüfen, öffnen Sie die Unternehmensportal-App, tippen Sie auf die Schaltfläche „Menu“ (Menü) oben rechts und anschließend auf „About“ (Info). Wenn Sie eine ältere Version installiert haben, beenden Sie die Unternehmensportal-App, und öffnen Sie den App Store. Tippen Sie in der unteren rechten Ecke auf die Schaltfläche „Updates“ und anschließend auf die Schaltfläche „Update“ (Aktualisieren) neben dem Element der Unternehmensportal-App in der Liste. Sobald das Update abgeschlossen ist, starten Sie die Unternehmensportal-App, und [registrieren Sie Ihr iOS-Gerät bei Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).



<!--HONumber=Oct16_HO2-->


