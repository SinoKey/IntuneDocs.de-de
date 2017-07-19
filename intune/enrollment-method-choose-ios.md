---
title: "Auswählen der Registrierungsmethode für iOS-Geräte in Intune"
titleSuffix: Intune on Azure
description: "Erfahren Sie, wie Sie die Registrierung von iOS-Geräten in Microsoft Intune einrichten."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 092f582cf30210858bd8cdd3879edfa873523ccb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2017
---
# <a name="choose-how-to-enroll-ios-and-macos-devices"></a>Auswählen der Registrierungsmethode für iOS- und masOS-Geräte

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

In diesem Thema werden die Methoden beschrieben, über die ein IT-Administrator die Registrierung von iOS-Geräten in Intune aktivieren kann.

Ihre Entscheidung, welche Methode zum Registrieren von iOS-Geräten verwendet wird, sollte auf den folgenden Informationen basieren. Alle der folgenden Methoden mit Ausnahme von BYOD sind für die Registrierung von firmeneigenen Geräten ausgelegt.

**Voraussetzung:** Ein [Apple Push Notification Service-Zertifikat](apple-mdm-push-certificate-get.md) ist erforderlich.

## <a name="user-owned-ios-devices-byod"></a>iOS-Gerät im Besitz des Benutzers (BYOD)

Wenn Benutzer ihre privaten Geräte (BYOD, Bring Your Own Device) registrieren möchten, können Sie die Unternehmensportal-App für iOS aus dem App Store herunterladen und die Registrierungsanweisungen in der App befolgen. Nach der Registrierung können Benutzer eine Verbindung mit dem Unternehmensnetzwerk herstellen, der Domäne oder Azure Active Directory beitreten und Zugriff auf Unternehmensressourcen erhalten. Zum Ermöglichen von BYOD ist nur ein [Apple Push Notification Service-Zertifikat](apple-mdm-push-certificate-get.md) erforderlich. Sie können die Registrierung privater iOS-Geräte auch blockieren. Unter [Festlegen von Gerätetypbeschränkungen](enrollment-restrictions-set.md) finden Sie Anweisungen.

## <a name="user-owned-macos-devices-byod"></a>macOS-Geräte im Besitz des Benutzers (BYOD)

Sie können die Registrierung von macOS-Geräten aktivieren. Zum Ermöglichen der macOS-Registrierung ist nur ein [Apple Push Notification Service-Zertifikat](apple-mdm-push-certificate-get.md) erforderlich. Weitere Informationen finden Sie unter [Registrieren von macOS-Geräten](./macos-enroll.md).

## <a name="enrollment-program-with-apple"></a>Apple-Registrierungsprogramm
Apple bietet Programme zum Erwerb von Geräten, die eine Infrastruktur für die Registrierung und Verwaltung von Geräten umfassen. Über eines dieser Programme erworbene Geräte können in einem drahtlosen Massenvorgang registriert werden, indem Geräteseriennummern für die Intune-Verwaltung zugewiesen werden.

- **Programm zur Geräteregistrierung (Device Enrollment Program, DEP)**: Das Programm zur Geräteregistrierung von Apple für Unternehmen. Weitere Informationen finden Sie unter [Registrieren von iOS-Geräten mithilfe des Programms zur Geräteregistrierung](device-enrollment-program-enroll-ios.md).
- **Apple School Manager**: Das Programm zur Geräteregistrierung von Apple für Bildungseinrichtungen. Weitere Informationen finden Sie unter [Aktivieren der iOS-Geräteregistrierung mit Apple School Manager](apple-school-manager-set-up-ios.md).

## <a name="apple-configurator"></a>Apple Configurator

Sie können iOS-Geräte registrieren, indem Sie ein Unternehmensregistrierungsprofil exportieren und dies mobilen Geräte anschließend mit einem Mac verbinden, auf dem Apple Configurator ausgeführt wird. Apple Configurator unterstützt zwei Formen der Registrierung:

- **Setup-Assistent für die Registrierung**: Setzt das Gerät auf die Werkseinstellungen zurück und bereitet es für die Einrichtung durch den neuen Benutzer des Geräts vor. Bei dieser Methode muss der Administrator das iOS-Gerät per USB mit einem Macintosh-Computer verbinden, auf dem Apple Configurator ausgeführt wird, um die Registrierung vorzukonfigurieren. Die Geräte werden dann an ihre Benutzer übergeben, die nach dem ersten Start des Geräts den Setup-Assistenten ausführen. Dieser Prozess konfiguriert das Gerät mit den Anmeldeinformationen Ihres Geschäfts- oder Schulkontos und schließt den Registrierungsvorgang ab. Weitere Informationen finden Sie unter [Registrieren von iOS-Geräten mithilfe von Apple Configurator und Setup-Assistent](apple-configurator-setup-assistant-enroll-ios.md).

- **Direkte Registrierung**: Erstellt eine Apple Configurator-kompatible Datei zur Verwendung während der Vorbereitung des Geräts. Das registrierte Gerät wird nicht auf die Werkseinstellungen zurückgesetzt und ist keinem Benutzer zugewiesen. Um Geräte anzumelden, muss der Administrator das iOS-Gerät per USB mit einem Macintosh-Computer verbinden, auf dem Apple Configurator ausgeführt wird. Weitere Informationen finden Sie unter [Registrierung von iOS-Geräte mit der Option „Direkte Registrierung“ von Apple Configurator](apple-configurator-direct-enroll-ios.md).

## <a name="use-the-device-enrollment-program-dep"></a>Verwenden des Geräteregistrierungsprogramms (Device Enrollment Program, DEP)

Auf über das DEP erworbenen Geräten wird ein Registrierungsprofil „Drahtlos“ bereitgestellt. Wenn ein Benutzer beim ersten Start des Geräts den Setup-Assistenten ausführt, wird das Gerät bei Intune registriert. Weitere Informationen finden Sie unter [Registrieren von iOS-Geräten mithilfe des Programms zur Geräteregistrierung](device-enrollment-program-enroll-ios.md).

## <a name="use-the-device-enrollment-manager-dem"></a>Verwenden des Geräteregistrierungs-Managers
Der Geräteregistrierungs-Manager ist ein allgemeines Benutzerkonto, mit dem bis zu 1.000 Geräte registriert und verwaltet werden können. Bei mit dem Geräteregistrierungs-Manager verwalteten Geräten gibt es keine Benutzeraffinität, weshalb diese Geräte keinen Besitzer haben. Sie erteilen einem Intune-Benutzer Berechtigungen des Geräteregistrierungs-Managers, um ihm diese Funktionen zur Verfügung zu stellen. Jedes Gerät, das der Geräteregistrierungs-Manager-Benutzer registriert, verwendet eine Intune-Lizenz. Weitere Informationen finden Sie unter [Registrieren von Geräten mithilfe des Geräteregistrierungs-Managers](device-enrollment-manager-enroll.md).
