---
title: Verwalten von Intune-Lizenzen | Microsoft-Dokumentation
description: "Zuweisen von Lizenzen zu Benutzern für Ihr Intune-Abonnement"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ad13897fe7bbe4fe13167bb4ce7f558b436a7a90
ms.openlocfilehash: b6ab60eff3c65244290b7141e81a7b052dd790ed
ms.lasthandoff: 02/15/2017


---

# <a name="manage-intune-licenses"></a>Verwalten von Intune-Lizenzen

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

In diesem Thema erfahren Administratoren, wie sie Benutzern Intune-Lizenzen zuweisen können, damit Geräte für die Verwaltung aufgenommen werden können.

Bevor Benutzer sich für die Verwendung des Intune-Diensts anmelden oder ihre Geräte für die Verwaltung registrieren können, müssen Sie jedem Benutzer zunächst über das [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) eine Lizenz für Ihr Intune-Abonnement zuweisen.

Unternehmen, die die Enterprise Mobility + Security (EMS) von Microsoft verwenden, verfügen möglicherweise über Benutzer, die nur Azure Active Directory Premium- oder Intune-Dienste im EMS-Paket benötigen. Sie können einen oder mehrere Dienste mithilfe von [Azure Active Directory PowerShell-Cmdlets](https://msdn.microsoft.com/library/jj151815.aspx) zuweisen. Weitere Informationen finden Sie unter [Verwalten von Intune-Lizenzen mithilfe von PowerShell](start-with-a-paid-subscription-to-microsoft-intune-step-4-posh.md).

## <a name="how-intune-licenses-are-assigned"></a>So werden Intune-Lizenzen zugewiesen
Wenn Benutzerkonten aus Ihrer lokalen Active Directory-Bereitstellung synchronisiert oder über das [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) manuell zu Ihrem Clouddienstabonnement hinzugefügt werden, wird ihnen nicht automatisch eine Intune-Lizenz zugewiesen. Stattdessen muss ein Intune-Mandantenadministrator die Benutzerkonten später bearbeiten, um den betreffenden Benutzern über das Office 365-Portal eine Lizenz zuzuweisen.

Wenn Azure AD von Ihrem Abonnement und anderen Ihrem Abonnement zugeordneten Clouddiensten gemeinsam verwendet wird, haben Sie ebenfalls Zugriff auf Benutzer, die diesen Diensten hinzugefügt wurden. Diese Benutzer verfügen nicht über eine [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Lizenz, bis Sie jedem von ihnen eine Lizenz zuweisen.

> [!TIP]
> Wenn die Option zum Zuweisen oder Widerrufen einer Lizenz für [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] deaktiviert ist, schließt Ihr Abonnement möglicherweise Volumenlizenzoptionen ein, beispielsweise die Optionen, die bei Verwendung der [Enterprise Mobility Suite + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx) verfügbar sind. Informationen zum Zuweisen oder Widerrufen von Lizenzen entnehmen Sie der Dokumentation Ihrer Lizenzoptionen.

## <a name="assign-an-intune-user-license"></a>Zuweisen einer Intune-Benutzerlizenz

Verwenden Sie das [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854), um cloudbasierte Benutzer manuell hinzuzufügen und um sowohl cloudbasierten Benutzerkonten als auch Konten, die aus Ihrer lokalen Active Directory-Bereitstellung mit Azure AD synchronisiert wurden, Lizenzen zuzuweisen.

1.  Melden Sie sich mit den Anmeldeinformationen Ihres Mandantenadministrators beim [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) an, und wählen Sie dann **Personen** > **Alle Benutzer**.

2.  Wählen Sie das Benutzerkonto aus, dem Sie eine Intune-Benutzerlizenz zuweisen möchten, und wählen Sie dann entweder **Microsoft Intune** oder **Enterprise Mobility Suite** aus.

3.  Das Benutzerkonto verfügt jetzt über die erforderlichen Berechtigungen, um den Dienst zu nutzen und Geräte für die Verwaltung zu registrieren.

> [!NOTE]
> Benutzer werden in der Konsole angezeigt, sobald sie ein Gerät registriert haben.

### <a name="use-powershell-to-selectively-manage-ems-user-licenses"></a>Selektive Verwaltung von EMS-Benutzerlizenzen über PowerShell
Organisationen, die Microsoft Enterprise Mobility + Security (EMS, früher Enterprise Mobility Suite) verwenden, verfügen jedoch möglicherweise über Benutzer, die nur Azure Active Directory Premium- oder Intune-Dienste im EMS-Paket benötigen. Sie können einen oder mehrere Dienste mithilfe von [Azure Active Directory PowerShell-Cmdlets](https://msdn.microsoft.com/library/jj151815.aspx) zuweisen.

Um Benutzerlizenzen für EMS-Dienste selektiv zuzuweisen, öffnen Sie PowerShell als Administrator auf einem Computer, auf dem das [Azure Active Directory-Modul für Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) installiert ist. Sie können PowerShell auf einem lokalen Computer oder einem AD FS-Server installieren.

Sie müssen eine neue Lizenz-SKU-Definition erstellen, die nur für die gewünschten Servicepläne gilt. Deaktivieren Sie zu diesem Zweck die Pläne, die Sie nicht anwenden möchten. Sie können beispielsweise eine Lizenz-SKU-Definition erstellen, die keine Intune-Lizenzen zuweist. Um eine Liste der verfügbaren Dienste anzuzeigen, geben Sie Folgendes ein:.

    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus

Sie können den folgenden Befehl ausführen, um den Intune-Serviceplan auszuschließen. Mit der gleichen Methode können Sie die Definition auf eine vollständige Sicherheitsgruppe ausweiten oder detailliertere Filter verwenden.

**Beispiel 1**<br>
Erstellen Sie über die Befehlszeile einen neuen Benutzer, und weisen Sie eine EMS-Lizenz zu, ohne den auf Intune bezogenen Teil der Lizenz zu aktivieren:

    Connect-MsolService

    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS


Überprüfen Sie das Ergebnis:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**Beispiel 2**<br>
Deaktivieren Sie den auf Intune bezogenen Teil der EMS-Lizenz für einen Benutzer, dem bereits eine Lizenz zugewiesen wurde:

    Connect-MsolService

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -LicenseOptions $CustomEMS

Überprüfen Sie das Ergebnis:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

>[!div class="step-by-step"]

>[&larr; **Synchronisieren von Benutzern mit Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Organisieren von Benutzern und Geräten** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  

