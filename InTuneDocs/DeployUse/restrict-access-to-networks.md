---
title: "Beschränken des Netzwerkzugriffs mit Cisco ISE | Microsoft Intune"
description: "Verwenden Sie Cisco ISE mit Intune, damit Geräte bei Intune registriert sind und mit der Richtlinie kompatibel sind, bevor sie auf WLAN und VPN zugreifen, die von Cisco ISE gesteuert werden."
keywords: 
author: nbigman
manager: angrobe
ms.date: 06/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5631bac3-921d-438e-a320-d9061d88726c
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ede9c4db136eb0498cad6d196488d03768741328
ms.openlocfilehash: 382dd93a5aec7415e5fb738f3068820e36d8ae06


---

# Verwenden von Cisco ISE mit Microsoft Intune
Die Intune-Integration mit Cisco Identity Services Engine (ISE) erlaubt Ihnen, in Ihrer ISE-Umgebung Netzwerkrichtlinien mithilfe der Intune-Geräteregistrierung und des Kompatibilitätszustands zu verfassen. Sie können diese Richtlinien so einsetzen, dass der Zugriff auf Ihr Unternehmensnetzwerk auf Geräte beschränkt wird, die von Intune verwaltet werden und mit Intune-Richtlinien kompatibel sind.

## Konfigurationsschritte

Sie müssen keine Einrichtungsschritte in Ihrem Intune-Mandanten vornehmen, um diese Integration zu aktivieren. Sie müssen Berechtigungen für Ihren Cisco ISE-Server für den Zugriff auf den Intune-Mandanten bereitstellen. Nachdem dies erfolgt ist, wird der Rest des Setups auf Ihrem Cisco ISE-Server durchgeführt. In diesem Artikel erhalten Sie Anweisungen, wie Sie für Ihren ISE-Server die Berechtigungen bereitstellen, auf Ihren Intune-Mandanten zuzugreifen.

### Schritt 1: Verwalten der Zertifikate
1. Exportieren Sie das Zertifikat in der Azure Active Directory-Konsole (Azure AD).

    #### Internet Explorer 11


    a. Führen Sie Internet Explorer als Administrator aus, und melden Sie sich bei der Azure AD-Konsole an.

    b. Wählen Sie das Schlosssymbol in der Adressleiste und **Anzeigen von Zertifikaten** aus.

    c. Wählen Sie auf der Registerkarte **Details** der Zertifikateigenschaften **In Datei kopieren** aus.

    d. Wählen Sie auf der Startseite **Assistent für den Zertifikatexport** **Weiter** aus.

    e. Lassen Sie auf der Seite **Format der zu exportierenden Datei** den Standardwert **DER-codiert-binär x. 509 (. CER)**, und wählen Sie **Weiter** aus.  

    f. Wählen Sie auf der Seite **Zu exportierende Datei** **Durchsuchen** aus, um einen Speicherort zum Speichern der Datei auszuwählen, und geben Sie einen Dateinamen ein. Obwohl es so aussieht, als ob Sie eine Datei zum exportieren auswählen, benennen Sie tatsächlich die Datei, in der das exportierte Zertifikat gespeichert wird. Wählen Sie **Weiter** &gt; **Fertig stellen** aus.

    #### Safari

    a. Melden Sie sich bei der Azure AD-Konsole an.

    b. Wählen Sie das Schlosssymbol aus &gt;  **Weitere Informationen**.

    c. Wählen Sie **Zertifikat anzeigen** &gt; **Details** aus.

    d. Wählen Sie das Zertifikat und anschließend **Exportieren** aus.  

    > [!IMPORTANT]
    > Überprüfen Sie das Ablaufdatum des Zertifikats, da Sie ein neues Zertifikat exportieren und importieren müssen, wenn dieses abläuft.


2. Importieren Sie von der ISE-Konsole aus das Intune-Zertifikat (die Datei, die Sie exportiert haben) in den **Vertrauenswürde Zertifikate**-Speicher.
### Abrufen eines selbstsignierten Zertifikats von ISE 
1.  Wechseln Sie in der ISE-Konsole zu **Verwaltung** > **Zertifikate** > **Systemzertifikaten** > **Selbstsigniertes Zertifikat generieren**.  
2.       Exportieren Sie das selbstsignierte Zertifikat.
3. Bearbeiten Sie in einem Text-Editor das exportierte Zertifikat:
 - Löschen Sie ** -----BEGIN CERTIFICATE-----**
 - Löschen Sie ** -----END CERTIFICATE-----**
 
Stellen Sie sicher, dass sich der gesamte Text in einer Zeile befindet


### Schritt 2: Erstellen einer App für ISE in Ihrem Azure AD-Mandanten
1. Wählen Sie in der Konsole von Azure AD **Anwendungen** > **Hinzufügen einer Anwendung** > **Eine von meinem Unternehmen entwickelte Anwendung hinzufügen** aus.
2. Stellen Sie einen Namen und eine URL für die App bereit. Die URL könnte die Website Ihres Unternehmens sein.
3. Laden Sie das App-Manifest (eine JSON-Datei) herunter.
4. Bearbeiten Sie die JSON-Manifestdatei. Geben Sie in der Einstellung namens **keyCredentials** den bearbeiteten Zertifikattext aus Schritt 1 als Einstellungswert an.
5. Speichern Sie die Datei, ohne ihren Namen zu ändern.
6. Stellen Sie Ihrer App Berechtigungen für Microsoft Graph und die Microsoft Intune-API bereit.

 a. Wählen Sie für Microsoft Graph Folgendes aus:
    - **Anwendungsberechtigungen**: Lesen von Verzeichnisdaten
    - **Delegierte Berechtigungen**:
        - Jederzeit auf die Daten des Benutzers zugreifen
        - Benutzer anmelden

 b. Wählen Sie für die Microsoft Intune-API in **Anwendungsberechtigungen** **Abrufen des Gerätestatus und der Kompatibilität von Intune** aus.

