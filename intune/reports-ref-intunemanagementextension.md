---
title: IntuneManagementExtension Entity | Microsoft-Dokumentation
description: "Referenzthema für die Entitätskategorie „IntuneManagementExtension“ von Entitätensammlungen in der Intune Data Warehouse-API."
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 93a5fde5f0c6ac870104ab90035e119757064cb3
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="reference-for-intune-management-extension"></a>Referenz für die Intune-Verwaltungserweiterung

Die Kategorie **IntuneManagementExtension** enthält Entitäten für mobile Geräte zur Nachverfolgung von Informationen wie etwa der folgenden:

  -  Versionen einer IntuneManagementExtension
  -  Installationsstatus einer IntuneManagementExtension

## <a name="intunemanagementextensionversion"></a>IntuneManagementExtensionVersion

Die Entität **IntuneManagementExtensionVersion** listet alle von IntuneManagementExtension verwendeten Versionen auf.

| Eigenschaft  | Beschreibung | Beispiel |
|---------|------------|--------|
| ExtensionVersionKey |Eindeutiger Bezeichner für die IntuneManagementExtension-Version. | 1 |
| ExtensionVersion |Die vierstellige Versionsnummer |1.0.2.0 |

## <a name="intunemanagementextensionhealthstate"></a>IntuneManagementExtensionHealthState

**IntuneManagementExtensionHealthState** listet alle möglichen Status der IntuneManagementExtension auf.

| Eigenschaft  | Beschreibung | Beispiel |
|---------|------------|--------|
| ExtensionStateKey |Eindeutiger Bezeichner des Integritätszustands | 2 |
| ExtensionState |Der Integritätsstatus einer IntuneManagementExtension | Healthy |

## <a name="intunemanagementextension"></a>IntuneManagementExtension

Die **IntuneManagementExtension** listet täglich den Integritätsstatus von IntuneManagementExtension auf jedem Windows 10-Gerät auf.
Die Daten der letzten 60 Tage werden aufbewahrt. 

| Eigenschaft  | Beschreibung | Beispiel |
|---------|------------|--------|
| DateKey |Eindeutiger Datumsbezeichner | 123 |
| TenantKey |Eindeutiger Mandantenbezeichner | 456 |
| DeviceKey |Eindeutiger Bezeichner des Geräts | 789 |
| ExtensionVersionKey |Eindeutiger Bezeichner für die IntuneManagementExtension-Version. | 1 |
| ExtensionStateKey|Eindeutiger Bezeichner des Integritätszustands | 2 |