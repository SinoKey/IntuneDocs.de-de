---
title: "Änderungsprotokoll für Intune Data Warehouse | Microsoft-Dokumentation"
description: "Eine Liste der Änderungen in der Intune Data Warehouse-API."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6d675a36cd5ea4c11d755174bf2b0bbc5d4b18ec
ms.sourcegitcommit: 5279a0bb8c5aef79aa57aa247ad95888ffe5a12b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2017
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Änderungsprotokoll für die Intune Data Warehouse-API

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bleiben Sie auf dem neuesten Stand bezüglich Updates für Intune Data Warehouse.

## <a name="1710"></a>1710
_Veröffentlicht im November 2017_

### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>Die Benutzerentität enthält die aktuellen Benutzerdaten im Data Warehouse-Datenmodell <!-- 1544273 -->

Die erste Version des Intune Data Warehouse-Datenmodells enthielt lediglich aktuelle Verlaufsdaten für Intune. Berichtersteller konnten den aktuellen Status eines Benutzers nicht erfassen. In diesem Update wird die [**Benutzerentität**](reports-ref-user.md) mit den aktuellen Benutzerdaten aufgefüllt.

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Neue Entitäten im Data Warehouse-Datenmodell<!-- 1479526 --><!-- -->

 - Die Entität [**UserDeviceAssociation**](reports-ref-user-device.md) wurde hinzugefügt. **UserDeviceAssociation** enthält Zuweisungen von Benutzergeräten in Ihrer Organisation.
 - Die Entität [ **IntuneManagementExtension**](reports-ref-intunemanagementextension.md) wurde hinzugefügt. **IntuneManagementExtension** enthält Entitäten für mobile Geräte zur Nachverfolgung von Informationen, wie z. B. Version und Installationsstatus.

## <a name="next-steps"></a>Nächste Schritte
 - Erfahren Sie [jede Woche die Neuerungen in Intune](whats-new.md). Sie erhalten auch Informationen zu bevorstehenden Änderungen, wichtige Hinweise zum Dienst und Informationen zu vorherigen Releases. 
 - Lesen Sie den [Microsoft Intune-Blog](http://go.microsoft.com/fwlink/?LinkID=273882).