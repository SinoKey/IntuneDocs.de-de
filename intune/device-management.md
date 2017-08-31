---
title: "Verwalten von Geräten mit Intune"
titleSuffix: Intune on Azure
description: "In diesem Artikel erfahren Sie, wie Sie die mit Intune verwalteten Geräte anzeigen und verschiedene Vorgänge auf diesen ausführen."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5d78b4a87eaa366b7bb00356c4b98d609620dcf3
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>Was ist die Microsoft Intune Geräteverwaltung?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Die Workload **Geräte** liefert Informationen zu den verwalteten Geräten und ermöglicht die Ausführung von Remoteaufgaben auf diesen Geräten. So greifen Sie auf die Workload zu

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.
4. Sie können Informationen über Geräte anzeigen und die aufgelisteten Remotegeräteaktionen durchführen.

## <a name="available-device-actions"></a>Verfügbare Geräteaktionen
Die verfügbaren Aktionen hängen von der Geräteplattform und der Konfiguration des Geräts ab.

- [Anzeigen des Gerätebestands](device-inventory.md)
- So führen Sie Remotegeräteaktionen durch:
    - [Unternehmensdaten entfernen](devices-wipe.md#remove-company-data)
    - [Zurücksetzen auf Werkseinstellungen](devices-wipe.md#factory-reset)
    - [Remotesperre](device-remote-lock.md) 
    - [Kennung zurücksetzen](device-passcode-reset.md)
    - [Umgehen der Aktivierungssperre](device-activation-lock-bypass.md) (nur iOS)
    - [Sauberer Start](device-fresh-start.md) (nur Windows)
    - [Modus für verlorene Geräte](device-lost-mode.md) (nur iOS)
    - [Gerät suchen](device-locate.md) (nur iOS)
    - [Neu starten](device-restart.md) (nur Windows)
    - [Zurücksetzen der PIN unter Windows 10](device-windows-pin-reset.md)
    - [Remotesteuerung für Android](device-profile-android-teamviewer.md)
    - [Synchronisieren von Geräten](device-sync.md)


## <a name="next-steps"></a>Nächste Schritte

- Wählen Sie **Geräteaktionen** aus, um den Status von Aktionen auf von Ihnen verwalteten Geräten anzuzeigen.
![Überwachen von Geräteaktionen](./media/monitor-device-actions.png)
