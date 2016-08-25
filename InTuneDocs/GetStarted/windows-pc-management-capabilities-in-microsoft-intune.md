---
title: "Funktionen für die Windows-PC-Verwaltung | Microsoft Intune"
description: "Erfahren Sie mehr über die Funktionen von Intune bei der Verwaltung von Windows-PCs mit Intune-Clientsoftware."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a6caef9e0f4d6235ecf1a89c1765d6c8e6ce1a7b
ms.openlocfilehash: e5e3833a38434d4fe55cae554fc49f567b606ad8


---

# Verwaltungsfunktionen für Windows-PCs (mit dem Microsoft Intune-PC-Client)
In den meisten Szenarien registrieren Sie Ihre Geräte bei Microsoft Intune, sodass Sie über eine größere Anzahl von Funktionen verfügen können als mit dem Intune-PC-Client. Allerdings können Sie PCs auch mit dem Intune-PC-Client verwalten, der die folgenden Funktionen bietet:

-   **Softwareupdateverwaltung**: Sie können PCs auf dem aktuellen Stand halten und entscheiden, wann Updates angewendet werden sollen.

-   **Windows-Firewall-Richtlinie**: Hiermit können Sie sicherstellen, dass die Windows-Firewall auf keinem von Ihrem Unternehmen verwendeten PC inaktiv oder nicht ordnungsgemäß konfiguriert ist.

-   **Schutz vor Schadsoftware**: Intune umfasst Endpoint Protection, um Ihre PCs vor Schadsoftware zu schützen.

-   **Remoteunterstützung**: Über Intune können Benutzer Kontakt mit IT-Supportmitarbeitern aufnehmen, die ihnen über eine in Intune integrierte Remotedesktop-Funktion Unterstützung bieten können (erfordert TeamViewer-Software).

-   **Verwaltung von Softwarelizenzen**: Überwachen Sie, wie viele Lizenzen verfügbar sind und wie viele Lizenzen verwendet werden.
-   **App-Bereitstellung**: Stellen Sie Software auf PCs bereit, die Sie verwalten. Einige App-Verwaltungsfunktionen sind nicht verfügbar, wenn Sie PCs mit der Clientsoftware verwalten.


Intune unterstützt die Installation der PC-Clientsoftware auf bis zu 7.000 Windows-Geräten.

## Anforderungen an das Betriebssystem
PCs, die die folgenden Windows-Versionen (jeweils 32-Bit und 64-Bit) ausführen, können mit Intune verwaltet werden:


-   **Windows Vista**: Business-, Enterprise- und Ultimate-Versionen

-   **Windows 7**: Professional-, Enterprise- oder Ultimate-Versionen (ohne Service Pack oder mit SP1)

-   **Windows 8**: Pro- und Enterprise-Versionen

-   **Windows 8.1**: Pro- und Enterprise-Versionen

- **Windows 10**: Pro-, Education- und Enterprise-Versionen


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
|Administratorrechte|Das Konto, mit dem die Clientsoftware installiert wird, muss über lokale Administratorrechte für den PC verfügen.|
|Windows Installer 3.1|Auf dem PC wird Windows Installer 3.1 oder höher benötigt.|
|Entfernen nicht kompatibler Clientsoftware|Bevor Sie die Intune-PC-Clientsoftware installieren, müssen Sie die folgende Clientsoftware auf dem PC deinstallieren:<br /><br />– Alle Configuration Manager-Versionen<br />– Alle Microsoft Systems Management Server-Versionen (SMS)|

### Weitere Informationen:
[Verwaltungsfunktionen für mobile Geräte in Microsoft Intune](./mobile-device-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Aug16_HO3-->


