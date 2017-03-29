---
title: Aktivieren von Lookout MTP in Intune | Microsoft-Dokumentation
description: Aktivieren von Lookout Mobile Threat Protection in der Intune-Verwaltungskonsole.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: d42fa20a3bc6b6f4a74dd0872aae25cfb33067b9
ms.openlocfilehash: d2a10a0e14d9b0b4d2e3f8e2715b47d984e5aa66
ms.lasthandoff: 03/21/2017


---

# <a name="enable-lookout-mtd-connection-in-the-intune-classic-console"></a>Aktivieren der Lookout MTD-Verbindung in der klassischen Intune-Konsole

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Um die Verbindung mit Lookout Mobile Threat Defense (MTD) in Intune zu aktivieren, muss der Intune-Connector in der Lookout-Konsole bereits konfiguriert sein.  Wenn dies noch nicht erfolgt ist, führen Sie die in [Einrichten Ihres Lookout Mobile Threat Defense-Abonnements](set-up-your-subscription-with-lookout-mtp.md) beschriebenen Schritte aus.

Um die Lookout MTP-Verbindung in Intune zu aktivieren, wählen Sie auf der Seite **Verwaltung** der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Option **Integration von Drittanbieterdiensten** aus. Wählen Sie **Lookout-Status** aus, und aktivieren Sie **Synchronisierung mit MTP** mithilfe der Umschaltfläche.

![Screenshot der Lookout-Synchronisierungsseite mit hervorgehobener Umschaltfläche „Aktivieren“](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> Sie **müssen** die Lookout for Work-App konfigurieren, bevor Sie die Regeln der Kompatibilitätsrichtlinie erstellen und den bedingten Zugriff konfigurieren. Dadurch wird sichergestellt, dass die App für die Installation durch Endbenutzer bereit und verfügbar ist, bevor sie Zugriff auf E-Mail oder andere Unternehmensressourcen erhalten.

Damit wird das Setup der Lookout- und Intune-Integration in der Intune-Administratorkonsole abgeschlossen.  Die nächsten Schritte zum Implementieren dieser Lösung umfassen die Bereitstellung der [Lookout for Work-Apps](https://docs.microsoft.com/intune/deploy-use/device-threat-protection-apps) und das Einrichten der [Kompatibilitätsrichtlinie](https://docs.microsoft.com/intune/deploy-use/device-threat-protection-policy).


## <a name="next-steps"></a>Nächste Schritte
[Konfigurieren der Lookout for Work-App](https://docs.microsoft.com/intune/deploy-use/device-threat-protection-apps)

