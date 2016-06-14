---
# required metadata

title: VPN-Verbindungen | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: abc57093-7351-408f-9f41-a30877f96f73

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# VPN-Verbindungen in Microsoft Intune
 Über virtuelle private Netzwerke (VPN) können Sie Benutzern sicheren Remotezugriff auf Ihr Unternehmensnetzwerk bieten. Remotebenutzer können genau so arbeiten wie bei einer physischen Verbindung des Geräts mit dem Netzwerk. Geräte verwenden ein VPN-Verbindungsprofil, um eine Verbindung mit dem VPN-Server zu initiieren. **VPN-Profile** in Microsoft Intune ermöglichen Ihnen die Bereitstellung von VPN-Einstellungen für Benutzer und Geräte in Ihrer Organisation. Durch Bereitstellen dieser Einstellungen erleichtern Sie dem Endbenutzer das Verbinden mit Ressourcen im Unternehmensnetzwerk.

Sie möchten z. B. allen iOS-Geräten, die Einstellungen zur Verfügung stellen, die zum Verbinden mit einer Dateifreigabe im Unternehmensnetzwerk erforderlich sind. Sie erstellen ein VPN-Profil mit den Einstellungen, die zum Herstellen einer Verbindung mit dem Unternehmensnetzwerk erforderlich sind, und stellen dieses Profil dann für alle Benutzer mit iOS-Geräten bereit. Die Benutzer sehen die VPN-Verbindung in der Liste der verfügbaren Netzwerke und können mit geringem Aufwand eine Verbindung herstellen.

Sie können die folgenden Gerätetypen mit VPN-Profilen konfigurieren:

* Geräte unter Android 4 und höher
* Geräte unter iOS 7.1 und höher
* Geräte unter Mac OS X 10.9 und höher
* Registrierte Geräte unter Windows 8.1 und höher
* Geräte unter Windows Phone 8.1 und höher
* Geräte unter Windows 10 Desktop und Mobile.

Die Konfigurationsoptionen für VPN-Profile variieren je nach gewähltem Gerätetyp.

## VPN-Verbindungstypen

Intune unterstützt die Erstellung von VPN-Profilen mit den folgenden Verbindungstypen:




Verbindungstyp |iOS und Mac OS X  |Android|Windows 8.1|Windows RT|Windows RT 8.1|Windows Phone 8.1  |Windows 10 Desktop und Mobile |
----------------|------------------|-------|-----------|----------|--------------|-----------------|------------|
Cisco AnyConnect|Ja |Ja   |Nein    |     Nein    |Nein  |Nein    | Ja (OMA-URI, nur mobil)|     
Pulse Secure|Ja  |Ja |Ja   |Nein  |Ja  |Ja| Ja|        
F5 Edge Client|Ja |Ja |Ja |Nein  |Ja  |   Ja |  Ja|   
Dell SonicWALL Mobile Connect|Ja |Ja |Ja |Nein  |Ja |Ja |Ja|         
CheckPoint Mobile VPN|Ja |Ja |Ja |Ja |Ja|Ja|Ja|
Microsoft SSL (SSTP)|Nein |Nein |Nein |Nein |Nein|Nein|Nein|
Microsoft Automatic|Nein |Nein |Nein |Nein |Nein|Nein|Ja|
IKEv2|Nein |Nein |Nein |Nein |Nein|Nein|Ja|
PPTP|Nein |Nein |Nein |Nein |Nein|Nein|Ja|
L2TP|Nein |Nein |Nein |Nein |Nein|Nein|Ja|


> [!IMPORTANT] Vor der Verwendung von VPN-Profilen, die auf einem Gerät bereitgestellt werden, müssen Sie die entsprechende VPN-App für das Profil installieren. Sie können die Informationen im Thema [Bereitstellen von Apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md) verwenden, um Unterstützung beim Bereitstellen der entsprechenden Anwendung mit Intune zu erhalten.  

 Informationen zum Erstellen benutzerdefinierter VPN-Profile mithilfe von URI-Einstellungen finden Sie unter [Benutzerdefinierte Konfigurationen für VPN-Profile](custom-configurations-for-vpn-profiles.md).     

## Schutz von VPN-Profilen

VPN-Profile können eine Reihe verschiedener Verbindungstypen und Protokolle von unterschiedlichen Herstellern verwenden. Diese Verbindungen werden in der Regel mit einer von zwei Methoden gesichert:

