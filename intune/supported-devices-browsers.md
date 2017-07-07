---
title: "Unterstützte Geräte – Microsoft Intune"
description: "Liste der unterstützten Geräteplattformen und Browser für die Intune-Geräteverwaltung"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: df9c4c0a0a23740bf9df4c13e34b8752838aa99a
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2017
---
# <a name="supported-devices-and-browsers"></a>Unterstützte Geräte und Browser

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Dieser Artikel richtet sich an Systemadministratoren, die für die Verwaltung der Geräte im Unternehmen verantwortlich sind. Hilfe zur Installation von Intune auf Ihrem Telefon finden Sie unter [Verwenden verwalteter Geräte zum Erledigen von Aufgaben](/intune-user-help/company-portal-frequently-asked-questions).

Prüfen Sie die folgenden Anforderungen, bevor Sie mit der Einrichtung von Microsoft Intune beginnen:

- [Unterstützte Geräte und Computer](#intune-supported-devices)
- [Liste der unterstützten Webbrowser, die Intune verwenden](#intune-supported-web-browsers)

Sie sollten sich auch mit der [Nutzung der Netzwerkbandbreite durch Intune](network-bandwidth-use.md) ([klassische Konsole](/intune-classic/get-started/network-bandwidth-use)) vertraut machen.

## <a name="intune-supported-devices"></a>Von Intune unterstützte Geräte

Sie können die folgenden Geräte mit Intune MDM (Verwaltung mobiler Geräte, Mobile Device Management) verwalten:

[!INCLUDE[mdm-supported-devices](./includes/mdm-supported-devices.md)]

Intune kann nicht verwendet werden, um Windows Server-Betriebssysteme zu verwalten.

### <a name="windows-pc-software-client"></a>Softwareclient für Windows-PCs

Ein [Intune-Softwareclient](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) auf Windows-PCs als eine alternative Registrierungsmethode bereitgestellt und installiert werden. Diese Funktionalität ist nur in der klassischen Intune-Konsole verfügbar. Sie können den Intune-Softwareclient zum Verwalten von PCs mit Windows 7 und höher (mit Ausnahme der Windows 10 Home-Edition) verwenden.

<!--  ### Exchange ActiveSync management

You can manage [Exchange ActiveSync devices](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) from the Intune console. This option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.  -->

## <a name="intune-supported-web-browsers"></a>Von Intune unterstützte Webbrowser

Für verschiedene Verwaltungsaufgaben müssen Sie eine der folgenden Verwaltungswebsites verwenden.

- [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Intune-Portal](https://portal.azure.com/)

Für diese Portale werden die folgenden Browser unterstützt:
- Microsoft Edge (neueste Version)
- Microsoft Internet Explorer 11
- Safari (neueste Version, nur auf Mac)
- Chrome (neueste Version)
- Firefox (neueste Version)

### <a name="intune-classic-portal"></a>Klassisches Intune-Portal

Die klassischen Intune-Funktionen wie der Intune-PC-Softwareclient und die Integration von Mobile Threat Defense-Partnern sind nur im klassischen Intune-Portal (https://manage.microsoft.com) verfügbar. Die klassische Intune-Konsole erfordert Silverlight-Browserunterstützung.

Die folgenden Silverlight-Browser unterstützen die klassische Intune-Konsole:
- Internet Explorer 10 oder höher
- Google Chrome (Versionen vor Version 42)
- Mozilla Firefox mit aktiviertem Silverlight – [weitere Informationen](https://go.microsoft.com/fwlink/?linkid=836872)

> [!Note]
> Microsoft Edge und mobile Browser werden für die klassische Intune-Konsole nicht unterstützt, da sie [Microsoft Silverlight](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx) nicht unterstützen.


Lediglich Benutzer mit Dienstadministratorrechten oder Mandantenadministratoren mit globaler Administratorrolle können sich bei diesem Portal anmelden. Für den Zugriff auf die Administratorkonsole sind für Ihr Konto eine Lizenz zur Verwendung von Intune und der Anmeldestatus **Zugelassen** erforderlich.
