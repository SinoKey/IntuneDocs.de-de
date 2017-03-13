---
title: "Einrichten der Windows-Geräteverwaltung mit Microsoft Intune | Microsoft-Dokumentation"
description: "Aktivieren Sie die Verwaltung mobiler Geräte (Mobile Device Management, MDM) für Windows-Geräte mit Microsoft Intune."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 02/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 255c3e47464ac7670a971881cf399e8e2bb17044
ms.openlocfilehash: 4acbae2aba4cff21286d45cb7cb1691864c281dc
ms.lasthandoff: 02/28/2017


---

# <a name="set-up-windows-device-management"></a>Einrichten der Windows-Geräteverwaltung

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Verwenden Sie eine der folgenden Methoden zum Einrichten der Registrierung für Windows-Geräte:

- [**Automatische Registrierung mit Azure Active Directory Premium für Windows 10 und Windows 10 Mobile**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)
 -  Diese Methode betrifft nur Windows 10- und Windows 10 Mobile-Geräte.
 -  Sie müssen für diese Methode über Azure Active Directory Premium verfügen. Verwenden Sie andernfalls die Registrierungsmethode für Windows 8.1 und Windows Phone 8.1.
 -  Wenn Sie die automatische Registrierung nicht aktivieren möchten, verwenden Sie die Registrierungsmethode für Windows 8.1 und Windows Phone 8.1.


- [**Registrierung für Windows 8.1 und Windows Phone 8.1 durch Konfigurieren von CNAME**](#set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname)
 - Sie müssen diese Methode verwenden, um Windows 8.1- und Windows Phone 8.1-Geräte zu registrieren.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname"></a>Einrichten der Registrierung für Windows 8.1 und Windows Phone 8.1 durch Konfigurieren von CNAME
Sie können Benutzern die Möglichkeit geben, ihre Geräte mithilfe des Intune-Unternehmensportals installieren und zu registrieren. Wenn Sie DNS-CNAME-Ressourceneinträge erstellen, können Benutzer sich mit Intune verbinden und dort registrieren, ohne einen Servernamen eingeben zu müssen.

### <a name="step-1-set-up-intune"></a>Schritt 1: Einrichten von Intune

Wenn nicht bereits geschehen, bereiten Sie die Verwaltung mobiler Geräte durch [Festlegen der Autorität für die Verwaltung mobiler Geräte (mobile device management, MDM)](prerequisites-for-enrollment.md#step-2-set-mdm-authority) auf **Microsoft Intune** und durch anschließendes Einrichten von MDM vor.

### <a name="step-2-create-cnames-optional"></a>Schritt 2: Erstellen von CNAME-Einträgen (optional)

Erstellen Sie **CNAME**-DNS-Ressourceneinträge für die Domäne des Unternehmens. Wenn der Name Ihrer Unternehmenswebsite beispielsweise „contoso.com“ lautet, erstellen Sie einen CNAME-Eintrag im DNS, der „EnterpriseEnrollment.contoso.com“ auf „enterpriseenrollment-s.manage.microsoft.com“ umleitet.


   Obwohl die Erstellung von CNAME DNS-Einträgen optional ist, vereinfachen diese die Registrierung für Benutzer. Wenn kein CNAME-Eintrag für die Registrierung gefunden wurde, werden Benutzer dazu aufgefordert, manuell den MDM-Servernamen „enrollment.manage.microsoft.com“ einzugeben.

   CNAME-Ressourceneinträge müssen die folgenden Informationen enthalten:

  |TYP|Hostname|Verweist auf|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Stunde|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Stunde|

  `EnterpriseEnrollment-s.manage.microsoft.com` – unterstützt eine Umleitung zum Intune-Dienst mit Domänenerkennung anhand des E-Mail-Domänennamens.

  `EnterpriseRegistration.windows.net` – unterstützt Windows 8.1- und Windows 10 Mobile-Geräte, die über das Geschäfts-, Schul- oder Unikonto bei Azure Active Directory registriert werden.

  Wenn Ihr Unternehmen mehrere Domänen für die Anmeldeinformationen der Benutzer verwendet, erstellen Sie CNAME-Einträge für jede Domäne.

  Wenn der Name Ihrer Unternehmenswebsite beispielsweise contoso.com lautet, erstellen Sie einen CNAME in DNS, der EnterpriseEnrollment.contoso.com an EnterpriseEnrollment-s.manage.microsoft.com umleitet. Es kann bis zu 72 Stunden dauern, bis Änderungen an DNS-Einträgen vollständig verteilt sind. Sie können die DNS-Änderung in Intune erst überprüfen, wenn der DNS-Eintrag verteilt ist.

### <a name="step-3-verify-cname"></a>Schritt 3: Überprüfen von CNAME

Wählen Sie in der [Intune-Verwaltungskonsole](http://manage.microsoft.com) **Admin** &gt; **Verwaltung mobiler Geräte** &gt; **Windows** aus. Geben Sie die URL der überprüften Domäne der Unternehmenswebsite in das Feld **Verifizierten Domänennamen eingeben** ein, und wählen Sie anschließend **Automatische Erkennung testen** aus.

### <a name="step-4-tell-your-users-how-to-enroll-their-devices-and-what-to-expect-after-theyre-brought-into-management"></a>Schritt 4: Benutzern erklären, wie sie ihre Geräte registrieren können, und sie darüber informieren, was sie erwarten können, wenn ihre Geräte verwaltet werden

   Registrierungsanleitungen für Endbenutzer finden Sie unter [Registrieren Ihres Windows-Geräts bei Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows).

   Weitere Informationen zu Aufgaben für Endbenutzer finden Sie unter [So informieren sie Ihre Endbenutzer über Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune) und [Endbenutzer-Leitfaden für Windows-Geräte](../enduser/using-your-windows-device-with-intune.md).

### <a name="see-also"></a>Weitere Informationen:
[Voraussetzungen für die Registrierung von Geräten in Microsoft Intune](prerequisites-for-enrollment.md)

