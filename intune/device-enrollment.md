---
title: "Was ist die Microsoft Intune Geräteregistrierung?"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Informationen zur Registrierung für iOS-, Android- und Windows-Geräte."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 57bad4be991b61fe5212d340ab8d89cb6af3b0f7
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---

# <a name="what-is-device-enrollment"></a>Was ist die Geräteregistrierung?
[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Dieses Thema beschreibt die Registrierung und die verschiedenen Methoden zum Registrieren von mobilen Geräten in der Intune-Verwaltung.

Sie registrieren Geräte in Intune, um diese Geräte verwalten zu können. Diese Funktion wird in der Intune-Dokumentation als Verwaltung mobiler Geräte (Mobile Device Management, MDM) bezeichnet. Wenn Geräte in Intune registriert werden, erhalten sie ein MDM-Zertifikat, das von den Geräten dann für die Kommunikation mit dem Intune-Dienst verwendet wird.

Auf welche Weise Sie Ihre Geräte registrieren, hängt von Gerätetyp, Besitz und benötigtem Verwaltungsniveau ab. Bei der BYOD-Registrierung (Bring Your Own Device, private Geräte der Mitarbeiter) können die Benutzer ihre privaten Smartphones, Tablets oder PCs selbst registrieren. Die Registrierung von unternehmenseigenen Geräten (corporate-owned devices, COD) macht Verwaltungsszenarios wie die automatische Registrierung, freigegebene Geräte oder Anforderungen für eine vorautorisierte Registrierung möglich.

Wenn Sie Exchange ActiveSync entweder lokal oder in der Cloud gehostet verwenden, können Sie eine einfache Intune-Verwaltung ohne Registrierung aktivieren (weitere Informationen folgen in Kürze). Sie können Windows-PCs als mobile Geräte verwalten. Dieses Vorgehen wird unten als empfohlenes Verfahren beschrieben.


## <a name="overview-of-device-enrollment-methods"></a>Übersicht über die Geräteregistrierungsmethoden

Die folgende Tabelle zeigt Intune-Registrierungsmethoden und die unterstützten Funktionen und Anforderungen der einzelnen Methoden. Die Funktionen und Anforderungen werden nachfolgend beschrieben. Die folgenden Begriffe werden in der Tabelle verwendet:

- **Zurücksetzen** – Gibt an, ob das Gerät zurückgesetzt werden muss, bevor Benutzer das Gerät registrieren können. Der Begriff „Zurücksetzen“ bedeutet die Zurücksetzung des Geräts auf Werkseinstellungen, wobei alle Daten entfernt werden. Weitere Informationen finden Sie unter [Verwenden des vollständigen oder selektiven Zurücksetzens von Geräten](devices-wipe.md).
- **Affinität** – Ordnet Geräte Benutzern zu. Für die Verwaltung mobiler Geräte (MAM, Mobile Application Management) und den bedingten Zugriff auf Unternehmensdaten erforderlich. Weitere Informationen finden Sie auf der Seite [Registrieren firmeneigener iOS-Geräte in Microsoft Intune](device-enrollment-program-enroll-ios.md).
- **Sperren**: Zeigt an, wenn Benutzer daran gehindert werden, die Registrierung ihrer Geräte aus der Verwaltung aufheben. Benutzer können die Registrierung ihrer Geräte auf allen Plattformen mithilfe ihrer Unternehmensportal-App aufheben. Sie können zur Aufhebung der Registrierung nicht die nativen Betriebssystemmenüs verwenden.


**iOS-Registrierungsmethoden**

| **Methode** |    **Zurücksetzen erforderlich?** |    **Affinität**    |    **Sperren** | **Details** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nein|    Ja |    Nein | Weitere Informationen folgen in Kürze.|
|**[DEM](#dem)**|    Nein |Nein |Nein    | [Weitere Informationen](device-enrollment-program-enroll-ios.md)|
|**[DEP](#dep)**|    Ja |    Optional |    Optional|[Weitere Informationen](device-enrollment-program-enroll-ios.md)|
|**[USB (Setup-Assistent)](#usb-sa)**|    Ja |    Optional |    Nein| [Weitere Informationen](apple-configurator-setup-assistant-enroll-ios.md)|
|**[USB (direkt)](#usb-direct)**|    Nein |    Nein    | Nein|[Weitere Informationen](apple-configurator-direct-enroll-ios.md)|

**Windows-Registrierungsmethoden**

| **Methode** |    **Zurücksetzen erforderlich?** |    **Affinität**    |    **Sperren** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nein |    Ja |    Nein | [Weitere Informationen](windows-enroll.md)|
|**[DEM](#dem)**|    Nein |Nein |Nein    |[Weitere Informationen](device-enrollment-manager-enroll.md)|

**Android-Registrierungsmethoden**

| **Methode** |    **Zurücksetzen erforderlich?** |    **Affinität**    |    **Sperren** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nein|    Ja |    Nein | [Weitere Informationen](android-enroll.md)|
|**[DEM](#dem)**|    Nein |Nein |Nein    |[Weitere Informationen](device-enrollment-program-enroll-ios.md)|
|**Android for Work**| Nein | Ja | Nein| [Weitere Informationen](android-enroll.md) |


## <a name="byod"></a>BYOD
BYOD-Benutzer installieren die Unternehmensportal-App und registrieren ihr Gerät. Dadurch können Benutzer Verbindungen mit dem Unternehmensnetzwerk herstellen und zur Domäne oder zu Azure Active Directory beitreten. Für die meisten Plattformen müssen Sie BYOD-Registrierung für viele COD-Szenarios ermöglichen. Sie können die Registrierung von persönlichen iOS- und Android-Geräten blockieren. Unter [Festlegen von Gerätetypbeschränkungen](enrollment-restrictions-set.md#set-device-type-restrictions) finden Sie Anweisungen.

## <a name="corporate-owned-devices"></a>Firmeneigene Geräte
Firmeneigene Geräte (Corporate-Owned Devices, COD) können über das Azure-Portal verwaltet werden. iOS-Geräte können direkt über die von Apple bereitgestellten Tools registriert werden. Alle Gerätetypen können von einem Administrator oder Manager die unter Verwendung des Geräteregistrierungs-Managers registriert werden. Geräte mit einer IMEI-Nummer können auch als firmeneigene Geräte identifiziert und gekennzeichnet werden, um COD-Szenarien zu unterstützen.

### <a name="dem"></a>Geräteregistrierungs-Manager (DEM)
Der Geräteregistrierungs-Manager (DEM) ist ein besonderes Benutzerkonto, das zum Registrieren und Verwalten mehrerer firmeneigener Geräte verwendet wird. Manager können das Unternehmensportal installieren und viele benutzerlose Geräte registrieren. Erfahren Sie mehr über den [DEM](device-enrollment-manager-enroll.md). ([Zurück zur Tabelle](#overview-of-device-enrollment-methods))

### <a name="dep"></a>DEP (Device Enrollment Program)
Mit der Apple DEP-Verwaltung (Device Enrollment Program, Programm zur Geräteregistrierung) können Sie Richtlinien erstellen und „drahtlos“ auf iOS-Geräten bereitstellen, die mit DEP erworben wurden und verwaltet werden. Das Gerät wird beim ersten Einschalten durch den Benutzer registriert und führt dann den iOS-Setup-Assistenten aus. Diese Methode unterstützt den iOS-Modus **Überwacht**, der wiederum Folgendes ermöglicht:

  -    Gesperrte Registrierung
  -    Kioskmodus und andere erweiterte Konfigurationen und Einschränkungen

Weitere Informationen zur iOS-Registrierung finden Sie unter:

- [Auswählen der Registrierungsmethode für iOS-Geräte](enrollment-method-choose-ios.md)
- [Registrieren von iOS-Geräten mithilfe des Programms zur Geräteregistrierung](device-enrollment-program-enroll-ios.md)
- [Zurück zur Tabelle oben](#overview-of-device-enrollment-methods)

### <a name="usb-sa"></a>USB (Setup-Assistent)
IT-Administratoren benutzen den Apple Configurator über USB, um jedes unternehmenseigene Gerät manuell für die Registrierung mit dem Setup-Assistenten vorzubereiten. Der IT- Administrator erstellt ein Registrierungsprofil und exportiert dieses in Apple Configurator. Wenn die Benutzer ihre Geräte erhalten, werden sie aufgefordert, den Setup-Assistenten auszuführen. Diese Methode unterstützt den iOS-Modus **Überwacht**, der wiederum Folgendes ermöglicht:
  -    Gesperrte Registrierung
  -    Kioskmodus und andere erweiterte Konfigurationen und Einschränkungen

Weitere Informationen zur iOS-Registrierung finden Sie unter:

- [Auswählen der Registrierungsmethode für iOS-Geräte](enrollment-method-choose-ios.md)
- [Registrieren von iOS-Geräten mithilfe von Configurator und Setup-Assistent](apple-configurator-setup-assistant-enroll-ios.md)

### <a name="usb-direct"></a>USB (direkt)
Für die direkte Registrierung muss der Administrator jedes Gerät manuell registrieren, indem er eine Registrierungsrichtlinie erstellt und in Apple Configurator exportiert. Über USB angeschlossene, unternehmenseigene Geräte werden direkt registriert, ohne dass ein Zurücksetzen auf Werkseinstellungen erforderlich ist. Geräte werden als benutzerlose Geräte verwaltet. Sie werden nicht gesperrt oder überwacht und unterstützen nicht den bedingten Zugriff, die Erkennung von Jailbreaks oder die Verwaltung mobiler Geräte.

Weitere Informationen zur iOS-Registrierung finden Sie unter:

- [Auswählen der Registrierungsmethode für iOS-Geräte](enrollment-method-choose-ios.md)
- [Registrieren von iOS-Geräten mithilfe von Configurator und direkter Registrierung](apple-configurator-direct-enroll-ios.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Verwaltung mobiler Geräte mit Exchange ActiveSync und Intune
Mobile Geräte, die nicht registriert, aber mit Exchange ActiveSync (EAS) verbunden sind, können von Intune mit der MDM EAS-Richtlinie verwaltet werden. Intune verwendet Exchange Connector für die Kommunikation mit EAS, entweder lokal oder in der Cloud gehostet. Weitere Informationen folgen in Kürze.

## <a name="supported-device-platforms-and-browsers"></a>Unterstützte Geräteplattformen und Browser

Siehe [Unterstützte Geräte und Browser für Intune](https://docs.microsoft.com/intune-classic/get-started/supported-mobile-devices-and-computers).

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Bereinigen mobiler Geräte nach Ablauf des MDM-Zertifikats

Das MDM-Zertifikat wird automatisch erneuert, wenn mobile Geräte mit dem Intune-Dienst kommunizieren. Wenn mobile Geräte zurückgesetzt werden oder für längere Zeit keine Kommunikation mit dem Intune-Dienst stattfindet, wird das MDM-Zertifikat nicht erneuert. Das Gerät wird 180 Tage nach Ablauf des MDM-Zertifikats aus dem Azure-Portal entfernt.
