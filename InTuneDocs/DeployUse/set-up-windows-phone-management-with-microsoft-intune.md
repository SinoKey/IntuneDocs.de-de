---
title: Einrichten der Windows 10 Mobile und Windows Phone-Verwaltung mit Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 61e9b6c3-8795-49b0-8ab2-a9a05ee3ea1f
author: NathBarn
---

## Einrichten der Windows Phone und Windows 10 Mobile-Verwaltung mit Microsoft Intune
Bevor Sie mit Windows 10 Mobile oder Windows Phone-Geräte verwalten können [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], müssen Sie die Einrichtung der Verwaltung. Wenn Sie Windows Phone 8.0-Geräte zu verwalten oder das Unternehmensportal auf Geräten bereitstellen müssen, finden Sie unter [Einrichten von Windows Phone 8.0-Management](set-up-windows-8.0-management-with-microsoft-intune.md).

## Einrichten der Verwaltung von Windows 10 Mobile und Windows Phone  
1.  **Einrichten von Intune**
    Wenn Sie noch nicht geschehen, Vorbereiten für die Verwaltung mobiler Geräte durch  [Festlegen der Verwaltungsautorität für mobile Geräte](https://technet.microsoft.com/library/mt346013.aspx) als **Microsoft Intune** und Einrichten von Mdm.

2.  **Festlegen eines DNS-Alias für die Adresse des Registrierungsservers** (optional)

    Erstellen einer DNS-erleichtert Alias (CNAME-Eintragstyp) für Benutzer ihre Geräte registrieren. Wenn Sie einen DNS-Alias erstellen möchten, müssen Benutzer

    1.  Erstellen Sie **CNAME** DNS-Ressourceneinträge für die Domäne des Unternehmens. Die CNAME-Ressourceneinträge müssen die folgenden Informationen enthalten:

|TYP|Hostname|Verweist auf|TTL|
|--------|-------------|-------------|-------|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Stunde|
|CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Stunde|

    For example, if your company’s website is contoso.com, you would create a CNAME in DNS that redirects EnterpriseEnrollment.contoso.com to manage.microsoft.com. If there is more than one verified domain, create a CNAME record for each domain.

      -   `manage.microsoft.com` – Supports a redirect to the Intune service with domain recognition from the email’s domain name

      -   `enterpriseregistration.windows.net` – Supports workplace join for mobile devices. It also supports conditional access for Windows 8.1

    2.  In the [Intune administration console](http://manage.microsoft.com), click **Administration** &gt; **Mobile Device Management** &gt; **Windows Phone**.

    3.  Type the URL of the verified domain of the company website in the **Specify a verified domain name** box and then click **Test Auto-Detection**.



![](../media/Windows-Device-Enrollment.png)

    No additional work is required unless you will deploy the Company Portal to devices.  Steps 2, 3 and 4 in the admin console can be safely ignored.

### Weitere Informationen:
[Vorbereiten der Registrierung von Geräten in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=Mar16_HO3-->


