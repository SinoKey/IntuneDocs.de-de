---
title: "Zurücksetzen einer Gerätekennung mit Intune"
titlesuffix: Azure portal
description: "In diesem Artikel erfahren Sie, wie Sie mit Intune die Kennung auf den von Ihnen verwalteten Geräten zurückzusetzen."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0446db40b829e92b681294ecc497a2c475480fac
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2017
---
# <a name="reset-the-passcode-on-intune-managed-devices"></a>Zurücksetzen der Kennung auf von Intune verwalteten Geräten


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Durch die Aktion **Kennung entfernen** wird eine neue Kennung für das Gerät generiert, die auf dem Blatt <*Gerätename*> **Übersicht** angezeigt wird.

## <a name="supported-platforms"></a>Unterstützte Plattformen

- Windows – Nicht unterstützt
- Windows Phone – Unterstützt unter Windows Phone 8.1 bis Windows 10 Creators Update nicht in Azure AD eingebunden, Windows 10 Creators Update und höher
- iOS – Unterstützt
- macOS – Nicht unterstützt
- Android– Unterstützt für ältere Versionen vor Android 7. Android for Work wird nicht unterstützt.

## <a name="how-to-reset-a-passcode"></a>So setzen Sie eine Kennung zurück

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.
4. Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.
5. Wählen Sie aus der Liste der verwalteten Geräte ein Gerät aus, und wählen Sie dann die Remotegeräteaktion **Kennung entfernen**.

## <a name="next-steps"></a>Nächste Schritte

Um den Status der gerade ausgeführten Aktion anzuzeigen, wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Geräteaktionen** aus.
