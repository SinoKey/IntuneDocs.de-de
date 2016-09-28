---
title: Vorherige Versionen | Microsoft Intune
description: 
keywords: 
author: Lindavr
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9d3305d9938244f0da769dc547cd7a42d7ef81ed
ms.openlocfilehash: 996198a2525dc830d229e7143afda3c71f4276b8


---

# Vorherige Versionen von Intune
## August 2016
## August 2016
## App-Verwaltung
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

### Ausgeblendete und eingeblendete Apps für iOS 9.3
Bei überwachten Geräten mit iOS 9.3 oder höher können Sie die Liste für ausgeblendete und eingeblendete Apps in der allgemeinen iOS-Konfigurationsrichtlinie für folgende Aufgaben verwenden:
- Angeben einer Liste von Apps, die vor Benutzern verborgen werden. Benutzer können diese Apps weder anzeigen noch starten.
- Angeben einer Liste von Apps, die Benutzer anzeigen und starten können. Es können keine anderen Apps angezeigt oder gestartet werden.

Die Apps, die Sie angeben können, umfassen sowohl von Ihnen bereitgestellte Apps als auch integrierte iOS-Apps, wie „Nachrichten“ und „Notizen“. Weitere Informationen finden Sie unter [iOS-Richtlinieneinstellungen in Microsoft Intune]( https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune).
<!---TFS 1279009 checked--->
### Richtlinie für zulässige und blockierte Apps für Samsung KNOX-Geräte
Sie können jetzt eine benutzerdefinierte Richtlinie für Samsung KNOX-Geräte konfigurieren, die Ihnen das Erstellen einer der folgenden Listen ermöglicht:
- Eine Liste von Apps, deren Ausführung auf dem Gerät blockiert wird. Eine in der Liste blockierter Apps definierte App kann nicht auf dem Gerät aktiviert werden, auch wenn sie auf dem Gerät installiert ist.
- Eine Liste von Apps, die Benutzer des Geräts aus dem Google Play Store installieren dürfen. Es können keine anderen Apps aus dem Store installiert werden.

Diese Einstellungen können nur von Geräten verwendet werden, auf denen Samsung KNOX ausgeführt wird.
Weitere Informationen finden Sie unter [Use custom policies to allow and block apps for Samsung KNOX devices]( custom-policy-to-allow-and-block-samsung-knox-apps.md) (Verwenden von benutzerdefinierten Richtlinien zum Zulassen und Blockieren von Apps für Samsung KNOX-Geräte).
<!---TFS 1311629 checked --->
### Neue, mit MAM-Richtlinien kompatible Apps
Die Yammer-App für [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) und [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) ist nun mit [Intune-Richtlinien für die Verwaltung mobiler Anwendungen](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) (Mobile Application Management, MAM) kompatibel. Dies gilt unabhängig davon, ob das Gerät registriert ist oder nicht.

Eine vollständige Liste MAM-kompatibler Apps finden Sie auf der Website [Microsoft Intune-Anwendungspartner](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners).
<!--- TFS 1252335 & 1252336 checked--->


<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

### Intune Viewer-Apps
Mit der Veröffentlichung der neuen RMS-Freigabe-App werden wir ab August 2016 die folgenden Intune Viewer-Apps entfernen:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer für Android aus Google Play

Anstatt die Intune-Viewer-Apps zu verwenden, empfehlen wir die Nutzung der neuen [Rights Management-App (RMS-Freigabe)](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app) für Android, die Ihnen das Bereitstellen einer App anstelle von drei getrennten Apps ermöglicht, um Unternehmensdateien sicher auf Android-Geräten anzuzeigen. Wenn die Intune-Viewer-App nicht mehr unterstützt wird, wird sie aus dem Google Store entfernt und steht nicht mehr zur zukünftigen Verwendung zur Verfügung.

## Geräteverwaltung
### Android 7.0-Unterstützung
Intune bietet „Day-0“-Unterstützung für das bevorstehende Android 7.0-Betriebssystem für mobile Geräte.
<!---TFS 1262053--->
### Funktion für das Remote-Zurücksetzen von Passcodes auf Android 7.0-Geräten von Google entfernt
Die Funktion, durch die IT-Administratoren und Endbenutzer den Passcode von Android 7.0-Geräten remote zurücksetzen konnten, wurde von Google entfernt. Zuvor konnten IT-Administratoren Benutzerpasscodes remote zurücksetzen, und Endbenutzer konnten ihre Passcodes auf der Unternehmensportal-Website zurücksetzen.



## Aktualisierungen am Unternehmensportal
### Unternehmensportal-Website
- **Feedbacklink vom Unternehmensportal zu Microsoft** <br/>
Auf der Unternehmensportal-Website können Endbenutzer auf einen neuen „Feedbacklink“ am unteren Seitenrand tippen, um Feedback zu ihren Erfahrungen mit der Website an Microsoft zu senden. Das gesammelte anonymisierte Feedback hilft Microsoft, die Benutzerfreundlichkeit der Unternehmensportal-Website zu verbessern.
<!--- TFS 1313657 checked--->

### iOS
- **Minimale Version des Managed Browser für iOS auf 8.0 aktualisiert**<br/>
Die Microsoft Intune Managed Browser-App für iOS wurde aktualisiert, um Geräte zu unterstützen, die iOS 8.0 oder höher ausführen. iOS 7.1-Geräte können zwar weiterhin die vorhandene Managed Browser-App verwenden, fordern Sie Ihre Benutzer jedoch auf, auf iOS 8.0 oder höher zu aktualisieren, um die neuen Features von Managed Browser in vollem Umfang zu nutzen.  
<!---TFS 1313253 checked--->

## Was steht an?

### iOS 10-Unterstützung
Intune unterstützt iOS 10 in vollem Umfang. Weitere Informationen folgen nach dem öffentlichen Release von iOS 10.

### Übergang von Intune-Gruppen zu Azure Active Directory-Gruppen ab September 2016
Intune erstellt eine neue Benutzeroberfläche für die Gruppenverwaltung, die Azure Active Directory-Sicherheitsgruppen (AAD) als Benutzer- und Gerätegruppen in Intune verwendet. Diese Gruppen werden für sämtliche Gruppenverwaltung, Richtlinien- und Profilbereitstellung verwendet, **wenn das neue Intune-Verwaltungsportal auf Azure-Basis eingeführt wird**.

Diese neue Benutzeroberfläche verhindert, dass Sie Gruppen zwischen Diensten duplizieren müssen, **ermöglicht Ihnen den Zugriff auf einige neue Gruppenfeatures in Azure Active Directory Premium (AADP)** und bietet Erweiterbarkeit mithilfe von PowerShell und Graph. Dies vereinheitlicht auch die Gruppenverwaltungsoberfläche der Enterprise Mobility-Verwaltung übergreifend.

Um den Wechsel zu Sicherheitsgruppen zu ermöglichen, wird die Benutzeroberfläche in der **aktuellen Administratorkonsole** einige Änderungen erfahren. **Diese Änderungen und die Verwendung von AAD-Sicherheitsgruppen werden in der Intune-Dokumentation aufgezeichnet**.

Neue Intune-Kunden **sehen einige der Sicherheitsgruppenänderungen, bevor aktuelle Mandanten sie sehen**.

Zusätzlich zu Änderungen der Gruppenverwaltung **werden die folgende Funktionen als veraltet markiert**:
- Ausschließen von Mitgliedern oder Gruppen beim Erstellen einer neuen Gruppe
- **Nicht gruppierte Benutzer** und **Nicht gruppierte Geräte**
- **Verwalten von Gruppen** in der Dienstadministratorrolle
- Benutzerdefinierte gruppenbasierte Warnungen für Benachrichtigungsregeln
- Pivotieren mit Gruppen in Berichten
<!--- TFS 1295329--->

