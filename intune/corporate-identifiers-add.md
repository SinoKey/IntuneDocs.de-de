---
title: "Hinzufügen von IMEI-IDs zu Intune"
titleSuffix: Intune on Azure
description: "Erfahren Sie, wie Sie in Microsoft Intune Unternehmensbezeichner (IMEI-Nummern) hinzufügen. \""
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6b38bf2da70537d07a050fa21be9a2a3062ca84b
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2017
---
# <a name="add-corporate-identifiers"></a>Hinzufügen von Unternehmensbezeichnern

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Als Intune-Administrator können Sie eine durch Trennzeichen getrennte Datei (CSV-Datei) erstellen und importieren, die IMEI-Nummern (International Mobile Equipment Identity) oder Seriennummern auflistet. Intune verwendet diese Bezeichner, um den Gerätebesitz als unternehmenseigen anzugeben. Sie können die IMEI-Nummern für alle unterstützten Plattformen deklarieren. Sie können die Seriennummer nur für iOS- und Android-Geräte deklarieren. Jede IMEI-Nummer oder Seriennummer kann Details enthalten, die in der Liste zu administrativen Zwecken angegeben sind.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

[Erfahren Sie, wie Sie die Seriennummer eines Apple-Geräts finden](https://support.apple.com/HT204308).<br>
[Erfahren Sie, wie Sie die Seriennummer Ihres Android-Geräts finden](https://support.google.com/store/answer/3333000).

## <a name="add-corporate-identifiers"></a>Hinzufügen von Unternehmensbezeichnern
Erstellen Sie dazu eine Liste mit zwei Spalten, die durch Trennzeichen getrennt ist (CSV) und keinen Header enthält. Fügen Sie die IMEI- oder Seriennummer in der linken Spalte und die Details in der rechten Spalte hinzu. Nur ein Typ von ID, IMEI- oder Seriennummer kann in eine CSV-Datei importiert werden. Details sind auf 128 Zeichen beschränkt und nur für administrative Zwecke bestimmt. Details werden nicht auf dem Gerät angezeigt. Die aktuelle Begrenzung beträgt 500 Zeilen pro CSV-Datei.

**Eine CSV-Datei mit Seriennummern hochladen**: Erstellen Sie eine durch Trennzeichen getrennte Liste (.csv) mit zwei Spalten ohne Header, und beschränken Sie die Liste auf 5.000 Geräte oder 5 MB pro CSV-Datei.

|||
|-|-|
|&lt;ID #1&gt;|&lt;Details zu Gerät 1&gt;|
|&lt;ID #2&gt;|&lt;Details zu Gerät 2&gt;|

Diese CSV-Datei wird bei der Anzeige in einem Text-Editor folgendermaßen angezeigt:

```
01234567890123,device details
02234567890123,device details
```

> [!IMPORTANT]
> Einige Android-Geräte verfügen über mehrere IMEI-Nummern. Intune liest nur eine IMEI-Nummer pro registriertem Gerät. Wenn Sie eine IMEI-Nummer importieren, es sich aber nicht um die IMEI-Nummer handelt, die von Intune inventarisiert wurde, wird das Gerät als ein persönliches Gerät und nicht als ein unternehmenseigenes Gerät eingestuft. Wenn Sie mehrere IMEI-Nummern für ein Gerät importieren, werden nicht inventarisierte Nummern als Anmeldungsstatus **Unbekannt** anzeigen.<br>
>Beachten Sie auch: Android-Seriennummern sind garantiert eindeutig oder vorhanden. Wenden Sie sich an Ihren Gerätehersteller, um herauszufinden, ob die Seriennummer eine zuverlässige Geräte-ID ist.
>Seriennummern, die vom Gerät an Intune übermittelt werden, stimmen möglicherweise nicht mit der angezeigten ID in den Menüs „Einstellungen für Android/Info“ auf dem Gerät überein. Überprüfen Sie den Typ der Seriennummer, die vom Gerätehersteller übermittelt wurde.


**So fügen Sie eine CSV-Liste von Unternehmensbezeichnern hinzu**

1. Wählen Sie im Intune-Portal die Optionen **Geräteregistrierung** > **Registrierungsbeschränkungen**, wählen Sie **Bezeichner von Unternehmensgeräten**, und klicken Sie dann auf **Hinzufügen**.

 ![Screenshot des Arbeitsbereichs des Bezeichners von Unternehmensgeräten mit hervorgehobener Schaltfläche „Hinzufügen“](./media/add-corp-id.png)

2. Geben Sie auf dem Blatt **Bezeichner hinzufügen** den Bezeichnertyp an, **IMEI** oder **Seriennummer**. Sie können angeben, ob für zuvor importierte Zahlen Folgendes gilt: **Hiermit überschreiben Sie Details für vorhandene Bezeichner**.

3. Klicken Sie auf das Ordnersymbol, und geben Sie den Pfad zu der Liste an, die Sie importieren möchten. Navigieren Sie zu der CSV-Datei, und wählen Sie **Hinzufügen** aus. Sie können auf **Aktualisieren** klicken, um neue Gerätebezeichner anzuzeigen.

Importierte Geräte sind nicht zwangsläufig registriert. Geräte können entweder **Registriert** oder **Nicht kontaktiert** sein. **Nicht kontaktiert** bedeutet, dass das Gerät noch nie mit dem Intune-Dienst kommuniziert hat.

## <a name="delete-corporate-identifiers"></a>Löschen von Unternehmensbezeichnern

1. Wählen Sie im Intune- Portal die Optionen **Geräteregistrierung** > **Registrierungsbeschränkungen**, wählen Sie **Bezeichner von Unternehmensgeräten**, und klicken Sie dann auf **Löschen**.

3. Wechseln Sie auf dem Blatt **Bezeichner löschen** zu der CSV-Datei der zu löschenden Geräte-IDs, und klicken Sie dann auf **Löschen**.

## <a name="imei-specifications"></a>IMEI-Spezifikationen
Detaillierte Angaben über International Mobile Equipment Identifier finden Sie unter [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).
