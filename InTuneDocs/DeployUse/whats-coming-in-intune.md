---
title: Anstehende Neuerungen | Microsoft Intune
description: 
keywords: 
author: Lindavr
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f02d8791bbca65a4bfda69e61e9e22c8124c436b
ms.openlocfilehash: 09fb5dac0276b4da49795539f40dbde15cd69bf5


---

# Anstehende Neuerungen in Microsoft Intune – August
Diese Informationen werden unter dem Geheimhaltungsvertrag auf einer sehr begrenzten Basis bereitgestellt und Änderungen sind vorbehalten. Einige der hier aufgeführten Features werden möglicherweise bis zum Stichtag nicht fertig und werden erst in eine spätere Version aufgenommen. Andere Features werden in einer Pilotphase getestet (Test-Flighting), um sicherzustellen, dass sie für Kunden bereit sind. Wenden Sie sich an Ihren Intune-/PM-Kontakt, wenn Sie Fragen oder Bedenken haben.

Diese Seite wird regelmäßig aktualisiert. Informieren Sie sich regelmäßig über neue Updates der anstehenden Neuerungen.

Die folgenden Änderungen sind in der Entwicklung für Intune. Alle diese Features werden letztlich auch für hybride Kundenbereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).


## App-Verwaltung
### Ausgeblendete und eingeblendete Apps für iOS 9.3
Bei überwachten Geräten mit iOS 9.3 oder höher können Sie die Liste für ausgeblendete und eingeblendete Apps in der allgemeinen iOS-Konfigurationsrichtlinie für folgende Aufgaben verwenden:
- Angeben einer Liste von Apps, die vor Benutzern verborgen werden. Benutzer können diese Apps weder anzeigen noch starten.
- Angeben einer Liste von Apps, die Benutzer anzeigen und starten können. Es können keine anderen Apps angezeigt oder gestartet werden.

Die Apps, die Sie angeben können, umfassen sowohl von Ihnen bereitgestellte Apps als auch integrierte iOS-Apps, wie „Nachrichten“ und „Notizen“.
<!---TFS 1279009--->

### Richtlinie für zulässige und blockierte Apps für Samsung KNOX-Geräte

Sie können jetzt eine benutzerdefinierte Richtlinie für Samsung KNOX-Geräte konfigurieren, die Ihnen das Erstellen einer der folgenden Listen ermöglicht:
- Eine Liste von Apps, deren Ausführung auf dem Gerät blockiert wird. Eine in der Liste blockierter Apps definierte App kann nicht auf dem Gerät aktiviert werden, auch wenn sie auf dem Gerät installiert ist.
- Eine Liste von Apps, die Benutzer des Geräts aus dem Google Play Store installieren dürfen. Es können keine anderen Apps aus dem Store installiert werden.

Diese Einstellungen können nur von Geräten verwendet werden, auf denen Samsung KNOX ausgeführt wird.
<!--- For details, see [Use custom policies to allow and block apps for Samsung KNOX devices]( custom-policy-to-allow-and-block-samsung-knox-apps.md)--->
<!---TFS 1311629 --->

### Neue, mit MAM-Richtlinien kompatible Apps
Die Yammer-App für [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) und [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) ist mit [Intune-Richtlinien für die Verwaltung mobiler Anwendungen](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) (Mobile Application Management, MAM) kompatibel. Dies gilt unabhängig davon, ob das Gerät registriert ist oder nicht.

Eine vollständige Liste MAM-kompatibler Apps finden Sie auf der Website [Microsoft Intune-Anwendungspartner](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners).
<!--- TFS 1252335 & 1252336--->

## Geräteverwaltung
### Android 7.0-Unterstützung
Ab August bietet Intune „Day-0“-Unterstützung für das bevorstehende Android 7.0-Betriebssystem für mobile Geräte.
<!---TFS 1262053--->
### Funktion für das Remote-Zurücksetzen von Passcodes auf Android 7.0-Geräten von Google entfernt
Die Funktion, durch die IT-Administratoren und Endbenutzer den Passcode von Android 7.0-Geräten remote zurücksetzen konnten, wurde von Google entfernt. Zuvor konnten IT-Administratoren Benutzerpasscodes remote zurücksetzen, und Endbenutzer konnten ihre Passcodes auf der Unternehmensportal-Website zurücksetzen.

## Gruppenverwaltung
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

## Unternehmensportal

### Feedbacklink vom Unternehmensportal zu Microsoft
Auf der Unternehmensportal-Website können Endbenutzer auf einen neuen „Feedbacklink“ am unteren Seitenrand tippen, um Feedback zu ihren Erfahrungen mit der Website an Microsoft zu senden. Das gesammelte anonymisierte Feedback hilft Microsoft, die Benutzerfreundlichkeit der Unternehmensportal-Website zu verbessern.
<!--- TFS 1313657--->