### Hinzufügen von „Benachrichtigungen“ zum Unternehmensportal für Android
Im September veröffentlichen wir ein Update zum Unternehmensportal für Android, mit dem auf der Startseite das neue Symbol **Benachrichtigungen** eingeführt wird. Beim Tippen auf dieses Symbol wird die Seite **Benachrichtigungen** aufgerufen, auf der für Ihre Endbenutzer alle Elemente angezeigt werden, die in der Unternehmensportal-App Aufmerksamkeit erfordern, z. B. Nichtkompatibilität, Registrierungsupdate und Registrierungsaktivierung. Wenn Sie auch die iOS-Unternehmensportal-App verwenden, sehen Sie die Benachrichtigungen bereits. Wenn die Seite **Benachrichtigungen** eingeführt wird, werden Sie die Seite **Unternehmenszugriff einrichten** nicht bei jedem Start bzw. jeder Fortsetzung des Unternehmensportals für Android sehen, solange das Gerät bereits registriert ist. Wir haben erfahren, dass viele von Ihnen Endbenutzeranleitungen erstellt haben, und würden eine vorherige Mitteilung schätzen, wenn Ihre Anleitung/Screenshots vielleicht aktualisiert werden müssen. Bitte aktualisieren Sie Ihre Dokumentation gemäß der anstehenden Änderung der Benutzeroberfläche. Aktualisierte Screenshots finden Sie hier: https://aka.ms/androidcpupdate.  

### Verbesserungen für das Abrufen von Apps durch iOS-Endbenutzer
Die folgenden Änderungen werden im September an den App-Kacheln in der Unternehmensportal-App für iOS vorgenommen, damit Benutzer für all ihre Apps an verschiedene Ansichten einer einzigen Stelle verwiesen werden: der Unternehmensportal-Website. Zurzeit verhindern Apple-Einschränkungen das Auflisten branchenspezifischer und verwalteter App Store-Apps in der Unternehmensportal-App, sodass Benutzer verschiedene Ansichten besuchen müssen, um all ihre Apps zu finden.

