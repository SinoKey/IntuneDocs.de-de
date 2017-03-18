---
title: "Hinzufügen von IMEI-IDs zu Intune"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie in Microsoft Intune Unternehmensbezeichner (IMEI-Nummern) hinzufügen. "
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: d8cb15d1b8c1c100f15084e43d2c3c4633fd64b5
ms.openlocfilehash: f12d538b1f4cd327b893d234f2b558185cdd9d85
ms.lasthandoff: 03/09/2017

---

# <a name="add-corporate-identifiers"></a>Hinzufügen von Unternehmensbezeichnern

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Sie können eine Liste von IMEI-Nummern (International Mobile Equipment Identity) erstellen, um Ihre Unternehmensgeräte zu identifizieren. Diese Geräte müssen nicht registriert sein, und sie haben entweder den Status „Registriert“ oder „Nicht kontaktiert“. „Nicht kontaktiert“ bedeutet, dass das Gerät noch nie im Intune-Dienst eingecheckt wurde.

Erstellen Sie dazu eine Liste mit zwei Spalten, die durch Trennzeichen getrennt ist (CSV) und keinen Header enthält. Fügen Sie den IMEI-Bezeichner in der linken Spalte und die Details in der rechten Spalte hinzu. Der aktuelle Höchstwert für die Liste ist 500 Zeilen.

In einem Text-Editor sieht die CSV-Liste etwa wie folgt aus:

01 234567 890123,Gerätedetails</br>
02 234567 890123,Gerätedetails

**So fügen Sie eine CSV-Liste von Unternehmensbezeichnern hinzu**

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

2. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Bezeichner von Unternehmensgeräten** aus.

3. Wenn Sie eine Datei mit den neuen Daten importieren, werden die bereits vorhandenen überschrieben. Wählen Sie **Hiermit überschreiben Sie Details für vorhandene Bezeichner** aus, um die vorhandenen Bezeichner durch die neuen zu ersetzen.

4. Navigieren Sie zu der IMEI-CSV-Datei, und wählen Sie **Hinzufügen** aus.

> [!IMPORTANT]
> Einige Android-Geräte verfügen über mehrere IMEI-Nummern. Intune inventarisiert eine IMEI-Nummer pro Gerät. Wenn Sie eine IMEI-Nummer importieren, es sich aber nicht um die IMEI-Nummer handelt, die von Intune inventarisiert wurde, wird das Gerät als ein persönliches Gerät und nicht als ein unternehmenseigenes Gerät eingestuft. Wenn Sie mehrere IMEI-Nummern für ein Gerät importieren, werden nicht inventarisierte Nummern als Anmeldungsstatus **Unbekannt** anzeigen.

**So löschen Sie eine CSV-Liste mit Unternehmensbezeichnern**

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

2. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Bezeichner von Unternehmensgeräten** aus.

3. Wählen Sie **Löschen** aus.