### Hinzufügen von „Benachrichtigungen“ zum Unternehmensportal für Android
Im September veröffentlichen wir ein Update zum Unternehmensportal für Android, mit dem auf der Startseite das neue Symbol **Benachrichtigungen** eingeführt wird. Beim Tippen auf dieses Symbol wird die Seite **Benachrichtigungen** aufgerufen, auf der für Ihre Endbenutzer alle Elemente angezeigt werden, die in der Unternehmensportal-App Aufmerksamkeit erfordern, z. B. Nichtkompatibilität, Registrierungsupdate und Registrierungsaktivierung. Wenn Sie auch die iOS-Unternehmensportal-App verwenden, sehen Sie die Benachrichtigungen bereits. Wenn die Seite **Benachrichtigungen** eingeführt wird, werden Sie die Seite **Unternehmenszugriff einrichten** nicht bei jedem Start bzw. jeder Fortsetzung des Unternehmensportals für Android sehen, solange das Gerät bereits registriert ist. Wir haben erfahren, dass viele von Ihnen Endbenutzeranleitungen erstellt haben, und würden eine vorherige Mitteilung schätzen, wenn Ihre Anleitung/Screenshots vielleicht aktualisiert werden müssen. Bitte aktualisieren Sie Ihre Dokumentation gemäß der anstehenden Änderung der Benutzeroberfläche. Aktualisierte Screenshots finden Sie hier: https://aka.ms/androidcpupdate.  


## Veraltete Dienste
### Unternehmensportal-Apps für Windows 8 und Windows Phone 8 gelten ab September 2016 als veraltet
Ab September 2016 stellt Microsoft Intune die Unterstützung für die Microsoft Intune-Unternehmensportal-Apps für die Plattformen Windows Phone 8 und Windows 8 ein. Aktualisieren Sie die Geräte auf Windows 8.1 und Windows Phone 8.1, und nutzen Sie die entsprechenden Windows 8.1- und Windows Phone 8.1-Unternehmensportal-Apps, um weiterhin Apps an diese Geräte zu verteilen.
<!---TFS 1255391--->

### Adressierung benutzerdefinierter Zielgruppen mithilfe von Benachrichtigungsregeln entfernt
Intune-Benachrichtigungsregeln definieren, an wen aus Intune eine E-Mail-Benachrichtigung gesendet wird. Derzeit können Sie Benachrichtigungsregeln zum Senden von E-Mails an alle Benutzer von Geräten in einer Intune-Gerätegruppe konfigurieren, die Sie erstellt haben. Ab Juni 2016 wird die Adressierung benutzerdefinierter Zielgruppen nicht mehr unterstützt.

Der vorläufige Zeitplan für diese Änderung ist wie folgt:
- Ab September 2016 wird Schritt 2 im Assistenten zum Erstellen von Benachrichtigungsregeln für neue Mandanten nicht mehr angezeigt. Vorhandene Mandanten sind nicht betroffen.
- Ab Oktober 2016 ist der Schritt „Gerätegruppen auswählen“ im Assistenten für einige vorhandene Mandanten nicht mehr sichtbar.
- Wir gehen davon aus, dass der Schritt „Gerätegruppen auswählen“ im Assistenten zu einem späteren Zeitpunkt für keinen Mandanten mehr sichtbar ist.

<!---   TFS 1278864--->
### Änderungen bei der Unterstützung der iOS-Unternehmensportal-App
Ab September müssen alle Benutzer der Microsoft Intune-Unternehmensportal-App für iOS die aktuelle Version verwenden. Neue Benutzer können nur die aktuelle Version herunterladen, und derzeitige Benutzer müssen ein Update auf die aktuelle Version durchführen. Die aktuelle Version erfordert iOS 8.0 oder höher. Daher können Benutzer von Geräten mit älteren iOS-Versionen erst dann das Unternehmensportal nutzen und eine Registrierung durchführen, wenn sie ihr Gerät auf iOS 8.0 oder höher aktualisieren und anschließend die Unternehmensportal-App auf die aktuelle Version aktualisieren. Registrierte Geräte mit Versionen vor iOS 8.0 werden weiterhin verwaltet und in der Intune-Verwaltungskonsole aufgeführt.

<!---TFS 1283165--->


### Intune Viewer-Apps
Mit der Veröffentlichung der neuen RMS-Freigabe-App werden wir im August 2016 die folgenden Intune-Viewer-Apps entfernen:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer für Android aus Google Play

Anstatt die Intune-Viewer-Apps zu verwenden, empfehlen wir die Nutzung der neuen Rights Management-App (RMS-Freigabe) für Android, die Ihnen das Bereitstellen einer App anstelle von drei getrennten Apps ermöglicht, um Unternehmensdateien sicher auf Android-Geräten anzuzeigen. Erfahren Sie mehr über die [RMS-Freigabeanwendung](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app).
<!--- goes in 1608 What's New--->


### Weitere Informationen:
Details zu aktuellen Entwicklungen finden Sie unter [Neuheiten in Microsoft Intune](whats-new-in-microsoft-intune.md).



<!--HONumber=Aug16_HO2-->


