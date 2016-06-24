---
# required metadata

title: Hinzufügen von Apps | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b770f4f-6d36-41e4-b535-514b46e29aaa

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Hinzufügen von Apps mit Microsoft Intune
Nehmen Sie sich vor der Bereitstellung von Apps mit Microsoft Intune etwas Zeit, um sich mit den in diesem Thema vorgestellten Konzepten vertraut zu machen. Dies hilft Ihnen zu verstehen, welche Apps auf welcher Plattform bereitgestellt werden können. Zudem lernen Sie die erforderlichen Komponenten kennen, die zuvor vorhanden sein müssen.

## Mit Intune bereitstellbare App-Typen
Sie können Apps auf allen Gerätetypen bereitstellen, die von Intune unterstützt werden. Je nach Art der Anwendung, die Sie bereitstellen möchten, unterscheiden sich der Prozess und die unterstützten Geräte. Verwenden Sie die folgenden Informationen, um besser zu verstehen, welche Optionen bereitgestellt werden können:


### **Windows Installer (&#42;.exe, &#42;.msi)**
- Diese Art von App muss die automatische Installation ohne Benutzereingabe unterstützen. Die Dokumentation Ihrer App sollte die relevanten Befehlszeilenoptionen einbeziehen, die für die automatische Installation der App erforderlich sind (z. B. **/q**). Eine Liste der gebräuchlichsten Befehlszeilenoptionen finden Sie [hier](https://support.microsoft.com/en-us/kb/227091).
- Wenn zusätzliche Dateien und Ordner für das Setupprogramm der App erforderlich sind, müssen sie an dem für die Setupdateien angegebenen Speicherort verfügbar sein.
- In den meisten Fällen müssen bei Windows Installer-Dateien (MSI) und Windows Installer Patch-Dateien (MSP-Dateien) keine Befehlszeilenargumente von Intune installiert werden. Überprüfen Sie die Dokumentation Ihrer App. Sind Befehlszeilenargumente erforderlich, müssen sie in "Name=Wert"-Paaren (z. B. TRANSFORMS=custom_transform.mst) eingegeben werden.

Diese Art von Anwendung wird in Ihren Cloudspeicher hochgeladen.
### **App-Paket für Android (APK-Datei)**
Diese Art von Anwendung wird in Ihren Cloudspeicher hochgeladen.
### **App-Paket für iOS (IPA-Datei)**
- Zum Bereitstellen von iOS-Apps müssen Sie über ein gültiges IPA-Paket verfügen.
- Das IPA-Paket muss von Apple signiert sein, und das im Bereitstellungsprofil angegebene Ablaufdatum darf noch nicht erreicht sein. Intune kann iOS-Anwendungen mit Unternehmenszertifikat verteilen. Es werden nicht alle Apps mit Entwicklerzertifikat von Apple unterstützt.
- Ihr Unternehmen muss für das iOS Developer Enterprise Program registriert sein.
- Stellen Sie sicher, dass der Zugriff auf die iOS-Bereitstellungs- und -Zertifizierungswebsites durch die Firewall Ihrer Organisation zugelassen wird.
- Eine Manifestdatei (PLIST) muss mit der Anwendung nicht bereitgestellt werden.

Diese Art von Anwendung wird in Ihren Cloudspeicher hochgeladen.

Derzeit können Endbenutzer Unternehmens-Apps nicht direkt über die Intune-Unternehmensportal-App für iOS installieren. Dies ist aufgrund der Einschränkungen für apps, die in das iOS-App Store veröffentlicht werden (siehe [App Store Richtlinien](https://developer.apple.com/app-store/review/guidelines/)). Benutzer können auf Unternehmens-Apps (einschließlich verwalteter App Store-Apps und Branchen-App-Pakete) zugreifen, indem sie die Unternehmensportal-App auf ihren Geräten starten und auf die Kachel „Unternehmens-Apps“ tippen. Daraufhin wird der Browser geöffnet, und sie werden zum Intune-Webportal geleitet.

### **Windows Phone-App-Paket (XAP, APPX, APPXBUNDLE)**
- Sie benötigen ein codesigniertes Zertifikat für mobile Geräte, um Apps bereitstellen zu können. Weitere Informationen finden Sie unter [Einrichten der Windows Phone-Verwaltung mit Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md).

Diese Art von Anwendung wird in Ihren Cloudspeicher hochgeladen.

Weitere Informationen zur Installation von Branchen-UWP-Apps (Universelle Windows-Plattform) mit Intune finden Sie weiter unten.

### **Windows-App-Paket (*.appx, *.appxbundle)**
- Sie benötigen ein codesigniertes Zertifikat für mobile Geräte, um Apps bereitstellen zu können. Weitere Informationen finden Sie unter [Einrichten der Windows-Geräteverwaltung mit Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md).

Diese Art von Anwendung wird in Ihren Cloudspeicher hochgeladen.
### **Windows Installer über MDM (MSI)**
Mit diesem Installationstyp können Sie Windows Installer-basierte Apps auf registrierten PCs mit Windows 10 erstellen und bereitstellen.<br /><br />Folgendes muss berücksichtigt werden, wenn Sie diese Art Installationsprogramm verwenden:
- Sie können nur eine einzelne Datei mit der Erweiterung ".msi" hochladen.
- Produktcode und Produktversion der Datei werden zur Erkennung der App verwendet.
- Es wird das standardmäßige Verhalten bei Neustart der App verwendet. Intune steuert dies nicht.
- Pro Benutzer definierte MSI-Pakete werden für einen einzelnen Benutzer installiert.
- Pro Gerät definierte MSI-Pakete werden für alle Benutzer des Geräts installiert.
- MSI-Pakete im Dualmodus werden zurzeit nur für alle Benutzer des Geräts installiert.
- App-Updates werden unterstützt, wenn jede Version den gleichen MSI-Produktcode aufweist.

Diese Art von Anwendung wird in Ihren Cloudspeicher hochgeladen.
### **Externer Link**
Für Folgendes verwendet:
- Eine **URL**, mit der Benutzer eine App aus einem App-Store herunterladen können.
- Einen **Link** zu einer webbasierten App, die im Webbrowser ausgeführt wird.

Auf externen Links basierende Apps werden nicht in Ihrem Intune-Cloudspeicher gespeichert.
### **Verwaltete iOS-App aus dem App Store**
Sie können kostenlose iOS-Apps aus dem App Store verwalten und bereitstellen. Sie können auch [Richtlinien für die Verwaltung mobiler Anwendungen](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) mit [kompatiblen Apps](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) verknüpfen und ihren Status in der Administratorkonsole überprüfen.<br /><br />Verwaltete iOS-Apps werden nicht in Ihrem Intune-Cloudspeicher gespeichert.
> [!TIP] Optionen für mobile Geräte sind nicht verfügbar, bis Sie die [Verwaltungsautorität für mobile Geräte](get-ready-to-enroll-devices-in-microsoft-intune.md) auf Intune festgelegt haben.

## Unterstützung für UWP-Apps (Universelle Windows-Plattform)
Windows 10-PCs erfordern keinen Sideload-Schlüssel für die Installation von branchenspezifischen Apps. Allerdings muss der Registrierungsschlüssel **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Appx\AllowAllTrustedApps** den Wert **1** haben, um das Querladen zu aktivieren.

Wenn dieser Registrierungsschlüssel nicht konfiguriert ist, legt Intune diesen Wert automatisch auf **1** fest, wenn Sie zum ersten Mal eine App auf dem Gerät bereitstellen. Wenn Sie diesen Wert auf **0** festgelegt haben, kann Intune den Wert nicht automatisch ändern, und die Bereitstellung von Sparten-Apps misslingt.

UWP-Sparten-Apps müssen mit einem codesignierten Zertifikat signiert sein, das auf jedem Gerät, auf dem die App bereitgestellt ist, als vertrauenswürdig eingestuft ist. Sie können Zertifikate aus einer internen PKI-Infrastruktur verwenden oder ein Zertifikat von einer öffentlichen Drittanbieter-Stammzertifizierungsstelle, das auf dem Gerät installiert ist.

Auf Windows 10 Mobile-Geräten können Sie ein nicht von Symantec stammendes Codesignaturzertifikat zum Signieren universeller **APPX**-Apps verwenden. Für **XAP**-Apps sowie für **APPX**-Pakete, die für Windows Phone 8.1 erstellt wurden, die Sie auf Windows 10 Mobile-Geräten installieren möchten, müssen Sie ein Codesignaturzertifikat von Symantec verwenden.

## Nächste Schritte 

Als Nächstes müssen Sie Apps in der Intune-Konsole hinzufügen, bevor Sie sie bereitstellen können. Sie können Apps für [registrierte Geräte](add-apps-for-mobile-devices-in-microsoft-intune.md) oder für [Windows-PCs hinzufügen, die Sie mit der Intune-Clientsoftware verwalten](add-apps-for-windows-pcs-in-microsoft-intune.md).

<!--HONumber=Jun16_HO2-->


