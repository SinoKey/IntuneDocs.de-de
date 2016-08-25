---
title: "Geräteverwaltung mit Exchange ActiveSync | Microsoft Intune"
description: "Verwalten mobiler Geräte mit der Exchange ActiveSync (EAS)-Verwaltung und dem Exchange Connector"
keywords: 
author: nathbarn
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: de3296e81c88b3ac04e3ba3f3d3ca222a59df7bd
ms.openlocfilehash: 96d8911dafe7897458297867ddfef97206fdfc9c


---

# Verwaltung mobiler Geräte mit Exchange ActiveSync und Microsoft Intune
Damit mobile Geräte direkt mit Microsoft Intune verwaltet werden können, müssen sie [bei Intune registriert](get-ready-to-enroll-devices-in-microsoft-intune.md) sein. Alternativ können Administratoren eine eingeschränktere Verwaltungslösung ermöglichen, bei der die Exchange ActiveSync (EAS)-Verwaltung mit einem Exchange Connector eingesetzt wird. Geräte können mit lokalen Exchange-Servern und mit Exchange Online unter Verwendung von Office 365 verwaltet werden. Intune unterstützt pro Abonnement nur eine Exchange Connector-Verbindung eines beliebigen Typs.

## Exchange-Zugriffsregeln für mobile Geräte ##

In Exchange muss über einen Satz von Regeln definiert werden, was geschieht, wenn mobile Geräte eine Verbindung mit EAS herzustellen versuchen. Diese Regeln werden in der Intune-Verwaltungskonsole verwaltet.

[Exchange-Zugriffsregeln für mobile Geräte](exchange-access-rules-for-mobile-devices.md)

## Installieren des Exchange Connectors
Mit dem Exchange Connector können Sie Ihre Exchange-Bereitstellung in der Intune-Konsole verwalten. Zuerst müssen Sie den entsprechenden Intune-zu-Exchange-Connector installieren und konfigurieren. Wählen Sie die entsprechende Option je nachdem, ob es sich um einen lokalen Exchange-Server handelt oder ob er als Dienst in der Cloud gehostet wird:

-   [Konfigurieren von Intune für die Exchange Online-Umgebung oder für die neue Exchange Online Dedicated-Umgebung](intune-service-to-service-exchange-connector.md)
-   [Installieren des Intune-Connectors für lokale Exchange-Server und ältere Exchange Online Dedicated-Umgebungen](intune-on-premises-exchange-connector.md)


## Anwenden der Richtlinie für mobile Geräte, die mit Exchange verwaltet werden
Die Intune-Konsole kann zum Verwalten von [EAS-Richtlinieneinstellungen](exchange-activesync-policy-settings-in-microsoft-intune.md) und zum [Beschränken des Zugriffs auf Unternehmensressourcen](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) verwendet werden. Eine Liste der Exchange ActiveSync-Richtlinieneinstellungen und -Funktionen, die von bestimmten mobilen Geräten unterstützt werden, finden Sie unter [Exchange ActiveSync Client Comparison Table](http://go.microsoft.com/fwlink/?LinkId=247270) (Vergleichstabelle der Exchange ActiveSync-Clients).

> [!NOTE]
> Nach dem Herstellen einer Verbindung zwischen Intune und einer Microsoft Exchange-Umgebung wird bei allen Benutzern, die über Intune verwaltet werden, die EAS-Richtlinie auf die aktuelle Standardrichtlinie auf dem Microsoft Exchange-Server zurückgesetzt, wenn keine spezifische Richtlinie in Intune definiert ist.

## Löschen von Unternehmensdaten von mobilen Geräten
Sie können [Unternehmensdaten von mobilen Geräten, die über EAS verwaltet werden, löschen](wipe-for-exchange-managed-mobile-devices.md), wenn diese nicht mehr verwendet werden oder wenn Geräte verloren gehen oder gestohlen werden.



<!--HONumber=Jul16_HO5-->


