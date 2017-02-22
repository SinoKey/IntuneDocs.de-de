---
title: "Registrieren von Windows-Geräten | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Aktivieren Sie die Verwaltung mobiler Geräte (Mobile Device Management, MDM) für Windows-Geräte in Intune."
keywords: 
author: staciebarker
manager: stabar
ms.date: 02/15/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4103a4cef393df585b9b9daa92ab63dd7805e9e
ms.openlocfilehash: a55118e60750616f8b058846148364cbeccb5784


---

# <a name="enroll-windows-devices"></a>Windows-Geräte registrieren 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Verwenden Sie eine der folgenden Methoden zum Einrichten der Registrierung für Windows-Geräte:

- [**Automatische Registrierung mit Azure Active Directory Premium für Windows 10 und Windows 10 Mobile**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)
 -  Diese Methode betrifft nur Windows 10- und Windows 10 Mobile-Geräte.
 -  Sie müssen für diese Methode über Azure Active Directory Premium verfügen. Verwenden Sie andernfalls die Registrierungsmethode für Windows 8.1 und Windows Phone 8.1.
 -  Wenn Sie die automatische Registrierung nicht aktivieren möchten, verwenden Sie die Registrierungsmethode für Windows 8.1 und Windows Phone 8.1.

- [**Registrierung für Windows 8.1 und Windows Phone 8.1 durch Konfigurieren von CNAME**](#set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname)
 - Sie müssen diese Methode verwenden, um Windows 8.1- und Windows Phone 8.1-Geräte zu registrieren.


## <a name="prerequisites"></a>Voraussetzungen

Wenn einige der folgenden Voraussetzungen in der Vorschau von Intune in Azure noch nicht erfüllt sind, müssen Sie sie in der klassischen Intune-Verwaltungskonsole ausführen.

- [Konfigurieren eines benutzerdefinierten Domänennamens](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- Festlegen von **Microsoft Intune** als [Autorität für die Verwaltung mobiler Geräte (MDM)](set-mdm-authority.md)
- [Konfigurieren der Unternehmensportal-App](/intune-azure/manage-apps/company-portal-app.md)
- Zuweisen von Lizenzen zu Benutzern

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname"></a>Einrichten der Registrierung für Windows 8.1 und Windows Phone 8.1 durch Konfigurieren von CNAME

Sie können Benutzern die Möglichkeit geben, ihre Geräte mithilfe des Intune-Unternehmensportals installieren und zu registrieren. Wenn Sie DNS-CNAME-Ressourceneinträge erstellen, können Benutzer sich mit Intune verbinden und dort registrieren, ohne einen Servernamen eingeben zu müssen.

1. **Erstellen von CNAME-Einträgen** (optional)<br>
 Erstellen Sie **CNAME**-DNS-Ressourceneinträge für die Domäne des Unternehmens. Wenn der Name Ihrer Unternehmenswebsite beispielsweise „contoso.com“ lautet, erstellen Sie einen CNAME-Eintrag im DNS, der „EnterpriseEnrollment.contoso.com“ auf „enterpriseenrollment-s.manage.microsoft.com“ umleitet.

    Obwohl die Erstellung von CNAME DNS-Einträgen optional ist, vereinfachen diese die Registrierung für Benutzer. Wenn kein CNAME-Eintrag für die Registrierung gefunden wurde, werden Benutzer dazu aufgefordert, manuell den MDM-Servernamen „enrollment.manage.microsoft.com“ einzugeben.

    Existieren mehrere überprüfte Domänen, erstellen Sie einen CNAME-Eintrag für jede Domäne. Die CNAME-Ressourceneinträge müssen die folgenden Informationen enthalten:

    CNAME-Ressourceneinträge müssen die folgenden Informationen enthalten:

  |TYP|Hostname|Verweist auf|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Stunde|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Stunde|

  `EnterpriseEnrollment-s.manage.microsoft.com` – unterstützt eine Umleitung zum Intune-Dienst mit Domänenerkennung anhand des E-Mail-Domänennamens.

  `EnterpriseRegistration.windows.net` – unterstützt Windows 8.1- und Windows 10 Mobile-Geräte, die über das Geschäfts-, Schul- oder Unikonto bei Azure Active Directory registriert werden.

  Wenn Ihr Unternehmen mehrere Domänen für die Anmeldeinformationen der Benutzer verwendet, erstellen Sie CNAME-Einträge für jede Domäne.

  Wenn der Name Ihrer Unternehmenswebsite beispielsweise contoso.com lautet, erstellen Sie einen CNAME in DNS, der EnterpriseEnrollment.contoso.com an EnterpriseEnrollment-s.manage.microsoft.com umleitet. Es kann bis zu 72 Stunden dauern, bis Änderungen an DNS-Einträgen vollständig verteilt sind. Sie können die DNS-Änderung in Intune erst überprüfen, wenn der DNS-Eintrag verteilt ist.

2.  **Überprüfen von CNAME**<br>Wählen Sie in der [Intune-Verwaltungskonsole](http://manage.microsoft.com) **Verwaltung** &gt; **Verwaltung mobiler Geräte** &gt; **Windows Phone** aus. Geben Sie die URL der überprüften Domäne der Unternehmenswebsite in das Feld **Verifizierten Domänennamen eingeben** ein, und wählen Sie anschließend **Automatische Erkennung testen** aus.

3.  **Optionale Schritte**<br>Der Schritt **Hinzufügen von Sideload-Schlüsseln** wird für Windows 10 nicht benötigt. <br>Der Schritt **Codesignaturzertifikat hochladen** wird nur benötigt, wenn Sie branchenspezifische Apps, die nicht im Windows Store verfügbar sind, für Geräte verteilen.

4.  **Benutzern erklären, wie sie ihre Geräte registrieren können, und sie darüber informieren, was sie erwarten können, wenn ihre Geräte verwaltet werden.**

    Registrierungsanleitungen für Endbenutzer finden Sie unter [Registrieren Ihres Windows-Geräts bei Intune](https://docs.microsoft.com/en-us/intune/enduser/enroll-your-device-in-intune-windows). Sie können Benutzer auch auf [Was kann mein IT-Administrator sehen, wenn ich mein Gerät bei Intune registriere?](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows) verweisen.

    Weitere Informationen zu Endbenutzeraufgaben finden Sie unter [Ressourcen zu Endbenutzerszenarios in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune).

Es sind keine weiteren Schritte erforderlich, es sei denn, Sie stellen das Unternehmensportal selbst auf Geräten bereit.  Die Schritte 2 und 3 in der Verwaltungskonsole können ignoriert werden.



<!--HONumber=Feb17_HO3-->


