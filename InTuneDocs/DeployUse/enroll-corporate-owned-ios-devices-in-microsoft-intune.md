---
title: "Registrieren firmeneigener iOS-Geräte | Microsoft Intune"
description: "Registrieren firmeneigener iOS-Geräte mithilfe des Apple Device Enrollment Program (DEP) oder Apple Configurator"
keywords: 
author: NathBarn
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8a124eb41789053451e0c709188430b1e043d435
ms.openlocfilehash: 872be93241c84a8334e4415f00b1383da7b15a61


---

# Registrieren firmeneigener iOS-Geräte in Microsoft Intune
Microsoft Intune unterstützt die Registrierung von firmeneigenen iOS-Geräten mithilfe des Apple-Programms zur Geräteregistrierung (Device Enrollment Program, DEP) oder des Tools [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017), das auf einem Mac-Computer ausgeführt wird.

Sie können firmeneigene iOS-Geräte auf drei Arten registrieren:

-   **Apple Configurator**: iOS-Geräte können durch Exportieren eines Unternehmensregistrierungsprofils und anschließendem Verbinden dieser mobilen Geräte mit einem Mac, auf dem Apple Configurator ausgeführt wird, registriert werden. Apple Configurator unterstützt zwei Formen der Registrierung:

    - **Setup-Assistent für die Registrierung** : Setzt das Gerät auf die Werkseinstellungen zurück und bereitet es für die Einrichtung durch den neuen Benutzer des Geräts vor. Bei dieser Methode muss der Administrator das iOS-Gerät per USB mit einem Macintosh-Computer verbinden, auf dem Apple Configurator ausgeführt wird, um die Registrierung vorzukonfigurieren. Die Geräte werden dann an ihre Benutzer übergeben, die den Setup-Assistenten ausführen, das Gerät mit den Anmeldeinformationen ihres Geschäfts- oder Schulkontos konfigurieren und den Registrierungvorgang abschließen. [Registrieren von iOS-Geräten mithilfe von Apple Configurator und Setup-Assistent](ios-setup-assistant-enrollment-in-microsoft-intune.md)

    - **Direkte Registrierung:** Erstellt eine Apple Configurator-kompatible Datei zur Verwendung während der Vorbereitung des Geräts. Das registrierte Gerät wird nicht auf die Werkseinstellungen zurückgesetzt, aber ist keinem Benutzer zugewiesen. Bei dieser Methode muss der Administrator das iOS-Gerät per USB mit einem Macintosh-Computer verbinden, auf dem Apple Configurator ausgeführt wird, um das Gerät zu registrieren. [Registrierung von iOS-Geräte mit der Option „Direkte Registrierung“ von Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md)

-   **Apple-Programm zur Geräteregistrierung (Device Enrollment Program, DEP):** Stellt Geräten, die über das Apple-Programm zur Geräteregistrierung erworben wurden, ein Registrierungsprofil per Funk bereit. Wenn der Benutzer auf dem Gerät den Setup-Assistenten ausführt, wird das Gerät bei Intune registriert.  Die Registrierung von Geräten über DEP kann von Benutzern nicht rückgängig gemacht werden. [Registrieren von iOS-Geräten, die über das Apple-Programm zur Geräteregistrierung erworben wurden](ios-device-enrollment-program-in-microsoft-intune.md)

## Benutzeraffinität zu firmeneigenen iOS-Geräten über das Unternehmensportal

Auf mit Benutzeraffinität konfigurierten Geräte kann die Unternehmensportal-App installiert und ausgeführt werden, um Apps herunterzuladen und Geräte zu verwalten. Sobald Benutzer ihre Geräte erhalten haben, müssen sie verschiedene zusätzliche Schritte ausführen, um den Setup-Assistenten abzuschließen und die Unternehmensportal-App zu installieren.

