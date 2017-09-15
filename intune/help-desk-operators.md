---
title: Helpdeskportal zur Problembehandlung
titlesuffix: Azure portal
description: "Helpdeskmitarbeiter verwenden das Portal zur Problembehandlung, um die technischen Problemen der Benutzer zu lösen."
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 14b47727428fcd6a16f9960e21f70ee64c7757d1
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2017
---
# <a name="use-the-troubleshooting-portal-to-help-users"></a>Verwenden des Problembehandlungsportals, um Benutzern zu helfen

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Das Portal zur Problembehandlung ermöglicht Helpdesk-Operatoren und Intune-Administratoren das Anzeigen von Benutzerinformationen zum Reagieren auf Hilfeanfragen von Benutzern. Organisationen, deren Personal Helpdesk-Operatoren einschließt, können den **Helpdesk-Operator** einer Gruppe von Benutzern zuweisen, die dann über das Blatt Problembehandlung Benutzern helfen können.

Wenn ein Benutzer beispielsweise den Support wegen eines technischen Problems mit Intune kontaktiert, gibt der Helpdesk-Operator den Namen des Benutzers ein. Intune zeigt nützliche Daten, die Ihnen beim Lösen vieler Probleme der Ebene 1 helfen können, einschließlich:
- Benutzerstatus
- Zuweisungen
- Kompatibilitätsprobleme
- Das Gerät reagiert nicht.
-   Das Gerät erhält keine VPN- oder WLAN-Einstellungen
-   App-Installationsfehler

## <a name="add-help-desk-operators"></a>Hinzufügen von Helpdeskoperatorn
Als Intune-Administrator können Sie die Rolle „Helpdesk-Operator“ einer Benutzergruppe zuweisen. Mitglieder dieser Gruppe können das Azure-Portal verwenden, um Probleme von Benutzern zu lösen. Jeder Helpdesk-Operator benötigt eine Intune-Lizenz zum Zugriff auf das Azure-Portal. Erfahren Sie, wie Sie [Intune-Lizenzen zuweisen](licenses-assign.md) können.

So fügen Sie Helpdesk-Benutzer hinzu:
1. [Fügen Sie Benutzer zu Intune hinzu](users-add.md), falls nötig.
2. [Erstellen Sie eine Helpdesk-Gruppe](groups-add.md), und fügen Sie der Gruppe Benutzer hinzu.
3. [Weisen Sie die RBCA-Rolle „Helpdeskbetreuer“ zu.](role-based-access-control.md#built-in-roles)

  ![Screenshot des Azure-Portals mit hervorgehobenen Intune-Rollen und einer Liste integrierter Rollen, darunter auch „Helpdesk-Operator“](./media/help-desk-user-add.png). Sie können auch eine [benutzerdefinierte Rolle erstellen](role-based-access-control.md#custom-roles), die Sie weiter anpassen können, um Helpdesk-Operatorn Zugriff zu gewähren.  Helpdeskbetreuer benötigen die folgenden Berechtigungen, um bei der Behebung von Problemen von Benutzern helfen zu können:
    - MobileApps: Lesen
    - ManagedApps: Lesen
    - ManagedDevices: Lesen
    - Organization: Lesen
    - DeviceCompliancePolices: Lesen
    - DeviceConfigurations: Lesen

4. Um Helpdesk-Operatoren Berechtigungen zuzuweisen, um die Dienstintegrität anzuzeigen und Support-Tickets für Intune zu öffnen, [gewähren Sie Benutzern Berechtigungen](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal) als **Dienstadministrator**. Gewähren Sie keine **Intune-Dienstadministratorberechtigungen**, da diese Verzeichnisrolle über mehr Rechte verfügt, als für Helpdesk-Operatoren erforderlich sind.

## <a name="access-the-troubleshooting-portal"></a>Zugriff auf das Problembehandlungsportal

Helpdeskmitarbeiter und Intune-Administratoren können auf zwei Arten auf das Portal zur Problembehandlung zugreifen:
- Öffnen Sie [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) in einem Webbrowser, um nur das Portal für die Problembehandlung anzuzeigen.
  ![Screenshot der Konsole zur Problembehandlung](./media/help-desk-console.png)
- Melden Sie sich im Azure-Portal an, wählen Sie **Mehr Dienste** > **Überwachung + Verwaltung** > **Intune**, und wechseln Sie anschließend zu **Hilfe und Support** > **Problembehandlung**.

Klicken Sie auf **Benutzer auswählen**, um einen Benutzer sowie dessen Details anzuzeigen.

## <a name="use-the-troubleshooting-portal"></a>Verwenden des Problembehandlungsportals

Im Problembehandlungsportal können Sie **Benutzer auswählen** zum Anzeigen von Informationen zu einem Benutzer wählen. Benutzerinformationen können Ihnen erleichtern, den aktuellen Status von Benutzern und ihren Geräten zu verstehen. Das Problembehandlungsportal zeigt die folgenden Details an:
- **Status des Kontos**
- **Benutzerstatus**
- **Geräte** mit Geräteaktionen
- **Gruppenmitgliedschaft**
- **Schutzstatus der App**
