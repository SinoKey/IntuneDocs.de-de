---
title: "Was geschieht, wenn Sie die Registrierung Ihres Geräts bei Intune aufheben? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47e03edb-0c57-4e25-8e89-4a1069267b8c
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1244d931d1bd3db012fbcfe0bd055d1fd4f2d88a
ms.openlocfilehash: f0108b884439aac9661c9f36f85b47d80209d155


---


# Was geschieht, wenn Sie die Registrierung Ihres Geräts bei Intune aufheben?

Klicken Sie im Abschnitt „Inhalt dieses Artikels“ weiter oben auf den Link, der dem Typ Ihres Geräts entspricht, um weitere Informationen zu erhalten.

- [Windows 10 Mobile, 8.1, Windows 8, Windows 7, Vista](#windows-10-mobile--8-1,-windows-8,-windows-7,-vista)
- [Windows 10, Windows 8.1 oder Windows Phone 8](#windows-10--windows-8-1-or-windows-phone-8)
- [Windows RT, das Windows 8.1 oder Windows RT ausführt](#windows-rt-running-windows-8-1-or-windows-rt)


## Windows 10, Windows 8.1, Windows 8, Windows 7, Vista

-   Ihr Gerät wird nicht mehr im Unternehmensportal angezeigt, und Sie können über das Unternehmensportal keine Apps mehr installieren.

-   Wenn die Intune-Clientsoftware installiert ist, wird diese von Ihrem Computer entfernt.

-   Die Intune Endpoint Protection-Software wird von Ihrem Computer entfernt. Wenn auf dem Computer eine andere Virenschutzsoftware installiert ist und diese deaktiviert wurde, wird sie unter Umständen nach dem Entfernen von Intune Endpoint Protection wieder aktiviert. Sie sollten Ihren Computer nach dem Entfernen aus dem Unternehmensportal überprüfen.

    > [!IMPORTANT]
    > Wenn die andere Virenschutzsoftware nicht wieder aktiviert wird oder keine andere Virenschutzsoftware installiert ist, bleibt der Computer unter Umständen anfällig für Viren und Schadsoftware.

-   Alle Einstellungen, die beim Hinzufügen des Geräts auf diesem geändert wurden (z. B. das Deaktivieren der Kamera, werden unwirksam).

-   Automatische Softwareupdates und Updates der Antivirensoftware vom Intune-Dienst werden nicht mehr auf dem Computer empfangen. Der Computer kann jedoch je nach Konfiguration weiterhin Updates von Windows Server Update Services, Windows Update oder Microsoft Update empfangen.

Zusätzlich für Windows 8.1:

-   Sie können keine Unternehmens-Apps und Unternehmensdaten mehr auf dem Gerät verwenden.

-   In einigen Mail-Apps wie Windows Mail kann nicht mehr auf Unternehmens-E-Mails zugegriffen werden, die auf dem Gerät gespeichert sind.

-   Möglicherweise können Sie keine Verbindung zum Unternehmensnetzwerk über WiFi oder ein virtuelles privates Netzwerk herstellen.

-   Unter Umständen haben Sie auf dem Gerät keinen Zugriff mehr auf einige Unternehmensressourcen, z. B. Dateifreigaben oder interne Websites.

## Windows 10 Mobile, Windows Phone 8.1 oder Windows Phone 8

-   Die Unternehmensportal-App wird auf Ihrem Gerät deinstalliert, d. h. das Gerät wird nicht mehr im Unternehmensportal angezeigt, und Sie sind dann nicht mehr in der Lage, Apps aus der Unternehmensportal-App oder von der Unternehmensportal-Website zu installieren.

-   Sie können keine Unternehmens-Apps und Unternehmensdaten mehr auf dem Gerät verwenden.

-   Alle Einstellungen, die beim Hinzufügen des Geräts auf diesem geändert wurden, z. B. das Deaktivieren der Kamera oder die Anforderung einer bestimmten Kennwortlänge, werden unwirksam.

    > [!IMPORTANT]
    > Die einzige Ausnahme sind die Verschlüsselungsrichtlinien, die weiterhin wirksam sind. Wenn in Ihrer Unternehmensrichtlinie vorgeschrieben war, dass Windows Phone verschlüsselt sein muss, können Sie Ihr Telefon nur noch entschlüsseln, indem Sie es auf Windows Phone über das Menü **Einstellungen** zurücksetzen.

## Windows RT, das Windows 8.1 oder Windows RT ausführt

-   Die Unternehmensportal-App wird auf Ihrem Gerät deinstalliert, d. h. das Gerät wird nicht mehr im Unternehmensportal angezeigt, und Sie sind dann nicht mehr in der Lage, Apps aus der Unternehmensportal zu installieren.

-   Sie können keine Unternehmens-Apps und Unternehmensdaten mehr auf dem Gerät verwenden.

-   Alle Einstellungen, die beim Hinzufügen des Geräts auf diesem geändert wurden, z. B. das Deaktivieren der Kamera oder die Anforderung einer bestimmten Kennwortlänge, werden unwirksam.

-   Möglicherweise können Sie keine Verbindung mehr zum Unternehmensnetzwerk über WiFi oder ein virtuelles privates Netzwerk herstellen.

-   Unter Umständen haben Sie auf dem Gerät keinen Zugriff mehr auf einige Unternehmensressourcen, z. B. Dateifreigaben oder interne Websites.

-   In einigen Mail-Apps wie Windows Mail kann nicht mehr auf Unternehmens-E-Mails zugegriffen werden, die auf dem Gerät gespeichert sind.

Wenn Sie Ihr Windows RT-Gerät entfernen, geschieht Folgendes:

-   Die Unternehmensportal-App wird auf Ihrem Gerät deinstalliert, d. h. das Gerät wird nicht mehr im Unternehmensportal angezeigt, und Sie sind dann nicht mehr in der Lage, Apps aus der Unternehmensportal zu installieren.

-   Sie können keine Unternehmens-Apps und Unternehmensdaten mehr auf dem Gerät verwenden.

-   Alle Einstellungen, die beim Hinzufügen des Geräts auf diesem geändert wurden, z. B. das Deaktivieren der Kamera oder die Anforderung einer bestimmten Kennwortlänge, werden unwirksam.

Wenn Sie Fragen haben, wenden Sie sich an Ihren IT-Administrator. Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](http://portal.manage.microsoft.com).

### Weitere Informationen:
[Verwenden Ihres Windows-Geräts mit Intune](using-your-windows-device-with-intune.md)


<!--HONumber=Jun16_HO4-->


