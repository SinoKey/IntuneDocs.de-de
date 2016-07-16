---
title: Neuheiten | Microsoft Intune
description: Erfahren Sie, was im Release dieses Monats und in den vergangenen Releases von Microsoft Intune neu ist
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 06/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 79617dd41e51402a73759da792f581028095a2f5
ms.openlocfilehash: 65e53ad6a74fbf0e9249c367f517ab52ea0efa80


---

# Neuheiten in Microsoft Intune
Erfahren Sie, was in diesem Release von Microsoft Intune neu ist. Sie erhalten auch Informationen über bevorstehende Änderungen, die Sie einplanen sollten, sowie über vergangene Releases.

Folgendes ist in diesem Release neu. Mit Ausnahme des Updates für Windows Defender-Richtlinieneinstellungen werden alle diese Funktionen auch für hybride Kundenbereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

## Juni 2016
### Status des Intune-Diensts
Informationen zum Status des Intune-Diensts wurden wie für andere Microsoft-Dienste an einen zentralen Speicherort verschoben. Sie finden diese Informationen jetzt im Verwaltungsportal von Office 365 unter „Dienststatus“. Weitere Informationen finden Sie in [diesem Blogbeitrag](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

## App-Verwaltung
- **Höhere Benutzerfreundlichkeit bei der Richtlinienkonfiguration für Unternehmensdaten in Windows 10.** Wir haben die Benutzerfreundlichkeit bei der Richtlinienkonfiguration für den Windows 10-Unternehmensdatenschutz verbessert. Dabei wurden Aufgaben wie das Erstellen von App-Regeln, das Festlegen von Definitionen für Netzwerkgrenzen und andere Einstellungen für den Unternehmensdatenschutz vereinfacht. Weitere Informationen finden Sie unter [Create an enterprise data protection (EDP) policy using Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) (Erstellen einer Enterprise Data Protection-Richtlinie (EDP) mithilfe von Microsoft Intune).


## Geräteverwaltung
- **Windows Defender-Richtlinieneinstellung zum Schutz gegen potenziell unerwünschte Apps.** Die allgemeine Konfigurationsrichtlinie für Windows 10 Desktop und Mobile wurde um die neue Windows Defender-Einstellung **Erkennung möglicherweise unerwünschter Anwendungen** erweitert. Mit dieser Einstellung können registrierte Windows-Desktopcomputer gegen Software geschützt werden, die von Windows Defender als möglicherweise unerwünscht eingestuft wird. Sie können verhindern, dass diese Anwendungen ausgeführt werden, oder den Überwachungsmodus verwenden, um zu melden, wenn eine möglicherweise unerwünschte Anwendung installiert wird. Weitere Informationen finden Sie unter [Einstellungen für Windows 10-Richtlinien in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).
<!---TFS 1244478--->

## Bedingter Zugriff
- **Cisco ISE-Netzwerkzugriffssteuerungs-Richtlinie für Intune.**  Kunden, die Cisco Identity Service Engine (ISE) 2.1 und Microsoft Intune verwenden, können eine Netzwerkzugriffssteuerungs-Richtlinie in ISE festlegen.

    Bei Verwendung dieser Richtlinie müssen Geräte, die sich über WLAN oder VPN verbinden müssen, die folgenden Voraussetzungen erfüllen, bevor sie Zugriff erhalten:

    * Die Geräte müssen über Intune verwaltet werden
    * Die Geräte müssen mit allen bereitgestellten Intune-Konformitätsrichtlinien kompatibel sein

 Endbenutzer mit nicht konformen Geräten werden aufgefordert, sich zu registrieren und jegliche Konformitätsprobleme zu beheben, um Zugriff zu erhalten.
- **Bedingter Zugriff für Browser.** Sie können eine Richtlinie für den bedingten Zugriff für [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md) und [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md) festlegen, sodass nur von unterstützten Webbrowsern auf verwalteten und kompatiblen iOS- und Android-Geräten darauf zugegriffen werden kann. Endbenutzer, die versuchen, sich mit iOS- und Android-Geräten bei Outlook Web Access- (OWA) und SharePoint-Websites anzumelden, werden aufgefordert, ihr Gerät bei Intune zu registrieren und alle Kompatibilitätsprobleme zu beheben, bevor die Anmeldung abgeschlossen werden kann.
<!---TFS 1175844--->

- **Dynamics CRM Online unterstützt den bedingten Zugriff.** Sie können eine Richtlinie für den bedingten Zugriff für [Dynamics CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md) festlegen, sodass nur der Zugriff durch verwaltete und kompatible iOS- und Android-Geräte möglich ist. Endbenutzer, die versuchen, sich bei der mobilen Dynamics CRM-App für iOS und Android anzumelden, werden aufgefordert, sich bei Intune zu registrieren und alle Kompatibilitätsprobleme zu beheben, bevor die Anmeldung abgeschlossen werden kann.
<!---TFS1295358--->

## Aktualisierungen am Unternehmensportal

### Android-Unternehmensportal-App

- Wenn IT-Administratoren die neue Richtlinie „Require that devices disallow installation of apps from unknown sources (Android 4.0+)“ (Geräte dürfen die Installation von Apps aus unbekannten Quellen nicht erlauben (Android 4.0 und höher)) anwenden, wird Endbenutzern mit Geräten mit Android 4.0 oder höher die Meldung „Die Installation von unbekannten Quellen muss deaktiviert sein.“ angezeigt. Benutzer müssen zu **Einstellungen** > **Sicherheit** wechseln und **Unbekannte Quellen** deaktivieren. Durch einen Link in der Konformitätsmeldung erhalten Benutzer mehr [Informationen](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) zu der Meldung und zu dem Grund, aus dem sie dazu aufgefordert werden, die Einstellung zu deaktivieren.

- Wenn IT-Administratoren die neue Richtlinie „Require that devices have enabled scanning of apps for security threats (Android 4.0+)“ (Bei Geräten muss die Option zum Überprüfen von Apps auf Sicherheitsbedrohungen aktiviert sein (Android 4.0 und höher)) anwenden, wird Endbenutzern mit Geräten mit Android 4.0 oder höher die Meldung „Gerät auf Sicherheitsbedrohungen überprüfen.“ angezeigt. Benutzer müssen zu **Einstellungen** > **Google** > **Sicherheit** wechseln und **Gerät auf Sicherheitsbedrohungen überprüfen** aktivieren. Durch einen Link in der Konformitätsmeldung erhalten Benutzer mehr [Informationen](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) zu der Meldung und zu dem Grund, aus dem sie dazu aufgefordert werden, die Einstellung zu aktivieren.

- Wenn IT-Administratoren die neue Richtlinie „USB-Debuggen muss deaktiviert sein (Android 4.2 und höher)“ anwenden, wird Endbenutzern mit Geräten mit Android 4.2 oder höher die Meldung „USB-Debuggen muss deaktiviert sein.“ angezeigt. Benutzer müssen zu **Einstellungen** > **Entwickleroptionen** wechseln und **USB-Debuggen** deaktivieren. Durch einen Link in der Konformitätsmeldung erhalten Benutzer mehr [Informationen](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) zu der Meldung und zu dem Grund, aus dem sie dazu aufgefordert werden, die Einstellung zu deaktivieren.

- Wenn IT-Administratoren die neue Richtlinie „Niedrigste zulässige Android-Sicherheitspatchebene (Android 6.0 und höher)“ anwenden, wird Endbenutzern mit Geräten mit Android 6.0 oder höher die Meldung „Dieses Gerät weist nicht die mindestens erforderliche Ebene für Android-Sicherheitspatches auf.“ angezeigt. Benutzer müssen den erforderlichen Sicherheitspatch installieren. Durch einen Link in der Konformitätsmeldung erhalten Benutzer mehr [Informationen](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) dazu, wie der erforderliche Sicherheitspatch installiert wird und wie Sie sehen können, welcher Sicherheitspatch aktuell installiert ist.

### iOS-Unternehmensportal-App

- Wenn Endbenutzer branchenspezifische Apps installieren, sehen sie jetzt eine verbesserte Benutzeroberfläche für die App-Installation. Wenn die App-Installation sehr lange dauert, können Benutzer das Gerät manuell synchronisieren, um eine Fortsetzung des Synchronisierungsprozesses zu erzwingen. Die Anweisungen für Endbenutzer finden Sie unter [Manuelles Synchronisieren des Geräts](/Intune/EndUser/sync-your-device-manually-ios).

- Die Microsoft Windows Intune-Unternehmensportal-App für iOS wurde aktualisiert, um die iOS-Version 8.0 und höher zu unterstützen. Dieses Update bedeutet, dass Endbenutzer nur dann die Unternehmensportal-App installieren und neue Geräte in Intune registrieren können, wenn das Gerät iOS Version 8.0 oder höher ausführt. Benutzer, die bereits Geräte registriert haben, auf denen eine nicht unterstützte Version von iOS ausgeführt wird, können weiterhin die auf ihrem Gerät vorhandene Unternehmensportal-App verwenden.


## Was steht an?

### Fahrplan für die Cloud
Halten Sie sich mit dem [Fahrplan für die Cloudplattform](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune) zu den anstehenden Entwicklungen für Intune auf dem Laufenden.

### Veraltete Dienste
- **Intune Viewer-Apps.** Mit der Veröffentlichung der neuen RMS-Freigabe-App werden wir ab August 2016 die folgenden Intune Viewer-Apps entfernen:
    - Intune AV Viewer
    - Intune PDF Viewer
    - Intune Image Viewer für Android aus Google Play

  Anstatt die Intune-Viewer-Apps zu verwenden, empfehlen wir die Nutzung der neuen Rights Management-App (RMS-Freigabe) für Android, die Ihnen das Bereitstellen einer App anstelle von drei getrennten Apps ermöglicht, um Unternehmensdateien sicher auf Android-Geräten anzuzeigen.

- **Entfernung der Zielgruppenadressierung benutzerdefinierter Gruppen bei Benachrichtigungsregeln.**
Intune-Benachrichtigungsregeln definieren, an wen aus Intune eine E-Mail-Benachrichtigung gesendet wird. Derzeit können Sie Benachrichtigungsregeln zum Senden von E-Mails an alle Benutzer von Geräten in einer Intune-Gerätegruppe konfigurieren, die Sie erstellt haben. Ab Anfang Juni 2016 wird die Adressierung von Gruppen, die von Benutzern erstellt wurden, nicht mehr unterstützt.

    Mittlerweile müssen Sie eine Benachrichtigungsregel einer Gruppe, die Sie in der Microsoft Intune-Verwaltungskonsole erstellt haben, wie folgt zuordnen:

    Klicken Sie im Arbeitsbereich **Verwaltung** auf **Benachrichtigungsregeln** > **Neue Regel erstellen**.

    In Schritt 2 des Assistenten zum Erstellen von Benachrichtigungsregeln wählen Sie die Gerätegruppen aus, für die die Regel gelten soll. Der Schritt „Gerätegruppen auswählen“ wurde aus der Intune-Konsole entfernt.

    Der vorläufige Zeitplan für diese Änderung ist wie folgt:
    - Im August 2016 wird Schritt 2 im Assistenten zum Erstellen von Benachrichtigungsregeln nicht mehr für neue Mandanten angezeigt. Vorhandene Mandanten sind nicht betroffen.
    - Ab September 2016 wird einigen vorhandenen Mandanten der Schritt „Gerätegruppen auswählen“ im Assistenten nicht angezeigt.
    - Ab November 2016 wird für alle Mandanten der Schritt „Gerätegruppen auswählen“ im Assistenten nicht mehr angezeigt.


- **Änderungen bei der Unterstützung der iOS-Unternehmensportal-App**. Im Juli müssen alle Benutzer der Microsoft Intune-Unternehmensportal-App für iOS ein Update auf die aktuelle Version durchführen. Neue Benutzer können nur die aktuelle Version herunterladen, und derzeitige Benutzer müssen ein Update auf die aktuelle Version durchführen. Die aktuelle Version erfordert iOS 8.0 oder höher. Daher können Benutzer von Geräten mit älteren iOS-Versionen erst dann das Unternehmensportal nutzen und eine Registrierung durchführen, wenn sie ihr Gerät auf iOS 8.0 oder höher aktualisieren und anschließend die Unternehmensportal-App auf die aktuelle Version aktualisieren. Registrierte Geräte mit Versionen vor iOS 8.0 werden weiterhin verwaltet und in der Intune-Verwaltungskonsole aufgeführt.





## Vorherige Versionen von Intune
Wenn Sie feststellen möchten, was während der letzten sechs Monate in Intune veröffentlicht wurde, sehen Sie sich den Artikel [Vorherige Versionen von Intune](previous-intune-releases.md) an.



### Weitere Informationen:
* [Microsoft Intune-Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Fahrplan für die Cloudplattform](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)



<!--HONumber=Jul16_HO1-->


