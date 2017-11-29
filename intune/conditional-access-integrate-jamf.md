---
title: "Integrieren von Jamf Pro in Intune zu Konformitätszwecken"
titlesuffix: Azure portal
description: "Verwenden Sie die Konformität zum Absichern von mit Jamf verwalteten Geräten."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6b37ffd23f8cf8764ba457b0803dfc308cf1c071
ms.sourcegitcommit: 82088d297eef629e3da6011681ead442ae7e25f7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Integrieren von Jamf Pro in Intune zu Konformitätszwecken

|Gilt für: Intune im Azure-Portal |
|--|
|Suchen Sie nach der Dokumentation zu Intune im klassischen Portal? [Klicken Sie hier](/intune/introduction-intune?toc=/intune-classic/toc.json).|
| |

|Zurzeit in privater Vorschau|
|--|
|Die in diesem Thema beschriebenen Features sind für Kunden derzeit nur in der privaten Vorschau verfügbar. Diese Meldung wird entfernt, wenn das Release für alle Kunden erfolgt ist.|
| |

Wenn Ihre Organisation [Jamf Pro](https://www.jamf.com) zur Verwaltung der Macs Ihrer Endbenutzer verwendet, können Sie Microsoft Intune-Konformitätsrichtlinien zusammen mit dem bedingten Zugriff in Azure Active Directory verwenden, um die Konformität von Geräten in Ihrer Organisation zu gewährleisten.

## <a name="prerequisites"></a>Voraussetzungen

Zur Konfiguration des bedingten Zugriffs mit Jamf Pro benötigen Sie Folgendes:

- Zugriff auf die private Intune-Vorschau für den bedingten Zugriff unter macOS
- Jamf Pro 10.1.0 oder höher
- [Die Unternehmensportal-App für macOS](https://aka.ms/macoscompanyportal)
- macOS-Geräte mit OS X 10.11 Yosemite oder höher

## <a name="connecting-intune-to-jamf-pro"></a>Herstellen einer Verbindung zwischen Intune und Jamf Pro

Eine Verbindung zwischen Intune und Jamf Pro können Sie folgendermaßen herstellen:

1. Erstellen einer neuen Anwendung in Azure
2. Ermöglichen einer Integration von Intune in Jamf Pro
3. Konfigurieren des bedingten Zugriffs in Jamf Pro

## <a name="create-a-new-application-in-azure-active-directory"></a>Erstellen einer neuen Anwendung in Azure Active Directory

1. Öffnen Sie **Azure Active Directory** > **App-Registrierung**.
2. Klicken Sie auf **+Registrierung einer neuen Anwendung**.
3. Geben Sie einen **Anzeigenamen** ein, z.B. **Bedingter Zugriff in Jamf**.
4. Wählen Sie **Web-App/API**.
5. Geben Sie die **Anmelde-URL** für Jamf Pro ein.
6. Klicken Sie auf **Anwendung erstellen**.
7. Speichern Sie die neu erstellte **Anwendungs-ID**, und öffnen Sie dann **Alle Einstellungen** > **Schlüssel**, um einen neuen Anwendungsschlüssel zu erstellen. Speichern Sie den Anwendungsschlüssel.

  > [!NOTE]
  > Der Anwendungsschlüssel wird während dieses Vorgangs nur einmal angezeigt. Achten Sie darauf, dass Sie ihn an einer Stelle speichern, an der Sie ihn problemlos abrufen können.

8. Navigieren Sie zu **Alle Einstellungen** > **API-Zugriff** > **Erforderliche Berechtigungen**, und löschen Sie alle Berechtigungen.

  > [!NOTE]
  > Fügen Sie eine neue erforderliche Berechtigung hinzu. Die Anwendung kann nur ordnungsgemäß funktionieren, wenn sie die einzelne erforderliche Berechtigung aufweist.

9.  Wählen Sie **Microsoft Intune-API**, und klicken Sie auf **Auswählen**.
10. Wählen Sie **Geräteattribute an Microsoft Intune senden**, und klicken Sie auf **Auswählen**.
11. Klicken Sie auf die Schaltfläche **Berechtigungen erteilen**, nachdem Sie die erforderlichen Berechtigungen für die Anwendung gespeichert haben.

  > [!NOTE]
  > Wenn der Anwendungsschlüssel abläuft, müssen Sie einen neuen Anwendungsschlüssel in Microsoft Azure erstellen und dann die Daten für den bedingten Zugriff in Jamf Pro aktualisieren. In Azure kann sowohl der alte als auch der neue Schlüssel aktiv sein, um Dienstunterbrechungen zu verhindern.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Ermöglichen einer Integration von Intune in Jamf Pro

1. Öffnen Sie im Microsoft Azure-Portal **Microsoft Intune** > **Gerätekompatibilität** > **Konformitätsconnector für Jamf**.
2. Aktivieren Sie den Konformitätsconnector für Jamf durch Einfügen der Anwendungs-ID in das Feld **Azure Active Directory-App-ID für Jamf**.
3. Klicken Sie auf **Speichern**.

## <a name="configure-conditional-access-in-jamf-pro"></a>Konfigurieren des bedingten Zugriffs in Jamf Pro

1. Navigieren Sie in Jamf Pro zu **Global Management** > **Conditional Access** (Globale Verwaltung > Bedingter Zugriff). Klicken Sie auf der Registerkarte **Microsoft** auf die Schaltfläche **Edit** (Bearbeiten).
2. Aktivieren Sie das Kontrollkästchen **Enable Conditional Access with Microsoft** (Bedingten Zugriff mit Microsoft aktivieren).
3. Geben Sie die erforderlichen Informationen zu Ihrem Azure-Mandanten ein, einschließlich **Location** (Standort) und **Domain name** (Domänenname) sowie die Angaben zu **Application ID** (Anwendungs-ID) und **Application Key** (Anwendungsschlüssel), die Sie in den vorherigen Schritten gespeichert haben.
4. Klicken Sie auf **Speichern**. Jamf Pro testet Ihre Einstellungen und überprüft den Erfolg des Vorgangs.

## <a name="information-shared-from-jamf-pro-to-intune"></a>Von Jamf Pro für Intune freigegebene Informationen

Jamf Pro erfasst Inventurinformationen zu verwalteten macOS-Geräten. Jamf Pro meldet die folgenden Informationen an Intune:

* Azure AD-Geräte-ID
* JAMF-Inventurstatus (Inventurstatus eines Computers, der sich innerhalb der letzten 24 Stunden bei Jamf Pro eingecheckt hat)
* Betriebssystemversion
* Azure AD-Benutzer-ID
* Verschlüsselt (FileVault 2)
* Gatekeeperstatus
* Kennwort: Mindestanzahl von Zeichensätzen
* Kennwortablauf (Tage)
* Kennworttyp: einfach, alphanumerisch oder unbekannt
* Automatische Anmeldung verhindern
* Erforderliche Kennungslänge
* Kennwort: Anzahl vorheriger Kennwörter zum Verhindern der Wiederverwendung
* Systemintegritätsschutz
* Zeitpunkt des letzten Check-Ins
* Architekturtyp
* Verfügbare Speichersteckplätze
* Akkukapazität
* Start-ROM
* Busgeschwindigkeit
* Cachegröße
* Gerätename
* Domäne beitreten
* Jamf-ID
* MAC-Adresse
* Automarke
* Modell
* Modellbezeichnung
* NIC-Geschwindigkeit
* Anzahl der Kerne
* Prozessoranzahl
* Betriebssystem
* Plattform
* Prozessorgeschwindigkeit
* Prozessortyp
* Sekundäre MAC-Adresse
* Seriennummer
* SMC-Version
* RAM gesamt
* UDID
* Benutzer-E-Mail-Adresse

## <a name="next-steps"></a>Nächste Schritte

- [Anwenden von Konformitätsrichtlinien auf mit Jamf verwaltete Geräte](conditional-access-assign-jamf.md)
