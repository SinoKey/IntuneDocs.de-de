---
title: Neuerungen in Microsoft Intune
titlesuffix: Azure portal
description: Erfahren Sie, welche Neuerungen es im Intune-Azure-Portal gibt
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 09/18/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 08a22a1fa6829807860b6278181dd638f1049770
ms.sourcegitcommit: 0d9bfd92bf5958261ed83b1f150bf207b7ba7e56
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Neuerungen in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Erfahren Sie jede Woche, welche Neuerungen Microsoft Intune zu bieten hat. Sie erhalten auch Informationen zu [bevorstehenden Änderungen](#whats-coming), [wichtige Hinweise](#notices) zum Dienst und Informationen zu [vorherigen Versionen](whats-new-archive.md).

> [!Note]
> Viele diese Features werden letztlich auch für hybride Bereitstellungen mit Configuration Manager unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Role-based access control
  ### Intune apps
  ### Monitor and troubleshoot

-->   

## <a name="week-of-september-11-2017"></a>Die Woche vom 11. September 2017

### <a name="device-enrollment"></a>Geräteregistrierung

#### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo----1475932---"></a>Zusätzliche Pushbenachrichtigungen für Benutzer in der Unternehmensportal-App für Android Oreo <!---1475932--->

Benutzern werden zusätzliche Benachrichtigungen angezeigt, die ihnen mitteilen, wann die Unternehmensportal-App für Android Oreo Hintergrundaufgaben durchführt, z.B. Abrufen von Richtlinien aus dem Intune-Dienst. Dadurch wird die Transparenz für Endbenutzer erhöht, für den Fall, dass das Unternehmensportal administrative Aufgaben auf ihren Geräten ausführt. Dies ist Teil der gesamten [Optimierung der Unternehmensportal-Benutzeroberfläche](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) für die Unternehmensportal-App für Android Oreo. 

#### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Informieren von Endbenutzern, welche Geräteinformation für iOS angezeigt werden kann <!--739894--> 

Wir haben dem Bildschirm „Gerätedetails“ den **Besitzertyp** auf der Unternehmensportal-App für iOS hinzugefügt. So können Benutzer direkt auf dieser Seite mehr über die Privatsphäre in der Dokumentation für Intune-Endbenutzer herausfinden. Sie finden diese Informationen ebenso auf dem Bildschirm „Info“. 

#### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Zugriff auf die Unternehmensportal-App für Android durch Endbenutzer ohne Registrierung <!---1169910--->

Endbenutzer müssen ihr Gerät bald nicht mehr registrieren, um auf die Unternehmensportal-App für Android zugreifen zu können. Endbenutzer innerhalb von Organisationen, die App-Schutzrichtlinien verwenden, werden beim Öffnen der Unternehmensportal-App nicht mehr aufgefordert, ihr Gerät zu registrieren. Zudem können Endbenutzer Apps vom Unternehmensportal installieren, ohne ihr Gerät zu registrieren. 


#### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Vereinfachung der Formulierung für die Unternehmensportal-App für Android <!---1396349--->  

Der Registrierungsvorgang für die Unternehmensportal-App für Android wurde durch einen neuen Text vereinfacht, um Endbenutzern eine einfachere Registrierung zu bieten. Wenn Sie über eine benutzerdefinierte Registrierungsdokumentation verfügen, sollten Sie diese aktualisieren, damit diese die neuesten Bildschirme anzeigt. Sie können Beispielabbildungen auf unserer Seite [Aktualisierungen für die Benutzeroberfläche für Endbenutzer-Apps in Intune](whats-new-app-ui.md#week-of-september-11-2017) sehen.

#### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Hinzufügen der Windows Information Protection-Zulassungsrichtlinie zur Windows 10-Unternehmensportal-App <!-- 677129 -->

Die Unternehmensportal-App unter Windows 10 wurde aktualisiert, um Unterstützung für Windows Information Protection (WIP) bereitzustellen. Die App kann zur WIP-Zulassungsrichtlinie hinzugefügt werden. Aufgrund dieser Änderung muss die App nicht mehr zur Liste **Ausnahme** hinzugefügt werden. 


## <a name="week-of-august-21-2017"></a>Woche vom 21. August 2017

### <a name="device-enrollment"></a>Geräteregistrierung
#### <a name="improvements-to-device-overview----1404453---"></a>Verbesserungen an der Geräteübersicht <!-- 1404453 -->  
Die Verbesserungen an der Geräteübersicht zeigen nun registrierte Geräte an, jedoch keine Geräte, die von Exchange ActiveSync verwaltet werden. Exchange ActiveSync-Geräte verfügen nicht über die gleichen Verwaltungsoptionen wie registrierte Geräte. Um die Anzahl der registrierten Geräte und die Anzahl der registrierten Geräte nach Plattform in Intune im Azure-Portal anzuzeigen, navigieren Sie zu **Geräte** > **Übersicht**.

### <a name="device-management"></a>Geräteverwaltung
#### <a name="improvements-to-device-inventory-collected-by-intune"></a>Verbesserungen am von Intune erfassten Gerätebestand
<!-- 961134, 1104426, 1281327, 1333543 -->
In diesem Release haben wir die folgenden Verbesserungen an den Bestandsinformationen vorgenommen, die von den von Ihnen verwalteten Geräten gesammelt werden:
 
-   Bei Android-Geräten können Sie nun eine Spalte zum Gerätebestand hinzufügen, die die neueste Patchebene für jedes Gerät anzeigt. Fügen Sie die Spalte **Sicherheitspatchebene** zu Ihrer Geräteliste hinzu, um dies anzuzeigen.
-   Wenn Sie in der Geräteansicht filtern, können Sie die Geräte nun nach ihrem Registrierungsdatum filtern. Beispielsweise könnten Sie nur Geräte anzeigen lassen, die nach einem von Ihnen angegebenen Datum registriert wurden.
-   Wir haben Verbesserungen an dem Filter vorgenommen, der vom Element **Last Check-in Date** (Letztes Eincheckdatum) verwendet wird.
-   In der Geräteliste können Sie jetzt die Telefonnummern von unternehmenseigenen Geräten anzeigen.
Darüber hinaus können Sie den Filterbereich verwenden, um Geräte nach Telefonnummer zu suchen.
 
Weitere Informationen zum Gerätebestand finden Sie unter [So zeigen Sie den Intune-Gerätebestand an](device-inventory.md).

#### <a name="conditional-access-support-for-macos-devices"></a>Unterstützung des bedingten Zugriffs für macOS-Geräte 
<!-- 720172 -->
Sie können nun eine Richtlinie für bedingten Zugriff festlegen, durch die Mac-Geräte bei Intune registriert werden und den Gerätekompatibilitätsrichtlinien entsprechen müssen. Benutzer können z.B. die Intune-Unternehmensportal-App für macOS herunterladen und ihre Mac-Geräte bei Intune registrieren. Intune bewertet, ob das Mac-Gerät mit Anforderungen wie PIN, Verschlüsselung, Betriebssystemversion und Systemintegrität kompatibel ist.

- Erfahren Sie mehr über die [conditional access support for macOS devices (Unterstützung des bedingten Zugriffs für macOS-Geräte)](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

#### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>Die Unternehmensportal-App für macOS befindet sich in der öffentlichen Vorschauversion <!---1484796--->.
Die Unternehmensportal-App für macOS ist nun als Teil der öffentlichen Vorschauversion für bedingten Zugriff in Enterprise Mobility + Security verfügbar. Diese Version unterstützt macOS 10.11 und höher. Laden Sie die Anwendung unter [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal) herunter. 


#### <a name="new-device-restriction-settings-for-windows-10"></a>Neue Einstellungen für Geräteeinschränkungen für Windows 10    
<!--1063965, 1308850  -->
In diesem Release haben wir neue Einstellungen für das [Windows 10-Geräteeinschränkungsprofil](/intune/device-restrictions-windows-10) in folgenden Kategorien hinzugefügt:

-   Windows Defender SmartScreen
-   App Store

#### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>Updates für die Einstellungen des Windows 10 Endpoint Protection-Geräteprofils für BitLocker
<!--1459533 -->    
In diesem Release haben wir die folgenden Verbesserungen daran vorgenommen, wie die BitLocker-Einstellungen in einem Windows 10 Endpoint Protection-Geräteprofil funktionieren:
 
Wenn Sie unter **BitLocker-Einstellungen für Betriebssystemlaufwerk** für die Einstellung **BitLocker für nicht kompatiblen TPM-Chip** **Blockieren** auswählen, hat dies bisher dazu geführt, dass BitLocker tatsächlich zugelassen ist. Wir haben dies nun behoben, sodass BitLocker blockiert wird, wenn dies ausgewählt wird.
Unter **BitLocker-Einstellungen für Betriebssystemlaufwerk** können Sie nun für die Einstellung **Agent für zertifikatbasierte Datenwiederherstellung** explizit den Agent für zertifikatbasierte Datenwiederherstellung blockieren. Standardmäßig ist der Agent jedoch zulässig.
Unter **BitLocker-Einstellungen für Festplattenlaufwerk** können Sie nun für die Einstellung **Datenwiederherstellungs-Agent** explizit den Datenwiederherstellungs-Agent blockieren.
Weitere Informationen finden Sie unter [Endpoint protection settings for Windows 10 and later (Endpoint Protection-Einstellungen für Windows 10 und höher)](endpoint-protection-windows-10.md).


### <a name="app-management"></a>App-Verwaltung
#### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Neue Anmeldeerfahrung für Benutzer des Android-Unternehmensportals sowie für Benutzer der App-Schutz-Richtlinien <!-- 621669 -->
Endbenutzer können jetzt in der Android-Unternehmensportal-App nach Apps suchen, Geräte verwalten und IT-Kontaktinformationen anzeigen, ohne ihre Android-Geräte registrieren zu müssen. Wenn ein Benutzer, der bereits eine App verwendet, die durch Richtlinien zum Intune-App-Schutz geschützt ist, zusätzlich die Android-Unternehmensportal-App startet, dann enthält er zukünftig keine Aufforderung mehr, das Gerät zu registrieren.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Neue Einstellung in der Android-Unternehmensportal-App für die Akkuoptimierung <!--1405990-->
Auf der Seite **Einstellungen** in der Unternehmensportal-App für Android ist eine neue Einstellung verfügbar, mit der Benutzer die Akkuoptimierung einfach für Unternehmensportal- und Microsoft Authenticator-Apps ausschalten können. Der in der Einstellung dargestellte Name der App hängt davon ab, welche App das Geschäftskonto verwaltet. Benutzern wird empfohlen, die Akkuoptimierung zugunsten besserer Leistung von Work-Apps auszuschalten, die E-Mails und Daten synchronisieren. 

#### <a name="multi-identity-support-for-onenote-for-ios---------1234281---"></a>Unterstützung mehrerer Identitäten für OneNote für iOS <!-- 1234281 -->
Benutzer können jetzt verschiedene Konten (geschäftlich und privat) mit Microsoft OneNote für iOS verwenden. App-Schutzrichtlinien können auf Unternehmensdaten in Arbeitsnotizbüchern angewendet werden, ohne dass persönliche Notizbücher betroffen sind. Beispielsweise kann eine Richtlinie einem Benutzer erlauben, Informationen in Arbeitsnotizbüchern zu suchen, verhindert jedoch, dass der Benutzer Unternehmensdaten aus dem Arbeitsnotizbuch in ein persönliches Notizbuch kopiert.
 
- Erfahren Sie mehr über die Apps, die [App-Schutz und mehrere Identitäten](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) mit Intune unterstützen.

#### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Neue Einstellungen zum Zulassen und Blockieren von Apps auf Samsung KNOX Standard-Geräten
<!-- 1305423 822899-->  
In dieser Version werden neue [Einstellungen für Geräteeinschränkungen](device-restrictions-android.md) hinzugefügt, mit denen Sie die folgenden App-Listen angeben können:
 
- Apps, die Benutzer installieren dürfen
- Apps, für deren Ausführung Benutzer blockiert sind
- Apps, die vor dem Benutzer auf dem Gerät verborgen werden
 
Sie können die Apps mithilfe der URL, des Paketnamens oder der Liste der Apps, die Sie verwalten, angeben.

#### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Neue App-basierte Benutzeroberflächenverknüpfung für Azure AD-Richtlinien für den bedingten Zugriff in Intune
<!-- 1016201 -->
IT-Administratoren können nun App-basierte Richtlinien für den bedingten Zugriff über die neue Benutzeroberfläche für Richtlinien für den bedingten Zugriff in der Azure AD-Workload festlegen. Der App-basierte bedingte Zugriff, der sich im Bereich Intune-App-Schutz im Azure-Portal befindet, bleibt dort vorläufig und wird parallel erzwungen. Es ist auch ein praktischer Link zur neuen Benutzeroberfläche der Richtlinie für den bedingten Zugriff im Intune-Workload vorhanden.

- Erfahren Sie mehr über den [app-based conditional access on Azure AD (App-basierten bedingten Zugriff für Azure AD)](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference).


## <a name="notices"></a>Benachrichtigungen

### <a name="ip-addresses-for-intune-updated----1175274---"></a>IP-Adressen für Intune aktualisiert <!-- 1175274 -->
Eine [aktualisierte Liste der DNS-Namen und IP-Adressen](/intune/network-bandwidth-use) steht für die Firewall-Proxyeinstellungen zur Verfügung.

### <a name="use-azure-active-directory-for-conditional-access----967947---"></a>Verwenden von Azure Active Directory für bedingten Zugriff <!-- 967947 -->
„Bedingter Zugriff“ ist im Abschnitt „Azure Active Directory“ des Azure-Portals verfügbar. Diese Option bietet ein leistungsstärkeres und flexibleres Framework für das Festlegen von Richtlinien für Cloud-Apps wie Office 365 Exchange Online und SharePoint Online.  Richtlinien können Sie statt in der Intune-Konsole auf dem Blatt **Bedingter Zugriff in Azure Active Directory** konfigurieren. In der Intune-Konsole vorhandene Richtlinien müssen im Azure-Portal neu erstellt werden. Weitere Informationen finden Sie unter [Erstellen von Azure AD-Richtlinien für den bedingten Zugriff](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview).

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Direkter Zugriff auf Apple-Registrierungsszenarien <!--951869-->
Für Intune-Konten, die nach Januar 2017 erstellt wurden, hat Intune direkten Zugriff auf Apple-Registrierungsszenarien mithilfe der Workload „Geräte registrieren“ im Azure-Portal aktiviert. Bisher konnte nur über Links im klassischen Intune-Portal auf die Apple-Registrierungsvorschau zugegriffen werden. Vor Januar 2017 erstellte Intune-Konten erfordern eine einmalige Migration, bevor diese Features in Azure verfügbar sind. Der Zeitplan für die Migration wurde noch nicht angekündigt, aber Sie erfahren so bald wie möglich Näheres. Wir empfehlen Ihnen dringend, ein Testkonto zu erstellen, um die neue Oberfläche zu testen, wenn Sie mit Ihrem vorhandenen Konto nicht auf das Azure-Portal zugreifen können.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Administratorrollen werden im Azure-Portal ersetzt
Die in der Verwaltung mobiler Anwendungen (Mobile Application Management, MAM) vorhandenen Administratorrollen (Mitwirkender, Besitzer und Schreibgeschützt), die im klassischen Intune-Portal (Silverlight) verwendet werden, werden im Intune-Azure-Portal durch einen vollständigen Satz neuer rollenbasierter Zugriffssteuerung (Role-Based Access Control, RBAC) ersetzt. Nach der Migration zum Azure-Portal müssen Sie Ihre Administratoren diesen neuen Administratorrollen neu zuweisen. Weitere Informationen zu RBAC und den neuen Rollen finden Sie unter [Rollenbasierte Zugriffssteuerung für Microsoft Intune](/intune/role-based-access-control).



## <a name="whats-coming"></a>Was steht an?

#### <a name="ios-11-mail-app-will-support-oauth----1196951---"></a>Die iOS 11-Mail-App wird OAuth <!---1196951---> unterstützen.
Der bedingte Zugriff über Intune unterstützt nun eine sicherere Authentifizierung auf iOS-Geräten mit OAuth. Der Ablauf der Unternehmensportal-App für iOS hat sich geändert, um dies zu unterstützen und eine sicherere Authentifizierung zu ermöglichen. Wenn Endbenutzer versuchen, sich mit einem neuen Exchange-Konto in der Mail-App anzumelden, wird ihnen eine Aufforderung in der Webansicht angezeigt. Bei der Registrierung in Intune werden Benutzer dazu aufgefordert, der nativen Mail-App den Zugriff auf ein Zertifikat zu gewähren. Den meisten Benutzern werden isolierte E-Mails nicht mehr angezeigt. Bestehende E-Mail-Konten werden weiterhin das Standardauthentifizierungsprotokoll verwenden. Diesen Benutzern werden also immer noch isolierte E-Mails zugestellt. Die Anmeldung für Endbenutzer ähnelt der Anmeldung bei mobilen Office-Apps.

### <a name="end-of-support-for-ios-80----1164477---"></a>Ablauf des Supports für iOS 8.0 <!---1164477--->
Verwaltete Apps und die Unternehmensportal-App für iOS benötigen iOS 9.0 und höher, um auf Unternehmensressourcen zugreifen zu können. Geräte, die nicht bis September aktualisiert werden, können nicht mehr auf das Unternehmensportal oder diese Apps zugreifen. 

### <a name="ui-updates-to-the-company-portal-website---1313244-part-2--"></a>Updates für die Benutzeroberfläche der Unternehmensportal-Website<!--1313244 part 2-->
__Aktualisierungen der Empfohlenen Apps__  
Wir haben der Website eine dedizierte Seite hinzugefügt, auf der Benutzer Apps durchsuchen können, die Sie empfehlen, und haben einige Optimierungen auf der Benutzeroberfläche für den Abschnitt „Featured“ (Empfohlen) auf der Homepage vorgenommen. Sie können diese Änderungen auf der Seite [Was gibt es Neues auf der App-Benutzeroberfläche](whats-new-app-ui.md) anzeigen.


### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Ablauf des Supports für Android 4.3 und niedriger <!---1171127, 1326920 --->
Verwaltete Apps und die Unternehmensportal-App für Android benötigen Android 4.4 oder höher, um auf Unternehmensressourcen zugreifen zu können. Geräte, die nicht bis Anfang Oktober aktualisiert werden, können nicht mehr auf das Unternehmensportal oder diese Apps zugreifen. Ab Dezember werden alle registrierten Geräte deaktiviert und können dann nicht mehr auf Unternehmensressourcen zugreifen. Bei Verwendung von App-Schutzrichtlinien ohne mobile Geräteverwaltung erhalten Apps keine Updates mehr, und die Qualität ihrer Benutzung wird mit der Zeit abnehmen.


### <a name="platform-support-reminder-windows-phone-81-mainstream-support-ended-july-11-2017"></a>Erinnerung zur Plattformunterstützung: Der Mainstream-Support für Windows Phone 8.1 endete am 11. Juli 2017.
<!-- 1327781 -->
Am 11. Juli 2017 hat die Windows Phone8.1-Plattform das Ende des Mainstream-Supports erreicht. Der Support für den Windows 8.1-PC ist davon nicht betroffen.

Dies hat keinen unmittelbaren Einfluss auf Windows Phone 8.1-Geräte, die vom Intune-Dienst verwaltet werden. Registrierte Geräte funktionieren weiterhin, und alle Richtlinien, Konfigurationen und Apps werden weiterhin wie erwartet funktionieren. Beachten Sie, dass es keine Verbesserungen für die Windows Phone 8.1-Plattform im Intune-Dienst sowie für die Unternehmensportal-App von Windows Phone 8.1.

Wir empfehlen Ihnen daher, zum schnellstmöglichen Zeitpunkt ein Upgrade für berechtigte Windows Phone 8.1-Geräte auf Windows 10 Mobile durchzuführen. 

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Änderungen bei der Unterstützung der Intune-iOS-Unternehmensportal-App <!-- 1164474  -->
In den kommenden Monaten erscheint eine neue Version für die Microsoft Intune-Unternehmensportal-App für iOS, die nur Geräte mit mindestens iOS 9.0 unterstützt. Die Version des Unternehmensportals, die iOS 8 unterstützt, wird für einen sehr kurzen Zeitraum weiterhin verfügbar sein. Beachten Sie jedoch, dass wenn Sie auch die MAM-fähigen iOS-Apps verwenden, für die wir iOS 9.0 und höher unterstützen, sicherstellen müssen, dass Ihre Benutzer ein Update auf das neueste Betriebssystem durchführen. 

#### <a name="how-does-this-affect-me"></a>Inwiefern betrifft das mich?
Wir geben Ihnen früh genug Bescheid, damit Sie genügend Zeit für die Planung haben, auch wenn wir noch kein bestimmtes Datum angeben können. Vergewissern Sie sich, dass Ihre Benutzer auf iOS 9 und höher aktualisiert haben, und Sie bei der Veröffentlichung der Unternehmensportal-App von Ihren Benutzern fordern, dass diese ihre Unternehmensportal-App aktualisieren.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wie sollte ich mich für die Änderung vorbereiten?
Ermutigen Sie Ihre Benutzer, ein Update auf iOS 9.0 oder höher durchzuführen, damit sie in den vollen Genuss der neuen Intune-Features kommen.  Fordern Sie Benutzer auf, die neue Version des Unternehmensportals zu installieren und die neuen darin angebotenen Funktionen zu benutzen.

Wechseln Sie zu Intune im Azure-Portal, und sehen Sie sich „Geräte > Alle Geräte“ an. Filtern Sie nach der iOS-Version, um alle aktuellen Geräte mit einem Betriebssystem vor iOS 9 anzuzeigen.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple erfordert Updates für die Transportsicherheit für Anwendungen <!--748318-->
Apple hat angekündigt, dass bestimmte Anforderungen für die Transportsicherheit für Anwendungen (Application Transport Security, ATS) erzwungen werden. ATS wird verwendet, um eine strengere Sicherheit in allen App-Kommunikationen über HTTPS zu erzwingen. Diese Änderung wirkt sich auf Intune-Kunden aus, die die iOS-Unternehmensportal-App verwenden.

Wir haben im Apple TestFlight-Programm eine Version der Unternehmensportal-App für iOS zur Verfügung gestellt, die die neuen ATS-Anforderungen erzwingt. Wenn Sie sie ausprobieren möchten, um Ihre ATS-Konformität zu testen, senden Sie eine E-Mail mit Angaben zu Vorname, Nachname, E-Mail-Adresse und Firmenname an <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a>. Unter [Intune support blog (Intune-Supportblog)](https://aka.ms/compportalats) finden Sie weitere Informationen.

### <a name="see-also"></a>Weitere Informationen:
* [Microsoft Intune-Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap für die Cloudplattform](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [What‘s new in the Intune App UI (Neues auf der Intune-App-Benutzeroberfläche)](whats-new-app-ui.md)
* [Neuerungen in den vorherigen Monaten](whats-new-archive.md)
