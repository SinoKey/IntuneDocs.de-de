---
# required metadata

title: Anmerkungen zu Microsoft Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: db9479b2-582d-4a1a-9fbc-fbfc6c680e6f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Anmerkungen zu Microsoft Intune
Microsoft Intune ist eine integrierte, cloudbasierte Clientverwaltungslösung, die Tools, Berichte und Upgradelizenzen für die aktuelle Windows-Version bietet und Ihre Computer schützt und auf dem neuesten Stand hält. Mithilfe von Intune können Sie mobile Geräte im Netzwerk über Exchange ActiveSync oder direkt über Intune verwalten. Die folgenden Anmerkungen enthalten wichtige Informationen zu Microsoft Intune sowie bekannte Probleme.


## Android-Benutzer können keine E-Mail senden, wenn der bedingte Zugriff für Exchange Online implementiert ist

Benutzer, die Samsung Android 5.1.1 und höher auf ihren Geräten ausführen, können keine E-Mails senden, wenn der bedingte Zugriff für Exchange Online konfiguriert ist. Samsung bestätigt, dass das Problem im integrierten Mailclient in Android 5.1.1 und höher auftritt, und arbeitet an einer Lösung.

**Problemumgehung 1**: Empfehlen Sie Endbenutzern, die Outlook-App für Android zu verwenden.

**Problemumgehung 2**: Führen Sie folgende Schritte aus, um betroffenen Benutzern das Senden von E-Mails zu ermöglichen:

1. Fügen Sie den betroffenen Benutzer im Abschnitt der ausgenommenen Gruppen der Richtlinie für den bedingten Zugriff für Exchange in eine Sicherheitsgruppe ein.
2. Gestatten Sie dem Benutzer die vorübergehende Synchronisierung im integrierten Mailclient.
3. Entfernen Sie den betroffenen Benutzer aus der ausgenommenen Gruppe, und lassen Sie sich bestätigen, dass der Benutzer jetzt E-Mails senden kann.

Microsoft arbeitet eng mit Samsung zusammen, um das Problem zu beheben oder weitere Problemumgehungen zu finden.



## Beim Ändern von Profilen für den Ressourcenzugriff zwischen Gruppen für iOS und Android tritt möglicherweise ein Fehler auf
**Problem:** Wenn Sie E-Mail- oder SCEO-Profile (Simple Certificate Enrollment Protocol) für den Ressourcenzugriff zwischen Gruppen ändern, können die Profile einen Konflikt auslösen und zu einem Fehler führen. Angenommen, Sie verfügen über ein auf Gruppe A gerichtetes E-Mail-Profil, das auf einen lokalen Exchange-Server verweist, und erstellen dann ein neues E-Mail-Profil, das Gruppe B gerichtet ist und auf Exchange Online verweist. Wenn Sie Benutzer aus Gruppe A in Gruppe B verschieben, behalten die Geräte das lokale Exchange-E-Mail-Profil bei und versuchen, das auf Gruppe B gerichtete Exchange Online-E-Mail-Profil zu installieren.

An dieser Stelle tritt nun eine der folgenden Situationen ein: 
* Wenn die E-Mail-Profile A und B identisch sind, wird E-Mail-Profil B vom Gerät abgelehnt, da E-Mail-Profil B bereits E-Mail-Profil A enthält.
* Wenn E-Mail-Profil A sich von E-Mail-Profil B unterscheidet, wie im obigen Beispiel erwähnt, erhält das Gerät zwei E-Mail-Profile.

**Hinweis:** Der Hostname und das für den Benutzernamen verwendete Attribut werden überprüft, um die E-Mail-Profile voneinander zu unterscheiden.

In beiden Fällen wurde das Profile für den Ressourcenzugriff (E-Mail-Profil) nicht vom Gerät entfernt, um zu verhindern, dass ein Benutzer unbeabsichtigt den Zugriff mehr auf E-Mails oder das SCEP-Zertifikat des Clients verliert.

**Problemumgehung:** Keine

