---
title: Helpdeskportal zur Problembehandlung
titleSuffix: Intune on Azure
description: "Helpdeskmitarbeiter verwenden das Portal zur Problembehandlung, um die technischen Problemen der Benutzer zu lösen."
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 7aad054f0861522174faa01b979083a818c106af
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2017
---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>Unterstützen von Benutzern im Portal zur Problembehandlung in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Das Portal zur Problembehandlung ermöglicht Helpdesk-Operatoren und Intune-Administratoren das Anzeigen von Benutzerinformationen zum Beheben von Hilfeanfragen von Benutzern. Organisationen, deren Personal Helpdesk-Operatoren einschließt, können den **Helpdesk-Operator** einer Gruppe von Benutzern zuweisen, die dann über das Blatt Problembehandlung Benutzern helfen können.

Wenn ein Benutzer beispielsweise den Support wegen eines technischen Problems mit Intune kontaktiert, gibt der Helpdesk-Operator den Namen des Benutzers ein. Intune zeigt nützliche Daten, die Ihnen beim Lösen vieler Probleme der Ebene 1 helfen können, einschließlich:
- Benutzerstatus
- Zuweisungen
- Fehler bei der App-Installation
- Kompatibilitätsprobleme
- Das Gerät reagiert nicht.
-   Das Gerät erhält keine VPN- oder WLAN-Einstellungen
-   App-Installationsfehler


## <a name="add-help-desk-operators"></a>Hinzufügen von Helpdeskoperatorn
Als Intune-Administrator können Sie die Rolle „Helpdesk-Operator“ einer Benutzergruppe zuweisen. Mitglieder dieser Gruppe können das Administratorportal verwenden, um Probleme von Benutzern zu lösen. Jeder Helpdesk-Operator benötigt eine Intune-Lizenz zum Zugriff auf das Intune-Portal. Erfahren Sie, wie Sie [Intune-Lizenzen zuweisen](licenses-assign.md) können.

So fügen Sie Helpdesk-Benutzer hinzu:
1. [Fügen Sie Benutzer zu Intune hinzu](users-add.md) (falls nötig)
2. [Erstellen Sie eine Helpdesk-Gruppe](groups-add.md), und fügen Sie der Gruppe Benutzer hinzu.
3. [Weisen Sie die RBAC-Helpdesk-Operatorrolle zu](role-based-access-control.md#built-in-roles), oder [erstellen Sie eine benutzerdefinierte Rolle](role-based-access-control.md#custom-roles) mit folgenden Berechtigungen:
  - MobileApps: Lesen
  - ManagedApps: Lesen
  - ManagedDevices: Lesen
  - Organization: Lesen
  - DeviceCompliancePolices: Lesen
  - DeviceConfigurations: Lesen

  ![Screenshot des Intune-Portals mit hervorgehobenen Intune-Rollen und einer Liste von integrierten Rollen, inklusive „Helpdesk-Operator“](./media/help-desk-user-add.png)

4. Um Helpdesk-Operatoren Berechtigungen zuzuweisen, um die Dienstintegrität anzuzeigen und Support-Tickets für Intune zu öffnen, [gewähren Sie Benutzern Berechtigungen](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal) als **Dienstadministrator**. Gewähren Sie keine **Intune-Dienstadministratorberechtigungen**, da diese Verzeichnisrolle über mehr Rechte verfügt, als für Helpdesk-Operatoren erforderlich sind.

## <a name="access-the-troubleshooting-portal"></a>Zugriff auf das Problembehandlungsportal

Helpdeskmitarbeiter und Intune-Administratoren können auf zwei Arten auf das Portal zur Problembehandlung zugreifen:
- Öffnen Sie [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) in einem Webbrowser, um nur das Portal für die Problembehandlung anzuzeigen.
  ![Screenshot der Konsole zur Problembehandlung](./media/help-desk-console.png)
- Melden Sie sich im Azure-Portal an, wählen Sie **Mehr Dienste** > **Überwachung + Verwaltung** > **Intune**, und wechseln Sie anschließend zu **Hilfe und Support** > **Problembehandlung**.

Klicken Sie auf **Benutzer auswählen**, um einen Benutzer sowie dessen Details anzuzeigen.

![Screenshot der Workload zur Problembehandlung in Intune mit dem Link „Benutzer auswählen“](media/help-desk-user.png)

## <a name="use-the-troubleshooting-portal"></a>Verwenden des Problembehandlungsportals

Im Problembehandlungsportal können Sie **Benutzer auswählen** zum Anzeigen von Informationen zu einem Benutzer wählen. Benutzerinformationen können Ihnen erleichtern, den aktuellen Status von Benutzern und ihren Geräten zu verstehen. Das Problembehandlungsportal zeigt die folgenden Details an:
- **Status des Kontos**
- **Benutzerstatus**
- **Geräte** mit Geräteaktionen
- **Gruppenmitgliedschaft**
- **Schutzstatus der App**
