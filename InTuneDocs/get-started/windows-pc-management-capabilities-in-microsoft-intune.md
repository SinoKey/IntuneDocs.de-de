---
title: Funktionen des Intune-PC-Softwareclients | Microsoft-Dokumentation
description: "Erfahren Sie mehr über die Funktionen von Intune bei der Verwaltung von Windows-PCs mit dem Intune-Softwareclient."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f268cf29461447306d0f5c3ca06d541d9a03a49d
ms.openlocfilehash: 36a20feed1756ea8dde2230db81099b6c5f8c7f6


---

# <a name="windows-pc-management-capabilities-when-you-use-the-intune-software-client"></a>Funktionen zur Verwaltung von Windows-PCs bei Verwendung des Intune-Softwareclients

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

In den meisten Szenarios registrieren Sie Ihre Geräte bei Microsoft Intune, sodass Sie über eine größere Anzahl von Funktionen verfügen. Allerdings können Sie PCs auch mit dem Intune-Softwareclient verwalten, der die folgenden Funktionen bietet:

-   **[Softwareupdateverwaltung](/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)**: Sie können PCs auf dem aktuellen Stand halten und entscheiden, wann Updates angewendet werden sollen.

-   **[Windows-Firewall-Richtlinie](/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)**: Hiermit können Sie sicherstellen, dass die Windows-Firewall auf keinem von Ihrem Unternehmen verwendeten PC inaktiv oder nicht ordnungsgemäß konfiguriert ist.

-   **[Schutz vor Schadsoftware](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)**: Intune umfasst Endpoint Protection, um Ihre PCs vor Schadsoftware zu schützen.

-   **[Remoteunterstützung](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#request-and-provide-remote-assistance-to-windows-pcs-that-use-the-intune-client-software )**: Über Intune können Benutzer Kontakt mit IT-Supportmitarbeitern aufnehmen, die ihnen über eine in Intune integrierte Remotedesktop-Funktion Unterstützung bieten können (erfordert TeamViewer-Software).

-   **[Verwaltung von Softwarelizenzen](/intune/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)**: Überwachen Sie, wie viele Lizenzen verfügbar sind und wie viele Lizenzen verwendet werden.
-   **[App-Bereitstellung](/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)**: Stellen Sie Software auf PCs bereit, die Sie verwalten. Einige App-Verwaltungsfunktionen sind nicht verfügbar, wenn Sie PCs mit dem Softwareclient verwalten.


Intune unterstützt die Installation des Softwareclients auf bis zu 7.000 Windows-Geräten.

## <a name="operating-system-requirements"></a>Anforderungen an das Betriebssystem
PCs, die die folgenden Windows-Versionen (jeweils 32-Bit und 64-Bit) ausführen, können mit Intune verwaltet werden:


-   **Windows Vista**: Business-, Enterprise- und Ultimate-Versionen

-   **Windows 7**: Professional-, Enterprise- oder Ultimate-Versionen (ohne Service Pack oder mit SP1)

-   **Windows 8**: Pro- und Enterprise-Versionen

-   **Windows 8.1**: Pro- und Enterprise-Versionen

- **Windows 10**: Pro-, Education- und Enterprise-Versionen


## <a name="minimum-hardware-requirements"></a>Hardwaremindestanforderungen
Im Folgenden sind die Hardwaremindestanforderungen zum Installieren des Intune-Softwareclients aufgeführt:

|Anforderungen|Details|
|---------------|--------------------|
|Netzwerk|Für den Client ist ein PC mit Internetzugriff erforderlich.|
|Prozessor und Arbeitsspeicher|Weitere Informationen entnehmen Sie den Prozessor- und Arbeitsspeicheranforderungen des PC-Betriebssystems.|
|Speicherplatz|200 MB verfügbarer Speicherplatz vor der Installation der Clientsoftware|

## <a name="further-requirements"></a>Weitere Anforderungen
Im Folgenden sind die Softwareanforderungen zum Installieren des Intune-Softwareclients aufgeführt:

|Anforderungen|Details|
|---------------|--------------------|
|Administratorrechte|Das Konto, mit dem die Clientsoftware installiert wird, muss über lokale Administratorrechte für den PC verfügen.|
|Windows Installer 3.1|Auf dem PC wird Windows Installer 3.1 oder höher benötigt.|
|Entfernen nicht kompatibler Clientsoftware|Bevor Sie die Intune-PC-Clientsoftware installieren, müssen Sie die folgende Clientsoftware auf dem PC deinstallieren:<br /><br />– Alle Configuration Manager-Versionen<br />– Alle Microsoft Systems Management Server-Versionen (SMS)|

### <a name="see-also"></a>Weitere Informationen:
[Verwaltungsfunktionen für registrierte Geräte in Microsoft Intune](./mobile-device-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Dec16_HO3-->


