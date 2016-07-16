---
title: "Verwaltung mobiler Geräte mit Exchange ActiveSync und Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: nathbarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: d24395786daa7aec103ec754895868a75983e099


---

# Verwaltung mobiler Geräte mit Exchange ActiveSync und Microsoft Intune
Damit die mobilen Geräte direkt mit Microsoft Intune verwaltet werden, müssen die Benutzer die Geräte bei Intune registrieren. Bei mobilen Geräten, die nicht von Benutzern registriert wurden, können Sie die Verwaltung mit Exchange ActiveSync (EAS) unter Verwendung des Exchange Connectors aktivieren. Geräte können entweder auf lokalen Exchange-Servern oder über in der Cloud gehostetes Exchange in Microsoft Office 365 verwaltet werden.

## Exchange-Zugriffsregeln für mobile Geräte ##

In Exchange muss über einen Satz von Regeln definiert werden, was geschieht, wenn mobile Geräte eine Verbindung mit EAS herzustellen versuchen. Diese Regeln werden in der Intune-Verwaltungskonsole verwaltet.

[Exchange-Zugriffsregeln für mobile Geräte](exchange-access-rules-for-mobile-devices.md)

## Installieren des Exchange Connectors
Mit dem Exchange Connector können Sie Ihre Exchange-Bereitstellung in der Intune-Konsole verwalten. Zuerst müssen Sie den entsprechenden Intune-zu-Exchange-Connector installieren und konfigurieren. Wählen Sie die entsprechende Option je nachdem, ob es sich um einen lokalen Exchange-Server handelt oder ob er als Dienst in der Cloud gehostet wird:

-   [Installieren des Intune-Connectors für lokales Exchange](intune-on-premises-exchange-connector.md)
-   [Konfigurieren des Intune Service to Service Connectors für gehostetes Exchange](intune-service-to-service-exchange-connector.md)

## Anwenden der Richtlinie für mobile Geräte, die mit Exchange verwaltet werden
Richtlinieneinstellungen können über die Intune-Konsole angewendet werden. Weitere Informationen finden Sie unter [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md). Eine Liste der Exchange ActiveSync-Richtlinieneinstellungen und -Funktionen, die von bestimmten mobilen Geräten unterstützt werden, finden Sie unter [Exchange ActiveSync Client Comparison Table](http://go.microsoft.com/fwlink/?LinkId=247270) (Vergleichstabelle der Exchange ActiveSync-Clients).

> [!NOTE]
> Nach dem Herstellen einer Verbindung zwischen Intune und einer Microsoft Exchange-Umgebung wird bei allen Benutzern, die über Intune verwaltet werden, die EAS-Richtlinie auf die aktuelle Standardrichtlinie auf dem Microsoft Exchange-Server zurückgesetzt, wenn keine spezifische Richtlinie in Intune definiert ist.

## Löschen von Unternehmensdaten von mobilen Geräten
Sie können [Unternehmensdaten von mobilen Geräten, die über EAS verwaltet werden, löschen](wipe-for-exchange-managed-mobile-devices.md), wenn diese nicht mehr verwendet werden oder wenn Geräte verloren gehen oder gestohlen werden.



<!--HONumber=Jun16_HO4-->


