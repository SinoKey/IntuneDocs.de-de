---
title: "Aktualisierungen für die Benutzeroberfläche für Endbenutzer-Apps in Intune | Microsoft-Dokumentation"
description: "Erfahren Sie, was sich an der Benutzeroberfläche für Apps geändert hat, die auf Endbenutzergeräten mit Intune funktionieren."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b782e382-8deb-48a7-a437-d7c5a17163f1
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: a9748a0ad6b9bbe10e36ba133ba74edb6aa6e09a
ms.openlocfilehash: 68dbaa2209ad1432279683a291734641e39ff736
ms.contentlocale: de-de
ms.lasthandoff: 05/05/2017


---
# <a name="ui-updates-for-intune-end-user-apps"></a>Aktualisierungen für die Benutzeroberfläche für Endbenutzer-Apps in Intune
Erfahren Sie, welche Aktualisierungen wir an der Benutzeroberfläche für Apps vorgenommen haben, die Ihre Endbenutzer in dieser Version von Microsoft Intune sehen werden. Damit werden Sie bei der Benutzerkommunikation sowie bei allen aktualisierten Benutzerdokumentationen unterstützt, die Sie zur Unterstützung Ihrer Entwicklung erstellt haben. Es kann auch helfen, zu verstehen, wie Probleme behandelt werden, die auftauchen, wenn Benutzer den Helpdesk für den Support mithilfe des Unternehmensportals aufrufen.

## <a name="coming-soon-in-the-ui"></a>In Kürze auf der Benutzeroberfläche verfügbar
Es folgen die Pläne für Möglichkeiten zum Verbessern der Benutzererfahrung durch Ändern unserer Benutzeroberfläche.

> [!Note]
> Beachten Sie, dass die Bilder unten eine Vorschau darstellen und das angekündigte Produkt sich von den abgebildeten Versionen unterscheiden kann.

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Verbesserter Anmeldevorgang für alle Unternehmensportal-Apps auf allen Plattformen <!--User Story 1132123-->

Wir kündigen eine in den nächsten Monaten kommende Änderung an, durch die der Anmeldevorgang für die Intune-Unternehmensportal-Apps für Android, iOS und Windows verbessert wird. Die neue Benutzeroberfläche wird für die Unternehmensportal-App automatisch auf allen Plattformen eingeführt, sobald Azure AD die Änderung umsetzt. Darüber hinaus können Benutzer sich jetzt mithilfe eines generierten Codes zur einmaligen Verwendung von einem anderen Gerät aus beim Unternehmensportal anmelden. Dies ist besonders nützlich, wenn Benutzer sich ohne Anmeldeinformationen anmelden müssen.  

Unten sehen Sie die vorherige Anmeldeoberfläche, die neue Anmeldeoberfläche mit Anmeldeinformationen und die neue Anmeldeoberfläche zur Anmeldung von einem anderen Gerät aus.

__Vorherige Anmeldeoberfläche__

![Die Seite für die Anmeldung beim Unternehmensportal mit einem Symbol für eine Person vor der grafischen Darstellung einer Website. Darunter befindet sich die Schaltfläche zum Anmelden. Ein Link am unteren Seitenrand führt zu Informationen von Microsoft zu Datenschutz und Cookies.](./media/cp_ios_aad_signin_before_1704_001.png)

![Nach dem Tippen auf „Anmelden“ geben Benutzer auf dieser Seite ihre Anmeldeinformationen ein. Die Seite erfordert die Eingabe von E-Mail-Adresse und Kennwort und bietet Möglichkeiten, Kennwortfehler zu beheben.](./media/cp_ios_aad_signin_before_1704_002.png)

![Nach Eingabe des Kennworts meldet sich die Unternehmensportal-App an und zeigt einen Ladebalken an.](./media/cp_ios_aad_signin_before_1704_003.png)

__Neue Anmeldeoberfläche__

![Die Seite für die Anmeldung beim Unternehmensportal mit einem Symbol für eine Person vor der grafischen Darstellung einer Website. Darunter befindet sich die Schaltfläche zum Anmelden. Ein Link am unteren Seitenrand führt zu Informationen von Microsoft zu Datenschutz und Cookies.](./media/cp_ios_aad_signin_after_1704_001.png)

![Der Benutzer wird nur zur Eingabe der E-Mail-Adresse aufgefordert, nicht zur Eingabe von E-Mail-Adresse und Kennwort im gleichen Bildschirm.](./media/cp_ios_aad_signin_after_1704_002.png)

