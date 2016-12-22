---
title: Vorherige Versionen | Microsoft Intune
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4dab832da4490c3df045d2c627b231028c92b25
ms.openlocfilehash: 3de5e57589a24600301e54a3b60eecb5321ff838


---

# <a name="previous-intune-releases"></a>Vorherige Versionen von Intune

Diese Seite ist eine Liste der Ankündigungen in [Neues in Microsoft Intune ](whats-new-in-microsoft-intune.md).

[!INCLUDE[wit_nextref](../includes/whats-new-last-six-months.md)]

## <a name="may-2016"></a>Mai 2016
Alle diese Features werden auch für hybride Bereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen Hybridfeatures finden Sie auf unserer [Seite mit neuen Hybridfeatures](https://technet.microsoft.com/en-us/library/mt718155.aspx).

### <a name="documentation"></a>Dokumentation
Willkommen bei der Preview-Version von [docs.microsoft.com](https://docs.microsoft.com/en-us/intune)!
Dies ist eine vollständig neue, moderne Inhaltsplattform, die Ihnen, unseren Kunden, helfen soll, Intune zu verstehen und zu nutzen.
Weitere Informationen zu allen neuen Features finden Sie unter [docs.microsoft.com: Einführung](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/).

### <a name="intune-service-health"></a>Status des Intune-Diensts
Informationen zum Status des Intune-Diensts wurden wie für andere Microsoft-Dienste an einen zentralen Speicherort verschoben. Sie finden diese Informationen jetzt im [Verwaltungsportal von Office 365](https://portal.office.com/Admin/Default.aspx) unter **Dienststatus**.
Weitere Informationen finden Sie in [diesem Blogbeitrag](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### <a name="app-management"></a>App-Verwaltung
- **MAM SDK: Unterstützung für die Konfiguration der PIN-Länge.** Sie können die Länge der PIN für MAM-Apps angeben, ähnlich wie eine Geräte-PIN. Dazu müssen Endbenutzer die neuen Einschränkungen einhalten, die Sie festlegen. Sie sehen einen leicht abgewandelten PIN-Bildschirm, mit dem längere Eingaben möglich sind. Weitere Informationen finden Sie unter [MAM-Richtlinien für Android](/intune/deploy-use/android-mam-policy-settings) und [MAM-Richtlinien für iOS](/intune/deploy-use/ios-mam-policy-settings).

- **Skype for Business für iOS und Android.** Sie können jetzt Skype for Business mit [MAM ohne Registrierungsrichtlinien](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) einrichten. Sobald Benutzer angemeldet sind, werden die MAM-Richtlinien angewendet.

- **Neue Apps für die Verwaltung mit MAM-Richtlinien verfügbar.** Die Apps Microsoft Word, Excel und PowerPoint für Android können jetzt MAM-Richtlinien auf Geräten zugeordnet werden, die nicht bei Intune registriert sind. Die vollständige Liste der unterstützten Apps finden Sie im Microsoft Intune-Katalog mit mobilen Anwendungen auf der Seite mit den [Microsoft Intune-Anwendungspartnern](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).


### <a name="company-portal-updates"></a>Aktualisierungen am Unternehmensportal

#### <a name="android-company-portal-app"></a>Android-Unternehmensportal-App
- **Popupbenachrichtigungen für Endbenutzer**: Endbenutzer sehen jetzt Popupbenachrichtigungen in der Android-Unternehmensportal-App, wenn Sie ihre Geräte im Unternehmensportal registrieren oder sie daraus entfernen.

- **Änderungen an den Geräteregistrierungs-Manager-Konten in der Android-Unternehmensportal-App.** Zum Verbessern der Leistung und Skalierung zeigt Intune nicht mehr alle Geräte des Geräteregistrierungs-Managers (Device Enrollment Manager, DEM) im Bereich „Meine Geräte“ der Android-Unternehmensportal-App an. Nur das lokale Gerät, das die App ausführt, wird angezeigt, und dies nur, wenn es über die Unternehmensportal-App registriert wurde. Der DEM-Benutzer kann Aktionen auf dem lokalen Gerät ausführen, aber die Remoteverwaltung der anderen registrierten Geräte kann nur über die Intune-Verwaltungskonsole ausgeführt werden.

#### <a name="company-portal-website"></a>Unternehmensportal-Website
- **Unternehmensportal-Website: Banner für die Geräteidentifikation stellt zusätzliche Informationen für Endbenutzer bereit.** Benutzer können das ausgewählte Gerät nun leichter identifizieren, wenn sie die Unternehmensportal-Website verwenden. Wenn das falsche Gerät ausgewählt wird, können sie das richtige Gerät auswählen, indem sie auf den Link **Hier tippen** im Banner auf der Startseite tippen.

### <a name="service-deprecation"></a>Veraltete Dienste
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


## <a name="april-2016"></a>April 2016
Alle diese Features werden auch für hybride Kundenbereitstellungen (Configuration Manager integriert in Intune) unterstützt.

### <a name="app-management"></a>App-Verwaltung
- **MAM-Benutzerkompatibilität.**
Sie können nun den [Status](/intune/deploy-use/monitor-mobile-app-management-policies-with-Microsoft-Intune) von Anwendungsverwaltungsrichtlinien für alle Benutzer in Ihrem Azure Active Directory-Mandanten (AAD) anzeigen. Dies umfasst u. a.:
   - Geräte
   - Apps auf dem Gerät

   Statuswerte:

   **Eingecheckt**: Gibt an, dass die Richtlinie dem Benutzer bereitgestellt wurde, dass die App im Kontext verwendet wurde und dass sie die Richtlinie erfolgreich empfangen hat.

    **Nicht eingecheckt**: Gibt an, dass die Richtlinie dem Benutzer bereitgestellt wurde, die App seitdem aber nicht im Arbeitskontext verwendet wurde.


- **MAM-Steuerelemente, um die Synchronisierung von Outlook-Kontakten zu verhindern (Android).**
Eine neue Einstellung ist für die [Verwaltung mobiler Anwendungen](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) ohne Registrierung des Geräts verfügbar. Mit dieser Einstellung kann verhindert werden, dass eine Anwendung Kontakte mit dem nativen Adressbuch auf Android-Geräten synchronisiert. Wenn diese Einstellung aktiviert ist, können Zielanwendungen Kontakte nicht mehr im nativen Adressbuch speichern. Wenn diese Einstellung deaktiviert ist, können Zielanwendungen Kontakte im nativen Adressbuch speichern. Wenn Sie [ein Gerät oder eine App remote zurücksetzen](/intune/deploy-use/wipe-managed-company-app-data-with-Microsoft-Intune), werden alle Kontakte entfernt, die bereits im nativen Adressbuch gespeichert wurden. Diese neue Einstellung wird zunächst von der Outlook-Anwendung auf Android-Geräten unterstützt.

### <a name="device-management"></a>Geräteverwaltung
- **Telefonnummeridentifikation für unternehmenseigene Geräte.** Telefone, die als „Unternehmen“ eingestuft sind, werden jetzt mit der vollständigen Telefonnummer identifiziert, wenn Sie beispielsweise einen Inventurbericht für mobile Geräte ausführen. BYOD-Telefonnummern werden weiterhin mit *** maskiert, und nur die letzten vier Ziffern werden angezeigt.


### <a name="company-portal-updates"></a>Aktualisierungen am Unternehmensportal
**Android-Unternehmensportal-App** Benutzer, die ihre Geräte nicht bei Intune registriert haben und die nicht das richtige Zertifikat installiert haben, können sich nicht bei der Android-Unternehmensportal-App anmelden. Ihnen wird die Meldung angezeigt, dass eine Anmeldung nicht möglich sei, da ein erforderliches Zertifikat auf dem Gerät nicht vorhanden sei. Die Meldung enthält einen Link zum Beheben dieses Problems, den Benutzer nutzen können, um eine Anleitung zum Installieren des Zertifikats zu erhalten. Die Schritte, denen die Endbenutzer folgen, um das Problem zu beheben, finden Sie unter [Auf Ihrem Gerät ist ein erforderliches Zertifikat nicht vorhanden](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing).

**iOS-Unternehmensportal-App** Unterstützung für die Aktion „Zum Aktualisieren ziehen“ wurde hinzugefügt, um den Inhalt auf dem Startbildschirm zu aktualisieren, einschließlich der aufgelisteten Apps und Geräte sowie der IT-Kontaktinformationen. Mit der Aktion „Zum Aktualisieren ziehen“ werden Kompatibilitäts- oder Richtlinieninformationen nicht überprüft. Sie erreichen dies, indem Sie die Kachel für das aktuelle Gerät auswählen und auf die Schaltfläche **Synchronisieren** tippen.

**Windows 10 Mobile- und Windows Phone 8.1-Unternehmensportal-App** Wenn Endbenutzer branchenspezifische Apps installieren, sehen sie jetzt eine verbesserte Benutzeroberfläche für die App-Installation. Wenn die App-Installation sehr lange dauert, können Benutzer das Gerät manuell synchronisieren, um eine Fortsetzung des Synchronisierungsprozesses zu erzwingen. Die Anweisungen für Endbenutzer finden Sie unter [Manuelles Synchronisieren des Geräts, um Anwendungsinstallationen zu beschleunigen](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually).

**Unternehmensportal-Website** Wenn Windows 10 Mobile- und Windows Phone 8.1-Benutzer branchenspezifische Apps installieren, sehen sie jetzt die folgenden neuen Status, die ihnen weitere Details zum Status ihrer Installation zur Verfügung zu stellen:

* **Gerätesynchronisierung ausstehend**: Der Benutzer hat auf „Installieren“ getippt hat, und das Gerät versucht nun, eine Synchronisierung mit der Intune-Infrastruktur durchzuführen. Die Synchronisierung ist erforderlich, bevor die Installation abgeschlossen werden kann. Die Meldung „Gerätesynchronisierung ausstehend“ ist außerdem ein Link, auf den Benutzer tippen können, um die [Anweisungen](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) zum manuellen Synchronisieren ihres Geräts mit Intune anzuzeigen, wenn die Synchronisierung sehr lange dauert oder unterbrochen wird.
* **Wird heruntergeladen**: Die Downloadanforderung des Benutzers wird verarbeitet, und das Gerät lädt die App herunter und installiert sie.

Bevor diese Statusangaben hinzugefügt wurden, waren die Benutzer verunsichert, wenn die Installation einer App sehr lange dauerte, da nur ein Status „Wird installiert“ angezeigt wurde – und das möglicherweise für Stunden. Das Hinzufügen der neuen Statusangaben bedeutet, dass sich Benutzer nicht an den Support wenden müssen, sondern auf den Link „Gerätesynchronisierung ausstehend“ tippen und den Anweisungen folgen können, um die Fortsetzung des Synchronisierungsprozesses zu erzwingen.

>[!div class="step-by-step"]

>[&larr; **Neuheiten in Intune**](whats-new-in-microsoft-intune.md)    



<!--HONumber=Dec16_HO1-->


