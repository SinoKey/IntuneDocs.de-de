---
title: "Einrichten der Windows-Geräteverwaltung mit Microsoft Intune | Microsoft Intune"
description: "Aktivieren Sie die Verwaltung mobiler Geräte (Mobile Device Management, MDM) für Windows-PCs inklusive Windows 10-Geräte mit Microsoft Intune."
keywords: 
author: staciebarker
manager: stabar
ms.date: 11/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6adfb7375f9747f64e7037164f48918789bd7ee0
ms.openlocfilehash: 7c518c176e315cbf005b2fceb8d74de09bdcfa98


---

# <a name="set-up-windows-device-management"></a>Einrichten der Windows-Geräteverwaltung

Als Intune-Administrator können Sie die Registrierung und die Verwaltung für Windows-PCs auf zwei Arten aktivieren:

- **[Automatische Registrierung mit Azure Active Directory](#azure-active-directory-enrollment)**: Windows 10- und Windows 10 Mobile-Benutzer registrieren ihre Geräte, indem Sie dem Gerät ein Geschäfts-, Schul- oder Unikonto hinzufügen.
- **[Unternehmensportal-Registrierung](#company-portal-app-enrollment)**: Benutzer von Windows 8.1 und höher registrieren ihre Geräte durch das Herunterladen und Installieren der Unternehmensportal-App und die anschließende Eingabe der Anmeldeinformationen des Geschäfts-, Schul- oder Unikontos in der App.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-company-portal-app-enrollment"></a>Einrichten der Registrierung der Unternehmensportal-App
Sie können Benutzern erlauben, ihre Geräte mithilfe der Intune-Unternehmensportal-App zu installieren und zu registrieren. Wenn Sie DNS-CNAME-Ressourceneinträge erstellen, können Benutzer sich mit Intune verbinden und dort registrieren, ohne einen Servernamen eingeben zu müssen.

1. **Einrichten von Intune**<br>
Wenn nicht bereits geschehen, bereiten Sie die Verwaltung mobiler Geräte durch [Festlegen der Autorität für die Verwaltung mobiler Geräte (mobile device management, MDM)](prerequisites-for-enrollment.md#step-2-set-mdm-authority) auf **Microsoft Intune** und durch anschließendes Einrichten von MDM vor.

2. **Erstellen von CNAME-Einträgen** (optional)<br>Erstellen Sie **CNAME**-DNS-Ressourceneinträge für die Domäne des Unternehmens. Wenn der Name Ihrer Unternehmenswebsite beispielsweise „contoso.com“ lautet, erstellen Sie einen CNAME in DNS, der „EnterpriseEnrollment.contoso.com“ an „enterpriseenrollment.manage.microsoft.com“ umleitet.

    Wenn Sie aktuell über einen CNAME-Eintrag im DNS verfügen, der „EnterpriseEnrollment.contoso.com“ auf „manage.microsoft.com“ umleitet, empfehlen wir, ihn durch einen CNAME-Eintrag im DNS zu ersetzen, der „EnterpriseEnrollment.contoso.com“ auf „enterpriseenrollment-s.manage.microsoft.com“ umleitet. Wir empfehlen Ihnen diese Änderung, da der Endpunkt „manage.microsoft.com“ in einem zukünftigen Release nicht mehr verwendet werden kann.

    CNAME-Ressourceneinträge müssen die folgenden Informationen enthalten:

  |TYP|Hostname|Verweist auf|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Stunde|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Stunde|

  `EnterpriseEnrollment-s.manage.microsoft.com` – unterstützt eine Umleitung zum Intune-Dienst mit Domänenerkennung anhand des E-Mail-Domänennamens.

  `EnterpriseRegistration.windows.net` – unterstützt Windows 8.1- und Windows 10 Mobile-Geräte, die über das Geschäfts-, Schul- oder Unikonto bei Azure Active Directory registriert werden.

  Wenn Ihr Unternehmen mehrere Domänen für die Anmeldeinformationen der Benutzer verwendet, erstellen Sie CNAME-Einträge für jede Domäne.

  Wenn der Name Ihrer Unternehmenswebsite beispielsweise contoso.com lautet, erstellen Sie einen CNAME in DNS, der EnterpriseEnrollment.contoso.com an EnterpriseEnrollment-s.manage.microsoft.com umleitet. Es kann bis zu 72 Stunden dauern, bis Änderungen an DNS-Einträgen vollständig verteilt sind. Sie können die DNS-Änderung in Intune erst überprüfen, wenn der DNS-Eintrag verteilt ist.

3.  **Überprüfen von CNAME**<br>Wählen Sie in der [Intune-Verwaltungskonsole](http://manage.microsoft.com) **Admin** &gt; **Verwaltung mobiler Geräte** &gt; **Windows** aus. Geben Sie die URL der überprüften Domäne der Unternehmenswebsite in das Feld **Verifizierten Domänennamen eingeben** ein, und wählen Sie anschließend **Automatische Erkennung testen** aus.

  ![Dialogfeld „Windows-Geräteverwaltung“](../media/enroll-intune-winenr.png)

4.  **Optionale Schritte**<br>Der Schritt **Hinzufügen von Sideload-Schlüsseln** wird für Windows 10 nicht benötigt. Der Schritt **Codesignaturzertifikat hochladen** wird nur benötigt, wenn Sie branchenspezifische Apps für Geräte verteilen, die nicht im Windows Store verfügbar sind.

6.  **Benutzern erklären, wie sie ihre Geräte registrieren können, und sie darüber informieren, was sie erwarten können, wenn ihre Geräte verwaltet werden.**

    Registrierungsanleitungen für Endbenutzer finden Sie unter [Registrieren Ihres Windows-Geräts bei Intune](../enduser/enroll-your-device-in-intune-windows.md).

    Weitere Informationen zu Endbenutzeraufgaben finden Sie unter den folgenden Links:
      - [Ressourcen zu Endbenutzerszenarios in Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
      - [Endbenutzer-Leitfaden für Windows-Geräte](../enduser/using-your-windows-device-with-intune.md)

### <a name="see-also"></a>Weitere Informationen:
[Voraussetzungen für die Registrierung von Geräten in Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Dec16_HO2-->


