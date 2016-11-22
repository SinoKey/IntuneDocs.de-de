---
title: "Einrichten der Windows 10 Mobile- und Windows Phone-Verwaltung | Microsoft Intune"
description: "Aktivieren Sie die Verwaltung mobiler Geräte (Mobile Device Management, MDM) für Windows 10 Mobile- oder Windows Phone-Geräte mit Microsoft Intune."
keywords: 
author: staciebarker
manager: angrobe
ms.date: 11/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9d44a6494bed0758b9768045bd204ea0eb481636
ms.openlocfilehash: 66d533d094a12239ca4ed1a30f9ce3a06e5cece1


---


# <a name="set-up-windows-phone-and-windows-10-mobile-management-with-microsoft-intune"></a>Einrichten der Windows 10 Mobile- und Windows Phone-Verwaltung mit Microsoft Intune

Als Intune-Administrator können Sie die Registrierung und die Verwaltung für Windows 10 Mobile- und Windows Phone-Geräte auf zwei Arten aktivieren:

- **[Automatische Registrierung mit Azure Active Directory](#azure-active-directory-enrollment)**: Windows 10- und Windows 10 Mobile-Benutzer registrieren ihre Geräte, indem Sie dem Gerät ein Geschäfts-, Schul- oder Unikonto hinzufügen.
- **[Unternehmensportal-Registrierung](#company-portal-app-enrollment)**: Benutzer von Windows Phone 8.1 und höher registrieren ihre Geräte durch das Herunterladen und Installieren der Unternehmensportal-App und die anschließende Eingabe der Anmeldeinformationen des Geschäfts-, Schul- oder Unikontos in der App.


[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="company-portal-app-enrollment"></a>Registrierung der Unternehmensportal-App
Sie können Benutzern erlauben, ihre Geräte mithilfe der Intune-Unternehmensportal-App zu installieren und zu registrieren. Wenn Sie DNS-CNAME-Ressourceneinträge erstellen, können Benutzer sich mit Intune verbinden und dort registrieren, ohne einen Servernamen eingeben zu müssen.

1.  **Einrichten von Intune**<br>Wenn nicht bereits geschehen, bereiten Sie die Verwaltung mobiler Geräte durch [Festlegen der Autorität für die Verwaltung mobiler Geräte (mobile device management, MDM)](prerequisites-for-enrollment.md#set-mobile-device-management-authority) auf **Microsoft Intune** und durch anschließendes Einrichten von MDM vor.

2.  **Erstellen von CNAME-Einträgen** (optional)<br>Erstellen Sie **CNAME**-DNS-Ressourceneinträge für die Domäne des Unternehmens. Wenn der Name Ihrer Unternehmenswebsite beispielsweise „contoso.com“ lautet, erstellen Sie einen CNAME-Eintrag im DNS, der „EnterpriseEnrollment.contoso.com“ auf „enterpriseenrollment-s.manage.microsoft.com“ umleitet. 

    Wenn Sie aktuell über einen CNAME-Eintrag im DNS verfügen, der „EnterpriseEnrollment.contoso.com“ auf „manage.microsoft.com“ umleitet, empfehlen wir, ihn durch einen CNAME-Eintrag im DNS zu ersetzen, der „EnterpriseEnrollment.contoso.com“ auf „enterpriseenrollment-s.manage.microsoft.com“ umleitet. Wir empfehlen Ihnen diese Änderung, da der Endpunkt „manage.microsoft.com“ in einem zukünftigen Release nicht mehr verwendet werden kann.

    Existieren mehrere überprüfte Domänen, erstellen Sie einen CNAME-Eintrag für jede Domäne. Die CNAME-Ressourceneinträge müssen die folgenden Informationen enthalten:

  |TYP|Hostname|Verweist auf|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Stunde|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Stunde|

  `EnterpriseEnrollment-s.manage.microsoft.com` – unterstützt eine Umleitung zum Intune-Dienst mit Domänenerkennung anhand des E-Mail-Domänennamens.

  `EnterpriseRegistration.windows.net` – unterstützt Windows 8.1- und Windows 10 Mobile-Geräte, die über das Geschäfts-, Schul- oder Unikonto bei Azure Active Directory registriert werden.

  Wenn Ihr Unternehmen mehrere Domänen für die Anmeldeinformationen der Benutzer verwendet, erstellen Sie CNAME-Einträge für jede Domäne.

  Wenn der Name Ihrer Unternehmenswebsite beispielsweise contoso.com lautet, erstellen Sie einen CNAME in DNS, der EnterpriseEnrollment.contoso.com an EnterpriseEnrollment-s.manage.microsoft.com umleitet. Es kann bis zu 72 Stunden dauern, bis Änderungen an DNS-Einträgen vollständig verteilt sind. Sie können die DNS-Änderung in Intune erst überprüfen, wenn der DNS-Eintrag verteilt ist.

3.  **Überprüfen von CNAME**<br>Wählen Sie in der [Intune-Verwaltungskonsole](http://manage.microsoft.com) **Verwaltung** &gt; **Verwaltung mobiler Geräte** &gt; **Windows Phone** aus. Geben Sie die URL der überprüften Domäne der Unternehmenswebsite in das Feld **Verifizierten Domänennamen eingeben** ein, und wählen Sie anschließend **Automatische Erkennung testen** aus.

    ![Dialogfeld „Verwaltung mobiler Geräte für Windows einrichten“](../media/windows-phone-enrollment.png)

4.  **Optionale Schritte**<br>Der Schritt **Hinzufügen von Sideload-Schlüsseln** wird für Windows 10 nicht benötigt. Der Schritt **Codesignaturzertifikat hochladen** wird nur benötigt, wenn Sie branchenspezifische Apps, die nicht im Windows Store verfügbar sind, für Geräte verteilen.

5.  **Benutzern erklären, wie sie ihre Geräte registrieren, um auf Unternehmensressourcen zugreifen zu können.**

    Registrierungsanleitungen für Endbenutzer finden Sie unter [Registrieren Ihres Windows-Geräts bei Intune](../enduser/enroll-your-device-in-intune-windows.md). Sie können Benutzer auch auf den Artikel [Was kann Ihr IT-Administrator sehen, wenn Sie Ihr Gerät bei Intune registrieren?](../enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows) verweisen.

    Informationen zu anderen Endbenutzeraufgaben finden Sie in den folgenden Artikeln:
    - [Informieren der Endbenutzer über den Einsatz von Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Endbenutzer-Leitfaden für Windows-Geräte](../enduser/using-your-windows-device-with-intune.md)

Es sind keine weiteren Schritte erforderlich, es sei denn, Sie stellen das Unternehmensportal selbst auf Geräten bereit.  Die Schritte 2 und 3 in der Verwaltungskonsole können ignoriert werden.



<!--HONumber=Nov16_HO2-->


