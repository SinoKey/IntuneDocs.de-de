---
title: "AirPlay-Einstellungen für iOS-Geräte in Intune"
titleSuffix: Intune Azure preview
description: "Erfahren Sie, wie Sie Intune verwenden können, um iOS-Geräte automatisch mit AirPlay-kompatiblen Geräten zu verbinden."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: f1f7aa6a0b441b51f20d104c4353a1542a9e01ad
ms.lasthandoff: 04/19/2017


---

# <a name="intune-airplay-settings-for-ios-devices"></a>AirPlay-Einstellungen für iOS-Geräte in Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Verwenden Sie diese Einstellungen, um von Ihnen verwaltete iOS-Geräte mit AirPlay-kompatiblen Geräten (z.B. Apple TV-Geräten) in Ihrem Netzwerk zu verbinden.
Diese Funktion ermöglicht Folgendes:

- **Konfigurieren einer Geräte- und Kennwortliste**: Stellen Sie Geräten die Namen und Kennwörter von AirPlay-Geräten bereit, damit diese automatisch eine Verbindung herstellen können, sobald sie sich im Empfangsbereich befinden. Wenn Sie Kennwörter angeben, müssen die Endbenutzer diese beim Herstellen der Verbindung nicht bereitstellen.
- **Konfigurieren von zulässigen Zielen**: Konfigurieren Sie eine Liste mit AirPlay-Geräten (anhand der Geräte-ID). Endbenutzer sehen nur die von Ihnen aufgelisteten Geräte und können nur mit diesen Geräten eine Verbindung herstellen (nur für überwachte Geräte).

## <a name="get-started"></a>Erste Schritte

1. Wählen Sie auf dem Blatt **Gerätefunktionen** die Option **AirPlay** aus.
2. Wählen Sie auf dem Blatt **AirPlay** eine oder beide der folgenden Aktionen aus:

## <a name="configure-a-device-and-password-list"></a>Konfigurieren einer Geräte- und Kennwortliste

1. Geben Sie auf dem Blatt **Kennwörter** den **Gerätenamen** und das **Kennwort** eines AirPlay-Geräts ein, z.B. **Contoso Apple TV**.
2. Klicken Sie nach dem Eingeben der Gerätedetails auf **Hinzufügen**. Das Gerät wird in der Liste **Gerätename** angezeigt.
3. Fügen Sie nach Bedarf weitere Geräte hinzu. Wenn Sie fertig sind, wählen Sie **OK** aus.


## <a name="configure-allowed-destinations"></a>Konfigurieren von zulässigen Zielen

1. Geben Sie auf dem Blatt *Zulässige Ziele (nur überwacht)* die **Geräte-ID** eines AirPlay-Geräts ein, z.B. „52:46:CD:51:83:4C“.
2. Klicken Sie nach dem Eingeben der Geräte-ID auf **Hinzufügen**. Die ID wird in der Liste **Geräte-ID** angezeigt.
3. Fügen Sie nach Bedarf weitere Geräte hinzu. Wenn Sie fertig sind, wählen Sie **OK** aus.

Sie können Geräte, Kennwörter und zulässige Ziele auch aus einer Datei mit durch Trennzeichen getrennten Werten (CSV-Datei) importieren.