7. Wählen Sie **Endpunkte anzeigen** aus, und kopieren Sie die folgenden Werte für die Verwendung bei der Konfiguration der ISE-Einstellungen:

|Wert im Azure AD-Portal|Entsprechendes Feld im ISE-Portal|
|-------------------|---------------------------------|
|Microsoft Azure AD Graph-API-Endpunkt|URL für AutoErmittlung|
|OAuth 2.0-Tokenendpunkt|Token ausgebende URL|
|Code mit Client-ID aktualisieren|Client-ID|


### Schritt 3: Konfigurieren der ISE-Einstellungen
Geben Sie in der Verwaltungskonsole von ISE diese Einstellungswerte ein:
  - **Servertyp**: Mobile Device Manager
  - **Authentifizierungstyp**: OAuth – Anmeldeinformationen des Clients
  - **AutoErmittlung**: Ja
  - **URL für AutoErmittlung**: *Geben Sie den Wert aus Schritt 1 ein.*
  - **Client-ID**: *Geben Sie den Wert aus Schritt 1 ein.*
  - **Token ausgebende URL**: *Geben Sie den Wert aus Schritt 1 ein.*



## Informationen die zwischen Ihrem Intune-Mandanten und Ihrem Cisco ISE-Server freigegeben sind.
Diese Tabelle listet die Informationen auf, die zwischen Ihrem Intune-Mandanten und Ihrem Cisco ISE-Server für die mit Intune verwalteten Geräte freigegeben sind.

|Eigenschaft|  Beschreibung|
|---------------|------------------------------------------------------------|
|complianceState|Die Zeichenfolge TRUE oder FALSE, die angibt, ob das Gerät kompatibel ist oder nicht.|
|isManaged|Die Zeichenfolge TRUE oder FALSE, die angibt, ob der Client durch Intune verwaltet wird oder nicht.|
|macAddress|Die MAC-Adresse des Geräts.|
|serialNumber|Die Seriennummer des Geräts. Gilt nur für iOS-Geräte.|
|imei|Die IMEI-Nummer (15 Dezimalzahlen: 14 Ziffern plus eine Prüfziffer) oder IMEISV-Nummer (16 Ziffern) enthält Informationen zum Ursprung, Modell und der Seriennummer des Geräts. Die Struktur dieser Nummer ist in 3GPP TS 23.003 angegeben. Gilt nur für Geräte mit SIM-Karten.|
|udid|Die eindeutige Geräte-ID (unique device identifier; UDID) ist eine Sequenz von 40 Buchstaben und Zahlen. Dies ist spezifisch für iOS-Geräte.|
|meid|Mobile Equipment Identifier, eine global eindeutige Identifikationsnummer eines physischen Arbeitsgeräts einer mobilen CDMA-Station. Das Zahlenformat wird durch den Bericht „S.R0048“ des Gremiums 3GPP2 definiert. Für die praktische Anwendung kann es auch als eine IMEI mit hexadezimalen Zahlen betrachtet werden. Ein MEID ist 56 Bits lang (14 hexadeximale Zahlen). Er besteht aus drei Feldern, inklusive einem 8-Bit-Regionscode (RR), einem 24-Bit-Herstellercode und einer vom Hersteller vergebenen 24-Bit Seriennummer.|
|osVersion|Die Betriebssystemversion für das Gerät.
|model|Das Gerätemodell.
|Hersteller|Der Hersteller des Geräts.
|azureDeviceId|Die Geräte-ID, nach der Arbeitsplatzeinbindung mit Azure AD. Ist für nicht verknüpfte Geräte eine leere GUID.|
|lastContactTimeUtc|Das Datum und die Uhrzeit, zu der das Gerät sich das letzte Mal beim Intune-Verwaltungsdienst gemeldet hat.


## Benutzerfreundlichkeit

Wenn ein Benutzer versucht, auf Ressourcen mittels eines Gerätes zuzugreifen, das nicht registriert ist, wird er zur Registrierung aufgefordert, so wie hier gezeigt.

![Beispiel für eine Registrierungsaufforderung](../media/cisco-ise-user-iphone.png)

Wenn der Benutzer sich für die Registrierung entscheidet, wird er zum Intune-Registrierungsprozess umgeleitet. Die benutzerfreundliche Registrierung für Intune wird in den folgenden Themen beschrieben:

- [Registrieren Ihres Android-Geräts bei Intune](/intune/enduser/enroll-your-device-in-Intune-android)</br>
- [Registrieren Ihres iOS-Geräts bei Intune](/intune/enduser/enroll-your-device-in-intune-ios)</br>
- [Registrieren Ihres Mac OS X-Geräts bei Intune](/intune/enduser/enroll-your-device-in-intune-mac-os-x)</br>
- [Registrieren Ihres Windows-Geräts bei Intune](/intune/enduser/enroll-your-device-in-intune-windows)</br>

Es gibt auch [herunterladbare Registrierungsanweisungen](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a), die Sie verwenden können, um einen angepassten Leitfaden für Ihre Benutzerfreundlichkeit zu erstellen.


### Weitere Informationen:

[Cisco Identity Services Engine-Administratorhandbuch, Version 2.1](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html#task_820C9C2A1A6647E995CA5AAB01E1CDEF)



<!--HONumber=Aug16_HO3-->


