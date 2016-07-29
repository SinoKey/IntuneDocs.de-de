---
title: Anstehende Neuerungen | Microsoft Intune
description: 
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 07/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 35ee5d0c8898c95898c0527a623cf13c454387f2
ms.openlocfilehash: 831cec6cd0e02a94c1a3f67d4adf5a5dcbb01449


---

# Anstehende Neuerungen in Microsoft Intune – Juli
Diese Informationen werden unter dem Geheimhaltungsvertrag auf einer sehr begrenzten Basis bereitgestellt und Änderungen sind vorbehalten. Einige der hier aufgeführten Features werden möglicherweise bis zum Stichtag nicht fertig und werden erst in eine spätere Version aufgenommen. Andere Features werden in einer Pilotphase getestet (Test-Flighting), um sicherzustellen, dass sie für Kunden bereit sind. Wenden Sie sich an Ihren Intune-/PM-Kontakt, wenn Sie Fragen oder Bedenken haben.

Diese Seite wird regelmäßig aktualisiert. Informieren Sie sich regelmäßig über neue Updates der anstehenden Neuerungen.

Die folgenden Änderungen sind in der Entwicklung für Intune. Alle diese Features werden letztlich auch für hybride Kundenbereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).


## App-Verwaltung
### Verbessern der Benutzererfahrung beim Update des App-Bereitstellungsprofils
Die Apple iOS-Reihe mobiler Geschäfts-Apps wird mit einem integrierten Bereitstellungsprofil erstellt und mit Code, der mit einem Zertifikat signiert wurde. Beim Ausführen der App auf einem iOS-Gerät bestätigt iOS die Integrität der iOS-App und erzwingt Richtlinien, die durch das Bereitstellungsprofil definiert werden.

Das Unternehmenssignaturzertifikat, das Sie zum Signieren von Apps verwenden, ist in der Regel 3 Jahre lang gültig. Allerdings läuft das Bereitstellungsprofil nach 1 Jahr ab. Mit diesem Update stellt Intune Ihnen die Tools zum proaktiven Bereitstellen einer neuen Richtlinie für Bereitstellungsprofile auf Geräten zur Verfügung, auf denen Apps installiert sind, die bald ablaufen, während das Zertifikat noch gültig ist.
<!--- TFS 1280247--->

### Xamarin-Unterstützung
Das Microsoft Intune App SDK unterstützt Xamarin-Apps in den folgenden Szenarien:

