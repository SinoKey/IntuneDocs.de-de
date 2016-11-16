---
title: Android-MAM-Richtlinieneinstellungen | Microsoft Intune
description: "In diesem Thema werden die Verwaltungsrichtlinieneinstellungen für mobile Apps auf Android-Geräten beschrieben."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5dbb702a-1df5-4637-95c9-77a5f0b1a0e3
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e5e41cbbf3bac3ed78ee3a6929e364f829fa1d4b
ms.openlocfilehash: f8a25815662333fd48d7ea9df24f5f228cee8217


---

# Android-Verwaltungsrichtlinieneinstellungen für mobile Apps in Microsoft Intune
Die in diesem Thema beschriebenen Richtlinieneinstellungen können im Azure-Portal auf dem Blatt **Einstellungen** für eine MAM-Richtlinie (mobile application management, Verwaltung mobiler Anwendungen) [konfiguriert](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) werden.
Es gibt zwei Kategorien von Richtlinieneinstellungen: Datenverlagerungs- und Zugriffseinstellungen. In diesem Thema verweist der Begriff *Richtlinienverwaltete Apps* auf Apps, die mit MAM-Richtlinien konfiguriert sind.

##  Einstellungen für die Datenverlagerung

- **Android-Sicherungen verhindern:** Wählen Sie **Ja** aus, um die Funktion zu deaktivieren, oder **Nein**, um die Sicherung von Unternehmensdaten aus richtlinienverwalteten Apps zuzulassen.

  Standardwert = **Ja**
- **Zulassen, dass die App Daten an andere Apps überträgt:** Wählen Sie eine der Optionen aus, um die Apps anzugeben, die Unternehmensdaten von richtlinienverwalteten Apps empfangen dürfen:
  -   **Richtlinienverwaltete Apps**: Datenübertragung nur an andere Apps zulassen, für die die MAM-Richtlinie gilt.
  -   **Alle Apps**: Datenübertragung an beliebige Apps zulassen
  -   **Keine**: Datenübertragung an andere Apps nicht zulassen

  Standardwert = **Richtlinienverwaltete Apps**
- **Zulassen, dass die App Daten von anderen Apps empfängt:** Geben Sie Apps an, die Daten an die richtlinienverwalteten Apps übertragen dürfen:
  -   **Richtlinienverwaltete Apps**: Datenübertragung nur von anderen richtlinienverwalteten Apps zulassen
  -   **Alle Apps**: Datenübertragung von beliebigen Apps zulassen
  -   **Keine**: Keine Datenübertragung von anderen Apps zulassen.

  Standardwert = **Alle Apps**

-   **„Speichern unter“ verhindern:** Wählen Sie **Ja** aus, um die Verwendung der Option „Speichern unter“ in jeder App zu deaktivieren, die diese Richtlinie verwendet. Wählen Sie **Nein** aus, wenn die Verwendung von „Speichern unter“ zulässig sein soll.

  Standardwert = **Ja**
- **Ausschneiden, Kopieren und Einfügen mit anderen Apps einschränken:** Geben Sie an, ob Ausschneiden, Kopieren und Einfügen eingeschränkt werden sollen. Wählen Sie aus:
  -   **Blockiert**: Ausschneiden, Kopieren und Einfügen zwischen richtlinienverwalteten Apps nicht zulassen
  -   **Richtlinienverwaltete Apps**: Ausschneiden, Kopieren und Einfügen nur zwischen richtlinienverwalteten Apps zulassen
  -   **Richtlinienverwaltete Apps mit Einfügen**: Ausschneiden oder Kopieren zwischen richtlinienverwalteten Apps zulassen. Einfügen der aus beliebigen Apps ausgeschnittenen oder kopierten Daten in diese App zulassen.
  -   **Jede App**: Keine Einschränkungen für das Ausschneiden, Kopieren und Einfügen zwischen beliebigen Apps

  Standardwert = **Richtlinienverwaltete Apps mit Einfügen**
-   **Anzeige von Webinhalten auf den Managed Browser beschränken:** Wenn diese Einstellung aktiviert ist, werden alle Links aus der App in der Managed Browser-App geöffnet.

  Für Geräte, die nicht bei Intune registriert sind, können Weblinks in richtlinienverwalteten Apps nur in der Managed Browser-App unter Verwendung der MAM-Richtlinie geöffnet werden.

  Wenn Sie Intune zum Verwalten Ihrer Geräte verwenden, lesen Sie [Verwalten des Internetzugriffs mittels Richtlinien für Managed Browser mit Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).

  Standardwert = **Ja**
