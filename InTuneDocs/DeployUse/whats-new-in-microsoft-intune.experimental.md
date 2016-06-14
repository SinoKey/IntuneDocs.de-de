---
# required metadata

experiment_id: lindavr-abtest-20160527
title: Neuerungen | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Neuerungen in Microsoft Intune

## Mai 2016


Mit Ausnahme der TeamViewer-Integration werden alle diese Features auch von Hybridbereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen Hybridfeatures finden Sie auf unserer [Seite mit neuen Hybridfeatures](https://technet.microsoft.com/en-us/library/mt718155.aspx).

### Dokumentation

Willkommen bei der Preview-Version von [docs.microsoft.com](https://docs.microsoft.com/en-us/intune)!
Dies ist eine vollständig neue, moderne Inhaltsplattform, die Ihnen, unseren Kunden, helfen soll, Intune zu verstehen und zu nutzen.
Weitere Informationen zu alle neuen Features finden Sie unter [docs.microsoft.com: Einführung](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/).

### Status des Intune-Diensts
Informationen zum Status des Intune-Diensts wurden wie für andere Microsoft-Dienste an einen zentralen Speicherort verschoben. Sie finden diese Informationen jetzt im [Verwaltungsportal von Office 365](https://portal.office.com/Admin/Default.aspx) unter **Dienststatus**.
Weitere Informationen finden Sie in [diesem Blogbeitrag](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).


### App-Verwaltung

- **MAM SDK: Unterstützung für die Konfiguration der PIN-Länge.** Sie können die Länge der PIN für MAM-Apps angeben, ähnlich wie eine Geräte-PIN. Dazu müssen Endbenutzer die neuen Einschränkungen einhalten, die Sie festlegen. Sie sehen einen leicht abgewandelten PIN-Bildschirm, mit dem längere Eingaben möglich sind. Weitere Informationen finden Sie unter [MAM-Richtlinien für Android](/intune/deploy-use/android-mam-policy-settings) und [MAM-Richtlinien für iOS](/intune/deploy-use/ios-mam-policy-settings).

- **Skype for Business für iOS und Android** Sie können jetzt Skype for Business mit [MAM ohne Registrierungsrichtlinien](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) einrichten. Sobald Benutzer angemeldet sind, werden die MAM-Richtlinien angewendet.

- **Neue Apps für die Verwaltung mit MAM-Richtlinien verfügbar.** Die Apps Microsoft Word, Excel und PowerPoint für Android können jetzt MAM-Richtlinien auf Geräten zugeordnet werden, die nicht bei Intune registriert sind. Die vollständige Liste der unterstützten Apps finden Sie im Microsoft Intune-Katalog mit mobilen Anwendungen auf der Seite mit den [Microsoft Intune-Anwendungspartnern](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).

### Geräteverwaltung

- **Remoteunterstützungssitzungen für Windows-PCs.** Mithilfe der von der Intune-Clientsoftware verwalteten TeamViewer-Integration für Windows-PCs können Sie Remoteunterstützungssitzungen mit Windows-PCs einrichten, um Ihre Helpdeskabteilung zu entlasten. PCs mit Windows 7, 8, 8.1 und Windows 10 werden unterstützt.
Weitere Informationen finden Sie unter [Allgemeine Aufgaben zur Verwaltung von Windows-PCs mit dem Microsoft Intune-Computerclient](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#respond-to-a-remote-assistance-request).

### Aktualisierungen am Unternehmensportal

#### Android-Unternehmensportal-App

- **Popupbenachrichtigungen für Endbenutzer**: Endbenutzer sehen jetzt Popupbenachrichtigungen in der Android-Unternehmensportal-App, wenn Sie ihre Geräte im Unternehmensportal registrieren oder sie daraus entfernen.

- **Änderungen an den Geräteregistrierungs-Manager-Konten in der Android-Unternehmensportal-App.** Zum Verbessern der Leistung und Skalierung zeigt Intune nicht mehr alle Geräte des Geräteregistrierungs-Managers (Device Enrollment Manager, DEM) im Bereich „Meine Geräte“ der Android-Unternehmensportal-App an. Nur das lokale Gerät, das die App ausführt, wird angezeigt, und dies nur, wenn es über die Unternehmensportal-App registriert wurde. Der DEM-Benutzer kann Aktionen auf dem lokalen Gerät ausführen, aber die Remoteverwaltung der anderen registrierten Geräte kann nur über die Intune-Verwaltungskonsole ausgeführt werden.
-
#### Unternehmensportal-Website

**Unternehmensportal-Website: Banner für die Geräteidentifikation stellt zusätzliche Informationen für Endbenutzer bereit.** Benutzer können das Gerät nun leichter identifizieren, das sie ausgewählt haben, wenn sie die Unternehmensportal-Website verwenden. Wenn das falsche Gerät ausgewählt wird, können sie das richtige Gerät auswählen, indem sie auf den Link **Hier tippen** im Banner auf der Startseite tippen.


## Was steht an?

- **Integration des Nachrichtencenters** Im Rahmen der Migration von Intune in das [Office 365-Verwaltungsportal](https://portal.office.com/) beginnen wir damit, das Nachrichtencenter zu nutzen, um über neue Features und andere Benachrichtigungen zu informieren. Wenn Sie zudem die mobile Begleit-App Office 365 Admin installieren, können Sie Benachrichtigungen auf Ihrem Mobiltelefon empfangen und problemlos alle Nachrichten an Benutzer oder einen Verteilungsalias weiterleiten.
Wir beginnen mit unserer Maiversion damit, das Nachrichtencenter zu nutzen, um Sie zu benachrichtigen, wenn Updates abgeschlossen sind, und wir werden Informationen zu neuen und verbesserten Features von Intune aufnehmen. Sehen Sie sich das Nachrichtencenter noch heute an, indem Sie sich beim [Office 365-Verwaltungsportal](https://portal.office.com/) anmelden und im linken Navigationsbereich die Option NACHRICHTENCENTER auswählen.

- **Änderungen an den Konten für Geräteregistrierungs-Manager**. Zum Verbessern der Leistung und Skalierung zeigt Intune nicht mehr **alle** Geräte des **Geräteregistrierungs-Managers (Device Enrollment Manager, DEM)** im Bereich „Meine Geräte“ der iOS-Unternehmensportal-App an. Nur das lokale Gerät, das die App ausführt, wird angezeigt, und dies nur, wenn es über die Unternehmensportal-App registriert wurde. Der DEM-Benutzer kann Aktionen auf dem lokalen Gerät ausführen, aber die Remoteverwaltung der anderen registrierten Geräte kann nur über die Intune-Verwaltungskonsole ausgeführt werden. Darüber hinaus wird in Intune die Verwendung von DEM-Konten mit dem Apple-Geräteregistrierungsprogramm oder dem Apple Configurator-Tool eingestellt. Diese beiden Registrierungsmethoden unterstützen bereits die benutzerunabhängige Registrierung für gemeinsam genutzte iOS-Geräte. Verwenden Sie DEM-Konten nur, wenn die benutzerunabhängige Registrierung für gemeinsam genutzte Geräte nicht verfügbar ist.

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

    Derzeit müssen Sie eine Benachrichtigungsregel einer Gruppe, die Sie in der Microsoft Intune-Verwaltungskonsole erstellt haben, wie folgt zuordnen:

    Klicken Sie im Arbeitsbereich **Verwaltung** auf **Benachrichtigungsregeln** > **Neue Regel erstellen**.

    In Schritt 2 des Assistenten zum Erstellen von Benachrichtigungsregeln wählen Sie die Gerätegruppen aus, für die die Regel gelten soll. Der Schritt „Gerätegruppen auswählen“ wurde aus der Intune-Konsole entfernt.

    Der vorläufige Zeitplan für diese Änderung ist wie folgt:
    - Juni 2016 wird neuen Mandanten Schritt 2 im Assistenten zum Erstellen von Benachrichtigungsregeln nicht mehr angezeigt. Vorhandene Mandanten sind nicht betroffen.
    - Ab August 2016 wird einigen vorhandenen Mandanten der Schritt „Gerätegruppen auswählen“ im Assistenten nicht angezeigt.
    - Ab Oktober 2016 wird allen Mandanten der Schritt „Gerätegruppen auswählen“ im Assistenten nicht mehr angezeigt.


- **Änderungen bei der Unterstützung der iOS-Unternehmensportal-App**. In den kommenden Monaten erfolgt ein Update für die Microsoft Intune-Unternehmensportal-App für iOS, die nur Geräte mit mindestens iOS 8.0 unterstützt. Benutzer können neue Geräte mit Versionen unter iOS 8.0 nicht registrieren. Registrierte Geräte mit Versionen unter iOS 8.0 werden weiterhin verwaltet und können für einen begrenzten Zeitraum die Unternehmensportal-App weiter nutzen. Für den Zugriff auf die neuesten Versionen der Unternehmensportal-App benötigen Geräte mindestens die iOS-Version 8.0. Wir empfehlen Ihnen, Benutzer zum Update auf iOS 8.0 oder höher aufzufordern, damit sie in den vollen Genuss der neuen Intune-Features kommen.



## Vorherige Versionen von Intune
Wenn Sie feststellen möchten, was während der letzten sechs Monate in Intune veröffentlicht wurde, sehen Sie sich den Artikel [Vorherige Versionen von Intune](previous-intune-releases.md) an.
> [!div class="op_single_selector"]
- [April 2016](previous-intune-releases.md)
- [März 2016](previous-intune-releases.md)
- [Februar 2016](previous-intune-releases.md)
- [Januar 2016](previous-intune-releases.md)
- [Dezember 2015](previous-intune-releases.md)
- [November 2015](previous-intune-releases.md)




### Weitere Informationen:
* [Microsoft Intune-Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Fahrplan für die Cloudplattform](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)


<!--HONumber=Jun16_HO1-->


