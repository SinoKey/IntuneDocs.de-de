---
title: Anwendungsrollout | Microsoft Intune
description: "Empfehlungen für ein Rollout von Apps in Microsoft Intune in mehreren Phasen."
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0fc32ed3-bcf4-472a-80e7-eb20986f78fa
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2427768c0ca73d20140462946ba2984b7999d864
ms.openlocfilehash: d72247936a0dec8e2e00d107c0d52c1568a92c03


---

# Anwendungsrollout
Dieses Thema enthält spezifische Empfehlungen für ein phasenweises Rollout von Apps in Microsoft Intune. Allgemeine Informationen über die Phasen des Rollouts finden Sie unter [Rolloutphasen für die Bereitstellung von Microsoft Intune](rollout-phases-for-microsoft-intune-deployment.md).

### Phasen des App-Rollouts
Phasen des App-Rollouts:

-   Projektumfang

-   Proof of Concept

-   Pilotphase

-   Rollout im gesamten Unternehmen

-   Betrieb und Wartung

## Projektumfang
Beachten Sie Folgendes:

-   Die Benutzeraufgabe, die von der App ermöglicht werden soll.

-   Die Eignung der App für Ihre Benutzer und deren Geräte (alle Betriebssysteme, die wahrscheinlich verwendet werden).

-   Stellen Sie sicher, dass das Installationsprogramm für die ausgewählte App von der App-Verteilung von Intune unterstützt wird, wie in [Hinzufügen von Apps mit Microsoft Intune](/intune/deploy-use/add-apps) beschrieben.

-   Stellen Sie sicher, dass die erforderlichen Komponenten für die App-Verteilung installiert sind. <!---, as described in [Plan for app deployment in Microsoft Intune](plan-for-app-deployment-in-microsoft-intune.md).--->

-   Ermitteln Sie, ob der App-Typ von Intune unterstützt wird.

-   Überprüfen Sie, ob ausreichend Cloudspeicher zum Hochladen der App verfügbar ist. Anweisungen zum Erwerb von zusätzlichem Speicher finden Sie unter [Hinzufügen von Apps mit Microsoft Intune](/intune/deploy-use/add-apps).

> [!NOTE]           
> Sie können diese [Planungsvorlage für mobile Apps](https://gallery.technet.microsoft.com/Mobile-app-planning-18689d59) herunterladen, die Ihnen bei Ihrem Rolloutprozess behilflich sein kann.

## Proof of Concept
In der Proof of Concept-Phase testen Sie Ihre App-Bereitstellung in einer Laborumgebung mit Geräten und Benutzern, die Sie ausschließlich für Testzwecke konfiguriert haben.

-   Lassen Sie Ihre Helpdeskmitarbeiter an dieser Phase teilnehmen, damit diese erfahren, welche Probleme während der Pilotphase und der Bereitstellung in der Produktion auftreten können. Informationen zur Problembehandlung finden Sie unter [Behandlung von Problemen mit der App-Bereitstellung in Microsoft Intune](/intune/troubleshoot/troubleshoot-app-deployment-problems-in-microsoft-intune).

-   An dieser Stelle des Verfahrens sollten Sie Kommunikationspläne für Benutzer in der Pilotphase und in der Produktion entwickeln. Der Plan sollte mindestens beinhalten, welche App bereitgestellt wird, wann und wie Benutzer sie erhalten, den Geschäftszweck der Bereitstellung und wie bei auftretenden Problemen vorzugehen ist, d. h. sowohl Informationen zur Selbsthilfe als auch Kontaktinformationen des Helpdesks sollten aufgeführt werden.

## Pilotphase
Während der Pilotphase stellen Sie die App für eine kleine Gruppe von Testbenutzern und -geräten bereit. Beachten Sie Folgendes:

-   Stellen Sie sicher, dass die Testgruppe für die Benutzer und Geräte repräsentativ ist, die die App nach dem Produktionsrollout verwenden.

-   Informieren Sie den Helpdesk in Bezug auf die App-Bereitstellung, und stellen Sie sicher, dass die Mitarbeiter auf die Hilfestellung für Benutzer in der Testgruppe vorbereitet sind.

-   Wählen Sie Testbenutzer aus, die die App auf typische Weise nutzen und Probleme zuverlässig an die Administratoren der Pilotphase melden.

-   Aktivieren Sie den Kommunikationsplan für Benutzer in der Pilotphase.

## Rollout im gesamten Unternehmen

-   Verwenden Sie die Ergebnisse der Pilotphase, um das Rollout im gesamten Unternehmen anzupassen.

-   Benachrichtigen Sie Ihren Helpdesk über den Zeitplan des App-Rollouts. Halten Sie Mechanismen bereit, um auf Hilfeanforderungen zu reagieren und das Rollout nach Bedarf anzupassen.

-   Bereiten Sie sich auf die Problembehandlung für die Bereitstellung vor, falls Probleme auftreten.

-   Aktivieren Sie den Kommunikationsplan für Benutzer in der Produktion.

-   Verwenden Sie einen schrittweisen Ansatz für die Bereitstellung der App, bei dem Sie Gruppen inkrementell hinzufügen, um sicherzustellen, dass das Rollout reibungslos verläuft.

## Betrieb und Wartung
**Betrieb:** Überwachen Sie Ihre Intune-Konsole auf Warnungen und Benutzer- oder Geräteprobleme, um sicherzustellen, dass die Anwendungsverteilung Ihrem Entwurf entsprechend verläuft.

**Helpdesk:** Stellen Sie sicher, dass Ihr Helpdesk über Änderungen an der App-Verfügbarkeit informiert ist, die zu Supportanfragen führen können.

### Weitere Informationen:
[Bereitstellen von Apps](/intune/deploy-use/deploy-apps)

[Behandlung von Problemen mit der App-Bereitstellung in Microsoft Intune](/intune/troubleshoot/troubleshoot-app-deployment-problems-in-microsoft-intune)



<!--HONumber=Jul16_HO3-->


