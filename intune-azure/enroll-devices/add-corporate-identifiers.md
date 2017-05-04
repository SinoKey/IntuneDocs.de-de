---
title: "Hinzufügen von IMEI-IDs zu Intune"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie in Microsoft Intune Unternehmensbezeichner (IMEI-Nummern) hinzufügen. "
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 15415f9f31d520d66257df3a7e134e4b1de8467c
ms.openlocfilehash: 8c9e6b39ee01697d993e5738ec35e8a64fc8e236
ms.lasthandoff: 04/07/2017

---

# <a name="add-corporate-identifiers"></a>Hinzufügen von Unternehmensbezeichnern

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Als IT-Administrator können Sie eine durch Trennzeichen getrennte Datei (CSV-Datei) erstellen und importieren, die IMEI-Nummern (International Mobile Equipment Identity) zum Identifizieren von firmeneigenen Geräten auflistet. Jede IMEI-Nummer kann Details enthalten, die in der Liste zu administrativen Zwecken angegeben sind.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

## <a name="add-corporate-identifiers"></a>Hinzufügen von Unternehmensbezeichnern
Erstellen Sie dazu eine Liste mit zwei Spalten, die durch Trennzeichen getrennt ist (CSV) und keinen Header enthält. Fügen Sie den IMEI-Bezeichner in der linken Spalte und die Details in der rechten Spalte hinzu. Details sind auf 128 Zeichen beschränkt und nur für administrative Zwecke bestimmt. Details werden nicht auf dem Gerät angezeigt. Die aktuelle Begrenzung beträgt 500 Zeilen pro CSV-Datei.

**Eine CSV-Datei mit Seriennummern hochladen**: Erstellen Sie eine durch Trennzeichen getrennte Liste (.csv) mit zwei Spalten ohne Header, und beschränken Sie die Liste auf 5.000 Geräte oder 5 MB pro CSV-Datei. 

|||
|-|-|
|&lt;IMEI 1&gt;|&lt;Details zu Gerät 1&gt;|
|&lt;IMEI 2&gt;|&lt;Details zu Gerät 2&gt;|

Diese CSV-Datei wird bei der Anzeige in einem Text-Editor folgendermaßen angezeigt:

```
01234567890123,device details
02234567890123,device details
```


> [!IMPORTANT]
> Einige Android-Geräte verfügen über mehrere IMEI-Nummern. Intune inventarisiert eine IMEI-Nummer pro Gerät. Wenn Sie eine IMEI-Nummer importieren, es sich aber nicht um die IMEI-Nummer handelt, die von Intune inventarisiert wurde, wird das Gerät als ein persönliches Gerät und nicht als ein unternehmenseigenes Gerät eingestuft. Wenn Sie mehrere IMEI-Nummern für ein Gerät importieren, werden nicht inventarisierte Nummern als Anmeldungsstatus **Unbekannt** anzeigen.

**So fügen Sie eine CSV-Liste von Unternehmensbezeichnern hinzu**

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

2. Wählen Sie auf dem Blatt „Intune“ **Geräteregistrierung**  >  **Registrierungsbeschränkungen**, wählen Sie **Bezeichner von Unternehmensgeräten**, und klicken Sie dann auf **Hinzufügen**.

3. Geben Sie auf dem Blatt **Bezeichner hinzufügen** den Bezeichner **IMEI** ein. Sie können angeben, ob für zuvor importierte Zahlen Folgendes gilt: **Hiermit überschreiben Sie Details für vorhandene Bezeichner.**.  

4. Klicken Sie auf das Ordnersymbol, und geben Sie den Pfad zu der Liste an, die Sie importieren möchten. Navigieren Sie zu der IMEI-CSV-Datei, und wählen Sie **Hinzufügen** aus.

Nach dem Importieren können diese Geräte registriert oder nicht registriert sein, und ihr Status ist entweder **Registriert** oder **Nicht kontaktiert**. **Nicht kontaktiert** bedeutet, dass das Gerät noch nie mit dem Intune-Dienst kommuniziert hat.

## <a name="delete--corporate-identifiers"></a>Löschen von Unternehmensbezeichnern

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

2. Wählen Sie auf dem Blatt „Intune“ **Geräteregistrierung**  >  **Registrierungsbeschränkungen**, und wählen Sie dann **Bezeichner von Unternehmensgeräten** und **Löschen**.

3. Wechseln Sie auf dem Blatt **Bezeichner löschen** zu der CSV-Datei der zu löschenden Geräte-IDs, und klicken Sie dann auf **Löschen**.

## <a name="imei-specifications"></a>IMEI-Spezifikationen
Detaillierte Angaben über International Mobile Equipment Identifier finden Sie unter [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).

