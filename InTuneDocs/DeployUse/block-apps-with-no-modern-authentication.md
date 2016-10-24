---
title: Blockieren von Apps ohne moderne Authentifizierung | Microsoft Intune
description: 
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 098b652c-01e0-45d1-a731-620b0d3dc7c1
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0f78ece8bbaf813c0082e6b764d174cf25bcb618
ms.openlocfilehash: 89f0bc5dd10c173718f9698e6e0342b5eb8c56e8


---

# Blockieren von Apps, die keine moderne Authentifizierung verwenden (ADAL)
Der bedingte Zugriff für Apps mit MAM-Richtlinien (MAM CA) hängt von Anwendungen ab, die die [moderne Authentifizierung](https://support.office.com/en-US/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) nutzen, bei der es sich um eine Implementierung von OAuth2 handelt. Die meisten mobilen Office-Anwendungen und Office-Anwendungen für den Desktop nutzen die moderne Authentifizierung. Es gibt jedoch Apps von Drittanbietern oder ältere Office-Apps, die andere Authentifizierungsmethoden wie die Standardauthentifizierung und die formularbasierte Authentifizierung nutzen.

Zum Blockieren dieser Apps wird Folgendes empfohlen:

* Setup-ADFS beansprucht Regeln zum Blockieren von nicht moderner Authentifizierungsprotokolle. Detaillierte Anleitungen werden in Szenario 3 beschrieben: [Blockieren des gesamten Zugriffs auf Office 365, bis auf browserbasierte Anwendungen](https://technet.microsoft.com/library/dn592182.aspx).

### Weitere Informationen:
[Allow only apps supported by Intune to access O365 services (Nur von Intune unterstützten Apps den Zugriff auf O365-Dienste erlauben)](allow-policy-managed-apps-access-to-o365.md)



<!--HONumber=Oct16_HO2-->


