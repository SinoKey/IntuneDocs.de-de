---
# required metadata

title: Verwaltungsfunktionen für mobile Geräte | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f23b3ee7-78da-4e53-9fc2-78e58401bcf9

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---
# Verwaltungsfunktionen für mobile Geräte in Microsoft Intune

Mit Microsoft Intune können Sie eine Vielzahl von Geräten verwalten, indem Sie diese beim Dienst *registrieren*. Benutzer können dann über ein *Unternehmensportal* eine Reihe von Vorgängen ausführen, z. B. ihr Gerät registrieren, Apps suchen und installieren, sicherstellen, dass ihr Gerät die Unternehmensrichtlinien erfüllt und sich an ihren IT-Support wenden.
Dieses Thema bietet eine vollständige Liste der Funktionen, die Ihnen durch die Registrierung Ihrer Geräte zur Verfügung stehen.

Verwaltung, Bestandserfassung, Bereitstellung und Außerbetriebnahme von Geräten und Apps erfolgen über die Intune-Verwaltungskonsole. Benutzer erhalten Zugriff auf das Unternehmensportal, das ihnen ermöglicht, Apps zu installieren, Geräte zu registrieren und zu entfernen und die Kontaktaufnahme mit der IT-Abteilung oder dem Helpdesk erleichtert.



## Gerätesicherheit und Konfiguration

|Funktion|Details|Weitere Informationen|
|--------------|-----------|--------------------|
|Konfigurationsrichtlinien<br><br>Benutzerdefinierte Richtlinien|Mit Konfigurationsrichtlinien für mobile Geräte können Sie viele Einstellungen und Features auf mobilen Geräten in Ihrer Organisation verwalten. Für alle Plattformen kann das Anfordern eines Kennworts, das Beschränken der Anzahl misslungener Anmeldeversuche, das Begrenzen des Zeitraums bis zur Sperrung des Bildschirms, das Festlegen eines Zeitraums für den Kennwortablauf und das Unterbinden der erneuten Verwendung zuvor bereits verwendeter Kennwörter festgelegt werden. Sie können auch die Verwendung von Hardware- und Softwarefunktionen steuern, z. B. die Verwendung der Gerätekamera oder des Webbrowsers.<br><br>Verwenden Sie benutzerdefinierte Richtlinien, wenn Konfigurationsrichtlinien nicht die Einstellung enthalten, die Sie benötigen. Bei iOS-Geräten können Sie die Einstellungen importieren, die Sie aus dem Apple Configurator Tool exportiert haben. Bei anderen Geräten können Sie OMA-URI-Einstellungen verwenden, um Einstellungen und Features auf dem Gerät zu konfigurieren.|[Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)<br />|
|Remotezurücksetzen, Remotesperre und Kennungsrückstellung|Löschen Sie vertrauliche Daten, wenn ein Gerät verloren geht oder gestohlen wird. Beispielsweise können Sie das Gerät remote sperren, die Werkseinstellungen wiederherstellen oder nur Unternehmensdaten zurücksetzen.<br>Sie können Passcodes zurücksetzen, wenn Benutzer nicht mehr auf ihr Gerät zugreifen können, und verlorene oder gestohlene Geräte sperren oder alle darauf vorhandenen Daten zurücksetzen.|[Geräteschutz durch Remotesperre und Zurücksetzen der Kennung](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune) und [ Außerkraftsetzen von Geräten in der Intune Verwaltung](/intune/deploy-use/retire-devices-from-microsoft-intune-management)|
|Kioskmodus|Hiermit können Sie bestimmte Features von mobilen Geräten sperren, z. B. die Bildschirmaufnahme und den Netzschalter. Außerdem können Sie Geräte auf die Ausführung einer einzigen, von Ihnen angegebenen App beschränken.|[Einstellungen für iOS-Konfigurationsrichtlinien in Microsoft Intune](/intune/deploy-use/ios-policy-settings-in-microsoft-intune)|

## App-Verwaltung

