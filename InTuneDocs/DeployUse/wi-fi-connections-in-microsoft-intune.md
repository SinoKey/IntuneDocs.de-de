---
title: WLAN-Verbindungen | Microsoft Intune
description: Verwenden Sie WLAN-Profile, um Benutzern zu helfen, eine Verbindung mit Ihren WLAN-Netzwerken herzustellen.
keywords: 
author: Nbigman
manager: angrobe
ms.date: 09/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0b1b86ed-2e80-474d-8437-17dd4bc07b55
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 310a1160d105a80623742ce4e2dc046c670bc167
ms.openlocfilehash: d597cd13bd2254a9303769e2f5d5519c739f0aaf


---

# Konfigurieren von Geräten zur Herstellung einer Verbindung mit Ihren WLAN-Unternehmensnetzwerken

Verwenden Sie WLAN-Profile in Microsoft Intune, um Benutzern und Geräten in Ihrer Organisation Einstellungen für Drahtlosnetzwerke bereitzustellen. Wenn Sie ein WLAN-Profil bereitstellen, erhalten Ihre Benutzer Zugriff auf Ihr Unternehmens-WLAN, ohne es selbst konfigurieren zu müssen.

Beispiel: Sie installieren ein neues WLAN-Netzwerk mit dem Namen **Contoso Wi-Fi** und möchten alle iOS-Geräte so einrichten, dass sie eine Verbindung mit diesem Netzwerk herstellen können. Gehen Sie dazu folgendermaßen vor:

![Zusammenfassung des WLAN-Profilprozesses](..\media\wi-fi-process-diagram.png) 

1.   Erstellen Sie ein WLAN-Profil mit den Einstellungen, die zum Verbinden mit dem Drahtlosnetzwerk **Contoso Wi-Fi** erforderlich sind.

2. Stellen Sie das Profil der Gruppe von Benutzern mit iOS-Geräten bereit.

3.   Auf den Endgeräten der Benutzer erscheint das Netzwerk **Contoso Wi-Fi** in der Liste der Drahtlosnetzwerke, und es kann bequem eine Verbindung zu diesem Netzwerk hergestellt werden.


## Erstellen eines WLAN-Profils

Sie können WLAN-Profile auf den folgenden Plattformen bereitstellen:

-   Android 4,0 und höher

-   iOS 7.1 und höher

-   Mac OS X 10.9 und höher

Sie können für Windows 8.1, Windows 10 Desktop oder Windows 10 Mobile ein WLAN-Konfigurationsprofil importieren, das zuvor in eine Datei exportiert wurde. Details finden Sie unter [Exportieren oder Importieren eines WLAN-Profils (nur Windows 8.1 oder höher)](#export-or-import-a-wi-fi-configuration-profile-for-windows-devices).

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) auf **Richtlinie** &gt; **Richtlinie hinzufügen**.

2.  Wählen Sie einen der folgenden Richtlinientypen aus, und klicken Sie dann auf **Richtlinie erstellen**:

    -   WLAN-Profil (Android 4 und höher)

    -   WLAN-Profil (iOS 7.1 und höher)

    -   WLAN-Profil (Mac OS X 10.9 und höher)

    Es gibt keine empfohlenen Einstellungen für diesen Richtlinientyp. Sie müssen eine benutzerdefinierte Richtlinie erstellen.

3.  Geben Sie den Namen und die Beschreibung für das Profil an.

4. Geben Sie die Werte der **Netzwerkverbindungen** an.
 - **SSID (Service Set Identifier)**: Benutzer sehen den Netzwerknamen, nicht die SSID.
 - **Verbinden, wenn das Netzwerk nicht seinen Namen überträgt (SSID)**: Wählen Sie diese Option aus, damit Geräte mit dem Netzwerk verbunden werden können, wenn es nicht in der Liste der Netzwerke angezeigt wird (weil es ausgeblendet ist und seinen Namen nicht sendet).
 
