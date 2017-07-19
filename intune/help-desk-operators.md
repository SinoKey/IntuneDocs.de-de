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
ms.openlocfilehash: 7a61c3703cd1016ef63c8baa371c3a21dca127fc
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2017
---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>Unterstützen von Benutzern im Portal zur Problembehandlung in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Das Portal zur Problembehandlung ermöglicht Helpdesk-Operatoren und Intune-Administratoren das Anzeigen von Benutzerinformationen zum Beheben von Hilfeanfragen von Benutzern. Organisationen, deren Personal Helpdesk-Operatoren einschließt, können den **Helpdesk-Operator** einer Gruppe von Benutzern zuweisen, die dann über das Blatt Problembehandlung Benutzern helfen können.

Wenn ein Benutzer beispielsweise den Support wegen eines technischen Problems mit Intune kontaktiert, gibt der Helpdesk-Operator den Namen des Benutzers ein. Intune zeigt relevante Informationen an, die beim Lösen von vielen Problemen der Ebene 1 helfen können, z.B. Benutzerstatus, App-Installationsfehler oder Kompatibilitätsprobleme. Die Probleme können Folgendes umfassen:
- Das Gerät reagiert nicht.
-   Das Gerät erhält keine VPN- oder WLAN-Einstellungen
-   App-Installationsfehler


## <a name="add-help-desk-operators"></a>Hinzufügen von Helpdeskoperatorn
Ein Intune-Administrator kann Benutzern auf zwei Weisen Helpdeskoperator-Berechtigungen zuweisen:
- Zuweisen der integrierten Rolle **Helpdesk-Operator**
- Erstellen und Zuweisen einer benutzerdefinierten Rolle

## <a name="assign-help-desk-operator-role"></a>Zuweisen der Rolle „Helpdesk-Operator“
Als Intune-Administrator können Sie die Rolle „Helpdesk-Operator“ einer Benutzergruppe zuweisen. Mitglieder dieser Gruppe können das Verwaltungsportal verwenden. Jeder Helpdesk-Operator benötigt eine Intune-Lizenz zum Zugriff auf das Intune-Portal. Erfahren Sie, wie Sie [Intune-Lizenzen zuweisen](licenses-assign.md) können.

1. Melden Sie sich als Intune-Administrator beim Intune-Portal an, und wählen Sie **Intune-Rollen** aus.
2. Wählen Sie auf der Workload **Intune-Rollen** **Helpdesk-Operator** > **Zuweisungen** und dann **Zuweisen** aus.
  ![Screenshot des Intune-Portals mit hervorgehobenen Intune-Rollen und einer Liste von integrierten Rollen, inklusive „Helpdesk-Operator“ mit hervorgehobener Schaltfläche „Zuweisungen“ und einem roten Kästchen um „Zuweisen“](./media/help-desk-user-assign.png)
3. Geben Sie einen **Zuweisungsnamen** (erforderlich) und eine **Zuweisungsbeschreibung** (optional) an, und weisen Sie dann **Mitglieder (Gruppen)** und **Bereich (Gruppen)** zu.
4. Mitglieder der Rolle „Helpdeskoperator“ können jetzt das Portal zur Problembehandlung verwenden.

Weitere Informationen zu Intune-Rollen finden Sie unter [Intune-Rollen (RBAC) für Microsoft Intune](role-based-access-control.md).

## <a name="create-a-custom-role-for-troubleshooting"></a>Erstellen einer benutzerdefinierte Rolle für die Problembehandlung
Als Intune-Administrator können Sie eine benutzerdefinierte Rolle erstellen, mit der Benutzer das Portal zur Problembehandlung mit Berechtigungen verwenden können, die den Anforderungen Ihres Unternehmens gerecht werden. Weitere Informationen zu Intune-Rollen finden Sie unter [Intune-Rollen (RBAC) für Microsoft Intune](role-based-access-control.md).

![Screenshot des Intune-Portals mit hervorgehobenen Intune-Rollen und einer Liste von integrierten Rollen, inklusive „Helpdesk-Operator“](./media/help-desk-user-add.png)

Um die Intune-Konsole für eine Helpdesk-Ansicht zu verwenden, sollte eine benutzerdefinierte Rolle „Helpdesk“ über die folgenden Berechtigungen verfügen:
- MobileApps: Lesen
- ManagedApps: Lesen
- ManagedDevices: Lesen
- Organization: Lesen

## <a name="access-the-troubleshooting-portal"></a>Zugriff auf das Problembehandlungsportal

Helpdeskmitarbeiter und Intune-Administratoren können auf zwei Arten auf das Portal zur Problembehandlung zugreifen:
- Öffnen Sie [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) in einem Webbrowser.
- Wechseln Sie im Intune-Portal zu **Hilfe und Support** > **Problembehandlung**.

![Screenshot der Workload zur Problembehandlung in Intune mit dem Link „Benutzer auswählen“](media/help-desk-user.png)

## <a name="use-the-troubleshooting-portal"></a>Verwenden des Problembehandlungsportals

Im Problembehandlungsportal können Sie **Benutzer auswählen** zum Anzeigen von Informationen zu einem Benutzer wählen. Benutzerinformationen können Ihnen erleichtern, den aktuellen Status von Benutzern und ihren Geräten zu verstehen. Das Problembehandlungsportal zeigt die folgenden Details an:
- **Mandantenstatus**
- **Benutzerstatus**
- **Geräte** und Geräteaktionen
- **Gruppenmitgliedschaft**
- **Schutzstatus der App**