- **App-Daten verschlüsseln:** Wählen Sie **Ja** aus, um die Verschlüsselung zu aktivieren. Wenn diese Einstellung aktiviert ist, stellt Microsoft die Verschlüsselung für Apps bereit, die einer MAM-Richtlinie zugeordnet sind. Daten werden während der Datei-E/A-Tasks synchron verschlüsselt. Inhalt im Gerätespeicher wird immer verschlüsselt.
  >[!NOTE]
  >Die Verschlüsselungsmethode ist nicht FIPS 140-2-zertifiziert.

  Standardwert = **Ja**

- **Kontaktsynchronisierung deaktivieren:** Wählen Sie **Ja** aus, um zu verhindern, dass Kontaktinformationen mit der nativen Adressbuch-App auf dem Gerät synchronisiert werden. Wenn Sie **Nein** auswählen, speichert die App die Kontaktinformationen in der nativen Adressbuch-App auf dem Gerät.

  Wenn Sie zum Entfernen von Unternehmensdaten eine selektive Zurücksetzung durchführen, werden Kontakte entfernt, die direkt aus der App mit dem nativen Adressbuch synchronisiert werden. Kontakte, die aus dem nativen Adressbuch mit einer anderen externen Quelle synchronisiert werden, können nicht zurückgesetzt werden. Dies gilt derzeit nur für die Microsoft Outlook-App.

  Standardwert = **Ja**
- **Drucken deaktivieren:** Wählen Sie **Ja** aus, um zu verhindern, dass Unternehmensdaten aus Apps gedruckt werden, die mit der MAM-Richtlinie verknüpft sind.

  Standardwert = **Ja**

##  Zugriffseinstellungen

- **PIN für Zugriff erforderlich:** Wählen Sie **Ja** aus, um für richtlinienverwaltete Apps eine PIN anzufordern. Benutzer werden beim ersten Ausführen der App im beruflichen Kontext aufgefordert, diese einzurichten.

 Standardwert = **Ja**

 -  **Einfache PIN zulassen:** Geben Sie an, ob Benutzer einfache PIN-Sequenzen wie z B. 1234 oder 1111 verwenden dürfen. Standardwert = **Ja**
 - **PIN-Länge:** Geben Sie die Mindestanzahl von Ziffern in einer PIN an. Standardwert = **4**
 - **Anzahl der Versuche bis zum Zurücksetzen der PIN:** Geben Sie die Anzahl der möglichen PIN-Eingabeversuche an, bevor der Benutzer die PIN zurücksetzen muss. Für diese Einstellung gibt es keinen Standardwert.
- **Unternehmensanmeldeinformationen für den Zugriff erforderlich:** Wählen Sie **Ja** aus, um Unternehmensanmeldeinformationen anstelle einer PIN für den Zugriff auf die App anzufordern. Wenn Sie diese Einstellung auf **Ja** festlegen, sind PIN oder Fingerabdruckidentifizierung damit hinfällig. Der Benutzer wird aufgefordert, die Unternehmensanmeldeinformationen einzugeben.

  Standardwert = **Nein**
- **Ausführen verwalteter Apps auf Geräten mit Jailbreak oder Rootzugriff blockieren:** Wählen Sie **Ja** aus, wenn Sie die Ausführung von verwalteten Apps auf Geräten mit entfernten Nutzungsbeschränkungen blockieren möchten. Der Benutzer kann die Apps weiterhin für private Zwecke verwenden, muss für berufliche Zwecke jedoch ein anderes Gerät verwenden.

  Standardwert = **Ja**
- **Überprüfen der Zugriffsanforderungen nach (Minuten)**
  -   **Timeout:** Geben Sie die Zeit (in Minuten) an, bevor die Zugriffsanforderungen der App erneut überprüft werden.
  -   **Offline-Toleranzperiode**: Wenn das Gerät offline ist, geben Sie die Zeit (in Minuten) an, bevor die Zugriffsanforderungen für die App erneut geprüft werden.

  Standardwerte = **30** Minuten Timeout, Offline-Toleranzperiode = **720** Minuten

-   **Offline-Intervall, bevor App-Daten zurückgesetzt werden (in Tagen):** Sie können die Unternehmensdaten zurücksetzen, wenn ein Gerät für einen bestimmten Zeitraum offline war.  Legen Sie die Anzahl der Tage fest, die ein Gerät offline sein kann, bevor die Unternehmensdaten vom Gerät entfernt werden.

    >[!TIP]
    >Durch die Eingabe des Werts **0** wird diese Einstellung deaktiviert.

  Standardwert = **90** Tage
- **Bildschirmaufnahme und Android-Assistent blockieren (Android 6 Marshmallow oder höher):** Wählen Sie **Ja** aus, um die Bildschirmaufnahme- und **Android Assistent**-Funktionen des Geräts zu blockieren, wenn diese App verwendet wird.



<!--HONumber=Oct16_HO3-->


