---
title: "Abkoppeln von Geräten | Microsoft Intune"
description: "Intune unterstützt sowohl die selektive als auch die vollständige Zurücksetzung, um das Gerät aus der Intune-Verwaltung zu entfernen, indem die Richtlinie und das Unternehmensportal entfernt werden."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7bea7ba4ef59c6b1400414b59456e19dc1c152fb
ms.openlocfilehash: ad5e9453f8132d383f8c23886e48505769c7f44b


---

# Abkoppeln von Geräten von der Intune-Verwaltung

Unabhängig davon, ob Geräte Unternehmenseigentum sind oder den Mitarbeitern persönlich gehören – es kommt der Zeitpunkt, an dem ein verwaltetes Gerät aus Intune-Verwaltung entfernt werden muss. Das Abkoppeln von Geräten ist recht einfach. Sie können Geräte, die als mobile Geräte verwaltet werden, wahlweise selektiv oder vollständig zurücksetzen. Außerdem können Sie mit Intune-Clientsoftware verwaltete PCs abkoppeln.

## Löschen von Daten und Apps von Geräten
Sowohl beim selektiven als auch beim vollständigen Zurücksetzen wird das Gerät aus der Intune-Verwaltung entfernt, indem die zugehörige Richtlinie und das Unternehmensportal entfernt werden. Dies bedeutet, dass das Gerät nicht mehr über die notwendigen Informationen zur Anmeldung bei Unternehmensressourcen wie Microsoft SharePoint, E-Mails oder Office 365 verfügt.

[Selektives Zurücksetzen](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) ist die bevorzugte Maßnahme für Mitarbeiter, die ihre eigenen Geräte bei Intune registriert haben, da persönliche Informationen auf dem Gerät nicht betroffen sind. Es werden nur Unternehmensdaten entfernt.

Geräte, die einem neuen Verwendungszweck zugewiesen werden sollen, können Sie auch [vollständig zurücksetzen](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe), um sie auf die Werks- bzw. Standardeinstellungen zurückzusetzen.

## So löschen Sie Geräte im Azure Active Directory-Portal

1.  Melden Sie sich mit den Anmeldeinformationen Ihrer Organisation bei [http://aka.ms/accessaad](http://aka.ms/accessaad) oder [https://portal.office.com](https://portal.office.com) an, und wählen Sie dann **Admin Center** &gt; **Azure AD** aus.

2.  Erstellen Sie ein Azure-Abonnement, wenn Sie noch keins besitzen. Hierzu sollte keine Kreditkarte oder Zahlung erforderlich sein, wenn Sie ein gebührenpflichtiges Konto besitzen (klicken Sie auf den Abonnementlink **Ihr kostenloses Azure Active Directory registrieren** ).

4.  Wählen Sie zuerst **Active Directory** und dann Ihre Organisation aus.

5.  Wählen Sie die Registerkarte **Benutzer** aus.

6.  Wählen Sie den Benutzer aus, dessen Geräte Sie löschen möchten.

7.  Klicken Sie auf **Geräte**.

8.  Wählen Sie die gewünschten Geräte aus, und klicken Sie auf Sie **Gerät löschen**. Das Gerät wird bei der nächsten Synchronisierung mit Active Directory gelöscht. Dies geschieht in der Regel innerhalb von 4 Stunden. Nach der Synchronisierung wird das Gerät aus der Verwaltung entfernt. Dadurch wird dieses Gerät beim Gerätegrenzwert für diesen Benutzer nicht mehr berücksichtigt.

## Abkoppeln von verwalteten Computern
Computer, die mit Intune-Clientsoftware verwaltet werden, können aus der Intune-Verwaltungskonsole entfernt werden. Dadurch wird gleichzeitig die Clientsoftware deinstalliert, und die Intune-Richtlinien werden vom Computer gelöscht. Hier erhalten Sie Informationen zum [Abkoppeln von mit der Intune-Clientsoftware verwalteten Computer](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#retire-a-computer.md).

## Blockieren des Zugriffs auf ein Gerät
Wenn ein Gerät verloren gegangen ist oder wenn ein Gerät abgekoppelt werden muss, weil ein Mitarbeiter Ihr Unternehmen verlassen hat, ohne firmeneigene Hardware zurückzugeben, können Sie für das Gerät auch [die Kennung zurücksetzen und es remote sperren](use-remote-lock-and-passcode-reset-in-microsoft-intune.md). Dadurch wird verhindert, dass Firmeninformationen missbräuchlich verwendet werden, obwohl Sie das Gerät möglicherweise als Verlust abschreiben müssen.

Sie sollten auch die Lizenz für das Intune-Benutzerkonto des Mitarbeiters widerrufen. Gleichzeitig wird die Lizenz freigegeben, und Sie können sie einem neuen Benutzerkonto zuweisen.

## Außerbetriebnehmen von Hardware
Manchmal ist es das Gerät selbst, das das Ende seines Lebenszyklus erreicht hat. In solchen Fällen werden durch das [Zurücksetzen auf die Werkseinstellungen](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) alle Daten vom Gerät und das Gerät aus Intune entfernt. Dann können Sie die Hardware gemäß der Unternehmensrichtlinie beseitigen.

### Weitere Informationen:
[Schützen von Daten durch vollständiges oder selektives Zurücksetzen](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)



<!--HONumber=Aug16_HO2-->