### Zertifikate

Beim Erstellen des VPN-Profils wählen Sie ein SCEP- oder PFX-Zertifikatprofil aus, das Sie zuvor in Intune erstellt haben.

Dieses wird als Identitätszertifikat bezeichnet und dient zur Authentifizierung anhand eines von Ihnen erstellten vertrauenswürdigen Zertifikatprofils (oder eines Stammzertifikats), mit dem überprüft wird, ob das Gerät des Benutzers eine Verbindung herstellen darf. Das vertrauenswürdige Zertifikat wird auf dem Computer bereitgestellt, der die VPN-Verbindung authentifiziert, in der Regel ist dies der VPN-Server.

Weitere Informationen zum Erstellen und Verwenden von Zertifikatprofilen in Intune finden Sie unter [Sicherer Zugriff auf Ressourcen mit Zertifikatprofilen](secure-resource-access-with-certificate-profiles.md).

### Benutzername und Kennwort

Der Benutzer authentifiziert sich beim VPN-Server durch Angabe seines Benutzernamens und Kennworts.

## Erstellen eines VPN-Profils

1. Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) auf **Richtlinie > Richtlinie hinzufügen**.
2. Wählen Sie eine Vorlage für die neue Richtlinie aus, indem Sie den entsprechenden Gerätetyp erweitern, und wählen Sie dann das VPN-Profil für dieses Gerät aus:
    * **VPN-Profil (Android 4 und höher)**
    * **VPN-Profil (iOS 7.1 und höher)**
    * **VPN-Profil (Mac OS X 10.9 und höher)**
    * **VPN-Profil (Windows 8.1 und höher)**
    * **VPN-Profil (Windows Phone 8.1 und höher)**
    * **VPN-Profil (Windows 10 Desktop und Mobile und höher)**

    Sie können nur benutzerdefinierte VPN-Profilrichtlinien erstellen und bereitstellen. Empfohlene Einstellungen sind nicht verfügbar.

3. Orientieren Sie sich bei der Konfiguration der Einstellungen für das VPN-Profil an der folgenden Tabelle:

