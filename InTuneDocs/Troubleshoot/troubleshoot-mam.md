---
title:
- "Problembehandlung der Verwaltung von mobilen Geräten | Microsoft Intune"
description: 
keywords: 
author: karaman
manager: angerobe
ms.date: 09/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
translationtype: Human Translation
ms.sourcegitcommit: 9cfb3694b2fae919fd0554a6e21b497cdcf19c72
ms.openlocfilehash: f33e8de82ee07bb4571a5bfaff63af72f9086376


---

# Problembehandlung der Verwaltung von mobilen Geräten

Wenn bei Ihrer Verwaltung von mobilen Geräten Probleme auftreten, beginnen Sie hier. In diesem Thema werden einige allgemeine Probleme, die auftreten können, sowie deren Lösungen behandelt.


**Problem:** MAM ohne Registrierungsrichtlinie von der Azure-Konsole erstreckt sich nicht auf die Skype for Business-App auf iOS- und Android-Geräten.

Lösung: Skype for Business muss für moderne Authentifizierung eingerichtet werden.  Führen Sie die Anweisungen in [Enable your tenant for modern authentication (Aktivieren Ihres Mandanten für moderne Authentifizierung)](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) aus, um moderne Authentifizierung für Skype einzurichten.

**Problem:** MAM ohne Registrierungsrichtlinien erstreckt sich auf keine (unterstützte Office-App)[https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners] für keinen Benutzer.
 
Lösung: Überprüfen Sie, ob der Benutzer für Intune lizenziert ist.  

**Problem:** Der IT-Administratorbenutzer kann keine MAM-Richtlinien im Azure-Portal konfigurieren

Lösung: Folgende Rollen haben Zugriff auf das Azure-Portal:

- Globaler Administrator, den Sie im [Office-Portal](http://portal.office.com/) einrichten können.
- Besitzer, den Sie im [Azure-Portal](https://portal.azure.com/) einrichten können.
- Mitwirkender, den Sie im [Azure-Portal](https://portal.azure.com/) einrichten können.

Hilfe zum Einrichten dieser Rollen finden Sie unter [Vorbereiten der Konfiguration von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). 

**Problem:** Im App-Bericht werden Benutzer, die wir kürzlich als Ziel der MAM-Richtlinie festgelegt haben, nicht aufgeführt.

Lösung: Wenn ein Benutzer neu als Ziel einer MAM-Richtlinie festgelegt worden ist, kann es bis zu 24 Stunden dauern, bis dieser Benutzer in Berichten als festgelegter Benutzer aufgeführt wird. 

**Problem:** Änderungen/Aktualisierungen von Richtlinien werden u. U. erst nach 8 Stunden wirksam.  

Lösung: Endbenutzer können sich bei der App abmelden und wieder anmelden, um die Synchronisierung mit dem Dienst zu erzwingen.  

**Problem:** Die MAM-Richtlinie wird nicht auf Apple DEP-Geräte angewendet

Lösung: Achten Sie darauf, User Affinity mit Apple DEP (Device Enrollment Program) zu verwenden. User Affinity ist für alle Apps erforderlich, die Benutzerauthentifizierung unter DEP benötigen.
Weitere Informationen zur iOS-DEP-Registrierung finden Sie unter [Registrieren unternehmenseigener iOS-Geräte mithilfe des Programm zur Geräteregistrierung (Device Enrollment Program, DEP)](https://docs.microsoft.com/en-us/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune).


### Weitere Informationen:
- [Überprüfen des Setups für die Verwaltung Ihrer mobilen Anwendungen](https://docs.microsoft.com/en-us/intune/deploy-use/validate-mobile-application-management)
- [Vorbereiten der Konfiguration von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) 





<!--HONumber=Sep16_HO2-->


