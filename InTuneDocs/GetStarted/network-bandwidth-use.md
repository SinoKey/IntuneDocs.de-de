---
title: Nutzung der Netzwerkbandbreite durch Intune | Microsoft Intune
description: Nutzung der Netzwerkbandbreite durch Intune
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0c1e08cc49d75303f6793894e3c8a040f6e7a8b1
ms.openlocfilehash: b40c5ce0d4447b10ec949af6933f28b091136315


---

# Nutzung der Netzwerkbandbreite durch Intune

Bevor Sie [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] einrichten, lesen Sie dieses Thema und andere Anforderungen, die unter [ Was Sie wissen sollten, bevor Sie Microsoft Intune starten](what-to-know-before-you-start-microsoft-intune.md) aufgeführt sind.

Planen Sie anhand der Informationen in den folgenden Abschnitten den Netzwerkdatenverkehr für [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)]-Clients.

## Durchschnittlicher Netzwerkdatenverkehr
In der folgenden Tabelle sind der ungefähre Umfang und die Häufigkeit gemeinsamer Inhalte aufgeführt, die je Client über das Netzwerk übertragen werden.

> [!NOTE]
> Um sicherzustellen, dass Computer und mobile Geräte die erforderlichen Updates und Inhalte von dem [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Dienst erhalten, müssen sie in regelmäßigen Abständen mit dem Internet verbunden werden. Die Zeit für das Empfangen von Updates oder Inhalten kann variieren, als Richtlinie gilt jedoch, dass sie für mindestens eine Stunde pro Tag kontinuierlich mit dem Internet verbunden sein sollen.

|Art des Inhalts|Ungefähre Größe|Häufigkeit und Details|
|----------------|--------------------|-------------------------|
|[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] -Clientinstallation<br /><br />**Die folgenden Anforderungen gelten zusätzlich zur [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Clientinstallation**|125 MB|**Einmalig**<br /><br />Der Umfang des Clientdownloads schwankt je nach Betriebssystem des Clientcomputers.|
|Clientregistrierungspaket|15 MB|**Einmalig**<br /><br />Weitere Downloads sind möglich, wenn Updates für diesen Inhaltstyp vorliegen.|
|Endpoint Protection-Agent|65 MB|**Einmalig**<br /><br />Weitere Downloads sind möglich, wenn Updates für diesen Inhaltstyp vorliegen.|
|Operations Manager-Agent|11 MB|**Einmalig**<br /><br />Weitere Downloads sind möglich, wenn Updates für diesen Inhaltstyp vorliegen.|
|Richtlinien-Agent|3 MB|**Einmalig**<br /><br />Weitere Downloads sind möglich, wenn Updates für diesen Inhaltstyp vorliegen.|
|Remoteunterstützung über den Microsoft Easy Assist-Agent|6 MB|**Einmalig**<br /><br />Weitere Downloads sind möglich, wenn Updates für diesen Inhaltstyp vorliegen.|
|Tägliche Clientvorgänge|6 MB|**Täglich**<br /><br />Durch den [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Client wird regelmäßig mit dem [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Dienst kommuniziert, um nach Updates und Richtlinien zu suchen und den Status des Clients an den Dienst zu melden.|
|Malwaredefinitionsupdates für Endpoint Protection|Variiert<br /><br />Normalerweise zwischen 40 KB und 2 MB|**Täglich**<br /><br />Bis zu drei Mal täglich.|
|Endpoint Protection-Modulupdate|5 MB|**Monatlich**|
|Softwareupdates|Variiert<br /><br />Die Größe hängt von den von Ihnen bereitgestellten Updates ab.|**Monatlich**<br /><br />Normalerweise werden Softwareupdates am zweiten Dienstag eines jeden Monats bereitgestellt.<br /><br />Durch einen neu registrierten oder bereitgestellten Computer kann mehr Netzwerkbandbreite verwendet werden, solange alle zuvor veröffentlichten Updates heruntergeladen werden.|
|Service Packs|Variiert<br /><br />Die Größe variiert für jedes von Ihnen bereitgestellte Service Pack.|**Variiert**<br /><br />Hängt vom Zeitpunkt der Service Pack-Bereitstellung ab.|
|Softwareverteilung|Variiert<br /><br />Die Größe hängt von der von Ihnen bereitgestellten Software ab.|**Variiert**<br /><br />Hängt vom Zeitpunkt der Softwarebereitstellung ab.|

## Möglichkeiten zum Verringern der Bandbreitennutzung
Mithilfe der folgenden Methoden können Sie die Nutzung der Netzwerkbandbreite für [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Clients reduzieren.

### Verwenden eines Proxyservers zum Zwischenspeichern von Inhaltsanforderungen
Mithilfe eines Proxyservers zur Zwischenspeicherung von Inhalt können Sie doppelte Downloads vermeiden und die Bandbreitennutzung durch Clients verringern, von denen Inhalte aus dem Internet angefordert werden.

Von einem zwischenspeichernden Proxyserver werden Inhaltsanforderungen der Clientcomputer in Ihrem Netzwerk empfangen, diese Inhalte aus dem Internet abgerufen und dann zwischengespeichert. Dies schließt sowohl HTTP-Antworten als auch binäre Downloads ein. Nachfolgende Anforderungen von [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Clientcomputern werden dann vom Server unter Verwendung der zwischengespeicherten Daten beantwortet.

Nachfolgend aufgeführt sind typische Einstellungen für die Verwendung eines Proxyservers, mit dem Inhalt für [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Clients zwischengespeichert wird.

|Einstellung|Empfohlener Wert|Details|
|-----------|---------------------|-----------|
|Cachegröße|5-30 GB|Dieser Wert schwankt abhängig von der Anzahl von Clientcomputern in Ihrem Netzwerk und den von Ihnen verwendeten Konfigurationen. Damit Dateien nicht zu schnell gelöscht werden, stellen Sie die Größe des Zwischenspeichers passend für Ihre Umgebung ein.|
|Größe der einzelnen Cachedatei|950 MB|Diese Einstellung ist möglicherweise nicht für alle Proxyserver mit Zwischenspeicherung verfügbar.|
|Objekttypen, die zwischengespeichert werden|HTTP<br /><br />HTTPS<br /><br />BITS|[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] -Pakete sind CAB-Dateien, die von BITS-Downloads (Background Intelligent Transfer Service) über HTTP abgerufen wurden.|
Informationen zur Verwendung eines Proxyservers zum Zwischenspeichern von Inhalt entnehmen Sie der Dokumentation zu Ihrer Proxyserverlösung.

### Verwenden von Background Intelligent Transfer Service auf Computern
[!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] unterstützt, um die während der Konfiguration beanspruchte Netzwerkbandbreite zu verringern. Die BITS-Richtlinie können Sie auf der Seite **Netzwerkbandbreite** der [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Agent-Richtlinie konfigurieren.

Weitere Informationen zu BITS und Windows-Computern finden Sie unter [Background Intelligent Transfer Service](http://technet.microsoft.com/library/bb968799.aspx) in der TechNet-Bibliothek.

### Verwenden von BranchCache auf Computern
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] -Clients kann der WAN-Datenverkehr verringert werden. Von den folgenden als Clients unterstützten Betriebssystemen wird auch BranchCache unterstützt:

-   [!INCLUDE[nextref_client_7](../includes/nextref_client_7_md.md)]

-   [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)]

-   [!INCLUDE[winblue_client_2](../includes/winblue_client_2_md.md)]

Zum Verwenden von BranchCache muss BranchCache auf dem Clientcomputer aktiviert und für den Modus **Verteilter Cache** konfiguriert sein.

Standardmäßig werden BranchCache und der Modus Verteilter Cache auf einem Computer aktiviert, wenn der [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Client installiert wird. Wenn auf einem Client jedoch bereits Gruppenrichtlinien vorhanden sind, von denen BranchCache deaktiviert wird, wird diese Richtlinie von [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] nicht außer Kraft gesetzt, und BranchCache bleibt auf diesem Computer deaktiviert.

Wenn Sie BranchCache verwenden, sprechen Sie mit den Administratoren in Ihrer Organisation, die Gruppenrichtlinien und die [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)]-Firewall-Richtlinie verwalten, um sicherzustellen, dass sie keine Richtlinien bereitstellen, von denen BranchCache oder Firewall-Ausnahmen deaktiviert werden. Weitere Informationen zu BranchCache finden Sie unter [BranchCache: Übersicht](http://technet.microsoft.com/library/hh831696.aspx).

### Weitere Informationen:
[Was Sie wissen sollten, bevor Sie Microsoft Intune starten](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Aug16_HO5-->


