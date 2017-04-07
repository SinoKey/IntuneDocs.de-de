---
title: Funktionsweise eines typischen Migrationszyklus in Intune| Microsoft-Dokumentation
description: "In diesem Artikel erfahren Sie mehr zur Funktionsweise eines Migrationszyklus in Intune. Außerdem wird ein Beispiel für das Behandeln des Migrationszyklus durch Kunden gegeben."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3688b724-9521-4210-bf4d-bcf47d8d4ca0
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: aa8fb215772b6e8d3a913d929c030d68e363970b
ms.lasthandoff: 03/27/2017


---

# <a name="phase-2-typical-migration-cycle"></a>Phase 2: typischer Migrationszyklus

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Es ist üblich, dass eine Organisation ihre Intune-Migration mit einem kleinen Pilotversuch mit einer Teilmenge aller Benutzer in ihrer IT-Abteilung startet. Zusätzlich muss Ihre Organisation möglicherweise Faktoren wie die Änderungsbereitschaft der Gruppe, die Anzahl der Benutzer, die Komplexität, die Anforderungen, den Ort und die Geschäftsrisiken besprechen, um einen Zeitrahmen für die Migration festlegen zu können.

Hier ist ein Beispiel, wie Sie Ihre Zielgruppen planen können:

  | **Migration der Zielgruppen** | **Zeitraum 1** | **Zeitraum 2** | **Zeitraum 3** | **Zeitraum 4** | **...**
|:---:|:---:|:---:|:---:|:---:|:---:|
| Begrenzter Pilotversuch der IT-Organisation (50 Benutzer) | Plan bekannt geben | Anweisung zum Registrieren | Frist setzen | Erzwingen des bedingten Zugriffs |  |                                                        
| Erweiterter Pilotversuch der IT-Organisation (200 Benutzer) |  | Plan bekannt geben | Anweisung zum Registrieren | Frist setzen | Erzwingen des bedingten Zugriffs | 
| Phase 1 der Migration Technologisch kompetente Benutzer (2000) |  |  | Plan bekannt geben | Anweisung zum Registrieren | Frist setzen | 
| Phase 2 der Migration Osten der USA |  |  |  | Plan bekannt geben | Anweisung zum Registrieren | 
| Alle Regionen |  |  |  |  | Plan bekannt geben | 

## <a name="customer-migration-case-study"></a>Fallstudie für die Kundenmigration

### <a name="adatum-corporation"></a>Adatum Corporation

- Schauen Sie sich an, [wie Adatum Corporation von einer Drittanbieter-MDM zu Intune migriert ist](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0).

## <a name="monitoring-migration"></a>Migrationsüberwachung

Microsoft Intune bietet mehrere Methoden, mit denen Sie Ihre Migration überwachen können:

1.  Gruppenansichten für Intune-Benutzer

2.  Integrierte Berichte

3.  Konsoleninterne Warnungen

Sie sollten überwachen, wie viele Benutzer nach jeder Phase Geräte registriert haben, damit Sie:

-   die Effektivität der Kommunikationsplan bewerten können

-   die Auswirkungen des Erzwingens von bedingtem Zugriff einschätzen können

Erfahren Sie, wie Sie [eine Intune-Migration überwachen](https://docs.microsoft.com/intune/deploy-use/understand-microsoft-intune-operations-by-using-reports) können.

## <a name="post-migration"></a>Aufgaben nach der Migration

Sie müssen den alten MDM-Anbieter außer Kraft setzen bzw. das Abonnement des Dienst beenden, nachdem Sie zu Intune migriert sind. Darüber hinaus müssen Sie alle nicht benötigten Infrastrukturanforderungen entfernen, indem Sie den Anweisungen des MDM-Anbieters folgen.

