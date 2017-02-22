---
title: "Benutzerdefinierte Intune-Einstellungen für Windows Phone 8.1-Geräte | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Erfahren Sie etwas über die Einstellungen, die Sie in einem benutzerdefinierten Windows Phone 8.1-Profil verwenden können."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 21c55041-3821-4a62-9f85-855b97dba269
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5ab494a3dd1e1bdea9703ab314574b192c5208ee
ms.openlocfilehash: 3656db2d9828dcc16c479ba072de691848fdd23b


---

# <a name="custom-settings-for-windows-phone-81-devices-in-intune-azure-preview"></a>Benutzerdefinierte Einstellungen für Windows Phone 8.1-Geräte in der Vorschau von Intune in Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Stellen Sie mithilfe des **benutzerdefinierten** Profils für Windows Phone 8.1 von Microsoft Intune die OMA-URI-Einstellungen bereit, um Features auf Windows Phone 8.1-Geräten zu steuern. Dies sind die Standardeinstellungen, die viele Hersteller von mobilen Geräten verwenden, um Gerätefunktionen zu steuern.

Diese Funktion soll es Ihnen ermöglichen, Einstellungen bereitzustellen, die nicht mit anderen Intune-Richtlinien konfigurierbar sind.

## <a name="custom-policy-settings-for-windows-phone-81-devices"></a>Benutzerdefinierte Richtlinieneinstellungen für Windows Phone 8.1-Geräte

1. Anweisungen zu den ersten Schritten finden Sie unter [Konfigurieren von benutzerdefinierten Geräteeinstellungen in Microsoft Intune](how-to-configure-custom-settings.md).
2. Wählen Sie auf dem Blatt **Profil erstellen** die Option **Einstellungen** aus, um eine oder mehrere OMA-URI-Einstellungen hinzufügen.
3. Konfigurieren Sie auf dem Blatt **Zeile hinzufügen** die folgenden Werte für jede Einstellung:
    - **Name:** Geben Sie einen eindeutigen Namen für die OMA-URI-Einstellung ein, damit Sie sie in der Liste der Einstellungen einfacher identifizieren können.
    - **Beschreibung:** Geben Sie eine Beschreibung ein, die eine Übersicht über die Einstellung bietet, und andere relevante Informationen, die Ihnen die Suche danach erleichtern.
    - **OMA-URI:** Geben Sie den OMA-URI an, für den Sie eine Einstellung bereitstellen möchten.
    - **Datentyp:** Wählen Sie den Datentyp aus, in dem Sie diese OMA-URI-Einstellung angeben. Wählen Sie aus **Zeichenfolge**, **Datum und Uhrzeit**, **Ganze Zahl**, **Gleitkomma** oder **Boolesch** aus.
    - **Wert:** Geben Sie den gewünschten Wert an, der dem von Ihnen eingegebenen OMA-URI zugeordnet werden soll.

4. Klicken Sie abschließend auf **OK**, und fahren Sie bei Bedarf mit dem Hinzufügen weiterer Einstellungen fort.



<!--HONumber=Feb17_HO1-->


