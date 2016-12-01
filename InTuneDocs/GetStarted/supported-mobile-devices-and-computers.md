---
title: "Unterstützte mobile Geräte und Browser | Microsoft Intune"
description: "Von Intune unterstützte mobile Geräte und Computer"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aeeccfa4-0f14-447e-a3df-c8435c8a4bb2
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 149f3a3310907d131affeaad4bd372aa60be9206
ms.openlocfilehash: 80541567c535cfeb7fca3eda3c9143f4b11d7abb


---

# <a name="supported-mobile-devices-and-computers"></a>Unterstützte mobile Geräte und Computer

Sie können die folgenden Gerätetypen registrieren und anschließend verwalten:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Informationen zu den Funktionen, die Ihnen bei der Geräteregistrierung zur Verfügung stehen, finden Sie unter [Auswählen der Methode zum Verwalten von Geräten](/Intune/get-started/choose-how-to-manage-devices).

Alternativ können Sie Windows-PCs mit der Clientsoftware Intune PC verwalten. Die Intune-PC-Clientsoftware unterstützt Windows 7 und höher, mit Ausnahme von Windows 10 Home. Die PC-Verwaltung mit dieser Clientsoftware bietet [diese Möglichkeiten](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

Kunden mit der Enterprise Management Suite können auch Azure Active Directory ( Azure AD) verwenden, um Windows 10-Geräte zu registrieren.

## <a name="microsoft-intune-supported-web-browsers"></a>Von Microsoft Intune unterstützte Webbrowser

Für verschiedene Verwaltungsaufgaben müssen Sie eine der folgenden Verwaltungswebsites verwenden.

- [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Microsoft Intune-Administratorkonsole](https://admin.manage.microsoft.com/)

> [!Note]
> Microsoft Edge und mobile Browser werden für die Administratorkonsole nicht unterstützt, da sie [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx) nicht unterstützen. Für die Intune-Konsole wird in Zukunft nicht mehr Silverlight verwendet, letztlich werden alle Intune-Features zur Verwaltung mobiler Geräte und Anwendungen [im neuen Azure-Portal verfügbar gemacht](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/). Diese Umstellung wird jedoch eine Zeit lang dauern.

|Intune-Feature |Unterstützte Browser|
|---------|---------|
|Intune-Administratorkonsole     |  Internet Explorer 10 oder höher<br /><br />Google Chrome (Versionen vor Version 42)<br /><br />Mozilla Firefox mit aktiviertem Silverlight<br /><br />**Hinweis:** Microsoft Edge und mobile Browser werden für die Administratorkonsole nicht unterstützt.                      
|Office 365-Verwaltungsportal     |Alle Browser, einschließlich mobiler und verwalteter Browser  |
|Unternehmensportal-Website     |**Auf mobilen Geräten:** Verwenden Sie für jede unterstützte Plattform den Standardwebbrowser.   <br /><br />**Auf Windows-PCs:** Internet Explorer 10 oder höher oder Microsoft Edge<br /><br />**Unter Mac OS X 10.9 oder höher:** Apple Safari    |

> [!Note]
> Microsoft Edge und mobile Browser werden für die Administratorkonsole nicht unterstützt, da sie [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx) nicht unterstützen. Für die Intune-Konsole wird in Zukunft nicht mehr Silverlight verwendet, letztlich werden alle Intune-Features zur Verwaltung mobiler Geräte und Anwendungen [im neuen Azure-Portal verfügbar gemacht](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/). Diese Umstellung wird jedoch eine Zeit lang dauern.

### <a name="office-365-portalhttpgomicrosoftcomfwlinkplinkid698854"></a>[Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)

**Als Mandantenadministrator verwenden Sie dieses Portal zum Verwalten Ihres Abonnements.** Dies umfasst die folgenden Aufgaben, sofern sie durch Ihre Administratorrolle zugelassen werden:

- Verwalten von Benutzerkonten für das Abonnement und Konfigurieren der Verzeichnissynchronisierung aus Ihrem lokalen Active Directory
- Verwalten von als „Sicherheitsgruppen“ bezeichneten Gruppen von Benutzern
- Zuweisen von Lizenzen, die Benutzern das Verwenden von Intune ermöglichen.
- Konfigurieren des Domänennamens, den Sie mit Ihrem Abonnement verwenden. Mit dem Domänennamen wird das Konto definiert, mit dem sich Benutzer anmelden.
- Verwalten von Abrechnungs- und Einkaufsdetails für Ihr Abonnement. Dies schließt die Anzahl der Ihnen zur Verfügung stehenden Lizenzen und die Menge des Cloudspeichers ein, den Sie verwenden können.
- Suchen von Links zum Anzeigen der Integrität des Intune-Diensts.
- Als Mandantenadministrator können Sie sich auch dann zur Verwaltung des Abonnements am Office 365-Portal anmelden, wenn Ihrem Konto keine Lizenz für die Nutzung von Intune zugewiesen ist.
- Jeder Benutzer, der über eine Intune-Lizenz verfügt, aber kein Administrator ist, kann über dieses Portal sein Kontokennwort zurücksetzen und sein Profil bearbeiten.
- Für den Zugriff auf das Office 365-Portal ist für Ihr Konto der Anmeldestatus **Zugelassen** erforderlich. Dieser Status unterscheidet sich vom Besitz einer Abonnementlizenz. Standardmäßig haben alle Benutzerkonten den Status **Zugelassen**.


### <a name="microsoft-intune-administrator-consolehttpsmanagemicrosoftcom"></a>[Microsoft Intune-Administratorkonsole](https://manage.microsoft.com/)

**Als Dienstadministrator verwenden Sie dieses Portal für tägliche Aufgaben** wie die folgenden:

- Festlegen von Richtlinien für Computer und mobile Geräte
- Hochladen und Bereitstellen von Software, z. B. Softwareupdates und Apps
- Verwalten von Endpoint Protection auf Computern
- Anzeigen des Gerätestatus und Ausführen von Berichten
- Melden Sie sich bei diesem Portal an. Sie müssen entweder über Dienstadministratorrechte verfügen oder ein Mandantenadministrator mit globaler Administratorrolle sein, damit Sie sich bei diesem Portal anmelden können.


Lediglich Benutzer mit Dienstadministratorrechten oder Mandantenadministratoren mit globaler Administratorrolle können sich bei diesem Portal anmelden. Für den Zugriff auf die Administratorkonsole sind für Ihr Konto eine Lizenz zur Verwendung von Intune und der Anmeldestatus **Zugelassen** erforderlich.



<!--HONumber=Nov16_HO4-->