5. Konfigurieren Sie die **Sicherheitseinstellungen** für die ausgewählte Plattform. Die verfügbaren Einstellungen hängen von den Sicherheitstypen ab, die Sie auswählen und die in [Sicherheitseinstellungen](#security-settings) beschrieben sind.

6. (Nur iOS und Mac OS X) Konfigurieren von **Proxyeinstellungen**

    |Name der Einstellung|Weitere Informationen|Zu verwenden in folgenden Fällen:|
    |----------------|-------------------|-------------|
    |**Proxyeinstellungen für diese WLAN-Verbindung**|Wählen Sie die Art der Proxyeinstellungen aus:<br /><br />-   **Keine** (Standard)<br />-   **Manuell**: Sie möchten die URL und die Portnummer des Proxyservers manuell angeben.<br />-   **Automatisch**: Sie möchten eine Konfigurationsdatei verwenden, um den Proxyserver zu konfigurieren.|Immer|
    |**Proxyserveradresse** und **Portnummer**|Geben Sie die URL und die Portnummer des Proxyservers an.|Für **Proxyeinstellungen für diese WLAN-Verbindung** wurde **Manuell** ausgewählt.|
    |**Proxyserver-URL**|Geben Sie die URL der Datei an, die die Proxyservereinstellungen enthält.|Für **Proxyeinstellungen für diese WLAN-Verbindung** wurde **Automatisch** ausgewählt.|

7.  Speichern des WLAN-Profils

Die neue Richtlinie wird im Knoten **Konfigurationsrichtlinien** des Arbeitsbereichs **Richtlinie** angezeigt. Informationen zur Bereitstellung des Profils finden Sie unter **Nächste Schritte**.

## Exportieren oder Importieren eines WLAN-Profils (nur Windows 8.1 oder höher)
 
Sie können für Windows 8.1, Windows 10 Desktop oder Windows 10 Mobile ein WLAN-Konfigurationsprofil importieren, das zuvor in eine Datei exportiert wurde. 

### Exportieren eines WLAN-Profils
In Windows können Sie WLAN-Profile mit dem Dienstprogramm **netsh wlan** in eine XML-Datei exportieren, die von Intune gelesen werden kann. Führen Sie auf einem Windows-Computer, auf dem das erforderliche WLAN-Profil bereits installiert ist, das folgende Verfahren aus.

1.  Erstellen Sie einen lokalen Ordner für die exportierten WLAN-Profile, z. B. „c\WiFi“.

2.  Öffnen Sie eine Eingabeaufforderung als Administrator.

3.  Führen Sie den Befehl `netsh wlan show profiles` aus, und notieren Sie den Namen des Profils, das Sie exportieren möchten.  In diesem Beispiel lautet der Profilname *WiFiName*.

4.  Führen Sie diesen Befehl aus: `netsh wlan export profile name="ProfileName" folder=c:\Wifi`. Dadurch wird ein WLAN-Profil namens „Wi-Fi-WiFiName.xml“ im Zielordner erstellt.

### Importieren eines WLAN-Profils
Verwenden Sie zum Importieren von WLAN-Einstellungen für die Bereitstellung an die benötigten Benutzer- und Gerätegruppen **WLAN-Importrichtlinie für Windows**.


1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) auf **Richtlinie** &gt; **Richtlinie hinzufügen**.

2.  Konfigurieren Sie eine Richtlinie vom Typ **Windows** &gt; **WLAN-Import (Windows 8.1 und später)**.

    Diese Richtlinie kann auf Windows 8.1, Windows 10 Desktop und Windows 10 Mobile angewendet werden.

    Sie können nur eine *benutzerdefinierte* WLAN-Importrichtlinie für Windows erstellen und bereitstellen. Empfohlene Einstellungen sind nicht verfügbar.

3.  Geben Sie die folgenden allgemeinen Informationen für die WLAN-Importrichtlinie an:

    |Name der Einstellung|Weitere Informationen|
    |----------------|--------------------|
    |**Name**|Geben Sie einen eindeutigen Namen für das WLAN-Profil ein, um es in der Intune-Konsole identifizieren zu können.|
    |**Beschreibung**|Geben Sie eine Beschreibung des WLAN-Profils sowie weitere relevante Informationen ein, um es besser zuordnen zu können.|

4.  Geben Sie unter der Überschrift **Benutzerdefiniertes WLAN-Profil** die folgenden Werte ein:

    |Name der Einstellung|Weitere Informationen|
    |----------------|--------------------|
    |**Profil-Konfigurationsdatei**|Klicken Sie auf **Importieren**, und wählen Sie die XML-Datei mit den WLAN-Profileinstellungen aus, die Sie in Intune importieren möchten.|
    |**Name des benutzerdefinierten Konfigurationsprofils (zur Anzeige beim Benutzer)**|Zeigt den Namen des WLAN-Profils an, wie er auf dem Gerät des Benutzers angezeigt wird.|
    |**Details zum Konfigurationsprofil**|Zeigt den XML-Code des ausgewählte Konfigurationsprofils an.|

5.  Klicken Sie danach auf **Richtlinie speichern**.

6.  Die neue Richtlinie wird im Knoten **Konfigurationsrichtlinien** des Arbeitsbereichs **Richtlinie** angezeigt.

## Bereitstellen des Profils

Ein Profil ist eine Art Richtlinie, verwenden Sie also den Arbeitsbereich „Richtlinien“, um sie bereitzustellen.

