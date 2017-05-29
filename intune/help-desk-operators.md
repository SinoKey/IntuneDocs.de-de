---
title: Helpdeskportal zur Problembehandlung | Microsoft-Dokumentation
titleSuffix: Intune Azure preview
description: "Helpdeskmitarbeiter verwenden das Portal zur Problembehandlung, um die technischen Problemen der Benutzer zu lösen."
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: e6bc22ccaf8c2c98cd67667f8fe30071ccdbc714
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017

---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>Unterstützen von Benutzern im Portal zur Problembehandlung in Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Im Portal zur Problembehandlung können Helpdeskoperator und Intune-Administratoren Benutzer und Geräte anzeigen und Aufgaben ausführen, um technische Intune-Probleme zu lösen.

## <a name="add-help-desk-operators"></a>Hinzufügen von Helpdeskoperatorn
Ein Intune-Administrator kann Benutzern Helpdeskoperator-Berechtigungen zuweisen. Helpdeskbenutzer können dann das Intune-Portal anzeigen, aber keine Administratoraufgaben außerhalb der Arbeitsauslastung zur Problembehandlung anzeigen oder ausführen.

1. Melden Sie sich als Intune-Administrator beim [Azure-Portal](https:portal.azure.com) an, und wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune**.
2. Wählen Sie auf dem linken Navigationsblatt **Intune-Rollen**.
3. Wählen Sie auf der Arbeitsauslastung **Intune-Rollen** **Helpdeskoperator** und dann **Zuweisen**.
4. Geben Sie einen **Zuweisungsnamen** (erforderlich) und eine **Zuweisungsbeschreibung** (optional) an, und weisen Sie dann **Mitglieder (Gruppen)** und **Bereich (Gruppen)** zu.
5. Mitglieder der Rolle „Helpdeskoperator“ können jetzt das Portal zur Problembehandlung verwenden.

Weitere Informationen zu Intune-Rollen finden Sie unter [Intune-Rollen (RBAC) für Microsoft Intune](role-based-access-control.md).

## <a name="access-the-troubleshooting-portal"></a>Zugriff auf das Problembehandlungsportal

Helpdeskmitarbeiter und Intune-Administratoren können auf zwei Arten auf das Portal zur Problembehandlung zugreifen:
- Wählen Sie im [Azure-Portal](https://portal.azure.com) **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune**, und wählen Sie dann im linken Navigationsblatt **Problembehandlung**. Andere Arbeitsauslastungen sind im linken Navigationsblatt sichtbar, aber nicht verfügbar.

![Screenshot der Workload zur Problembehandlung in Intune mit dem Link „Benutzer auswählen“](media/help-desk-user.png)
- Öffnen Sie [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) in einem Webbrowser. Nur das Problembehandlungsportal wird angezeigt.

## <a name="use-the-troubleshooting-portal"></a>Verwenden des Problembehandlungsportals

Im Problembehandlungsportal können Sie **Benutzer auswählen** zum Anzeigen von Informationen für einen Benutzer auswählen. Benutzerinformationen können Ihnen erleichtern, den aktuellen Status von Benutzern und ihren Geräten zu verstehen. Das Problembehandlungsportal zeigt die folgenden Intune-Benutzer und Gerätedetails an:
- Benutzerkontoinformationen
- Benutzergruppenmitgliedschaft
- Gerätedetails

Helpdeskbenutzer können auch Remoteaufgaben auf Geräten ausführen, z.B. **Remotesperre**.

