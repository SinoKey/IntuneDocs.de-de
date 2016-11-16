---
title: Funktionen des Intune-PC-Softwareclients | Microsoft Intune
description: "Erfahren Sie mehr über die Funktionen von Intune bei der Verwaltung von Windows-PCs mit dem Intune-Softwareclient."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: e786cd33b5c963fa373d281e93721d0dd0f5456c


---

# Funktionen zur Verwaltung von Windows-PCs bei Verwendung des Intune-Softwareclients
In den meisten Szenarios registrieren Sie Ihre Geräte bei Microsoft Intune, sodass Sie über eine größere Anzahl von Funktionen verfügen. Allerdings können Sie PCs auch mit dem Intune-Softwareclient verwalten, der die folgenden Funktionen bietet:

-   **[Softwareupdateverwaltung](/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)**: Sie können PCs auf dem aktuellen Stand halten und entscheiden, wann Updates angewendet werden sollen.

-   **[Windows-Firewall-Richtlinie](/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)**: Hiermit können Sie sicherstellen, dass die Windows-Firewall auf keinem von Ihrem Unternehmen verwendeten PC inaktiv oder nicht ordnungsgemäß konfiguriert ist.

-   **[Schutz vor Schadsoftware](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)**: Intune umfasst Endpoint Protection, um Ihre PCs vor Schadsoftware zu schützen.

-   **[Remoteunterstützung](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#request-and-provide-remote-assistance-to-windows-pcs-that-use-the-intune-client-software )**: Über Intune können Benutzer Kontakt mit IT-Supportmitarbeitern aufnehmen, die ihnen über eine in Intune integrierte Remotedesktop-Funktion Unterstützung bieten können (erfordert TeamViewer-Software).

-   **[Verwaltung von Softwarelizenzen](/intune/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)**: Überwachen Sie, wie viele Lizenzen verfügbar sind und wie viele Lizenzen verwendet werden.
-   **[App-Bereitstellung](/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)**: Stellen Sie Software auf PCs bereit, die Sie verwalten. Einige App-Verwaltungsfunktionen sind nicht verfügbar, wenn Sie PCs mit dem Softwareclient verwalten.


Intune unterstützt die Installation des Softwareclients auf bis zu 7.000 Windows-Geräten.

## Anforderungen an das Betriebssystem
PCs, die die folgenden Windows-Versionen (jeweils 32-Bit und 64-Bit) ausführen, können mit Intune verwaltet werden:


-   **Windows Vista**: Business-, Enterprise- und Ultimate-Versionen

-   **Windows 7**: Professional-, Enterprise- oder Ultimate-Versionen (ohne Service Pack oder mit SP1)

-   **Windows 8**: Pro- und Enterprise-Versionen

-   **Windows 8.1**: Pro- und Enterprise-Versionen

- **Windows 10**: Pro-, Education- und Enterprise-Versionen


## Hardwaremindestanforderungen
Im Folgenden sind die Hardwaremindestanforderungen zum Installieren des Intune-Softwareclients aufgeführt:

|Anforderungen|Details|
|---------------|--------------------|
|Netzwerk|Für den Client ist ein PC mit Internetzugriff erforderlich.|
|Prozessor und Arbeitsspeicher|Weitere Informationen entnehmen Sie den Prozessor- und Arbeitsspeicheranforderungen des PC-Betriebssystems.|
|Speicherplatz|200 MB verfügbarer Speicherplatz vor der Installation der Clientsoftware|

## Weitere Anforderungen
Im Folgenden sind die Softwareanforderungen zum Installieren des Intune-Softwareclients aufgeführt:

|Anforderungen|Details|
|---------------|--------------------|
|Administratorrechte|Das Konto, mit dem die Clientsoftware installiert wird, muss über lokale Administratorrechte für den PC verfügen.|
|Windows Installer 3.1|Auf dem PC wird Windows Installer 3.1 oder höher benötigt.|
|Entfernen nicht kompatibler Clientsoftware|Bevor Sie die Intune-PC-Clientsoftware installieren, müssen Sie die folgende Clientsoftware auf dem PC deinstallieren:<br /><br />– Alle Configuration Manager-Versionen<br />– Alle Microsoft Systems Management Server-Versionen (SMS)|

### Weitere Informationen:
[Verwaltungsfunktionen für registrierte Geräte in Microsoft Intune](./mobile-device-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Oct16_HO4-->


