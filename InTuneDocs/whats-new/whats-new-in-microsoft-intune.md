---
title: Neuheiten | Microsoft-Dokumentation
description: Erfahren Sie, was im Release dieses Monats und in den vergangenen Releases von Microsoft Intune neu ist
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 0dc3fd3b4cc355bc95677ca648efdee07d1066b2
ms.lasthandoff: 04/24/2017


---
# <a name="whats-new-in-microsoft-intune---april-2017"></a>Neuerungen in Microsoft Intune – April 2017
Erfahren Sie, was in diesem Release von Microsoft Intune neu ist. Sie erhalten auch Informationen über bevorstehende Änderungen, die Sie einplanen sollten, sowie über vergangene Releases.

> [!Note]
> Alle diese Features werden letztlich auch für hybride Kundenbereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Neue Funktionen

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Verbesserter Anmeldevorgang für alle Unternehmensportal-Apps auf allen Plattformen <!--User Story 1132123-->

Wir verbessern den Anmeldevorgang für die Intune-Unternehmensportal-Apps für Android, iOS und Windows. Die neue Benutzeroberfläche wird für die Unternehmensportal-App automatisch auf allen Plattformen eingeführt, sobald Azure AD die Änderung umsetzt. Darüber hinaus können Benutzer sich jetzt mithilfe eines generierten Codes zur einmaligen Verwendung von einem anderen Gerät aus beim Unternehmensportal anmelden. Dies ist besonders nützlich, wenn Benutzer sich ohne Anmeldeinformationen anmelden müssen.

Screenshots der vorherigen Anmeldeoberfläche, der neuen Anmeldeoberfläche mit Anmeldeinformationen und der neuen Anmeldeoberfläche zur Anmeldung von einem anderen Gerät aus finden Sie auf der Seite mit den [Neuerungen der App-Benutzeroberfläche](whats-new-in-intune-app-ui.md).

### <a name="myapps-available-for-managed-browser---822308-822303--"></a>MyApps verfügbar für Managed Browser <!--822308, 822303-->

Microsoft MyApps verfügen jetzt über eine bessere Unterstützung innerhalb von Managed Browser. Managed Browser-Benutzer, die nicht für die Verwaltung vorgesehen sind, werden direkt an den MyApps-Dienst weitergeleitet, wo sie auf ihre durch den Administrator bereitgestellte SaaS-Apps zugreifen können. Benutzer, die für die Verwendung für die Intune-Verwaltung ausgelegt sind, können weiterhin auf MyApps vom integrierten Managed Browser-Lesezeichen aus zugreifen.

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431-971473--"></a>Neue Symbole für Managed Browser und das Unternehmensportal <!--918433, 918431, 971473-->

Managed Browser erhält aktualisierte Symbole für die Android- und iOS-Versionen der App. Das neue Symbol enthält den aktualisierten Intune-Badge, damit es konsistenter mit anderen Apps in Enterprise Mobility + Security (EM+S) wird. Sie können das neue Symbol für Managed Browser auf der Seite mit den [Neuerungen der Intune-App-Benutzeroberfläche](whats-new-in-intune-app-ui.md) finden.

Das Unternehmensportal erhält auch aktualisierte Symbole für die Android-, iOS- und Windows-Versionen der App, um die Konsistenz mit anderen Apps in EM+S zu verbessern. Diese Symbole werden von April bis Ende Mai schrittweise auf den Plattformen veröffentlicht.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Statusanzeige zur Anmeldung im Android-Unternehmensportal <!--953374-->

Ein Update auf die Android-Unternehmensportal-App zeigt eine Statusanzeige der Anmeldung an, wenn der Benutzer die App startet oder fortsetzt. Der Indikator durchläuft neue Status, beginnend mit „Verbinden...“, „Anmelden...“, dann „Checking for security requirements...“ (Suche nach Sicherheitsanforderungen...), bevor dem Benutzer erlaubt wird, auf die App zuzugreifen. Screenshots der neuen Bildschirme für die Unternehmensportal-App finden Sie auf der Seite mit den [Neuerungen der Intune-App-Benutzeroberfläche](whats-new-in-intune-app-ui.md).

### <a name="block-apps-from-accessing-sharepoint-online----679339---"></a>Verhindern, dass Apps auf SharePoint Online zugreifen<!-- 679339 -->