Name der Einstellung  |Weitere Informationen  
---------|---------
**Name**     |Geben Sie einen eindeutigen Namen für das VPN-Profil ein, damit Sie es leichter in der Intune-Konsole identifizieren können.         
**Beschreibung**     |Geben Sie eine Beschreibung mit einem Überblick über das VPN-Profil und anderen relevanten Informationen ein, die Ihnen bei der Suche danach helfen.         
**VPN-Verbindungsname (wird Benutzern angezeigt)**     |Geben Sie einen Namen für das VPN-Profil ein. Dies ist der Name, der Benutzern in der Liste der verfügbaren VPN-Verbindungen auf ihren Geräten angezeigt wird.         
**Verbindungstyp**     |  Wählen Sie einen der folgenden Verbindungstypen zur Verwendung im VPN-Profil aus: **Cisco AnyConnect** (nicht verfügbar für Windows 8.1 oder Windows Phone 8.1), **Pulse Secure**, **F5 Edge Client**, **Dell SonicWALL Mobile Connect**, **CheckPoint Mobile VPN**
**VPN-Serverbeschreibung**     | Geben Sie eine Beschreibung für den VPN-Server an, mit dem Geräte eine Verbindung herstellen. **Beispiel:** Contoso-VPN-Server Wenn der Verbindungstyp **F5 Edge Client** ist, geben Sie im Feld **Serverliste** eine Liste der Serverbeschreibungen und IP-Adressen an.
**IP-Adresse oder FQDN des Servers**    |Geben Sie die IP-Adresse oder den vollständig qualifizierten Domänennamen des VPN-Servers an, mit dem Geräte eine Verbindung herstellen. **Beispiele:** 192.168.1.1, vpn.contoso.com.  Wenn der Verbindungstyp **F5 Edge Client** ist, geben Sie im Feld **Serverliste** eine Liste der Serverbeschreibungen und IP-Adressen an.         |         
**Serverliste**     |Klicken Sie auf **Hinzufügen**, um einen neuen VPN-Server zur Verwendung für die VPN-Verbindung hinzuzufügen. Sie können auch angeben, welcher Server als Standardserver für die Verbindung dienen soll. Diese Option wird nur für den Verbindungstyp **F5 Edge Client** angezeigt.         
**Gesamten Netzwerkdatenverkehr über die VPN-Verbindung senden**     |Wenn Sie diese Option aktivieren, wird der gesamte Netzwerkdatenverkehr über die VPN-Verbindung gesendet. Wenn Sie diese Option nicht auswählen, verhandelt der Client dynamisch die Routen für getrenntes Tunneln beim Herstellen einer Verbindung mit dem VPN-Server eines Drittanbieters. Nur Verbindungen mit dem Unternehmensnetzwerk werden über einen VPN-Tunnel gesendet. Beim Verbinden mit Ressourcen im Internet wird VPN-Tunneln nicht verwendet.
**Authentifizierungsmethode**| Wählen Sie die von der VPN-Verbindung verwendete Authentifizierungsmethode aus: **Zertifikate** oder **Benutzername und Kennwort**. (Die Einstellung „Benutzername und Kennwort“ ist für den Verbindungstyp „Cisco AnyConnect“ nicht verfügbar.) Die Option **Authentifizierungsmethode** ist für Windows 8.1 nicht verfügbar.
**Benutzeranmeldeinformationen bei jeder Anmeldung speichern**|Aktivieren Sie diese Option, um sicherzustellen, dass die Benutzeranmeldeinformationen gespeichert werden, sodass der Benutzer die Anmeldeinformationen nicht bei jeder Verbindungsherstellung erneut eingeben muss.
**Wählen Sie ein Clientzertifikat für die Clientauthentifizierung (Identitätszertifikat) aus**|Wählen Sie das SCEP-Clientzertifikat aus, das Sie zuvor erstellt haben und das zur Authentifizierung der VPN-Verbindung verwendet wird. Weitere Informationen zum Verwenden von Zertifikatprofilen in Intune finden Sie unter [Sicherer Zugriff auf Ressourcen mit Zertifikatprofilen](secure-resource-access-with-certificate-profiles.md). Diese Option wird nur für die Authentifizierungsmethode **Zertifikate** angezeigt.
**Rolle**| Geben Sie den Namen der Benutzerrolle an, die Zugriff auf diese Verbindung hat. Eine Benutzerrolle definiert persönliche Einstellungen und Optionen und aktiviert oder deaktiviert bestimmte Zugriffsfeatures. Diese Option wird nur für den Verbindungstyp **Pulse Secure** angezeigt.
**Bereich**|Geben Sie den Namen des gewünschten Authentifizierungsbereichs an. Ein Authentifizierungsbereich ist eine Gruppe von Authentifizierungsressourcen, die vom Verbindungstyp „Pulse Secure“ verwendet werden. Diese Option wird nur für den Verbindungstyp **Pulse Secure** angezeigt.
**Anmeldegruppe oder Domäne**|Geben Sie den Namen der Anmeldegruppe oder Domäne an, mit der Sie eine Verbindung herstellen möchten. Diese Option wird nur für den Verbindungstyp **Dell SonicWALL Mobile Connect** angezeigt.
**Fingerabdruck**|Geben Sie eine Zeichenfolge wie z. B. „Contoso-Fingerabdruckcode“ an, anhand der überprüft wird, ob der VPN-Server vertrauenswürdig ist. Mit einem Fingerabdruck kann wie folgt verfahren werden: Er kann an den Client gesendet werden, damit dieser weiß, dass alle Server vertrauenswürdig sind, die beim Verbinden den betreffenden Fingerabdruck vorweisen. Wenn das Gerät noch nicht über den Fingerabdruck verfügt, wird der Benutzer aufgefordert, dem VPN-Server zu vertrauen, mit dem eine Verbindung hergestellt wird, während der Fingerabdruck angezeigt wird (der Benutzer überprüft den Fingerabdruck manuell und klickt auf **Vertrauen**, um die Verbindung herzustellen). Diese Option wird nur für den Verbindungstyp **CheckPoint Mobile VPN** angezeigt.
**VPN für App**|Mit dieser Option können Sie diese VPN-Verbindung einer iOS- oder Mac OS X-App zuzuordnen, sodass die Verbindung geöffnet wird, wenn die Anwendung ausgeführt wird. Die Zuordnung des VPN-Profils zu einer App kann bei der Bereitstellung der Software erfolgen. Weitere Informationen finden Sie unter [Bereitstellen von Apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md).
**Proxyeinstellungen automatisch erkennen** (nur iOS, Mac OS X, Windows 8.1 und Windows Phone 8.1)|Geben der VPN-Server einen Proxyserver für die Verbindung erfordert, geben Sie an, ob Geräte die Verbindungseinstellungen automatisch erkennen sollen. Weitere Informationen finden Sie in der Windows Server-Dokumentation.
**Automatisches Konfigurationsskript verwenden** (nur iOS, Mac OS X, Windows 8.1 und Windows Phone 8.1)|Wenn der VPN-Server einen Proxyserver für die Verbindung erfordert, geben Sie an, ob Sie die Einstellungen mit einem automatischen Konfigurationsskript definieren und dann eine URL zur Datei mit den Einstellungen angeben möchten. Weitere Informationen finden Sie in der Windows Server-Dokumentation.
**Proxyserver verwenden** (nur iOS, Mac OS X, Windows 8.1 und Windows Phone 8.1)|Wenn der VPN-Server einen Proxyserver für die Verbindung erfordert, aktivieren Sie diese Option, und geben Sie dann die Adresse und die Portnummer des Proxyservers an. Weitere Informationen finden Sie in der Windows Server-Dokumentation.
**Proxyeinstellungen für lokale Adressen umgehen** (nur iOS, Mac OS X, Windows 8.1 und Windows Phone 8.1)|Wenn der VPN-Server einen Proxyserver für die Verbindung erfordert, aktivieren Sie diese Option, wenn der Proxyserver für von Ihnen angegebene lokale Adressen nicht verwendet werden soll. Weitere Informationen finden Sie in der Windows Server-Dokumentation.
**Benutzerdefiniertes XML** (Windows 8.1 und höher sowie Windows Phone 8.1 und höher)|Ermöglicht Ihnen die Angabe benutzerdefinierter XML-Befehle zum Konfigurieren der VPN-Verbindung. Beispiele: Für **Pulse Secure**: &lt;pulse-schema&gt;&lt;isSingleSignOnCredential&gt;true&lt;/isSingleSignOnCredential&gt;&lt;/pulse-schema&gt;. Für **CheckPoint Mobile VPN**: &lt;CheckPointVPN port="443" name="CheckPointSelfhost" sso="true"  debug="3" /&gt;. Für **Dell SonicWALL Mobile Connect**: &lt;MobileConnect&gt;&lt;Compression&gt;false&lt;/Compression&gt;&lt;debugLogging&gt;True&lt;/debugLogging&gt;&lt;packetCapture&gt;False&lt;/packetCapture&gt;&lt;/MobileConnect&gt;. Für **F5 Edge Client**: &lt;f5-vpn-conf&gt;&lt;single-sign-on-credential /&gt;&lt;/f5-vpn-conf&gt;. Weitere Informationen über das Schreiben von benutzerdefinierten XML-Befehlen finden Sie in der VPN-Dokumentation der einzelnen Hersteller.
**DNS-Suffix-Suchliste** (nur Windows Phone 8.1)|Geben Sie in jeder Zeile ein DNS-Suffix an. Jedes angegebene DNS-Suffix wird beim Verbinden mit einer Website unter Verwendung eines Kurznamens gesucht. Geben Sie z. B. die DNS-Suffixe **domain1.contoso.com** und **domain2.contoso.com** ein, rufen Sie die URL **http://mywebsite** auf, und die URLs **http://mywebsite.domain1.contoso.com** und **http://mywebsite.domain2.contoso.com** werden durchsucht.
**Bei Verbindung mit dem Unternehmens-WLAN VPN umgehen** (nur Windows Phone 8.1)|Gibt an, dass die VPN-Verbindung nicht verwendet wird, wenn das Gerät mit dem Unternehmens-WLAN verbunden ist.
**VPN umgehen, wenn mit Heimat-WLAN-Netzwerk verbunden** (nur Windows Phone 8.1)|Gibt an, dass die VPN-Verbindung nicht verwendet wird, wenn das Gerät mit einem WLAN-Heimnetzwerk verbunden ist.

