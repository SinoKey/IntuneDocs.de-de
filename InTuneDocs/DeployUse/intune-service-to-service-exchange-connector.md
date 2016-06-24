---
# required metadata

title: Konfigurieren des Microsoft Intune Service to Service Connector für Hosted Exchange | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Konfigurieren des Microsoft Intune Service to Service Connector für Hosted Exchange

Anhand dieser Informationen können Sie Microsoft Intune und den von Office 365 gehosteten Exchange Online-Dienst verbinden.

## Anforderungen an Service to Service Connector
Der **Service to Service Connector** unterstützt nur cloudbasiertes Exchange und weist keine Anforderungen an lokale Infrastruktur auf.

|Anforderungen|Weitere Informationen|
|---------------|--------------------|
|Konfiguration und Ausführung von gehostetem Exchange|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Autorität für die Verwaltung mobiler Geräte| [Festlegen von Microsoft Intune als Autorität für die Verwaltung mobiler Geräte](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority)|
|Microsoft Exchange-Version|Sie müssen über ein Office 365-Abonnement mit einem Exchange Server 2013-Mandanten (oder höher) verfügen. Solange der Mandant Exchange Server 2013 (oder höher) ist, wird in der gleichen Umgebung Exchange Server 2010 vom Connector unterstützt.|
|Active Directory-Synchronisierung|Bevor Sie den Intune-Connector verwenden können, müssen Sie die [Active Directory-Synchronisierung einrichten](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3), damit Ihre lokalen Benutzer und Sicherheitsgruppen mit Ihrer Instanz von Azure Active Directory synchronisiert werden.|

### Anforderungen an Exchange-Cmdlets

Sie müssen in Exchange Online ein Benutzerkonto erstellen, das vom Intune Exchange Connector verwendet wird. Das Konto muss über die Berechtigung zum Verwenden der Intune-Verwaltungskonsole und zum Ausführen der erforderlichen Windows PowerShell-Exchange-Cmdlets verfügen:

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## Einrichten des Service to Service Connectors

1. Öffnen Sie die [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) mit einem Benutzerkonto mit Administratorrechten für Exchange und Berechtigungen für die [zuvor genannten](#exchange-cmdlet-requirements) Cmdlets. Microsoft Intune verwendet die E-Mail-Adresse des aktuell angemeldeten Benutzers, um die Verbindung einzurichten.

2.  Wählen Sie im Bereich mit den Arbeitsbereichsverknüpfungen **VERWALTUNG** aus. Wechseln Sie dann zu **Verwaltung mobiler Geräte** > **Microsoft Exchange** > **Exchange-Verbindung einrichten**..
![Seite „Service to Service Connector einrichten“](../media/intunesa5cservicetoserviceconnector.png)

3.  Wählen Sie auf der Seite **Exchange-Verbindung einrichten** die Option **Service to Service Connector einrichten** aus..


Der Service to Service Connector wird automatisch konfiguriert und mit Ihrer gehosteten Exchange-Umgebung synchronisiert.

## Überprüfen der Exchange-Verbindung

Nachdem Sie den Exchange-Connector erfolgreich konfiguriert haben, wählen Sie in der Intune-Verwaltungskonsole den Arbeitsbereich **VERWALTUNG** aus. Wechseln Sie zu **Verwaltung mobiler Geräte** > **Microsoft Exchange**, und überprüfen Sie die unter **Exchange-Verbindungsinformationen** angezeigten Details..

Sie können auch die Uhrzeit und das Datum des letzten erfolgreichen Synchronisationsversuchs überprüfen.


<!--HONumber=May16_HO1-->


