---
title: "Benutzergerätezuordnung | Microsoft-Dokumentation"
description: "Referenzthema für die Kategorie „Benutzergerätezuordnung“ der Entitätscollection in der Intune Data Warehouse-API"
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 09/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: BCDBABCB-A7B1-42F2-BDD1-D055E33F2239
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 490e29f87c65875a385472e6abe9400363383f9b
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2017
---
# <a name="reference-for-user-device-association-entity"></a>Verweis für die Entität „Benutzergerätezuordnung“

Die Kategorie **Benutzergerätezuordnung** enthält die Entität **Benutzergerätezuordnung**, die zum Definieren von Gerätezuordnungen in Organisationen verwendet wird.

**Benutzergerätezuordnung**

Die Entität **Benutzergerätezuordnung** stellt die Gerätedefinitionszuordnungen in Organisationen dar.

| Name               | Beschreibung                                                                                      | Beispiel                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | Eindeutiger Bezeichner des Benutzers im Data Warehouse – Ersatzschlüssel                             | 123                    |
| DeviceKey          | Eindeutiger Bezeichner für das Gerät im Data Warehouse                                           | 123                    |
| CreatedDateTimeUTC | Datum und Uhrzeit in UTC, als die Benutzergerätezuordnung erstellt wurde                               | 23.11.2016 12:00:00 Uhr |
| IsDeleted          | Gibt an, dass der Benutzer dieses Geräts die Registrierung aufgehoben hat und die Zuordnung nicht mehr aktuell ist | True                   |
| EndedDateTimeUTC   | Datum und Uhrzeit in UTC, als IsDeleted in **TRUE** geändert wurde                                         | 23.06.2017, 12:00:00 Uhr |