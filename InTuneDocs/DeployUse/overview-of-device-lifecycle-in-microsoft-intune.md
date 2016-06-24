---
# required metadata

title: Übersicht über den Gerätelebenszyklus | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f6051fa7-133f-4712-86a5-e5f5bc5ab3c7

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Übersicht über den MDM-Lebenszyklus (mobile Geräteverwaltung)

Der Intune-Lebenszyklus für Geräte beginnt zunächst mit dem Registrieren eines Geräts und durchläuft dann verschiedene Schritte, die dann abgeschlossen sind, wenn das Gerät nicht mehr benötigt wird.

![Der Gerätelebenszyklus](./media/device-lifecycle.png "the Intune device lifecycle")

## Registrieren
Die heutigen Strategien zur Verwaltung mobiler Geräte (Mobile Device Management, MDM) befassen sich mit verschiedenen Mobiltelefonen, Tablets und PCs (iOS, Android, Windows und Mac OS X). Wenn Sie das Gerät verwalten müssen, was bei unternehmenseigenen Geräten im Allgemeinen der Fall ist, besteht der erste Schritt darin, die [Geräteregistrierung einzurichten](enroll-devices-in-microsoft-intune.md). Durch das Registrieren bei Intune (MDM) oder durch [Installieren der Intune-Clientsoftware](manage-windows-pcs-with-microsoft-intune.md) können Sie auch Windows-PCs verwalten.

## Konfigurieren
Das Registrieren Ihrer Geräte ist nur der erste Schritt. Um alle Intune-Angebote zu nutzen und um sicherzustellen, dass die Geräte sicher und mit Unternehmensstandards kompatibel sind, können Sie aus einer Vielzahl von **Richtlinien** auswählen, mit denen Sie nahezu jeden Aspekt des Betriebs von verwalteten Geräten konfigurieren können. Sollen Benutzer beispielsweise Kennwörter für Geräte verwenden, die Unternehmensdaten enthalten? Sie können festlegen, dass ein Kennwort erforderlich ist. Haben Sie ein Unternehmens-WLAN? Sie können es automatisch konfigurieren. Hier sind die verfügbaren Typen von Konfigurationsoptionen aufgeführt:

- [**Konfigurationsrichtlinien**](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md): Mit diesen Richtlinien können Sie konfigurieren, wie die Features und Funktionen der von Ihnen verwalteten Geräten arbeiten. Beispielsweise können Sie die Verwendung eines Kennworts auf Windows Phones verlangen oder die Verwendung der Kamera auf iPhones deaktivieren.
- [**Richtlinien für den Zugriff auf Unternehmensressourcen**](enable-access-to-company-resources-with-microsoft-intune.md): Wenn Sie Ihren Benutzern den Zugriff auf ihre Arbeit über ihre persönlichen Geräte gestatten, stellt Sie dies vor gewisse Herausforderungen. Wie gewährleisten Sie beispielsweise, dass alle Geräte, die auf Unternehmens-E-Mail zugreifen müssen, ordnungsgemäß konfiguriert sind? Wie können Sie sicherstellen, dass Benutzer über eine VPN-Verbindung auf das Unternehmensnetzwerk zugreifen können, ohne die häufig komplexen erforderlichen Einstellungen kennen zu müssen? Intune kann Sie entlasten, indem die von Ihnen verwalteten Geräte automatisch für den Zugriff auf allgemeine Unternehmensressourcen konfiguriert werden.
- [**Windows-PC-Verwaltungsrichtlinien (mit der Intune-Clientsoftware)**](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md): Auch wenn Ihnen durch die Registrierung von Windows-PCs bei Intune die meisten Verwaltungsfunktionen für Geräte bereitgestellt werden, unterstützt Intune weiterhin das Verwalten von Windows-PCs über die Intune-Clientsoftware. Wenn Sie Informationen über einige Aufgaben benötigen, die Sie mit PCs ausführen können, beginnen Sie hier.

## Schützen
In der modernen IT-Welt ist der Schutz von Geräten vor unbefugtem Zugriff eine der wichtigsten Aufgaben, die Sie erfüllen müssen. Zusätzlich zu den Elementen im Schritt **Konfigurieren** des Gerätelebenszyklus stellt Intune weitere Funktionen bereit, mit denen Sie von Ihnen verwaltete Geräte vor unbefugtem Zugriff oder böswilligen Angriffen schützen können:
- [**Mehrstufige Authentifizierung**](protect-windows-devices-with-multi-factor-authentication.md): Durch das Hinzufügen einer zusätzlichen Authentifizierungsebene zu den Benutzeranmeldungen können Sie Geräte noch sicherer machen. Windows, Windows Phone und Windows Mobile-Geräte bieten die mehrstufige Authentifizierung, die eine zweite Authentifizierungsebene wie einen Telefonanruf oder eine SMS erfordert, bevor Benutzer Zugriff erhalten.
- [**Microsoft Passport-Einstellungen**](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md): Microsoft Passport ist eine alternative Anmeldemethode, die Benutzern das Verwenden einer *Geste*, z. B. Fingerabdruck oder Windows Hello, ermöglicht, um sich ohne Kennwort anzumelden.
- [**Richtlinien zum Schutz von Windows-PCs (mit der Intune-Clientsoftware)**](policies-to-protect-windows-pcs-in-microsoft-intune.md): Wenn Sie Windows-PCs mit der Intune-Clientsoftware verwalten, stehen Richtlinien zur Verfügung, mit denen Sie die Einstellungen für Endpoint Protection, Softwareupdates und Windows-Firewall auf von Ihnen verwalteten PCs steuern können.

## Außerkraftsetzen
Wenn ein Gerät verloren geht, gestohlen wird oder ersetzt werden muss, oder wenn Benutzer in eine andere Position wechseln, ist es in der Regel an der Zeit, das Gerät [abzukoppeln oder zurückzusetzen](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md). Hierzu gibt es verschiedene Möglichkeiten, angefangen beim Zurücksetzen des Geräts über das Entfernen des Geräts aus der Verwaltung bis hin zum Löschen der darauf befindlichen Unternehmensdaten.


<!--HONumber=May16_HO2-->


