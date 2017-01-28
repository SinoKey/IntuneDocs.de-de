---
title: "Apple-DEP-Verwaltung für iOS-Geräte | Microsoft-Dokumentation"
description: "Stellen Sie ein Registrierungsprofil bereit, das über das iOS-Programm zur Geräteregistrierung (Device Enrollment Program, DEP) erworbene iOS-Geräte drahtlos registriert, damit Sie Apple-Geräte verwalten können."
keywords: 
author: staciebarker
ms.author: stabar
manager: arob98
ms.date: 12/31/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8ff9d9e7-eed8-416c-8508-efc20fca8578
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8063b933a767740a7951fa69a918a8677b664d02
ms.openlocfilehash: e8a21ace32b5668f8158b9a383b882b7c2f524df


---

# <a name="enroll-corporate-owned-device-enrollment-program-ios-devices"></a>Registrieren unternehmenseigener iOS-Geräte mithilfe des Programm zur Geräteregistrierung (Device Enrollment Program, DEP)

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune kann ein Registrierungsprofil bereitstellen, das über das Programm zur Geräteregistrierung (Device Enrollment Program, DEP) erworbene iOS-Geräte drahtlos registriert. Das Registrierungspaket kann Setup-Assistent-Optionen für das Gerät enthalten. Die Registrierung von Geräten über DEP kann von Benutzern nicht rückgängig gemacht werden.

