---
title: "Synchronisieren von Geräten mit Intune"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie Geräte mit Intune synchronisieren, um die neuesten Richtlinien und Aktionen zu erhalten."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3906b567935f026202ccf0e81424a1bb36e376ef
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2017
---
# <a name="sync-devices-with-intune-to-get-the-latest-policies-and-actions"></a>Synchronisieren von Geräten mit Intune, um die neuesten Richtlinien und Aktionen zu erhalten


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Die Geräteaktion **Sync** (Synchronsieren) zwingt das ausgewählte Gerät dazu, sofort bei Intune einzuchecken. Checkt ein Gerät ein, empfängt es sofort alle ihm zugewiesenen ausstehenden Aktionen oder Richtlinien.  Dadurch können Sie sofort zugewiesene Richtlinien überprüfen und Probleme beheben, ohne den nächsten geplanten Check-In abwarten zu müssen.

## <a name="supported-platforms"></a>Unterstützte Plattformen

- Windows – Unterstützt
- Windows Phone – Unterstützt
- iOS – Unterstützt
- macOs – Unterstützt
- Android – Unterstützung

## <a name="how-to-sync-a-device"></a>So synchronisieren Sie ein Gerät

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.
4. Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.
5. Wählen Sie aus der Liste der verwalteten Geräte ein Gerät aus, und wählen Sie dann die Remotegeräteaktion **Sync** aus.
7. Wählen Sie zum Bestätigen der Aktion **Ja** aus.

## <a name="next-steps"></a>Nächste Schritte

Wählen Sie **Geräteaktionen** aus, um den Status der Synchronisierung anzuzeigen. 
