---
title: Verwenden des Data Warehouse von Intune | Microsoft-Dokumentation
description: "Verwenden Sie das Data Warehouse von Intune zum Erstellen von Berichten, die einen Einblick in Ihre mobile Unternehmensumgebung ermöglichen."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: db6661dd92b890d711f655a60eb883b417a30d8a
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2017
---
# <a name="use-the-intune-data-warehouse"></a>Verwenden des Data Warehouse von Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Verwenden Sie das Data Warehouse von Intune zum Erstellen von Berichten, die einen Einblick in Ihre mobile Unternehmensumgebung ermöglichen. Einige der Berichte enthalten beispielsweise:
-   Trend der Benutzer, die sich bei Intune registrieren, sodass Sie Ihre Lizenzkäufe optimieren können
-   Strukturplan für App- und BS-Versionen, damit Sie den Zustand von Mobilgeräten überprüfen können
-   Trends zur Konformität der Registrierungen und Geräte, sodass Sie reibungslos Richtlinienaktualisierungen durchführen können

Das Data Warehouse bietet Ihnen Zugriff auf mehr Informationen über Ihre mobile Umgebung als das Azure-Portal. Mit dem Data Warehouse von Intune können Sie auf Folgendes zugreifen:

  -  Verlaufsdaten für Intune
  -  Daten, die täglich aktualisiert werden
  -  Ein Datenmodell, das den OData-Standard verwendet

> [!Important]  
> Sie können die neuesten Funktionen des Data Warehouse mithilfe der Betaversion ausprobieren. Für die Verwendung die Betaversion muss Ihre URL den Abfrageparameter `api-version=beta` enthalten. Die Beta-Version bietet Features bevor sie als unterstützter Dienst allgemein verfügbar gemacht werden. Da Intune neue Features hinzufügt, könnten sich in der Betaversion Verhalten und Datenverträge ändern. Benutzerdefinierter Code oder Berichtstools, die von der Betaversion abhängig sind, könnten mit laufenden Updates nicht mehr funktionieren. <!-- If you experience problems with the beta service, follow [link to feedback process]() to report the issue or provide feedback.-->

**Nächste Schritte**

- Rufen Sie einen Link ab und verwenden Sie Power BI, um Einblicke zu erhalten. Anweisungen hierzu finden Sie unter [Connect to the Intune Data Warehouse with Power BI (Verbinden mit dem Data Warehouse von Intune mit Power BI)](reports-proc-get-a-link-powerbi.md).
- Weitere Informationen über die Intune-Data Warehouse-API, das Datenmodell und Beziehungen zwischen Entitäten<!-- , and an example of creating a custom client to retrieve data,--> finden Sie unter [Intune Data Warehouse-API](reports-nav-intune-date-warehouse.md).