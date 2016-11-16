---
title: "Einrichten der Windows-Geräteverwaltung mit Microsoft Intune | Microsoft Intune"
description: "Aktivieren Sie die Verwaltung mobiler Geräte (Mobile Device Management, MDM) für Windows-PCs inklusive Windows 10-Geräte mit Microsoft Intune."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: dfc5241376033471a232b059ac07fa4488f05514
ms.openlocfilehash: c405408bd6a1e2b0743566e413436aefbaa7018b


---

# Einrichten der Windows-Geräteverwaltung

Als Intune-Administrator können Sie die Registrierung und die Verwaltung für Windows-PCs auf zwei Arten aktivieren:

- **[Automatische Registrierung mit Azure Active Directory](#azure-active-directory-enrollment)**: Windows 10- und Windows 10 Mobile-Benutzer registrieren ihre Geräte, indem Sie dem Gerät ein Geschäfts-, Schul- oder Unikonto hinzufügen.
- **[Unternehmensportal-Registrierung](#company-portal-app-enrollment)**: Benutzer von Windows 8.1 und höher registrieren ihre Geräte durch das Herunterladen und Installieren der Unternehmensportal-App und die anschließende Eingabe der Anmeldeinformationen des Geschäfts-, Schul- oder Unikontos in der App.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## Einrichten der Registrierung der Unternehmensportal-App
Sie können Benutzern erlauben, ihre Geräte mithilfe der Intune-Unternehmensportal-App zu installieren und zu registrieren. Wenn Sie DNS-CNAME-Ressourceneinträge erstellen, können Benutzer sich mit Intune verbinden und dort registrieren, ohne einen Servernamen eingeben zu müssen.

1. **Einrichten von Intune**<br>
Wenn nicht bereits geschehen, bereiten Sie die Verwaltung mobiler Geräte durch [Festlegen der Autorität für die Verwaltung mobiler Geräte (mobile device management, MDM)](prerequisites-for-enrollment.md#set-mobile-device-management-authority) auf **Microsoft Intune** und durch anschließendes Einrichten von MDM vor.

2. **Erstellen Sie einen oder mehrere CNAME-Einträge** (optional)<br>Erstellen Sie **CNAME**-DNS-Ressourceneinträge für die Domäne des Unternehmens, um die Registrierung zu vereinfachen. Obwohl die Erstellung von CNAME DNS-Einträgen optional ist, vereinfachen diese die Registrierung für Benutzer. Wenn kein CNAME-Eintrag für die Registrierung gefunden wurde, werden Benutzer dazu aufgefordert, manuell den MDM-Servernamen, `https://manage.microsoft.com`, einzugeben. CNAME-Ressourceneinträge müssen die folgenden Informationen enthalten:

  |TYP|Hostname|Verweist auf|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Stunde|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Stunde|

  `EnterpriseEnrollment-s.manage.microsoft.com` – Unterstützt eine Umleitung zum Intune-Dienst mit Domänenerkennung anhand des E-Mail-Domänennamens

  `EnterpriseRegistration.windows.net` – Unterstützt Windows 8.1- und Windows 10 Mobile-Geräte, die über das Geschäfts-, Schul- oder Unikonto bei Azure Active Directory registriert werden.

  Wenn Ihr Unternehmen mehrere Domänen für die Anmeldeinformationen der Benutzer verwendet, erstellen Sie CNAME-Einträge für jede Domäne.

  Wenn der Name Ihrer Unternehmenswebsite beispielsweise contoso.com lautet, erstellen Sie einen CNAME in DNS, der EnterpriseEnrollment.contoso.com an EnterpriseEnrollment-s.manage.microsoft.com umleitet. Es kann bis zu 72 Stunden dauern, bis Änderungen an DNS-Einträgen vollständig verteilt sind. Sie können die DNS-Änderung in Intune erst überprüfen, wenn der DNS-Eintrag verteilt ist.

3.  **CNAME überprüfen**<br>Wählen Sie in der [Intune-Verwaltungskonsole](http://manage.microsoft.com) **Admin** &gt; **Verwaltung mobiler Geräte** &gt; **Windows** aus. Geben Sie die URL der überprüften Domäne der Unternehmenswebsite in das Feld **Verifizierten Domänennamen eingeben** ein, und wählen Sie anschließend **Automatische Erkennung testen** aus.

  ![Dialogfeld „Windows-Geräteverwaltung“](../media/enroll-intune-winenr.png)

4.  **Optionale Schritte**<br>Der Schritt **Hinzufügen von Sideload-Schlüsseln** wird für Windows 10 nicht benötigt. Der Schritt **Codesignaturzertifikat hochladen** wird nur benötigt, wenn Sie branchenspezifische Apps für Geräte verteilen, die nicht im Windows Store verfügbar sind. [Erfahren Sie mehr](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

6.  **Informieren von Benutzern**<br>Sie müssen Ihren Benutzern mitteilen, wie sie ihre Geräte registrieren können und was sie erwartet, nachdem die Geräte in die Verwaltung eingebunden wurden.
      - [Informieren der Endbenutzer über den Einsatz von Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
      - [Endbenutzer-Leitfaden für Windows-Geräte](../enduser/using-your-windows-device-with-intune.md)

### Weitere Informationen:
[Voraussetzungen für die Registrierung von Geräten in Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Oct16_HO3-->