![Der Benutzer wird erst zur Eingabe des Kennworts aufgefordert, wenn die E-Mail-Adresse akzeptiert wurde.](./media/cp_ios_aad_signin_after_1704_003.png)

![Nach Abschluss des Authentifizierungsprozesses meldet sich die Unternehmensportal-App an und zeigt einen entsprechenden Ladebalken an.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

__Neue Anmeldeoberfläche bei Anmeldung von einem anderen Gerät aus__

![Die Seite für die Anmeldung beim Unternehmensportal mit einem Symbol für eine Person vor der grafischen Darstellung einer Website. Darunter befindet sich die Schaltfläche zum Anmelden. Ein Link am unteren Seitenrand führt zu Informationen von Microsoft zu Datenschutz und Cookies.](./media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

Tippen Sie auf den Link __Von anderem Gerät aus anmelden__.

![Der Benutzer erhält die Anweisung, mit einem über den Arbeitscomputer bezogenen eindeutigen Passcode zur Seite „aka.ms/devicelogin“ zu wechseln und sich dort mit dem Code anzumelden.](./media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

Starten Sie einen Browser, und wechseln Sie zu [https://aka.ms/devicelogin](https://aka.ms/devicelogin).

![Ein Bild des Browsers des Benutzers auf dem Arbeitscomputer statt in der Unternehmensportal-App. Die angezeigte Seite „Geräteanmeldung“ fordert den Benutzer auf, den über die Unternehmensportal-App empfangenen Code einzugeben.](./media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

Geben Sie den Code ein, den Sie in der Unternehmensportal-App erhalten haben. Wenn Sie __Weiter__ auswählen, können Sie sich mit jeder von Ihrem Unternehmen unterstützten Methode authentifizieren, z.B. per Smartcard.

![Der Benutzer hat den eindeutigen Code in das Feld eingegeben und wurde auf der Seite „Geräteanmeldung“ aufgefordert, zu bestätigen, dass das Intune-Unternehmensportal die App ist, die zur Anmeldung autorisiert werden soll.](./media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

![Eine Bestätigungsseite informiert darüber, dass der Benutzer sich jetzt auf dem Gerät bei der Unternehmensportal-App angemeldet hat und dass diese Seite geschlossen werden kann.](./media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

Die Unternehmensportal-App beginnt mit der Anmeldung.

![Nach Abschluss des Authentifizierungsprozesses meldet sich die Unternehmensportal-App an und zeigt einen entsprechenden Ladebalken an.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

## <a name="april-2017"></a>April 2017

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Neue Symbole für Managed Browser und das Unternehmensportal <!--918433, 918431-->

Managed Browser erhält aktualisierte Symbole für die Android- und iOS-Versionen der App. Das neue Symbol enthält den aktualisierten Intune-Badge, damit es konsistenter mit anderen Apps in Enterprise Mobility + Security (EM+S) wird.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_manbro_before_042017.png" alt="The previous version of the Managed Browser app icon." width=200 height=366 align=center>
          </td>
          <td>
             <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_manbro_after_042017.png" alt="The updated version of the Managed Browser app icon." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

Das Unternehmensportal erhält auch aktualisierte Symbole für die Android-, iOS- und Windows-Versionen der App, um die Konsistenz mit anderen Apps in EM+S zu verbessern. Diese Symbole werden von April bis Ende Mai schrittweise auf den Plattformen veröffentlicht.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Statusanzeige zur Anmeldung im Android-Unternehmensportal <!--953374-->

Ein Update auf die Android-Unternehmensportal-App zeigt eine Statusanzeige der Anmeldung an, wenn der Benutzer die App startet oder fortsetzt. Der Indikator durchläuft neue Status, beginnend mit „Verbinden...“, „Anmelden...“, dann „Checking for security requirements...“ (Suche nach Sicherheitsanforderungen...), bevor dem Benutzer erlaubt wird, auf die App zuzugreifen.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_connecting_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Connecting' underneath it." width=200 height=366 align=center>
          </td>
          <td>
             <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_signing_in_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Signing in' underneath it." width=200 height=366 align=center>
           </td>
           <td>
              <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_checking_security_reqs_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Checking for security requirements' underneath it." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Verbesserter App-Installationsstatus für die Windows 10-Unternehmensportal-App <!--676495-->
Die Windows 10-Unternehmensportal-App bietet jetzt auf der Seite mit den App-Details eine Installationsstatusanzeige. Diese wird für moderne Apps auf Geräten mit Windows 10 Anniversary Update und höher unterstützt.

__Vorher__
  ![ Eine Abbildung der vorherigen Version des Ladebildschirms, auf dem der Status schlicht „Wird installiert“ lautet.](./media/cp_win10_install_status_before_1704.png)

__Nachher__
  ![ Eine Abbildung der aktualisierten Version des Ladebildschirms, der nun eine Statusanzeige für die Installation zeigt.](./media/cp_win10_install_status_after_1704.png)

## <a name="february-2017"></a>Februar 2017

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622-announced-1702--"></a>Neue Benutzeroberfläche für die Unternehmensportal-App für Android <!--621622, announced 1702-->
Ab März befolgt die Unternehmensportal-App für Android die [material design guidelines (Richtlinien für Materialdesign)](https://material.io/guidelines/material-design/introduction.html), um ein moderneres Erscheinungsbild zu vermitteln. Diese verbesserte Benutzeroberfläche enthält Folgendes:

* __Farben__: Die Farben der Registerkartentitel können mithilfe Ihrer benutzerdefinierten Farbpalette angepasst werden.

![Auf der linken Seite sehen Sie ein Bild der Unternehmensportal-App für Android vor der Aktualisierung. Auf der rechten Seite sehen Sie ein Bild der Unternehmensportal-App für Android nach der Aktualisierung. Beide Bilder zeigen als ausgewählte Registerkarte die Registerkarte „Geräte“ aus den drei Registerkarten „Apps“, „Geräte“ und „An IT-Abteilung wenden“.](./media/CP_Android_DevicesTab_BeforeAfter.png)

* __Schnittstelle__: Die Schaltflächen __Empfohlene Apps__ und __Alle Apps__ wurden in der Registerkarte __Apps__ aktualisiert. Die Schaltfläche __Suche__ ist nun eine unverankerte interaktive Schaltfläche.

![Auf der linken Seite sehen Sie ein Bild der Unternehmensportal-App für Android vor der Aktualisierung. Auf der rechten Seite sehen Sie ein Bild der Unternehmensportal-App für Android nach der Aktualisierung. Beide Bilder zeigen als ausgewählte Registerkarte die Registerkarte „Apps“ aus den drei Registerkarten „Apps“, „Geräte“ und „An IT-Abteilung wenden“.](./media/CP_Android_AppsTab_BeforeAfter.png)

* __Navigation__: Alle Apps zeigen die Registerkartenansicht __Featured__ (Highlights), __Alle__ und __Kategorien__ für die einfachere Navigation. __An IT-Abteilung wenden__ wurde zur besseren Lesbarkeit optimiert.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_contactit_after.png" alt="The Company Portal app for Android displaying an updated version of the Contact IT tab. The tab shows available contact information for IT, including phone number, email address, IT website, and IT contact information." width=200 height=366 align=center>
          </td>
      </tr>
   </table>
</body>
</html>

## <a name="january-2017"></a>Januar 2017

### <a name="modernizing-the-company-portal-website---753980-announced-1701--"></a>Modernisieren der Unternehmensportal-Website<!--753980, announced 1701-->
Ab Februar unterstützt die Unternehmensportal-Website Apps, die für Benutzer bestimmt sind, die über keine verwalteten Geräte verfügen. Die Website wird an andere Microsoft-Produkte und -Dienste mithilfe eines neuen Farbschemas, dynamischen Illustrationen und einem „Hamburger-Menü“ ausgerichtet, ![Miniaturansicht des Hamburger-Menüs, das nun in der linken oberen Ecke der Unternehmensportal-App zu sehen ist,](./media/CP_hamburger_menu.png) das nun Helpdesk-Kontaktdetails enthält sowie Informationen zu vorhandenen verwalteten Diensten. Die Angebotsseite wird neu angeordnet, um Apps hervorzuheben, die für Benutzer verfügbar sind, und mit einer Karussellsicht für empfohlene und kürzlich aktualisierte Apps.

![Auf der linken Seite sehen Sie ein Bild der aktuellen Version der Unternehmensportal-Website mit den derzeitigen Versionen von Apps, Meine Geräte sowie den Ansichten „Featured“ (Highlights) und „Kategorien“. Auf der rechten Seite sehen Sie ein Bild der neuen Version der Unternehmensportal-Website mit einem aktualisierten App-Karussell, einer Liste mit kürzlich veröffentlichten Apps und einer aktualisierten Ansicht „Kategorien“.](./media/CP_Website_BeforeAfter_Feb2016.png)


### <a name="see-also"></a>Weitere Informationen:
* [Microsoft Intune-Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap für die Cloudplattform](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Neuigkeiten in der Azure-Vorschau](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Neuheiten – Archiv](whats-new-archive.md)