Die folgenden zusätzlichen Einstellungen sind für Windows 10 Desktop und mobile Geräte verfügbar.

Name der Einstellung  |Weitere Informationen  
---------|---------
**Regeln für den Netzwerkdatenverkehr**| Legen Sie die Protokolle, die lokalen und Remoteports sowie die Adressbereiche fest, die für die VPN-Verbindung aktiviert werden sollen. Wenn Sie keine Regel für den Netzwerkdatenverkehr erstellen, werden alle Protokolle, Ports und Adressbereiche aktiviert. Nachdem Sie eine Regel erstellt haben, werden nur die in dieser oder weiteren Regeln festgelegten Protokolle, Ports und Adressbereiche von der VPN-Verbindung verwendet.
**Routen**|Die Routen, welche die VPN-Verbindung verwenden.
**DNS-Server**| Die DNS-Server, die von der VPN-Verbindung verwendet werden, nachdem die Verbindung hergestellt wurde.         
**Zugeordnete Apps**     | Sie können eine Liste von Apps bereitstellen, die automatisch die VPN-Verbindung verwenden. Der Typ der App bestimmt den App-Bezeichner. Geben Sie für universelle Apps den Namen der Paketfamilie an und für Desktop-Apps den Dateipfad der App.          


> [!IMPORTANT] Es wird empfohlen, alle Listen mit Apps zu schützen, die Sie für die Verwendung in der Konfiguration eines App-bezogenen VPN zusammenstellen. Wenn ein nicht autorisierter Benutzer die Liste ändert und Sie sie in die Liste der Apps für App-bezogenes VPN importieren, autorisieren Sie möglicherweise den VPN-Zugriff auf Apps, auf die nicht zugegriffen werden soll. Eine Möglichkeit, App-Listen zu schützen, ist die Verwendung einer Zugriffssteuerungsliste (Access Control List, ACL).

