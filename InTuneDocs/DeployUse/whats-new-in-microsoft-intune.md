---
title: Neuheiten | Microsoft Intune
description: Erfahren Sie, was im Release dieses Monats und in den vergangenen Releases von Microsoft Intune neu ist
keywords: 
author: Lindavr
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b93c6fe16e598c6f4b0d87981de8655f3de9c8d3
ms.openlocfilehash: 051f2994c59b2886a81a50d7c72f51627064bc6a


---

# Neuheiten in Microsoft Intune
Erfahren Sie, was in diesem Release von Microsoft Intune neu ist. Sie erhalten auch Informationen über bevorstehende Änderungen, die Sie einplanen sollten, sowie über vergangene Releases.

Alle diese Features werden letztlich auch für hybride Kundenbereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

## August 2016
## Aktualisierungen am Unternehmensportal

### Android
- **Android-Unternehmensportal-App**<br/>
Die Intune-Unternehmensportal-App für Android bietet „Day-0“-Unterstützung für das bevorstehende Android 7.0-Betriebssystem für mobile Geräte.  

- **Funktion für das Remote-Zurücksetzen von Passcodes auf Android 7.0-Geräten von Google entfernt**<br/>
IT-Administratoren und Endbenutzer von Intune sind nicht in der Lage, den Gerätepasscode auf Android 7.0-Geräten remote zurückzusetzen, da diese Funktion von Google für Android 7.0-Geräte entfernt wurde. Bei Versionen vor Android 7.0 kann ein Benutzerpasscode weiterhin von IT-Administratoren remote zurückgesetzt werden, und Endbenutzer sind weiterhin in der Lage, ihre Passcodes auf der Unternehmensportal-Website zurückzusetzen.

## Juli 2016
## App-Verwaltung
### Verbessern der Benutzererfahrung beim Update des App-Bereitstellungsprofils
Die Apple iOS-Reihe mobiler Geschäfts-Apps wird mit einem integrierten Bereitstellungsprofil erstellt und mit Code, der mit einem Zertifikat signiert wurde. Beim Ausführen der App auf einem iOS-Gerät bestätigt iOS die Integrität der iOS-App und erzwingt Richtlinien, die durch das Bereitstellungsprofil definiert werden.

