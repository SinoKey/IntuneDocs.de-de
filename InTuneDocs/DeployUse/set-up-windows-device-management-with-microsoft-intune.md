---
title: "Einrichten der Windows-Geräteverwaltung mit Microsoft Intune | Microsoft Intune"
description: "Aktivieren Sie die Verwaltung mobiler Geräte (Mobile Device Management, MDM) für Windows-PCs inklusive Windows 10-Geräte mit Microsoft Intune."
keywords: 
author: NathBarn
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
ms.sourcegitcommit: ebb1648ab13d31a2ba1ab17615814be8dda8a08c
ms.openlocfilehash: 9b063c1e6b1ff5dcab16fce958ede49303284b18


---

# Einrichten der Windows-Geräteverwaltung

Als Intune-Administrator können Sie die Registrierung und die Verwaltung für Windows PCs auf zwei Arten aktivieren:

- **[Automatische Registrierung mit Azure AD](#azure-active-directory-enrollment)** – Windows 10- und Windows 10 Mobile-Benutzer registrieren ihre Geräte, indem Sie dem Gerät ein Geschäfts- oder Schulkonto hinzufügen.
- **[Unternehmensportal-Registrierung](#company-portal-app-enrollment)** – Windows 8.1-Geräte und neuere Geräte werden durch das Herunterladen und Installieren der Unternehmensportal-App registriert und anschließend durch die Eingabe der Anmeldeinformationen des Geschäfts- oder Schulkontos in der App.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## Konfigurieren der Registrierung der Unternehmensportal-App
Sie können Benutzern erlauben, ihre Geräte durch Installieren und Registrieren mit der Intune-Unternehmensportal-App zu registrieren. Durch das Erstellen eines DNS-CNAME-Eintrags können Benutzer sich mit Intune verbinden und dort registrieren, ohne einen Servernamen eingeben zu müssen.

1. **Einrichten von Intune**<br>
Wenn nicht bereits geschehen, bereiten Sie die Verwaltung mobiler Geräte durch [Festlegen der Autorität für die Verwaltung mobiler Geräte](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) auf **Microsoft Intune** und Einrichten von MDM vor.

2. **Erstellen Sie einen oder mehrere CNAME-Einträge** (optional)<br>Erstellen Sie **CNAME**-DNS-Ressourceneinträge für die Domäne des Unternehmens, um die Registrierung zu vereinfachen. Obwohl die Erstellung von CNAME DNS-Einträgen optional ist, vereinfacht die Erstellung von CNAME-Datensätzen die Registrierung für Benutzer. Wenn kein CNAME-Eintrag für die Registrierung gefunden wurde, werden Benutzer dazu aufgefordert, manuell den MDM-Servernamen, `https://manage.microsoft.com`, einzugeben.  Die CNAME-Ressourceneinträge müssen die folgenden Informationen enthalten:

  |TYP|Hostname|Verweist auf|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Stunde|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Stunde|

  `EnterpriseEnrollment-s.manage.microsoft.com` – Unterstützt eine Umleitung zum Intune-Dienst mit Domänenerkennung anhand des E-Mail-Domänennamens

  `EnterpriseRegistration.windows.net` – Unterstützt Windows 8.1- und Windows 10 Mobile- Geräte, die über das Geschäfts- oder Schulkonto bei Azure Active Directory registriert werden.

  Wenn Ihr Unternehmen mehrere Domänen für die Anmeldeinformationen der Benutzer verwendet, erstellen Sie CNAME-Einträge für jede Domäne.

  Wenn der Name Ihrer Unternehmenswebsite beispielsweise contoso.com lautet, erstellen Sie einen CNAME in DNS, der EnterpriseEnrollment.contoso.com an EnterpriseEnrollment-s.manage.microsoft.com umleitet. Es kann bis zu 72 Stunden dauern, bis Änderungen an DNS-Einträgen vollständig verteilt sind. Sie können die DNS-Änderung in Intune erst überprüfen, wenn der DNS-Eintrag verteilt ist.

3.  **CNAME überprüfen**<br>Klicken Sie in der [Intune-Verwaltungskonsole](http://manage.microsoft.com) auf **Verwaltung** &gt; **Verwaltung mobiler Geräte** &gt; **Windows**. Geben Sie die URL der überprüften Domäne der Unternehmenswebsite in das Feld **Verifizierten Domänennamen eingeben** ein, und klicken Sie dann auf **Automatische Erkennung testen**.

  ![Dialogfeld „Windows-Geräteverwaltung“](../media/enroll-intune-winenr.png)

4.  **Optionale Schritte**<br>Der Schritt **Hinzufügen von Sideload-Schlüsseln** wird für Windows 10 nicht benötigt. Der Schritt **Codesignaturzertifikat hochladen** wird nur benötigt, wenn Sie branchenspezifische Apps für Geräte verteilen, die nicht im Windows Store verfügbar sind. [Erfahren Sie mehr](set-up-windows-phone-8.0-management-with-microsoft-intune.md)

6.  **Informieren von Benutzern**<br>Sie müssen Ihren Benutzern mitteilen, wie sie ihre Geräte registrieren können und was sie erwartet, wenn die Geräte in die Verwaltung eingebunden sind.
      - [Informieren der Endbenutzer über den Einsatz von Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
      - [Endbenutzer-Leitfaden für Windows-Geräte](../enduser/using-your-windows-device-with-intune.md)

### Weitere Informationen:
[Vorbereiten der Registrierung von Geräten in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Aug16_HO5-->


