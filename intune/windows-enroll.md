---
title: "Windows-Geräte registrieren"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Aktivieren Sie die Verwaltung mobiler Geräte (Mobile Device Management, MDM) für Windows-Geräte in Intune."
keywords: 
author: nathbarn
manager: nathbarn
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 687be18cedd063b3c2701937f2522e801e51644b
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---

# <a name="enroll-windows-devices"></a>Windows-Geräte registrieren

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Dieses Thema hilft IT-Administratoren, die Windows-Registrierung für ihre Benutzer zu vereinfachen.  Windows-Geräte können ohne zusätzliche Schritte registriert werden, aber Sie können die Registrierung für Ihre Benutzer vereinfachen.

Für Geräte, die das Windows 10 Creators Update ausführen und in die Azure Active Directory-Domäne eingebunden sind, haben wir Unterstützung für die Mehrbenutzerverwaltung hinzugefügt. Das bedeutet Folgendes: Wenn sich unterschiedliche Standardbenutzer mit ihren Azure AD-Anmeldeinformationen auf dem Gerät anmelden, erhalten sie alle Apps und Richtlinien, die ihrem jeweiligen Benutzernamen zugewiesen sind. Benutzer können das Unternehmensportal derzeit nicht für Self-Service-Szenarien – beispielsweise zum Installieren von Apps – verwenden.

Zwei Faktoren bestimmen, wie Sie die Registrierung von Windows-Geräten vereinfachen können:

- **Verwenden Sie Azure Active Directory Premium?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) ist in Enterprise Mobility + Security und in anderen Lizenzierungsplänen enthalten.
- **Welche Versionen von Windows-Clients werden registriert?** <br>Windows 10-Geräte können automatisch durch Hinzufügen eines Geschäfts-oder Schulkontos registriert werden. Frühere Versionen müssen mithilfe der Unternehmensportal-App registriert werden.

||**Azure AD Premium**|**AD (Sonstiges)**|
|----------|---------------|---------------|  
|**Windows 10**|[Automatische Registrierung](#enable-windows-10-automatic-enrollment) |[Benutzerregistrierung](#enable-windows-enrollment-without-azure-ad-premium)|
|**Frühere Windows-Versionen**|[Benutzerregistrierung](#enable-windows-enrollment-without-azure-ad-premium)|[Benutzerregistrierung](#enable-windows-enrollment-without-azure-ad-premium)|

[!INCLUDE[AAD-enrollment](./includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-azure-ad-premium"></a>Aktivieren der Windows-Registrierung ohne Azure AD Premium
Sie können Benutzern das Registrieren ihrer Geräte ohne automatische Azure AD Premium-Registrierung ermöglichen. Weisen Sie Benutzern Lizenzen zu, damit sie sich registrieren können, sobald sie den privat genutzten Geräten ihre Geschäftskonten hinzugefügt haben oder Ihrer Azure AD mit den firmeneigenen Geräten beigetreten sind. Durch das Erstellen eines DNS-Alias (Eintragstyp CNAME) erleichtern Sie es den Benutzern, ihre Geräte zu registrieren. Wenn Sie DNS-CNAME-Ressourceneinträge erstellen, können Benutzer sich mit Intune verbinden und dort registrieren, ohne einen Servernamen eingeben zu müssen.

**Schritt 1: Erstellen von CNAME-Einträgen** (optional)<br>
Erstellen Sie CNAME-DNS-Ressourceneinträge für die Domäne des Unternehmens. Wenn der Name Ihrer Unternehmenswebsite beispielsweise „contoso.com“ lautet, erstellen Sie einen CNAME-Eintrag im DNS, der „EnterpriseEnrollment.contoso.com“ auf „enterpriseenrollment-s.manage.microsoft.com“ umleitet.

Obwohl die Erstellung von CNAME DNS-Einträgen optional ist, vereinfachen diese die Registrierung für Benutzer. Wenn kein CNAME-Eintrag für die Registrierung gefunden wurde, werden Benutzer aufgefordert, manuell den MDM-Servernamen „enrollment.manage.microsoft.com“ einzugeben.

|Typ|Hostname|Verweist auf|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 Stunde|

Wenn Sie mehr als ein UPN-Suffix haben, müssen Sie einen CNAME für jeden Domänennamen erstellen und jeden auf EnterpriseEnrollment-s.manage.microsoft.com zeigen. Wenn z.B. Benutzer bei Contoso name@contoso.com aber auch name@us.contoso.com und name@eu.constoso.com als ihre E-Mail/UPN verwenden, muss der Contoso-DNS-Administrator die folgenden CNAMEs erstellen.

|Typ|Hostname|Verweist auf|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 Stunde|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 Stunde|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 Stunde|

`EnterpriseEnrollment-s.manage.microsoft.com` – unterstützt eine Umleitung zum Intune-Dienst mit Domänenerkennung anhand des E-Mail-Domänennamens.

Es kann bis zu 72 Stunden dauern, bis Änderungen an DNS-Einträgen vollständig verteilt sind. Sie können die DNS-Änderung in Intune erst überprüfen, wenn der DNS-Eintrag verteilt ist.

**Schritt 2: Verifizieren des CNAME-Eintrags** (optional)<br>
Wählen Sie im Azure Intune-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** > **Windows-Registrierung aktivieren** aus. Geben Sie die URL der überprüften Domäne der Unternehmenswebsite in das Feld **Verifizierten Domänennamen eingeben** ein, und wählen Sie anschließend **Automatische Erkennung testen** aus.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Benutzern mitteilen, wie Windows-Geräte registriert werden
Benutzern erklären, wie sie ihre Windows-Geräte registrieren können, und sie darüber informieren, was sie erwarten können, wenn ihre Geräte verwaltet werden. Registrierungsanleitungen für Endbenutzer finden Sie unter [Registrieren Ihres Windows-Geräts bei Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). Sie können Benutzer auch auf [Was kann mein IT-Administrator sehen, wenn ich mein Gerät bei Intune registriere?](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows) verweisen.

Weitere Informationen zu Endbenutzeraufgaben finden Sie unter [Ressourcen zu Endbenutzerszenarios in Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/how-to-educate-your-end-users-about-microsoft-intune).