- Schreiben neuer Apps oder Ändern des Codes vorhandener branchenspezifischer Apps mit dem Intune-SDK. Sie erhalten das Plug-In auf der [GitHub-Seite für Microsoft Intune](https://github.com/msintuneappsdk).
- Hinzufügen von MAM-Unterstützung zu vorhandenen branchenspezifischen Apps mithilfe des Intune App Wrapping Tools.

Hilfe bei der Auswahl der zu verwendenden Methode erhalten Sie unter [Auswählen der Vorbereitung von Apps für die mobile Anwendungsverwaltung mit Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).

<!--- TFS 1061478 & TFS 1152340--->

## Geräteverwaltung
### Höhere Limits bei der Geräteregistrierung
Intune erhöht das maximal konfigurierbare Limit für die Geräteregistrierung von 5 auf 15 Geräte pro Benutzer.
<!---TFS 1289896 --->

## Gruppenverwaltung
### Übergang von Intune-Gruppen zu Azure Active Directory-Gruppen ab August 2016
Intune erstellt eine neue Benutzeroberfläche für die Gruppenverwaltung, die Azure Active Directory-Sicherheitsgruppen (AAD) als Benutzer- und Gerätegruppen in Intune verwendet. Diese Gruppen werden für sämtliche Gruppenverwaltung, Richtlinien- und Profilbereitstellung verwendet, **wenn das neue Intune-Verwaltungsportal auf Azure-Basis eingeführt wird**.

Diese neue Benutzeroberfläche verhindert, dass Sie Gruppen zwischen Diensten duplizieren müssen, **ermöglicht Ihnen den Zugriff auf einige neue Gruppenfeatures in Azure Active Directory Premium (AADP)** und bietet Erweiterbarkeit mithilfe von PowerShell und Graph. Dies vereinheitlicht auch die Gruppenverwaltungsoberfläche der Enterprise Mobility-Verwaltung übergreifend.

Um den Wechsel zu Sicherheitsgruppen zu ermöglichen, wird die Benutzeroberfläche in der **aktuellen Administratorkonsole** einige Änderungen erfahren. **Diese Änderungen und die Verwendung von AAD-Sicherheitsgruppen werden in der Intune-Dokumentation aufgezeichnet**.

Neue Intune-Kunden **sehen einige der Sicherheitsgruppenänderungen, bevor aktuelle Mandanten sie sehen**.

Zusätzlich zu Änderungen der Gruppenverwaltung **werden die folgende Funktionen als veraltet markiert**:
- Ausschließen von Mitgliedern oder Gruppen beim Erstellen einer neuen Gruppe
- „Verwalten von Gruppen“ in der Dienstadministratorrolle
- Benutzerdefinierte gruppenbasierte Warnungen für Benachrichtigungsregeln
- Pivotieren mit Gruppen in Berichten


## Unternehmensportal

### Hinzufügen von „Benachrichtigungen“ zum Unternehmensportal für Android
Wir veröffentlichen ein Update für das Unternehmensportal für Android im August, mit dem ein neues Symbol **Benachrichtigungen** auf der Startseite eingeführt wird. Beim Tippen auf dieses Symbol wird die Seite **Benachrichtigungen** aufgerufen, auf der für Ihre Endbenutzer alle Elemente angezeigt werden, die in der Unternehmensportal-App Aufmerksamkeit erfordern, z. B. Nichtkompatibilität, Registrierungsupdate und Registrierungsaktivierung. Wenn Sie auch die iOS-Unternehmensportal-App verwenden, sehen Sie die Benachrichtigungen bereits. Wenn die Seite **Benachrichtigungen** eingeführt wird, werden Sie die Seite **Unternehmenszugriff einrichten** nicht bei jedem Start bzw. jeder Fortsetzung des Unternehmensportals für Android sehen, solange das Gerät bereits registriert ist. Wir haben erfahren, dass viele von Ihnen Endbenutzeranleitungen erstellt haben, und würden eine vorherige Mitteilung schätzen, wenn Ihre Anleitung/Screenshots vielleicht aktualisiert werden müssen. Bitte aktualisieren Sie Ihre Dokumentation gemäß der anstehenden Änderung der Benutzeroberfläche. Aktualisierte Screenshots finden Sie hier: https://aka.ms/androidcpupdate.  

### Unterstützen von Benutzern, Probleme bei der Registrierung zu beheben, wenn beim Workplace Join ein Fehler auftritt
Wenn Sie den bedingten Zugriff verwenden, werden die Registrierungsschritte für Windows 8.1, Windows 10 Desktop und Windows 10 Mobile in der Unternehmensportal-Website für Endbenutzer vereinfacht, bei denen ein Fehler beim Workplace Join (WPJ) auftritt. Wenn Endbenutzer versuchten, das Gerät zu registrieren und einen WPJ auszuführen, und die Registrierung erfolgreich verlief, aber bei dem WPJ ein Fehler auftrat, wurde das registrierte Gerät bisher nicht in der Liste der Geräte angezeigt, die Benutzer identifizieren konnten, und dies verwirrte die Benutzer. Benutzer sehen jetzt die separaten Schritte „Geräteregistrierung“ und „Workplace Join“, mit denen sie leichter den Status ihres Geräts anzeigen und den Prozess abschließen können, nachdem ein Fehler beim WPJ aufgetreten ist. Die separaten Schritte sollten auch die Problembehandlung für IT-Administratoren vereinfachen.

### Änderungen an den Geräteregistrierungs-Manager-Konten in der iOS-Unternehmensportal-App
Zum Verbessern der Leistung und Skalierung zeigt Intune nicht mehr alle Geräte des Geräteregistrierungs-Managers (Device Enrollment Manager, DEM) im Bereich „Meine Geräte“ der Unternehmensportal-App für iOS an. Nur das lokale Gerät, das die App ausführt, wird angezeigt, und dies nur, wenn es über die Unternehmensportal-App registriert wurde. Der DEM-Benutzer kann Aktionen auf dem lokalen Gerät ausführen, aber die Remoteverwaltung der anderen registrierten Geräte kann nur über die Intune-Verwaltungskonsole ausgeführt werden.  Darüber hinaus wird in Intune die Verwendung von DEM-Konten mit dem Apple-Geräteregistrierungsprogramm oder dem Apple Configurator-Tool eingestellt. Diese beiden Registrierungsmethoden unterstützen bereits die benutzerunabhängige Registrierung für gemeinsam genutzte iOS-Geräte. Verwenden Sie DEM-Konten nur, wenn die benutzerunabhängige Registrierung für gemeinsam genutzte Geräte nicht verfügbar ist.
<!---TFS 1233681--->
### Einschränken der Installationen quergeladener Apps auf registrierten Android-Geräten
Auf Android-Geräten können nicht mehr Apps über die Unternehmensportal-Website installiert werden, es sei denn, die Geräte wurden mithilfe der Intune-Unternehmensportal-App für Android in Intune registriert. 
<!---TFS 1299082--->

## Veraltete Dienste
**Unternehmensportal-Apps für Windows 8 und Windows Phone 8 werden ab September 2016 eingestellt.** Ab September 2016 stellt Microsoft Intune die Unterstützung für die Microsoft Intune-Unternehmensportal-Apps für die Plattformen Windows Phone 8 und Windows 8 ein. Aktualisieren Sie die Geräte auf Windows 8.1 und Windows Phone 8.1, und nutzen Sie die entsprechenden Windows 8.1- und Windows Phone 8.1-Unternehmensportal-Apps, um weiterhin Apps an diese Geräte zu verteilen.
<!---TFS 1255391--->

**Entfernung der Zielgruppenadressierung benutzerdefinierter Gruppen bei Benachrichtigungsregeln.**
Intune-Benachrichtigungsregeln definieren, an wen aus Intune eine E-Mail-Benachrichtigung gesendet wird. Derzeit können Sie Benachrichtigungsregeln zum Senden von E-Mails an alle Benutzer von Geräten in einer Intune-Gerätegruppe konfigurieren, die Sie erstellt haben. Ab Anfang Juni 2016 wird die Adressierung von Gruppen, die von Benutzern erstellt wurden, nicht mehr unterstützt.

Der vorläufige Zeitplan für diese Änderung ist wie folgt:
- Im August 2016 wird Schritt 2 im Assistenten zum Erstellen von Benachrichtigungsregeln nicht mehr für neue Mandanten angezeigt. Vorhandene Mandanten sind nicht betroffen.
- Ab September 2016 wird einigen vorhandenen Mandanten der Schritt „Gerätegruppen auswählen“ im Assistenten nicht angezeigt.
- Ab November 2016 wird für alle Mandanten der Schritt „Gerätegruppen auswählen“ im Assistenten nicht mehr angezeigt.

<!---   TFS 1278864--->

**Änderungen bei der Unterstützung der iOS-Unternehmensportal-App.**
Im Juli müssen alle Benutzer der Microsoft Intune-Unternehmensportal-App für iOS ein Update auf die aktuelle Version durchführen. Neue Benutzer können nur die aktuelle Version herunterladen, und derzeitige Benutzer müssen ein Update auf die aktuelle Version durchführen. Die aktuelle Version erfordert iOS 8.0 oder höher. Daher können Benutzer von Geräten mit älteren iOS-Versionen erst dann das Unternehmensportal nutzen und eine Registrierung durchführen, wenn sie ihr Gerät auf iOS 8.0 oder höher aktualisieren und anschließend die Unternehmensportal-App auf die aktuelle Version aktualisieren. Registrierte Geräte mit Versionen vor iOS 8.0 werden weiterhin verwaltet und in der Intune-Verwaltungskonsole aufgeführt.  

**Intune Viewer-Apps.** Mit der Veröffentlichung der neuen RMS-Freigabe-App werden wir ab August 2016 die folgenden Intune Viewer-Apps entfernen:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer für Android aus Google Play

Anstatt die Intune-Viewer-Apps zu verwenden, empfehlen wir die Nutzung der neuen Rights Management-App (RMS-Freigabe) für Android, die Ihnen das Bereitstellen einer App anstelle von drei getrennten Apps ermöglicht, um Unternehmensdateien sicher auf Android-Geräten anzuzeigen. Weitere Informationen zur RMS-Freigabe-App (mit Link zur Dokumentation).



### Weitere Informationen:
Details zu aktuellen Entwicklungen finden Sie unter [Neuheiten in Microsoft Intune](whats-new-in-microsoft-intune.md).



<!--HONumber=Jul16_HO3-->


