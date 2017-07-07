---
title: Aktivieren von Skycure Mobile Threat Defense in Intune
description: Aktivieren Sie Skycure Mobile Threat Defense in der klassischen Intune-Konsole.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0cc4e59d-819a-47a2-a26f-4f8d0f8df7bf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4dad45d15fec7189fdcf184839040b9e3f9a3a48
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2017
---
# <a name="enable-skycure-mobile-threat-defense-in-intune"></a>Aktivieren von Skycure Mobile Threat Defense in Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Um die Verbindung mit Skycure Mobile Threat Defense zu aktivieren, muss der [Intune-Connector in der Skycure-Konsole] (/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune) bereits konfiguriert sein.

## <a name="to-enable-the-skycure-mtd-connection-in-intune"></a>So aktivieren Sie die Skycure MTD-Verbindung in Intune

1.  Wechseln Sie zur [klassischen Intune-Konsole](https://manage.microsoft.com/), und geben Sie dann Ihre Anmeldeinformationen ein.

2.  Wählen Sie **Admin** &gt; **Third Party Service Integration** (Integration von Drittanbieterdiensten), wählen Sie dann **Skycure-Status**, und aktivieren Sie mithilfe der Umschaltfläche **Synchronisierung mit MTD**.

    ![Aktivieren der Skycure-Umschaltfläche in der klassischen Intune-Konsole](../media/mtp/enable-skycure-1.png)

> [!IMPORTANT] 
> Sie müssen die Skycure-Apps konfigurieren, bevor Sie die Regeln der Kompatibilitätsrichtlinie erstellen und den bedingten Zugriff konfigurieren. Dadurch wird sichergestellt, dass die App für die Installation durch Endbenutzer bereit und verfügbar ist, bevor sie Zugriff auf E-Mail oder andere Unternehmensressourcen erhalten.

Damit wird das Einrichten der Skycure- und Intune-Integration in der Intune-Administratorkonsole abgeschlossen. Die nächsten Schritte zum Implementieren dieser Lösung umfassen die Bereitstellung der Skycure for Work-Apps und das Einrichten der Kompatibilitätsrichtlinie.

## <a name="next-steps"></a>Nächste Schritte

[Erstellen der Mobile Threat Defense-Kompatibilitätsrichtlinie](/intune-classic/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)
