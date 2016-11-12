---
title: "Voraussetzungen für MAM-Richtlinien | Microsoft Intune"
description: "Dieses Thema beschreibt die erforderlichen Voraussetzungen und Schritte zur Einrichtung von Benutzern, bevor Sie Verwaltungsrichtlinien für mobile Apps erstellen können."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5778ccc632b72b3cca2593febeccbf7149591275
ms.openlocfilehash: 6d7843286369e2371ea204ac70d2e85e4c086d76


---

# Vorbereiten der Konfiguration von Verwaltungsrichtlinien für mobile Apps im Azure-Portal
In diesem Thema beschreibt die Voraussetzungen und die Schritte, die Sie ausführen müssen, **bevor** Sie im Azure-Portal Richtlinien für die Verwaltung von mobilen Apps (MAM, Mobile App Management) erstellen können.

Um zu verstehen, wie MAM-Richtlinien in Intune Ihre Unternehmensdaten schützen kann, gehen Sie unter [Schützen von Apps und Daten mit Microsoft Intune](protect-apps-and-data-with-microsoft-intune.md).

## Was ist das Azure-Portal?
Das Azure-Portal stellt die neue Verwaltungskonsole zum Erstellen von MAM-Richtlinien dar und unterstützt die folgenden MAM-Szenarios:
- **Geräte, die bei Intune registriert sind**
- **Geräte, die mithilfe einer anderen MDM-Lösung verwaltet werden**
- **Geräte, die nicht durch eine MDM-Lösung verwaltet werden (BYOD)**


Derzeit können Sie sowohl mit der **Intune-Verwaltungskonsole** als auch mit dem **Azure-Portal** MAM-Richtlinien konfigurieren.  Beachten Sie Folgendes:

* Die Richtlinien, die Sie im **Azure-Portal** erstellen, werden für alle oben aufgelisteten **MAM-Szenarios** unterstützt. Die **Intune-Verwaltungskonsole** unterstützt nur das Erstellen von Richtlinien für **Geräte, die durch Intune registriert und verwaltet sind**.
* Möglicherweise werden nicht alle Einstellungen der MAM-Richtlinie in der Intune-Verwaltungskonsole angezeigt, dar **neue Einstellungen** möglicherweise nur dem **Azure-Portal** hinzugefügt werden.
* Wenn Sie sowohl in der Intune-Verwaltungskonsole **als auch** im Azure-Portal MAM-Richtlinien erstellen, wird die im **Azure-Portal erstellte Richtlinie auf die Apps angewendet und für die Benutzer bereitgestellt**.
    * MAM-Richtlinien, die in der Intune-Verwaltungskonsole erstellt wurden, können nicht in das Azure-Portal importiert werden.  Die MAM-Richtlinien müssen im Azure-Portal neu erstellt werden.
* Andere **App-Verwaltungsfunktionen**, wie das Bereitstellen von Apps sowie Richtlinien für die App-Konfiguration, sind derzeit nur in der **Intune-Verwaltungskonsole** verfügbar.


Wenn Sie noch keine Erfahrungen mit dem Azure-Portal haben, sollten Sie sich im Artikel [Azure-Portal für MAM-Richtlinien in Microsoft Intune](azure-portal-for-microsoft-intune-mam-policies.md) einen kurzen Überblick über die Grundlagen zur Verwendung des Azure-Portals verschaffen.

Anweisungen zum Erstellen einer MAM-Richtlinie in der Intune-Verwaltungskonsole finden Sie unter [Konfigurieren und Bereitstellen von Verwaltungsrichtlinien für mobile Anwendungen in der Microsoft Intune-Konsole](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).


##  Unterstützte Plattformen
- iOS 8.1 oder höher

- Android 4 oder höher

