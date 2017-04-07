---
title: Zuweisen von Intune-Lizenzen | Microsoft-Dokumentation
description: "Zuweisen von Lizenzen zu Benutzern für Ihr Intune-Abonnement"
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 03/28/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: c66226b7fc31f91669c4f4f0693ccbd7c679189f
ms.openlocfilehash: b2fc3a3dc47466313a54d2f6aef6b67dff8d7343
ms.lasthandoff: 03/29/2017


---

# <a name="assign-intune-licenses-to-your-user-accounts"></a>Ihren Benutzerkonten Intune-Lizenzen zuweisen

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Egal, ob Sie manuell Benutzer hinzufügen oder aus Ihrem lokalen Active Directory synchronisieren, Sie müssen zunächst jedem Benutzer eine Intune-Lizenz zuweisen, bevor Benutzer ihre Geräte in Intune registrieren können.

## <a name="assign-an-intune-license-in-the-office-365-admin-center"></a>Eine Intune-Lizenz im Office 365 Admin Center zuweisen

Sie können das [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) verwenden, um cloudbasierte Benutzer manuell hinzuzufügen; außerdem können Sie es verwenden, um sowohl cloudbasierten Benutzerkonten als auch Konten, die aus Ihrer lokalen Active Directory-Bereitstellung mit Azure AD synchronisiert wurden, Lizenzen zuzuweisen.

1.  Melden Sie sich mit den Anmeldeinformationen Ihres Mandantenadministrators beim [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) an, und wählen Sie dann **Benutzer** > **Aktive Benutzer**.

2.  Wählen Sie das Benutzerkonto, dem Sie eine Intune-Benutzerlizenz zuweisen möchten, und wählen Sie dann **Produktlizenzen** > **Bearbeiten**.

3.  Schalten Sie **Intune** oder **Enterprise Mobility + Security** auf **An** um, und wählen Sie **Speichern**.

4. Das Benutzerkonto verfügt jetzt über die erforderlichen Berechtigungen, um den Dienst zu nutzen und Geräte für die Verwaltung zu registrieren.

> [!NOTE]
> Benutzer werden erst in der Administratorkonsole angezeigt, nachdem sie ein Gerät registriert haben. Darüber hinaus können Sie eine Gruppe von Benutzern auswählen, die Sie gleichzeitig bearbeiten möchten; so können Sie für alle Benutzer entweder eine Lizenz hinzufügen oder diese ersetzen.

## <a name="use-powershell-to-selectively-manage-ems-user-licenses"></a>Selektive Verwaltung von EMS-Benutzerlizenzen über PowerShell
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

