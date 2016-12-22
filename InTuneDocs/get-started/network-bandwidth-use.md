---
title: Nutzung der Netzwerkbandbreite durch Intune | Microsoft Intune
description: Nutzung der Netzwerkbandbreite durch Intune
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 363300f04480a9ed80bd710db5c4ec7c90dd8be3


---

# <a name="intune-network-bandwidth-use"></a>Nutzung der Netzwerkbandbreite durch Intune

Bevor Sie Microsoft Intune einrichten, lesen Sie dieses Thema und andere Anforderungen, die unter [Was Sie wissen sollten, bevor Sie Microsoft Intune starten](what-to-know-before-you-start-microsoft-intune.md) aufgeführt sind.

Planen Sie anhand der Informationen in den folgenden Abschnitten den Netzwerkdatenverkehr für Microsoft Intune-Clients.

## <a name="average-network-traffic"></a>Durchschnittlicher Netzwerkdatenverkehr
Die Tabelle führt den ungefähren Umfang und die Häufigkeit gemeinsamer Inhalte auf, die pro Client über das Netzwerk übertragen werden.

> [!NOTE]
> Um sicherzustellen, dass Computer und mobile Geräte die erforderlichen Updates und Inhalte vom Intune-Dienst erhalten, müssen sie in regelmäßigen Abständen mit dem Internet verbunden werden. Die Zeit für das Empfangen von Updates oder Inhalten kann variieren, als Richtlinie gilt jedoch, dass sie für mindestens eine Stunde pro Tag kontinuierlich mit dem Internet verbunden sein sollen.

|Art des Inhalts|Ungefähre Größe|Häufigkeit und Details|
|----------------|--------------------|-------------------------|
|Intune-Clientinstallation<br /><br />**Die folgenden Anforderungen gelten zusätzlich zur Intune-Clientinstallation**|125 MB|**Einmalig**<br /><br />Der Umfang des Clientdownloads schwankt je nach Betriebssystem des Clientcomputers.|
|Clientregistrierungspaket|15 MB|**Einmalig**<br /><br />Weitere Downloads sind möglich, wenn Updates für diesen Inhaltstyp vorliegen.|
|Endpoint Protection-Agent|65 MB|**Einmalig**<br /><br />Weitere Downloads sind möglich, wenn Updates für diesen Inhaltstyp vorliegen.|
|Operations Manager-Agent|11 MB|**Einmalig**<br /><br />Weitere Downloads sind möglich, wenn Updates für diesen Inhaltstyp vorliegen.|
|Richtlinien-Agent|3 MB|**Einmalig**<br /><br />Weitere Downloads sind möglich, wenn Updates für diesen Inhaltstyp vorliegen.|
|Remoteunterstützung über den Microsoft Easy Assist-Agent|6 MB|**Einmalig**<br /><br />Weitere Downloads sind möglich, wenn Updates für diesen Inhaltstyp vorliegen.|
|Tägliche Clientvorgänge|6 MB|**Täglich**<br /><br />Der Intune-Client kommuniziert regelmäßig mit dem Intune-Dienst, um nach Updates und Richtlinien zu suchen und den Status des Clients an den Dienst zu melden.|
|Malwaredefinitionsupdates für Endpoint Protection|Variiert<br /><br />Normalerweise zwischen 40 KB und 2 MB|**Täglich**<br /><br />Bis zu drei Mal täglich.|
|Endpoint Protection-Modulupdate|5 MB|**Monatlich**|
|Softwareupdates|Variiert<br /><br />Die Größe hängt von den von Ihnen bereitgestellten Updates ab.|**Monatlich**<br /><br />Normalerweise werden Softwareupdates am zweiten Dienstag eines jeden Monats bereitgestellt.<br /><br />Durch einen neu registrierten oder bereitgestellten Computer kann mehr Netzwerkbandbreite verwendet werden, solange alle zuvor veröffentlichten Updates heruntergeladen werden.|
|Service Packs|Variiert<br /><br />Die Größe variiert für jedes von Ihnen bereitgestellte Service Pack.|**Variiert**<br /><br />Hängt vom Zeitpunkt der Service Pack-Bereitstellung ab.|
|Softwareverteilung|Variiert<br /><br />Die Größe hängt von der von Ihnen bereitgestellten Software ab.|**Variiert**<br /><br />Hängt vom Zeitpunkt der Softwarebereitstellung ab.|