## <a name="apple-dep-management-for-ios-devices-with-microsoft-intune"></a>Apple-DEP-Verwaltung für iOS-Geräte mit Microsoft Intune
Zum Verwalten unternehmenseigener iOS-Geräte mit dem Apple-Programm zur Geräteregistrierung (Device Enrollment Program, DEP) müssen Unternehmen am Apple-DEP teilnehmen und Geräte über das Programm beziehen. Details zu diesem Prozess finden Sie unter:  [https://deploy.apple.com](https://deploy.apple.com). Das Programm bietet den Vorteil, dass Geräte eingerichtet werden können, ohne dass ein USB-Kabel für die Verbindung jedes Geräts mit einem Computer verwendet werden muss.

Bevor Sie unternehmenseigene iOS-Geräte mit DEP registrieren können, benötigen Sie ein DEP-Token von Apple. Mit diesem Token kann Intune Informationen zu DEP-Geräten synchronisieren, die Ihrem Unternehmen gehören. Damit kann Intune außerdem Registrierungsprofile an Apple übermitteln und diesen Profile Geräte zuweisen.

1.  **Beginnen der Verwaltung von iOS-Geräten mit Microsoft Intune**</br>
    Bevor Sie iOS-DEP-Geräte (Device Enrollment Program, Programm zur Geräteregistrierung) registrieren können, müssen Sie die Aktivierung der iOS-Verwaltung für Intune abschließen.

2.  **Abrufen eines Verschlüsselungsschlüssels**</br>
    Öffnen Sie als Administrator die [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com), wechseln Sie zu **Verwaltung** &gt; **Verwaltung mobiler Geräte** &gt; **iOS** &gt; **Programm zur Geräteregistrierung**, und wählen Sie anschließend **Verschlüsselungsschlüssel herunterladen** aus. Speichern Sie die Verschlüsselungsschlüsseldatei (PEM) lokal. Die PEM-Datei wird verwendet, um ein Vertrauensstellungszertifikat vom Apple Device Enrollment Program-Portal anzufordern.

      ![Abrufen eines Tokens für Geräteregistrierungsprogramm](../media/dev-sa-ios-dep.png)

3.  **Abrufen eines Device Enrollment Program-Tokens**</br>
    Wechseln Sie zum [Portal des Programms zur Geräteregistrierung](https://deploy.apple.com) (https://deploy.apple.com), und melden Sie sich mit Ihrer Unternehmens-Apple-ID an. Diese Apple-ID muss später verwendet werden, um Ihr DEP-Token zu erneuern.

    1.  Wechseln Sie im [Portal des Programms zur Geräteregistrierung](https://deploy.apple.com) zu **Programm zur Geräteregistrierung** &gt; **Server verwalten**, und wählen Sie anschließend **MDM-Server hinzufügen** aus.

    2.  Geben Sie den **MDM-Servernamen** ein, und wählen Sie anschließend **Weiter** aus. Der Servername dient als Referenz zum Identifizieren des MDM-Servers (mobile device management, Verwaltung mobiler Geräte). Es handelt sich nicht um den Namen oder die URL des Microsoft Intune-Servers.

    3.  Das Dialogfeld **&lt;Servername&gt; hinzufügen** wird geöffnet. Wählen Sie **Datei auswählen** aus, um die PEM-Datei hochzuladen, und wählen Sie anschließend **Weiter** aus.

    4.  Im Dialogfeld **&lt;Servername&gt; hinzufügen** wird der Link **Ihr Servertoken** angezeigt. Laden Sie die Servertokendatei (.p7m) auf Ihren Computer herunter, und wählen Sie anschließend **Fertig** aus.

    Diese Zertifikatdatei (.p7m) wird verwendet, um eine Vertrauensstellung zwischen dem Intune- und Apple Device Enrollment Program-Server herzustellen.

4.  **Hinzufügen des DEP-Tokens zu Intune**</br>
    Wechseln Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) zu **Verwaltung** &gt; **Verwaltung mobiler Geräte** &gt; **iOS** &gt; **Programm zur Geräteregistrierung**, und wählen Sie anschließend **DEP-Token hochladen** aus. **Wechseln Sie** zur Zertifikatdatei (.p7m), geben Sie Ihre **Apple-ID**ein, und wählen Sie anschließend **Hochladen** aus.

5.  **Hinzufügen der Corporate Device Enrollment-Richtlinie**</br>
    Wechseln Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) zu **Richtlinie** &gt; **Unternehmensgeräteregistrierung**, und wählen Sie anschließend **Hinzufügen** aus.

    Geben Sie **allgemeine** Details ein, wie z.B. **Name** und **Beschreibung**. Geben Sie außerdem an, ob die dem Profil zugeordneten Geräte zu einem Benutzer oder einer Gruppe gehören.
      - **Benutzeraffinität anfordern**: Das Gerät muss während der ersten Installation einem Benutzer zugewiesen werden, bevor es dazu berechtigt sein kann, im Namen dieses Benutzers auf Unternehmensdaten und -E-Mails zuzugreifen. **Benutzeraffinität** muss für DEP-verwaltete Geräte eingerichtet werden, die Benutzern gehören und das Unternehmensportal verwenden müssen (um Apps zu installieren). Mehrstufige Authentifizierung (Multifactor authentication, MFA) funktioniert nicht während der Registrierung auf DEP-Geräten mit Benutzeraffinität. Nach der Registrierung funktioniert die MFA auf diesen Geräten wie erwartet. 

      > [!NOTE]
      > Für DEP mit Benutzeraffinität muss der Endpunkt WS-Trust 1.3 Username/Mixed aktiviert sein, um Benutzertoken anzufordern.

      - **Keine Benutzeraffinität**: Das Gerät ist keinem Benutzer zugeordnet. Verwenden Sie diese Zuweisung für Geräte, die Aufgaben ohne den Zugriff auf lokale Benutzerdaten ausführen. Apps, die eine Benutzerzugehörigkeit erfordern, einschließlich der Unternehmensportal-App, die für die Installation branchenspezifischer Apps verwendet wird, funktionieren nicht.

    Sie können auch **Geräte folgender Gruppe zuweisen**. Wählen Sie **Auswählen...** aus, um eine Gruppe auszuwählen.

    [!INCLUDE[groups deprecated](../includes/group-deprecation.md)]

    Aktivieren Sie als Nächstes **DEP-Einstellungen für diese Richtlinie konfigurieren**, um DEP zu unterstützen.

      ![Bereich „Setup-Assistent“](../media/pol-sa-corp-enroll.png)

     Die folgenden Einstellungen sind für DEP-verwaltete Geräte verfügbar:

     - **Abteilung**: Wird angezeigt, wenn Benutzer während der Aktivierung auf **Info zur Konfiguration** tippen
     - **Supportrufnummer**: Wird angezeigt, wenn der Benutzer während der Aktivierung auf die Schaltfläche **Hilfe erforderlich** klickt
     - **Vorbereitungsmodus**: Wird während der Aktivierung festgelegt und kann ohne Zurücksetzen des Geräts auf die Werkseinstellungen nicht geändert werden:
        - **Nicht überwacht**: Verwaltungsfunktionen sind eingeschränkt.
        - **Überwacht**: Ermöglicht weitere Verwaltungsfunktionen und deaktiviert standardmäßig die Aktivierungssperre.
     - **Registrierungsprofil für Gerät sperren**: Wird während der Aktivierung festgelegt und kann ohne Zurücksetzen des Geräts auf die Werkseinstellungen nicht geändert werden
        - **Deaktivieren**: Ermöglicht das Entfernen des Verwaltungsprofils aus dem Menü **Einstellungen**.
        - **Aktivieren**: (Erfordert **Vorbereitungsmodus** = **Überwacht**) Deaktiviert iOS-Einstellungen, die das Entfernen des Verwaltungsprofils zulassen könnten.
     - **Setup-Assistent-Optionen**: Diese optionalen Einstellungen können später im iOS-Menü **Einstellungen** eingerichtet werden.
        - **Kennung**: Aufforderung zur Eingabe der Kennung während der Aktivierung. Fordern Sie immer eine Kennung an, es sei denn, das Gerät und der Zugriff darauf werden auf andere Weise geschützt (d.h. im Kioskmodus zum Einschränken des Geräts auf eine App).
        - **Ortungsdienste**: Falls aktiviert, fordert der Setup-Assistent den Dienst während der Aktivierung an.
        - **Wiederherstellen**: Falls aktiviert, fordert der Setup-Assistent die iCloud-Sicherung während der Aktivierung an.
        - **Apple-ID**: Falls aktiviert, fordert iOS Benutzer zur Angabe einer Apple-ID an, wenn Intune versucht, eine App ohne eine ID zu installieren. Eine Apple ID ist erforderlich, um iOS App Store-Apps herunterzuladen, einschließlich Apps, die von Intune installiert wurden.
        - **Geschäftsbedingungen**: Falls aktiviert, fordert der Setup-Assistenten Benutzer auf, die Apple-Geschäftsbedingungen während der Aktivierung zu akzeptieren.
        - **Touch ID**: Falls aktiviert, fordert der Setup-Assistent diesen Dienst während der Aktivierung an.
        - **Apple Pay**: Falls aktiviert, fordert der Setup-Assistent diesen Dienst während der Aktivierung an.
        - **Zoom**: Falls aktiviert, fordert der Setup-Assistent diesen Dienst während der Aktivierung an.
        - **Siri**: Falls aktiviert, fordert der Setup-Assistent diesen Dienst während der Aktivierung an.
        - **Diagnosedaten an Apple senden**: Falls aktiviert, fordert der Setup-Assistent diesen Dienst während der Aktivierung an.
     -  **Zusätzliche Verwaltung durch Apple Configurator aktivieren**: Auf **Nicht zulassen** festlegen, um das Synchronisieren von Dateien mit iTunes oder die Verwaltung per Apple Configurator zu verhindern. Es empfiehlt sich, **Nicht zulassen** auszuwählen, weitere Konfigurationen aus Apple Configurator zu exportieren und diese anschließend als benutzerdefiniertes iOS-Konfigurationsprofil per Intune bereitzustellen, anstatt diese Einstellung zu wählen, um eine manuelle Bereitstellung mit oder ohne Zertifikat zuzulassen.
        - **Nicht zulassen**: Verhindert, dass das Gerät per USB kommuniziert (Verbindung wird deaktiviert).
        - **Zulassen**: Erlaubt einem Gerät das Kommunizieren über eine USB-Verbindung mit jedem PC oder Mac
        - **Zertifikat anfordern**: Ermöglicht eine Verbindung mit einem Mac, indem ein Zertifikat in das Registrierungsprofil importiert wird.

6.  **Zuweisen von DEP-Geräten zur Verwaltung** Wechseln Sie zum [Device Enrollment Program-Portal](https://deploy.apple.com) (https://deploy.apple.com), und melden Sie sich mit der Apple ID Ihres Unternehmens an. Wechseln Sie zu **Bereitstellungsprogramm** &gt; **Programm zur Geräteregistrierung** &gt; **Geräte verwalten**. Geben Sie an, wie Sie **Geräte wählen**, fügen Sie Geräteinformationen hinzu, und geben Sie die Details zum Gerät wie **Seriennummer**und **Bestellnummer**an, oder **laden Sie eine CSV-Datei hoch**. Wählen Sie als Nächstes **Zu Server zuweisen** aus. Wählen Sie den für Microsoft Intune angegebenen &lt;Servernamen&gt; und anschließend **OK** aus.

7.  **Synchronisieren von mit DEP verwalteten Geräten** Öffnen Sie als Administrator die [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com), wechseln Sie zu **Verwaltung** &gt; **Verwaltung mobiler Geräte** &gt; **iOS** &gt; **Programm zur Geräteregistrierung**, und wählen Sie anschließend **Jetzt synchronisieren** aus. Eine Synchronisierungsanforderung wird an Apple gesendet. Um mit DEP verwaltete Geräte nach der Synchronisierung anzuzeigen, navigieren Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) zu **Gruppen** &gt; **Alle Geräte** &gt; **Vorabregistrierte Unternehmensgeräte** &gt; **Nach iOS-Seriennummer**. Im Arbeitsbereich **Nach iOS-Seriennummer** wird der **Status** verwalteter Geräte als „Nicht kontaktiert“ angezeigt, bis das Gerät eingeschaltet und der Setup-Assistent darauf ausgeführt wird.

    Zur Einhaltung der Apple-Bedingungen für zulässigen DEP-Datenverkehr erzwingt Intune die folgenden Einschränkungen:
     -  Eine vollständige DEP-Synchronisation kann nicht öfter als einmal alle sieben Tage erfolgen. Während einer vollständigen Synchronisierung aktualisiert Intune jede Seriennummer, die Intune von Apple zugewiesen wurde, und zwar unabhängig davon, ob die Seriennummer vorher synchronisiert wurde oder nicht. Wenn eine vollständige Synchronisierung innerhalb von sieben Tagen nach der vorherigen vollständigen Synchronisierung versucht wird, aktualisiert Intune nur Seriennummern, die nicht bereits in Intune aufgeführt sind.
     -  Synchronisierungsanforderungen müssen binnen 10 Minuten abgeschlossen werden. Während dieser Zeit oder bis zum erfolgreichen Erfüllen der Anforderung wird die Schaltfläche **Synchronisieren** deaktiviert.

8.  **Verteilen von Geräten an Benutzer** Ihre unternehmenseigenen Geräte können jetzt an Benutzer verteilt werden. Wenn ein iOS-Gerät eingeschaltet wird, wird es für die Verwaltung durch Intune registriert.

## <a name="changes-to-intune-group-assignments"></a>Änderungen an den Intune-Gruppenzuweisungen

Ab Dezember 2016 werden Gerätegruppen in Azure Active Directory verschoben. Nach diesem Übergang zu Azure Active Directory-Gruppen wird die Gruppenzuweisung nicht länger in den Optionen des **Unternehmensregistrierungsprofils** angezeigt. Da diese Änderung über mehrere Monate hinweg umgesetzt wird, wird Ihnen die Änderung möglicherweise nicht sofort angezeigt. Nach dem Wechsel zum neuen Portal können die Zuweisungen dynamischer Gerätegruppen basierend auf dem Namen des Unternehmensregistrierungsprofils definiert werden. Mit diesem Vorgang wird sichergestellt, dass Geräte, die bereits einer Gerätegruppe zugewiesen wurden, automatisch mit bereitgestellter Richtlinie und bereitgestellten Apps in der Gruppe registriert werden. [Weitere Informationen zu Azure Active Directory-Gruppen](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/)

### <a name="see-also"></a>Weitere Informationen:
[Voraussetzungen für die Registrierung von Geräten](prerequisites-for-enrollment.md)



<!--HONumber=Jan17_HO1-->


