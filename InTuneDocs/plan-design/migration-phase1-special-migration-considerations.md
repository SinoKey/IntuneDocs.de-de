---
title: "Besondere Überlegungen bei der Migration | Microsoft-Dokumentation"
description: "In diesem Artikel werden Kunden darüber informiert, welche Aspekte sie vor dem Beginn einer Migration berücksichtigen sollten."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 634e84312fa1a93eb85bf70e1593ca11359b72ff
ms.lasthandoff: 03/27/2017


---

# <a name="phase-1-special-migration-considerations"></a>Phase 1: Besondere Überlegungen bei der Migration

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Es gibt spezielle Aspekte bei der Migration, die je nach vorhandener Umgebung des MDM-Anbieters zu berücksichtigen sind.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Apple Device Enrollment Programm (DEP) auf Werkseinstellungen zurücksetzen

Das Apple-Programm zur Geräteregistrierung (Device Enrollment Program, DEP) legt Gerätekonfigurationen fest, die vom Endbenutzer nicht entfernt werden können. Wenn Sie die erweiterten Verwaltungsfunktionen von DEP beibehalten möchten, muss das Gerät für die Anmeldung bei Intune auf die Werkseinstellungen zurückgesetzt werden.

Führen Sie folgende Schritte aus, um DEP weiterhin zum Verwalten der Geräte in Intune zu verwenden:

1.  Integrieren Sie [DEP in Intune](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune).

2.  Gehen Sie zu Ihrem Apple-DEP-Konto, und [weisen Sie die Seriennummern der DEP-Geräte von Ihrem vorhandenen MDM-Anbieter Intune neu zu](https://help.apple.com/deployment/business/#/tesf9562af26).

3.  [Synchronisieren](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) Sie Ihr DEP-Konto mit Intune.

4.  [Erstellen Sie geeignete DEP-Registrierungsprofile, und weisen Sie diese den Seriennummern in Intune zu](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune).

5.  Setzen Sie die Geräte auf die Werkseinstellungen zurück (entweder remote über den aktuellen MDM-Anbieter oder manuell auf jedem Gerät).

6.  Verteilen Sie die Geräte an Endbenutzer.

## <a name="next-steps"></a>Nächste Schritte 

[Phase 2: Die Migration](https://docs.microsoft.com/intune/plan-design/migration-phase2-migration-campaign)