1.  Wählen Sie im Arbeitsbereich **Richtlinie** die Richtlinie aus, die Sie bereitstellen möchten, und klicken Sie dann auf **Bereitstellung verwalten**.

2.  Führen Sie im Dialogfeld **Bereitstellung verwalten** folgende Schritte aus:

    -   **Zum Bereitstellen der Richtlinie**: Wählen Sie mindestens eine Gruppe aus, für die Sie die Richtlinie bereitstellen möchten, und klicken Sie auf **Hinzufügen** &gt; **OK**.

    -   **Wenn Sie das Dialogfeld schließen möchten, ohne die Richtlinie bereitzustellen:** Klicken Sie auf **Abbrechen**.


Eine Statuszusammenfassung und Warnungen auf der Seite **Übersicht** des Arbeitsbereichs **Richtlinie** identifiziert Probleme mit der Richtlinie, die Ihre Aufmerksamkeit erfordern. Darüber hinaus wird eine Statusübersicht im Arbeitsbereich „Dashboard“ angezeigt.

## Sicherheitseinstellungen
Diese Tabellen enthalten die Details für die Sicherheitseinstellungen, die für Android-, iOS- und Mac OS X-WLAN-Profile verfügbar sind. 

### Sicherheitseinstellungen für Android-Geräte

  |Name der Einstellung|Weitere Informationen|Zu verwenden in folgenden Fällen:|
|----------------|--------------------|-------------|
|**Sicherheitstyp**|Wählen Sie das Sicherheitsprotokoll für das Drahtlosnetzwerk:<br /><br />-   **WPA-Enterprise/WPA2-Enterprise**<br />-   **Keine Authentifizierung (Offen)**, wenn das Netzwerk nicht gesichert ist.|Immer|
|**EAP-Typ**|Wählen Sie die den EAP-Typ (Extensible Authentication-Protokoll) zur Authentifizierung von gesicherten Drahtlosverbindungen:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TTLS**|Wenn Sie den Sicherheitstyp **WPA-Enterprise/WPA2-Enterprise** ausgewählt haben.|
|**Stammzertifikate für die Serverüberprüfung auswählen**|Klicken Sie auf **Auswählen**, und wählen Sie dann das vertrauenswürdige Stammzertifikatprofil zur Authentifizierung der Verbindung. **Wichtig:** Informationen zum Erstellen des vertrauenswürdigen Stammzertifikatprofils finden Sie unter [Sicherer Zugriff auf Ressourcen mit Zertifikatprofilen](secure-resource-access-with-certificate-profiles.md).|Wenn ein beliebiger **EAP-Typ** ausgewählt wurde.|
|**Authentifizierungsmethode**|Wählen Sie die Authentifizierungsmethode für die Verbindung aus:<br /><br />-   **Zertifikate** zur Angabe des Clientzertifikats<br />-   **Benutzername und Kennwort** zur Angabe einer anderen Authentifizierungsmethode|Bei **PEAP** oder **EAP-TTLS** als **EAP-Typ**.|
|**EAP-fremde Authentifizierungsmethode auswählen (Innere Identität)**|Wählen Sie, wie Sie die Verbindung authentifizieren möchten:<br /><br />-   **Keine**<br />-   **Unverschlüsseltes Kennwort (PAP)**<br />-   **Challenge Handshake Authentication-Protokoll (CHAP)**<br />-   **Microsoft CHAP (MS-CHAP)**<br />-   **Microsoft CHAP, Version 2 (MS-CHAP v2)**<br /><br />Die verfügbaren Optionen hängen vom ausgewählten EAP-Typ ab.|Die **Authentifizierungsmethode** ist **Benutzername und Kennwort**.|
|**Identitätsschutz aktivieren (Äußere Identität)**|Geben Sie den Text ein, der als Antwort auf eine EAP-Identity-Request gesendet werden soll. Dies kann ein beliebiger Text sein. Während der Authentifizierung wird zuerst diese anonyme Identität gesendet und anschließend die echte Kennung über einen sicheren Tunnel.|Bei **PEAP** oder **EAP-TTLS** als **EAP-Typ**.|
|**Wählen Sie ein Clientzertifikat für die Clientauthentifizierung (Identitätszertifikat) aus**|Klicken Sie auf **Auswählen**, und wählen Sie dann das vertrauenswürdige SCEP-Zertifikatprofil zur Authentifizierung der Verbindung. **Wichtig:** Informationen zum Erstellen eines SCEP-Zertifikatprofils finden Sie unter [Sicherer Zugriff auf Ressourcen mit Zertifikatprofilen](secure-resource-access-with-certificate-profiles.md).|Der Sicherheitstyp ist **WPA-Enterprise/WPA2-Enterprise** und ein beliebiger **EAP-Typ** wurde ausgewählt.|

