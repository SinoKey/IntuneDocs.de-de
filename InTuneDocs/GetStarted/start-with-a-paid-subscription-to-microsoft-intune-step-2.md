---
title: "Konfigurieren eines benutzerdefinierten Domänennamens | Microsoft Intune"
description: "Beschreibt den Prozess des Hinzufügens eines benutzerdefinierten Domänennamens für Ihr Intune-Abonnement."
keywords: 
author: Staciebarker
manager: arob98
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: f18afc5487fe20ba4a13d938dad78fa6087128d7


---


# Konfigurieren eines benutzerdefinierten Domänennamens

Standardmäßig verwendet Intune den **<domain>.onmicrosoft.com**-Domänennamen, den Sie beim Abonnieren des Diensts ausgewählt haben. Wenn Ihr Unternehmen über eine eigene Domäne verfügt, können Sie Ihre Intune-Instanz so konfigurieren, dass diese Domäne anstelle des bei der Einrichtung Ihres Abonnements angegebenen Domänennamens verwendet wird.

Bevor Sie neue Benutzerkonten erstellen oder Kunden aus ihrem lokalen Active Directory synchronisieren, wird dringend empfohlen, dass Sie entscheiden, ob nur die .onmicrosoft.com-Domäne verwendet oder benutzerdefinierte Domänennamen hinzugefügt werden sollen. Das Konfigurieren einer benutzerdefinierten Domäne vor dem Hinzufügen von Benutzern kann die Verwaltung von Benutzeridentitäten für Ihr Abonnement vereinfachen, denn die Benutzer werden auf diese Weise in die Lage versetzt, sich mit den Anmeldeinformationen anzumelden, mit denen sie auch auf andere Domänenressourcen zugreifen.

Wenn Sie einen cloudbasierten Dienst von Microsoft abonnieren, wird Ihre Instanz dieses Diensts zu einem Microsoft [Azure AD-Mandanten](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant). Azure AD stellt Identitäts- und Verzeichnisdienste für Ihren cloudbasierten Dienst bereit. Die Aufgaben beim Konfigurieren von Intune zum Verwenden des benutzerdefinierten Domänennamens Ihres Unternehmens sind identisch mit denen bei anderen Azure AD-Mandanten. Daher können Sie sich an den Informationen und Verfahren unter [Hinzufügen Ihrer Domäne](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/) orientieren.

> [!TIP]
> Weitere Informationen zum Verwenden Ihrer benutzerdefinierten Domäne mit einem cloudbasierten Dienst von Microsoft finden Sie unter [Konzeptioneller Überblick über benutzerdefinierte Domänennamen in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/).

### Nächste Schritte
Gratulation! Sie haben Schritt 2 der Kurzanleitung *Erste Schritte mit Intune* abgeschlossen.

>[!div class="step-by-step"]

>[&larr;**Anmelden bei Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-1.md)     [**Hinzufügen von Benutzern zu Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-3.md)  



<!--HONumber=Jul16_HO3-->


