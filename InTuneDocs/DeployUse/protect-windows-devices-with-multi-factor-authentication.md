---
# required metadata

title: Schützen von Windows-Geräten mit mehrstufiger Authentifizierung | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9b4f197d-bc10-4bee-91c9-19bcc8287d36

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Schützen von Windows-Geräten mit mehrstufiger Authentifizierung
Microsoft Intune integriert die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA), um Ihre Unternehmensressourcen zu sichern. MFA erfordert zusätzlich zu Benutzernamen und Kennwörtern weitere Authentifizierungsfaktoren wie z. B eine Bestätigung per SMS. Intune unterstützt die Verwendung von MFA während der Registrierung von Geräten unter Windows 8.1 oder höher, Windows Phone 8.1 oder Windows 10 Desktop und Mobile. 

## Lokale Infrastrukturanforderungen für ADFS-MFA
Um die mehrstufige Authentifizierung einzurichten, benötigen Sie Folgendes:

-   **Active Directory-Domäne, mit der der ADFS-Server verbunden ist.**

-   **Active Directory Federation Services (ADFS)-Server, konfiguriert für MFA.** Einen Server mit Windows Server 2012 R2, eingerichtet als ADFS-Server. Weitere Informationen finden Sie unter [Sichern von Cloud- und lokalen Ressourcen mithilfe von Azure Multi-Factor Authentication-Server mit Windows Server 2012 R2 AD FS](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-adfs-w2k12/).

Alle oben aufgeführten Server müssen die Systemanforderungen unter [Systemanforderungen und Installationsinformationen für Windows Server 2012 R2](http://technet.microsoft.com/library/dn303418.aspx) erfüllen..

#### MFA mit Intune
Verfügt Ihre Organisation über eine lokale IT-Infrastruktur, die eine Active Directory-Domäne mit Active Directory-Verbunddiensten (AD FS) umfasst, können Sie MFA auf dem Verbundserver konfigurieren und anschließend für die Intune-Registrierung aktivieren. Durch Konfigurieren von MFA auf Intune ermöglichen Sie Ihren Benutzern, sich einmalig während der Registrierung zu authentifizieren und danach auf Unternehmensressourcen zuzugreifen, ohne jedes Mal den MFA-Prozess durchlaufen zu müssen.

>[!NOTE]
>MFA kann auf dem AD FS-Server pro Benutzer oder pro Gruppe angefordert werden.  

#### MFA ohne Intune
Wenn Sie MFA auf dem Verbundserver konfigurieren, aber nicht für die Registrierung bei Intune aktivieren, müssen die Benutzer sich jedes Mal per MFA authentifizieren, wenn sie von einem beliebigen Gerät aus auf Unternehmensressourcen zugreifen (nicht nur während der Geräteregistrierung).

Sie können Azure Active Directory (AAD) MFA auch so konfigurieren, dass die mehrstufige Authentifizierung stets angefordert wird, wenn Benutzer auf Unternehmensressourcen zugreifen. Diese Anforderung kann auf Benutzerbasis aktiviert werden. AAD-MFA ist ein Clouddienst, der keine lokale IT-Infrastruktur erfordert. Anweisungen zum Einrichten von AAD MFA finden Sie unter [Erste Schritte mit Azure Multi-Factor Authentication in der Cloud](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-cloud/)..

## Anfordern von ADFS-MFA bei der Registrierung von Windows-Geräten
Informationen zum Aktivieren von MFA in AD FS finden Sie unter [Verwalten von Risiken mit zusätzlicher mehrstufiger Authentifizierung für sensible Anwendungen](http://technet.microsoft.com/library/dn280949.aspx)..

## Einrichten von MFA während der Geräteregistrierung in Intune
>[!Important]  
>Aktivieren Sie MFA in Ihrem Azure AD-Mandanten oder in Ihrer lokalen Umgebung, bevor Sie MFA für die Intune-Registrierung von Windows-Geräten anfordern. Wenn Sie dies nicht tun, erhalten Benutzer eine Fehlermeldung, wenn sie versuchen, ihre Windows-Geräte zu registrieren. Benutzer erhalten auch dann eine Fehlermeldung, wenn die automatische Registrierung während der Einbindung über Azure AD konfiguriert ist und Benutzer versuchen, ihre Geräte über Azure AD einzubinden.

1.  Klicken Sie in der Intune-Verwaltungskonsole auf **Admin** &gt; **Verwaltung mobiler Geräte** &gt; **Mehrstufige Authentifizierung**..

2.  Klicken Sie auf **Mehrstufige Authentifizierung konfigurieren**, und klicken Sie dann auf **Mehrstufige Authentifizierung aktivieren**..



<!--HONumber=May16_HO1-->


