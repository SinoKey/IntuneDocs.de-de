---
title: Intune-Integration mit Microsoft-Cloud-Diensten und Produkten
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: 
ms.assetid: 
author: Staciebarker
---
# Intune-Integration mit Microsoft-Cloud-Diensten und Produkten

Vor der Einrichtung [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)], lesen Sie dieses Thema und andere Anforderungen aufgeführt, [Wissenswertes vor dem Starten von Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md).
##Integration mit anderen Microsoft-Clouddiensten


[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] basiert auf der gleichen Grundlage wie andere Clouddienste von Microsoft. Wenn Sie mehrere Clouddienste über dasselbe Konto abonnieren, wird dieselbe Microsoft Azure AD-Infrastruktur von diesen Diensten verwendet, und sie alle sind Mandanten von Azure AD. Von Azure AD werden die zentralen Funktionen für Verzeichnis- und Identitätsverwaltung der Microsoft-Clouddienste bereitgestellt.

Erfahren Sie mehr über [Verwalten von Azure AD ](http://technet.microsoft.com/library/hh967611.aspx) in der TechNet-Bibliothek.

## Integration mit anderen Microsoft-Produkten
Sie können [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] als eigenständigen oder mit anderen Produkten integrierten Clouddienst verwenden. Gegenwärtig kann nur [!INCLUDE[cmshort](../includes/cmshort_md.md)] direkt mit [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] integriert werden.

Die Entscheidung zur Integration von [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] mit [!INCLUDE[cmshort](../includes/cmshort_md.md)] ist endgültig und erfordert die Festlegung der Autorität für die Verwaltung mobiler Geräte über die [!INCLUDE[cmshort](../includes/cmshort_md.md)]-Konsole statt über die [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)]. Nachdem die Autorität für die Verwaltung mobiler Geräte festgelegt wurde, können Sie diese Konfiguration nicht mehr ändern.

Bei Verwendung [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] mit [!INCLUDE[cmshort](../includes/cmshort_md.md)], verwenden Sie die [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] verwalten [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] und verwenden Sie stattdessen die [!INCLUDE[cmshort](../includes/cmshort_md.md)] Konsole. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] verwendet weiterhin den cloudspeicher in Azure zum Hosten von Software, die Sie für Geräte, die Sie bereitstellen mit verwalten [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

Weitere Informationen finden Sie unter [Verwalten von mobilen Geräten mit Configuration Manager und Microsoft Intune](http://msdn.microsoft.com/library/2c6bd0e5-d436-41c8-bf38-30152d76be10) in der [!INCLUDE[cm5short](../includes/cm5short_md.md)] SP1-Dokumentation.

### Weitere Informationen:
[Wissenswertes vor dem Starten von Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)

<!--HONumber=Mar16_HO4-->


