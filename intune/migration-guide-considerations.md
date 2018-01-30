---
title: "Besondere Überlegungen bei der Migration"
description: "Dieser Artikel bietet spezielle Überlegungen bei der Migration, bevor Sie eine Migrationskampagne starten."
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 86f3f7f2c8066e1b7b50dfc5931184c394d4f15b
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="special-migration-considerations"></a>Besondere Überlegungen bei der Migration

Es gibt spezielle Aspekte bei der Migration, die je nach vorhandener Umgebung des MDM-Anbieters zu berücksichtigen sind.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Apple Device Enrollment Programm (DEP) auf Werkseinstellungen zurücksetzen

Das Apple-Programm zur Geräteregistrierung (Device Enrollment Program, DEP) legt Gerätekonfigurationen fest, die vom Endbenutzer nicht entfernt werden können. Wenn Sie die erweiterten Verwaltungsfunktionen von DEP beibehalten möchten, muss das Gerät für die Anmeldung bei Intune auf die Werkseinstellungen zurückgesetzt werden.

Um die Geräte in Intune weiter mit dem Programm zur Geräteregistrierung zu verwalten, [richten Sie die iOS-Geräteregistrierung mit dem Programm zur Geräteregistrierung ein](device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>Nächste Schritte

[Phase 2: Die Migration](migration-guide-campaign.md)
