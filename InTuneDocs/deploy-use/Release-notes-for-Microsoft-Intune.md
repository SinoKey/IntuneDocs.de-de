---
title: Anmerkungen zu Microsoft Intune | Microsoft-Dokumentation
description: Anmerkungen zu dieser Intune-Version
keywords: 
author: Staciebarker
ms.author: stabar
manager: angrobe
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: db9479b2-582d-4a1a-9fbc-fbfc6c680e6f
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: fd300a5dfe6d6976491988453ec69e99668889fb


---

# <a name="release-notes-for-microsoft-intune"></a>Anmerkungen zu Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune ist eine integrierte, cloudbasierte Clientverwaltungslösung, die Tools, Berichte und Upgradelizenzen für die aktuelle Windows-Version bietet. Intune hilft außerdem dabei, Ihre Computer auf dem neuesten Stand zu halten und zu sichern. Mithilfe von Intune können Sie mobile Geräte im Netzwerk über Exchange ActiveSync oder direkt über Intune verwalten. Die folgenden Anmerkungen enthalten wichtige Informationen zu Microsoft Intune sowie bekannte Probleme.


## <a name="android-users-cant-send-email-when-conditional-access-for-exchange-online-is-implemented"></a>Android-Benutzer können keine E-Mail senden, wenn der bedingte Zugriff für Exchange Online implementiert ist

**Problem:** Benutzer, die Samsung Android 5.1.1 und höher auf ihren Geräten ausführen, können keine E-Mails senden, wenn der bedingte Zugriff für Exchange Online eingerichtet wurde. Samsung bestätigt, dass das Problem im integrierten Mailclient in Android 5.1.1 und höher auftritt, und arbeitet an einer Lösung.

**Problemumgehung 1**: Empfehlen Sie Benutzern, die Outlook-App für Android zu verwenden.

**Problemumgehung 2**: Führen Sie folgende Schritte aus, um betroffenen Benutzern das Senden von E-Mails zu ermöglichen:

1. Fügen Sie jeden betroffenen Benutzer im Abschnitt der ausgenommenen Gruppen der Richtlinie für den bedingten Zugriff für Exchange in eine Sicherheitsgruppe ein.
2. Gestatten Sie dem Benutzer die vorübergehende Synchronisierung im integrierten Mailclient.
3. Entfernen Sie den betroffenen Benutzer aus der ausgenommenen Gruppe, und lassen Sie sich bestätigen, dass der Benutzer jetzt E-Mails senden kann.

Microsoft arbeitet eng mit Samsung zusammen, um das Problem zu beheben oder weitere Problemumgehungen zu finden.



## <a name="changing-resource-access-profiles-between-groups-for-ios-and-android-might-fail"></a>Beim Ändern von Profilen für den Ressourcenzugriff zwischen Gruppen für iOS und Android tritt möglicherweise ein Fehler auf
**Problem:** Wenn Sie E-Mail- oder SCEP-Profile (Simple Certificate Enrollment Protocol) für den Ressourcenzugriff zwischen Gruppen ändern, können die Profile einen Konflikt auslösen und zu einem Fehler führen. Angenommen, Sie verfügen über ein auf Gruppe A ausgerichtetes E-Mail-Profil, das auf einen lokalen Exchange-Server verweist. Anschließend erstellen Sie ein neues E-Mail-Profil, das auf Gruppe B ausgerichtet ist und auf Exchange Online verweist. Wenn Sie Benutzer aus Gruppe A in Gruppe B verschieben, behalten die Geräte das lokale Exchange-E-Mail-Profil bei und versuchen, das auf Gruppe B ausgerichtete Exchange Online-E-Mail-Profil zu installieren.

An dieser Stelle tritt nun eine der folgenden Situationen ein: 
* Wenn die E-Mail-Profile A und B identisch sind, wird E-Mail-Profil B vom Gerät abgelehnt, da E-Mail-Profil B bereits E-Mail-Profil A enthält.
* Wenn sich E-Mail-Profil A von E-Mail-Profil B unterscheidet, wie im Beispiel erwähnt, erhält das Gerät zwei E-Mail-Profile.

> [!NOTE]
> Der Hostname und das für den Benutzernamen verwendete Attribut werden überprüft, um die E-Mail-Profile voneinander zu unterscheiden.

In beiden Fällen wurde das Profil für den Ressourcenzugriff (E-Mail-Profil) nicht vom Gerät entfernt, um zu verhindern, dass ein Benutzer unbeabsichtigt den Zugriff auf E-Mails oder das SCEP-Zertifikat des Clients verliert.

**Problemumgehung:** Keine

