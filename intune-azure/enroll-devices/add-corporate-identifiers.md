---
title: "Hinzufügen von IMEI-Bezeichnern zu Intune | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie in Microsoft Intune Unternehmensbezeichner (IMEI-Nummern) hinzufügen. "
keywords: 
author: staciebarker
ms.author: stabark
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: e134a6e3ff143dacce1d70ef0ab44ade0722ed57

---

# <a name="add-corporate-identifiers"></a>Hinzufügen von Unternehmensbezeichnern

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Sie können eine Liste von IMEI-Nummern (International Mobile Equipment Identity) erstellen, um Ihre Unternehmensgeräte zu identifizieren. Diese Geräte müssen nicht registriert sein, und sie haben entweder den Status „Registriert“ oder „Nicht kontaktiert“. „Nicht kontaktiert“ bedeutet, dass das Gerät noch nie im Intune-Dienst eingecheckt wurde.

Erstellen Sie dazu eine Liste mit zwei Spalten, die durch Trennzeichen getrennt ist (CSV) und keinen Header enthält. Fügen Sie den IMEI-Bezeichner in der linken Spalte und die Details in der rechten Spalte hinzu. Der aktuelle Höchstwert für die Liste ist 500 Zeilen.

In einem Text-Editor sieht die CSV-Liste etwa wie folgt aus:

01 234567 890123,Gerätedetails</br>
02 234567 890123,Gerätedetails

**So fügen Sie eine CSV-Liste von Unternehmensbezeichnern hinzu**

1. Wählen Sie im Azure-Portal **Weitere Dienste** aus, geben Sie **Intune** in das Textfeld ein, und wählen Sie dann **Andere** > **Intune** aus.

2. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Bezeichner von Unternehmensgeräten** aus.

3. Wenn Sie eine Datei mit den neuen Daten importieren, werden die bereits vorhandenen überschrieben. Wählen Sie **Hiermit überschreiben Sie Details für vorhandene Bezeichner** aus, um die vorhandenen Bezeichner durch die neuen zu ersetzen.

4. Navigieren Sie zu der IMEI-CSV-Datei, und wählen Sie **Hinzufügen** aus.

**So löschen Sie eine CSV-Liste mit Unternehmensbezeichnern**

1. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Bezeichner von Unternehmensgeräten** aus.

2. Wählen Sie **Löschen** aus.



<!--HONumber=Feb17_HO1-->