- Die Kachel **Unternehmens-Apps** verweist derzeit auf eine Liste aller Apps auf der Registerkarte ALLE der Unternehmensportal-Website, und diese Funktion bleibt weiterhin bestehen. Der Name der Kachel ändert sich in **Alle Apps**.
- Die Kachel **Andere Apps** verweist zurzeit auf eine Ansicht innerhalb der Unternehmensportal-App, in der alle Apps aufgeführt werden, deren Anzeige Apple der Unternehmensportal-App gestattet. Der Name der Kachel wird in **Ausgewählte Apps** geändert, und durch Tippen auf die Kachel gelangen Benutzer auf die Registerkarte AUSGEWÄHLTE der Unternehmensportal-Website.
-  Die Kachel **Kategorien** verweist zurzeit auf eine Ansicht innerhalb der Unternehmensportal-App, in der Kategorien von Apps aufgeführt werden. Der Name der Kachel wird nicht geändert, aber sie verweist jetzt auf die Registerkarte KATEGORIEN der Unternehmensportal-Website. Aktualisierte Screenshots finden Sie [hier](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
<!---TFS 1317133--->

### Fahrplan für die Cloud
Halten Sie sich mit dem [Fahrplan für die Cloudplattform](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune) zu den anstehenden Entwicklungen für Intune auf dem Laufenden.

### Veraltete Dienste
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **Änderungen bei der Unterstützung der iOS-Unternehmensportal-App**<br/>
Ab September müssen alle Benutzer der Microsoft Intune-Unternehmensportal-App für iOS die aktuelle Version verwenden. Neue Benutzer können nur die aktuelle Version herunterladen, und derzeitige Benutzer müssen ein Update auf die aktuelle Version durchführen. Die aktuelle Version erfordert iOS 8.0 oder höher. Daher können Benutzer von Geräten mit älteren iOS-Versionen erst dann das Unternehmensportal nutzen und eine Registrierung durchführen, wenn sie ihr Gerät auf iOS 8.0 oder höher aktualisieren und anschließend die Unternehmensportal-App auf die aktuelle Version aktualisieren. Registrierte Geräte mit Versionen vor iOS 8.0 werden weiterhin verwaltet und in der Intune-Verwaltungskonsole aufgeführt.  

- **Minimale Version des Managed Browser für iOS auf 8.0 aktualisiert**<br/>
Im August wird Intune eine aktualisierte Microsoft Intune Managed Browser-App für iOS veröffentlichen, die nur Geräte unter iOS 8.0 oder höher unterstützt. iOS 7.1-Geräte können zwar weiterhin die vorhandene Managed Browser-App verwenden, doch fordern Sie Ihre Benutzer bitte auf, auf iOS 8.0 oder höher zu aktualisieren und die neuen Features von Managed Browser in vollem Umfang zu nutzen.  
<!---TFS 1313253--->

- **Unternehmensportal-Apps für Windows 8 und Windows Phone 8 werden eingestellt.** <br/>
Ab Oktober 2016 wird Microsoft Intune die Unterstützung für Windows 8- und Windows Phone 8-Unternehmensportal-Apps beenden. Microsoft Intune wird auch die Unterstützung für die Windows Phone 8-Plattform beenden. Daher werden Sie keine Windows Phone 8-Geräte mehr registrieren oder aktualisieren können. Sie können weiterhin Windows Phone 8 und Windows 8-Geräte verwalten, die bereits registriert sind. Aktualisieren Sie Windows Phone 8- und Windows 8-Geräte auf Windows Phone 8.1 und Windows 8.1, und nutzen Sie die entsprechenden Windows Phone 8.1- und Windows 8.1-Unternehmensportal-Apps, um weiterhin Apps an diese Geräte verteilen zu können.
<!---TFS 1255391--->

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->

## Juli 2016
### App-Verwaltung
#### Verbessern der Benutzererfahrung beim Update des App-Bereitstellungsprofils
Die Apple iOS-Reihe mobiler Geschäfts-Apps wird mit einem integrierten Bereitstellungsprofil erstellt und mit Code, der mit einem Zertifikat signiert wurde. Beim Ausführen der App auf einem iOS-Gerät bestätigt iOS die Integrität der iOS-App und erzwingt Richtlinien, die durch das Bereitstellungsprofil definiert werden.

Das Unternehmenssignaturzertifikat, das Sie zum Signieren von Apps verwenden, ist in der Regel 3 Jahre lang gültig. Allerdings läuft das Bereitstellungsprofil nach 1 Jahr ab. Mit diesem Update stellt Intune Ihnen die Tools zum proaktiven Bereitstellen einer neuen Richtlinie für Bereitstellungsprofile auf Geräten zur Verfügung, auf denen Apps installiert sind, die bald ablaufen, während das Zertifikat noch gültig ist. Weitere Informationen finden Sie unter [Use iOS mobile provisioning profile policies to keep your line of business apps up to date](/intune/deploy-use/ios-mobile-app-provisioning-profiles) (Verwenden von Richtlinien für iOS-Mobilbereitstellungsprofile, um Ihre Business-Apps aktuell zu halten).
<!--- TFS 1280247--->
#### Xamarin-SDK für Intune-Apps ist verfügbar
Mit der Intune-App-SDK-Xamarin-Komponente können Sie die Intune-Verwaltungsfeatures für mobile Apps in Ihren mit Xamarin erstellten mobilen iOS- und Android-Apps aktivieren. Sie finden die Komponente im [Xamarin Store](https://components.xamarin.com/view/Microsoft.Intune.MAM) oder auf der [Microsoft Intune-Github-Seite](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

### Geräteverwaltung
#### Höhere Limits bei der Geräteregistrierung
Intune erhöhte das maximal konfigurierbare Limit für die Geräteregistrierung von 5 auf 15 Geräte pro Benutzer.
<!---TFS 1289896 --->

#### TeamViewer-Integration für Windows-PCs, auf denen die Intune-Clientsoftware ausgeführt wird
Mithilfe der [TeamViewer](https://www.teamviewer.com)-Integration für Windows-PCs, auf denen der Intune-Client ausgeführt wird, können Sie Remoteunterstützungssitzungen mit Windows-PCs herstellen, um Helpdeskabteilungen für Endbenutzer zu entlasten. Dies gilt für Windows 7, 8, 8.1 und Windows 10. Weitere Informationen finden Sie unter [Allgemeine Aufgaben zur Verwaltung von Windows-PCs mit dem Microsoft Intune-Computerclient](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).
<!---TFS 1284856--->

### Aktualisierungen am Unternehmensportal
#### Unternehmensportal-Website
- **Verbesserte Endbenutzererfahrung bei der Registrierung von Windows-Geräten**<br/>
Wenn Sie den bedingten Zugriff verwenden, werden die Registrierungsschritte für Windows 8.1, Windows 10 Desktop und Windows 10 Mobile in der Unternehmensportal-Website erklärt. Benutzer sehen jetzt die separaten Schritte „Geräteregistrierung“ und „Workplace Join“, mit denen sie leichter den Status ihres Geräts anzeigen und den Prozess abschließen können, wenn ein Fehler beim Workplace Join (WPJ) auftritt. Die separaten Schritte sollten auch die Problembehandlung für IT-Administratoren vereinfachen. Wenn Endbenutzer versuchten, das Gerät zu registrieren, und alle Registrierungsschritte außer dem WPJ erfolgreich verliefen, wurde das registrierte Gerät bisher nicht in der Liste der Geräte angezeigt, die Benutzer identifizieren konnten, und dies verwirrte die Benutzer.

#### Android
- **Android-Unternehmensportal-App**<br/>
Wenn Android-Endbenutzer eine Fehlermeldung erhalten, ihrem Gerät fehle ein erforderliches Zertifikat, können sie auf eine Schaltfläche „Problembehebung“ tippen, um [Schritte](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) für die Installation des fehlenden Zertifikats abzurufen. Wenn Benutzer die Schritte ausführen, jedoch eine zusätzliche „Fehlendes Zertifikat“-Fehlermeldung angezeigt wird, werden sie aufgefordert, sich an ihren IT-Administrator zu wenden und diesen [Link](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues) anzugeben, der Schritte enthält, mit denen IT-Administratoren das Zertifikatsproblem beheben können.

- **Einschränken der Installationen quergeladener Apps auf registrierten Geräten**<br/>
Auf Android-Geräten können nicht mehr Apps über die Unternehmensportal-Website installiert werden, es sei denn, die Geräte wurden mithilfe der Intune-Unternehmensportal-App für Android in Intune registriert.
<!---TFS 1299082--->

#### iOS
- **Änderungen an den Geräteregistrierungs-Manager-Konten in der iOS-Unternehmensportal-App**<br/>
Zum Verbessern der Leistung und Skalierung zeigt Intune nicht mehr alle Geräte des Geräteregistrierungs-Managers (Device Enrollment Manager, DEM) im Bereich **Meine Geräte** der Unternehmensportal-App für iOS an. Nur das lokale Gerät, das die App ausführt, wird angezeigt, und dies nur, wenn es über die Unternehmensportal-App registriert wurde.

Der DEM-Benutzer kann Aktionen auf dem lokalen Gerät ausführen, aber die Remoteverwaltung der anderen registrierten Geräte kann nur über die Intune-Verwaltungskonsole ausgeführt werden. Darüber hinaus wird in Intune die Verwendung von DEM-Konten mit dem Apple-Geräteregistrierungsprogramm oder dem Apple Configurator-Tool eingestellt. Diese beiden Registrierungsmethoden unterstützen bereits die benutzerunabhängige Registrierung für gemeinsam genutzte iOS-Geräte.

Verwenden Sie DEM-Konten nur, wenn die benutzerunabhängige Registrierung für gemeinsam genutzte Geräte nicht verfügbar ist. Weitere Informationen siehe [Registrieren von firmeneigenen Geräten mit dem Geräteregistrierungs-Manager in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### Ändern von Namen für Windows-Features
- [Microsoft Passport für Windows](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) heißt jetzt **Windows Hello for Business**.
- [Unternehmensdatenschutz](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) heißt jetzt **Windows Information Protection**.

## Juni 2016
### Status des Intune-Diensts
Informationen zum Status des Intune-Diensts wurden wie für andere Microsoft-Dienste an einen zentralen Speicherort verschoben. Sie finden diese Informationen jetzt im Verwaltungsportal von Office 365 unter „Dienststatus“. Weitere Informationen finden Sie in [diesem Blogbeitrag](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### App-Verwaltung
- **Höhere Benutzerfreundlichkeit bei der Richtlinienkonfiguration für Unternehmensdaten in Windows 10.** Wir haben die Benutzerfreundlichkeit bei der Richtlinienkonfiguration für den Windows 10-Unternehmensdatenschutz verbessert. Dabei wurden Aufgaben wie das Erstellen von App-Regeln, das Festlegen von Definitionen für Netzwerkgrenzen und andere Einstellungen für den Unternehmensdatenschutz vereinfacht. Weitere Informationen finden Sie unter [Create an enterprise data protection (EDP) policy using Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) (Erstellen einer Enterprise Data Protection-Richtlinie (EDP) mithilfe von Microsoft Intune).


### Geräteverwaltung
- **Windows Defender-Richtlinieneinstellung zum Schutz gegen potenziell unerwünschte Apps.** Die allgemeine Konfigurationsrichtlinie für Windows 10 Desktop und Mobile wurde um die neue Windows Defender-Einstellung **Erkennung möglicherweise unerwünschter Anwendungen** erweitert. Mit dieser Einstellung können registrierte Windows-Desktopcomputer gegen Software geschützt werden, die von Windows Defender als möglicherweise unerwünscht eingestuft wird. Sie können verhindern, dass diese Anwendungen ausgeführt werden, oder den Überwachungsmodus verwenden, um zu melden, wenn eine möglicherweise unerwünschte Anwendung installiert wird. Weitere Informationen finden Sie unter [Einstellungen für Windows 10-Richtlinien in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).
<!---TFS 1244478--->

### Bedingter Zugriff
- **Cisco ISE-Netzwerkzugriffssteuerungs-Richtlinie für Intune.**  Kunden, die Cisco Identity Service Engine (ISE) 2.1 und Microsoft Intune verwenden, können eine Netzwerkzugriffssteuerungs-Richtlinie in ISE festlegen.

    Bei Verwendung dieser Richtlinie müssen Geräte, die sich über WLAN oder VPN verbinden müssen, die folgenden Voraussetzungen erfüllen, bevor sie Zugriff erhalten:

    * Die Geräte müssen über Intune verwaltet werden
    * Die Geräte müssen mit allen bereitgestellten Intune-Konformitätsrichtlinien kompatibel sein

 Endbenutzer mit nicht konformen Geräten werden aufgefordert, sich zu registrieren und jegliche Konformitätsprobleme zu beheben, um Zugriff zu erhalten.
- **Bedingter Zugriff für Browser.** Sie können eine Richtlinie für den bedingten Zugriff für [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md) und [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md) festlegen, sodass nur von unterstützten Webbrowsern auf verwalteten und kompatiblen iOS- und Android-Geräten darauf zugegriffen werden kann. Endbenutzer, die versuchen, sich mit iOS- und Android-Geräten bei Outlook Web Access- (OWA) und SharePoint-Websites anzumelden, werden aufgefordert, ihr Gerät bei Intune zu registrieren und alle Kompatibilitätsprobleme zu beheben, bevor die Anmeldung abgeschlossen werden kann.
<!---TFS 1175844--->

- **Dynamics CRM Online unterstützt den bedingten Zugriff.** Sie können eine Richtlinie für den bedingten Zugriff für [Dynamics CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md) festlegen, sodass nur der Zugriff durch verwaltete und kompatible iOS- und Android-Geräte möglich ist. Endbenutzer, die versuchen, sich bei der mobilen Dynamics CRM-App für iOS und Android anzumelden, werden aufgefordert, sich bei Intune zu registrieren und alle Kompatibilitätsprobleme zu beheben, bevor die Anmeldung abgeschlossen werden kann.
<!---TFS1295358--->

##Aktualisierungen des E-Unternehmensportals

#### Android-Unternehmensportal-App

- Wenn IT-Administratoren die neue Richtlinie „Require that devices disallow installation of apps from unknown sources (Android 4.0+)“ (Geräte dürfen die Installation von Apps aus unbekannten Quellen nicht erlauben (Android 4.0 und höher)) anwenden, wird Endbenutzern mit Geräten mit Android 4.0 oder höher die Meldung „Die Installation von unbekannten Quellen muss deaktiviert sein.“ angezeigt. Benutzer müssen zu **Einstellungen** > **Sicherheit** wechseln und **Unbekannte Quellen** deaktivieren. Durch einen Link in der Konformitätsmeldung erhalten Benutzer mehr [Informationen](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) zu der Meldung und zu dem Grund, aus dem sie dazu aufgefordert werden, die Einstellung zu deaktivieren.

- Wenn IT-Administratoren die neue Richtlinie „Require that devices have enabled scanning of apps for security threats (Android 4.0+)“ (Bei Geräten muss die Option zum Überprüfen von Apps auf Sicherheitsbedrohungen aktiviert sein (Android 4.0 und höher)) anwenden, wird Endbenutzern mit Geräten mit Android 4.0 oder höher die Meldung „Gerät auf Sicherheitsbedrohungen überprüfen.“ angezeigt. Benutzer müssen zu **Einstellungen** > **Google** > **Sicherheit** wechseln und **Gerät auf Sicherheitsbedrohungen überprüfen** aktivieren. Durch einen Link in der Konformitätsmeldung erhalten Benutzer mehr [Informationen](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) zu der Meldung und zu dem Grund, aus dem sie dazu aufgefordert werden, die Einstellung zu aktivieren.

- Wenn IT-Administratoren die neue Richtlinie „USB-Debuggen muss deaktiviert sein (Android 4.2 und höher)“ anwenden, wird Endbenutzern mit Geräten mit Android 4.2 oder höher die Meldung „USB-Debuggen muss deaktiviert sein.“ angezeigt. Benutzer müssen zu **Einstellungen** > **Entwickleroptionen** wechseln und **USB-Debuggen** deaktivieren. Durch einen Link in der Konformitätsmeldung erhalten Benutzer mehr [Informationen](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) zu der Meldung und zu dem Grund, aus dem sie dazu aufgefordert werden, die Einstellung zu deaktivieren.

- Wenn IT-Administratoren die neue Richtlinie „Niedrigste zulässige Android-Sicherheitspatchebene (Android 6.0 und höher)“ anwenden, wird Endbenutzern mit Geräten mit Android 6.0 oder höher die Meldung „Dieses Gerät weist nicht die mindestens erforderliche Ebene für Android-Sicherheitspatches auf.“ angezeigt. Benutzer müssen den erforderlichen Sicherheitspatch installieren. Durch einen Link in der Konformitätsmeldung erhalten Benutzer mehr [Informationen](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) dazu, wie der erforderliche Sicherheitspatch installiert wird und wie Sie sehen können, welcher Sicherheitspatch aktuell installiert ist.

#### iOS-Unternehmensportal-App

- Wenn Endbenutzer branchenspezifische Apps installieren, sehen sie jetzt eine verbesserte Benutzeroberfläche für die App-Installation. Wenn die App-Installation sehr lange dauert, können Benutzer das Gerät manuell synchronisieren, um eine Fortsetzung des Synchronisierungsprozesses zu erzwingen. Die Anweisungen für Endbenutzer finden Sie unter [Manuelles Synchronisieren des Geräts](/Intune/EndUser/sync-your-device-manually-ios).

- Die Microsoft Windows Intune-Unternehmensportal-App für iOS wurde aktualisiert, um die iOS-Version 8.0 und höher zu unterstützen. Dieses Update bedeutet, dass Endbenutzer nur dann die Unternehmensportal-App installieren und neue Geräte in Intune registrieren können, wenn das Gerät iOS Version 8.0 oder höher ausführt. Benutzer, die bereits Geräte registriert haben, auf denen eine nicht unterstützte Version von iOS ausgeführt wird, können weiterhin die auf ihrem Gerät vorhandene Unternehmensportal-App verwenden.


## Mai 2016

Alle diese Features werden auch für hybride Bereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen Hybridfeatures finden Sie auf unserer [Seite mit neuen Hybridfeatures](https://technet.microsoft.com/en-us/library/mt718155.aspx).

### Dokumentation
Willkommen bei der Preview-Version von [docs.microsoft.com](https://docs.microsoft.com/en-us/intune)!
Dies ist eine vollständig neue, moderne Inhaltsplattform, die Ihnen, unseren Kunden, helfen soll, Intune zu verstehen und zu nutzen.
Weitere Informationen zu allen neuen Features finden Sie unter [docs.microsoft.com: Einführung](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/).

### Status des Intune-Diensts
Informationen zum Status des Intune-Diensts wurden wie für andere Microsoft-Dienste an einen zentralen Speicherort verschoben. Sie finden diese Informationen jetzt im [Verwaltungsportal von Office 365](https://portal.office.com/Admin/Default.aspx) unter **Dienststatus**.
Weitere Informationen finden Sie in [diesem Blogbeitrag](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).


### App-Verwaltung
- **MAM SDK: Unterstützung für die Konfiguration der PIN-Länge.** Sie können die Länge der PIN für MAM-Apps angeben, ähnlich wie eine Geräte-PIN. Dazu müssen Endbenutzer die neuen Einschränkungen einhalten, die Sie festlegen. Sie sehen einen leicht abgewandelten PIN-Bildschirm, mit dem längere Eingaben möglich sind. Weitere Informationen finden Sie unter [MAM-Richtlinien für Android](android-mam-policy-settings.md) und [MAM-Richtlinien für iOS](ios-mam-policy-settings.md).

- **Skype for Business für iOS und Android.** Sie können jetzt Skype for Business mit [MAM ohne Registrierungsrichtlinien](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md) einrichten. Sobald Benutzer angemeldet sind, werden die MAM-Richtlinien angewendet.

- **Neue Apps für die Verwaltung mit MAM-Richtlinien verfügbar.** Die Apps Microsoft Word, Excel und PowerPoint für Android können jetzt MAM-Richtlinien auf Geräten zugeordnet werden, die nicht bei Intune registriert sind. Die vollständige Liste der unterstützten Apps finden Sie im Microsoft Intune-Katalog mit mobilen Anwendungen auf der Seite mit den [Microsoft Intune-Anwendungspartnern](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).


### Aktualisierungen am Unternehmensportal

#### Android-Unternehmensportal-App
- **Popupbenachrichtigungen für Endbenutzer**: Endbenutzer sehen jetzt Popupbenachrichtigungen in der Android-Unternehmensportal-App, wenn Sie ihre Geräte im Unternehmensportal registrieren oder sie daraus entfernen.

- **Änderungen an den Geräteregistrierungs-Manager-Konten in der Android-Unternehmensportal-App.** Zum Verbessern der Leistung und Skalierung zeigt Intune nicht mehr alle Geräte des Geräteregistrierungs-Managers (Device Enrollment Manager, DEM) im Bereich „Meine Geräte“ der Android-Unternehmensportal-App an. Nur das lokale Gerät, das die App ausführt, wird angezeigt, und dies nur, wenn es über die Unternehmensportal-App registriert wurde. Der DEM-Benutzer kann Aktionen auf dem lokalen Gerät ausführen, aber die Remoteverwaltung der anderen registrierten Geräte kann nur über die Intune-Verwaltungskonsole ausgeführt werden.

#### Unternehmensportal-Website
- **Unternehmensportal-Website: Banner für die Geräteidentifikation stellt zusätzliche Informationen für Endbenutzer bereit.** Benutzer können das ausgewählte Gerät nun leichter identifizieren, wenn sie die Unternehmensportal-Website verwenden. Wenn das falsche Gerät ausgewählt wird, können sie das richtige Gerät auswählen, indem sie auf den Link **Hier tippen** im Banner auf der Startseite tippen.

## Was steht an?
- **Integration des Nachrichtencenters**. Im Rahmen der Migration von Intune in das [Office 365-Verwaltungsportal](https://portal.office.com/) beginnen wir damit, das Nachrichtencenter zu nutzen, um über neue Features und andere Benachrichtigungen zu informieren. Wenn Sie zudem die mobile Begleit-App Office 365 Admin installieren, können Sie Benachrichtigungen auf Ihrem Mobiltelefon empfangen und problemlos alle Nachrichten an Benutzer oder einen Verteilungsalias weiterleiten.
Wir beginnen mit unserer Maiversion damit, das Nachrichtencenter zu nutzen, um Sie zu benachrichtigen, wenn Updates abgeschlossen sind, und wir werden Informationen zu neuen und verbesserten Features von Intune aufnehmen. Sehen Sie sich das Nachrichtencenter noch heute an, indem Sie sich beim [Office 365-Verwaltungsportal](https://portal.office.com/) anmelden und im linken Navigationsbereich die Option NACHRICHTENCENTER auswählen.

- **Änderungen an den Konten für Geräteregistrierungs-Manager**. Zum Verbessern der Leistung und Skalierung zeigt Intune nicht mehr **alle** Geräte des Geräteregistrierungs-Managers (Device Enrollment Manager, DEM) im Bereich **Meine Geräte** der iOS-Unternehmensportal-App an. Nur das lokale Gerät, das die App ausführt, wird angezeigt, und dies nur, wenn es über die Unternehmensportal-App registriert wurde. Der DEM-Benutzer kann Aktionen auf dem lokalen Gerät ausführen, aber die Remoteverwaltung der anderen registrierten Geräte kann nur über die Intune-Verwaltungskonsole ausgeführt werden. Darüber hinaus wird in Intune die Verwendung von DEM-Konten mit dem Apple-Geräteregistrierungsprogramm oder dem Apple Configurator-Tool eingestellt. Diese beiden Registrierungsmethoden unterstützen bereits die benutzerunabhängige Registrierung für gemeinsam genutzte iOS-Geräte. Verwenden Sie DEM-Konten nur, wenn die benutzerunabhängige Registrierung für gemeinsam genutzte Geräte nicht verfügbar ist.

### Fahrplan für die Cloud
Halten Sie sich mit dem [Fahrplan für die Cloudplattform](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune) zu den anstehenden Entwicklungen für Intune auf dem Laufenden.

### Veraltete Dienste
- **Intune Viewer-Apps.** Mit der Veröffentlichung der neuen RMS-Freigabe-App werden wir ab August 2016 die folgenden Intune Viewer-Apps entfernen:
    - Intune AV Viewer
    - Intune PDF Viewer
    - Intune Image Viewer für Android aus Google Play

  Anstatt die Intune-Viewer-Apps zu verwenden, empfehlen wir die Nutzung der neuen Rights Management-App (RMS-Freigabe) für Android, die Ihnen das Bereitstellen einer App anstelle von drei getrennten Apps ermöglicht, um Unternehmensdateien sicher auf Android-Geräten anzuzeigen. Weitere Informationen zur RMS-Freigabe-App (mit Link zur Dokumentation).

- **Entfernung der Zielgruppenadressierung benutzerdefinierter Gruppen bei Benachrichtigungsregeln.**
Intune-Benachrichtigungsregeln definieren, an wen aus Intune eine E-Mail-Benachrichtigung gesendet wird. Derzeit können Sie Benachrichtigungsregeln zum Senden von E-Mails an alle Benutzer von Geräten in einer Intune-Gerätegruppe konfigurieren, die Sie erstellt haben. Ab Anfang Juni 2016 wird die Adressierung von Gruppen, die von Benutzern erstellt wurden, nicht mehr unterstützt.

    Mittlerweile müssen Sie eine Benachrichtigungsregel einer Gruppe, die Sie in der Microsoft Intune-Verwaltungskonsole erstellt haben, wie folgt zuordnen:

    Klicken Sie im Arbeitsbereich **Verwaltung** auf **Benachrichtigungsregeln** > **Neue Regel erstellen**.

    In Schritt 2 des Assistenten zum Erstellen von Benachrichtigungsregeln wählen Sie die Gerätegruppen aus, für die die Regel gelten soll. Der Schritt „Gerätegruppen auswählen“ wurde aus der Intune-Konsole entfernt.

    Der vorläufige Zeitplan für diese Änderung ist wie folgt:
    - Im Juni 2016 wird neuen Mandanten Schritt 2 im Assistenten zum Erstellen von Benachrichtigungsregeln nicht mehr angezeigt. Vorhandene Mandanten sind nicht betroffen.
    - Ab August 2016 wird einigen vorhandenen Mandanten der Schritt „Gerätegruppen auswählen“ im Assistenten nicht angezeigt.
    - Ab Oktober 2016 wird für alle Mandanten der Schritt „Gerätegruppen auswählen“ im Assistenten nicht mehr angezeigt.


- **Änderungen bei der Unterstützung der iOS-Unternehmensportal-App**. In den kommenden Monaten erfolgt ein Update für die Microsoft Intune-Unternehmensportal-App für iOS, die nur Geräte mit mindestens iOS 8.0 unterstützt. Benutzer können neue Geräte mit Versionen unter iOS 8.0 nicht registrieren. Registrierte Geräte mit Versionen unter iOS 8.0 werden weiterhin verwaltet und können für einen begrenzten Zeitraum die Unternehmensportal-App weiter nutzen. Für den Zugriff auf die neuesten Versionen der Unternehmensportal-App benötigen Geräte mindestens die iOS-Version 8.0. Wir empfehlen Ihnen, Benutzer zum Update auf iOS 8.0 oder höher aufzufordern, damit sie in den vollen Genuss der neuen Intune-Features kommen.  


## April 2016
Alle diese Features werden auch für hybride Kundenbereitstellungen (Configuration Manager integriert in Intune) unterstützt.
### App-Verwaltung
- **MAM-Benutzerkompatibilität.**
Sie können nun den [Status](monitor-mobile-app-management-policies-with-Microsoft-Intune.md) von Anwendungsverwaltungsrichtlinien für alle Benutzer in Ihrem Azure Active Directory-Mandanten (AAD) anzeigen. Dies umfasst u. a.:
   - Geräte
   - Apps auf dem Gerät

   Statuswerte:

   **Eingecheckt**: Gibt an, dass die Richtlinie dem Benutzer bereitgestellt wurde, dass die App im Kontext verwendet wurde und dass sie die Richtlinie erfolgreich empfangen hat.

    **Nicht eingecheckt**: Gibt an, dass die Richtlinie dem Benutzer bereitgestellt wurde, die App seitdem aber nicht im Arbeitskontext verwendet wurde.


- **MAM-Steuerelemente, um die Synchronisierung von Outlook-Kontakten zu verhindern (Android).**
Eine neue Einstellung ist für die [Verwaltung mobiler Anwendungen](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) ohne Registrierung des Geräts verfügbar. Mit dieser Einstellung kann verhindert werden, dass eine Anwendung Kontakte mit dem nativen Adressbuch auf Android-Geräten synchronisiert. Wenn diese Einstellung aktiviert ist, können Zielanwendungen Kontakte nicht mehr im nativen Adressbuch speichern. Wenn diese Einstellung deaktiviert ist, können Zielanwendungen Kontakte im nativen Adressbuch speichern. Wenn Sie [ein Gerät oder eine App remote zurücksetzen](wipe-managed-company-app-data-with-Microsoft-Intune.md), werden alle Kontakte entfernt, die bereits im nativen Adressbuch gespeichert wurden. Diese neue Einstellung wird zunächst von der Outlook-Anwendung auf Android-Geräten unterstützt.

### Geräteverwaltung
- **Telefonnummeridentifikation für unternehmenseigene Geräte.** Telefone, die als „Unternehmen“ eingestuft sind, werden jetzt mit der vollständigen Telefonnummer identifiziert, wenn Sie beispielsweise einen Inventurbericht für mobile Geräte ausführen. BYOD-Telefonnummern werden weiterhin mit *** maskiert, und nur die letzten vier Ziffern werden angezeigt.


### Aktualisierungen am Unternehmensportal
**Android-Unternehmensportal-App** Benutzer, die ihre Geräte nicht bei Intune registriert haben und die nicht das richtige Zertifikat installiert haben, können sich nicht bei der Android-Unternehmensportal-App anmelden. Ihnen wird die Meldung angezeigt, dass eine Anmeldung nicht möglich sei, da ein erforderliches Zertifikat auf dem Gerät nicht vorhanden sei. Die Meldung enthält einen Link zum Beheben dieses Problems, den Benutzer nutzen können, um eine Anleitung zum Installieren des Zertifikats zu erhalten. Die Schritte, denen die Endbenutzer folgen, um das Problem zu beheben, finden Sie unter [Auf Ihrem Gerät ist ein erforderliches Zertifikat nicht vorhanden](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing).

**iOS-Unternehmensportal-App** Unterstützung für die Aktion „Zum Aktualisieren ziehen“ wurde hinzugefügt, um den Inhalt auf dem Startbildschirm zu aktualisieren, einschließlich der aufgelisteten Apps und Geräte sowie der IT-Kontaktinformationen. Mit der Aktion „Zum Aktualisieren ziehen“ werden Kompatibilitäts- oder Richtlinieninformationen nicht überprüft. Sie erreichen dies, indem Sie die Kachel für das aktuelle Gerät auswählen und auf die Schaltfläche **Synchronisieren** tippen.

**Windows 10 Mobile- und Windows Phone 8.1-Unternehmensportal-App** Wenn Endbenutzer branchenspezifische Apps installieren, sehen sie jetzt eine verbesserte Benutzeroberfläche für die App-Installation. Wenn die App-Installation sehr lange dauert, können Benutzer das Gerät manuell synchronisieren, um eine Fortsetzung des Synchronisierungsprozesses zu erzwingen. Die Anweisungen für Endbenutzer finden Sie unter [Manuelles Synchronisieren des Geräts, um Anwendungsinstallationen zu beschleunigen](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually).

**Unternehmensportal-Website** Wenn Windows 10 Mobile- und Windows Phone 8.1-Benutzer branchenspezifische Apps installieren, sehen sie jetzt die folgenden neuen Status, die ihnen weitere Details zum Status ihrer Installation zur Verfügung zu stellen:

* **Gerätesynchronisierung ausstehend**: Der Benutzer hat auf „Installieren“ getippt hat, und das Gerät versucht nun, eine Synchronisierung mit der Intune-Infrastruktur durchzuführen. Die Synchronisierung ist erforderlich, bevor die Installation abgeschlossen werden kann. Die Meldung „Gerätesynchronisierung ausstehend“ ist außerdem ein Link, auf den Benutzer tippen können, um die [Anweisungen](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) zum manuellen Synchronisieren ihres Geräts mit Intune anzuzeigen, wenn die Synchronisierung sehr lange dauert oder unterbrochen wird.
* **Wird heruntergeladen**: Die Downloadanforderung des Benutzers wird verarbeitet, und das Gerät lädt die App herunter und installiert sie.

Bevor diese Statusangaben hinzugefügt wurden, waren die Benutzer verunsichert, wenn die Installation einer App sehr lange dauerte, da nur ein Status „Wird installiert“ angezeigt wurde – und das möglicherweise für Stunden. Das Hinzufügen der neuen Statusangaben bedeutet, dass sich Benutzer nicht an den Support wenden müssen, sondern auf den Link „Gerätesynchronisierung ausstehend“ tippen und den Anweisungen folgen können, um die Fortsetzung des Synchronisierungsprozesses zu erzwingen.


## März 2016
### Neuheiten seit dem 29. März 2016
Mit Ausnahme des Updates auf die allgemeine Windows 10-Konfigurationsrichtlinie werden alle Funktionen, die am 29. März 2016 freigegeben wurden, auch für hybride Kundenbereitstellungen unterstützt (in Intune integrierter Configuration Manager). Die Hybridunterstützung für die Aktualisierung der allgemeinen Windows 10-Konfigurationsrichtlinie ist bald erhältlich. Beachten Sie, dass für einige dieser Features die neueste Version von Configuration Manager erforderlich sein kann.

### App-Verwaltung
- **MAM-Steuerelemente zum Verhindern der Synchronisierung von Outlook-Kontakten (iOS).** Eine neue Einstellung ist für die Verwaltung mobiler Anwendungen ohne Geräteregistrierung verfügbar. Mit dieser Einstellung kann verhindert werden, dass eine Anwendung Kontakte mit dem nativen Adressbuch auf iOS-Geräten synchronisiert. Wenn diese Einstellung aktiviert ist, kann die App keine Kontakte mehr im nativen Adressbuch speichern. Wenn diese Einstellung deaktiviert ist, kann die App Kontakte im nativen Adressbuch speichern. Wenn Sie ein Gerät oder eine App selektiv zurücksetzen, werden alle Kontakte entfernt, die bereits im nativen Adressbuch gespeichert wurden. Diese neue Einstellung wird von der Outlook-Anwendung auf iOS-Geräten unterstützt. Weitere Informationen zu diesen und anderen Einstellungen finden Sie unter [Erstellen und Bereitstellen von MAM-Richtlinien](https://technet.microsoft.com/en-us/library/dn292747.aspx).

### Zugriffssteuerung
- **Skype for Business Online unterstützt bedingten Zugriff.** Sie können eine Richtlinie für bedingten Zugriff für Skype for Business Online festlegen, sodass nur verwaltete und kompatible iOS- und Android-Geräte darauf zugreifen können. Endbenutzer, die versuchen, sich bei der mobilen Skype for Business-App für iOS und Android anzumelden, werden aufgefordert, sich bei Intune zu registrieren und alle Kompatibilitätsprobleme zu beheben, bevor die Anmeldung abgeschlossen werden kann. Weitere Informationen finden Sie unter [Verwalten des Zugriffs auf Skype for Business Online](https://technet.microsoft.com/en-us/library/mt695297.aspx).

### Geräteverwaltung
- **Intune-Unterstützung für iOS 9.3.** Am Montag, dem 21. März, verkündete Apple die Verfügbarkeit von iOS 9.3. Wir haben daran gearbeitet, Microsoft Intune mit der neuesten Version des Apple-Betriebssystems für Mobilgeräte kompatibel zu machen, und [geben hiermit bekannt, dass Intune die Verwaltung von iOS 9.3-Geräten unterstützt](https://blogs.technet.microsoft.com/microsoftintune/2016/03/23/microsoft-intune-provides-support-for-ios-9-3/).

  Alle vorhandenen Intune-Features, die derzeit für die Verwaltung von iOS-Geräten verfügbar sind, werden weiterhin reibungslos funktionieren, wenn Benutzer ihre Geräte auf iOS 9.3 aktualisieren. Außerdem wird iOS 9.3 auch jetzt für hybride Kundenbereitstellungen (Configuration Manager integriert in Intune) unterstützt.

- **Die allgemeine Windows 10-Konfigurationsrichtlinie enthält jetzt Einstellungen für die Verwaltung von Windows Defender auf registrierten Windows 10-PCs.** Weitere Informationen finden Sie unter [Einstellungen für Windows 10-Konfigurationsrichtlinien in Microsoft Intune](https://technet.microsoft.com/en-us/library/mt404697.aspx).


### Unternehmensportal

- **Windows-App-Pakete stehen direkt über die Website des Unternehmensportals zur Verfügung.** Benutzer von Windows 8-, Windows 8.1- und Windows RT-PCs können Windows-App-Pakete (mit der Erweiterung APPX) nun direkt von der Website des Unternehmensportals installieren. Zuvor mussten Sie sie bereitstellen, oder die Benutzer mussten die Unternehmensportal-App auf ihren Geräten installieren, um Apps zu installieren.

- **Benutzer können ihre Geräte remote über die Website des Unternehmensportals sperren.** Eine neue Option für Remotesperren wurde der Website des Unternehmensportals hinzugefügt, damit die Benutzer ihr Gerät bei Verlust oder Diebstahl über das Portal remote sperren können. Informationen finden Sie in den [Endbenutzeranweisungen](https://technet.microsoft.com/library/mt590895.aspx/?wt.mc_id=ui#BKMK_iwp_remote_lock). Die folgende Tabelle enthält eine Übersicht über die Plattformunterstützung für Remotesperren für eigenständiges Intune und Intune mit Configuration Manager.

|Plattform | Details zur Unterstützung|
|---------|----------------|
|Android |Unterstützt|
|iOS |Unterstützt|
|Windows 10 Mobile |Wird nur unterstützt, wenn für das Telefon eine Kennung festgelegt wurde|
|Windows 10 Desktop |Nicht unterstützt|
|Windows Phone 8.1 |Wird nur unterstützt, wenn für das Telefon eine Kennung festgelegt wurde|
|Windows Phone 8.0 |Nicht unterstützt|
|PC (Windows 8.0 und früher) |Nicht unterstützt|
|PC (Windows 8.1) |Nicht unterstützt|

### Neuheiten seit dem 10. März 2016

### App-Verwaltung

- **Verwenden der Verwaltungsfunktionen für mobile Geräte des Drittanbieters, dass die iOS-Verwaltungsfunktion „Öffnen in“ genutzt wird** Sie können die Verwaltungsfunktionen für mobile Geräte des Drittanbieters so verwenden, dass die iOS-Verwaltungsfunktion „Öffnen in“ genutzt wird. Sie können die Einschränkungen in den Konfigurationsprofileinstellungen festlegen und die App anhand der Informationen unter [Verwalten der Datenübertragung zwischen iOS-Apps](manage-data-transfer-between-ios-apps-with-microsoft-intune.md) bereitstellen.

     Dieser Ansatz hat zwei wesentliche Vorteile:

     1. Benutzer müssen sich bei ihrem Geschäftskonto anmelden, bevor sie Zugriff auf Unternehmensdaten in Clouddiensten oder anderen Apps erhalten. Dadurch wird sichergestellt, dass die Richtlinien für die Verwaltung mobiler Geräte (Mobile App Management, MAM) gelten, wenn auf die Daten zugegriffen wird.

     2. Verwaltete E-Mail-Profile und andere über die MDM-Lösung eines Drittanbieters verwaltete Apps können Dateien und Daten mit den Apps gemeinsam nutzen, die über Intune MAM-Richtlinien verfügen.

- **Verwalten der Microsoft Outlook-App mit MAM-Richtlinien für nicht in Intune registrierte Geräte** Sie können jetzt die Microsoft Outlook-App auf Geräten verwalten, die nicht mithilfe der Intune-Richtlinie für die Verwaltung mobiler Anwendungen in Intune registriert sind. Die aktualisierte Microsoft Outlook-App mit den MAM-Funktionen ist sowohl für [iOS](https://itunes.apple.com/us/app/microsoft-outlook-email-calendar/id951937596?mt=8)- als auch für [Android](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook)-Geräte verfügbar. Verwenden Sie die Anweisungen im Abschnitt [Erstellen und Bereitstellen von Verwaltungsrichtlinien für mobile Apps](https://technet.microsoft.com/library/mt627829.aspx), um eine MAM-Richtlinie zu erstellen.  


- **Konfigurationsrichtlinien für mobile Apps bieten mehr Flexibilität beim Angeben von Benutzerinformationen für iOS-Apps** Sie können Benutzereinstellungen angeben, die eine iOS-App beim Öffnen möglicherweise benötigt. Sie können beispielsweise einen Netzwerkport oder Benutzernamen angeben. Weitere Informationen finden Sie unter [Konfigurieren von iOS-Apps mit Konfigurationsrichtlinien für mobile Apps in Microsoft Intune](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md).


- **Bereitstellen von Adobe Reader für Microsoft Intune für von Intune verwaltete iOS-Geräte in Ihrem Unternehmen** Die Adobe Reader-App für iOS kann jetzt auf registrierten Geräten mit der Intune-Richtlinie für die Verwaltung mobiler Anwendungen verwaltet werden.

- **Sicherstellen, dass bereitgestellte Webclips im Managed Browser geöffnet werden** Sie können zielabhängige Webclips bereitstellen, die auf iOS- und Android-Geräten nur im Managed Browser geöffnet werden können. Angenommen, Sie stellen Links zu Unternehmensressourcen über das Unternehmensportal bereit. Wenn Benutzer zu den Links navigieren, werden diese direkt im Managed Browser geöffnet, in dem sie durch die MAM-Richtlinie geschützt werden können. Weitere Informationen finden Sie unter [Bereitstellen von Apps](deploy-apps.md).


- **Suchen, Verwalten und Verteilen von Windows Store für Unternehmen-Apps für Windows 10-Geräte in der Intune-Verwaltungskonsole** Intune bietet Unterstützung für Windows Store für Unternehmen und hilft beim Suchen, Verwalten und Verteilen von Apps auf Windows 10-Geräten, die Sie verwalten. Windows Store für Unternehmen ermöglicht Ihnen die Bereitstellung und Überwachung dieser Apps in der Intune-Verwaltungskonsole, die Sie bereits für die Verwaltung anderer Apps nutzen. Insbesondere verwaltet Windows Store für Unternehmen den Inhalt und die Lizenzierung von „online lizenzierten Apps“. Weitere Informationen finden Sie unter [Verwalten von Apps, die im Windows Store für Unternehmen erworben wurden](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md).


### Geräteverwaltung
- **Verteilen von PFX-Zertifikaten an iOS-Geräte** Intune-Administratoren können iOS-PFX-Zertifikate für die WLAN-, E-Mail- und VPN-Authentifizierung auf iOS-Geräten erstellen und bereitstellen. Diese Funktion ist bereits für Android- und Windows 10-Geräte verfügbar. Weitere Informationen finden Sie unter [Aktivieren des Zugriffs auf Unternehmensressourcen mithilfe von Zertifikatprofilen](secure-resource-access-with-certificate-profiles.md).


- **Anwenden von Apps und Richtlinien auf verschiedene Gerätegruppen basierend auf der Benutzerkategorieauswahl** Intune-Administratoren können jetzt benutzerdefinierte Gerätekategorien für Benutzer definieren, aus deren während der Registrierung ausgewählt werden kann. Administratoren können beispielsweise die Benutzer bitten anzugeben, ob sie ein Gerät für „Kasse“, „Lieferfahrzeug“ oder „Lagerraum“ registrieren. Die ausgewählte Kategorie sorgt dafür, dass das Gerät Mitglied einer Intune-Gerätegruppe wird, die für die Bereitstellung anderer Apps und Richtlinien für das registrierte Gerät verwendet werden kann. Weitere Informationen finden Sie unter [Kategorisieren von Geräten mithilfe der Zuordnung von Gerätegruppen](categorize-devices-with-device-group-mapping-in-microsoft-intune.md).

### Änderungen und Updates für das Unternehmensportal von Microsoft
In dieser Version wurden die folgenden Änderungen am Unternehmensportal vorgenommen:

**Android-Unternehmensportal-App**

* Wenn Ihre Benutzer eine App starten, die durch die mobile Anwendungsverwaltung (MAM) verwaltet wird, wird ihnen eine Meldung angezeigt, die sie darüber benachrichtigt, dass die App von ihrem Unternehmen verwaltet wird. Benutzer können jetzt auf einen Link zu weiteren Informationen tippen, um hier [weitere Informationen](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_use_mgd_apps) zur Bedeutung von „verwalteten Apps“ zu erhalten. Sie können auch auf die Option „Nicht mehr anzeigen“ tippen, damit die Nachricht beim Starten der App nicht mehr angezeigt wird.
* Es wurden neue Bildschirme hinzugefügt, um die Benutzer durch den Registrierungsprozess zu leiten und weitere Informationen dazu bereitzustellen, warum sich Benutzer registrieren sollten. Zudem werden Informationen angezeigt, welche IT-Administratoren ihre registrierten Geräte anzeigen können und welche dazu nicht in der Lage sind. Weitere Informationen finden Sie in den [Registrierungsanweisungen](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc).
* Fehlermeldungen für die Registrierung werden jetzt in der Unternehmensportal-App angezeigt. Zuvor wurden diese Nachrichten auf der Unternehmensportal-Website angezeigt. Durch diese Änderung werden alle Fehlermeldungen jetzt an einem und nicht an zwei verschiedenen Orten angezeigt.


**iOS-Unternehmensportal-App**
* Wenn Ihre Benutzer eine App starten, die durch die mobile Anwendungsverwaltung (MAM) verwaltet wird, wird ihnen eine Meldung angezeigt, die sie darüber benachrichtigt, dass die App von ihrem Unternehmen verwaltet wird. Benutzer können jetzt auf einen Link zu weiteren Informationen tippen, um hier [weitere Informationen](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_use_mgd_apps) zur Bedeutung von „verwalteten Apps“ zu erhalten. Sie können auch auf die Option „Nicht mehr anzeigen“ tippen, damit die Nachricht beim Starten der App nicht mehr angezeigt wird.
* Es wurden neue Bildschirme hinzugefügt, um die Benutzer durch den Registrierungsprozess zu leiten und weitere Informationen dazu bereitzustellen, warum sich Benutzer registrieren sollten. Zudem werden Informationen angezeigt, welche IT-Administratoren ihre registrierten Geräte anzeigen können und welche dazu nicht in der Lage sind. Weitere Informationen finden Sie in den [Registrierungsanweisungen](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device).
* Fehlermeldungen für die Registrierung werden jetzt in der Unternehmensportal-App angezeigt. Zuvor wurden diese Nachrichten auf der Unternehmensportal-Website angezeigt. Durch diese Änderung werden alle Fehlermeldungen jetzt an einem und nicht an zwei verschiedenen Orten angezeigt.




## Februar 2016
### Änderungen und Updates für das Unternehmensportal von Microsoft

In dieser Version wurden die folgenden Änderungen am Unternehmensportal vorgenommen:

#### Android-Unternehmensportal-App
- Es wurden neue Bildschirme hinzugefügt, um die Benutzer durch den Registrierungsprozess zu leiten und weitere Informationen dazu bereitzustellen, warum sich Benutzer registrieren sollten. Zudem werden Informationen angezeigt, welche IT-Administratoren ihre registrierten Geräte anzeigen können und welche dazu nicht in der Lage sind. Weitere Informationen finden Sie in den [Registrierungsanweisungen](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc).
- Fehlermeldungen für die Registrierung werden jetzt in der Unternehmensportal-App angezeigt. Zuvor wurden diese Nachrichten auf der Unternehmensportal-Website angezeigt. Durch diese Änderung werden alle Fehlermeldungen jetzt an einem und nicht an zwei verschiedenen Orten angezeigt.

#### iOS-Unternehmensportal-App
 - Es wurden neue Bildschirme hinzugefügt, um die Benutzer durch den Registrierungsprozess zu leiten und weitere Informationen dazu bereitzustellen, warum sich Benutzer registrieren sollten. Zudem werden Informationen angezeigt, welche IT-Administratoren ihre registrierten Geräte anzeigen können und welche dazu nicht in der Lage sind. Weitere Informationen finden Sie in den [Registrierungsanweisungen](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device).

 - Fehlermeldungen für die Registrierung werden jetzt in der Unternehmensportal-App angezeigt. Zuvor wurden diese Nachrichten auf der Unternehmensportal-Website angezeigt. Durch diese Änderung werden alle Fehlermeldungen jetzt an einem und nicht an zwei verschiedenen Orten angezeigt.


## Januar 2016

### Nutzen von Windows 10-Features
* **Bedingter Zugriff mit dem Integritätsnachweisdienst** Intune-Administratoren können jetzt den Status des Windows 10-Nachweises zur Geräteintegrität in der Intune-Verwaltungskonsole anzeigen. Mit dem Nachweis der Geräteintegrität kann der Administrator sicherstellen, dass Clientcomputer über vertrauenswürdige BIOS-, TPM- und Bootsoftwarekonfigurationen verfügen. Damit Sie den Nachweis der Geräteintegration unterstützen, müssen die Clientgeräte Windows 10 mit aktiviertem TPM 2 ausführen. Der Nachweis der Geräteintegrität zeigt die Anzahl der Geräte an, die jeweils für Folgendes aktiviert sind:
    * Antischadsoftware-Frühstart
    * BitLocker
    * Sicherer Start
    * Codeintegrität

    Weitere Informationen zum Festlegen der Geräteintegrität, zu erfassten Datenpunkten und zum Integritätsnachweisbericht finden Sie unter [Einführung in Gerätekompatibilitätsrichtlinien für Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md). Die [HAS-Dienstdetails](https://msdn.microsoft.com/en-us/library/dn934876.aspx) erläutern den Dienst ausführlich.

* **Windows 10 Passport for Work-Richtlinie und Zertifikatverwaltung** Intune ermöglicht die [Integration in Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md). Dies ist eine alternative Anmeldemethode für Windows 10, die Active Directory oder ein Azure Active Directory-Konto verwendet, um ein Kennwort, eine Smartcard oder eine virtuelle Smartcard zu ersetzen. Mit Passport können Sie anstelle eines Kennworts eine Benutzeraktion zur Anmeldung verwenden. Eine Benutzeraktion kann eine einfache PIN, eine biometrische Authentifizierung wie Windows Hello oder ein externes Gerät sein, z. B. ein Fingerabdruckleser.

* **VPN für bestimmte Apps** Sie können Apps auswählen, die automatisch eine Verbindung zum Unternehmensnetzwerk über VPN herstellen. Erstellen Sie die Liste der Apps bei der Einrichtung des VPN-Profils, wie unter „Benutzer beim Herstellen einer Verbindung zu ihren VPN-Profilen mit Microsoft Intune unterstützen“.

* **Unterstützung für vollständiges Zurücksetzen unter Windows 10** Sie können jetzt eine vollständige Remotezurücksetzung von Windows 10-Desktopgeräten starten, die über die Intune-Verwaltungskonsole bei Intune registriert wurden. Bei der vollständigen Zurücksetzung unter Windows 10 wird das Gerät auf die Werkseinstellungen zurückgesetzt.


### VPP-Update (Apple Volume Purchase Program)
Intune kann Sie jetzt beim [Verwalten von Apps unterstützen, die Sie über das Apple Volume Purchase Program (VPP) for Business erworben haben](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md). Dies umfasst die Synchronisierung von Lizenzinformationen zwischen Apple und Intune sowie die Nachverfolgung der Anzahl von Kopien, die Sie von jeder App bereitgestellt haben.

### Verwenden von IMEI-Nummern zum Identifizieren von unternehmenseigenen Geräten
Sie können jetzt für mobile Geräteplattformen, die über eine IMEI-Nummer verfügen, die entsprechenden [IMEI-Nummern (International Mobile Equipment Identity) importieren](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md), um die Identifizierung von unternehmenseigenen mobilen Geräten zu unterstützen. Nach der Registrierung in Intune werden Geräte mit importierten IMEI-Nummern als unternehmenseigene Geräte gekennzeichnet, die zum Anwenden von Richtlinien verwendet werden können, die sich von denen unterscheiden, die auf Geräte angewendet werden, die sich im privaten Besitz befinden.

### Weitere Apps sind jetzt mit Intune MAM-Richtlinien kompatibel.
Weitere Apps von Microsoft-Partnern sind jetzt mit Intune-Verwaltungsrichtlinien für mobile Anwendungen (MAM) kompatibel (für Geräte, die von Intune verwaltet werden):
* Box for EMM (von Box Inc) – nur iOS
* Adobe Reader (von Adobe) – nur Android
* Foxit PDF Reader (von der Foxit Corporation) – iOS und Android


### Unterstützung von Internet Explorer 9 endet im Januar
Ab Februar 2016 wird Internet Explorer 9 nicht mehr als offizieller Browser für den Zugriff auf die Microsoft Intune-Unternehmensportalwebsite, das Intune-Kontoportal und die Intune-Verwaltungskonsole unterstützt. Sie müssen zu Internet Explorer 10 oder höher migrieren.


>[!div class="step-by-step"]

>[&larr; **Neuheiten in Intune**](whats-new-in-microsoft-intune.md)    



<!--HONumber=Sep16_HO2-->


