---
# required metadata

title: Android-MAM-Richtlinieneinstellungen | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5dbb702a-1df5-4637-95c9-77a5f0b1a0e3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: andcerat
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Android-Verwaltungsrichtlinieneinstellungen für mobile Apps in Microsoft Intune
Die nachfolgend beschriebenen Richtlinieneinstellungen können im Azure-Portal auf dem Blatt [Einstellungen](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) für eine MAM-Richtlinie **konfiguriert** werden.
Es gibt zwei Kategorien von Richtlinieneinstellungen: Datenverlagerung und Zugriff:

##  Einstellungen für die Datenverlagerung
Der Begriff **Richtlinienverwaltete Apps** wird verwendet, um auf Apps zu verweisen, die mit MAM-Richtlinien konfiguriert sind.
- **Android-Datensicherungen verhindern:** Wählen Sie **Ja** aus, um die Funktion zu deaktivieren, oder **Nein**, um die Datensicherung von Unternehmensdaten aus richtlinienverwalteten Apps zuzulassen.

  **Standardwert = Ja**
- **App Übertragung von Daten an andere Apps erlauben:** Wählen Sie eine der Optionen, um die Apps anzugeben, die Unternehmensdaten von richtlinienverwalteten Apps empfangen dürfen:
  -   **Richtlinienverwaltete Apps**: Datenübertragung nur an andere Apps zulassen, für die die MAM-Richtlinie gilt
  -   **Alle Apps**: Datenübertragung an beliebige Apps zulassen
  -   **Keine**: Datenübertragung an andere Apps nicht zulassen

  **Standardwert = Richtlinienverwaltete Apps**
- **App Empfang von Daten aus anderen Apps erlauben:** Geben Sie Apps an, die Daten an die richtlinienverwalteten Apps übertragen dürfen:
  -   **Richtlinienverwaltete Apps**: Datenübertragung nur von anderen richtlinienverwalteten Apps zulassen
  -   **Alle Apps**: Datenübertragung von beliebigen Apps zulassen
  -   **Keine**: Datenübertragung von anderen Apps nicht zulassen

      **Standardwert = Alle Apps**

-   **„Speichern unter“ verhindern:** Wählen Sie **Ja** aus, um die Verwendung der Option „Speichern unter“ in jeder App zu deaktivieren, die diese Richtlinie verwendet. Wählen Sie **Nein** aus, wenn die Verwendung von „Speichern unter“ zulässig sein soll.

  **Standardwert = Ja**
- **Ausschneiden, Kopieren und Einfügen mit anderen Apps einschränken:** Geben Sie an, ob Ausschneiden, Kopieren und Einfügen eingeschränkt werden sollen. Wählen Sie aus:
  -   **Blockiert**: Ausschneiden, Kopieren und Einfügen zwischen richtlinienverwalteten Apps nicht zulassen.
  -   **Richtlinienverwaltete Apps**: Ausschneiden, Kopieren und Einfügen nur zwischen richtlinienverwalteten Apps zulassen.
  -   **Richtlinienverwaltete Apps mit Einfügen**: Ausschneiden oder Kopieren zwischen richtlinienverwalteten Apps zulassen. Einfügen der aus beliebigen Apps ausgeschnittenen oder kopierten Daten in diese App zulassen.
  -   **Jede App**: Keine Einschränkungen für das Ausschneiden, Kopieren und Einfügen zwischen beliebigen Apps.

    **Standardwert = Richtlinienverwaltete Apps mit Einfügen**
-   **Anzeige von Webinhalten auf den Managed Browser beschränken:** Wenn diese Einstellung aktiviert ist, werden alle Links aus der App in Managed Browser geöffnet.

  Für Geräte, die nicht bei Intune registriert sind, können Weblinks in richtlinienverwalteten Apps nur in der Managed Browser-App unter Verwendung der Verwaltungsrichtlinie für mobile Apps geöffnet werden.

  Wenn Sie Intune zum Verwalten Ihrer Geräte verwenden, lesen Sie [Verwalten des Internetzugriffs mittels Richtlinien für verwaltete Browser mit Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).

    **Standardwert = Ja**
- **App-Daten verschlüsseln:** Wählen Sie **Ja** aus, um die Verschlüsselung zu aktivieren. Wenn diese Einstellung aktiviert ist, wird bei Apps, die einer Verwaltungsrichtlinie für mobile Apps zugeordnet sind, die Verschlüsselung von Microsoft bereitgestellt. Daten werden während der Datei-E/A-Vorgänge synchron verschlüsselt. Inhalt im Speicher des Geräts wird immer verschlüsselt.
  >[!NOTE] Die Verschlüsselungsmethode ist nicht FIPS 140-2-zertifiziert.

  **Standardwert = Ja**