Sie können jetzt eine Richtlinie für den App-basierten bedingten Zugriff erstellen, um Apps, auf die keine Schutzrichtlinien angewendet wurden, am Zugriff auf [SharePoint Online](/InTune/deploy-use/mam-ca-for-sharepoint-online) zu hindern. Im Szenario des App-basierten bedingten Zugriffs können Sie Apps festlegen, die über das Azure-Portal auf SharePoint Online zugreifen können sollen.

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Massenregistrierung von Windows 10-Geräten <!-- 747607 -->

Sie können jetzt eine große Anzahl von Geräten, auf denen das Windows 10 Creators Update ausgeführt wird, mit Windows Configuration Designer (WCD) in Azure Active Directory und Intune einbinden. Um die [MDM-Massenregistrierung](/intune/deploy-use/bulk-enroll-windows) für Ihren Azure AD-Mandanten zu aktivieren, erstellen Sie ein Bereitstellungspaket, das Geräte mithilfe von Windows Configuration Designer in Ihren Azure AD-Mandanten einbindet. Sie können das Paket auf alle unternehmenseigenen Geräte anwenden, die Sie per Massenvorgang registrieren und verwalten möchten. Nachdem das Paket auf Ihre Geräte angewendet wurde, werden die Geräte in Azure AD eingebunden und bei Intune registriert und sind dann bereit für die Anmeldung durch Ihre Azure AD-Benutzer.  Azure AD-Benutzer sind auf diesen Geräten Standardbenutzer und erhalten zugewiesene Richtlinien sowie erforderliche Apps. Die Verwendung von Self-Service-Funktionen und Unternehmensportalen wird derzeit nicht unterstützt.

## <a name="notices"></a>Benachrichtigungen

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Direkter Zugriff auf Apple-Registrierungsszenarien <!--951869-->

Für Intune-Konten, die nach Januar 2017 erstellt wurden, hat Intune direkten Zugriff auf Apple-Registrierungsszenarien mithilfe der Workload „Geräte registrieren“ im Azure-Vorschauportal aktiviert. Bisher konnte nur über Links im klassischen Intune-Portal auf die Apple-Registrierungsvorschau zugegriffen werden. Vor Januar 2017 erstellte Intune-Konten erfordern eine einmalige Migration, bevor diese Features in Azure verfügbar sind. Der Zeitplan für die Migration wurde noch nicht angekündigt, aber Sie erfahren so bald wie möglich Näheres. Wir empfehlen Ihnen dringend, ein Testkonto zu erstellen, um die neue Oberfläche zu testen, wenn Sie mit Ihrem vorhandenen Konto nicht auf die Vorschau zugreifen können.

### <a name="whats-coming-for-appx-in-intune-on-azure----1000270---"></a>Was für APPX in Intune unter Azure bereitsteht <!-- 1000270 -->

Als Teil der Migration zu Intune unter Azure werden wir drei APPX-Änderungen vornehmen:

1. Einen neuen APPX-App-Typ in der klassischen Intune-Verwaltungskonsole hinzufügen, der nur für MDM-registrierte Geräte bereitgestellt werden kann
2. Den vorhandenen APPX-App-Typ nur für PCs wiederverwenden, die über den Intune PC-Agent verwaltet werden
3. Alle vorhandenen APPX-Formate in MDM-Formate mit der Migration konvertieren

#### <a name="how-does-this-affect-me"></a>Inwiefern betrifft das mich?

Diese Änderungen werden keine Ihrer vorhandenen Bereitstellungen auf Geräte beeinflussen, die über den Intune PC-Agent verwaltet werden. Nach der Migration können Sie diese migrierten APPX-Formate auf allen neuen Geräten bereitstellen, die über den Intune PC-Agent verwaltet wird und die zuvor noch nicht zugewiesen wurden.

#### <a name="what-action-do-i-need-to-take"></a>Was muss ich tun?

