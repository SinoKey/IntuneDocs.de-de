---
title: "Vorbereitungen zum Konfigurieren von App-Schutzrichtlinien für Windows 10"
titleSuffix: Intune on Azure
description: Einrichten des MAM-Anbieters (Mobile Application Management) in Azure AD
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 6f2f0b610b900bb41a3c2bd7416b6db28434a155
ms.openlocfilehash: bf56d3a80f0d167baa95e9dfdb20d08e02590984
ms.contentlocale: de-de
ms.lasthandoff: 06/13/2017


---

# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Vorbereitungen zum Konfigurieren von App-Schutzrichtlinien für Windows 10

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Vor der Erstellung einer Windows 10-App-Schutzrichtlinie müssen Sie die mobile Anwendungsverwaltung (MAM) für Windows 10 aktivieren, indem Sie den MAM-Anbieter in Azure AD einrichten. Mit dieser Konfiguration können Sie den Registrierungsstatus definieren, wenn Sie eine neue WIP-Richtlinie (Windows Information Protection) in Intune erstellen.

> [!NOTE]
> Der Registrierungsstatus kann entweder „MAM“ oder „Mobile Geräteverwaltung (MDM)“ lauten.

## <a name="to-configure-the-mam-provider"></a>Konfigurieren des MAM-Anbieters

1.  Navigieren Sie zum [Azure-Portal](https://portal.azure.com/) und melden Sie sich mit Ihren Intune-Anmeldeinformationen an.

2.  Wählen Sie im linken Menü **Azure Active Directory** aus.

    ![Konfiguration des MAM-Anbieters](./media/mam-provider-sc-1.png)

3.  Das Blatt **Azure AD** wird geöffnet. Wählen Sie **Mobilität (MDM und MAM)** und klicken Sie dann auf **Microsoft Intune**.

    ![Mobilität (MDM und MAM)](./media/mam-provider-sc-1.png)

4.  Das Blatt zur Konfiguration wird geöffnet. Wählen Sie zuerst **Standard-MAM-URLs wiederherstellen** aus und konfigurieren Sie dann Folgendes:

    a.  MAM-Benutzerbereich: Mit MAM können Sie Unternehmensdaten für bestimmte Benutzergruppen, die Windows 10-Geräte verwenden, oder alle Benutzer schützen.

    b.  URL zu den MAM-Nutzungsbedingungen: Die URL zum Endpunkt für die Nutzungsbedingungen des MAM-Diensts. Hierdurch werden die Bedingungen des MAM-Diensts für Endbenutzer angezeigt.

    c.  URL für MAM-Ermittlung: Dies ist die URL, nach denen Geräte beim Anwenden von App-Schutzrichtlinien suchen müssen.

    d.  URL für MAM-Kompatibilität:

5.  Nachdem Sie diese Einstellungen konfiguriert haben, wählen Sie **Speichern**.

## <a name="next-steps"></a>Nächste Schritte

[Erstellen einer WIP-App-Schutzrichtlinie](windows-information-protection-policy-create.md)
