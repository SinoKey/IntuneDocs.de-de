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
ms.openlocfilehash: b81846c2e45f968184d50d2ea7c50aabb86b4964
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2017
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Änderungsprotokoll für die Intune Data Warehouse-API

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bleiben Sie auf dem neuesten Stand bezüglich Updates für Intune Data Warehouse.

## <a name="1710"></a>1710
_Veröffentlicht: Oktober 2017_

### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>Die Benutzerentität enthält die aktuellen Benutzerdaten im Data Warehouse-Datenmodell <!-- 1544273 -->

Die erste Version des Intune Data Warehouse-Datenmodells enthielt lediglich aktuelle Verlaufsdaten für Intune. Berichtersteller konnten den aktuellen Status eines Benutzers nicht erfassen. In diesem Update wird die [**Benutzerentität**](reports-ref-user.md) mit den aktuellen Benutzerdaten aufgefüllt.

### <a name="new-entity-in-the-in-data-warehouse-data-model----1479526---"></a>Neue Entitäten im Data Warehouse-Datenmodell <!-- 1479526 -->

Die Entität [**UserDeviceAssociation**](reports-ref-user-device.md) wurde hinzugefügt. **UserDeviceAssociation** enthält Zuweisungen von Benutzergeräten in Ihrer Organisation.

## <a name="next-steps"></a>Nächste Schritte
 - Erfahren Sie [jede Woche die Neuerungen in Intune](whats-new.md). Sie erhalten auch Informationen zu bevorstehenden Änderungen, wichtige Hinweise zum Dienst und Informationen zu vorherigen Releases. 
 - Lesen Sie den [Microsoft Intune-Blog](http://go.microsoft.com/fwlink/?LinkID=273882).