## <a name="when-you-enroll-a-windows-81-device-that-must-authenticate-to-a-proxy-server-the-enrollment-process-fails-with-no-visible-cause"></a>Wenn Sie ein Windows 8.1-Gerät registrieren, das bei einem Proxyserver authentifiziert werden muss, tritt bei der Registrierung ohne sichtbaren Grund ein Fehler auf
**Problem:** Wenn Sie ein Windows 8.1-Gerät registrieren und das Gerät während der Registrierung bei einem Proxyserver authentifiziert werden muss, ist die Registrierung nicht möglich, wenn die Anmeldeinformationen für den Proxyserver nicht vom Gerät zwischengespeichert wurden. Wenn die Anmeldeinformationen für den Proxyserver nicht auf dem Gerät zwischengespeichert wurden, muss der Registrierungsvorgang warten, bis der Benutzer die Anmeldeinformationen eingibt. Während der Registrierung wird jedoch keine Aufforderung zur Eingabe der Anmeldeinformationen für den Proxyserver angezeigt. Das Ergebnis ist, dass der Registrierungsprozess sich nicht mit dem Proxyserver authentifizieren kann. Dieser Fehler wird dem Benutzer nicht sichtbar angezeigt.

**Problemumgehung:** Richten Sie die Anmeldeinformationen für den Proxyserver vor der Registrierung auf allen Windows 8.1-Geräten ein, die bei einem Netzwerk registriert werden müssen, für das ein authentifizierter Proxyserver erforderlich ist, und speichern Sie diese. So richten Sie die Anmeldeinformationen auf einem Windows 8.1-Gerät ein und speichern diese:

1.  Öffnen Sie Internet Explorer auf dem Windows 8.1-Gerät.
2.  Wenn Sie zur Eingabe der Anmeldeinformationen für den Proxyserver aufgefordert werden, geben Sie die entsprechenden Anmeldeinformationen ein, und wählen Sie die Option **Anmeldedaten speichern** aus.
3.  Registrieren Sie das Gerät.

## <a name="windows-phone-81-devices-fail-to-enroll-with-microsoft-intune-when-device-authentication-is-enabled-in-ad-fs"></a>Die Registrierung von Windows Phone 8.1-Geräten in Microsoft Intune schlägt fehl, wenn die Geräteauthentifizierung in AD FS aktiviert ist
**Problem:** Wenn Sie ein Windows Phone 8.1-Gerät registrieren, tritt bei der Registrierung ein Fehler auf, wenn die optionale Einstellung für die Geräteauthentifizierung als Teil der globalen Authentifizierungsrichtlinie in den Active Directory-Verbunddiensten (AD FS) aktiviert ist.

**Problemumgehung:** Deaktivieren Sie die Geräteauthentifizierung auf dem AD FS-Server, indem Sie **Geräteauthentifizierung aktivieren** unter **Globale Authentifizierungsrichtlinie bearbeiten**deaktivieren. Weitere Informationen finden Sie unter [Konfigurieren von Authentifizierungsrichtlinien](http://technet.microsoft.com/library/dn486781.aspx).


## <a name="microsoft-intune-app-wrapping-tool-for-android-has-no-built-in-uninstall-capability"></a>Das Microsoft Intune App Wrapping Tool für Android besitzt keine eigene Deinstallationsfunktion.
**Problem:** Das **Microsoft Intune App Wrapping Tool für Android** besitzt keine eigene Funktion zum Deinstallieren des Tools.

**Problemumgehung:** Navigieren Sie zum Speicherort, in dem Sie das Tool installiert haben, und löschen Sie das Verzeichnis. Der Standardspeicherort für die Installation ist: **C:\Programme (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**. Weitere Informationen zum App Wrapping Tool finden Sie unter [Vorbereiten von Android-Apps für die Verwaltung von mobilen Anwendungen mit dem Intune App Wrapping Tool](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool).

## <a name="remote-assistance-is-not-available-on-computers-that-run-windows-8-or-windows-81"></a>Bei Computern mit Windows 8 oder Windows 8.1 ist keine Remoteunterstützung verfügbar
**Problem:** In dieser Version ist die Remoteunterstützungsfunktion auf Computern mit Windows 8 oder Windows 8.1 nicht verfügbar.

**Problemumgehung:** Keine

## <a name="alert-notifications-for-recipients-that-are-automatically-added-might-not-work"></a>Warnungsbenachrichtigungen können bei automatisch hinzugefügten Empfängern nicht funktionsfähig sein
**Problem:** Wenn Empfänger einer Warnungsbenachrichtigung automatisch hinzugefügt werden, erhalten sie möglicherweise nicht immer eine Benachrichtigung.

**Problemumgehung:** Fügen Sie Empfänger zu „Warnungsbenachrichtigung“ manuell hinzu, um sicherzustellen, dass sie Warnungsbenachrichtigungen erhalten.

## <a name="language-support-in-the-azure-portal"></a>Sprachunterstützung im Azure-Portal
Das Azure-Portal unterstützt die folgenden Sprachen: Chinesisch (Vereinfacht), Chinesisch (Traditionell), Tschechisch, Niederländisch, Englisch, Deutsch, Ungarisch, Italienisch, Japanisch, Portugiesisch (Brasilien), Portugiesisch (Portugal), Russisch, Spanisch, Französisch, Koreanisch, Polnisch, Schwedisch und Türkisch.

Die Intune-Verwaltungskonsole und die mobilen Oberflächen für Benutzer unterstützen zusätzlich zu allen vom Azure-Portal unterstützten Sprachen außerdem Dänisch, Griechisch, Finnisch, Norwegisch und Rumänisch.



<!--HONumber=Dec16_HO2-->


