---
title: "Konfigurieren eines benutzerdefinierten Domänennamens | Microsoft Intune"
description: "Hinzufügen eines benutzerdefinierten Domänennamens für Ihr Intune-Abonnement"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 29b6e5a3d319c741482fcc2b600842e2e42b96e2
ms.openlocfilehash: 9fe78bca15ffee1e5e0e7e3758ff70b6bc92b619


---


# <a name="configure-a-custom-domain-name"></a>Konfigurieren eines benutzerdefinierten Domänennamens

Wenn sich Ihre Organisation für einen cloudbasierten Microsoft-Dienst wie Intune registriert, erhalten Sie einen anfänglichen Domänenname, der in Azure Active Directory (AD) gehostet wird. Der Name sieht so aus: **IhreDomäne.onmicrosoft.com**. In diesem Beispiel ist **IhreDomäne** der Domänenname, den Sie bei der Registrierung ausgewählt haben, und **onmicrosoft.com** ist das Suffix, das den Konten zugewiesen wird, die Sie Ihrem Abonnement hinzufügen. Wenn Ihr Unternehmen über eine eigene Domäne verfügt, können Sie Ihre Intune-Instanz so konfigurieren, dass diese Domäne anstelle des bei der Einrichtung Ihres Abonnements angegebenen Domänennamens verwendet wird.

Bevor Sie Benutzerkonten erstellen oder Ihr lokales Active Directory-Verzeichnis synchronisieren, wird dringend empfohlen, dass Sie entscheiden, ob nur die .onmicrosoft.com-Domäne verwendet oder benutzerdefinierte Domänennamen hinzugefügt werden sollen. Das Konfigurieren einer benutzerdefinierten Domäne vor dem Hinzufügen von Benutzern kann die Verwaltung von Benutzeridentitäten für Ihr Abonnement vereinfachen, denn die Benutzer werden auf diese Weise in die Lage versetzt, sich mit den Anmeldeinformationen anzumelden, mit denen sie auch auf andere Domänenressourcen zugreifen.

Wenn Sie einen cloudbasierten Dienst von Microsoft abonnieren, wird Ihre Instanz dieses Diensts zu einem Microsoft [Azure AD-Mandanten](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant). Azure AD stellt Identitäts- und Verzeichnisdienste für Ihren cloudbasierten Dienst bereit. Die Aufgaben beim Konfigurieren von Intune zum Verwenden des benutzerdefinierten Domänennamens Ihres Unternehmens sind identisch mit denen bei anderen Azure AD-Mandanten. Daher können Sie sich an den Informationen und Verfahren unter [Hinzufügen Ihrer Domäne](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/) orientieren.

> [!TIP]
> Weitere Informationen zum Verwenden Ihrer benutzerdefinierten Domäne mit einem cloudbasierten Dienst von Microsoft finden Sie unter [Konzeptioneller Überblick über benutzerdefinierte Domänennamen in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/).

Sie können diesen anfänglichen Domänennamen weder ändern noch entfernen. Sie können jedoch Ihre eigenen benutzerdefinierten Domänennamen für die Verwendung mit Intune hinzufügen, überprüfen oder entfernen; das ist hilfreich, wenn Sie Ihre Geschäftsidentität beibehalten möchten.

## <a name="to-add-and-verify-your-custom-domain"></a>So fügen Sie Ihre benutzerdefinierte Domäne hinzu und überprüfen sie

1. Gehen Sie zum [Verwaltungsportal von Office 365](https://portal.office.com/Admin/Default.aspx) und melden Sie sich bei Ihrem Administratorkonto an.

2. Wählen Sie im Navigationsbereich **Einstellungen** &gt; **Domänen** aus.

3. Wählen Sie **Domäne hinzufügen** aus, und geben Sie Ihren benutzerdefinierten Domänennamen ein.

4. Das Dialogfeld **Domäne überprüfen** öffnet sich und bietet Ihnen die Werte, um den TXT-Eintrag in Ihrem DNS-Hostinganbieter zu erstellen.
    - **GoDaddy-Benutzer**: Das Verwaltungsportal von Office 365 leitet Sie zur Anmeldeseite von GoDaddy um. Nachdem Sie Ihre Anmeldeinformationen eingegeben und die Vereinbarung über die Erlaubnis für das Ändern der Domäne akzeptiert haben, wird der TXT-Eintrag automatisch erstellt. Alternativ können Sie [den TXT-Eintrag erstellen](https://support.office.com/en-us/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a?ui=en-US&rs=en-US&ad=US).
    - **Register.com-Benutzer**: Befolgen Sie die [schrittweise Anleitung](https://support.office.com/en-us/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e?ui=en-US&rs=en-US&ad=US#BKMK_verify), um den TXT-Eintrag zu erstellen.

    > [!TIP]
    > Stellen Sie sicher, dass Sie ein DNS-Alias (CNAME) für [Windows-Geräteregistrierung](/Intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) erstellen, während Sie Änderungen in Ihrem DNS-Hostinganbieter durchführen.

Die Schritte zum Hinzufügen und Überprüfen einer benutzerdefinierten Domäne können alternativ [in Azure Active Directory durchgeführt werden](https://azure.microsoft.com/en-us/documentation/articles/active-directory-add-domain/).

In einem Hybrid Cloud-Szenario können Sie, nachdem Sie Ihren benutzerdefinierten Domänennamen hinzugefügt haben, und überprüft wurde, dass Ihre Organisation ihn besitzt, weiterhin die Benutzerkonten in Ihrem lokalen Active Directory verwalten und diese anschließend mit Azure AD synchronisieren.

## <a name="to-synchronize-on-premises-users-with-azure-ad"></a>So synchronisieren Sie lokale Benutzer mit Azure AD##

1. [Fügen Sie das UPN-Suffix](https://technet.microsoft.com/en-us/library/cc772007.aspx) für Ihre benutzerdefinierte Domäne in Ihrem lokalen Active Directory hinzu.
2. Legen Sie das neue UPN-Suffix für die lokalen Benutzer fest, die Sie importieren möchten.
3. Führen Sie die [Azure AD Connect-Synchronisierung](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/) aus, um Ihre lokalen Benutzer mit Azure AD zu integrieren.
4. Sobald die Informationen des Benutzerkontos erfolgreich synchronisiert wurden, können Sie mithilfe des [Verwaltungsportals für Office 365](https://portal.office.com/Admin/Default.aspx) Microsoft Intune-Lizenzen zuweisen.

### <a name="see-also"></a>Weitere Informationen:

[Informationen über Ihre erste onmicrosoft.com-Domäne in Office 365](https://support.office.com/en-us/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A?ui=en-US&rs=en-US&ad=US)

[Was Sie wissen sollten, bevor Sie Microsoft Intune starten](what-to-know-before-you-start-microsoft-intune.md)
### <a name="next-steps"></a>Nächste Schritte
Gratulation! Sie haben Schritt 2 der Kurzanleitung *Erste Schritte mit Intune* abgeschlossen.

>[!div class="step-by-step"]

>[&larr;**Anmelden bei Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-1.md)     [**Hinzufügen von Benutzern zu Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-3.md)  



<!--HONumber=Nov16_HO4-->


