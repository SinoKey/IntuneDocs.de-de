---
title: "Migrationshandbuch für die Verwaltung mobiler Geräte mit Intune"
description: "Dieses Handbuch soll Kunden von Anfang bis Ende bei den unterschiedlichsten Aspekten der Migration von einem Drittanbieter von MDM zu Microsoft Intune unterstützen."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9e86f342413a0f31c51d7a56f862986c433309eb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2017
---
# <a name="intune-migration-guide"></a>Intune-Migrationshandbuch

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

![Artikel MDM-Intune-Migrationshandbuch](./media/MDM-migration-guide-art.PNG)

Eine erfolgreiche Migration in Intune beginnt mit einem soliden Plan, der die aktuelle MDM-Umgebung (Mobile Device Management, Verwaltung mobiler Geräte), Geschäftsziele und technische Anforderungen miteinbezieht. Zusätzlich müssen Sie die wichtigsten Stakeholder kennen, die Ihren Migrationsplan unterstützen und bei diesem mit Ihnen zusammenarbeiten werden.

Dieses Handbuch soll Sie von Anfang bis Ende bei den unterschiedlichsten Aspekten der Migration von einem Drittanbieter von MDM zu Intune unterstützen.

## <a name="whats-included-in-this-guide"></a>Inhalt dieses Handbuchs

Dieses Handbuch enthält zwei Phasen, die beide Aufgaben, Strategien und Unterstützung bei der Vorgehensweise beinhalten, die Sie während der Migration zu Intune MDM Schritt für Schritt begleiten.

-   [Phase 1: Vorbereitung von Intune für die Verwaltung mobiler Geräte] (migration-guide-prepare.md)

    -   [Anforderungen Ihrer MDM-Migration analysieren](migration-guide-prepare.md#assess-mdm-requirements)

    -   [Grundlegende Einrichtung](migration-guide-setup.md)

    -   [Konfigurieren von Richtlinien für die Verwaltung von Apps und Geräten](migration-guide-configure-policies.md)

    -   [Konfigurieren von App-Schutzrichtlinien] (migration-guide-app-protection-policies.md)

    -   [Besondere Überlegungen bei der Migration](migration-guide-considerations.md)

-   [Phase 2: Die Migration](migration-guide-campaign.md)

    -   [Kommunikationsplan](migration-guide-communication-plan.md)

    -   [Fördern der Einführung mit bedingtem Zugriff für Endbenutzer](migration-guide-drive-adoption.md)
    
    -   [Typischer Migrationszyklus](migration-guide-cycle.md)
        -   [Migrationsüberwachung](migration-guide-cycle.md#monitoring-migration)
        -   [Aufgaben nach der Migration](migration-guide-cycle.md#post-migration)

## <a name="assumptions"></a>Annahmen

-   Sie haben Intune bereits in einer PoC-Umgebung (Proof of Concept) evaluiert und entschieden, diese Lösung zur Verwaltung mobiler Geräte in Ihrer Organisation einzusetzen.

-   Sie sind bereits mit Intune und seinen Funktionen vertraut. 

> [!NOTE]
> Konsultieren Sie das [Intune-Evaluierungshandbuch](/intune-classic/understand-explore/sign-up-for-30-day-trial-microsoft-intune), wenn Sie sich mit Intune vor der Migration vertrauter machen möchten.

## <a name="before-you-begin"></a>Vorbereitung

Es ist wichtig, dass Sie wissen, dass Ihre Bereitstellung mit Intune möglicherweise von Ihrer alten MDM-Bereitstellung unterscheidet. Im Gegensatz zu herkömmlichen MDM-Diensten baut Intune auf der identitätsgesteuerten Zugriffssteuerung auf, weshalb keine Netzwerkproxyvorrichtung zur Zugriffssteuerung auf Unternehmensdaten von mobilen Geräten außerhalb des Netzwerkumkreises der Organisation erforderlich ist. Microsoft bietet Lösungen zur Sicherung von Datendiensten innerhalb der Cloud selbst durch eine Folge von fest integrierten Clouddiensten, die zusammen als Angebot von Enterprise Client und Security bezeichnet werden.

-   Erfahren Sie mehr über die [gängigsten Arten der Verwendung von Intune](migration-guide-prepare.md#assess-mdm-requirements).

## <a name="next-steps"></a>Nächste Schritte

[Phase 1: Vorbereitung von Intune für die Verwaltung mobiler Geräte] (migration-guide-prepare.md)
