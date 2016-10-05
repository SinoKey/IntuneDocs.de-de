---
title: "Exchange-Connector für Exchange Online | Microsoft Intune"
description: "Verbinden Sie Intune mit dem Office 365-Exchange-Dienst, um die Verwaltung mobiler Geräte (Mobile Device Management, MDM) mit Exchange ActiveSync zu unterstützen."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c880bd9dfb998355a18e78af898a96d4cee393f7
ms.openlocfilehash: a6438bb3ca21e5c46dca5ebe69266fd9bce9a4b8


---

# Konfigurieren des Microsoft Intune Service to Service Connector für Hosted Exchange

Anhand dieser Informationen können Sie Microsoft Intune und Exchange Online oder den neuen Exchange Online Dedicated-Dienst verbinden. Wenn Sie herausfinden möchten, ob es sich bei Ihrer Exchange Online Dedicated-Umgebung um die **neue** oder die **ältere** Konfiguration handelt, wenden Sie sich an Ihren Kundenbetreuer. Intune unterstützt pro Abonnement nur eine Exchange Connector-Verbindung eines beliebigen Typs.

## Anforderungen an Service to Service Connector
Der **Service to Service Connector** unterstützt nur Exchange Online oder das neue Exchange Cloud Dedicated und stellt keine Anforderungen an die lokale Infrastruktur.

|Anforderungen|Weitere Informationen|
|---------------|--------------------|
|Konfiguration und Ausführung von Exchange Online|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Autorität für die Verwaltung mobiler Geräte| [Festlegen von Microsoft Intune als Autorität für die Verwaltung mobiler Geräte](prerequisites-for-enrollment.md#set-mobile-device-management-authority)|
|Microsoft Exchange-Version|Exchange Online oder Exchange Online Dedicated (neu)|
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

2.  Wählen Sie im Bereich mit den Arbeitsbereichsverknüpfungen **ADMIN** aus. Gehen Sie anschließend zu **Verwaltung mobiler Geräte** > **Microsoft Exchange** > **Exchange-Verbindung einrichten**.
![Seite „Service to Service Connector einrichten“](../media/intunesa5cservicetoserviceconnector.png)

3.  Wählen Sie auf der Seite **Exchange-Verbindung einrichten** die Option **Dienst für Service Connector einrichten** aus.


Der Service to Service Connector wird automatisch konfiguriert und mit Ihrer Exchange Online- oder neuen Exchange Online Dedicated-Umgebung synchronisiert.

## Überprüfen der Exchange-Verbindung

Nachdem Sie den Exchange Connector erfolgreich konfiguriert haben, wählen Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) den Arbeitsbereich **Verwaltung** aus. Wechseln Sie zu **Verwaltung mobiler Geräte** > **Microsoft Exchange**, und stellen Sie sicher, dass die von Ihnen bereitgestellten Details unter **Exchange-Verbindungsinformationen** angezeigt werden.

Sie können auch die Uhrzeit und das Datum des letzten erfolgreichen Synchronisationsversuchs überprüfen.



<!--HONumber=Sep16_HO4-->