Registrieren von firmeneigenen iOS-Geräten mit Benutzeraffinität
1. Wenn Benutzer ihr Gerät einschalten, werden sie aufgefordert, den Setup-Assistenten zu durchlaufen. Während des Setups werden Benutzer zur Eingabe ihrer Anmeldeinformationen aufgefordert. Sie müssen die Anmeldeinformationen (d. h. den eindeutigen persönlichen Namen) verwenden, die ihrem Abonnement in Intune zugeordnet sind.

2. Während des Setups werden Benutzer zur Eingabe einer Apple ID aufgefordert. Eine Apple ID muss angegeben werden, damit das Gerät das Unternehmensportal installieren kann. Eine Apple ID kann auch nach Abschluss des Setups im iOS-Einstellungsmenü angegeben werden.

3. Nach Abschluss des Setups muss auf dem Gerät die Unternehmensportal-App aus dem App Store installiert werden, z. B. die Unternehmensportal-App.

4. Der Benutzer kann sich nun mit dem eindeutigen persönlichen Namen, der beim Setup des Geräts verwendet wurde, am Unternehmensportal anmelden.

5. Nach der Anmeldung wird der Benutzer aufgefordert, sein Gerät zu registrieren. Der erste Schritt besteht im Identifizieren des Geräts. Die App zeigt eine Liste mit iOS-Geräten, die bereits vom Unternehmen registriert und dem Intune-Konto des Benutzers zugewiesen wurden. Wählen Sie das entsprechende Gerät aus.

  Wenn das Gerät nicht bereits vom Unternehmen registriert wurde, wählen Sie „Neues Gerät“, um den standardmäßigen Registrierungsvorgang fortzusetzen.

6. Auf dem nächsten Bildschirm muss der Benutzer die Seriennummer des neuen Geräts bestätigen. Der Benutzer kann auf den Link „Seriennummer bestätigen“ tippen, um zum Bestätigen der Seriennummer die App „Einstellungen“ zu starten. Der Benutzer muss dann die letzten 4 Zeichen der Seriennummer in die Unternehmensportal-App eingeben.

  Dieser Schritt dient zum Überprüfen, ob das Gerät das vom Unternehmen in Intune registrierte Gerät ist. Wenn die Seriennummer des Geräts nicht übereinstimmt, wurde der falsche Gerät ausgewählt. Kehren Sie zum vorherigen Bildschirm zurück, und wählen Sie ein anderes Gerät aus.

7. Nachdem die Seriennummer überprüft wurde, wird die Unternehmensportal-App zur Unternehmensportal-Website umgeleitet, um die Registrierung abzuschließen. Anschließend wird der Benutzer aufgefordert, zur App zurückzukehren.

8. Die Registrierung ist damit abgeschlossen. Sie können nun die Funktionen des Geräts in vollem Umfang nutzen.

### Informationen zu unternehmenseigenen verwalteten Geräten ohne Benutzeraffinität

Ohne Benutzeraffinität konfigurierte Geräte unterstützen nicht das Unternehmensportal und dürfen nicht die App installieren. Das Unternehmensportal ist für Benutzer gedacht, die über Anmeldeinformationen ihres Unternehmens verfügen und Zugriff auf personalisierte Unternehmensressourcen (z. B. E-Mail) benötigen. Geräte, die ohne Benutzeraffinität registriert wurden, bieten nicht die Anmeldung dedizierter Benutzer. Kiosk-, Verkaufsstellen- (POS-) oder gemeinsam genutzte Geräte sind typisch Anwendungsfälle für Geräte, die ohne Benutzeraffinität registriert werden. Wenn Benutzeraffinität erforderlich ist, muss vor der Registrierung des Geräts in dessen Registrierungsprofil Benutzeraffinität ausgewählt worden sein. Zum Ändern des Affinitätsstatus eines Geräts müssen Sie das Gerät deaktivieren und erneut registrieren.



### Weitere Informationen:
[Vorbereiten der Registrierung von Geräten in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