Nach der Migration müssen Sie die APPX erneut als PC-APPX hochladen, wenn Sie neue PC-Bereitstellungen machen möchten. Weitere Informationen finden Sie unter [Appx changes in Intune on Azure (APPX-Änderungen in Intune unter Azure)](https://aka.ms/appxchange) im Intune-Support-Teamblog.  


## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Neuigkeiten in der öffentlichen Vorschau der neuen Intune-Administratoroberfläche auf Azure <!--736542-->

Anfang 2017 erfolgt die Migration der gesamten Administratoroberfläche zu Azure. Dies ermöglicht die leistungsstarke und integrierte Verwaltung von EMS-Kernworkflows in einer modernen, mit Grafik-APIs erweiterbaren Dienstplattform.

Neue Testmandanten sehen die öffentliche Vorschau der neuen Administratoroberfläche im Azure-Portal bereits in diesem Monat. Die Umgebung ist zwar noch in der Previewphase, schrittweise werden aber Funktionen und Parität zur vorhandenen Intune-Konsole bereitgestellt.

Die Administratoroberfläche im Azure-Portal verwendet die bereits angekündigten neuen Gruppierungs- und Zielgruppenadressierungsfunktionen. Bei der Migration eines vorhandenen Mandanten zur neuen Gruppierungsoberfläche erfolgt gleichzeitig die Migration zur Vorschau der neuen Administratoroberfläche auf Ihrem Mandanten. Wenn Sie in der Zwischenzeit bis zur Migration Ihres Mandanten einzelne neue Funktionen testen oder anschauen möchten, melden Sie sich für ein neues Intune-Testkonto an, oder sehen Sie sich die [neue Dokumentation](/intune-azure/introduction/whats-new) an.

> [!Note]
> Wir veröffentlichen gerade die aktuellen Monatsupdates für die Vorschau des Azure-Portals. Aufgrund der Rolloutmethode des Intune-Diensts stehen die Änderungen jedoch möglicherweise nicht sofort zur Verfügung.  Mehrere Komponenten des Diensts müssen nacheinander aktualisiert werden, damit die neuen Portalfeatures verfügbar werden. Änderungen an der Vorschau des Azure-Portals werden im Laufe des Monats eingeführt. Die Liste mit allen Änderungen finden Sie unter [Neuigkeiten in der Vorschau von Microsoft Intune](/intune-azure/introduction/whats-new).

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Administratorrollen werden im Azure-Portal ersetzt

Die in der Verwaltung mobiler Anwendungen (Mobile Application Management, MAM) vorhandenen Administratorrollen (Mitwirkender, Besitzer und Schreibgeschützt), die im klassischen Intune-Portal (Silverlight) verwendet werden, werden im Intune-Azure-Portal durch einen vollständigen Satz neuer rollenbasierter Zugriffssteuerung (Role-Based Access Control, RBAC) ersetzt. Nach der Migration zum Azure-Portal müssen Sie die Administratoren diesen neuen Administratorrollen neu zuweisen. Weitere Informationen zu RBAC und den neuen Rollen finden Sie unter [Rollenbasierte Zugriffssteuerung für Microsoft Intune](/intune-azure/access-control/role-based-access-control).


## <a name="whats-coming"></a>Was steht an?

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Stellen Sie sich auf eine Änderung ein: Intune ändert die Oberfläche des Intune-Partnerportals <!-- 1050016 -->

Ab dem Dienstupdate Mitte Mai 2017 entfernen wir die Intune-Partnerseite von manage.microsoft.com.  

Wenn Sie ein Partneradministrator sind, können Sie über die Intune-Partnerseite nicht mehr im Namen Ihrer Kunden Elemente anzeigen und Aktionen durchführen. Stattdessen müssen Sie sich bei einer der beiden anderen Partnerportale von Microsoft anmelden.

Sowohl das [Microsoft Partner Center](https://partnercenter.microsoft.com/) als auch das [Microsoft Office 365 Partner Admin Center](https://portal.office.com/) ermöglicht Ihnen das Anmelden bei den von Ihnen verwalteten Kundenkonten. Verwenden Sie als Partner künftig eine dieser Websites für die Verwaltung Ihrer Kunden. 


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple erfordert Updates für die Transportsicherheit für Anwendungen <!--748318-->

Apple hat angekündigt, dass sie ab Frühjahr 2017 bestimmte Anforderungen für die Transportsicherheit für Anwendungen (Application Transport Security, ATS) erzwingen werden. ATS wird verwendet, um eine strengere Sicherheit in allen App-Kommunikationen über HTTPS zu erzwingen. Diese Änderung wirkt sich auf Intune-Kunden aus, die die iOS-Unternehmensportal-App verwenden. Unter [Intune support blog (Intune-Supportblog)](https://aka.ms/compportalats) finden Sie weitere Informationen.

### <a name="see-also"></a>Weitere Informationen:
* [Microsoft Intune-Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap für die Cloudplattform](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Neuigkeiten in der Azure-Vorschau](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [What‘s new in the Intune App UI (Neues auf der Intune-App-Benutzeroberfläche)](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Neuheiten – Archiv](whats-new-archive.md)

