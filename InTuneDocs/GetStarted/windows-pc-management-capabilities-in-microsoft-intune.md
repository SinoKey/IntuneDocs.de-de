---
title: "Funktionen für die Windows-PC-Verwaltung | Microsoft Intune"
description: "Erfahren Sie mehr über die Funktionen von Intune bei der Verwaltung von Windows-PCs mit Intune-Clientsoftware."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: 28eebfc49eeff6b070ac32a7d2c4bbec59a527b9


---

# Verwaltungsfunktionen für Windows-PCs (mit dem Microsoft Intune-PC-Client)
In den meisten Szenarien registrieren Sie Ihre Geräte bei Microsoft Intune, sodass Sie über eine größere Anzahl von Funktionen verfügen können als mit dem Intune-PC-Client. Allerdings können Sie PCs auch mit dem Intune-PC-Client verwalten, der die folgenden Funktionen bietet:

-   **Verwalten von Softwareupdates**: Sie können PCs auf dem aktuellen Stand halten und festlegen, wann Updates angewendet werden sollen.

-   **Windows-Firewall-Richtlinie**: Hiermit können Sie sicherstellen, dass die Windows-Firewall auf keinem von Ihrem Unternehmen verwendeten PC inaktiv oder nicht ordnungsgemäß konfiguriert ist.

-   **Schutz vor Schadsoftware**: Intune umfasst Endpoint Protection, um Ihre PCs vor Schadsoftware zu schützen.

-   **Remoteunterstützung**: Über Intune können Benutzer Kontakt mit IT-Supportmitarbeitern aufnehmen, die ihnen über eine in Intune integrierte Remotedesktopfunktion Unterstützung bieten können <!--- (requires TeamViewer software)--->.

-   **Verwaltung von Softwarelizenzen**: Überwachen Sie, wie viele Lizenzen verfügbar sind und wie viele Lizenzen verwendet werden.
-   **App-Bereitstellung**: Stellen Sie Software auf PCs bereit, die Sie verwalten. Einige App-Verwaltungsfunktionen sind nicht verfügbar, wenn Sie PCs mit der Clientsoftware verwalten.


Intune unterstützt die Installation der PC-Clientsoftware auf bis zu 7.000 Windows-Geräten.

## Anforderungen an das Betriebssystem
PCs mit den folgenden Windows-Versionen (x86 und x64) können mit Intune verwaltet werden:


-   **Windows Vista**: Business, Enterprise und UltimateEdition.

-   **Windows 7**: Professional, Enterprise oder Ultimate (ohne Service Pack oder mit SP1).

-   **Windows 8**: Pro und Enterprise

-   **Windows 8.1**: Pro und Enterprise

- **Windows 10**: Home, Education, Pro und Enterprise


## Hardwaremindestanforderungen
Im Folgenden sind die Hardwaremindestanforderungen zum Installieren des Intune-PC-Clients aufgeführt:

|Anforderungen|Details|
|---------------|--------------------|
|Netzwerk|Für den Client ist ein PC mit Internetzugriff erforderlich.|
|Prozessor und Arbeitsspeicher|Weitere Informationen entnehmen Sie den Prozessor- und Arbeitsspeicheranforderungen des PC-Betriebssystems.|
|Speicherplatz|200 MB verfügbarer Speicherplatz vor der Installation der Clientsoftware|

## Weitere Anforderungen
Im Folgenden sind die Softwareanforderungen zum Installieren des Intune-PC-Clients aufgeführt:

|Anforderungen|Details|
|---------------|--------------------|
|Administratorrechte|Das Konto, mit dem die Clientsoftware installiert wird, muss über lokale Administratorrechte auf dem PC verfügen.|
|Windows Installer 3.1|Auf dem PC muss Windows Installer 3.1 oder höher installiert sein.|
|Entfernen nicht kompatibler Clientsoftware|Bevor Sie die Intune-PC-Clientsoftware installieren, müssen Sie die folgende Clientsoftware auf dem PC deinstallieren:<br /><br />– Alle Configuration Manager-Versionen<br />– Alle Microsoft Systems Management Server-Versionen (SMS)|

### Weitere Informationen:
[Verwaltungsfunktionen für mobile Geräte in Microsoft Intune](./mobile-device-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


