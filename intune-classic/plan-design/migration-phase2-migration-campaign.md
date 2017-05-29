---
title: Migration mit Intune starten | Microsoft-Dokumentation
description: "Dieser Artikel bietet eine Anleitung für den Start einer Migration."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f781b029-50f2-46ee-8ff7-03b4a6719e80
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: e98730105044d2147d9be37002fc20ec2de8eb0e
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---

# <a name="phase-2-migration-campaign"></a>Phase 2: Die Migration

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Organisationen sollten sich für eine Vorgehensweise bei der Migration entscheiden, die am besten zu ihren Bedürfnissen passt, und eine Implementierungstaktik nach ihren spezifischen Anforderungen anpassen. Diese Anleitung hilft Ihnen bei der Registrierung Ihrer Geräte in Intune.

## <a name="keys-to-a-successful-migration"></a>Wichtige Faktoren für eine erfolgreiche Migration

Dies sind die wichtigsten Punkte für die Migration vom MDM eines Drittanbieters nach Intune:

-   Die Kommunikation ist sehr wichtig, um die Ausfallzeit für Endbenutzer möglichst niedrig und deren Zufriedenheit möglichst hoch zu halten.

-   Achten Sie darauf, dass Sie genaue Anweisungen für die Migration geben.

-   Die Registrierung aller verwalteter Geräte in Ihrem alten MDM-Anbieter muss vor der Registrierung in Intune aufgehoben werden.

-   Bieten Sie den Endbenutzern eine Anleitung des alten MDM-Anbieters für das Aufheben der Geräteregistrierung.

-   Gehen Sie schrittweise vor. Beginnen Sie mit einer kleinen Gruppe von Pilotbenutzern und fügen Sie nach und nach mehr Benutzergruppen hinzu, bis alle bereitgestellt wurden.

-   Überwachen Sie das Laden des Helpdesks und den Registrierungserfolg der jeweiligen Zyklen. Planen Sie großzügig, um sicherzustellen, dass Erfolgskriterien für jede Gruppe ausgewertet werden können, bevor Sie mit der Migration der nächsten beginnen. Ihre Pilotbereitstellung sollte Folgendes überprüfen:

    -   ob sich die Registrierungerfolgs- und Fehlerraten im Rahmen bewegen

    -   Benutzerproduktivität:

        -   Unternehmensressourcen wie z.B. VPN, Wi-Fi, E-Mail und Zertifikate funktionieren ordnungsgemäß.

        -   Auf bereitgestellte Apps kann zugegriffen werden.

    -   Datensicherheit:

        -   Kompatibilitätsberichte

        -   Schutzmaßnahmen für mobile Apps wurden erzwungen

-   Wenn Sie mit der ersten Phase der Migration zufrieden sind, wiederholen Sie für die nächste Phase den Migrationszyklus (siehe unten unter „Typischer Migrationszyklus“).

-   Wiederholen Sie die Zyklen in Phasen, bis alle Benutzer zu Intune migriert wurden.

-   Stellen Sie sicher, dass das Helpdesk-Team zur Unterstützung der Endbenutzer während der gesamten Migration zur Verfügung steht. Führen Sie eine freiwillige Migration aus, bis Sie die Arbeitsauslastung für Supportanrufe einschätzen können.

-   Legen Sie keine Frist für die Registrierung fest, bis die restliche Arbeit von Ihrem Helpdesk verarbeitet werden kann

> [!IMPORTANT] 
> Konfigurieren Sie Intune und Ihre vorhandene Drittanbieter-MDM-Projektmappe nicht gleichzeitig so, dass Zugriffssteuerelemente auf Ressourcen wie Exchange oder SharePoint Online angewendet werden. Zusätzlich sollten Geräte immer nur in einer Projektmappe gleichzeitig registriert sein.

## <a name="next-steps"></a>Nächste Schritte

[Phase 2: Kommunikationsplan](/intune-classic/plan-design/migration-phase2-communication-plan)

