---
title: "Intune-Konfigurationseinstellungen für freigegebene iOS-Geräte"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie mehr über die Intune-Einstellungen zur Anzeige von Informationen auf dem iOS-Geräte-Sperrbildschirm."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 4/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f122e4ee-90e7-4b42-b801-8c1c7c0a5bf7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 2bc107054f438d5ed72de87dec85900f871c0acc
ms.lasthandoff: 04/19/2017


---

# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a>Konfigurationseinstellungen für freigegebene Geräte zum Anzeigen von Nachrichten auf dem iOS-Geräte-Sperrbildschirm

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Konfigurationseinstellungen für freigegebene Geräte ermöglichen Ihnen, optionalen Text anzugeben, der im Anmeldefenster und auf dem Sperrbildschirm angezeigt wird (z.B. eine „Wenn verloren, zurück an“-Nachricht und Informationen zum Bestandskennzeichen). 

>[!IMPORTANT]
> Diese Funktion wird auf überwachten Geräten mit iOS 9.3 und höher unterstützt.

1. Wählen Sie auf dem Blatt **Gerätefunktionen** **Konfiguration freigegebener Geräte (nur überwacht)**.
2. Konfigurieren Sie auf dem Blatt **Konfiguration freigegebener Geräte (nur überwacht)** Folgendes:
    - **Bestandskennzeicheninformationen**: Geben Sie Informationen zum Bestandskennzeichen des Geräts ein. Beispiel: **Im Besitz von Contoso Corp.**. Die von Ihnen eingegebenen Informationen werden auf alle Geräte angewendet, denen Sie dieses Profil zuweisen.
    - **Fußnote zum Sperrbildschirm**: Geben Sie einen Hinweis ein, der Ihnen helfen könnte, das Gerät zurückzubekommen, wenn es verloren geht oder gestohlen wird. Beispiel: **Wenn Sie das Gerät gefunden haben, rufen Sie bitte „Nummer“ an**.
3. Wenn Sie fertig sind, klicken Sie auf **OK**, bis Sie zum Blatt **Profil erstellen** zurückkehren, und wählen Sie dann **Erstellen** aus. 

