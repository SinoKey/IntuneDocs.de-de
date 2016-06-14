---
# required metadata

title: Einrichten der Windows 10 Mobile- und Windows Phone-Verwaltung mit Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Einrichten der Windows 10 Mobile- und Windows Phone-Verwaltung mit Microsoft Intune
Bevor Sie Windows 10 Mobile- oder Windows Phone-Geräte mit Intune verwalten können, müssen die Geräte mit Intune kommunizieren können. Um dies zu vereinfachen, können Sie einen DNS-Eintrag erstellen. Dann brauchen die Benutzer nicht die Adresse des Servers einzugeben. Die folgenden Schritte beschreiben, wie Sie die Registrierung für die Benutzer vereinfachen.  

In den meisten Fällen können die Benutzer die Unternehmensportal-App aus dem Windows Store installieren. Wenn Sie Windows Phone 8.0-Geräte verwalten oder das Unternehmensportal auf Windows Phone-Geräten bereitstellen müssen, müssen Sie die Unternehmensportal-App zusätzlich herunterladen und signieren. Siehe [Einrichten der Windows Phone 8.0-Verwaltung](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

1.  **Einrichten von Intune** Falls nicht bereits geschehen, bereiten Sie die Verwaltung mobiler Geräte durch [Festlegen der Autorität für die Verwaltung mobiler Geräte](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) auf **Microsoft Intune** vor.

2.  **Festlegen eines DNS-Alias für die Adresse des Registrierungsservers** (optional)

    Durch das Erstellen eines DNS-Alias (Eintragstyp CNAME) erleichtern Sie es den Benutzern, ihre Geräte zu registrieren. Wenn Sie keinen DNS-Alias erstellen, müssen die Benutzer folgende Schritte ausführen:

  1.  Erstellen Sie **CNAME**-DNS-Ressourceneinträge für die Domäne des Unternehmens. Wenn der Name Ihrer Unternehmens-Website beispielsweise contoso.com lautet, erstellen Sie einen CNAME in DNS, von dem EnterpriseEnrollment.contoso.com an manage.microsoft.com umgeleitet wird. Wenn mehr als eine überprüfte Domäne vorhanden ist, erstellen Sie einen CNAME-Eintrag für jede Domäne. Die CNAME-Ressourceneinträge müssen folgende Informationen enthalten:

      |TYP|Hostname|Verweist auf|TTL|
      |--------|-------------|-------------|-------|
      |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Stunde|
      |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Stunde|

      Es kann bis zu 72 Stunden dauern, bis Änderungen an DNS-Einträgen vollständig verteilt sind. Sie können die DNS-Änderung in Intune erst überprüfen, wenn der DNS-Eintrag verteilt ist.

      **EnterpriseEnrollment-s.manage.microsoft.com** – Unterstützt eine Umleitung zum Intune-Dienst mit Domänenerkennung anhand des E-Mail-Domänennamens.

      **EnterpriseRegistration.windows.net** – Unterstützt Windows 8.1- und Windows 10 Mobile-Geräte, die über das jeweilige Geschäfts-, Schul- oder Unikonto bei Azure Active Directory registriert werden.

    2.  Klicken Sie in der [Intune-Verwaltungskonsole](http://manage.microsoft.com) auf **Verwaltung** &gt; **Verwaltung mobiler Geräte** &gt; **Windows Phone**.

      ![Dialogfeld „Verwaltung mobiler Geräte für Windows einrichten“](../media/windows-device-enrollment.png)

    3.  Geben Sie die URL der überprüften Domäne der Unternehmenswebsite in das Feld **Verifizierten Domänennamen eingeben** ein, und klicken Sie dann auf **Automatische Erkennung testen**.



Es sind keine weiteren Schritte erforderlich, es sei denn, Sie stellen das Unternehmensportal selbst auf Geräten bereit.  Die Schritte 2 und 3 in der Verwaltungskonsole können ignoriert werden.


<!--HONumber=May16_HO2-->


