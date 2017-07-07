---
title: "Überwachen von App-Informationen und -Zuweisungen"
titleSuffix: Intune on Azure
description: "Wenn Sie Benutzern oder Geräten eine App zugewiesen haben, können Sie mithilfe dieser Informationen den Status der App überwachen.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d588ecc8f2e211b5a8ccdfe7b7720869cc6327b8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Überwachen von App-Informationen und -Zuweisungen mit Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune bietet eine Reihe von Möglichkeiten, mit denen Sie die Eigenschaften von verwalteten Apps sowie deren Zuweisungsstatus überwachen können.

1. Wählen Sie in der Workload **Mobile Apps** die Option **Verwalten** > **Apps** aus.
2. Wählen Sie auf dem Blatt mit der Liste der Apps die App aus, für die Sie Informationen anzeigen möchten. Daraufhin wird das Blatt <*App-Name*> **Geräteinstallationsstatus** angezeigt: ![Blatt mit Installationsstatus zur App](./media/monitor-apps.png).

Nehmen Sie dann eine der folgenden Aktionen, um weitere Informationen zu Ihren Apps und deren Zuweisungen zu erhalten.

## <a name="general"></a>Allgemein

- **Übersicht**: Bietet eine grundlegende Übersicht über die App sowie Informationen zum Status aller Zuweisungen für die App. Sie können eines der Diagramme auswählen, um die Blätter **Geräteinstallationsstatus** oder **Benutzerinstallationsstatus** zu öffnen, um ausführlichere Informationen zu erhalten.

## <a name="manage"></a>Verwalten von

- **Eigenschaften**: Ermöglicht es Ihnen, Informationen zur ausgewählten App anzuzeigen und zu ändern. Weitere Informationen zu Eigenschaften von Apps finden Sie unter [Hinzufügen von Apps zu Microsoft Intune](apps-add.md).
- **Zuweisungen**: Stellt Informationen zu Zuweisungen für diese App bereit. Weitere Informationen finden Sie unter [Zuweisen von Apps zu Gruppen mit Microsoft Intune](apps-deploy.md).

## <a name="monitor"></a>Überwachen

- **Geräteinstallationsstatus**: Enthält ausführliche Informationen zu jedem Gerät, dem Sie die ausgewählte App zugewiesen haben, einschließlich Gerätename, Betriebssystem, wann das Gerät zuletzt bei Intune eingecheckt war und dem Status der App-Installation.
- **Benutzerinstallationsstatus**: Enthält ausführliche Informationen zum Benutzer, dem Sie die ausgewählte App zugewiesen haben, einschließlich der Anzahl der Installationen der App, über die der Benutzer auf all seinen Geräten verfügt sowie Informationen zu möglichen Installationsfehlern.