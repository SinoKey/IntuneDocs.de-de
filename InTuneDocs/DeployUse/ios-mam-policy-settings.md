---
title: iOS-MAM-Richtlinieneinstellungen | Microsoft Intune
description: 
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 673ff872-943c-4076-931c-0be90363aea9
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5a445f06d6c2328f7689468ca4d68a969af1e825
ms.openlocfilehash: b3df4b35dbe2710157b88a4e7fdba9734f8b998b


---

#  iOS-Richtlinieneinstellungen für die Verwaltung mobiler Apps
Die nachfolgend beschriebenen Richtlinieneinstellungen können im Azure-Portal auf dem Blatt [Einstellungen](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) für eine MAM-Richtlinie **konfiguriert** werden.

Es gibt zwei Kategorien von Richtlinieneinstellungen: Datenverlagerung und Zugriff:

##  Einstellungen für die Datenverlagerung
Der Begriff **Richtlinienverwaltete Apps** wird verwendet, um auf Apps zu verweisen, die mit MAM-Richtlinien konfiguriert sind.

- **iTunes- und iCloud-Sicherungen verhindern:** Wählen Sie **Ja**, um die Funktion zu deaktivieren, oder **Nein**, um das Sichern von Unternehmensdaten aus den richtlinienverwalteten Apps zuzulassen.

  **Standardwert = Ja**

- **App Übertragung von Daten an andere Apps erlauben:** Wählen Sie eine der Optionen, um die Apps anzugeben, die Daten von richtlinienverwalteten Apps empfangen dürfen:
  - **Richtlinienverwaltete Apps**: Datenübertragung nur an andere Apps zulassen, für die die MAM-Richtlinie gilt.
  - **Alle Apps**: Datenübertragung an beliebige Apps zulassen.
  - **Keine**: Keine Datenübertragung an beliebige Apps zulassen, auch nicht an andere richtlinienverwaltete Apps.

  Wenn Sie diese Option auf **Richtlinienverwaltete Apps** oder **Keine** festlegen, wird zudem das iOS 9-Feature blockiert, das der Spotlight-Suche erlaubt, Daten in Apps zu suchen.

  **Standardwert = Richtlinienverwaltete Apps**

- **App Empfang von Daten aus anderen Apps erlauben:** Geben Sie Apps an, die Daten an die richtlinienverwalteten Apps übertragen dürfen:
  -  **Richtlinienverwaltete Apps**: Datenübertragung nur von anderen richtlinienverwalteten Apps zulassen.
  -  **Alle Apps**: Datenübertragung von beliebigen Apps zulassen.
  -  **Keine**: Keine Datenübertragung von anderen Apps zulassen.

  **Standardwert = Alle Apps**

- **„Speichern unter“ verhindern:** Wählen Sie **Ja** aus, um die Verwendung der Option „Speichern unter“ in jeder App zu deaktivieren, die diese Richtlinie verwendet. Wählen Sie **Nein** aus, wenn die Verwendung von „Speichern unter“ zulässig sein soll.

  **Standardwert = Ja**

- **Ausschneiden, Kopieren und Einfügen mit anderen Apps einschränken:** Geben Sie an, ob Ausschneiden, Kopieren und Einfügen eingeschränkt werden sollen. Wählen Sie aus:
  -   **Blockiert**: Ausschneiden, Kopieren und Einfügen zwischen richtlinienverwalteten Apps nicht zulassen.
  -   **Richtlinienverwaltete Apps**: Ausschneiden, Kopieren und Einfügen nur zwischen richtlinienverwalteten Apps zulassen.
  -   **Richtlinienverwaltete Apps mit Einfügen**: Ausschneiden oder Kopieren zwischen richtlinienverwalteten Apps zulassen. Einfügen der aus beliebigen Apps ausgeschnittenen oder kopierten Daten in diese App zulassen.
  - **Jede App**: Keine Einschränkungen für das Ausschneiden, Kopieren und Einfügen zwischen beliebigen Apps.

  **Standardwert = Richtlinienverwaltete Apps mit Einfügen**

- **Anzeige von Webinhalten auf den Managed Browser beschränken:** Wenn diese Einstellung aktiviert ist, werden alle Links aus der App im Managed Browser geöffnet.

  Für Geräte, die nicht bei Intune registriert sind, können Weblinks in richtlinienverwalteten Apps nur in der Managed Browser-App unter Verwendung der Verwaltungsrichtlinie für mobile Apps geöffnet werden.

  Wenn Sie Intune zum Verwalten Ihrer Geräte verwenden, lesen Sie [Verwalten des Internetzugriffs mittels Richtlinien für verwaltete Browser mit Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).

    **Standardwert = Ja**