Das Unternehmenssignaturzertifikat, das Sie zum Signieren von Apps verwenden, ist in der Regel 3 Jahre lang gültig. Allerdings läuft das Bereitstellungsprofil nach 1 Jahr ab. Mit diesem Update stellt Intune Ihnen die Tools zum proaktiven Bereitstellen einer neuen Richtlinie für Bereitstellungsprofile auf Geräten zur Verfügung, auf denen Apps installiert sind, die bald ablaufen, während das Zertifikat noch gültig ist. Weitere Informationen finden Sie unter [Use iOS mobile provisioning profile policies to keep your line of business apps up to date](/intune/deploy-use/ios-mobile-app-provisioning-profiles) (Verwenden von Richtlinien für iOS-Mobilbereitstellungsprofile, um Ihre Business-Apps aktuell zu halten).
<!--- TFS 1280247--->
### Xamarin-SDK für Intune-Apps ist verfügbar
Mit der Intune-App-SDK-Xamarin-Komponente können Sie die Intune-Verwaltungsfeatures für mobile Apps in Ihren mit Xamarin erstellten mobilen iOS- und Android-Apps aktivieren. Sie finden die Komponente im [Xamarin Store](https://components.xamarin.com/view/Microsoft.Intune.MAM) oder auf der [Microsoft Intune-Github-Seite](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

## Geräteverwaltung
### Höhere Limits bei der Geräteregistrierung
Intune erhöhte das maximal konfigurierbare Limit für die Geräteregistrierung von 5 auf 15 Geräte pro Benutzer.
<!---TFS 1289896 --->

### TeamViewer-Integration für Windows-PCs, auf denen die Intune-Clientsoftware ausgeführt wird
Mithilfe der [TeamViewer](https://www.teamviewer.com)-Integration für Windows-PCs, auf denen der Intune-Client ausgeführt wird, können Sie Remoteunterstützungssitzungen mit Windows-PCs herstellen, um Helpdeskabteilungen für Endbenutzer zu entlasten. Dies gilt für Windows 7, 8, 8.1 und Windows 10. Weitere Informationen finden Sie unter [Allgemeine Aufgaben zur Verwaltung von Windows-PCs mit dem Microsoft Intune-Computerclient](intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

## Aktualisierungen am Unternehmensportal
### Unternehmensportal-Website
- **Verbesserte Endbenutzererfahrung bei der Registrierung von Windows-Geräten**<br/>
Wenn Sie den bedingten Zugriff verwenden, werden die Registrierungsschritte für Windows 8.1, Windows 10 Desktop und Windows 10 Mobile in der Unternehmensportal-Website erklärt. Benutzer sehen jetzt die separaten Schritte „Geräteregistrierung“ und „Workplace Join“, mit denen sie leichter den Status ihres Geräts anzeigen und den Prozess abschließen können, wenn ein Fehler beim Workplace Join (WPJ) auftritt. Die separaten Schritte sollten auch die Problembehandlung für IT-Administratoren vereinfachen. Wenn Endbenutzer versuchten, das Gerät zu registrieren, und alle Registrierungsschritte außer dem WPJ erfolgreich verliefen, wurde das registrierte Gerät bisher nicht in der Liste der Geräte angezeigt, die Benutzer identifizieren konnten, und dies verwirrte die Benutzer.

### Android
- **Android-Unternehmensportal-App**<br/>
Wenn Android-Endbenutzer eine Fehlermeldung erhalten, ihrem Gerät fehle ein erforderliches Zertifikat, können sie auf eine Schaltfläche „Problembehebung“ tippen, um [Schritte](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) für die Installation des fehlenden Zertifikats abzurufen. Wenn Benutzer die Schritte ausführen, jedoch eine zusätzliche „Fehlendes Zertifikat“-Fehlermeldung angezeigt wird, werden sie aufgefordert, sich an ihren IT-Administrator zu wenden und diesen [Link](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues) anzugeben, der Schritte enthält, mit denen IT-Administratoren das Zertifikatsproblem beheben können.

- **Einschränken der Installationen quergeladener Apps auf registrierten Geräten**<br/>
Auf Android-Geräten können nicht mehr Apps über die Unternehmensportal-Website installiert werden, es sei denn, die Geräte wurden mithilfe der Intune-Unternehmensportal-App für Android in Intune registriert.
<!---TFS 1299082--->

### iOS
- **Änderungen an den Geräteregistrierungs-Manager-Konten in der iOS-Unternehmensportal-App**<br/>
Zum Verbessern der Leistung und Skalierung zeigt Intune nicht mehr alle Geräte des Geräteregistrierungs-Managers (Device Enrollment Manager, DEM) im Bereich **Meine Geräte** der Unternehmensportal-App für iOS an. Nur das lokale Gerät, das die App ausführt, wird angezeigt, und dies nur, wenn es über die Unternehmensportal-App registriert wurde.

    Der DEM-Benutzer kann Aktionen auf dem lokalen Gerät ausführen, aber die Remoteverwaltung der anderen registrierten Geräte kann nur über die Intune-Verwaltungskonsole ausgeführt werden. Darüber hinaus wird in Intune die Verwendung von DEM-Konten mit dem Apple-Geräteregistrierungsprogramm oder dem Apple Configurator-Tool eingestellt. Diese beiden Registrierungsmethoden unterstützen bereits die benutzerunabhängige Registrierung für gemeinsam genutzte iOS-Geräte.

    Verwenden Sie DEM-Konten nur, wenn die benutzerunabhängige Registrierung für gemeinsam genutzte Geräte nicht verfügbar ist. Weitere Informationen siehe [Registrieren von firmeneigenen Geräten mit dem Geräteregistrierungs-Manager in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

## Ändern von Namen für Windows-Features
- [Microsoft Passport für Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) heißt jetzt **Windows Hello for Business**.
- [Unternehmensdatenschutz](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) heißt jetzt **Windows Information Protection**.

## Was steht an?
### Übergang von Intune-Gruppen zu Azure Active Directory-Gruppen ab August 2016
Intune erstellt eine neue Benutzeroberfläche für die Gruppenverwaltung, die Azure Active Directory-Sicherheitsgruppen (AAD) verwendet. Diese Sicherheitsgruppen auf Basis von Azure AD können Benutzer und Geräte enthalten und werden für sämtliche Gruppenverwaltung, Richtlinien- und Profilbereitstellung verwendet, wenn das neue Intune-Verwaltungsportal auf Azure-Basis eingeführt wird.

Diese neue Oberfläche wird:
- Sie davon befreien, Gruppen zwischen Diensten duplizieren zu müssen.
- Ihnen den Zugriff auf einige neue Azure Active Directory Premium-Gruppenfeatures (AADP) ermöglichen.
- Erweiterbarkeit mit PowerShell und Graph bieten.
- Die Gruppenverwaltungsoberfläche der Enterprise Mobility-Verwaltung übergreifend vereinheitlichen.

Um den Wechsel zu Sicherheitsgruppen zu ermöglichen, wird die Benutzeroberfläche in der aktuellen Administratorkonsole einige Änderungen erfahren. Diese Änderungen und die Verwendung von Azure AD-Sicherheitsgruppen werden in der Intune-Dokumentation aufgezeichnet.

Neue Intune-Kunden sehen einige der Sicherheitsgruppenänderungen, bevor aktuelle Mandanten sie sehen.

Zusätzlich zu Änderungen der Gruppenverwaltung werden die folgende Funktionen als veraltet markiert:
- Ausschließen von Mitgliedern oder Gruppen beim Erstellen einer neuen Gruppe
- **Nicht gruppierte Benutzer** und **Nicht gruppierte Geräte**
- **Verwalten von Gruppen** in der Dienstadministratorrolle
- Benutzerdefinierte gruppenbasierte Warnungen für Benachrichtigungsregeln
- Pivotieren mit Gruppen in Berichten

Weitere Informationen dazu, wie diese Veralterungen entschärft werden können, werden im August veröffentlicht.

### Hinzufügen von „Benachrichtigungen“ zum Unternehmensportal für Android
Im September veröffentlichen wir ein Update zum Unternehmensportal für Android, mit dem auf der Startseite das neue Symbol **Benachrichtigungen** eingeführt wird. Beim Tippen auf dieses Symbol wird die Seite **Benachrichtigungen** aufgerufen, auf der für Ihre Endbenutzer alle Elemente angezeigt werden, die in der Unternehmensportal-App Aufmerksamkeit erfordern, z. B. Nichtkompatibilität, Registrierungsupdate und Registrierungsaktivierung. Wenn Sie auch die iOS-Unternehmensportal-App verwenden, sehen Sie die Benachrichtigungen bereits. Wenn die Seite **Benachrichtigungen** eingeführt wird, werden Sie die Seite **Unternehmenszugriff einrichten** nicht bei jedem Start bzw. jeder Fortsetzung des Unternehmensportals für Android sehen, solange das Gerät bereits registriert ist. Wir haben erfahren, dass viele von Ihnen Endbenutzeranleitungen erstellt haben, und würden eine vorherige Mitteilung schätzen, wenn Ihre Anleitung/Screenshots vielleicht aktualisiert werden müssen. Bitte aktualisieren Sie Ihre Dokumentation gemäß der anstehenden Änderung der Benutzeroberfläche. Aktualisierte Screenshots finden Sie hier: https://aka.ms/androidcpupdate.  



### Fahrplan für die Cloud
Halten Sie sich mit dem [Fahrplan für die Cloudplattform](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune) zu den anstehenden Entwicklungen für Intune auf dem Laufenden.

### Veraltete Dienste
- **Änderungen bei der Unterstützung der iOS-Unternehmensportal-App**<br/>
Im Juli müssen alle Benutzer der Microsoft Intune-Unternehmensportal-App für iOS ein Update auf die aktuelle Version durchführen. Neue Benutzer können nur die aktuelle Version herunterladen, und derzeitige Benutzer müssen ein Update auf die aktuelle Version durchführen. Die aktuelle Version erfordert iOS 8.0 oder höher. Daher können Benutzer von Geräten mit älteren iOS-Versionen erst dann das Unternehmensportal nutzen und eine Registrierung durchführen, wenn sie ihr Gerät auf iOS 8.0 oder höher aktualisieren und anschließend die Unternehmensportal-App auf die aktuelle Version aktualisieren. Registrierte Geräte mit Versionen vor iOS 8.0 werden weiterhin verwaltet und in der Intune-Verwaltungskonsole aufgeführt.  

- **Minimale Version des Managed Browser für iOS auf 8.0 aktualisiert**<br/>
Im August wird Intune eine aktualisierte Microsoft Intune Managed Browser-App für iOS veröffentlichen, die nur Geräte unter iOS 8.0 oder höher unterstützt. iOS 7.1-Geräte können zwar weiterhin die vorhandene Managed Browser-App verwenden, doch fordern Sie Ihre Benutzer bitte auf, auf iOS 8.0 oder höher zu aktualisieren und die neuen Features von Managed Browser in vollem Umfang zu nutzen.  
<!---TFS 1313253--->

- **Unternehmensportal-Apps für Windows 8 und Windows Phone 8 werden ab September 2016 eingestellt.** <br/>
Ab September 2016 stellt Microsoft Intune die Unterstützung für die Microsoft Intune-Unternehmensportal-Apps für die Plattformen Windows Phone 8 und Windows 8 ein. Aktualisieren Sie die Geräte auf Windows 8.1 und Windows Phone 8.1, und nutzen Sie die entsprechenden Windows 8.1- und Windows Phone 8.1-Unternehmensportal-Apps, um weiterhin Apps an diese Geräte zu verteilen.
<!---TFS 1255391--->

- **Intune Viewer-Apps** <br/>
Mit der Veröffentlichung der neuen RMS-Freigabe-App werden wir ab August 2016 die folgenden Intune Viewer-Apps entfernen:
    - Intune AV Viewer
    - Intune PDF Viewer
    - Intune Image Viewer für Android aus Google Play

  Anstatt die Intune-Viewer-Apps zu verwenden, empfehlen wir die Nutzung der neuen [Rights Management-App (RMS-Freigabe)](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app) für Android, die Ihnen das Bereitstellen einer App anstelle von drei getrennten Apps ermöglicht, um Unternehmensdateien sicher auf Android-Geräten anzuzeigen. Wenn die Intune-Viewer-App nicht mehr unterstützt wird, wird sie aus dem Google Store entfernt und steht nicht mehr zur zukünftigen Verwendung zur Verfügung.

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



## Vorherige Versionen von Intune
Wenn Sie feststellen möchten, was während der letzten sechs Monate in Intune veröffentlicht wurde, sehen Sie sich den Artikel [Vorherige Versionen von Intune](previous-intune-releases.md) an.

### Weitere Informationen:
* [Microsoft Intune-Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Fahrplan für die Cloudplattform](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)



<!--HONumber=Aug16_HO1-->


