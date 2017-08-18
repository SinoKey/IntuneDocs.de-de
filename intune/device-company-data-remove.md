---
title: "Entfernen von Unternehmensdaten von Geräten mit Intune"
titleSuffix: Intune on Azure
description: "Erfahren Sie, wie Sie von den Geräten, die Sie über Intune verwalten, nur die Unternehmensdaten entfernen.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f021e95f-157f-4e8a-9253-1cff03d6ee3e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b0cc7d62770057ff9df5a36e6e5df58b29430534
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2017
---
# <a name="remove-company-data-from-intune-managed-devices"></a>Entfernen von Unternehmensdaten von über Intune verwalteten Geräten


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Die Geräteaktion **Unternehmensdaten entfernen** entfernt nur Unternehmensdaten von Geräten, die über Intune verwaltet werden. Es werden keine persönlichen Daten vom Gerät entfernt. Nach dem Entfernen wird das Gerät nicht mehr von Intune verwaltet und kann nicht auf die Unternehmensressourcen zugreifen.

## <a name="supported-platforms"></a>Unterstützte Plattformen

- Windows – Unterstützt (nicht für Windows-Geräte, die mit Azure Active Directory verknüpft sind)
- Windows Phone – Unterstützt
- iOS – Unterstützt
- macOs – Unterstützt
- Android – Unterstützung

## <a name="how-to-remove-company-data"></a>So entfernen Sie Unternehmensdaten

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.
4. Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.
5. Wählen Sie aus der Liste der verwalteten Geräte ein Gerät aus, und wählen Sie dann die Remotegeräteaktion **Unternehmensdaten entfernen**.

## <a name="next-steps"></a>Nächste Schritte

Um den Status der gerade ausgeführten Aktion anzuzeigen, wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Geräteaktionen** aus.