>[!NOTE]
>Windows-Geräte unterstützen diese Verwaltungsrichtlinien für mobile Anwendungen nicht. Wenn Sie jedoch Windows 10-Geräte mit Intune registrieren, können Sie Windows Information Protection verwenden, das ähnliche Funktionen bietet. Weitere Informationen finden Sie unter [Schutz von Unternehmensdaten mit Windows Information Protection (WIP)](https://technet.microsoft.com/en-us/itpro/windows/keep-secure/protect-enterprise-data-using-wip).

##  Unterstützte Apps
* **Microsoft-Apps**: Bei diesen Apps ist das Intune App SDK integriert, und vor der Anwendung von MAM-Richtlinien sind keine weiteren Schritte nötig.
Die vollständige Liste der unterstützten Microsoft-Apps finden Sie in der [Microsoft Intune mobile application gallery](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) (Microsoft Intune-Katalog für mobile Anwendungen) auf der Seite für Microsoft Intune-Anwendungspartner. Klicken Sie auf eine App, um die unterstützten Szenarien und Plattformen anzuzeigen und zu erfahren, ob die App mehrere Identitäten unterstützt.
* **Branchenspezifische Apps Ihrer Organisation**: Diese Apps müssen vorbereitet werden. Bevor Sie MAM-Richtlinien auf sie anwenden können, müssen Sie das Intune App SDK in die Apps integrieren.

  * Für Geräte, die mit Intune verwaltet werden, lesen Sie die Informationen unter [Auswählen der Vorbereitung von Apps für MAM](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).
  * Für nicht verwaltete Geräte, z.B. für Geräte im Besitz der Mitarbeiter, oder für Geräte, die über eine andere Lösung für mobile Geräte verwaltet werden, lesen Sie die Informationen unter [Schützen von branchenspezifischen Apps und Daten auf nicht in Intune registrierten Geräten](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

## Voraussetzungen

-   Ein Microsoft Intune-Abonnement.    Benutzer benötigen [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Lizenzen, um Apps mit MAM-Richtlinien erhalten zu können.
Sie verfügen bereits über ein [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Abonnement, wenn Sie zurzeit [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] zum Verwalten Ihrer Geräte verwenden.  Sie sind ebenfalls im Besitz eines [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Abonnements, wenn Sie eine EMS-Lizenz (Enterprise Mobility Suite) erworben haben. Wenn Sie [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] testen, um die MAM-Fähigkeiten kennenzulernen, können Sie auf der [Microsoft Intune-Webseite](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/) ein Testkonto erhalten.

    Um zu überprüfen, ob Sie über ein [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Abonnement verfügen, navigieren Sie im Office-Portal zur Seite **Abrechnung**.  In den Abonnements sollte [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] als **Aktiv** angezeigt werden.

-   Ein Office 365-Abonnement, das für Folgendes erforderlich ist:
  - Anwenden von MAM-Richtlinien auf Apps, die mehrere Identitäten unterstützen.
  - Erstellen von SharePoint Online- und Exchange Online-Arbeitskonten. Lokale Exchange- und SharePoint-Bereitstellungen werden nicht unterstützt.
-   Einrichten von Skype for Business Online für die moderne Authentifizierung. Weitere Informationen finden Sie unter [Aktivieren der modernen Authentifizierung](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).


- Azure Active Directory (Azure AD) zum Erstellen von Benutzern. Azure AD authentifiziert Benutzer, wenn diese die App starten und ihre geschäftlichen Anmeldeinformationen eingeben.

    > [!NOTE]
    > Benutzergruppen müssen in Azure AD eingerichtet werden. Intune-Benutzergruppen können nicht zum Bereitstellen von MAM-Richtlinien im Azure-Portal verwendet werden.

### Erstellen von Benutzern und Zuweisen von Microsoft Intune-Lizenzen

1.  Melden Sie sich mit Ihren Administratoranmeldeinformationen beim [Office-Portal](http://portal.office.com) an.

2.  Fügen Sie Benutzer hinzu, so wie im Abschnitt **Hinzufügen von Benutzern** in [diesem](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-2) Thema beschrieben, und weisen Sie Intune-Lizenzen zu. Um einem Benutzer Zugriff auf das Office-Portal, das Azure AD-Portal und das Azure-Portal zu gewähren, weisen Sie dem Benutzer die Rolle **Globaler Administrator** zu.

5.  MAM-Richtlinien werden für Benutzergruppen in Azure Active Directory bereitgestellt. Um Benutzergruppen für Ihre MAM-Richtlinien zu erstellen, erstellen Sie eine Benutzergruppe, so wie im Abschnitt **Erstellen einer Benutzergruppe** in [diesem](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-3) Thema beschrieben.

### Nichtglobale Administratorbenutzer

Globale Administratoren haben Zugriff auf das [Azure-Portal](https://portal.azure.com).  Wenn Sie möchten, dass Benutzer, die nichtglobale Administratoren darstellen, in der Lage sind, Richtlinien zu konfigurieren und andere Verwaltungsaufgaben für mobile Apps auszuführen, können Sie den jeweiligen Benutzern die Rolle „Mitwirkender“ zuweisen. Weitere Informationen finden Sie unter [Verwenden von Rollenzuweisungen zum Verwalten Ihrer Azure-Abonnementressourcen](https://azure.microsoft.com/en-us/documentation/articles/role-based-access-control-configure/).

---------------------------------

In der folgenden Tabelle werden die Rollen und Berechtigungen aufgelistet, die Sie Administratoren zuweisen können.

|||
|--|----|
|**Rolle**|**Berechtigungen**|
|Globaler Administrator (Office 365-Portal)|Zugriff auf das Office 365-Portal und das Azure AD-Portal.<br /><br />Zugriff auf das Azure-Portal (damit können sowohl Rollenverwaltungs- als auch Verwaltungsaufgaben für mobile Apps ausgeführt werden).|
|Besitzer (Azure-Portal)|Zugriff auf das Azure-Portal (damit können sowohl Rollenverwaltungs- als auch Verwaltungsaufgaben für mobile Apps ausgeführt werden).|
|Mitwirkender (Azure-Portal)|Zugriff auf das Azure-Portal (damit können nur Verwaltungsaufgaben für mobile Apps ausgeführt werden).|




## Nächste Schritte
[Erstellen und Bereitstellen von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