|Funktion|Details|Weitere Informationen|
|--------------|-----------|--------------------|
|App-Bereitstellung und -Verwaltung|Bietet eine Reihe von Tools zum Verwalten von mobilen Apps während deren Lebenszyklus, einschließlich der App-Bereitstellung von Installationsdateien und App Stores sowie eine detaillierte Überwachung des Status der App und App-Entfernung.|[Bereitstellen von Anwendungen in Microsoft Intune](/intune/deploy-use/deploy-apps)|
|Kompatible und nicht kompatible Anwendungen|Damit können Sie Listen der kompatiblen Apps (die Benutzer installieren dürfen) und nicht kompatiblen Apps (die nicht von Benutzern installiert werden dürfen) angeben.|[iOS-Richtlinieneinstellungen in Microsoft Intune](/intune/deploy-use/ios-policy-settings-in-microsoft-intune)|
|Mobile Anwendungsverwaltung|Konfigurieren Sie Einschränkungen für Apps mithilfe der mobilen Anwendungsverwaltung für Geräte, die mit Intune verwaltet werden, und Geräte, die nicht von Intune verwaltet werden. Dadurch können Sie die Sicherheit Ihrer Unternehmensdaten erhöhen, indem Sie Vorgänge wie das Kopieren und Einfügen, die externe Sicherung von Daten und die Übertragung von Daten zwischen Apps einschränken.|[Configure and deploy mobile application management policies in the Microsoft Intune console](/intune/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console)<br><br>[Erstellen und Bereitstellen von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)<br /><br />[Vorbereiten von iOS-Apps für die Verwaltung mobiler Anwendungen mit dem Microsoft Intune App Wrapper-Tool](/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)<br /><br />[Vorbereiten von Android-Apps für die Verwaltung von mobilen Anwendungen mit dem Microsoft Intune App Wrapper-Tool](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)|
|Konfiguration mobiler Apps|Verwenden Sie Konfigurationsrichtlinien für mobile Apps, um Einstellungen für iOS anzugeben, die beim Ausführen der App durch den Benutzer erforderlich sein können. Beispielsweise kann eine App erfordern, dass der Benutzer eine Portnummer oder Anmeldeinformationen angibt. Dies kann helfen, die Konfiguration der App zu optimieren und die Anzahl der Anrufe beim Helpdesk zu verringern.|[Konfigurieren von iOS-Apps mit Konfigurationsrichtlinien für mobile Apps in Microsoft Intune](/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)|
|Managed Browser|Nachdem Sie den Managed Browser für Ihre Benutzer bereitgestellt haben, können Sie mithilfe einer Richtlinie für Managed Browser steuern, welche Websites die Benutzer besuchen dürfen. Darüber hinaus können Sie Richtlinien zur mobilen Anwendungsverwaltung auf den Managed Browser anwenden.|[Verwalten des Internetzugriffs mittels Richtlinien für verwaltete Browser mit Microsoft Intune](/intune/deploy-use/manage-internet-access-using-managed-browser-policies)|
|Microsoft Passport|Intune ermöglicht die Integration in Microsoft Passport for Work. Dies ist eine alternative Anmeldemethode für Windows 10, die Active Directory oder ein Azure Active Directory-Konto verwendet, um ein Kennwort, eine Smartcard oder eine virtuelle Smartcard zu ersetzen.|[Steuern von Microsoft Passport-Einstellungen auf Geräten mit Microsoft Intune](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)|

## Zugriff auf Unternehmensressourcen

|Funktion|Details|Weitere Informationen|
|--------------|-----------|--------------------|
|Zertifikatprofile|Erstellt und bietet Tools zum Erstellen und Bereitstellen von vertrauenswürdigen Zertifikatprofilen und Simple Certificate Enrollment Protocol-Zertifikaten (SCEP), die zum Sichern und Authentifizieren von WLAN-, VPN- und E-Mail-Profilen verwendet werden können.|[Sicherer Zugriff auf Ressourcen mit Zertifikatprofilen in Microsoft Intune](/intune/deploy-use/secure-resource-access-with-certificate-profiles)|
|WLAN-Profile|Bereitstellen von Einstellungen für drahtlose Netzwerke für Ihre Benutzer. Durch Bereitstellen dieser Einstellungen erleichtern Sie dem Endbenutzer das Herstellen einer Verbindung mit dem Unternehmensnetzwerk.|[WLAN-Verbindungen in Microsoft Intune](/intune/deploy-use/wi-fi-connections-in-microsoft-intune)|
|E-Mail-Profile|Erstellen und Bereitstellen von E-Mail-Einstellungen für Geräte. Auf diese Weise erhalten Benutzer Zugriff auf Unternehmens-E-Mails auf ihren persönlichen Geräten, ohne dafür ein Setup vornehmen zu müssen.|[Konfigurieren des Zugriffs auf Unternehmens-E-Mail mithilfe von E-Mail-Profilen in Microsoft Intune](/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)|
|VPN-Profile|Stellen Sie VPN-Einstellungen für Benutzer und Geräte in Ihrer Organisation bereit. Durch Bereitstellen dieser Einstellungen erleichtern Sie dem Endbenutzer das Verbinden mit Ressourcen im Unternehmensnetzwerk.|[VPN-Verbindungen in Microsoft Intune](/intune/deploy-use/vpn-connections-in-microsoft-intune)|
|Bedingte Zugriffsrichtlinien|Verwalten des Zugriffs auf Microsoft Exchange-E-Mail- und SharePoint Online auf Geräten, die nicht von Intune verwaltet werden.|[Beschränken des Zugriffs auf E-Mail und SharePoint mit Microsoft Intune](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)|

## Inventar und Berichterstellung

|Funktion|Details|Weitere Informationen|
|--------------|-----------|--------------------|
|Inventar und Berichterstellung|Suchen Sie nach Informationen zu den Geräten, die Sie verwalten, und der Software, die sie verwenden.|[Verstehen Sie Ihre Geräte mithilfe des Inventars in Microsoft Intune](./deploy-use/understand-your-devices-with-inventory-in-microsoft-intune)|


### Weitere Informationen:
[Funktionen für die Windows-PC-Verwaltung in Microsoft Intune](./windows-pc-management-capabilities-in-microsoft-intune.md)


<!--HONumber=May16_HO2-->


