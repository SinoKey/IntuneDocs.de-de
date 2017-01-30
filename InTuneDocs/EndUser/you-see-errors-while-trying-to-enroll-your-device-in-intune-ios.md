---
title: "Fehlermeldungen beim Versuch der Registrierung Ihres iOS-Geräts | Microsoft-Dokumentation"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 92a8d06d-0ecb-4912-898b-993e8eaf4e58
searchScope:
- Company Portal
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a87fe0cf9591040f1455d71b1f40cd0705ba8abf
ms.openlocfilehash: 06866b9db458851dbb23d5ccf741cad3e1d4c5d0


---

# <a name="you-see-errors-while-trying-to-enroll-your-ios-device-in-intune"></a>Es werden Fehlermeldungen angezeigt, wenn Sie versuchen, Ihr iOS-Gerät bei Intune zu registrieren

In der folgenden Tabelle sind Fehler aufgeführt, die bei der Registrierung Ihres iOS-Geräts bei Intune auftreten können. Geben Sie diesen Link an Ihren IT-Administrator weiter. Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](http://portal.manage.microsoft.com).

|Fehlermeldung|Problem|Informationen für den IT-Administrator|
|-----------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|NoEnrollmentPolicy|Keine Registrierungsrichtlinie|Vergewissern Sie sich, dass alle für die Registrierung erforderlichen Komponenten, wie der Apple Push Notification Service (APNs), eingerichtet wurden, und dass „iOS as a platform“ (iOS als Plattform) aktiviert ist. Anweisungen hierzu finden Sie unter [Einrichten der iOS- und Mac-Geräteverwaltung](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).|
|DeviceCapReached|Sie haben bereits zu viele mobile Geräte registriert.|Der Benutzer muss eines seiner derzeit registrierten mobilen Geräte aus dem Unternehmensportal entfernen, bevor ein weiteres mobiles Gerät registriert wird. Sehen Sie sich die Anweisungen für Ihren Gerätetyp an: [Android](unenroll-your-device-from-intune-android.md), [iOS](unenroll-your-device-from-intune-ios.md), [Windows](unenroll-your-device-from-intune-windows.md).|
|APNSCertificateNotValid|Es liegt ein Problem mit dem Zertifikat vor, über das die Kommunikation Ihres mobilen Geräts mit Ihrem Unternehmensnetzwerk ermöglicht wird.<br /><br />Wenden Sie sich an Ihre IT-Administratoren, und teilen Sie ihnen mit, dass die Meldung **APNSCertificateNotValid** beim Versuch angezeigt wurde, Ihr mobiles Gerät zu registrieren, und informieren Sie sie über die Lösung in dieser Tabelle.|Über den Apple Push Notification Service (APNs) ist der Zugriff auf registrierte iOS-Geräte möglich. Wenn die Schritte zum Erhalten eines APNs-Zertifikats nicht ausgeführt wurden oder das APNs-Zertifikat abgelaufen ist, ist die Registrierung nicht möglich, und es wird diese Meldung angezeigt.<br /><br />Überprüfen Sie die Informationen über das Einrichten von Benutzern unter [Synchronisieren von Active Directory und Hinzufügen von Benutzern zu Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) und [Erstellen von Gruppen zum Organisieren von Benutzern und Geräten](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|AccountNotOnboarded|Es liegt ein Problem mit dem Zertifikat vor, über das die Kommunikation Ihres mobilen Geräts mit Ihrem Unternehmensnetzwerk ermöglicht wird.<br /><br />Wenden Sie sich an Ihre IT-Administratoren, und teilen Sie ihnen mit, dass die Meldung **APNSNotOnboarded** beim Versuch angezeigt wird, Ihr mobiles Gerät zu registrieren, und informieren Sie sie über die Lösung in dieser Tabelle.|Über den Apple Push Notification Service (APNs) ist der Zugriff auf registrierte iOS-Geräte möglich. Wenn die Schritte zum Erhalten eines APNs-Zertifikats nicht ausgeführt wurden oder das APNs-Zertifikat abgelaufen ist, ist die Registrierung nicht möglich, und es wird diese Meldung angezeigt.<br /><br />Weitere Informationen finden Sie unter [Einrichten der iOS- und Mac-Geräteverwaltung](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).|
|DeviceTypeNotSupported|Sie haben möglicherweise versucht, eine Registrierung mit einem Nicht-iOS-Gerät auszuführen. Der Mobilgerättyp, den Sie versuchen zu registrieren, wird nicht unterstützt.<br /><br />Stellen Sie sicher, dass auf Ihrem Gerät mindestens die iOS-Version 8.0 ausgeführt wird.<br /><br />Wenden Sie sich an Ihre IT-Administratoren, und teilen Sie ihnen mit, dass die Meldung **DeviceTypeNotSupported** beim Versuch angezeigt wird, Ihr mobiles Gerät zu registrieren, und informieren Sie sie über die Lösung in dieser Tabelle.|Stellen Sie sicher, dass auf dem Gerät des Benutzers mindestens die iOS-Version 8.0 ausgeführt wird.|
|UserLicenseTypeInvalid|Sie können Ihr mobiles Gerät nicht registrieren, da Ihr Benutzerkonto noch kein Mitglied einer erforderlichen Benutzergruppe ist.<br /><br />Wenden Sie sich an Ihre IT-Administratoren, und teilen Sie ihnen mit, dass die Meldung **UserLicenseTypeInvalid** beim Versuch angezeigt wird, Ihr mobiles Gerät zu registrieren, und informieren Sie sie über die Lösung in dieser Tabelle.|Bevor Benutzer ihre Geräte registrieren können, müssen sie Mitglied der richtigen Benutzergruppe sein. Diese Meldung bedeutet, dass der Benutzer den falschen Lizenztyp für die festgelegte Autorität für die Verwaltung mobiler Geräte hat. Beispielsweise wird dieser Fehler angezeigt, wenn Intune als Autorität für die Verwaltung mobiler Geräte festgelegt wurde und der Benutzer eine System Center 2012 R2 Configuration Manager-Lizenz verwendet.<br /><br />In den folgenden Abschnitten erhalten Sie weitere Informationen:<br /><br />Weitere Informationen finden Sie unter [Einrichten der iOS- und Mac-Geräteverwaltung](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) und im Abschnitt über das Einrichten von Benutzern in [Synchronisieren von Active Directory und Hinzufügen von Benutzern zu Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) und unter [Erstellen von Gruppen zum Organisieren von Benutzern und Geräten](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|MdmAuthorityNotDefined|Ihr IT-Administrator muss die Verwaltung mobiler Geräte in Ihrem Unternehmen einrichten.<br /><br />Wenden Sie sich an Ihre IT-Administratoren, und teilen Sie ihnen mit, dass die Meldung **MdmAuthorityNotDefined** beim Versuch angezeigt wird, Ihr mobiles Gerät zu registrieren, und informieren Sie sie über die Lösung in dieser Tabelle.|Die Autorität für die Verwaltung mobiler Geräte wurde in Intune nicht festgelegt.<br /><br />Lesen Sie Punkt 1 im Abschnitt „Schritt 5: Registrieren mobiler Geräte und Installieren einer App“ unter [Schritte zum Durchführen einer 30-tägigen Evaluierung von Intune](/Intune/Understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune).|



<!--HONumber=Jan17_HO4-->


