---
# required metadata

title: Verwalten von Intune-Lizenzen | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Verwalten von Intune-Lizenzen
Benutzer benötigen eine Lizenz für Ihr Intune-Abonnement, bevor sie sich beim Dienst anmelden oder Geräte für die Verwaltung registrieren können. Verfügen Benutzer über eine Lizenz, sind sie Mitglieder der [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)]-Benutzergruppe. In dieser Gruppe sind alle Benutzer enthalten, die über eine Lizenz zur Verwendung des Abonnements verfügen. **Jede Benutzerlizenz unterstützt die Registrierung von bis zu fünf Geräten.**.

## So werden Intune-Lizenzen zugewiesen
Wenn Benutzerkonten aus Ihrem lokalen Active Directory synchronisiert oder über das Kontoportal manuell zu Ihrem Clouddienstabonnement hinzugefügt werden, wird ihnen nicht automatisch eine Intune-Lizenz zugewiesen. Stattdessen muss ein Intune-Mandantenadministrator die Benutzerkonten später bearbeiten, um den betreffenden Benutzern eine Lizenz aus dem Kontoportal zuzuweisen.

Wenn Azure AD von Ihrem Abonnement und anderen Ihrem Abonnement zugeordneten Clouddiensten gemeinsam verwendet wird, haben Sie ebenfalls Zugriff auf Benutzer, die diesen Diensten hinzugefügt wurden. Diese Benutzer verfügen nicht über eine [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Lizenz, bis Sie jedem von ihnen eine Lizenz zuweisen.

> [!TIP]
> Wenn die Option zum Zuweisen oder Widerrufen einer Lizenz für [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] deaktiviert ist, schließt Ihr Abonnement möglicherweise Volumenlizenzoptionen ein, beispielsweise die Optionen, die bei Verwendung der [Enterprise Mobility Suite](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx) verfügbar sind. Informationen zum Zuweisen oder Widerrufen von Lizenzen entnehmen Sie der Dokumentation Ihrer Lizenzoptionen.

## Zuweisen einer Intune-Benutzerlizenz

Verwenden Sie das **[!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)]**, um cloudbasierte Benutzer manuell hinzuzufügen und um sowohl cloudbasierten Benutzerkonten als auch Konten, die aus Ihrem lokalen Active Directory mit Azure AD synchronisiert wurden, Lizenzen zuzuweisen.

1.  Melden Sie sich mit den Anmeldeinformationen Ihres Mandantenadministrators beim Intune-Kontoportal an.

2.  Wählen Sie das Benutzerkonto aus, dem Sie eine Intune-Benutzerlizenz zuweisen möchten, und aktivieren Sie in den Eigenschaften des Benutzerkontos das Kontrollkästchen **Microsoft Intune**.

3.  Das Benutzerkonto wird jetzt der Microsoft Intune-Benutzergruppe zugewiesen, die dem Benutzer Berechtigungen zur Verwendung des Diensts und zur Registrierung von Geräten für die Verwaltung gewährt.

### Selektive Verwaltung von EMS-Benutzerlizenzen über PowerShell
Unternehmen, die die Enterprise Mobility Suite (EMS) von Microsoft verwenden, verfügen möglicherweise über Benutzer, die nur Azure Active Directory Premium- oder Intune-Dienste im EMS-Paket benötigen. Sie können einen oder mehrere Dienste mithilfe von [Azure Active Directory PowerShell-Cmdlets](https://msdn.microsoft.com/library/jj151815.aspx) zuweisen.. 

Um Benutzerlizenzen für EMS-Dienste selektiv zuzuweisen, öffnen Sie PowerShell als Administrator auf einem Computer, auf dem das [Azure Active Directory-Modul für Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) installiert ist. Sie können PowerShell auf einem lokalen Computer oder einem AD FS-Server installieren.

Sie müssen eine neue Lizenz-SKU-Definition erstellen, die nur für die gewünschten Servicepläne gilt. Deaktivieren Sie zu diesem Zweck die Pläne, die Sie nicht anwenden möchten. Sie können beispielsweise eine Lizenz-SKU-Definition erstellen, die keine Intune-Lizenzen zuweist. Um eine Liste der verfügbaren Dienste anzuzeigen, geben Sie Folgendes ein:.
 
    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus 

Sie können den folgenden Befehl ausführen, um den Intune-Serviceplan auszuschließen. Mit der gleichen Methode können Sie die Definition auf eine vollständige Sicherheitsgruppe ausweiten oder detailliertere Filter verwenden. 

**Beispiel 1**
Erstellen Sie über die Befehlszeile einen neuen Benutzer, und weisen Sie eine EMS-Lizenz zu, ohne den auf Intune bezogenen Teil der Lizenz zu aktivieren:

    Connect-MsolService 
        
    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US
    
    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS 
    

Überprüfen Sie das Ergebnis:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**Beispiel 2**
Deaktivieren Sie den auf Intune bezogenen Teil der EMS-Lizenz für einen Benutzer, dem bereits eine Lizenz zugewiesen wurde:

    Connect-MsolService 
    
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -RemoveLicenses IAPProdPartnerTest:EMS
    
    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS
 
Überprüfen Sie das Ergebnis:
 
    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com" .Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

### Nächste Schritte
Gratulation! Sie haben Schritt 4 der Kurzanleitung *Erste Schritte mit Intune* abgeschlossen..
>[!div class="step-by-step"]

>[&larr; **Synchronisieren von Benutzern mit Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Organisieren von Benutzern und Geräten** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  


<!--HONumber=May16_HO1-->


