---
title: "Unterstützte mobile Geräte und Browser | Microsoft Intune"
description: "Liste der unterstützten Geräte und der Browser, die Intune ausführen können"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/01/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aeeccfa4-0f14-447e-a3df-c8435c8a4bb2
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: b0eab195c00aae4b593fff535179a1b993c36dde


---

# <a name="supported-devices-and-web-browsers-for-intune"></a>Unterstützte Geräte und Webbrowser für Intune

Als Intune-Administrator können Sie eine Vielzahl von Geräten über einen Webbrowser verwalten. Dieses Thema enthält:

- [Listen unterstützter Geräteplattformen](#intune-supported-devices)
- [Liste der unterstützten Webbrowser, die Intune verwenden](#intune-supported-web-browsers)

## <a name="intune-supported-devices"></a>Von Intune unterstützte Geräte

Sie können die folgenden Geräte mit Intune MDM (Verwaltung mobiler Geräte, Mobile Device Management) verwalten:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Intune kann nicht verwendet werden, um Windows Server-Betriebssysteme zu verwalten.

Die Intune-Geräteverwaltung bietet [diese Funktionen](mobile-device-management-capabilities-in-microsoft-intune.md).

### <a name="windows-pc-software-client"></a>Softwareclient für Windows-PCs

Ein [Intune-Softwareclient](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune) auf Windows-PCs als eine alternative Registrierungsmethode bereitgestellt und installiert werden. Sie können den Intune-Softwareclient zum Verwalten von PCs mit Windows 7 und höher (mit Ausnahme der Windows 10 Home-Edition) verwenden. Die PC-Verwaltung mit dieser Clientsoftware bietet [diese Möglichkeiten](windows-pc-management-capabilities-in-microsoft-intune.md).

### <a name="exchange-activesync-management"></a>Exchange ActiveSync-Verwaltung

Sie können [Exchange ActiveSync-Geräte](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) über die Intune-Konsole verwalten. Diese Option bietet im Vergleich zu anderen Methoden eine begrenzte Anzahl von Funktionen für die Verwaltung. Eine Liste der unterstützten Geräte finden Sie unter [Funktionen der integrierten Verwaltung mobiler Geräte für Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0).

## <a name="intune-supported-web-browsers"></a>Von Intune unterstützte Webbrowser

Für verschiedene Verwaltungsaufgaben müssen Sie eine der folgenden Verwaltungswebsites verwenden.

- [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Microsoft Intune-Administratorkonsole](https://admin.manage.microsoft.com/)

|Intune-Feature |Unterstützte Browser|
|---------|---------|
|**Intune-Administratorkonsole**     |  Internet Explorer 10 oder höher<br /><br />Google Chrome (Versionen vor Version 42)<br /><br />Mozilla Firefox mit aktiviertem Silverlight<br />**Hinweis:** Ab März 2017 wird Silverlight von Mozilla nicht mehr unterstützt. [Erfahren Sie mehr](https://go.microsoft.com/fwlink/?linkid=836872). |
|**Office 365-Verwaltungsportal**     |Alle Browser, einschließlich mobiler und verwalteter Browser  |
|**Unternehmensportal-Website**     |**Auf mobilen Geräten:** Verwenden Sie für jede unterstützte Plattform den Standardwebbrowser.   <br /><br />**Auf Windows-PCs:** Internet Explorer 10 oder höher oder Microsoft Edge<br /><br />**Unter Mac OS X 10.9 oder höher:** Apple Safari    |

> [!Note]
> Microsoft Edge und mobile Browser werden für die Administratorkonsole nicht unterstützt, da sie [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx) nicht unterstützen. Für die Intune-Konsole wird in Zukunft nicht mehr Silverlight verwendet, letztlich werden alle Intune-Features zur Verwaltung mobiler Geräte und Anwendungen [im neuen Azure-Portal verfügbar gemacht](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/). Diese Umstellung wird jedoch eine Zeit lang dauern.


Lediglich Benutzer mit Dienstadministratorrechten oder Mandantenadministratoren mit globaler Administratorrolle können sich bei diesem Portal anmelden. Für den Zugriff auf die Administratorkonsole sind für Ihr Konto eine Lizenz zur Verwendung von Intune und der Anmeldestatus **Zugelassen** erforderlich.
>[!div class="step-by-step"]

>[&larr; **Voraussetzungen**](what-to-know-before-you-start-microsoft-intune.md)     [**Netzwerke** &rarr;](network-bandwidth-use.md)  



<!--HONumber=Dec16_HO2-->


