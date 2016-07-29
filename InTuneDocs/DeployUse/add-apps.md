---
title: "Hinzufügen von Apps | Microsoft Intune"
description: Nehmen Sie sich vor der Bereitstellung von Apps mit Intune etwas Zeit, um sich mit den in diesem Thema vorgestellten Konzepten vertraut zu machen.
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b770f4f-6d36-41e4-b535-514b46e29aaa
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: 3b35e835634733f542b7ddaf2ede2ad2464721fd


---

# Hinzufügen von Apps mit Microsoft Intune
Nehmen Sie sich vor der Bereitstellung von Apps mit Microsoft Intune etwas Zeit, um sich mit den in diesem Thema vorgestellten Konzepten vertraut zu machen. Dies hilft Ihnen zu verstehen, welche Apps auf welcher Plattform bereitgestellt werden können. Zudem lernen Sie die erforderlichen Komponenten kennen, die zuvor vorhanden sein müssen.

## Für die Bereitstellung verfügbare App-Typen

### Softwareinstallationsprogramm

|App-Typ|Details|
|----------------|-------|
|**Windows Installer (&#42;.exe, &#42;.msi)**|Diese Art von App muss die automatische Installation ohne Benutzereingabe unterstützen. Die Dokumentation Ihrer App sollte die relevanten Befehlszeilenoptionen einbeziehen, die für die automatische Installation der App erforderlich sind (z. B. **/q**).<br>Eine Liste der gebräuchlichsten Befehlszeilenoptionen finden Sie [hier](https://support.microsoft.com/en-us/kb/227091).<br><br>Wenn zusätzliche Dateien und Ordner für das Setupprogramm der App erforderlich sind, müssen sie an dem für die Setupdateien angegebenen Speicherort verfügbar sein.<br><br>In den meisten Fällen müssen bei Windows Installer-Dateien (MSI) und Windows Installer Patch-Dateien (MSP-Dateien) keine Befehlszeilenargumente von Intune installiert werden. Überprüfen Sie die Dokumentation Ihrer App.<br><br>Sind Befehlszeilenargumente erforderlich, müssen sie in "Name=Wert"-Paaren (z. B. TRANSFORMS=custom_transform.mst) eingegeben werden.|
|**App-Paket für Android (APK-Datei)**|Zum Bereitstellen von Android-Apps müssen Sie über ein gültiges APK-Paket verfügen.|
|**App-Paket für iOS (IPA-Datei)**|Zum Bereitstellen von iOS-Apps müssen Sie über ein gültiges IPA-Paket verfügen.<br><br>Das IPA-Paket muss von Apple signiert sein, und das im Bereitstellungsprofil angegebene Ablaufdatum darf noch nicht erreicht sein. Intune kann iOS-Anwendungen mit Unternehmenszertifikat verteilen.<br>Es werden nicht alle Apps mit Entwicklerzertifikat von Apple unterstützt.<br><br>Ihr Unternehmen muss für das iOS Developer Enterprise Program registriert sein.<br><br>Stellen Sie sicher, dass der Zugriff auf die iOS-Bereitstellungs- und -Zertifizierungswebsites durch die Firewall Ihrer Organisation zugelassen wird.<br><br>Sie müssen keine Manifestdatei (PLIST) mit der App bereitstellen.|
|**Windows Phone-App-Paket (XAP, APPX, APPXBUNDLE)**|Sie benötigen ein codesigniertes Zertifikat für mobile Geräte, um Apps bereitstellen zu können.<br>Weitere Informationen finden Sie unter [Einrichten der Windows Phone-Verwaltung mit Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md).|
|**Windows-App-Paket (*.appx, *.appxbundle)**|Sie benötigen ein codesigniertes Zertifikat für mobile Geräte, um Apps bereitstellen zu können.<br>Weitere Informationen finden Sie unter [Einrichten der Windows-Geräteverwaltung mit Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md).|
|**Windows Installer über MDM (MSI)**|Hiermit können Sie Windows Installer-basierte Apps auf registrierten PCs (mit Verwaltung über MDM) erstellen und bereitstellen, auf denen Windows 10 ausgeführt wird.<br /><br />Sie können nur eine einzelne Datei mit der Erweiterung ".msi" hochladen.<br><br>Produktcode und Produktversion der Datei werden zur Erkennung der App verwendet.<br><br>Es wird das standardmäßige Verhalten bei Neustart der App verwendet. Intune steuert dies nicht.<br><br>Pro Benutzer definierte MSI-Pakete werden für einen einzelnen Benutzer installiert.<br><br>Pro Gerät definierte MSI-Pakete werden für alle Benutzer des Geräts installiert.<br><br>MSI-Pakete im Dualmodus werden zurzeit nur für alle Benutzer des Geräts installiert.<br><br>App-Updates werden unterstützt, wenn jede Version den gleichen MSI-Produktcode aufweist.<br>
Alle App-Typen mit Softwareinstallationsprogramm sind in Ihren Cloudspeicher hochgeladen.

### **Externer Link**
Für Folgendes verwendet:
- Eine **URL**, mit der Benutzer eine App aus einem App-Store herunterladen können.
- Einen **Link** zu einer webbasierten App, die im Webbrowser ausgeführt wird.

Auf externen Links basierende Apps werden nicht in Ihrem Intune-Cloudspeicher gespeichert.
### **Verwaltete iOS-App aus dem App Store**
Sie können kostenlose iOS-Apps aus dem App Store verwalten und bereitstellen. Sie können auch [Richtlinien für die Verwaltung mobiler Anwendungen](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) mit [kompatiblen Apps](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) verknüpfen und ihren Status in der Administratorkonsole überprüfen.<br /><br />Verwaltete iOS-Apps werden nicht in Ihrem Intune-Cloudspeicher gespeichert.

> [!TIP]
> Optionen für mobile Geräte sind nicht verfügbar, bis Sie [die Verwaltungsautorität für mobile Geräte](get-ready-to-enroll-devices-in-microsoft-intune.md) auf Intune festgelegt haben.

## Der Intune-Softwareherausgeber
Der **Microsoft Intune-Softwareherausgeber** wird gestartet, wenn Sie in der Intune-Administratorkonsole Apps hinzufügen oder ändern. Im Herausgeber wählen Sie einen Software-Installationsprogrammtyp aus und konfigurieren ihn, der zum Hochladen von Apps (Programme für Computer oder Apps für mobile Geräte) für die Speicherung im Intune-Cloudspeicher oder zum Bereitstellen eines Links zu einem Onlineshop bzw.einer Webanwendung dient.

Bevor Sie mit der Verwendung des Softwareherausgebers beginnen, müssen Sie die Vollversion von [Microsoft .NET Framework 4.0](https://www.microsoft.com/download/details.aspx?id=17851) installieren. Nach der Installation müssen Sie möglicherweise den Computer neu starten, damit der Softwareherausgeber ordnungsgemäß geöffnet wird.

## Cloudspeicherplatz
Alle Apps, die Sie mithilfe des Software-Installationsprogrammtyps erstellen (beispielsweise eine branchenspezifische App), werden verpackt und in den Microsoft Intune-Cloudspeicher hochgeladen. Ein Testabonnement von Intune enthält 2 GB cloudbasierten Speicher, der zum Speichern von verwalteten Apps und Updates verwendet wird. Ihr vollständiges Abonnement enthält 20 GB Speicherplatz.

Im Knoten **Speichernutzung** des Arbeitsbereichs **Verwaltung** können Sie sehen, wie viel Speicherplatz Sie verwenden.

### Anforderungen für Cloudspeicherplatz

-   Stellen Sie sicher, dass sich alle App-Installationsdateien im selben Ordner befinden.

-   Die maximale Dateigröße für hochgeladene Dateien beträgt 2 GB.


## Unterstützung für UWP-Apps (Universelle Windows-Plattform)
Windows 10-PCs erfordern keinen Sideload-Schlüssel für die Installation von branchenspezifischen Apps. Allerdings muss der Registrierungsschlüssel **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Appx\AllowAllTrustedApps** den Wert **1** haben, um das Querladen zu aktivieren.

Wenn dieser Registrierungsschlüssel nicht konfiguriert ist, legt Intune diesen Wert automatisch auf **1** fest, wenn Sie zum ersten Mal eine App auf dem Gerät bereitstellen. Wenn Sie diesen Wert auf **0** festgelegt haben, kann Intune den Wert nicht automatisch ändern, und die Bereitstellung von Sparten-Apps misslingt.

UWP-Sparten-Apps müssen mit einem codesignierten Zertifikat signiert sein, das auf jedem Gerät, auf dem die App bereitgestellt ist, als vertrauenswürdig eingestuft ist. Sie können Zertifikate aus einer internen PKI-Infrastruktur verwenden oder ein Zertifikat von einer öffentlichen Drittanbieter-Stammzertifizierungsstelle, das auf dem Gerät installiert ist.

Auf Windows 10 Mobile-Geräten können Sie ein nicht von Symantec stammendes Codesignaturzertifikat zum Signieren universeller **APPX**-Apps verwenden. Für **XAP**-Apps sowie für **APPX**-Pakete, die für Windows Phone 8.1 erstellt wurden, die Sie auf Windows 10 Mobile-Geräten installieren möchten, müssen Sie ein Codesignaturzertifikat von Symantec verwenden.

## Nächste Schritte 

Als Nächstes müssen Sie Apps in der Intune-Konsole hinzufügen, bevor Sie sie bereitstellen können. Sie können Apps für [registrierte Geräte](add-apps-for-mobile-devices-in-microsoft-intune.md) oder für [Windows-PCs hinzufügen, die Sie mit der Intune-Clientsoftware verwalten](add-apps-for-windows-pcs-in-microsoft-intune.md).



<!--HONumber=Jul16_HO3-->