## Wenn Sie ein Windows 8.1-Gerät registrieren, das bei einem Proxyserver authentifiziert werden muss, tritt bei der Registrierung ohne Angabe eines Grunds ein Fehler auf
**Problem:** Wenn Sie ein Windows 8.1-Gerät registrieren und das Gerät während der Registrierung bei einem Proxyserver authentifiziert werden muss, ist die Registrierung nicht möglich, wenn die Anmeldeinformationen für den Proxyserver nicht vom Gerät zwischengespeichert wurden. Wenn die Anmeldeinformationen für den Proxyserver nicht auf dem Gerät zwischengespeichert wurden, muss der Registrierungsvorgang warten, bis der Benutzer die Anmeldeinformationen eingibt. Während der Registrierung wird jedoch keine Aufforderung zur Eingabe der Anmeldeinformationen für den Proxyserver angezeigt. Das Resultat ist, dass der Registrierungsprozess nicht beim Proxyserver authentifiziert werden kann und dass keine Ursache für diesen Fehler angezeigt wird.

**Problemumgehung:** Konfigurieren und speichern Sie die Anmeldeinformationen für den Proxyserver vor der Registrierung auf allen Windows 8.1-Geräten, die bei einem Netzwerk registriert werden müssen, für das ein authentifizierter Proxyserver erforderlich ist. So konfigurieren und speichern Sie die Anmeldeinformationen auf einem Windows 8.1-Gerät

1.  Öffnen Sie **Internet Explorer** auf dem Windows 8.1-Gerät..

2.  Wenn Sie zur Eingabe der Anmeldeinformationen für den Proxyserver aufgefordert werden, geben Sie die entsprechenden Details ein, und wählen Sie die Option **Anmeldedaten speichern**aus..

3.  Registrieren Sie das Gerät.

## Die Registrierung von Windows Phone 8.1-Geräten in Microsoft Intune schlägt fehl, wenn die Geräteauthentifizierung in AD FS aktiviert ist
**Problem:** Wenn Sie ein Windows Phone 8.1-Gerät registrieren, tritt bei der Registrierung ein Fehler auf, wenn die optionale Einstellung für die Geräteauthentifizierung als Teil der globalen Authentifizierungsrichtlinie in den Active Directory-Verbunddiensten (AD FS) aktiviert ist.

**Problemumgehung:** Deaktivieren Sie die Geräteauthentifizierung auf dem AD FS-Server, indem Sie **Geräteauthentifizierung aktivieren** unter **Globale Authentifizierungsrichtlinie bearbeiten**deaktivieren. Weitere Informationen finden Sie unter [Konfigurieren von Authentifizierungsrichtlinien](http://technet.microsoft.com/library/dn486781.aspx).


## Das Microsoft Intune App Wrapping Tool für Android besitzt keine eigene Deinstallationsfunktion.
**Problem:** Das **Microsoft Intune App Wrapping Tool für Android** besitzt keine eigene Funktion zum Deinstallieren des Tools.

**Problemumgehung:** Navigieren Sie zum Speicherort, in dem Sie das Tool installiert haben, und löschen Sie das Verzeichnis. Der Standardspeicherort für die Installation ist: **C:\Programme (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**. Weitere Informationen zum App Wrapping Tool finden Sie unter [Vorbereiten von Android-Apps für die Verwaltung mit dem App Wrapping Tool](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)..

## Bei Computern mit Windows 8 oder Windows 8.1 ist keine Remoteunterstützung verfügbar
**Problem:** In dieser Version ist die Remoteunterstützungsfunktion auf Computern mit Windows 8 oder Windows 8.1 nicht verfügbar.

**Problemumgehung:** Keine

## Warnbenachrichtigungen sind bei automatisch hinzugefügten Empfängern nicht funktionsfähig
**Problem:** Wenn ein Empfänger einer Warnbenachrichtigung automatisch hinzugefügt wird, erhält er möglicherweise nicht immer eine Benachrichtigung.

**Problemumgehung:** Fügen Sie Empfänger Warnbenachrichtigung manuell hinzu, um sicherzustellen, dass sie eine Warnungsbenachrichtigung erhalten.

## Sprachunterstützung im Azure-Vorschauportal
Das Azure-Vorschauportal basiert auf einer neuen Plattform und unterstützt die folgenden Sprachen: Chinesisch (Vereinfacht), Chinesisch (Traditionell), Deutsch, Englisch, Französisch, Italienisch, Japanisch, Koreanisch, Niederländisch, Polnisch, Portugiesisch (Brasilien), Portugiesisch (Portugal), Russisch, Schwedisch, Spanisch, Türkisch, Tschechisch und Ungarisch.

Die Intune-Verwaltungskonsole und die mobilen Oberflächen für Endbenutzer unterstützen zusätzlich zu allen vom Azure-Vorschauportal unterstützten Sprachen außerdem Dänisch, Finnisch, Griechisch, Norwegisch und Rumänisch.


<!--HONumber=May16_HO1-->


