---
title: Nutzung der Netzwerkbandbreite durch Intune | Microsoft-Dokumentation
description: Nutzung der Netzwerkbandbreite durch Intune
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/04/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 0c7f813e00eebc9113ce9e395c02bf8e58e6d15c
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---

# <a name="intune-network-bandwidth-use"></a>Nutzung der Netzwerkbandbreite durch Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Diese Anleitung klärt Intune-Administratoren über die Netzwerkanforderungen für den Intune-Dienst auf. Mithilfe dieser Informationen können Sie feststellen, welche Bandbreitenanforderungen gestellt werden und welche IP-Adressen und Porteinstellungen für die Proxyeinstellungen erforderlich sind.

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

Zum Verwalten von Computern, die sich hinter Firewalls und Proxyservern befinden, müssen Sie die Firewalls und Proxyserver so einrichten, dass die Kommunikation für Intune zugelassen wird. Beim Verwalten von Computern, die sich hinter einem Proxyserver befinden, berücksichtigen Sie Folgendes:

-   Der Proxyserver muss sowohl **HTTP** (80) als auch **HTTPS** (443) unterstützen, da Intune-Clients beide Protokolle verwenden.
-   Intune unterstützt nicht authentifizierte Proxyserver.

Sie können Proxyservereinstellungen entweder auf einzelnen Clientcomputern modifizieren oder mithilfe der Gruppenrichtlinieneinstellungen für alle Clientcomputer hinter einem bestimmten Proxyserver ändern.

Für verwaltete Geräte sind Konfigurationen erforderlich, über die **Alle Benutzer** über Firewalls auf Dienste zugreifen können.

In den folgenden Tabellen sind die Ports und Dienste aufgeführt, auf die der Intune-Client zugreift:

|**Domänen**|**IP-Adresse**|
|---------------------|-----------|
|portal.manage.microsoft.com<br> m.manage.microsoft.com |40.86.181.86<br>13.82.59.78<br>13.74.184.100<br>40.68.188.2<br>13.75.42.6<br>52.230.25.184 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 104.40.82.191 <br>13.82.96.212 <br>52.169.9.87 <br>52.174.26.23 <br>40.83.123.72 <br>13.76.177.110 |
|portal.fei.msua01.manage.microsoft.com<br>m.fei.msua01.manage.microsoft.com |13.64.196.170|
|fei.msua01.manage.microsoft.com<br> portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com |40.71.34.120 |
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com |13.64.198.190|
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br> m.fei.msua02.manage.microsoft.com |    13.64.198.190|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |13.64.188.173|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |40.71.32.174|
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |13.64.197.181 |
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |40.71.38.205|
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |13.64.191.182 |
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |40.71.37.51 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |40.118.250.246 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |13.90.142.194 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.64.250.226 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.90.151.142 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.169.155.165 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.174.188.97 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.178.190.24 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.174.16.215 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |40.69.69.27 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |52.166.196.199 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |40.69.71.164 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |52.174.182.102 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |40.69.78.145 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |52.174.192.105 |
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |13.94.46.250|
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |52.163.119.15 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |13.75.124.145 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |52.163.119.5|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.175.35.226|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.163.119.6|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.175.38.24|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.163.119.3|

