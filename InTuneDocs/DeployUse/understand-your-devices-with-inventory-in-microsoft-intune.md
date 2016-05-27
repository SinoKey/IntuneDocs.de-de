---
# required metadata

title: Verstehen Sie Ihre Geräte mithilfe des Inventars in Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 312911fe-b963-4949-9911-ae425e0590b2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Verstehen Sie Ihre Geräte mithilfe des Inventars in Microsoft Intune
Mit Microsoft Intune können Sie das Inventar an registrierten Geräten und Windows-PCs anzeigen, auf denen die Intune-Clientsoftware ausgeführt wird.

## Welche Daten registrierter Geräte werden gesammelt?
Um das von den mobilen Geräten gesammelte Inventar anzuzeigen, führen Sie die [Inventurberichte für mobile Geräte](understand-microsoft-intune-operations-by-using-reports.md)aus. Intune sammelt das folgende Inventar von den mobilen Geräten:

|Eigenschaft|Gesammelt von|
|------------|-----------------------|
|**Name**|Alle Geräte|
|**Betriebssystem**|Alle Geräte|
|**Hersteller**|Alle Geräte|
|**Modell**|Alle Geräte|
|**Verwaltungskanal**|Alle Geräte|
|**Bei AAD registriert**|Alle Geräte mit Ausnahme von Mac OS X|
|**Kompatibel**|Alle Geräte|
|**EAS-aktiviert**|Alle Geräte mit Ausnahme von Mac OS X|
|**EAS-Aktivierungs-ID**|Alle Geräte mit Ausnahme von Mac OS X|
|**EAS-Aktivierungszeitpunkt**|Alle Geräte mit Ausnahme von Mac OS X|
|**Verwaltungsstatus**|Alle Geräte|
|**Email Address**|Alle Geräte|
|**Exchange ActiveSync-ID**|Alle Geräte|
|**Jailbreak oder Rooting**|Nur iOS- und Android-Geräte|
|**Eindeutige Geräte-ID**|Alle Geräte mit Ausnahme von Exchange ActiveSync|
|**Seriennummer**|iOS-, Mac OS X-, Android-, Windows 8.1-, Windows 10-Geräte|
|**Gesamtmenge des Speicherplatzes**|iOS-, Mac OS X-, Windows 8.1-, Windows 10-Geräte|
|**Freier Speicherplatz**|iOS-, Mac OS X-, Windows 8.1-, Windows 10-Geräte|
|**Telefonnummer**<br>Telefone, die als geschäftlich eingestuft sind, werden jetzt mit der vollständigen Telefonnummer identifiziert, wenn Sie beispielsweise einen Inventurbericht für mobile Geräte ausführen. BYOD-Telefonnummern werden mit &#42; maskiert, und nur die letzten vier Ziffern werden angezeigt.|iOS-, Android- und Windows Phone-Geräte|
|**IMEI**|Exchange ActiveSync-, iOS-, Android- und Windows Phone-Geräte|
|**MEID**<br>Mobile Equipment Identifier|Nur iOS-Geräte|
|**WiFi-MAC**|Alle Geräte mit Ausnahme von Exchange ActiveSync|
|**Netzbetreiber des Abonnenten**|Nur iOS- und Android-Geräte|
|**Mobilfunktechnologie**|Nur iOS- und Android-Geräte|
|**Überwacht**|Nur iOS-Geräte|
|**Aktivierungssperrenstatus**|Nur iOS-Geräte|
|**Registrierungsdatum**|Alle Geräte|
|**Zuletzt aktualisiert**|Alle Geräte|
|**Ethernet MAC**|Nur Mac OS X-Geräte|
|**Aktivierungssperre aktiviert**|Nur iOS-Geräte|
|**Verschlüsselung aktiviert**|Alle Geräte|

## Was wird von Windows-PCs gesammelt
> [!IMPORTANT]
> Dieser Abschnitt gilt nur für Windows-PCs, auf denen die Intune-Windows-PC-Clientsoftware ausgeführt wird.

Um das von den Windows-PCs gesammelte Inventar anzuzeigen, führen Sie die [Computerinventurberichte](understand-microsoft-intune-operations-by-using-reports.md) aus. Intune sammelt das folgende Inventar von den Windows-PCs:

-   **Name**

-   **Chassistyp**

-   **Hersteller**

-   **Modell**

-   **Betriebssystem**

-   **TPM-Version**

-   **Gesamter Speicherplatz**

-   **Verwendeter Speicherplatz**

-   **Freier Speicherplatz**

-   **Name des Betriebssystem-Datenträgers**

-   **Speicherplatz des Betriebssystem-Datenträgers**

-   **Freier Speicherplatz des Betriebssystem-Datenträgers**

-   **Physischer Speicher**

-   **Name des Prozessors**

-   **Prozessorarchitektur**

-   **CPU-Geschwindigkeit**

-   **IP-Adresse**

-   **Seriennummer**

-   **Letzter Benutzer, der sich angemeldet hat**

-   **Zugewiesener Benutzer**

-   **Zuletzt aktualisiert**

### Weitere Informationen
[Überwachung und Berichte in Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)



<!--HONumber=May16_HO1-->


