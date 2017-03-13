---
title: Intune Mobile Threat Defense | Microsoft-Dokumentation
description: "Schützen Sie den Zugriff auf Unternehmensressourcen auf der Basis von Geräterisiko."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 08d87906-8158-4d5e-a49d-ad919efef3d1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b7ab3041a38bd394195a67690d245d1ad9fd0566
ms.openlocfilehash: fd54a1c94c9a4a279710d6be9f7cfe3b48468cb7
ms.lasthandoff: 03/03/2017


---

# <a name="intune-mobile-threat-defense-connectors"></a>Intune Mobile Threat Defense-Connector

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Mit Intune Mobile Threat Defense-Connectors können Sie Ihren ausgewählten Mobile Threat Defense-Hersteller als Informationsquelle für Ihre Konformitätsrichtlinien und bedingte Zugriffsregeln nutzen. Dadurch können IT-Administratoren eine Schutzeben auf ihre Unternehmensressoucen wie Exchange und Sharepoint anwenden, besonders von gefährdeten Mobilgeräten.

## <a name="what-problem-does-this-solve"></a>Welches Problem wird dadurch gelöst?

Unternehmen müssen vertrauliche Daten vor auftretenden Bedrohungen schützen. Dazu gehören physische, App-und netzwerkbasierte Bedrohungen sowie Sicherheitsrisiken beim Betriebssystem.
In der Vergangenheit haben Firmen PCs vor Angriffen proaktiv geschützt, während mobile Geräte nicht überwacht wurden und ungeschützt blieben. Mobile Plattformen bieten integrierten Schutz in Form von App-Isolierung und sicherheitsgeprüfter App Stores für Verbraucher, doch diese Plattformen bleiben weiterhin für komplexe Angriffe anfällig. Immer mehr Mitarbeiter nutzen ihre Geräte für die Arbeit und benötigen Zugriff auf vertrauliche Informationen. Geräte müssen gegen zunehmend raffinierter werdende Angriffe geschützt werden.

## <a name="how-the-intune-mobile-threat-defense-connectors-work"></a>Wie funktioniert der Intune Mobile Threat Defense-Connector?

Der Connector schützt Unternehmensressourcen, indem er einen Kommunikationskanal zwischen Intune und Ihrem ausgewählten Mobile Threat Defense-Hersteller erstellt. Intune Mobile Threat Defense-Partner bieten intuitive und leicht bereitzustellende Anwendungen für Mobilgeräte, die aktiv Informationen zu Bedrohungen überprüfen und analysieren, um sie mit Intune für Berichts- oder Erzwingungszwecke zu teilen. Wenn eine verbundene Mobile Threat Defense-App z.B. einem Mobile Threat Defense-Hersteller mitteilt, dass ein Telefon in Ihrem Netzwerk aktuell mit einem Netzwerk verbunden ist, das anfällig für „Man in the Middle“-Angriffe ist, wird diese Information an eine entsprechende Risikostufe (niedrig/mittel/hoch) weitergeleitet. Diese kann anschließend mit Ihren konfigurierten Zulassungen der Risikostufe in Intune verglichen werden, um zu bestimmen, ob der Zugriff auf bestimmte Ressourcen Ihrer Wahl aufgehoben werden sollte, während das Gerät gefährdet ist.

## <a name="sample-scenarios"></a>Beispielszenarien

Wenn ein Gerät von der Mobile Threat Defense-Lösung als gefährdet eingestuft wird:

![](http://i.imgur.com/kF8tI42.png)

Der Zugriff wird gewährt, wenn das Gerät wiederhergestellt ist:

![](http://i.imgur.com/zG4ZrzX.png)

## <a name="mobile-threat-defense-partners"></a>Mobile Threat Defense-Partner

Lernen Sie, wie Sie den Zugriffs auf Unternehmensressourcen auf der Basis von Geräte-, Netzwerk- und Anwendungsrisiko schützen:

- [Lookout](https://docs.microsoft.com/intune/deploy-use/lookout-mobile-threat-defense-connector)
