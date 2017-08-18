---
title: "Remote-Sperren von verwalteten Geräten durch Intune"
titleSuffix: Intune on Azure
description: "In diesem Artikel erfahren Sie, wie Sie die von Ihnen verwalteten Geräte mit Intune remote sperren."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ab885fa6f693e65295986c182353f4918024281f
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2017
---
# <a name="remotely-lock-managed-devices-with-intune"></a>Remote-Sperren von verwalteten Geräten durch Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Mit der Geräteaktion **Remote sperren** wird das ausgewählte Gerät gesperrt. Der Eigentümer des Geräts muss zum Entsperren seine Kennung verwenden. Sie können nur Remotesperrungen von Geräten durchführen, für die eine PIN oder ein Kennwort festgelegt wurde.

## <a name="supported-platforms"></a>Unterstützte Plattformen

- Windows – Nicht unterstützt
- Windows Phone – Unterstützt auf Windows Phone 8.1 und später
- iOS – Unterstützt
- macOS – Nicht unterstützt
- Android – Unterstützung

## <a name="how-to-remote-lock-a-device"></a>So sperren Sie ein Gerät aus der Ferne

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.
4. Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.
5. Wählen Sie aus der Liste der verwalteten Geräte ein Gerät aus, und wählen Sie dann die Remotegeräteaktion **Remote sperren**.

## <a name="next-steps"></a>Nächste Schritte

Um den Status der gerade ausgeführten Aktion anzuzeigen, wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Geräteaktionen** aus.
