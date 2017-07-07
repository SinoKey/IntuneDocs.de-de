---
title: "Besondere Überlegungen bei der Migration"
description: "In diesem Artikel werden Kunden darüber informiert, welche Aspekte sie vor dem Beginn einer Migration berücksichtigen sollten."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: bc39ffd3a4f11a4c2b32f75dc5befcd8ce42f43e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2017
---
# <a name="special-migration-considerations"></a>Besondere Überlegungen bei der Migration

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Es gibt spezielle Aspekte bei der Migration, die je nach vorhandener Umgebung des MDM-Anbieters zu berücksichtigen sind.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Apple Device Enrollment Programm (DEP) auf Werkseinstellungen zurücksetzen

Das Apple-Programm zur Geräteregistrierung (Device Enrollment Program, DEP) legt Gerätekonfigurationen fest, die vom Endbenutzer nicht entfernt werden können. Wenn Sie die erweiterten Verwaltungsfunktionen von DEP beibehalten möchten, muss das Gerät für die Anmeldung bei Intune auf die Werkseinstellungen zurückgesetzt werden.

Um die Geräte in Intune weiter mit dem Programm zur Geräteregistrierung zu verwalten, [richten Sie die iOS-Geräteregistrierung mit dem Programm zur Geräteregistrierung ein](/intune/device-enrollment-program-enroll-ios).


## <a name="next-steps"></a>Nächste Schritte 

[Phase 2: Die Migration](migration-guide-campaign.md)
