---
title: Apple-DEP-Verwaltung für iOS-Geräten mit Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid:
author: NathBarn
---
# Registrieren von firmeneigenen Geräten
Organisationen können Intune zum Verwalten der großen Anzahl von mobilen Geräten mit einem einzelnen Benutzerkonto namens ein [Konto des geräteregistrierungsmanagers](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). Nach dem Erstellen ein Konto des geräteregistrierungsmanagers, kann dieses Konto verwendet werden, zum Registrieren von mehr als fünf Standardgeräte normale Benutzer standardmäßig zulässig. Nach dem Erstellen ein Konto des geräteregistrierungsmanagers, werden Sie zum Registrieren von firmeneigene Geräte für Ihre Endbenutzer bereit.
Wählen Sie aus den folgenden corporate Device Enrollment-Optionen um mehr zu erfahren:

> [! Div-Klasse "Op_single_selector" =]
- [Apple Device Enrollment Programm (DEP) für iOS](iOS-device-enrollment-program.md)
- [Apple Configurator Setup-Assistenten für iOS](iOS-setup-assistant-enrollment.md)
- [Apple Configurator direkte Anmeldung für iOS](iOS-direct-enrollment.md)
- [Geben Sie COD-Geräte mit IMEI-Nummern](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)

## Apple-DEP-Verwaltung für iOS-Geräten mit Microsoft Intune
Zum Verwalten unternehmenseigener iOS-Geräte mit dem Apple-Programm zur Geräteregistrierung (Device Enrollment Program, DEP) müssen Unternehmen am Apple-DEP teilnehmen und Geräte über das Programm beziehen. Details zu diesem Prozess finden Sie unter:  [https://deploy.apple.com](https://deploy.apple.com). Das Programm bietet den Vorteil, dass Geräte eingerichtet werden können, ohne dass jedes Gerät physisch über USB mit einem Computer verbunden werden muss.

Bevor Sie firmeneigene iOS-Geräte mit DEP registrieren können, benötigen Sie einen DEP-Token von Apple. Mit diesem Token kann Intune Informationen zu DEP-Geräten synchronisieren, die Ihrem Unternehmen gehören. Damit kann Intune außerdem Registrierungsprofile an Apple übermitteln und diesen Profile Geräte zuweisen.

1.  **Starten der Verwaltung von iOS-Geräten mit Microsoft Intune**
    Bevor Sie iOS-Device Enrollment Program (DEP) Geräte registrieren können, müssen Sie die iOS-Verwaltung für Intune aktivieren abschließen.

2.  **Abrufen eines Verschlüsselungsschlüssels**
    Öffnen Sie als Administrator die [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com), wechseln Sie zu **Verwaltung** &gt; **Verwaltung mobiler Geräte** &gt; **iOS** &gt; **Device Enrollment Program**, und klicken Sie auf **Verschlüsselungsschlüssel herunterladen**. Speichern Sie die Verschlüsselungsschlüsseldatei (PEM) lokal. Die PEM-Datei wird verwendet, um ein Vertrauensstellungszertifikat vom Apple Device Enrollment Program-Portal anzufordern.

3.  **Abrufen eines Device Enrollment Program-Tokens**
    Klicken Sie auf die [Device Enrollment Program-Portal](https://deploy.apple.com) (https://deploy.apple.com), und melden Sie sich mit Apple ID Ihres Unternehmens Diese Apple-ID muss später verwendet werden, um das DEP-Token zu erneuern.

    1.  Wechseln Sie im [Device Enrollment Program-Portal](https://deploy.apple.com) zu **Device Enrollment Program** &gt; **Server verwalten**, und klicken Sie dann auf **MDM-Server hinzufügen**.

    2.  Geben Sie den **MDM-Servernamen** ein , und klicken Sie dann auf **Weiter**. Der Servername dient als Referenz zum Identifizieren des MDM-Servers. Es ist nicht der Name oder die URL des Microsoft Intune-Servers.

    3.  Das Dialogfeld **&lt;Servername&gt; hinzufügen** wird geöffnet. Klicken Sie auf **Datei auswählen...** die PEM-Datei hochladen, und klicken Sie auf **Weiter**.

    4.  Im Dialogfeld **&lt;Servername&gt; hinzufügen** wird der Link **Ihr Servertoken** angezeigt. Laden Sie die Servertokendatei (.p7m) auf Ihren Computer herunter, und klicken Sie dann auf **Fertig**.

    Diese Zertifikatdatei (.p7m) wird verwendet, um eine Vertrauensstellung zwischen dem Intune- und Apple Device Enrollment Program-Server herzustellen.

4.  **Intune DEP-Token hinzufügen**
    Wechseln Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com), wechseln Sie zu **Verwaltung** &gt; **Verwaltung mobiler Geräte** &gt; **iOS** &gt; **Device Enrollment Program**, und klicken Sie auf **DEP-Token hochladen**. **Wechseln Sie** zur Zertifikatdatei (.p7m), geben Sie Ihre **Apple-ID**ein, und klicken Sie auf **Hochladen**.

5.  **Hinzufügen der Corporate Device Enrollment-Richtlinie**
    Wechseln Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com), wechseln Sie zu **Richtlinie** &gt; **Corporate Device Enrollment** ein , und klicken Sie dann auf **Hinzufügen**. Geben Sie **allgemeine** Details ein, wie z. B. **Name** und **Beschreibung**. Geben Sie an, ob die dem Profil zugeordneten Geräte zu einem Benutzer oder einer Gruppe gehören, und aktivieren Sie dann **Device Enrollment Program-Einstellungen für diese Richtlinie konfigurieren** , um DEP zu unterstützen. Die **Setup-Assistent-Bereiche** definieren die iOS-Geräteeinstellungen, die während des Setups konfiguriert werden.

6.  **Zuweisen von DEP-Geräten für die Verwaltung**
    Klicken Sie auf die [Device Enrollment Program-Portal](https://deploy.apple.com) (https://deploy.apple.com), und melden Sie sich mit Apple ID Ihres Unternehmens Wechseln Sie **Bereitstellungsprogramm** &gt; **Device Enrollment Program** &gt; **Geräte verwalten**. Geben Sie an, wie Sie **Geräte wählen**, fügen Sie Geräteinformationen hinzu, und geben Sie die Details zum Gerät wie **Seriennummer**und **Bestellnummer**an, oder **laden Sie eine CSV-Datei hoch**. Wählen Sie als Nächstes **Zu Server zuweisen** . Wählen Sie den für Microsoft Intune angegebenen &lt;Servernamen&gt; aus, und klicken Sie dann auf **OK**.

7.  **Synchronisieren von DEP verwalteter Geräte**
    Öffnen Sie als Administrator die [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com), wechseln Sie zu **Verwaltung** &gt; **Verwaltung mobiler Geräte** &gt; **iOS** &gt; **Device Enrollment Program**, und klicken Sie auf **Jetzt synchronisieren**. Eine Synchronisierungsanforderung wird an Apple gesendet. Anzeigen von DEP verwalteter Geräte nach der Synchronisierung in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) go **Gruppen** & Gt; **Alle firmeneigenen Geräte**. In der **firmeneigene Geräte** Arbeitsbereich der **Zustand** verwalteter Geräte als "Nicht kontaktiert", bis das Gerät eingeschaltet ist und ausgeführt wird der Setup-Assistent das Gerät zu registrieren.

8.  **Verteilen von Geräten an Benutzer**
    Ihre firmeneigenen Geräte können jetzt an Benutzer verteilt werden. Wenn ein iOS-Gerät eingeschaltet wird, wird es für die Verwaltung durch Intune registriert.



### Weitere Informationen:
[Vorbereitungen zum Registrieren von Geräten](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=Mar16_HO5-->


