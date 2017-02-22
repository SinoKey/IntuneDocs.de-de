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
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: 3c0de501c172484f036aa2d812f0c40fcfa1d93f

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

1. Wählen Sie im Azure-Portal **Weitere Dienste** aus, geben Sie **Intune** in das Textfeld ein, und wählen Sie dann **Andere** > **Intune** aus.

2. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Übersicht** aus.

3. Wählen Sie auf dem Blatt **Mit der Geräteverwaltung beginnen** die Option **MDM-Autorität auf Intune festlegen** aus. Eine Meldung zeigt an, dass Sie die MDM-Autorität erfolgreich auf Intune festgelegt haben.



<!--HONumber=Feb17_HO1-->


