---
title: "So überwachen Sie die Gerätekompatibilität"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie die Gerätekonformität überwachen."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0790934b-48b9-435b-a8aa-e83ed5b73191
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: d59d94aafa71a9891a6746902339255ea7a9ad15
ms.lasthandoff: 02/18/2017


---
# <a name="how-to-monitor-compliance-in-intune-azure-preview"></a>Überwachen der Gerätekonformität in der Vorschau von Intune in Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Sie können sich auf dem Blatt **Übersicht** eine Zusammenfassung des Status Ihrer **Konformitätsprofile** ansehen.
Sie können interaktiv einen Drilldown in den Diagrammen durchführen, um Details anzuzeigen. Wenn Sie mehrere Konformitätsprofile konfiguriert haben, können Sie den Status für jede Richtlinie anzeigen, indem Sie auf dem Blatt „Richtlinie“ im Abschnitt **Verwalten** die Option **Berichte** auswählen.  Die Details der für die Vorschau verfügbaren Berichte werden unten aufgeführt.

##  <a name="device-compliance"></a>Gerätekompatibilität

Die Zusammenfassung des Gerätekonformitätsberichts zeigt zusammengestellte Informationen zur Anzahl der Geräte, für die einer der folgenden Status gemeldet wurde:

- **Kompatibel:** Das Gerät wurde vor Kurzem auf Konformität überprüft und als konform mit den Einstellungen des angegebenen Konformitätsprofils bewertet.
- **Nicht kompatibel:**: Das Gerät wurde überprüft und als nicht konform bewertet.  Wenn im Profil eine Karenzzeit angegeben wurde, ist diese abgelaufen, und das Gerät hat damit in einen nicht konformen Status.
- **Karenzzeit:** Das Gerät wurde überprüft und als nicht konform bewertet. Die Karenzzeit gilt jedoch immer noch, bis das Gerät als nicht konform gekennzeichnet wird.

Sie können in jedem Abschnitt einen Drilldown durchführen, um weitere Details zu den einzelnen Geräten und Benutzern anzuzeigen.

## <a name="setting-compliance"></a>Einstellungskonformität

Der Einstellungskonformitätsbericht enthält Einzelheiten zu jeder Konformitätseinstellung. Beispiele:

- Anzahl der Geräte, die mit der Einstellung nicht konform sind
- Die Plattform, auf der die Einstellung angewendet wird

Sie können für jede Einstellung einen Drilldown durchführen, um weitere Informationen zu den Profilen, für die diese Einstellungen aktiviert wurden, und zu den konfigurierten Werten der Einstellungen zu erhalten.

