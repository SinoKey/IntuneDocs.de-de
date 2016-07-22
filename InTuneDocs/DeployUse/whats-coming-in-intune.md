---
title: Anstehende Neuerungen | Microsoft Intune
description: 
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 06/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
ms.sourcegitcommit: b203f51171d38f2b0fc2b46e556679322701d29b
ms.openlocfilehash: 77d2e74dcb032ff52808998c56de7d6b8847ebbe


---

# Anstehende Neuerungen in Microsoft Intune
Diese Informationen werden unter dem Geheimhaltungsvertrag auf einer sehr begrenzten Basis bereitgestellt und Änderungen sind vorbehalten. Einige der hier aufgeführten Features werden möglicherweise bis zum Stichtag nicht fertig und werden erst in eine spätere Version aufgenommen. Andere Features werden in einer Pilotphase getestet (Test-Flighting), um sicherzustellen, dass sie für Kunden bereit sind. Wenden Sie sich an Ihren Intune-/PM-Kontakt, wenn Sie Fragen oder Bedenken haben.

Diese Seite wird regelmäßig aktualisiert. Informieren Sie sich regelmäßig über neue Updates der anstehenden Neuerungen.

Die folgenden Änderungen sind in der Entwicklung für Intune. Alle diese Features werden auch für hybride Kundenbereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).


## App-Verwaltung
- **Höhere Benutzerfreundlichkeit bei der Richtlinienkonfiguration für Unternehmensdaten in Windows 10.** Wir haben die Benutzerfreundlichkeit bei der Richtlinienkonfiguration für den Windows 10-Unternehmensdatenschutz verbessert. Dabei wurden Aufgaben wie das Erstellen von App-Regeln, das Festlegen von Definitionen für Netzwerkgrenzen und andere Einstellungen für den Unternehmensdatenschutz vereinfacht.
<!---TFS 1303011--->

- **Bedingter Zugriff für Browser.** Sie können eine Richtlinie für bedingten Zugriff für Exchange Online und SharePoint Online festlegen, sodass nur verwaltete und kompatible iOS- und Android-Geräte darauf zugreifen können. Endbenutzer, die versuchen, sich mit iOS- und Android-Geräten bei Outlook Web Access- (OWA) und SharePoint-Websites anzumelden, werden aufgefordert, ihr Gerät bei Intune zu registrieren und alle Kompatibilitätsprobleme zu beheben, bevor die Anmeldung abgeschlossen werden kann.
<!---TFS 1175844--->

- **Dynamics CRM Online unterstützt den bedingten Zugriff.** Kunden können eine Richtlinie für bedingten Zugriff für Dynamics CRM Online festlegen, sodass nur der Zugriff durch verwaltete und kompatible iOS- und Android-Geräte möglich ist. Endbenutzer, die versuchen, sich bei der mobilen Dynamics CRM-App für iOS und Android anzumelden, werden aufgefordert, sich bei Intune zu registrieren und alle Kompatibilitätsprobleme zu beheben, bevor die Anmeldung abgeschlossen werden kann.
<!---TFS1295358--->

### Xamarin-Unterstützung
Das Microsoft Intune App SDK unterstützt Xamarin-Apps in den folgenden Szenarien:

- Schreiben neuer Apps oder Ändern des Codes vorhandener branchenspezifischer Apps mit dem Intune-SDK. Sie erhalten das Plug-In auf der [GitHub-Seite für Microsoft Intune](https://github.com/msintuneappsdk).
- Hinzufügen von MAM-Unterstützung zu vorhandenen branchenspezifischen Apps mithilfe des Intune App Wrapping Tools.

Hilfe bei der Auswahl der zu verwendenden Methode erhalten Sie unter [Auswählen der Vorbereitung von Apps für die mobile Anwendungsverwaltung mit Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).
<!--- TFS 1061478 & TFS 1152340--->

## Geräteverwaltung
- **Windows Defender-Richtlinieneinstellung zum Schutz gegen potenziell unerwünschte Apps.** Die allgemeine Konfigurationsrichtlinie für Windows 10 Desktop und Mobile wurde um die neue Windows Defender-Einstellung **Erkennung möglicherweise unerwünschter Anwendungen** erweitert. Mit dieser Einstellung können registrierte Windows-Desktopcomputer gegen Software geschützt werden, die von Windows Defender als möglicherweise unerwünscht eingestuft wird. Sie können verhindern, dass diese Anwendungen ausgeführt werden, oder den Überwachungsmodus verwenden, um zu melden, wenn eine möglicherweise unerwünschte Anwendung installiert wird.
<!---TFS 1244478--->

## Bedingter Zugriff
**Cisco ISE-Netzwerkzugriffssteuerungs-Richtlinie für Intune.**  Kunden, die Cisco Identity Service Engine (ISE) 2.1 und Microsoft Intune verwenden, können eine Netzwerkzugriffssteuerungs-Richtlinie in ISE festlegen.

Bei Verwendung dieser Richtlinie müssen Geräte, die sich über WLAN oder VPN verbinden müssen, die folgenden Voraussetzungen erfüllen, bevor sie Zugriff erhalten:

* Die Geräte müssen über Intune verwaltet werden
* Die Geräte müssen mit allen bereitgestellten Intune-Konformitätsrichtlinien kompatibel sein

Endbenutzer mit nicht konformen Geräten werden aufgefordert, sich zu registrieren und jegliche Konformitätsprobleme zu beheben, um Zugriff zu erhalten.
<!---TFS 1299144--->

## Unternehmensportal
**Änderungen an den Geräteregistrierungs-Manager-Konten in der iOS-Unternehmensportal-App.** Zum Verbessern der Leistung und Skalierung zeigt Intune nicht mehr alle Geräte des Geräteregistrierungs-Managers (Device Enrollment Manager, DEM) im Bereich „Meine Geräte“ der Unternehmensportal-App für iOS an. Nur das lokale Gerät, das die App ausführt, wird angezeigt, und dies nur, wenn es über die Unternehmensportal-App registriert wurde. Der DEM-Benutzer kann Aktionen auf dem lokalen Gerät ausführen, aber die Remoteverwaltung der anderen registrierten Geräte kann nur über die Intune-Verwaltungskonsole ausgeführt werden.  Darüber hinaus wird in Intune die Verwendung von DEM-Konten mit dem Apple-Geräteregistrierungsprogramm oder dem Apple Configurator-Tool eingestellt. Diese beiden Registrierungsmethoden unterstützen bereits die benutzerunabhängige Registrierung für gemeinsam genutzte iOS-Geräte. Verwenden Sie DEM-Konten nur, wenn die benutzerunabhängige Registrierung für gemeinsam genutzte Geräte nicht verfügbar ist.
<!---TFS 1233681--->

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



<!--HONumber=Jul16_HO1-->


