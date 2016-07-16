---
title: "Domänennamen für Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 06/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c3c136f0-330d-432a-a91f-16f7dd097e55
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3d99669f90fe7ebec7854b7a800b09b0685c314e
ms.openlocfilehash: aaede1500f28c6eb8c2a21924d7c3b7f633eca26


---



# Verwalten von benutzerdefinierten Domänen mit Microsoft Intune

Die Schritte zum Hinzufügen und Überprüfen einer benutzerdefinierten Domäne können alternativ [in Azure Active Directory durchgeführt werden](https://azure.microsoft.com/en-us/documentation/articles/active-directory-add-domain/).

Wenn sich Ihre Organisation für einen cloudbasierten Microsoft-Dienst wie Intune registriert, wird Ihnen ein anfänglicher Domänenname gegeben, der in Azure Active Directory gehostet wird. Der Name sieht so aus: **IhreDomäne.onmicrosoft.com**. In diesem Beispiel ist **IhreDomäne** der Domänenname, den Sie bei der Registrierung ausgewählt haben, und **onmicrosoft.com** ist das Suffix, das den Konten zugewiesen wird, die Sie Ihrem Abonnement hinzufügen.

Sie können diesen anfänglichen Domänennamen weder ändern noch entfernen. Sie können jedoch Ihre eigenen benutzerdefinierten Domänennamen für die Verwendung mit Intune hinzufügen, überprüfen oder entfernen; das ist hilfreich, wenn Sie Ihre Geschäftsidentität beibehalten möchten.

## So fügen Sie Ihre benutzerdefinierte Domäne hinzu und überprüfen sie 

1. Gehen Sie zum [Verwaltungsportal von Office 365](https://portal.office.com/Admin/Default.aspx) und melden Sie sich bei Ihrem Administratorkonto an.
    > [!IMPORTANT]
    > Überprüfen Sie Ankündigungen unter     [Intune Account Portal has merged with the Office 365 management portal](https://docs.microsoft.com/en-us/intune/deploy-use/account-portal-merged-with-Office-365) (Intune-Kontenportal wurde mit dem Verwaltungsportal von Office 365 zusammengeführt), um weitere Informationen zum Verwaltungsort von Microsoft Intune-Benutzern, -Gruppen und Domänen zu erhalten.
2. Wählen Sie im Navigationsbereich **Einstellungen** &gt; **Domänen** aus.
3. Wählen Sie **Domäne hinzufügen** aus, und geben Sie Ihren benutzerdefinierten Domänennamen ein.
4. Das Dialogfeld **Domäne überprüfen** öffnet sich und bietet Ihnen die Werte, um den TXT-Eintrag in Ihrem DNS-Hostinganbieter zu erstellen.
    > [!TIP]
    > Das Verwaltungsportal von Office 365 leitet Sie zur Anmeldeseite von GoDaddy um, wenn eine GoDaddy-Domäne verwendet wird. Der TXT-Eintrag wird automatisch erstellt, nachdem Sie Ihre Anmeldeinformationen eingegeben und die Vereinbarung über die Erlaubnis für das Ändern der Domäne akzeptiert haben.
    > 
    > Alternativ können Sie [den TXT-Eintrag manuell erstellen, wenn Sie eine GoDaddy-Domäne verwenden](https://support.office.com/en-us/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a?ui=en-US&rs=en-US&ad=US), basierend auf den in diesem Schritt angegebenen Werten.

    > [!NOTE]
    > Führen Sie die [Schritt-für-Schritt-Anleitung](https://support.office.com/en-us/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e?ui=en-US&rs=en-US&ad=US#BKMK_verify) aus, um den TXT-Eintrag zu erstellen, wenn Sie eine Register.com-Domäne verwenden, basierend auf den in diesem Schritt bereitgestellten Werten.

5. Stellen Sie sicher, dass Sie ein DNS-Alias (CNAME) für [Windows-Geräteregistrierung](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) erstellen, während Sie Änderungen in Ihrem DNS-Hostinganbieter durchführen.

In einem Hybrid Cloud-Szenario können Sie, nachdem Sie Ihren benutzerdefinierten Domänennamen hinzugefügt haben, und überprüft wurde, dass Ihre Organisation ihn besitzt, weiterhin die Benutzerkonten in Ihrem lokalen Active Directory verwalten und diese anschließend mit Azure AD synchronisieren.

## So synchronisieren Sie lokale Benutzer mit Azure AD##

1. [Fügen Sie das UPN-Suffix](https://technet.microsoft.com/en-us/library/cc772007.aspx) für Ihre benutzerdefinierte Domäne in Ihrem lokalen Active Directory hinzu.
2. Legen Sie das neue UPN-Suffix für die lokalen Benutzer fest, die Sie importieren möchten.
3. Führen Sie die [Azure AD Connect-Synchronisierung](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/) aus, um Ihre lokalen Benutzer mit Azure AD zu integrieren.
4. Sobald die Informationen des Benutzerkontos erfolgreich synchronisiert wurden, können Sie mithilfe des [Verwaltungsportals für Office 365](https://portal.office.com/Admin/Default.aspx) Microsoft Intune-Lizenzen zuweisen.

### Weitere Informationen:

[Informationen über Ihre erste „onmicrosoft.com“-Domäne in Office 365](https://support.office.com/en-us/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A?ui=en-US&rs=en-US&ad=US)

[Was Sie wissen sollten, bevor Sie mit der Verwendung von Microsoft Intune starten](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Jun16_HO5-->


