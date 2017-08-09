---
title: Datenmodell von Data Warehouse | Microsoft-Dokumentation
description: "Intune Data Warehouse prüft täglich die Daten, um eine Verlaufsansicht Ihrer sich ständig ändernden mobilen Umgebung bereitzustellen."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4D04D3D9-4B6C-41CD-AAF8-466AF8FA6032
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d56935bc2828273af28323e40d9f3b4e2bd84025
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2017
---
# <a name="data-warehouse-data-model"></a>Datenmodell von Data Warehouse

Intune Data Warehouse prüft täglich die Daten, um eine Verlaufsansicht Ihrer sich ständig ändernden mobilen Umgebung bereitzustellen.

Die Daten aus Ihrem Mandanten werden in einem Data Warehouse zusammengeführt. Das Warehouse besteht aus einer Reihe von Entitäten und Beziehungen, die für die Arten von Fragen aussagekräftig sind, die Sie stellen möchten. Beispielsweise können Sie die Anzahl der Installationen einer intern entwickelten Android-Anwendung pro Tag im Laufe der letzten Woche analysieren, und damit prüfen, ob es einen Aufwärtstrend bei den Installationen gibt. Die Struktur des Data Warehouse ermöglicht Ihnen Einblicke in Ihre mobile Umgebung. Andere analytische Tools wie Microsoft Power BI können das Datenmodell von Data Warehouse wiederum nutzen, um Visualisierungen und dynamische Dashboards zu erstellen.

Die Intune Data Warehouse-Struktur verwendet ein Sternschema-Modell. Ein Sternschema organisiert Fakten in einer Zeitdimension. Im Kontext des Modells ist ein *Fakt* eine quantitative Messung, z.B. die Anzahl der Geräte, die Anzahl von Apps oder der Zeitpunkt der Registrierung. Ein *Dimension* ist im Kontext des Modells ein Satz von Kategorien und deren hierarchische Beziehungen. Beispielsweise werden Tage in Monaten und Monaten in Jahren gruppiert. Ein Sternschema-Modell bietet hohe für Flexibilität und Analysefunktionen, damit Sie die Berichte erstellen können, die zum Verständnis der Entwicklung Ihrer mobilen Umgebung benötigen.

Das Warehouse macht Daten in den folgenden allgemeinen Kategorien verfügbar:
  -  Apps und Nutzung mit aktiviertem App-Schutz
  -  Registrierte Geräte, Eigenschaften und Inventar
  -  Apps- und Softwareinventar
  -  Gerätekonfiguration und Konformitätsrichtlinien

**Entitätenmengen des Datenmodells**

Entitätenmengen heißen im Datenmodell Auflistungen von Entitäten. Diese Mengen enthalten Entitäten, die die gesammelten Daten im Modell definieren. Jede Entitätenmenge stellt einen Zugriffspunkt auf das Data Warehouse-Datenmodell bereit. Sie finden Informationen zu den folgenden Kategorien von Entitäten:

  -  [Datum](reports-ref-date.md)
  -  [Benutzer](reports-ref-user.md)
  -  [Mobile App-Verwaltung (MAM)](reports-ref-mobile-app-management.md)
  -  [Geräte](reports-ref-devices.md)
  -  [Anwendung](reports-ref-application.md)
  -  [Richtlinie](reports-ref-policy.md)

<!-- ## Data Model relationships

For more information on the relationships in the data model, see [Relationships of Entities](). -->