## <a name="ways-to-reduce-network-bandwidth-use"></a>Möglichkeiten zum Verringern der Bandbreitennutzung
Mithilfe der folgenden Methoden können Sie die Nutzung der Netzwerkbandbreite für Intune-Clients reduzieren.

### <a name="use-a-proxy-server-to-cache-content-requests"></a>Verwenden eines Proxyservers zum Zwischenspeichern von Inhaltsanforderungen
Mithilfe eines Proxyservers zur Zwischenspeicherung von Inhalt können Sie doppelte Downloads vermeiden und die Bandbreitennutzung durch Clients verringern, von denen Inhalte aus dem Internet angefordert werden.

Von einem zwischenspeichernden Proxyserver werden Inhaltsanforderungen der Clientcomputer in Ihrem Netzwerk empfangen, diese Inhalte aus dem Internet abgerufen und dann zwischengespeichert. Dies schließt sowohl HTTP-Antworten als auch binäre Downloads ein. Der Server verwendet die zwischengespeicherten Informationen, um auf nachfolgende Anforderungen von Intune-Clientcomputern zu antworten.

Nachfolgend werden typische Einstellungen für die Verwendung eines Proxyservers aufgeführt, mit dem Inhalt für Intune-Clients zwischengespeichert wird.

|Einstellung|Empfohlener Wert|Details|
|-----------|---------------------|-----------|
|Cachegröße|5-30 GB|Dieser Wert schwankt abhängig von der Anzahl von Clientcomputern in Ihrem Netzwerk und den von Ihnen verwendeten Konfigurationen. Damit Dateien nicht zu schnell gelöscht werden, stellen Sie die Größe des Zwischenspeichers passend für Ihre Umgebung ein.|
|Größe der einzelnen Cachedatei|950 MB|Diese Einstellung ist möglicherweise nicht für alle Proxyserver mit Zwischenspeicherung verfügbar.|
|Objekttypen, die zwischengespeichert werden|HTTP<br /><br />HTTPS<br /><br />BITS|Intune-Pakete sind CAB-Dateien, die per BITS-Download (Background Intelligent Transfer Service) über HTTP abgerufen wurden.|
Informationen zur Verwendung eines Proxyservers zum Zwischenspeichern von Inhalt entnehmen Sie der Dokumentation zu Ihrer Proxyserverlösung.

### <a name="use-background-intelligent-transfer-service-on-computers"></a>Verwenden von Background Intelligent Transfer Service auf Computern
Intune unterstützt die Verwendung von BITS (Background Intelligent Transfer Service) auf einem Windows-Computer, um die im von Ihnen konfigurierten Zeitraum beanspruchte Netzwerkbandbreite zu verringern. Die BITS-Richtlinie können Sie auf der Seite **Netzwerkbandbreite** der Intune-Agent-Richtlinie konfigurieren.

