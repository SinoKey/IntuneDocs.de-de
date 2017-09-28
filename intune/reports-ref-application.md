---
title: Anwendung | Microsoft-Dokumentation
description: "Referenzthema für die Kategorie „Anwendung“ der Entitätsauflistungen in der Intune Data Warehouse-API"
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A92DEF30-5D01-4774-9917-E26F5F0E2E68
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cd684feec1df6b20f9349052496a21895527710b
ms.sourcegitcommit: 0d9bfd92bf5958261ed83b1f150bf207b7ba7e56
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2017
---
# <a name="reference-for-application-entities"></a>Verweis für Anwendungsentitäten

Die Kategorie **Anwendung** (Application) enthält Entitäten für mobile Geräte, die folgende Informationen nachverfolgen:

  -  Version einer App
  -  Installationsquelle einer App
  -  Typ der Entwickler, die eine App entwickelt haben
  -  Typen verwalteter Software für eine App, z.B. **sidecar** oder **desktop**
  -  Volume Purchasing Program (VPP) – Status einer App

## <a name="apprevision"></a>AppRevision

Die Entität **AppRevision** führt alle Versionen einer App auf.

| Eigenschaft  | Beschreibung | Beispiel |
|---------|------------|--------|
| AppKey |Eindeutiger Bezeichner der App |123 |
| ApplicationId |Eindeutiger Bezeichner einer App. Ähnlich wie AppKey, dieser Schlüssel ist jedoch ein natürlicher Schlüssel. |b66bc706-ffff-7437-0340-032819502773 |
| Revision |Die Version, die vom Administrator während des Uploads der Binärdatei erwähnt wurde |2 |
| Titel |Titel der App |Excel |
| Herausgeber |Herausgeber der App |Microsoft |
| UploadState |Hochladestatus der App |1 |
| AppTypeKey |Der Verweis zu AppType wird im folgenden Abschnitt beschrieben. | |
| VppProgramTypeKey |Der Verweis zu VppProgramType ist weiter unten beschrieben. | |
| CreationTime |Die Uhrzeit, als diese Revision erstellt wurde |23.11.2016 12:00:00 |
| ModifiedTime |Das letzte Mal, als etwas mit dieser Revision verknüpftes geändert wurde |23.11.2016 12:00:00 |
| Size |Größe der Binärdatei | |
| StartDateInclusiveUTC |Datum und Uhrzeit in UTC, als diese App-Revision im Data Warehouse erstellt wurde. |23.11.2016 12:00:00 |
| EndDateExclusiveUTC |Datum und Uhrzeit in UTC, als diese App-Revision veraltet wurde |23.11.2016 12:00:00 |
| IsCurrent |Gibt an, ob diese App-Version aktuell oder nicht im Data Warehouse vorhanden ist |Wahr/falsch |
| RowLastModifiedDateTimeUTC |Datum und Uhrzeit in UTC, als diese App-Version zuletzt im Data Warehouse geändert wurde. |23.11.2016 12:00:00 Uhr |

## <a name="apptypes"></a>AppTypes

Die Entität **AppTypes** führt die Installationsquelle einer App auf.

| Eigenschaft  | Beschreibung |
|---------|------------|
| AppTypeID |ID für den Typ |
| AppTypeKey |Untergeordneter Schlüssel für den Schlüssel |
| AppTypeName |App-Typ |

## <a name="example"></a>Beispiel

| AppTypeID  | Name | Beschreibung |
|---------|------------|--------|
| 0 |Android Store-App |Eine Android Store-App |
| 1 |Android-Branchen-App |Eine branchenspezifische Android-App |
| 2 |Verwaltete Android Store-App (MAM) |Eine Android Store-App, die für die Verwaltung aktiviert ist |
| 3 |iOS Store-App |Eine iOS Store-App |
| 4 |Branchenspezifische iOS-App |Eine branchenspezifische iOS-App |
| 5 |Verwaltete iOS Store-App (MAM?) |Eine iOS Store-App, die für die Verwaltung aktiviert ist |
| 6 |O365 Pro Plus Suite |Die Office 365 Pro Plus Suite für Windows 10 |
| 7 |Web-App |Eine Web-App |
| 8 |Windows Phone 8.1 Store-App |Eine Windows Phone 8.1 Store-App |
| 9 |Windows Store-App |Eine Windows Store-App |
| 10 |Branchenspezifische Windows-Apps |Eine branchenspezifische Windows-App |
| 11 |Windows Mobile MSI |Eine branchenspezifische MSI-App |
| 12 |Branchenspezifische Windows Phone-App |Eine Branchenspezifische Windows Phone-App |


## <a name="vppprogramtypes"></a>VppProgramTypes

Die Entität **VppProgramTypes** führt mögliche VPP-Programmtypen für eine App auf.

| Eigenschaft  | Beschreibung |
|---------|------------|
| VppProgramTypeID |ID für den Typ |
| VppProgramTypeKey |Untergeordneter Schlüssel für den Schlüssel |
| VppProgramTypeName |VPP-Programmtyp |

## <a name="example"></a>Beispiel

| VppProgramID  | Name | Beschreibung |
|---------|------------|--------|
| 3DDA2474-470B-4503-9830-2665C21C1945 |Microsoft |VPP-Programm von Microsoft |
| 00000000-0000-0000-0000-000000000000 |Noch nicht verfügbar. |Standardwert; Kein VPP |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B |Apple |VPP-Programm von Apple |



## <a name="applicationinventory"></a>ApplicationInventory

Die Entität **ApplicationInventory** listet die Anwendungen auf, die zum Zeitpunkt der Inventursammlung auf dem Gerät gefunden wurden.

| Eigenschaft  | Beschreibung |
|---------|------------|
| DeviceKey |Dies ist ein Verweis auf die Gerätetabelle, die die Intune-Geräte-ID enthält |
| DateKey |Verweis auf die Datumstabelle, die den Tag der Inventur angibt |
| ApplicationName |Anwendungsname |
| ApplicationVersion |Version der Anwendung |
| BundleSize |Größe der App in Byte |
