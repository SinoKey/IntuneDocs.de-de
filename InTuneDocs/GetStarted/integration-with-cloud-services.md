---
title: Intune-Integration mit Microsoft-Clouddiensten | Microsoft Intune
description: Intune-Integration mit Microsoft-Clouddiensten und -Produkten sowie mit anderen Microsoft-Produkten
keywords: 
author: Staciebarker
manager: arob98
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 49675811-08a3-408f-810b-89552ff404bd
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: e20293f431e0a9ff385f82276d25e71d460230de


---

# Intune-Integration in Microsoft Cloud Services und Microsoft-Produkte

Bevor Sie [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] einrichten, lesen Sie dieses Thema und andere Anforderungen, die unter [ Was Sie wissen sollten, bevor Sie Microsoft Intune starten](what-to-know-before-you-start-microsoft-intune.md) aufgeführt sind.
##Integration mit anderen Microsoft-Clouddiensten


[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] basiert auf der gleichen Grundlage wie andere Clouddienste von Microsoft. Wenn Sie mehrere Clouddienste über dasselbe Konto abonnieren, wird dieselbe Microsoft Azure AD-Infrastruktur von diesen Diensten verwendet, und sie alle sind Mandanten von Azure AD. Von Azure AD werden die zentralen Funktionen für Verzeichnis- und Identitätsverwaltung der Microsoft-Clouddienste bereitgestellt.

Erfahren Sie mehr über die [Verwaltung von Azure AD](http://technet.microsoft.com/library/hh967611.aspx) in der TechNet-Bibliothek.

## Integration mit anderen Microsoft-Produkten
Sie können [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] als eigenständigen oder mit anderen Produkten integrierten Clouddienst verwenden. Gegenwärtig kann nur [!INCLUDE[cmshort](../includes/cmshort_md.md)] direkt mit [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] integriert werden.

Die Entscheidung zur Integration von [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] mit [!INCLUDE[cmshort](../includes/cmshort_md.md)] ist endgültig und erfordert die Festlegung der Autorität für die Verwaltung mobiler Geräte über die [!INCLUDE[cmshort](../includes/cmshort_md.md)]-Konsole statt über die [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)]. Nachdem die Autorität für die Verwaltung mobiler Geräte festgelegt wurde, können Sie diese Konfiguration nicht mehr ändern.

Bei Verwendung von [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] mit [!INCLUDE[cmshort](../includes/cmshort_md.md)] verwenden Sie nicht die [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)], um [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] zu verwalten, sondern die [!INCLUDE[cmshort](../includes/cmshort_md.md)]-Konsole. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Intune verwendet weiterhin den Cloudspeicher in Azure zum Hosten von Software, die Sie für Geräte bereitstellen, die Sie mit [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] verwalten.

Weitere Informationen finden Sie unter [Verwalten von mobilen Geräten mit Configuration Manager und Microsoft Intune](http://msdn.microsoft.com/library/2c6bd0e5-d436-41c8-bf38-30152d76be10) in der Dokumentation zu [!INCLUDE[cm5short](../includes/cm5short_md.md)] SP1.

### Weitere Informationen:
[Was Sie wissen sollten, bevor Sie Microsoft Intune starten](what-to-know-before-you-start-microsoft-intune.md)


<!--HONumber=Jul16_HO3-->