Weitere Informationen zu BITS und Windows-Computern finden Sie unter [Background Intelligent Transfer Service](http://technet.microsoft.com/library/bb968799.aspx) in der TechNet-Bibliothek.

### <a name="use-branchcache-on-computers"></a>Verwenden von BranchCache auf Computern
Intune-Clients können BranchCache verwenden, um den WAN-Datenverkehr zu verringern. Von den folgenden als Clients unterstützten Betriebssystemen wird auch BranchCache unterstützt:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

Zum Verwenden von BranchCache muss BranchCache auf dem Clientcomputer aktiviert und für den Modus **Verteilter Cache** konfiguriert sein.

Standardmäßig werden BranchCache und der Modus „Verteilter Cache“ auf einem Computer aktiviert, wenn der Intune-Client installiert wird. Wenn auf einem Client jedoch bereits eine Gruppenrichtlinie vorhanden ist, die BranchCache deaktiviert, wird diese Richtlinie von Intune nicht außer Kraft gesetzt, und BranchCache bleibt auf diesem Computer deaktiviert.

Wenn Sie BranchCache verwenden, sprechen Sie mit den Administratoren in Ihrer Organisation, die Gruppenrichtlinien und die Intune-Firewallrichtlinie verwalten, um sicherzustellen, dass sie keine Richtlinien bereitstellen, mit denen BranchCache oder Firewallausnahmen deaktiviert werden. Weitere Informationen zu BranchCache finden Sie unter [BranchCache: Übersicht](http://technet.microsoft.com/library/hh831696.aspx).

## <a name="network-communication-requirements"></a>Anforderungen für die Netzwerkkommunikation

Sie müssen die Netzwerkkommunikation zwischen den verwalteten Geräten, den Geräten zum Verwalten Ihres Intune-Abonnements und den Websites aktivieren, die für cloudbasierte Dienste benötigt werden.

Intune verwendet keine lokale Infrastruktur, z.B. einen Server, auf dem die Intune-Software ausgeführt wird. Es gibt jedoch Optionen zum Verwenden einer lokalen Infrastruktur, darunter Synchronisierungstools für Exchange und Active Directory.

Zum Verwalten von Computern, die sich hinter Firewalls und Proxyservern befinden, müssen Sie die Firewalls und Proxyserver so einrichten, dass die Kommunikation für Intune zugelassen wird.

### <a name="requirements-for-proxy-servers"></a>Anforderungen an Proxyserver
Beim Verwalten von Computern, die sich hinter einem Proxyserver befinden, berücksichtigen Sie Folgendes:

-   Der Proxyserver muss sowohl **HTTP** als auch **HTTPS** unterstützen, da Intune-Clients beide Protokolle verwenden.
-   Intune unterstützt nicht authentifizierte Proxyserver.

Sie können Proxyservereinstellungen entweder auf einzelnen Clientcomputern modifizieren oder mithilfe der Gruppenrichtlinieneinstellungen für alle Clientcomputer hinter einem bestimmten Proxyserver ändern.

### <a name="requirements-for-firewalls-ports-and-domains"></a>Anforderungen an Firewalls, Ports und Domänen
Für verwaltete Geräte sind Konfigurationen erforderlich, über die **Alle Benutzer** über Firewalls auf Dienste zugreifen können.

In der folgenden Tabelle sind die Ports und Dienste aufgeführt, auf die vom Intune-Client zugegriffen wird:

|**Domäne**|**Ports**|**IP-Adresse**|
|------|----|---|
|manage.microsoft.com<br>a.manage.microsoft.com<br>admin.manage.microsoft.com<br>enterpriseenrollment.manage.microsoft.com<br>enterpriseenrollment-s.manage.microsoft.com<br>i.manage.microsoft.com<br>m.manage.microsoft.com<br>p.manage.microsoft.com<br>portal.manage.microsoft.com<br>r.manage.microsoft.com|80 und 443|134.170.168.254<br>134.170.51.126
|account.manage.microsoft.com|80 und 443|157.56.13.59
|fef.msua01.manage.microsoft.com|80 und 443|138.91.243.97
|fef.msua02.manage.microsoft.com|80 und 443|23.96.112.46
|fef.msua04.manage.microsoft.com|80 und 443|23.96.112.28
|fef.msua05.manage.microsoft.com|80 und 443|138.91.244.151
|fef.msub01.manage.microsoft.com|80 und 443|137.135.128.214
|fef.msub02.manage.microsoft.com|80 und 443|137.135.130.29
|fef.msub03.manage.microsoft.com|80 und 443|23.97.165.17
|fef.msub05.manage.microsoft.com|80 und 443|23.97.166.52
|fef.msuc01.manage.microsoft.com|80 und 443|207.46.225.1
|fef.msuc02.manage.microsoft.com|80 und 443|23.98.66.118
|fef.msuc03.manage.microsoft.com|80 und 443|23.101.0.100
|fef.msuc05.manage.microsoft.com|80 und 443|207.46.154.33
|fef.msua06.manage.microsoft.com|80 und 443|104.42.188.1
|fei.msua01.manage.microsoft.com|80 und 443|138.91.240.131
|fei.msua02.manage.microsoft.com|80 und 443|23.96.112.143
|fei.msua04.manage.microsoft.com|80 und 443|23.96.112.147
|fei.msua05.manage.microsoft.com|80 und 443|138.91.240.163
|fei.msub01.manage.microsoft.com|80 und 443|137.135.130.85
|fei.msub02.manage.microsoft.com|80 und 443|137.135.132.149
|fei.msub03.manage.microsoft.com|80 und 443|23.97.160.232
|fei.msub05.manage.microsoft.com|80 und 443|23.97.162.250
|fei.msuc01.manage.microsoft.com|80 und 443|207.46.224.73
|fei.msuc02.manage.microsoft.com|80 und 443|23.98.66.194
|fei.msuc03.manage.microsoft.com|80 und 443|23.101.2.105
|fei.msuc05.manage.microsoft.com|80 und 443|207.46.147.126
|fei.msua06.manage.microsoft.com|80 und 443|138.91.149.190
|m.fei.msua01.manage.microsoft.com|80 und 443|138.91.240.131
|m.fei.msua02.manage.microsoft.com|80 und 443|23.96.112.143
|m.fei.msua04.manage.microsoft.com|80 und 443|23.96.112.147
|m.fei.msua05.manage.microsoft.com|80 und 443|138.91.240.163
|m.fei.msub01.manage.microsoft.com|80 und 443|137.135.130.85
|m.fei.msub02.manage.microsoft.com|80 und 443|137.135.132.149
|m.fei.msub03.manage.microsoft.com|80 und 443|23.97.160.232
|m.fei.msub05.manage.microsoft.com|80 und 443|23.97.162.250
|m.fei.msuc01.manage.microsoft.com|80 und 443|207.46.224.73
|m.fei.msuc02.manage.microsoft.com|80 und 443|23.98.66.194
|m.fei.msuc03.manage.microsoft.com|80 und 443|23.101.2.105
|m.fei.msuc05.manage.microsoft.com|80 und 443|207.46.147.126
|m.fei.msua06.manage.microsoft.com|80 und 443|138.91.149.190
|m.msua01.manage.microsoft.com|80 und 443|157.55.50.182
|m.msua02.manage.microsoft.com|80 und 443|134.170.49.121
|m.msua04.manage.microsoft.com|80 und 443|134.170.49.126
|m.msua05.manage.microsoft.com|80 und 443|157.55.240.190
|m.msua06.manage.microsoft.com|80 und 443|134.170.49.114
|m.msub01.manage.microsoft.com|80 und 443|94.245.121.50
|m.msub02.manage.microsoft.com|80 und 443|94.245.121.58
|m.msub03.manage.microsoft.com|80 und 443|94.245.121.56
|m.msub05.manage.microsoft.com|80 und 443|157.56.113.123
|m.msuc01.manage.microsoft.com|80 und 443|104.44.84.187
|m.msuc02.manage.microsoft.com|80 und 443|104.44.84.188
|m.msuc03.manage.microsoft.com|80 und 443|104.44.84.189
|m.msuc05.manage.microsoft.com|80 und 443|111.221.76.60
|msua01.manage.microsoft.com|80 und 443|157.55.50.182
|msua02.manage.microsoft.com|80 und 443|134.170.49.121
|msua04.manage.microsoft.com|80 und 443|134.170.49.126
|msua05.manage.microsoft.com|80 und 443|157.55.240.190
|msub01.manage.microsoft.com|80 und 443|94.245.121.50
|msub02.manage.microsoft.com|80 und 443|94.245.121.58
|msub03.manage.microsoft.com|80 und 443|94.245.121.56
|msub05.manage.microsoft.com|80 und 443|157.56.113.123
|msuc01.manage.microsoft.com|80 und 443|104.44.84.187
|msuc02.manage.microsoft.com|80 und 443|104.44.84.188
|msuc03.manage.microsoft.com|80 und 443|104.44.84.189
|msuc05.manage.microsoft.com|80 und 443|111.221.76.60
|msua06.manage.microsoft.com|80 und 443|134.170.49.114
|ncufun.account.manage.microsoft.com|80 und 443|157.55.252.224
|neufun.account.manage.microsoft.com|80 und 443|65.52.229.134
|portal.fei.msua01.manage.microsoft.com|80 und 443|138.91.240.131
|portal.fei.msua02.manage.microsoft.com|80 und 443|23.96.112.143
|portal.fei.msua04.manage.microsoft.com|80 und 443|23.96.112.147
|portal.fei.msua05.manage.microsoft.com|80 und 443|138.91.240.163
|portal.fei.msub01.manage.microsoft.com|80 und 443|137.135.130.85
|portal.fei.msub02.manage.microsoft.com|80 und 443|137.135.132.149
|portal.fei.msub03.manage.microsoft.com|80 und 443|23.97.160.232
|portal.fei.msub05.manage.microsoft.com|80 und 443|23.97.162.250
|portal.fei.msuc01.manage.microsoft.com|80 und 443|207.46.224.73
|portal.fei.msuc02.manage.microsoft.com|80 und 443|23.98.66.194
|portal.fei.msuc03.manage.microsoft.com|80 und 443|23.101.2.105
|portal.fei.msuc05.manage.microsoft.com|80 und 443|207.46.147.126
|portal.fei.msua06.manage.microsoft.com|80 und 443|138.91.149.190
|portal.msua01.manage.microsoft.com|80 und 443|157.55.50.182
|portal.msua02.manage.microsoft.com|80 und 443|134.170.49.121
|portal.msua04.manage.microsoft.com|80 und 443|134.170.49.126
|portal.msua05.manage.microsoft.com|80 und 443|157.55.240.190
|portal.msub01.manage.microsoft.com|80 und 443|94.245.121.50
|portal.msub02.manage.microsoft.com|80 und 443|94.245.121.58
|portal.msub03.manage.microsoft.com|80 und 443|94.245.121.56
|portal.msub05.manage.microsoft.com|80 und 443|157.56.113.123
|portal.msuc01.manage.microsoft.com|80 und 443|104.44.84.187
|portal.msuc02.manage.microsoft.com|80 und 443|104.44.84.188
|portal.msuc03.manage.microsoft.com|80 und 443|104.44.84.189
|portal.msuc05.manage.microsoft.com|80 und 443|111.221.76.60
|portal.msua06.manage.microsoft.com|80 und 443|134.170.49.114
|ssu2.manage.microsoft.com|80 und 443|157.55.99.181
|status.manage.microsoft.com|80 und 443|157.55.99.170
|swda01.manage.microsoft.com<br>swda02.manage.microsoft.com<br>swdb01.manage.microsoft.com<br>swdb02.manage.microsoft.com<br>swdc01.manage.microsoft.com<br>swdc02.manage.microsoft.com|80 und 443|93.184.215.200
|*.microsoftonline-p.com|80 und 443||
|has.spserv.microsoft.com<br>Für den Dienst zum Nachweis der Geräteintegrität erforderlich|443||
|*.microsoftonline-p.net|80 und 443||
|*.portal.office.com|80 und 443||
|*.spynet2.microsoft.com|443||
|c.microsoft.com|80 und 443||
|c1.microsoft.com|80 und 443||
|blob.core.windows.net|80 und 443||
|ajax.aspnetcdn.com|80 und 443||
|*.googleapis.com<br>Diese Domäne ist für JQuery-Unterstützung bei Verwendung der Unternehmensportal-Website erforderlich.|80 und 443||
|wustat.microsoft.com|80 und 443||
|Microsoft Update Services|\*.update.microsoft.com<br>download.microsoft.com<br>update.microsoft.com<br>\*.download.windowsupdate.com<br>download.windowsupdate.com<br>\*.windowsupdate.com<br>windowsupdate.microsoft.com<br>ntservicepack.microsoft.com|80 und 443|
|DNS-Lookupanforderungen|manage.microsoft.com.nsatc.net|80|
|Samsung KNOX Standard-Gerätekommunikation über die Firewall|Damit Samsung KNOX Standard-Geräte über die Firewall mit KNOX-Servern kommunizieren können, folgen Sie den Anweisungen in den häufig gestellten Fragen zu Samsung KNOX Standard.||
|Bedingter Zugriff, Kommunikation|443|204.79.197.200|
|Dokumentation, Hilfe und Support:</br></br>*.livemeeting.com<br>\*.microsoftonline.com<br>\*.social.technet.microsoft.com<br>blogs.technet.com<br>go.microsoft.com<br>onlinehelp.Microsoft.com<br>www.microsoft.com|80|||

>[!div class="step-by-step"]

>[&larr; **Voraussetzungen**](supported-mobile-devices-and-computers.md)     [**Netzwerke** &rarr;](start-with-a-paid-subscription-to-microsoft-intune-step-1.md)  



<!--HONumber=Dec16_HO2-->


