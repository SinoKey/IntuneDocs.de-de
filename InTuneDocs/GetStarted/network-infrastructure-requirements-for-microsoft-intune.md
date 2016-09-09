---
title: Anforderungen an die Netzwerkinfrastruktur | Microsoft Intune
description: "Anforderungen an Firewall, Port, Domäne und Proxyserver"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 074de65b-84a5-4a01-a824-18ffd838eab0
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0c1e08cc49d75303f6793894e3c8a040f6e7a8b1
ms.openlocfilehash: e1e855bcd8ef617fa5383e757ee844603978feac


---

# Anforderungen an die Netzwerkinfrastruktur für Microsoft Intune
Bevor Sie Microsoft Intune einrichten, lesen Sie dieses Thema und andere Anforderungen, die unter [Was Sie wissen sollten, bevor Sie Microsoft Intune starten](what-to-know-before-you-start-microsoft-intune.md) aufgeführt sind.

Die in diesem Thema aufgeführten Anforderungen ermöglichen es Ihrer Netzwerkinfrastruktur, die Kommunikation zwischen den Geräten, die Sie verwalten und für die Verwaltung Ihres Intune-Abonnements verwenden, und den Websites im Internet zu übertragen, die vom cloudbasierten Dienst verwendet werden.

Es ist nicht erforderlich, eine lokale Infrastruktur (z. B. einen Server, bei dem Sie Software installieren müssen) zu verwenden. Es gibt jedoch Optionen zum Verwenden von lokaler Infrastruktur einschließlich Synchronisierungstools für Exchange und Active Directory.

Zum Verwalten von Computern, die sich hinter Firewalls und Proxyservern befinden, müssen Sie die Firewalls und Proxyserver so einrichten, dass die Kommunikation für Intune zugelassen wird.

## Anforderungen an Firewalls, Ports und Domänen
Für verwaltete Geräte sind Konfigurationen erforderlich, über die **Alle Benutzer** über Firewalls auf verschiedene Dienste zugreifen können.

In der folgenden Tabelle sind die Ports und Dienste aufgeführt, auf die vom Intune-Client zugegriffen wird:


|**Domain**|**Ports**|**IP-Adresse**|
|------|----|
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
|Samsung KNOX-Gerätekommunikation über die Firewall|Damit Samsung KNOX-Geräte über die Firewall mit KNOX-Servern in Kontakt treten können, befolgen Sie die Anweisungen unter „Samsung KNOX FAQ“.||
|Bedingter Zugriff, Kommunikation|443|204.79.197.200|
|Dokumentation, Hilfe und Support:</br></br>*.livemeeting.com<br>\*.microsoftonline.com<br>\*.social.technet.microsoft.com<br>blogs.technet.com<br>go.microsoft.com<br>onlinehelp.Microsoft.com<br>www.microsoft.com|80|||



## Anforderungen an Proxyserver
Beim Verwalten von Computern, die sich hinter einem Proxyserver befinden, berücksichtigen Sie Folgendes:

-   Der Proxyserver muss sowohl **HTTP** als auch **HTTPS** unterstützen, da Intune-Clients beide Protokolle verwenden.

-   Intune unterstützt nicht authentifizierte Proxyserver.

Sie können Proxyservereinstellungen entweder auf einzelnen Clientcomputern modifizieren oder mithilfe der Gruppenrichtlinieneinstellungen für alle Clientcomputer hinter einem bestimmten Proxyserver ändern.

Sie können auch einen Proxyserver verwenden, der Inhalte zwischenspeichert, um die [Netzwerkbandbreite zu verringern](network-bandwidth-use.md), die von Intune-Clients verwendet wird.


### Weitere Informationen:
[Was Sie wissen sollten, bevor Sie Microsoft Intune starten](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Aug16_HO5-->


