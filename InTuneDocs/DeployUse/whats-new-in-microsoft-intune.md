---
title: Neuheiten | Microsoft Intune
description: Erfahren Sie, was im Release dieses Monats und in den vergangenen Releases von Microsoft Intune neu ist
keywords: 
author: Lindavr
manager: angrobe
ms.date: 08/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d51ab5d486e7e23d2527f9cb95f105e7916cdb27
ms.openlocfilehash: 138d362618c9859a55988b7a2ada85e44b0e95c5


---

# Neuheiten in Microsoft Intune
Erfahren Sie, was in diesem Release von Microsoft Intune neu ist. Sie erhalten auch Informationen über bevorstehende Änderungen, die Sie einplanen sollten, sowie über vergangene Releases.

Alle diese Features werden letztlich auch für hybride Kundenbereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

## August 2016
## App-Verwaltung
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

### Ausgeblendete und eingeblendete Apps für iOS 9.3
Bei Geräten mit iOS 9.3 oder höher können Sie die Liste für ausgeblendete und eingeblendete Apps in der allgemeinen iOS-Konfigurationsrichtlinie für folgende Aufgaben verwenden:
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


### Fahrplan für die Cloud
Halten Sie sich mit dem [Fahrplan für die Cloudplattform](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune) zu den anstehenden Entwicklungen für Intune auf dem Laufenden.

### Veraltete Dienste
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **Änderungen bei der Unterstützung der iOS-Unternehmensportal-App**<br/>
Ab September müssen alle Benutzer der Microsoft Intune-Unternehmensportal-App für iOS die aktuelle Version verwenden. Neue Benutzer können nur die aktuelle Version herunterladen, und derzeitige Benutzer müssen ein Update auf die aktuelle Version durchführen. Die aktuelle Version erfordert iOS 8.0 oder höher. Daher können Benutzer von Geräten mit älteren iOS-Versionen erst dann das Unternehmensportal nutzen und eine Registrierung durchführen, wenn sie ihr Gerät auf iOS 8.0 oder höher aktualisieren und anschließend die Unternehmensportal-App auf die aktuelle Version aktualisieren. Registrierte Geräte mit Versionen vor iOS 8.0 werden weiterhin verwaltet und in der Intune-Verwaltungskonsole aufgeführt.  

- **Minimale Version des Managed Browser für iOS auf 8.0 aktualisiert**<br/>
Im August wird Intune eine aktualisierte Microsoft Intune Managed Browser-App für iOS veröffentlichen, die nur Geräte unter iOS 8.0 oder höher unterstützt. iOS 7.1-Geräte können zwar weiterhin die vorhandene Managed Browser-App verwenden, doch fordern Sie Ihre Benutzer bitte auf, auf iOS 8.0 oder höher zu aktualisieren und die neuen Features von Managed Browser in vollem Umfang zu nutzen.  
<!---TFS 1313253--->

- **Unternehmensportal-Apps für Windows 8 und Windows Phone 8 werden ab September 2016 eingestellt.** <br/>
Ab September 2016 stellt Microsoft Intune die Unterstützung für die Microsoft Intune-Unternehmensportal-Apps für die Plattformen Windows Phone 8 und Windows 8 ein. Aktualisieren Sie die Geräte auf Windows 8.1 und Windows Phone 8.1, und nutzen Sie die entsprechenden Windows 8.1- und Windows Phone 8.1-Unternehmensportal-Apps, um weiterhin Apps an diese Geräte zu verteilen.
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



## Vorherige Versionen von Intune
Wenn Sie feststellen möchten, was während der letzten sechs Monate in Intune veröffentlicht wurde, sehen Sie sich den Artikel [Vorherige Versionen von Intune](previous-intune-releases.md) an.

### Weitere Informationen:
* [Microsoft Intune-Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Fahrplan für die Cloudplattform](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)



<!--HONumber=Aug16_HO3-->