- **ContactSyncDisabled:** Wählen **Ja** aus, um zu verhindern, dass Kontaktinformationen mit der native Adressbuch-App auf dem Gerät synchronisiert werden. Wenn Sie **Nein** auswählen, speichert die App die Kontaktinformationen in der nativen Adressbuch-App auf dem Gerät.<br/>Wenn Sie zum Entfernen von Unternehmensdaten eine selektive Zurücksetzung durchführen, werden Kontakte entfernt, die direkt aus der App mit dem nativen Adressbuch synchronisiert werden. Kontakte, die aus dem nativen Adressbuch mit einer anderen externen Quelle synchronisiert werden, können nicht zurückgesetzt werden. Dies gilt derzeit nur für die **Microsoft Outlook**-App.

  **Standardwert = Ja**

##  Richtlinieneinstellungen für den Android-Zugriff
Der Begriff **Richtlinienverwaltete Apps** wird verwendet, um auf Apps zu verweisen, die mit MAM-Richtlinien konfiguriert sind.

- **PIN für Zugriff erforderlich:** Wählen Sie **Ja** aus, um für richtlinienverwaltete Apps eine PIN anzufordern. Benutzer werden beim ersten Ausführen der App im beruflichen Kontext aufgefordert, diese einzurichten.

 **Standardwert = Ja**

 -  **Einfache PIN zulassen:** Geben Sie an, ob Benutzer einfache PIN-Sequenzen wie z. B. 1234 oder 1111 verwenden dürfen. **Standardwert = Ja**.
 - **PIN-Länge:** Geben Sie die Mindestanzahl von Ziffern in einer PIN an. **Standardwert = 4**
 - **Anzahl der Versuche bis zum Zurücksetzen der PIN:** Geben Sie die Anzahl der möglichen PIN-Eingabeversuche an, bevor der Benutzer die PIN zurücksetzen muss. **Für diese Einstellung gibt es keinen Standardwert.**
- **Unternehmensanmeldeinformationen für den Zugriff erforderlich:** Wählen Sie **Ja** aus, um Unternehmensanmeldeinformationen anstelle einer PIN für den Zugriff auf die App anzufordern.  Wenn Sie diese Einstellung auf **Ja** festlegen, sind PIN oder Fingerabdruckidentifizierung damit hinfällig.  Der Benutzer wird aufgefordert, die Unternehmensanmeldeinformationen einzugeben.

  **Standardwert = Nein**
- **Ausführen verwalteter Apps auf Geräten mit Jailbreak oder Rootzugriff blockieren:** Wählen Sie **Ja** aus, wenn Sie die Ausführung von verwalteten Apps auf per Jailbreak oder Rooting manipulierten Geräten blockieren möchten. Der Benutzer kann die Apps weiterhin für private Zwecke verwenden, muss für berufliche Zwecke jedoch ein anderes Gerät verwenden.

  **Standardwert = Ja**
- **Überprüfen der Zugriffsanforderungen nach (Minuten)**-   **Timeout:**: Die Zeit (in Minuten), bevor die Zugriffsanforderungen der App erneut überprüft werden.
  -   **Offline-Toleranzperiode**: Wenn das Gerät offline ist, die Zeit (in Minuten), bevor die Zugriffsanforderungen für die App erneut geprüft werden.

    **Standardwerte = 30 Minuten Timeout, Offline-Toleranzperiode = 720 Minuten**

-   **Offline-Intervall, bevor App-Daten zurückgesetzt werden (in Tagen):** Sie können die Unternehmensdaten zurücksetzen, wenn ein Gerät für einen bestimmten Zeitraum offline war.  Legen Sie die Anzahl der Tage fest, die ein Gerät offline sein kann, bevor die Unternehmensdaten vom Gerät entfernt werden. **Tipp:** Mit der Eingabe des Werts 0 wird diese Einstellung deaktiviert.

  **Standardwert = 90 Tage**
- **Bildschirmaufnahmen und Android Assistant blockieren (Android 6 Marshmallow oder höher):** Wählen Sie **Ja** aus, um die Bildschirmaufnahme- und **Android Assistant**-Funktionen des Geräts zu blockieren, wenn diese App verwendet wird.


<!--HONumber=Jun16_HO2-->


