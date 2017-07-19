---
title: "Verwalten von Apps aus dem Windows Store für Unternehmen"
titleSuffix: Intune on Azure
description: "Erfahren Sie, wie Sie Apps aus dem Windows Store für Unternehmen in Intune synchronisieren und dann zuweisen und nachverfolgen können."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: de6ed7623e33a50bdf8452cbf1bad9c648b13d04
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune"></a>Verwalten von Apps, die im Windows Store für Unternehmen mit Microsoft Intune erworben wurden

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Im [Windows Store für Unternehmen](https://www.microsoft.com/business-store) können Sie Apps für Ihre Organisation suchen und einzeln oder im Rahmen eines Volumenprogramms erwerben. Indem Sie den Store mit Microsoft Intune verbinden, können Sie im Rahmen von Volumenprogrammen erworbene Apps über das Intune-Portal verwalten. Beispiel:
* Sie können die Liste der Apps, die Sie im Speicher erworben haben, mit Intune synchronisieren.
* Synchronisierte Apps werden in der Intune-Verwaltungskonsole angezeigt und können wie alle anderen Apps zugewiesen werden.
* Sie können in der Intune-Verwaltungskonsole die Anzahl der verfügbaren und der verwendeten Lizenzen nachverfolgen.
* Intune blockiert die Zuweisung und Installation von Apps, wenn nicht genügend Lizenzen vorhanden sind.

## <a name="before-you-start"></a>Vorbereitung

Überprüfen Sie die folgenden Informationen, bevor Sie beginnen, Apps aus dem Windows Store für Unternehmen zu synchronisieren und zuzuweisen:

- Konfigurieren Sie Intune als Autorität zur Verwaltung mobiler Geräte für Ihre Organisation.
- Sie müssen im Windows Store für Unternehmen über ein registriertes Konto verfügen.
- Sobald ein Konto für den Windows Store für Unternehmen Intune zugeordnet wurde, können Sie dieses zugeordnete Konto nicht mehr ändern.
- Apps, die im Store erworben wurden, können Intune nicht manuell hinzugefügt oder daraus gelöscht werden. Sie können nur mit dem Windows Store für Unternehmen synchronisiert werden.
- Intune synchronisiert online und offline lizenzierte Apps, die Sie aus dem Windows Store für Unternehmen erworben haben.
- Es können nur kostenlose Offline-Apps mit Intune synchronisiert werden.
- Geräte müssen mit Active Directory Domain Services oder einem Arbeitsbereich verknüpft sein, damit diese Funktion verwendet werden kann.
- Registrierte Geräte müssen die Version 1511 oder höher von Windows 10 verwenden.

## <a name="associate-your-windows-store-for-business-account-with-intune"></a>Verknüpfen Ihres Kontos für den Windows Store für Unternehmen mit Intune
Bevor Sie die Synchronisierung in der Intune-Konsole aktivieren, müssen Sie Ihr Konto für den Windows Store für Unternehmen so konfigurieren, dass Intune als Verwaltungstool verwendet wird:
1. Stellen Sie sicher, dass Sie sich beim Windows Store für Unternehmen und bei Intune mit demselben Mandantenkonto anmelden.
2. Wählen Sie im Windows Store für Unternehmen **Einstellungen** > **Verwaltungstools** aus.
3. Wählen Sie auf der Seite „Verwaltungstools“ die Option **Verwaltungstool hinzufügen** und dann **Microsoft Intune** aus.

> [!NOTE]
> Zuvor konnten Sie nur ein Verwaltungstool zum Zuweisen von Apps mit Windows Store für Unternehmen zuweisen. Nun können Sie mehrere Verwaltungstools dem Store zuordnen, z.B. Intune und Configuration Manager.

Sie können nun fortfahren und die Synchronisierung in der Intune-Konsole einrichten.

## <a name="configure-synchronization"></a>Konfigurieren der Synchronisierung

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Mobile Apps** aus.
1. Wählen Sie auf dem Blatt **Mobile Apps** die Option **Setup** > **Windows Store für Unternehmen** aus.
2. Klicken Sie auf **Aktivieren**.
3. Klicken Sie auf den Link zur Registrierung für den Windows Store für Unternehmen, falls Sie dies noch nicht getan haben, und weisen Sie Ihr Konto wie oben beschrieben zu.
5. Wählen Sie in der Dropdownliste **Sprache** die Sprache aus, in der Apps aus dem Windows Store für Unternehmen im Intune-Portal angezeigt werden. Die Installation der Apps erfolgt unabhängig von der Anzeigesprache in der Sprache des Endbenutzers, sofern verfügbar.
6. Klicken Sie auf **Synchronisieren**, um die im Windows Store erworbenen Apps in Intune abzurufen.

## <a name="synchronize-apps"></a>Synchronisieren von Apps

1. Wählen Sie in der Workload **Mobile Apps** die Option **Setup** > **Windows Store für Unternehmen** aus.
2. Klicken Sie auf **Synchronisieren**, um die im Windows Store erworbenen Apps in Intune abzurufen.

## <a name="assign-apps"></a>Zuweisen von Apps

Sie weisen Apps aus dem Store auf die gleiche Weise wie andere Intune-Apps zu. Weitere Informationen finden Sie unter [Zuweisen von Apps zu Gruppen mit Microsoft Intune](apps-deploy.md). Anstelle der Zuweisung von Apps auf der Seite **Alle Apps** weisen Sie diese über die Seite **Lizenzierte Apps** zu.

Offline-Apps können Benutzergruppen, Gerätegruppen oder Gruppen mit Benutzern und Geräten als Ziel haben.
Offline-Apps können für einen bestimmten Benutzer auf einem Gerät oder für alle Benutzer auf einem Gerät installiert werden. 


Wenn Sie eine App aus dem Windows Store für Unternehmen zuweisen, wird von jedem Benutzer, der die App installiert, eine Lizenz verwendet. Wenn alle verfügbaren Lizenzen für eine zugewiesene App verwendet werden, können Sie keine weiteren Kopien zuweisen. Unternehmen Sie eine der folgenden Aktionen aus:
* Deinstallieren Sie die App auf einigen Geräten.
* Beschränken Sie die aktuelle Zuweisung auf die Anzahl von Benutzern, für die Sie über Lizenzen verfügen.
* Erwerben Sie zusätzliche Kopien der App im Windows Store für Unternehmen.


