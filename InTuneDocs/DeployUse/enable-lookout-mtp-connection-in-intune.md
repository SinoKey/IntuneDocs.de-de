---
title: Aktivieren von Lookout MTP in Intune | Microsoft Intune
description: Aktivieren von Lookout Mobile Threat Protection in der Intune-Verwaltungskonsole.
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1334500471d2aea5e8c58a3219c755bfd9953424
ms.openlocfilehash: 4ae7d6c571f69c0cc51dc15355e50325afb88694


---

# Aktivieren der Lookout MTP-Verbindung in der Intune-Verwaltungskonsole
In diesem Thema erfahren Sie, wie die Lookout MTP-Verbindung in Intune aktiviert wird. Vor der Ausführung dieses Schritts sollte die Konfiguration des Intune-Connectors in der Lookout MTP-Konsole bereits erfolgt sein.  Wenn dies noch nicht erfolgt ist, führen Sie die in [Einrichten Ihres Abonnements von Lookout Mobile Threat Protection](set-up-your-subscription-with-lookout-mtp.md) beschriebenen Schritte aus.

Um die Lookout MTP-Verbindung in Intune zu aktivieren, wählen Sie auf der Seite **Verwaltung** der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Option **Integration von Drittanbieterdiensten** aus. Wählen Sie **Lookout-Status** aus, und aktivieren Sie **Synchronisierung mit MTP** mithilfe der Umschaltfläche.

![Screenshot der Lookout-Synchronisierungsseite mit hervorgehobener Umschaltfläche „Aktivieren“](../media/mtp/lookout-intune-synchronization.png)

Damit wird das Setup der Lookout- und Intune-Integration in der Intune-Administratorkonsole abgeschlossen.  Die nächsten Schritte zum Implementieren dieser Lösung umfassen die Bereitstellung der [Lookout for Work-Apps](configure-and-deploy-lookout-for-work-apps.md) und das Einrichten der [Kompatibilitätsrichtlinie](enable-device-threat-protection-rule-in-compliance-policy.md).

>[!IMPORTANT]
> Sie **müssen** die Lookout for Work-App konfigurieren, bevor Sie die Regeln der Kompatibilitätsrichtlinie erstellen und den bedingten Zugriff konfigurieren. Dadurch wird sichergestellt, dass die App für die Installation durch Endbenutzer bereit und verfügbar ist, bevor sie Zugriff auf E-Mail oder andere Unternehmensressourcen erhalten.
## Nächste Schritte
[Konfigurieren der Lookout for Work-App ](configure-and-deploy-lookout-for-work-apps.md)



<!--HONumber=Sep16_HO2-->


