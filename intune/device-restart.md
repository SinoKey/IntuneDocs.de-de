---
title: "Remoteneustart von Geräten mit Intune"
titlesuffix: Azure portal
description: "In diesem Artikel erfahren Sie, wie Geräte über die Aktion zum Neustarten des Geräts remote neu gestartet werden."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7177616d654ca9af0b7e7276a1a4b5453117f36c
ms.sourcegitcommit: 22ab1c6a6bfeb4fef9850d12b29829c3fecbbeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2018
---
# <a name="remotely-restart-devices-with-intune"></a>Remoteneustart von Geräten mit Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Die Geräteaktion **Neu starten** führt dazu, dass das von Ihnen gewählte Gerät neu gestartet wird. Der Eigentümer des Geräts wird nicht automatisch über den Neustart benachrichtigt und kann daher Daten verlieren.

## <a name="supported-platforms"></a>Unterstützte Plattformen

- Windows – unter Windows 8.1 und höher unterstützt
- Windows Phone – Unterstützt auf Windows Phone 8.1 und später
- iOS – Unterstützt

    > [!Note]  
    > Für diesen Befehl wird ein überwachtes Gerät und das Zugriffsrecht **Gerätesperre** benötigt. Das Gerät wird sofort neu gestartet. Kennungsgeschützte iOS-Geräte verbinden Sie nach dem Neustart nicht wieder mit dem WLAN-Netzwerk und können unter Umständen nicht mehr mit dem Server kommunizieren.
- macOS – Nicht unterstützt
- Android – Nicht unterstützt

## <a name="how-to-restart-a-device"></a>So starten Sie einen Auftrags neu

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.
4. Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.
5. Wählen Sie aus der Liste der verwalteten Geräte ein Gerät aus, und wählen Sie dann die Remotegeräteaktion **Neu starten**.

## <a name="next-steps"></a>Nächste Schritte

Um den Status der gerade ausgeführten Aktion anzuzeigen, wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Geräteaktionen** aus.
