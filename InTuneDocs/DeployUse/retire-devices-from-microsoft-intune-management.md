---
# required metadata

title: Abkoppeln von Geräten | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Abkoppeln von Geräten von der Intune-Verwaltung

Unabhängig davon, ob Geräte Unternehmenseigentum sind oder den Mitarbeitern persönlich gehören – es kommt der Zeitpunkt, an dem ein verwaltetes Gerät von der Verwaltung in Intune abgekoppelt werden muss. Der Abkopplungsprozess für Geräte ist verhältnismäßig einfach: Sie setzen das Gerät selektiv oder vollständig zurück.
## Löschen von Daten und Apps von Geräten
Sowohl beim selektiven als auch beim vollständigen Zurücksetzen wird das Gerät aus der Intune-Verwaltung entfernt, indem die zugehörige Richtlinie und das Unternehmensportal entfernt werden. Dies bedeutet, dass das Gerät nicht mehr über die notwendigen Informationen zur Anmeldung bei Unternehmensressourcen wie Microsoft SharePoint, E-Mails oder Office 365 verfügt.

[Selektives Zurücksetzen](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) ist die bevorzugte Maßnahme für Mitarbeiter, die ihre eigenen Geräte bei Intune registriert haben, da persönliche Informationen auf dem Gerät nicht betroffen sind. Es werden nur Unternehmensdaten entfernt.

Firmeneigene Geräte können Sie auch [vollständig zurücksetzen](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe), um sie auf die Werkseinstellungen zurückzusetzen.

## Widerrufen des Zugriffs auf das Unternehmensnetzwerk
Falls Sie ein Gerät abkoppeln, weil ein Mitarbeiter Ihr Unternehmen verlässt und die firmeneigene Hardware nicht zurückgegeben hat, können Sie das Gerät auch [remote sperren](use-remote-lock-and-passcode-reset-in-microsoft-intune.md). Dadurch wird verhindert, dass Firmeninformationen und Firmenhardware missbräuchlich verwendet werden, obwohl Sie das Gerät möglicherweise als Verlust abschreiben müssen.

Sie sollten auch die Lizenz für das Intune-Benutzerkonto des Mitarbeiters widerrufen. Dadurch wird die Lizenz freigegeben, und Sie können sie einem neuen Benutzerkonto zuweisen.

## Außerbetriebnehmen von Hardware
Manchmal ist es das Gerät selbst, das das Ende seines Lebenszyklus erreicht hat. In solchen Fällen werden durch das [Zurücksetzen auf die Werkseinstellungen](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) alle Daten vom Gerät und das Gerät aus Intune entfernt. Dann können Sie die Hardware gemäß der Unternehmensrichtlinie beseitigen.

### Weitere Informationen:
[Schützen von Daten durch vollständiges oder selektives Zurücksetzen](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)


<!--HONumber=May16_HO1-->


