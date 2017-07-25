---
title: "Festlegen von Registrierungseinschränkungen in Intune"
titleSuffix: Intune on Azure
description: "Schränken Sie die Registrierung plattformbezogen ein, und legen Sie in Intune einen Grenzwert für die Geräteregistrierung fest. \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: amyros
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ce779e8dad2c9813d5faf1f03bca9b33690508fe
ms.sourcegitcommit: b287025b1a0d09d41faf51cf98c34b676fa1d98e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2017
---
# <a name="add-groups-in-intune"></a>Hinzufügen von Gruppen in Intune
Intune verwendet Azure Active Directory-Gruppen (AD) zur Verwaltung von Geräten und Benutzern. Als Intune-Administrator können Sie Gruppen entsprechend der Anforderungen Ihrer Organisation einrichten. Sie können Gruppen erstellen, um Benutzer oder Geräte nach geografischem Standort, Abteilung oder Hardwareeigenschaften zu organisieren. Sie können Gruppen zur bedarfsgerechten Verwaltung von Aufgaben verwenden. So können Sie beispielsweise Richtlinien für viele Benutzer festlegen oder Apps für eine Reihe von Geräten bereitstellen.

In diesem Thema wird das Hinzufügen von Gruppen für die Verwendung in Intune erläutert.

Sie können die folgenden Gruppentypen hinzufügen:
- **Zugewiesene Gruppen**: Manuelles Hinzufügen von Benutzern oder Geräten in eine statische Gruppe
- **Dynamische Gruppen**: (Azure Active Directory Premium) Dynamisches Erstellen von Benutzer- oder Gerätegruppen, die durch einfache oder erweiterte Regeln definiert werden

## <a name="add-a-new-group"></a>Hinzufügen einer neuen Gruppe

Führen Sie die folgenden Schritte aus, um eine neue Gruppe zu erstellen:
1. Wechseln Sie im Intune-Portal zu **Gruppen**, und wählen Sie dann auf dem Blatt **Alle Gruppen** die Option **Neue Gruppe** aus.
  ![Screenshot des Intune-Portals mit ausgewählter Option „Neue Gruppe“](./media/groups-add-new.png)
2. Geben Sie den **Namen** und die **Beschreibung** der neuen Gruppe an. Diese Eigenschaften werden nur im Intune-Portal und nicht den Benutzern angezeigt.

3. Wählen Sie den **Mitgliedschaftstyp** aus:
  - **Zugewiesen**: Zur Erstellung einer Gruppe mit manuell zugewiesenen Mitgliedern. Weitere Informationen zu [zugewiesenen Azure AD-Gruppen](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
  - **Dynamischer Benutzer**: Zur Erstellung einer Benutzergruppe, die durch eine **Dynamische Abfrage** definiert wird.
  - **Dynamisches Gerät**: Zur Erstellung einer Gerätegruppe, die durch eine **Dynamische Abfrage** definiert wird.

  ![Screenshot der Intune-Gruppeneigenschaften mit Name, Beschreibung, Mitgliedschaftstyp, Option „Office-Features aktivieren“ und Mitgliedern](./media/groups-add-properties.png)

  Mit Azure AD können Sie dynamische Gruppen auf der Grundlage von Regeln erstellen, die die Mitgliedschaft definieren. Weitere Informationen zum [Erstellen von attributbasierten dynamischen Gruppen](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

4. Sie können die Option **Office-Features aktivieren** auswählen, um Mitgliedern von Benutzergruppen Zugriff auf freigegebene Office 365-Apps zu gewähren.
5. Klicken Sie auf die Option **Erstellen**, um die neue Gruppe hinzuzufügen.

## <a name="see-also"></a>Weitere Informationen:
- [Verwalten des Zugriffs auf Ressourcen mit Azure Active Directory-Gruppen](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [Klassische Intune-Gruppen im Azure-Portal](groups-get-started.md)
