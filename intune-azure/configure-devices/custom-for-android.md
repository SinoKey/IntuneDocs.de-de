---
title: "Benutzerdefinierte Intune-Einstellungen für Android-Geräte | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Erfahren Sie etwas über die Einstellungen, die Sie in einem benutzerdefinierten Android-Profil verwenden können."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 6a49a87984a465c6a656ad40122d0e64b23599fc
ms.lasthandoff: 02/16/2017


---

# <a name="custom-settings-for-android-devices-in-microsoft-intune"></a>Benutzerdefinierte Einstellungen für Android-Geräte in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Stellen Sie mithilfe des **benutzerdefinierten** Profils für Android von Microsoft Intune die OMA-URI-Einstellungen bereit, um Features auf Android-Geräten zu steuern. Dies sind die Standardeinstellungen, die viele Hersteller von mobilen Geräten verwenden, um Gerätefunktionen zu steuern.

Diese Funktion soll es Ihnen ermöglichen, Android-Einstellungen bereitzustellen, die nicht mit Intune-Richtlinien konfigurierbar sind.

## <a name="custom-profile-settings-for-android-devices"></a>Benutzerdefinierte Profileinstellungen für Android-Geräte

1. Anweisungen zu den ersten Schritten finden Sie unter [Konfigurieren von benutzerdefinierten Geräteeinstellungen in Microsoft Intune](how-to-configure-custom-settings.md).
2. Wählen Sie auf dem Blatt **Profil erstellen** die Option **Einstellungen** aus, um eine oder mehrere OMA-URI-Einstellungen hinzufügen.
3. Konfigurieren Sie auf dem Blatt **Zeile bearbeiten** die folgenden Werte für jede Einstellung:
    - **Name:** Geben Sie einen eindeutigen Namen für die OMA-URI-Einstellung ein, damit Sie sie in der Liste der Einstellungen einfacher identifizieren können.
    - **Beschreibung:** Geben Sie eine Beschreibung ein, die eine Übersicht über die Einstellung bietet, und andere relevante Informationen, die Ihnen die Suche danach erleichtern.
    - **Datentyp:** Wählen Sie den Datentyp aus, in dem Sie diese OMA-URI-Einstellung angeben. Wählen Sie aus **Zeichenfolge**, **Zeichenfolge (XML)**, **Datum und Uhrzeit**, **ganze Zahl**, **Gleitkomma** oder **Boolesch** aus.
    - **OMA-URI:** Geben Sie den OMA-URI an, für den Sie eine Einstellung bereitstellen möchten.
    - **Wert:** Geben Sie den gewünschten Wert an, der dem von Ihnen eingegebenen OMA-URI zugeordnet werden soll.
4. Klicken Sie abschließend auf **OK**, und fahren Sie bei Bedarf mit dem Hinzufügen weiterer Einstellungen fort.