Im Folgenden finden Sie ein Beispiel für die Verwendung von Einstellungen für Unternehmensgrenzen. Wenn Sie das VPN nur für Remotedesktops aktivieren möchten, erstellen Sie eine Regel für den Netzwerkdatenverkehr, die Datenverkehr für Protokollnummer 27 am externen Port 3996 zulässt. Kein anderer Datenverkehr verwendet das VPN.

Das Definieren von Routen innerhalb von Unternehmensgrenzen ist nützlich, wenn Sie für Ihren VPN-Verbindungstyp nicht definieren können, wie Datenverkehr bei getrenntem Tunneln behandelt wird. Verwenden Sie in diesem Fall **Routen**, um die Routen aufzulisten, die das VPN verwenden.

Sie können die VPN-Nutzung auf Windows 10-Geräten auf bestimmte Apps beschränken, indem Sie eine benutzerdefinierte OMA-URI-Einstellung definieren.

Die neue Richtlinie wird im Knoten **Konfigurationsrichtlinien** des Arbeitsbereichs **Richtlinie** angezeigt.

## Bereitstellen der Richtlinie

1.  Wählen Sie im Arbeitsbereich **Richtlinie** die Richtlinie aus, die Sie bereitstellen möchten, und wählen Sie dann **Bereitstellung verwalten** aus.

2.  Führen Sie im Dialogfeld **Bereitstellung verwalten** folgende Schritte aus:

    -   **So stellen Sie die Richtlinie bereit**: Wählen Sie mindestens eine Gruppe aus, für die Sie die Richtlinie bereitstellen möchten, und klicken Sie auf **Hinzufügen** &gt; **OK**.

    -   **So schließen Sie das Dialogfeld, ohne die Richtlinie bereitzustellen**: Klicken Sie auf **Abbrechen**.


Nach der erfolgreichen Bereitstellung sehen Benutzer den von Ihnen angegebenen VPN-Verbindungsnamen in der Liste der VPN-Verbindungen auf ihrem Gerät.

Eine Statuszusammenfassung und Warnungen auf der Seite **Übersicht** des Arbeitsbereichs **Richtlinie** identifiziert Probleme mit der Richtlinie, die Ihre Aufmerksamkeit erfordern. Darüber hinaus wird eine Statusübersicht im Arbeitsbereich „Dashboard“ angezeigt.

### Weitere Informationen:
[Benutzerdefinierte Konfigurationen für VPN-Profile](Custom-configurations-for-VPN-profiles.md)
[App-bezogenes VPN für Android Pulse Secure](per-app-vpn-for-android-pulse-secure.md)


<!--HONumber=May16_HO5-->


