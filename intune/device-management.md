---
title: "Verwalten von Geräten mit Intune"
titleSuffix: Intune on Azure
description: "In diesem Artikel erfahren Sie, wie Sie die mit Intune verwalteten Geräte anzeigen und verschiedene Vorgänge auf diesen ausführen."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e0fc5337b92ac604a448038f685b27623b6153f9
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>Was ist die Microsoft Intune Geräteverwaltung?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Die Workload **Geräte** liefert Informationen zu den verwalteten Geräten und ermöglicht die Ausführung von Remoteaufgaben auf diesen Geräten. So greifen Sie auf die Workload zu

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.
4. Jetzt können Sie die aufgeführten Remotegeräteaktionen ausführen. Die verfügbaren Aktionen hängen von der Geräteplattform und der Konfiguration des Geräts ab:

## <a name="available-device-actions"></a>Verfügbare Geräteaktionen

- [Anzeigen des Gerätebestands](device-inventory.md)
- So führen Sie Remotegeräteaktionen durch:
    - [Unternehmensdaten entfernen](device-company-data-remove.md) 
    - [Zurücksetzen auf Werkseinstellungen](device-factory-reset.md)
    - [Remotesperre](device-remote-lock.md)
    - [Kennung zurücksetzen](device-passcode-reset.md)
    - [Aktivierungssperre umgehen](device-activation-lock-bypass.md)
    - [Sauberer Start](device-fresh-start.md)
    - [Modus für verlorene Geräte](device-lost-mode.md)
    - [Gerät suchen](device-locate.md)
    - [Neu starten](device-restart.md)
    - [Zurücksetzen der PIN unter Windows 10](device-windows-pin-reset.md)
    - [Remotesteuerung für Android](device-profile-android-teamviewer.md)
    - [Synchronisieren von Geräten](device-sync.md)


## <a name="next-steps"></a>Nächste Schritte

- Wählen Sie **Geräteaktionen** aus, um den Status von Aktionen auf von Ihnen verwalteten Geräten anzuzeigen. 
![Überwachen von Geräteaktionen](./media/monitor-device-actions.png)
