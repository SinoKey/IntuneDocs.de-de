---
title: Verstehen Sie Ihre Geräte mithilfe des Inventars in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 312911fe-b963-4949-9911-ae425e0590b2
author: robstackmsft
---
# Verstehen Sie Ihre Geräte mithilfe des Inventars in Microsoft Intune
Microsoft Intune können Sie anzeigen, der Bestand an registrierte Geräte und Windows-PCs, die die Intune-Clientsoftware ausgeführt wird.

## Was wird von registrierten Geräten gesammelt?
Führen Sie zum Anzeigen der Inventur gesammelt, die von mobilen Geräten die [Inventurberichte für Mobile Geräte](understand-microsoft-intune-operations-by-using-reports.md). Intune erfasst die folgenden Inventur aus registrierte Geräte:

|Eigenschaft|Exchange ActiveSync|iOS|Mac OS X|Android|Windows RT und Windows 8.1|Windows Phone 8 und Windows Phone 8.1|Windows 10|Details|
|------------|-----------------------|-------|------------|-----------|------------------------------|-----------------------------------------|--------------|---------|
|**Name**|Ja|Ja|Ja|Ja|Ja|Ja|Ja|-|
|**Betriebssystem**|Ja|Ja|Ja|Ja|Ja|Ja|Ja|-|
|**Hersteller**|Ja|Ja|Ja|Ja|Ja|Ja|Ja|-|
|**Modell**|Ja|Ja|Ja|Ja|Ja|Ja|Ja|-|
|**Verwaltungskanal**|Ja|Ja|Ja|Ja|Ja|Ja|Ja|-|
|**AAD registriert**|Ja|Ja|Nein|Ja|Ja|Ja|Ja||-|
|**Kompatibel**|Ja|Ja|Ja|Ja|Ja|Ja|Ja|-|
|**EAS-aktiviert**|Ja|Ja|Nein|Ja|Ja|Ja|Ja|-|
|**EAS-Activation-ID**|Ja|Ja|Nein|Ja|Ja|Ja|Ja|-|
|**EAS-Aktivierungszeit**|Ja|Ja|Nein|Ja|Ja|Ja|Ja|-|
|**Verwaltungsstatus**|Ja|Ja|Ja|Ja|Ja|Ja|Ja|-|
|**E-Mail-Adresse**|Ja|Ja|Ja|Ja|Ja|Ja|Ja|-|
|**Exchange ActiveSync-ID**|Ja|Ja|Ja|Ja|Ja|Ja|Ja|-|
|**Jailbreak oder Rooting**|Nein|Ja|Nein|Ja|Nein|Nein|Nein|-|
|**Eindeutige Geräte-ID**|Nein|Ja|Ja|Ja|Ja|Ja|Ja|-|
|**Seriennummer**|Nein|Ja|Ja|Ja|Ja|Nein|Ja|-|
|**Gesamtmenge des Speicherplatzes**|Nein|Ja|Ja|Nein|Ja|Nein|Ja|-|
|**Freier Speicherplatz**|Nein|Ja|Ja|Nein|Ja|Nein|Ja|-|
|**Telefonnummer**|Nein|Ja|Nein|Ja|Nein|Ja|Nein|Telefonnummer wird mit maskiert & #42; mit Ausnahme der letzten 4 Ziffern.|
|**IMEI**|Ja|Ja|Nein|Ja|Nein|Ja|Nein|-|
|**MEID**|Nein|Ja|Nein|Nein|Nein|Nein|Nein|Mobile Geräte-ID|
|**WiFi-MAC**|Nein|Ja|Ja|Ja|Ja|Ja|Ja|-|
|**Netzbetreiber des Abonnenten**|Nein|Ja|Nein|Ja|Nein|Nein|Nein|-|
|**Mobilfunktechnologie**|Nein|Ja|Nein|Ja|Nein|Nein|Nein|-|
|**Überwacht**|Nein|Ja|Nein|Nein|Nein|Nein|Nein|-|
|**Status der Sperre-Aktivierung**|Nein|Ja|Nein|Nein|Nein|Nein|Nein|-|
|**Registrierungsdatum**|Ja|Ja|Ja|Ja|Ja|Ja|Ja|-|
|**Zuletzt aktualisiert**|Ja|Ja|Ja|Ja|Ja|Ja|Ja|-|
|**Ethernet-MAC**|Nein|Nein|Ja|Nein|Nein|Nein|Nein|-|
|**Aktivierungssperre aktiviert**|Nein|Ja|Nein|Nein|Nein|Nein|Nein|-|
|**Verschlüsselung aktiviert**|Ja|Ja|Ja|Ja|Ja|Ja|Ja|-|

## Was wird von Windows-PCs gesammelt.
> [!IMPORTANT]
> Dieser Abschnitt gilt nur für Windows-PCs, die die Computer mit Windows Intune-Clientsoftware ausgeführt werden.

Führen Sie zum Anzeigen der Inventur gesammelt, die von Windows-PCs das [Computerinventurberichte](understand-microsoft-intune-operations-by-using-reports.md). Intune sammelt die folgenden Inventur von Windows-PCs:

-   **Name**

-   **Chassistyp**

-   **Hersteller**

-   **Modell**

-   **Betriebssystem**

-   **TPM-Version**

-   **Gesamter Speicherplatz**

-   **Verwendeter Speicherplatz**

-   **Freier Speicherplatz**

-   **Name der Betriebssystem-Datenträger**

-   **Betriebssystem-Datenträger-Speicherplatz**

-   **Betriebssystem-Datenträger freien Speicherplatz**

-   **Physischer Speicher**

-   **Prozessornamen**

-   **Prozessorarchitektur**

-   **CPU-Geschwindigkeit**

-   **IP-Adresse**

-   **Seriennummer**

-   **Letzte Benutzer anmelden**

-   **Zugewiesener Benutzer**

-   **Zuletzt aktualisiert**

### Siehe auch
[Überwachung und Berichte in Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)



<!--HONumber=Mar16_HO4-->