- **App-Daten verschlüsseln:** Für Apps, die einer [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Verwaltungsrichtlinie für mobile Anwendungen zugeordnet sind, werden Daten im Ruhezustand mit vom Betriebssystem bereitgestellter Verschlüsselung auf Geräteebene verschlüsselt. Wenn eine PIN erforderlich ist, werden die Daten gemäß den Einstellungen in der Verwaltungsrichtlinie für mobile Apps verschlüsselt. Wie in der Apple-Dokumentation angegeben, [sind die von iOS 7 verwendeten Module FIPS 140-2-zertifiziert](http://support.apple.com/en-us/HT202739).

  In den Richtlinieneinstellungen können Sie PIN-Verschlüssungswerte festlegen.  Diese Werte bestimmen, wann die Daten verschlüsselt werden. Folgende Optionen sind verfügbar:
  - **Wenn Gerät gesperrt**: Alle App-Daten unter dieser Richtlinie werden verschlüsselt, während das Gerät gesperrt ist.
  -   **Wenn Gerät gesperrt (außer geöffnete Dateien)**: Alle App-Daten unter dieser Richtlinie werden verschlüsselt, wenn das Gerät gesperrt ist, außer den Daten in Dateien, die derzeit in der App geöffnet sind.
  -   **Nach Neustart des Geräts**: Alle App-Daten unter dieser Richtlinie werden verschlüsselt, wenn das Gerät neu gestartet wird, bis das Gerät zum ersten Mal entsperrt wird.
  -   **Geräteeinstellungen verwenden**: App-Daten werden basierend auf den Standardeinstellungen des Geräts verschlüsselt.
  Wenn Sie diese Einstellung aktivieren, muss der Endbenutzer eine PIN einrichten und verwenden, um auf sein Gerät zuzugreifen.  Wenn keine PIN eingerichtet wurde, werden die Apps nicht gestartet, und der Endbenutzer wird mit der Meldung „Ihr Unternehmen verlangt, dass Sie zuerst eine Geräte-PIN aktivieren, bevor Sie auf diese Anwendung zugreifen können“ aufgefordert, eine PIN einzurichten.

  **Standardwert = Die Option „Verschlüsselung“ wurde nicht ausgewählt.**
- **Kontaktsynchronisierung deaktivieren:** Wählen Sie **Ja** aus, um zu verhindern, dass Kontaktinformationen mit der nativen Adressbuch-App auf dem Gerät synchronisiert werden. Wenn Sie **Nein** auswählen, speichert die App die Kontaktinformationen in der nativen Adressbuch-App auf dem Gerät.

  Wenn Sie zum Entfernen von Unternehmensdaten eine selektive Zurücksetzung durchführen, werden Kontakte entfernt, die direkt aus der App mit dem nativen Adressbuch synchronisiert werden. Kontakte, die aus dem nativen Adressbuch mit einer anderen externen Quelle synchronisiert werden, können nicht zurückgesetzt werden. Dies gilt derzeit nur für die **Microsoft Outlook**-App.

  **Standardwert = Ja**
##  Richtlinieneinstellungen für den iOS-Zugriff
Der Begriff **Richtlinienverwaltete Apps** wird verwendet, um auf Apps zu verweisen, die mit MAM-Richtlinien konfiguriert sind.
- **PIN für Zugriff erforderlich:**  Wählen Sie **Ja** aus, um für richtlinienverwaltete Apps eine PIN anzufordern. Benutzer werden beim ersten Ausführen der App im beruflichen Kontext aufgefordert, diese einzurichten.

  **Standardwert = Ja**
    -  **Einfache PIN zulassen:** Geben Sie an, ob Benutzer einfache PIN-Sequenzen wie z. B. 1234 oder 1111 verwenden dürfen. **Standardwert = Ja**.
    - **PIN-Länge:** Geben Sie die Mindestanzahl von Ziffern in einer PIN an. **Standardwert = 4**
    - **Anzahl der Versuche bis zum Zurücksetzen der PIN:** Geben Sie die Anzahl der möglichen PIN-Eingabeversuche an, bevor der Benutzer die PIN zurücksetzen muss.
  **Für diese Einstellung gibt es keinen Standardwert**.

  - **Fingerabdruck anstelle von PIN erforderlich (iOS 8.0+):** Wählen Sie **Ja** aus, um für den Zugriff auf die App einen Identitätsnachweis in Form eines Fingerabdrucks anstelle einer aus Zahlen bestehenden PIN anzufordern.
Auf iOS-Geräten können Sie zulassen, dass sich die Benutzer per Fingerabdruck anstelle einer PIN identifizieren. Wenn der Benutzer versucht, mit seinem Geschäftskonto auf diese App zuzugreifen, wird er aufgefordert seine Identität per Fingerabdruck und nicht durch Eingabe einer PIN zu bestätigen.

    **Standardwert = Ja**
- **Unternehmensanmeldeinformationen für den Zugriff erforderlich:** Wählen Sie **Ja** aus, um Unternehmensanmeldeinformationen anstelle einer PIN für den Zugriff auf die App anzufordern. **Wenn Sie diese Einstellung auf „Ja“ festlegen, sind PIN oder Fingerabdruckidentifizierung damit hinfällig.** Der Benutzer wird aufgefordert, die Unternehmensanmeldeinformationen einzugeben.

  **Standardwert = Nein**
- **Ausführen verwalteter Apps auf Geräten mit Jailbreak oder Rootzugriff blockieren:** Wählen Sie **Ja** aus, wenn Sie die Ausführung von verwalteten Apps auf per Jailbreak oder Rooting manipulierten Geräten blockieren möchten. Der Benutzer kann die Apps weiterhin für private Zwecke verwenden, muss für berufliche Zwecke jedoch ein anderes Gerät verwenden.

  **Standardwert = Ja**
- **Überprüfen der Zugriffsanforderungen nach (Minuten)**|-   **Timeout:**: Die Zeit (in Minuten), bevor die Zugriffsanforderungen der App erneut überprüft werden.
  -   **Offline-Toleranzperiode**: Wenn das Gerät offline ist, die Zeit (in Minuten), bevor die Zugriffsanforderungen für die App erneut geprüft werden.

  **Standardwert = 30 Minuten Timeout, Offline-Toleranzperiode = 720 Minuten**
  - **Offline-Intervall, bevor App-Daten zurückgesetzt werden (in Tagen):** Sie können die Unternehmensdaten zurücksetzen, wenn ein Gerät für einen bestimmten Zeitraum offline war.  Legen Sie die Anzahl der Tage fest, die ein Gerät offline sein kann, bevor die Unternehmensdaten vom Gerät entfernt werden. **Mit der Eingabe des Werts 0 wird diese Einstellung deaktiviert**.

  **Standardwert = 90 Tage**



<!--HONumber=Jun16_HO4-->


