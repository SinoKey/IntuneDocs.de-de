---
title: "Mehrstufige Authentifizierung für Windows | Microsoft Intune"
description: Intune integriert die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA), um Ihre Unternehmensressourcen zu sichern.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9b4f197d-bc10-4bee-91c9-19bcc8287d36
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 1bfd17f9fcc73049254bc77351eae48da874fb4c


---

# <a name="protect-windows-devices-with-multi-factor-authentication"></a>Schützen von Windows-Geräten mit mehrstufiger Authentifizierung
Microsoft Intune integriert die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA), um Ihre Unternehmensressourcen zu sichern. MFA erfordert zusätzlich zu Benutzernamen und Kennwörtern weitere Authentifizierungsfaktoren, wie z.B eine Bestätigung per SMS. Intune unterstützt die Verwendung von MFA während der Registrierung von Geräten unter Windows 8.1 oder höher, Windows Phone 8.1 oder Windows 10 Desktop und Mobile.

## <a name="on-premises-infrastructure-requirements-for-adfs-mfa"></a>Lokale Infrastrukturanforderungen für ADFS-MFA
Um die mehrstufige Authentifizierung einzurichten, benötigen Sie Folgendes:

-   Automatische Registrierung, wie unter [Einrichten der Windows-Geräteverwaltung](set-up-windows-device-management-with-microsoft-intune.md) beschrieben.
-   **Eine Active Directory-Domäne, mit der der AD FS-Server verbunden ist**.

-   **AD FS-Server (Active Directory Federation Services), konfiguriert für MFA**. Ein Server, der Windows Server 2012 R2 ausführt und als AD FS-Server eingerichtet ist. Weitere Informationen finden Sie unter [Sichern von Cloud- und lokalen Ressourcen mithilfe von Azure Multi-Factor Authentication-Server mit Windows Server 2012 R2 AD FS](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-adfs-w2k12/).

Die Server müssen die Systemanforderungen unter [Systemanforderungen und Installationsinformationen für Windows Server 2012 R2](http://technet.microsoft.com/library/dn303418.aspx) erfüllen.

 


#### <a name="mfa-with-intune"></a>MFA mit Intune
Verfügt Ihre Organisation über eine lokale IT-Infrastruktur, die eine Active Directory-Domäne mit Active Directory-Verbunddiensten (Active Directory Federation Services; AD FS) umfasst, können Sie MFA auf dem Verbundserver einrichten und anschließend für die Intune-Registrierung aktivieren. Durch Konfigurieren von MFA auf Intune können Benutzer sich einmalig während der Registrierung authentifizieren und anschließend Unternehmensressourcen verwenden, ohne jedes Mal den MFA-Prozess durchlaufen zu müssen.

>[!NOTE]
>MFA kann auf dem AD FS-Server pro Benutzer oder pro Gruppe angefordert werden.  

#### <a name="mfa-without-intune"></a>MFA ohne Intune
Wenn Sie MFA auf dem Verbundserver einrichten, aber nicht für die Registrierung bei Intune aktivieren, müssen die Benutzer sich jedes Mal per MFA authentifizieren, wenn sie auf Unternehmensressourcen zugreifen (nicht nur während der Geräteregistrierung).

Sie können Azure Active Directory (Azure AD) MFA auch so verwenden, dass die mehrstufige Authentifizierung auf Benutzerbasis stets angefordert wird, wenn Benutzer auf Unternehmensressourcen zugreifen. Azure AD-MFA ist ein Clouddienst, der keine lokale IT-Infrastruktur erfordert. Anweisungen zum Einrichten von Azure AD MFA finden Sie unter [Erste Schritte mit Azure Multi-Factor Authentication in der Cloud](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-cloud/).

## <a name="requiring-adfs-mfa-during-enrollment-of-windows-devices"></a>Anfordern von ADFS-MFA bei der Registrierung von Windows-Geräten
Informationen zum Aktivieren der MFA in ADFS finden Sie unter [Verwalten von Risiken mit zusätzlicher mehrstufiger Authentifizierung für sensible Anwendungen](http://technet.microsoft.com/library/dn280949.aspx).

## <a name="set-up-device-enrollment-mfa-in-intune"></a>Einrichten von MFA während der Geräteregistrierung in Intune
>[!Important]  
>Aktivieren Sie MFA in Ihrem Azure AD-Mandanten oder in Ihrer lokalen Umgebung, bevor Sie MFA für die Intune-Registrierung von Windows-Geräten anfordern. Wenn Sie dies nicht tun, erhalten Benutzer eine Fehlermeldung, wenn sie versuchen, ihre Windows-Geräte zu registrieren. Benutzer erhalten auch dann eine Fehlermeldung, wenn die automatische Registrierung während der Einbindung über Azure AD eingerichtet ist und Benutzer versuchen, ihre Geräte über Azure AD einzubinden.

1.  Wählen Sie in der Intune-Verwaltungskonsole **Admin** &gt; **Verwaltung mobiler Geräte** &gt; **Multi-Factor Authentication** aus.

2.  Wählen Sie **Multi-Factor Authentication konfigurieren** aus, und wählen Sie anschließend **Multi-Factor Authentication aktivieren** aus.



<!--HONumber=Nov16_HO1-->


