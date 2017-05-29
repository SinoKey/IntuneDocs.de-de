---
title: "Intune AirPrint-Einstellungen für iOS- und macOS-Geräte"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie Intune verwenden können, um iOS- und macOS-Geräte automatisch mit AirPrint-kompatiblen Druckern zu verbinden."
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 55486693e2f5678ceeb20dd3a0ef3c52553871d2
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---

# <a name="airprint-settings-for-ios-and-macos-devices"></a>AirPrint-Einstellungen für iOS- und macOS-Geräte

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Verwenden Sie diese Einstellungen, um iOS- oder macOS-Geräte für die automatische Verbindung mit AirPrint-kompatiblen Druckern im Netzwerk zu konfigurieren. Sie benötigen die IP-Adresse und den Ressourcenpfad der Drucker, um fortzufahren.

## <a name="find-airprint-printer-information"></a>Ermitteln von AirPrint-Druckerinformationen

Mit diesem Verfahren können Sie AirPrint-Informationen zur AirPrint-Nutzlast hinzufügen, sodass Benutzer von iOS-Geräten auf bekannten AirPrint-Druckern drucken können.

1. Öffnen Sie das Terminal auf einem Mac, der mit dem gleichen lokalen Netzwerk (Subnetz) verbunden ist wie die AirPrint-Drucker (über **/Anwendungen/Hilfsprogramme**).
2. Geben Sie im Terminal die Zeichenfolge **ippfind** ein, und drücken Sie die EINGABETASTE.
3. Notieren Sie sich die vom Befehl zurückgegebenen Druckerinformationen, z.B.: **ipp://myprinter.local.:631/ipp/port1**. Beim ersten Teil der Informationen handelt es sich um den Namen des Druckers, beim letzten Teil um den Ressourcenpfad.
4. Geben Sie im Terminal die Zeichenfolge **ping myprinter.local** ein, und drücken Sie die EINGABETASTE.
5. Notieren Sie sich die vom Befehl zurückgegebenen IP-Adressinformationen, z.B.: **PING myprinter.local (10.50.25.21)**.
6. Verwenden Sie die IP-Adresse und den Ressourcenpfad in den Einstellungen der AirPrint-Nutzlast. Eine IP-Adresse könnte beispielsweise **10.50.25.21** lauten, ein Ressourcenpfad **/ipp/port1**.

## <a name="configure-an-airprint-profile"></a>Konfigurieren eines AirPrint-Profils

1. Wählen Sie auf dem Blatt **Gerätefunktionen** die Option **AirPrint** aus.
2. Um ein AirPrint-Ziel hinzuzufügen, geben Sie auf dem Blatt **AirPrint** die **IP-Adresse** und den **Ressourcenpfad** des Ziels ein, und klicken Sie auf **Hinzufügen**.
3. Fügen Sie so viele Ziele hinzu, wie Sie benötigen. Wenn Sie fertig sind, wählen Sie **OK** aus.

Sie können auch eine Liste mit Druckern aus einer Datei mit durch Trennzeichen getrennten Werten (CSV-Datei) importieren oder die Liste exportieren.

