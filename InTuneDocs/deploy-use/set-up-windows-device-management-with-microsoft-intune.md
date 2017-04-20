---
title: "Einrichten der Windows-Geräteverwaltung mit Microsoft Intune | Microsoft-Dokumentation"
description: "Aktivieren Sie die Verwaltung mobiler Geräte (Mobile Device Management, MDM) für Windows-Geräte mit Microsoft Intune."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 03/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 771aed4e1c57171183b9a9ea7d9e0f702dc1859c
ms.openlocfilehash: f6014c5500b05762d123b2285ef859d67382e402
ms.lasthandoff: 04/06/2017


---

# <a name="set-up-windows-device-management"></a>Einrichten der Windows-Geräteverwaltung

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Verwenden Sie eine der folgenden Methoden zum Einrichten der Registrierung für Windows-Geräte:

- [**Automatische Registrierung von Windows 10 mit Azure Active Directory Premium**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)
 -  Diese Methode ist nur für Windows 10-Geräte verfügbar.
 -  Sie müssen für diese Methode über Azure Active Directory Premium verfügen.
 -  Wenn Sie die automatische Registrierung nicht aktivieren möchten, verwenden Sie die Registrierungsmethode für Windows 8.1 und Windows Phone 8.1.

- [**Registrierung ohne automatische Registrierung bei Azure AD Premium**](#enable-windows-enrollment-without-azure-ad-premium)
 - Sie müssen diese Methode verwenden, um Windows 8.1- und Windows Phone 8.1-Geräte zu registrieren.
 - Sie können diese Methode für Windows 8.1 und höher verwenden, wenn Sie Azure Active Directory (AD) Premium nicht verwenden möchten.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-automatic-enrollment"></a>Aktivieren der Windows-Registrierung ohne automatische Registrierung
Sie können Benutzer das Installieren und Registrieren ihrer Geräte ohne automatische Azure AD Premium-Registrierung ermöglichen. Nachdem Sie Benutzerkonten Lizenzen zugewiesen haben, kann der Benutzer dieses Konto einem Windows-Gerät hinzufügen und zustimmen, das Gerät in der Verwaltung zu registrieren. Wenn Sie DNS-CNAME-Ressourceneinträge erstellen, können Benutzer sich mit Intune verbinden und dort registrieren, ohne einen Servernamen eingeben zu müssen.

**Schritt 1: Erstellen von CNAME-Einträgen** (optional)<br>
Erstellen Sie CNAME-DNS-Ressourceneinträge für die Domäne des Unternehmens. Wenn der Name Ihrer Unternehmenswebsite beispielsweise „contoso.com“ lautet, erstellen Sie einen CNAME-Eintrag im DNS, der „EnterpriseEnrollment.contoso.com“ auf „enterpriseenrollment-s.manage.microsoft.com“ umleitet.

Obwohl die Erstellung von CNAME DNS-Einträgen optional ist, vereinfachen diese die Registrierung für Benutzer. Wenn kein CNAME-Eintrag für die Registrierung gefunden wurde, werden Benutzer dazu aufgefordert, manuell den MDM-Servernamen „enrollment.manage.microsoft.com“ einzugeben.

Existieren mehrere überprüfte Domänen, erstellen Sie einen CNAME-Eintrag für jede Domäne. Die CNAME-Ressourceneinträge müssen die folgenden Informationen enthalten:

CNAME-Ressourceneinträge müssen die folgenden Informationen enthalten:

|TYP|Hostname|Verweist auf|TTL|
|--------|-------------|-------------|-------|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Stunde|
|CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Stunde|

`EnterpriseEnrollment-s.manage.microsoft.com` – unterstützt eine Umleitung zum Intune-Dienst mit Domänenerkennung anhand des E-Mail-Domänennamens.

Wenn Ihr Unternehmen mehrere Domänen für die Anmeldeinformationen der Benutzer verwendet, erstellen Sie CNAME-Einträge für jede Domäne.

Wenn der Name Ihrer Unternehmenswebsite beispielsweise contoso.com lautet, erstellen Sie einen CNAME in DNS, der EnterpriseEnrollment.contoso.com an EnterpriseEnrollment-s.manage.microsoft.com umleitet. Es kann bis zu 72 Stunden dauern, bis Änderungen an DNS-Einträgen vollständig verteilt sind. Sie können die DNS-Änderung in Intune erst überprüfen, wenn der DNS-Eintrag verteilt ist.

**Schritt 2: Verifizieren des CNAME-Eintrags** (optional)<br>
Wählen Sie in der [Intune-Verwaltungskonsole](http://manage.microsoft.com) **Admin** &gt; **Verwaltung mobiler Geräte** &gt; **Windows** aus. Geben Sie die URL der überprüften Domäne der Unternehmenswebsite in das Feld **Verifizierten Domänennamen eingeben** ein, und wählen Sie anschließend **Automatische Erkennung testen** aus.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Benutzern mitteilen, wie Windows-Geräte registriert werden
Benutzern erklären, wie sie ihre Windows-Geräte registrieren können, und sie darüber informieren, was sie erwarten können, wenn ihre Geräte verwaltet werden.
Registrierungsanleitungen für Endbenutzer finden Sie unter [Registrieren Ihres Windows-Geräts bei Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows). Sie können Benutzer auch auf [Was kann mein IT-Administrator sehen, wenn ich mein Gerät bei Intune registriere?](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows) verweisen.

Weitere Informationen zu Endbenutzeraufgaben finden Sie unter [Ressourcen zu Endbenutzerszenarios in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune).

### <a name="see-also"></a>Weitere Informationen:
[Voraussetzungen für die Registrierung von Geräten in Microsoft Intune](prerequisites-for-enrollment.md)

