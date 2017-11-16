---
title: "Überwachen von App-Informationen und -Zuweisungen"
titlesuffix: Azure portal
description: "Wenn Sie Benutzern oder Geräten eine App zugewiesen haben, können Sie mithilfe dieser Informationen den Status der App überwachen.\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3736b6d43f5cd3b6c75097a2ceabebffd75f0caa
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2017
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Überwachen von App-Informationen und -Zuweisungen mit Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune bietet eine Reihe von Möglichkeiten, mit denen Sie die Eigenschaften von verwalteten Apps sowie deren Zuweisungsstatus überwachen können.

1. Melden Sie sich im Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** + **Intune** aus.
3. Klicken Sie in der Workload **Mobile Apps** auf **Apps** in der Gruppe **Verwalten**.
     
    ![Blatt „App-Installationsstatus“](./media/monitor-apps.png)
5. Wählen Sie in der Liste auf dem Blatt „Apps“ eine App aus. Ihnen wird dann das Blatt <*App-Name*> **Geräteinstallationsstatus** angezeigt.

Der Bericht zum Geräteinstallationsstatus enthält folgende Spalten:

1.  **Gerätename**: Der Name des Gerätetyps
2.  **Benutzername**: Der Name des Benutzers
3.   **Plattform**: Das auf dem Gerät installierte Betriebssystem
4.  **Version**: Die Versionsnummer der App
5.   **Status**: Die möglichen Statuswerte für Apps sind: **Installiert**, **Nicht installiert**, **Installation steht aus** und **Fehler**.
6. **Statusdetails**: Eine lesbare Beschreibung des App-Status auf dem Gerät
7. **Letzter Check-In**: Wann das Gerät zuletzt in Intune eingecheckt wurde

Nehmen Sie dann eine der folgenden Aktionen, um weitere Informationen zu Ihren Apps und deren Zuweisungen zu erhalten.

## <a name="general"></a>Allgemein

- **Übersicht**: Bietet eine grundlegende Übersicht über die App sowie Informationen zum Status aller Zuweisungen für die App. Sie können eines der Diagramme auswählen, um die Blätter **Geräteinstallationsstatus** oder **Benutzerinstallationsstatus** zu öffnen, um ausführlichere Informationen zu erhalten.

## <a name="manage"></a>Verwalten von

- **Eigenschaften**: Ermöglicht es Ihnen, Informationen zur ausgewählten App anzuzeigen und zu ändern. Weitere Informationen zu Eigenschaften von Apps finden Sie unter [Hinzufügen von Apps zu Microsoft Intune](apps-add.md).
- **Zuweisungen**: Stellt Informationen zu Zuweisungen für diese App bereit. Weitere Informationen finden Sie unter [Zuweisen von Apps zu Gruppen mit Microsoft Intune](apps-deploy.md).

## <a name="monitor"></a>Überwachen

- **Geräteinstallationsstatus**: Enthält ausführliche Informationen zu jedem Gerät, dem Sie die ausgewählte App zugewiesen haben, einschließlich Gerätename, Betriebssystem, wann das Gerät zuletzt bei Intune eingecheckt war und dem Status der App-Installation.
- **Benutzerinstallationsstatus**: Enthält ausführliche Informationen zum Benutzer, dem Sie die ausgewählte App zugewiesen haben, einschließlich der Anzahl der Installationen der App, über die der Benutzer auf all seinen Geräten verfügt sowie Informationen zu möglichen Installationsfehlern.