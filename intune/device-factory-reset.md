---
title: "Zurücksetzen von Geräten auf die Werkseinstellungen mit Intune"
titleSuffix: Intune on Azure
description: "Erfahren Sie, wie Sie Geräte, die Sie in Intune verwalten, auf die jeweiligen Werkseinstellungen zurücksetzen.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8eff9b53-eef2-4c50-8aee-556bc49d69f2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 44f69179f76c8d5eeca1594485ca3a9c1b036188
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2017
---
# <a name="reset-intune-managed-devices-to-factory-settings"></a>Zurücksetzen von in Intune verwalteten Geräten auf die Werkseinstellungen


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Das Feature **Zurücksetzung auf Werkseinstellungen** setzt ein Gerät auf die Standardeinstellungen zurück. Das Gerät wird nicht mehr von Intune verwaltet, und sowohl die Unternehmens- als auch persönliche Daten werden entfernt. Diese Aktion kann nicht rückgängig gemacht werden.

## <a name="supported-platforms"></a>Unterstützte Plattformen

- Windows – unterstützt unter Windows 8.1 und höher (nicht von EAS-verwaltete Geräte)
- Windows Phone – Unterstützt
- iOS – Unterstützt
- macOS – Nicht unterstützt
- Android – Unterstützt (Android for Work wird nicht unterstützt)

## <a name="how-to-reset-a-device-to-factory-settings"></a>So setzen Sie ein Gerät auf Werkseinstellungen zurück

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.
4. Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.
5. Wählen Sie aus der Liste der verwalteten Geräte ein Gerät aus, und wählen Sie dann die Remotegeräteaktion **Zurücksetzung auf Werkseinstellungen**.

## <a name="next-steps"></a>Nächste Schritte

Um den Status der gerade ausgeführten Aktion anzuzeigen, wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Geräteaktionen** aus.

