---
title: "Verwalten von Geräten mit Intune"
titleSuffix: Intune on Azure
description: "In diesem Artikel erfahren Sie, wie Sie die mit Intune verwalteten Geräte anzeigen und verschiedene Vorgänge auf diesen ausführen."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/05/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f066e62e323fffb7c6954d83b2b55ee63f4be46
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>Was ist die Microsoft Intune Geräteverwaltung?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Die Workload **Geräte** liefert Informationen zu den verwalteten Geräten und ermöglicht die Ausführung von Remoteaufgaben auf diesen Geräten. So greifen Sie auf die Workload zu

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.

Nun können Sie die folgenden Aktionen ausführen:

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


## <a name="support-for-each-device-action"></a>Unterstützung für Geräteaktionen

Die folgende Tabelle veranschaulicht, welche Geräteplattformen die jeweilige Aktion unterstützen.

|||||||
|-|-|-|-|-|-|
|Geräteaktion|Windows|Windows Phone|iOS|macOS|Android|
|**Unternehmensdaten entfernen**|Ja|Ja|Ja|Ja|Ja|
|**Zurücksetzen auf Werkseinstellungen**|Windows 8.1 und höher (nicht von EAS-verwaltete Geräte)|Ja|Ja|Nein|Android for Work wird nicht unterstützt.|
|**Löschen**|Ja|Ja|Ja|Ja|Ja|
|**Remotesperre**|Nein|Windows Phone 8.1 und höher|Ja|Nein|Ja|
|**Kennung zurücksetzen**|Nein|Windows Phone 8.1 bis Windows 10 Creators Update nicht in Azure AD eingebunden, Windows 10 Creators Update und höher: alle|Ja|Nein|In früheren Versionen als Android 7 wird Android for Work nicht unterstützt.|
|**Neue Kennung** (für Windows 10-Geräte)|Nein|Windows 10 Creators Update und höher (in Azure AD eingebunden)|Nein|Nein|Android for Work wird nicht unterstützt.|
|**Aktivierungssperre umgehen**|Nein|Nein|Nur unternehmenseigene Geräte|Nein|Nein|
|**Modus für verlorene Geräte**|Nein|Nein|iOS 9.3 und höher, überwacht und unternehmenseigen|Nein|Nein|
|**Gerät suchen**|Nein|Nein|Modus für verlorene Geräte von iOS 9.3 und höher, überwacht und unternehmenseigen|Nein|Nein|
|**Aktuellen Benutzer abmelden**|Nein|Nein|iOS 9.3 und höher (nur freigegebene iPad-Geräte)|Nein|Nein|
|**Neu starten**|Windows 8.1 und höher|Windows Phone 8.1 und höher|Nein|Nein|Nein|
|**Sauberer Start**|Windows 10 Creators Update und höher|Nein|Nein|Nein|Nein|
|**Neue Remoteunterstützungssitzung**|Nein|Nein|Nein|Nein|Ja|
|**Benutzer entfernen**|Nein|Nein|iOS 9.3 und höher (nur freigegebene iPad-Geräte)|Nein|Nein|

## <a name="next-steps"></a>Nächste Schritte

- Wählen Sie **Geräteaktionen** aus, um den Status von Aktionen auf von Ihnen verwalteten Geräten anzuzeigen. 
![Überwachen von Geräteaktionen](./media/monitor-device-actions.png)