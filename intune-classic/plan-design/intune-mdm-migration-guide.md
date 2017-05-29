---
title: "Migrationshandbuch für die Verwaltung mobiler Geräte mit Intune (Mobile Device Management, MDM) | Microsoft-Dokumentation"
description: "Dieses Handbuch soll Kunden von Anfang bis Ende bei den unterschiedlichsten Aspekten der Migration von einem Drittanbieter von MDM zu Microsoft Intune unterstützen."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: cce6d997c1aad73819b8cfcf31a1505f0ce75923
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---

# <a name="intune-migration-guide"></a>Intune-Migrationshandbuch

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

![Artikel MDM-Intune-Migrationshandbuch](../media/MDM-migration-guide-art.PNG)

Eine erfolgreiche Migration in Intune beginnt mit einem soliden Plan, der die aktuelle MDM-Umgebung, Geschäftsziele und technische Anforderungen miteinbezieht. Zusätzlich müssen Sie die wichtigsten Stakeholder kennen, die Ihren Migrationsplan unterstützen und bei diesem mit Ihnen zusammenarbeiten werden.

Dieses Handbuch soll Sie von Anfang bis Ende bei den unterschiedlichsten Aspekten der Migration von einem Drittanbieter von MDM zu Intune unterstützen.

## <a name="whats-included-in-this-guide"></a>Inhalt dieses Handbuchs

Dieses Handbuch enthält zwei Phasen, die beide Aufgaben, Strategien und Unterstützung bei der Vorgehensweise beinhalten, die Sie während der Migration zu Intune MDM Schritt für Schritt begleiten.

-   [Phase 1: Vorbereiten von Intune für die Verwaltung mobiler Geräte] (/intune-classic/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)

    -   [Anforderungen Ihrer MDM-Migration analysieren](/intune-classic/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements)

    -   [Grundlegende Einrichtung](/intune-classic/plan-design/migration-phase1-basic-setup)

    -   [Konfigurieren von Richtlinien für die Verwaltung von Apps und Geräten](/intune-classic/plan-design/migration-phase1-configure-device-and-app-management-policies)

    -   [Konfigurieren von App-Schutzrichtlinien] (/intune-classic/plan-design/migration-phase1-configure-app-protection-policies)

    -   [Besondere Überlegungen bei der Migration](/intune-classic/plan-design/migration-phase1-special-migration-considerations)

-   [Phase 2: Die Migration](/intune-classic/plan-design/migration-phase2-migration-campaign)

    -   [Kommunikationsplan](/intune-classic/plan-design/migration-phase2-communication-plan)

    -   [Fördern der Einführung mit bedingtem Zugriff für Endbenutzer](/intune-classic/plan-design/migration-phase2-drive-end-user-adoption-with-conditional-access)
    
    -   [Typischer Migrationszyklus](/intune-classic/plan-design/migration-phase2-typical-migration-cycle)
        -   [Migrationsüberwachung](/intune-classic/plan-design/migration-phase2-typical-migration-cycle#monitoring-migration)
        -   [Aufgaben nach der Migration](/intune-classic/plan-design/migration-phase2-typical-migration-cycle#post-migration)

## <a name="assumptions"></a>Annahmen

-   Sie haben Intune bereits in einer PoC-Umgebung (Proof of Concept) evaluiert und entschieden, diese Lösung zur Verwaltung mobiler Geräte in Ihrer Organisation einzusetzen.

-   Sie sind bereits mit Intune und seinen Funktionen vertraut. 

> [!NOTE]
> Konsultieren Sie das [Intune-Evaluierungshandbuch](/intune-classic/understand-explore/sign-up-for-30-day-trial-microsoft-intune), wenn Sie sich mit Intune vor der Migration vertrauter machen möchten.

## <a name="before-you-begin"></a>Vorbereitung

Es ist wichtig, dass Sie wissen, dass Ihre Bereitstellung mit Intune möglicherweise von Ihrer alten MDM-Bereitstellung unterscheidet. Im Gegensatz zu herkömmlichen MDM-Diensten baut Intune auf der identitätsgesteuerten Zugriffssteuerung auf, weshalb keine Netzwerkproxyvorrichtung zur Zugriffssteuerung auf Unternehmensdaten von mobilen Geräten außerhalb des Netzwerkumkreises der Organisation erforderlich ist. Microsoft bietet Lösungen zur Sicherung von Datendiensten innerhalb der Cloud selbst durch eine Folge von fest integrierten Clouddiensten, die zusammen als Angebot von Enterprise Client und Security bezeichnet werden.

-   Erfahren Sie mehr über die [gängigsten Arten der Verwendung von Intune](/intune-classic/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements).

## <a name="next-steps"></a>Nächste Schritte

[Phase 1: Vorbereiten von Intune für die Verwaltung mobiler Geräte] (/intune-classic/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)

