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
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: e0a853c34c6d38e8fae6f4712ba6c2b767e5d0ba
ms.lasthandoff: 03/22/2017

---

# <a name="add-corporate-identifiers"></a>Hinzufügen von Unternehmensbezeichnern

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Als IT-Administrator können Sie eine durch Trennzeichen getrennte Datei (CSV-Datei) erstellen und importieren, die IMEI-Nummern (International Mobile Equipment Identity) zum Identifizieren von firmeneigenen Geräten auflistet. Jede IMEI-Nummer kann Details enthalten, die in der Liste zu administrativen Zwecken angegeben sind.

## <a name="create-a-csv-file"></a>Erstellen einer CSV-Datei
Erstellen Sie dazu eine Liste mit zwei Spalten, die durch Trennzeichen getrennt ist (CSV) und keinen Header enthält. Fügen Sie den IMEI-Bezeichner in der linken Spalte und die Details in der rechten Spalte hinzu. Details sind auf 128 Zeichen beschränkt. Die aktuelle Begrenzung beträgt 500 Zeilen pro CSV-Datei.

**Eine CSV-Datei mit Seriennummern hochladen**: Erstellen Sie eine durch Trennzeichen getrennte Liste (.csv) mit zwei Spalten ohne Header, und beschränken Sie die Liste auf 5.000 Geräte oder 5 MB pro CSV-Datei.

|||
|-|-|
|&lt;IMEI 1&gt;|&lt;Details zu Gerät 1&gt;|
|&lt;IMEI 2&gt;|&lt;Details zu Gerät 2&gt;|

    This .csv file when viewed in a text editor appears as:

    ```
    01 234567 890123,device details
    02 234567 890123,device details
    ```

**So fügen Sie eine CSV-Liste von Unternehmensbezeichnern hinzu**

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

2. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Bezeichner von Unternehmensgeräten** aus.

3. Wenn Sie eine Datei mit den neuen Daten importieren, werden die bereits vorhandenen überschrieben. Wählen Sie **Hiermit überschreiben Sie Details für vorhandene Bezeichner** aus, um die vorhandenen Bezeichner durch die neuen zu ersetzen.

4. Navigieren Sie zu der IMEI-CSV-Datei, und wählen Sie **Hinzufügen** aus.

> [!IMPORTANT]
> Einige Android-Geräte verfügen über mehrere IMEI-Nummern. Intune inventarisiert eine IMEI-Nummer pro Gerät. Wenn Sie eine IMEI-Nummer importieren, es sich aber nicht um die IMEI-Nummer handelt, die von Intune inventarisiert wurde, wird das Gerät als ein persönliches Gerät und nicht als ein unternehmenseigenes Gerät eingestuft. Wenn Sie mehrere IMEI-Nummern für ein Gerät importieren, werden nicht inventarisierte Nummern als Anmeldungsstatus **Unbekannt** anzeigen.

Nach dem Importieren können diese Geräte registriert oder nicht registriert sein, und ihr Status ist entweder **Registriert** oder **Nicht kontaktiert**. **Nicht kontaktiert** bedeutet, dass das Gerät noch nie mit dem Intune-Dienst kommuniziert hat.

## <a name="delete-a-csv-list"></a>Löschen einer CSV-Liste

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

2. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Bezeichner von Unternehmensgeräten** aus.

3. Wählen Sie **Löschen** aus.

Detaillierte Angaben über International Mobile Equipment Identifier finden Sie unter [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).