### Sicherheitseinstellungen für iOS und Mac OS X-Geräte

  |Name der Einstellung|Weitere Informationen|Zu verwenden in folgenden Fällen:|
|----------------|--------------------|-------------|
|**Sicherheitstyp**|Wählen Sie das Sicherheitsprotokoll für das Drahtlosnetzwerk:<br /><br />-   **WPA-Personal/WPA2-Personal**<br />-   **WPA-Enterprise/WPA2-Enterprise**<br />-   **WEP**<br />-   **Keine Authentifizierung (Offen)**, wenn das Netzwerk nicht gesichert ist.|Immer|
|**EAP-Typ**|Wählen Sie die den EAP-Typ (Extensible Authentication-Protokoll) zur Authentifizierung von gesicherten Drahtlosverbindungen:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TLS**<br />-   **EAP-AST**<br />-   **LEAP**<br />-   **EAP-SIM**|Sie haben den Sicherheitstyp **WPA-Enterprise/WPA2-Enterprise** ausgewählt.|
|**Namen der vertrauenswürdigen Serverzertifikate**|Wählen Sie das vertrauenswürdige Stammzertifikatprofil zur Authentifizierung der Verbindung. **Wichtig:** Informationen zum Erstellen des vertrauenswürdigen Stammzertifikatprofils finden Sie unter [Sicherer Zugriff auf Ressourcen mit Zertifikatprofilen](secure-resource-access-with-certificate-profiles.md).|Sie haben als EAP-Typ **EAP-TLS**, **PEAP**, **EAP-TTLS** oder **EAP-FAST** ausgewählt.|
|**Geschützte Zugriffsanmeldeinformationen (PAC) verwenden**|Wählen Sie die Verwendung von geschützten Zugriffsanmeldeinformationen zum Herstellen eines authentifizierten Tunnels zwischen dem Client und dem Authentifizierungsserver. Eine vorhandene PAC-Datei wird ggf. verwendet.|Der **EAP-Typ** ist **EAP-FAST**.|
|**PAC bereitstellen**|Stellt die PAC-Datei auf Ihren Geräten bereit.<br /><br />Bei Verwendung dieser Option können Sie auch **PAC anonym bereitstellen** auswählen, damit die PAC-Datei ohne Authentifizierung des Servers bereitgestellt wird.|**Geschützte Zugriffsanmeldeinformationen (PAC) verwenden** wurde ausgewählt.|
|**Authentifizierungsmethode**|Wählen Sie die Authentifizierungsmethode für die Verbindung aus:<br /><br /><ul><li>**Zertifikate** zur Angabe des Clientzertifikats</li><li>**Benutzername und Kennwort** für eine der folgenden EAP-fremden Methoden zur Authentifizierung (auch als innere Identität bekannt):<br /><br /><ul><li>**Keine**</li><li>**Unverschlüsseltes Kennwort (PAP)**</li><li>**Challenge Handshake Authentication-Protokoll (CHAP)**</li><li>**Microsoft CHAP (MS-CHAP)**</li><li>**Microsoft CHAP, Version 2 (MS-CHAP v2)**</li><li>**EAP-TLS**</li></ul></li></ul>|Bei **PEAP** oder **EAP-TTLS** als **EAP-Typ**.|
|**Wählen Sie ein Clientzertifikat für die Clientauthentifizierung (Identitätszertifikat) aus**|Wählen Sie das SCEP-Zertifikatprofil zur Authentifizierung der Verbindung. **Wichtig:** Informationen zum Erstellen eines SCEP-Zertifikatprofils finden Sie unter [Sicherer Zugriff auf Ressourcen mit Zertifikatprofilen](secure-resource-access-with-certificate-profiles.md).|Wenn der Sicherheitstyp **WPA-Enterprise/WPA2-Enterprise** ist und **EAP-TLS**, **PEAP** oder **EAP-TTLS** als **EAP-Typ** ausgewählt wurde.|
|**Identitätsschutz aktivieren (Äußere Identität)**|Geben Sie den Text ein, der als Antwort auf eine EAP-Identity-Request gesendet werden soll. Dies kann ein beliebiger Text sein.<br /><br />Während der Authentifizierung wird zuerst diese anonyme Identität gesendet und anschließend die echte Kennung über einen sicheren Tunnel.|Wenn **PEAP**, **EAP-TTLS** oder **EAP-FAST** als **EAP-Typ** ausgewählt wurde.|


### Weitere Informationen:
Unter [Erstellen eines WLAN-Profils über einen vorinstallierten Schlüssel](pre-shared-key-wi-fi-profile.md) erfahren Sie, wie Sie ein WLAN-Profil mit einem vorinstallierten Schlüssel erstellen.



<!--HONumber=Sep16_HO1-->


