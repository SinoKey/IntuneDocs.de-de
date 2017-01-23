---
title: Voraussetzungen | Microsoft-Dokumentation
description: "Links zu erforderlichen Komponenten und Anforderungen für Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/10/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a567d55141c4510a5c81861df1522f118104de61
ms.openlocfilehash: 900b3a9bcc9ce58cd165b14592c850b50739a33a


---

# <a name="prerequisites-to-getting-started-with-intune"></a>Voraussetzungen für den Einstieg in Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Prüfen Sie die folgenden Anforderungen, bevor Sie mit der Einrichtung von Microsoft Intune beginnen:

- [Unterstützte Geräte und Computer](#intune-supported-devices)
- [Liste der unterstützten Webbrowser, die Intune verwenden](#intune-supported-web-browsers)

Sie sollten sich auch mit der [Nutzung der Netzwerkbandbreite durch Intune](network-bandwidth-use.md) vertraut machen.

## <a name="intune-supported-devices"></a>Von Intune unterstützte Geräte

Sie können die folgenden Geräte mit Intune MDM (Verwaltung mobiler Geräte, Mobile Device Management) verwalten:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Intune kann nicht verwendet werden, um Windows Server-Betriebssysteme zu verwalten.

Die Intune-Geräteverwaltung bietet [diese Funktionen](mobile-device-management-capabilities-in-microsoft-intune.md).

### <a name="windows-pc-software-client"></a>Softwareclient für Windows-PCs

Ein [Intune-Softwareclient](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune) auf Windows-PCs als eine alternative Registrierungsmethode bereitgestellt und installiert werden. Sie können den Intune-Softwareclient zum Verwalten von PCs mit Windows 7 und höher verwenden. Die PC-Verwaltung mit dieser Clientsoftware bietet [diese Möglichkeiten](windows-pc-management-capabilities-in-microsoft-intune.md).

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

>[**Netzwerk** &rarr;](network-bandwidth-use.md)  



<!--HONumber=Jan17_HO2-->


