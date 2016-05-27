---
# required metadata

title: Archiv der Neuheiten | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


## September 2015
### Updates für die Verwaltung von mobilen Geräten und Apps
**Alle Intune iOS-Verwaltungsfeatures unterstützen jetzt iOS 9**
Ausführliche Informationen zu den iOS 9-Verwaltungsfunktionen finden Sie in diesem [Blogbeitrag](http://blogs.technet.com/b/microsoftintune/archive/2015/09/09/day-zero-support-for-ios-9-with-intune.aspx)..

**Neue Konfigurationsrichtlinie für iOS für mobile Apps**
Mithilfe der neuen Konfigurationsrichtlinie für mobile Apps können Sie automatisch Einstellungen bereitstellen, die eine iOS-App bei der Ausführung möglicherweise benötigt. So könnten Sie beispielsweise einen Netzwerkport oder einen Benutzernamen bereitstellen. Weitere Informationen finden Sie unter [Konfigurieren von Apps mit Konfigurationsrichtlinien für mobile Apps in Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx)..

**Einfachere App-Verwaltung für iOS 9-Benutzer**
 In dieser Version können Sie bereits bereitgestellte Apps für iOS 9-Benutzer unter die Verwaltung von Intune bringen. Wenn Sie bei früheren Versionen von iOS eine App bereitstellen und eine nicht verwaltete Version der App bereits auf einem Gerät installiert ist, müssen Sie den Benutzer nach wie vor bitten, die App manuell zu deinstallieren, bevor Intune die verwaltete App installieren kann.

 Aber beginnend mit dieser Version von Intune können Sie Benutzer von iOS 9-Geräten jetzt auffordern, Intune die Verwaltung der App und die Anwendung aller relevanten Verwaltungsrichtlinien für mobile Anwendungen zu erlauben.

 **Windows 10-Verwaltung** Verwenden Sie die neue [allgemeine Windows 10-Konfigurationsrichtlinie](https://technet.microsoft.com/library/mt404697.aspx), um die Kennwort-, Geräte-, Browser- und sonstigen Einstellungen für registrierte Geräte, auf denen Windows 10 und Windows 10 Mobile ausgeführt wird, zu konfigurieren.

 **Erstellen und Bereitstellen von Apps auf registrierten Windows 10-Geräten** Dank eines neuen Softwareinstallationsprogramm-Typs, Windows Installer über MDM (&#42;.msi), können Sie Windows Installer-Apps für registrierte Geräte, auf denen Windows 10 ausgeführt wird, erstellen und darauf bereitstellen. Weitere Informationen finden Sie unter [Erste Schritte bei der Bereitstellung von Apps in Microsoft Intune](https://technet.microsoft.com/library/dn646955.aspx)..

### Änderungen und Updates für die Unternehmensportal-Apps von Microsoft
In dieser Version wurden die folgenden Änderungen an den Unternehmensportal-Apps vorgenommen:

**iOS**
* Microsoft erfasst automatisch anonyme Daten über die Leistung und die Verwendung des Unternehmensportals, um Microsoft-Produkte und -Dienste zu verbessern. Endbenutzer können die Datenerfassung über die Einstellung "Nutzungsdaten" auf ihrem Gerät deaktivieren, Administratoren haben jedoch keine Kontrolle über die Datenerfassung und können die Auswahl der Endbenutzer für diese Einstellung nicht ändern.
* Unterstützung für Vollbildauflösung auf dem iPhone 6 und 6 Plus
* Fehlerbehebungen für verbesserte Sicherheit.

### Neuerungen in der Intune-Dokumentation – September 2015
**Neue Themen**

|Name|Details|
|----|--------|
|[Einstellungen für Windows 10-Konfigurationsrichtlinien in Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx)|Dies ist eine neue Konfigurationsrichtlinie, mit der Sie die Einstellungen und Funktionen auf Geräten verwalten können, auf denen Windows 10 und Windows 10 Mobile ausgeführt wird.
| [Konfigurieren von Apps mit Konfigurationsrichtlinien für mobile Apps in Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx)|Dies ist ein neuer Richtlinientyp, mit dem Sie automatisch Einstellungen bereitstellen können, die beim Ausführen einer iOS-App durch den Benutzer möglicherweise erforderlich sind. |

**Aktualisierte Themen**

|Name|Details|
|----|-------|
|[Verwenden von Richtlinien zum Verwalten von Computern und mobilen Geräten mit Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx)|Aktualisiert mit den neuesten Informationen zum Grundverständnis und Erstellen von Richtlinien.|

## August 2015
### Updates für die Verwaltung von mobilen Geräten und Apps
* **Geschäftsbedingungen** für die Intune-Registrierung und den Unternehmenszugriff werden [jetzt mithilfe von Richtlinien verwaltet](https://technet.microsoft.com/library/mt405893.aspx). Sie können verschiedene Sätze von Geschäftsbedingungen bereitstellen, um die Anforderungen bestimmter Benutzergruppen zu erfüllen. Beispielsweise können Sie Geschäftsbedingungen in verschiedenen Sprachen für geografisch definierte Benutzergruppen bereitstellen. Sie können auch [Ihre Geschäftsbedingungen bearbeiten](https://technet.microsoft.com/library/mt405893.aspx#BKMK_TCVers) und angeben, ob die Versionsnummern erhöht werden sollen, sodass Benutzer den neuen Geschäftsbedingungen zustimmen müssen, bevor sie das Unternehmensportal verwenden können.
* **Eine Reihe von Intune-Richtlinien wurde umbenannt** , um die Konsistenz im gesamten Produkt zu erhöhen und sie leichter auffindbar zu machen. Eine Liste aller verfügbaren Intune-Richtlinien finden Sie unter [Verwenden von Richtlinien zum Verwalten von Computern und mobilen Geräten mit Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx)..
* **Zertifikatprofile vom Typ „PKCS #12 (.PFX)“** sind für Android 4.0 oder höher und Windows 10 (Desktop und mobil) und höher erhältlich. Für die Verwendung von PFX ist kein NDES-Server erforderlich. Weitere Informationen zum Verwenden von PFX-Zertifikatprofilen finden Sie unter [Aktivieren des Zugriffs auf Unternehmensressourcen mithilfe von Zertifikatprofilen mit Microsoft Intune](http://technet.microsoft.com/library/dn818904.aspx).
* **Einstellungen für Unternehmensgrenzen für Windows 10 Desktop und Mobile** ermöglichen differenzierte VPN-Einstellungen, wie unter [Unterstützen von Benutzern beim Verbinden mit ihrer Arbeit über VPN-Profile in Microsoft Intune](https://technet.microsoft.com/library/dn818905.aspx) beschrieben.
* **Die OneDrive-App für Android unterstützt jetzt mehrere Identitäten.** Diese und weitere Aktualisierungen an den Verwaltungsrichtlinien für mobile Apps werden in der [Liste der Microsoft-Anwendungen, die verwaltet werden können](https://technet.microsoft.com/library/dn708489.aspx), beschrieben..
* **Umgehung der iOS-Aktivierungssperre** Wenn firmeneigene iOS-Geräte durch eine Aktivierungssperre geschützt sind, müssen Sie vor dem Löschen oder erneuten Aktivieren des Geräts die Apple-ID und das zugehörige Kennwort des Benutzers eingeben. Dies kann ein Problem darstellen, wenn Benutzer das Unternehmen verlassen und ein firmeneigenes Gerät ohne deaktivierte Aktivierungssperre zurückgeben. Sie können die [Intune-Umgehung der Aktivierungssperre](https://technet.microsoft.com/library/mt414176.aspx) verwenden, um dieses Problem zu beheben.

### Bedingter Zugriff für PCs
Sie können jetzt bedingte Zugriffsrichtlinien für PCs konfigurieren. Dadurch können Office-Desktop-Apps auf Exchange Online- und SharePoint Online-Dienste zugreifen.
Um bedingte Zugriffsrichtlinien für PCs zu aktivieren, muss der PC entweder in eine Domäne eingebunden oder kompatibel sein.
* Der Abschnitt **Erste Schritte** in [Verwalten des Zugriffs auf E-Mail und SharePoint mit Microsoft Intune](http://technet.microsoft.com/library/dn818907) enthält eine vollständige Liste der Anforderungen für das Aktivieren des bedingten Zugriffs für PCs.
* Optionen, die Sie festlegen können, um den bedingten Zugriff für E-Mail-Zugriff zu aktivieren, finden Sie unter [Verwalten des E-Mail-Zugriffs mit Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx).
* Optionen, die Sie festlegen können, um den bedingten Zugriff für SharePoint Online zu aktivieren, finden Sie unter [Verwalten des Zugriffs auf SharePoint Online mit Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx).

### Änderungen und Updates für die Unternehmensportal-Apps von Microsoft
In dieser Version wurden die folgenden Änderungen an den Unternehmensportal-Apps vorgenommen:

**Android**

Den Benutzern werden jetzt nach der Anmeldung Anweisungen zur Geräteregistrierung angezeigt, sofern das Gerät noch nicht für die Verwaltung registriert wurde.

### Neuerungen in der Intune-Dokumentation – August 2015
**Neue Themen**

|Titel|Details|
|-----|-------|
|[Unterstützen des Schutz von iOS-Geräten durch Umgehung der Aktivierungssperre für Microsoft Intune](https://technet.microsoft.com/library/mt414176.aspx)|Erfahren Sie, wie Sie Intune verwenden können, um die iOS-Aktivierungssperre zu umgehen, wenn ein Benutzer das Unternehmen verlässt und ein gesperrtes Gerät zurückgibt.|

**Aktualisierte Themen**

|Titel|Details|
|-----|-------|
|[Microsoft-Apps zur Verwendung mit den Microsoft Intune-Verwaltungsrichtlinien für mobile Anwendungen](https://technet.microsoft.com/library/dn708489.aspx)|Aktualisiert mit den neuesten Informationen zu Apps, die Sie mit Verwaltungsrichtlinien für mobile Geräte verwalten können.
|[Verwenden von Richtlinien zum Verwalten von Computern und mobilen Geräten mit Microsoft Intune](http://technet.microsoft.com/library/dn743712.aspx)|Aktualisiert mit den neuesten Richtlinien, die zu Intune hinzugefügt wurden.|
<!---
## July 2015
July updates for Intune are limited to behind-the-scenes enhancements that allow us to continue providing you with a high-quality service experience. New features are not included in this service update.

### Intune Onboarding benefit
Microsoft offers the Intune Onboarding benefit for eligible plans. The Onboarding benefit lets you work remotely with Microsoft specialists to get your Intune environment ready for use. For more information, see [Microsoft Intune Onboarding benefit description](https://technet.microsoft.com/library/mt228266.aspx)
### Changes and updates to Microsoft Company Portal apps
The following changes have been made to the company portal apps in this release.

**Android**

Microsoft automatically collects anonymous data about the performance and use of the company portal to improve Microsoft products and services. End users can turn off data collection by using the Usage Data setting on their device, but administrators have no control over the data collection and cannot change the end user’s selection for this setting.--->


<!--HONumber=May16_HO1-->


