---
title: Blockieren von Apps ohne moderne Authentifizierung | Microsoft-Dokumentation
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 098b652c-01e0-45d1-a731-620b0d3dc7c1
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 0e1fa2341c0f74492a0ef80d0054922052bbe561


---

# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Blockieren von Apps, die keine moderne Authentifizierung verwenden (ADAL)

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Der bedingte Zugriff für Apps mit MAM-Richtlinien (MAM CA) hängt von Anwendungen ab, die die [moderne Authentifizierung](https://support.office.com/en-US/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) nutzen, bei der es sich um eine Implementierung von OAuth2 handelt. Die meisten mobilen Office-Anwendungen und Office-Anwendungen für den Desktop nutzen die moderne Authentifizierung. Es gibt jedoch Apps von Drittanbietern oder ältere Office-Apps, die andere Authentifizierungsmethoden wie die Standardauthentifizierung und die formularbasierte Authentifizierung nutzen.

Zum Blockieren dieser Apps wird Folgendes empfohlen:

* Setup-ADFS beansprucht Regeln zum Blockieren von nicht moderner Authentifizierungsprotokolle. Detaillierte Anleitungen werden in Szenario 3 beschrieben: [Blockieren des gesamten Zugriffs auf Office 365, bis auf browserbasierte Anwendungen](https://technet.microsoft.com/library/dn592182.aspx).

>[!IMPORTANT]
>MAM CA darf nicht mit der zertifikatbasierten Authentifizierung von Azure Active Directory (Azure AD) verwendet werden. Es darf immer jeweils nur eine Authentifizierungsmethode konfiguriert werden.



### <a name="see-also"></a>Weitere Informationen:
[Nur von Intune unterstützten Apps den Zugriff auf O365-Dienste erlauben](allow-policy-managed-apps-access-to-o365.md)



<!--HONumber=Dec16_HO2-->


