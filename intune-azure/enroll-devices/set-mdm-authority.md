---
title: "Festlegen der Autorität für die Verwaltung mobiler Geräte | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Erfahren Sie, wie die Autorität für die Verwaltung mobiler Geräte in Intune festlegen. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: 72a162175e278faa236add5698d65233fa851c7b
ms.lasthandoff: 02/15/2017

---

# <a name="set-the-mobile-device-management-authority"></a>Festlegen der Autorität für die Verwaltung mobiler Geräte 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Die Einstellung für die Autorität für die Verwaltung mobiler Geräte bestimmt, wie Sie Ihre Geräte verwalten. Mögliche Konfigurationen:

- **Intune Standalone:** Ausschließliche Verwaltung in der Cloud, die Sie mithilfe des Azure-Portals konfigurieren. Ihnen stehen alle Funktionen von Intune zur Verfügung.

- **Intune Hybrid:** Integration der Intune-Cloudlösung in System Center Configuration Manager. Sie konfigurieren Intune mithilfe der Configuration Manager-Konsole.

- **Verwaltung mobiler Geräte für Office 365:** Integration von Office 365 in die Intune-Cloudlösung. Sie konfigurieren Intune über das Office 365 Admin Center. Ihnen steht eine Teilmenge der Funktionen von Intune Standalone zur Verfügung.

>[!IMPORTANT]
>Nachdem Sie die Autorität für die Verwaltung mobiler Geräte einmal festgelegt haben, müssen Sie sich für eine Änderung an den [Microsoft-Support](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune) wenden. Sie sollten Ihre Auswahl daher sorgfältig treffen.

**So richten Sie die Autorität für die Verwaltung mobiler Geräte ein**

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

2. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Übersicht** aus.

3. Wählen Sie auf dem Blatt **Mit der Geräteverwaltung beginnen** die Option **MDM-Autorität auf Intune festlegen** aus. Eine Meldung zeigt an, dass Sie die MDM-Autorität erfolgreich auf Intune festgelegt haben.

