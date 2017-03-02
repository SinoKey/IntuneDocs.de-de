---
title: "Konfigurieren der Einstellungen für Bildungseinrichtungen von iOS"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie etwas über die Einstellungen, die Sie zum Konfigurieren der Einstellungen für Bildungseinrichtungen auf iOS-Geräten verwenden können."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 44c427f8-0f22-43c2-8c29-e0f9fa533b1f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 8d801c0b264e95348f55b1d4046c00e43ead5d10
ms.lasthandoff: 02/18/2017


---

# <a name="how-to-configure-intune-education-settings-for-ios-devices-in-intune-azure-preview"></a>Konfigurieren von Intune-Einstellungen für Bildungseinrichtungen für iOS-Geräte in der Vorschau von Intune in Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="create-a-device-profile-containing-ios-education-settings"></a>Erstellen eines Geräteprofils mit iOS-Einstellungen für Bildungseinrichtungen

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Andere** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte konfigurieren** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
3. Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
4. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das Editionsupgradeprofil ein.
5. Wählen Sie in der Dropdownliste **Plattform** die Option **iOS** aus.
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **Bildungswesen** aus.
7. Wählen Sie auf dem Blatt **Bildungswesen** Folgendes aus:
    - **Stammzertifikatdatei für Lehrer**
    - **PKCS12-/PFX-Profil für Lehrer**
    - **Stammzertifikatdatei für Schüler und Studenten**
    - **PKCS12-/PFX-Profil für Schüler und Studenten**
8. Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.

