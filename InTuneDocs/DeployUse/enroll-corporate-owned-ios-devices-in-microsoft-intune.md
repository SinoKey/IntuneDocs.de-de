---
# required metadata

title: Registrieren firmeneigener iOS-Geräte in Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Registrieren firmeneigener iOS-Geräte in Microsoft Intune
Microsoft Intune unterstützt die Registrierung von firmeneigenen iOS-Geräten mithilfe des Apple-Programms zur Geräteregistrierung (Device Enrollment Program, DEP) oder des Tools [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017), das auf einem Mac-Computer ausgeführt wird.

Sie können firmeneigene iOS-Geräte auf drei Arten registrieren:

-   **Setup-Assistent für die Registrierung** : Setzt das Gerät auf die Werkseinstellungen zurück und bereitet es für die Einrichtung durch den neuen Benutzer des Geräts vor. Bei dieser Methode muss der Administrator das iOS-Gerät per USB mit einem Macintosh-Computer verbinden, auf dem Apple Configurator ausgeführt wird, um die Registrierung vorzukonfigurieren. Die Geräte werden dann an ihre Benutzer übergeben, die den Setup-Assistenten ausführen, das Gerät mit den Anmeldeinformationen ihres Geschäfts- oder Schulkontos konfigurieren und den Registrierungvorgang abschließen. [Registrieren von iOS-Geräten mithilfe von Apple Configurator und Setup-Assistent](ios-setup-assistant-enrollment-in-microsoft-intune.md)

-   **Direkte Registrierung:** Erstellt eine Apple Configurator-kompatible Datei zur Verwendung während der Vorbereitung des Geräts. Das registrierte Gerät wird nicht auf die Werkseinstellungen zurückgesetzt, aber ist keinem Benutzer zugewiesen. Bei dieser Methode muss der Administrator das iOS-Gerät per USB mit einem Macintosh-Computer verbinden, auf dem Apple Configurator ausgeführt wird, um das Gerät zu registrieren. [Registrierung von iOS-Geräte mit der Option „Direkte Registrierung“ von Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md)

-   **Apple-Programm zur Geräteregistrierung (Device Enrollment Program, DEP):** Stellt Geräten, die über das Apple-Programm zur Geräteregistrierung erworben wurden, ein Registrierungsprofil per Funk bereit. Wenn der Benutzer auf dem Gerät den Setup-Assistenten ausführt, wird das Gerät bei Intune registriert.  Die Registrierung von Geräten über DEP kann von Benutzern nicht rückgängig gemacht werden. [Registrieren von iOS-Geräten, die über das Apple-Programm zur Geräteregistrierung erworben wurden](ios-device-enrollment-program-in-microsoft-intune.md)




### Weitere Informationen:
[Vorbereiten der Registrierung von Geräten in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


