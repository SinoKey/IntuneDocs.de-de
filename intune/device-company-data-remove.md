---
title: "Entfernen von Unternehmensdaten von Geräten mit Intune"
titleSuffix: Intune on Azure
description: "Erfahren Sie, wie Sie von den Geräten, die Sie über Intune verwalten, nur die Unternehmensdaten entfernen.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f021e95f-157f-4e8a-9253-1cff03d6ee3e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 39acd12333e9685f94d23416fb1a61ce93f45476
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2017
---
# <a name="remove-company-data-from-intune-managed-devices"></a>Entfernen von Unternehmensdaten von über Intune verwalteten Geräten


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Die Option **Unternehmensdaten entfernen** entfernt nur Unternehmensdaten von Geräten, die über Intune verwaltet werden. Es werden keine persönlichen Daten vom Gerät entfernt. Das Gerät wird nicht mehr von Intune verwaltet und kann damit nicht mehr auf Unternehmensressourcen zugreifen (nicht unterstützt für Windows-Geräte, die mit Azure Active Directory verbunden sind).

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.
4. Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.
5. Wählen Sie aus der Liste der verwalteten Geräte ein Gerät aus, und wählen Sie dann die Remotegeräteaktion **Unternehmensdaten entfernen**.

Um den Status der gerade ausgeführten Aktion anzuzeigen, wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Geräteaktionen** aus.
