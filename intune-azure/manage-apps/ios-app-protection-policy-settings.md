---
title: "Einstellungen für App-Schutzrichtlinien für iOS | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): In diesem Thema werden die Einstellungen für App-Schutzrichtlinien für iOS-Geräte beschrieben."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f8b08f2-504c-4b38-bea2-b8a4ef0526b8
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c169ed02e707d605f2b3108bcf955b41d7e48918
ms.openlocfilehash: 451e4c396bc9384172592a159acab1af620e6007
ms.lasthandoff: 02/14/2017


---

#  <a name="ios-app-protection-policy-settings"></a>Einstellungen für App-Schutzrichtlinien für iOS
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Die in diesem Thema beschriebenen Richtlinieneinstellungen können im Azure-Portal auf dem Blatt **Einstellungen** für eine Schutzrichtlinie [konfiguriert](app-protection-policies.md) werden.

Es gibt zwei Kategorien von Richtlinieneinstellungen: Datenverlagerungs- und Zugriffseinstellungen. In diesem Thema bezieht sich der Begriff ***richtlinienverwaltete Apps*** auf Apps, die mit App-Schutzrichtlinien konfiguriert sind.

##  <a name="data-relocation-settings"></a>Einstellungen für die Datenverlagerung

| Einstellung | Verwendung | Standardwert(e) |
|------|------|------|
| **iTunes- und iCloud-Sicherungen verhindern** | Wählen Sie **Ja**, um zu verhindern, dass diese App Geschäfts-, Schul- oder Unidaten in iTunes und iCloud sichert. Wählen Sie **Nein**, um dieser App zu erlauben, Geschäfts-, Schul- oder Unidaten in iTunes und iCloud zu sichern.| Ja |
| **App Übertragung von Daten an andere Apps erlauben** | Geben Sie an, welche Apps Daten von dieser App empfangen können: <ul><li> **Richtlinienverwaltete Apps**: Datenübertragung nur an andere richtlinienverwaltete Apps zulassen</li> <li>**Alle Apps**: Datenübertragung an beliebige Apps zulassen </li> <li>**Keine**: Keine Datenübertragung an beliebige Apps zulassen, auch nicht an andere richtlinienverwaltete Apps.</li></ul> Wenn Sie diese Option auf **Richtlinienverwaltete Apps** oder **Keine** festlegen, wird zudem das iOS 9-Feature blockiert, das der Spotlight-Suche die Suche von Daten in Apps erlaubt. <br><br> Es gibt einige ausgenommene Apps und Dienste für die Intune möglicherweise die Datenübertragung zulässt. Unter [Data transfer exemptions (Ausnahmen bei der Datenübertragung)](#Data-transfer-exemptions) finden Sie eine vollständige Liste der Apps und Dienste. | Alle Apps |
| **App Empfang von Daten aus anderen Apps erlauben** | Geben Sie an, welche Apps Daten an diese App übertragen können: <ul><li>**Richtlinienverwaltete Apps**: Datenübertragung nur von anderen richtlinienverwalteten Apps zulassen</li><li>**Alle Apps**: Datenübertragung von beliebigen Apps zulassen</li><li>**Keine**: Keine Datenübertragung von beliebigen Apps zulassen, auch nicht von anderen richtlinienverwalteten Apps </li></ul> <p>  Es gibt einige ausgenommene Apps und Dienste von denen Intune möglicherweise die Datenübertragung zulässt. Unter [Data transfer exemptions (Ausnahmen bei der Datenübertragung)](#Data-transfer-exemptions) finden Sie eine vollständige Liste der Apps und Dienste. | Alle Apps |
| **„Speichern unter“ verhindern** | Wählen Sie **Ja** aus, um die Verwendung der Option „Speichern unter“ in dieser App zu deaktivieren. Wählen Sie **Nein** aus, wenn die Verwendung von „Speichern unter“ zulässig sein soll. | Nein |
| **Beschränken von Ausschneiden, Kopieren und Einfügen mit anderen Apps** | Geben Sie an, wann Ausschneide-, Kopier- und Einfügeaktionen in dieser App erlaubt sind. Wählen Sie aus: <ul><li>**Blockiert**: Ausschneide-, Kopier- und Einfügeaktionen zwischen dieser App und anderen Apps nicht zulassen.</li><li>**Richtlinienverwaltete Apps**: Nur Ausschneide-, Kopier- und Einfügeaktionen zwischen dieser App und anderen richtlinienverwalteten Apps zulassen.</li><li>**Richtlinienverwaltete Apps mit Einfügen**: Ausschneiden oder Kopieren zwischen dieser App und anderen richtlinienverwalteten Apps zulassen. Einfügen von Daten aus beliebigen Apps in diese App zulassen.</li><li>**Jede App**: Keine Einschränkungen für das Ausschneiden, Kopieren und Einfügen in und aus dieser App. | Jede App |
|**Anzeige von Webinhalten auf den Managed Browser beschränken** | Wählen Sie **Ja**, um zu erzwingen, dass Weblinks in der App in der Managed Browser-App geöffnet werden. <br><br> Auf Geräten, die nicht bei Intune registriert sind, können Weblinks in richtlinienverwalteten Apps nur in der Managed Browser-App geöffnet werden. <br><br> Wenn Sie Intune zum Verwalten Ihrer Geräte verwenden, lesen Sie [Verwalten des Internetzugriffs mittels Richtlinien für Managed Browser mit Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/manage-internet-access-using-managed-browser-policies). | Nein |
| **App-Daten verschlüsseln** | Für richtlinienverwaltete Apps werden Daten im Ruhezustand mithilfe des von iOS bereitgestellten Verschlüsselungsschemas auf Geräteebene verschlüsselt. Wenn eine PIN erforderlich ist, werden die Daten gemäß den Einstellungen in der App-Schutzrichtlinie verschlüsselt. <br><br> Wechseln Sie [hier](https://support.apple.com/HT202739) zur offiziellen Apple-Dokumentation, um zu prüfen, welche iOS-Verschlüsselungsmodule FIPS 140-2-zertifiziert sind bzw. bei welchen die FIPS 140-2-Zertifizierung aussteht. <br><br> Geben Sie an, wann Geschäfts-, Schul- oder Unidaten in dieser App verschlüsselt werden. Es stehen die folgenden Optionen zur Auswahl: <ul><li>**Wenn das Gerät gesperrt ist**: Alle App-Daten, die dieser Richtlinie unterliegen, werden verschlüsselt, solange das Gerät gesperrt ist.</li><li>**Wenn das Gerät gesperrt ist und Dateien geöffnet sind**: Alle App-Daten, die dieser Richtlinie unterliegen, werden verschlüsselt, solange das Gerät gesperrt ist, außer den Daten in Dateien, die derzeit in der App geöffnet sind.</li><li>**Nach Geräteneustart**: Alle App-Daten unter dieser Richtlinie werden verschlüsselt, wenn das Gerät neu gestartet wird, bis das Gerät zum ersten Mal entsperrt wird.</li><li>**Geräteeinstellungen verwenden**: App-Daten werden basierend auf den Standardeinstellungen des Geräts verschlüsselt. Wenn Sie diese Einstellung aktivieren, muss der Benutzer eine PIN einrichten und verwenden, um auf sein Gerät zuzugreifen.  Wenn keine PIN eingerichtet wurde, werden die Apps nicht geöffnet, und der Benutzer wird mit der Meldung „Ihre Organisation hat festgelegt, dass Sie zunächst eine Geräte-PIN aktivieren müssen, um auf diese App zuzugreifen“ aufgefordert, eine PIN einzurichten. </li></ul> | Wenn das Gerät gesperrt ist |
| **Kontaktsynchronisierung deaktivieren** | Wählen Sie **Ja**, um zu verhindern, dass die App Daten in der nativen App „Kontakte“ auf dem Gerät speichert. Wenn Sie **Nein** wählen, darf die App Daten in der nativen App „Kontakte“ auf dem Gerät speichern. <br><br>Bei Ausführung eines selektiven Zurücksetzens zum Entfernen von Geschäfts-, Schul- oder Unidaten aus der App werden Kontakte entfernt, die direkt aus der App in die native App „Kontakte“ synchronisiert wurden. Kontakte, die aus dem nativen Adressbuch mit einer anderen externen Quelle synchronisiert werden, können nicht zurückgesetzt werden. Dies gilt derzeit nur für die Microsoft Outlook-App. | Nein |
| **Drucken deaktivieren** | Wählen Sie **Ja**, um zu verhindern, dass die App Geschäfts-, Schul- oder Unidaten druckt. | Nein |


> [!NOTE]
> Keine der Einstellungen für die Datenverlagerung steuert die von Apple verwaltete Funktion „Öffnen in“ auf iOS-Geräten. Informationen zum Verwalten der Apple-Funktion „Öffnen in“ finden Sie unter [Verwalten der Datenübertragung zwischen iOS-Apps mit Microsoft Intune](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).

## <a name="data-transfer-exemptions"></a>Datenübertragungsausnahmen

Die App-Schutzrichtlinie von Intune erlaubt unter bestimmten Umständen die Datenübertragung zu und von einigen ausgenommenen Apps und Plattformdiensten. Diese Liste unterliegt Änderungen und gibt die Dienste und Apps wieder, die als nützlich für die sichere Produktivität gelten.

| Name der App/des Diensts | Beschreibung |
| ---- | --- |
|Tel; telprompt | Native Phone-App |
| Skype | Skype |
| App-Einstellungen | Geräteeinstellungen |
| itms; itmss; itms-Apps; itms-appss; itms-Dienste | App Store |
| calshow | Nativer Kalender |


## <a name="access-settings"></a>Zugriffseinstellungen

| Einstellung | Verwendung | Standardwert(e) |
|------|------|------|
| **PIN für Zugriff anfordern** | Wählen Sie **Ja**, um zum Verwenden dieser App eine PIN anzufordern. Benutzer werden beim ersten Ausführen der App in einem Geschäfts-, Schul- oder Unikontext aufgefordert, diese PIN einzurichten. Standardwert = **Ja**<br><br> Konfigurieren Sie die folgenden Einstellungen für die PIN: <ul><li>**Anzahl der Versuche vor dem Zurücksetzen der PIN**: Geben Sie die Anzahl der Versuche an, die der Benutzer zum erfolgreichen Eingeben seiner PIN hat, ehe diese zurückgesetzt werden muss. Standardwert = **5**.</li><li> **Einfache PIN zulassen:** Wählen Sie **Ja**, um Benutzern das Verwenden einfacher PIN-Sequenzen wie z.B. 1234 oder 1111 zu erlauben. Wählen Sie **Nein**, um zu verhindern, dass einfache Sequenzen verwendet werden. Standardwert = **Ja** </li><li> **PIN-Länge:** Geben Sie die Mindestanzahl von Ziffern in einer PIN-Sequenz an. Standardwert = **4** </li><li> **Fingerabdruck anstelle von PIN zulassen (iOS 8.0 und höher):** Wählen Sie **Ja**, um Benutzern für den Zugriff auf die App das Verwenden einer [Touch ID](https://support.apple.com/en-us/HT201371) anstelle einer PIN zu erlauben. Standardwert = **Ja**</li></ul> Auf iOS-Geräten können Sie Benutzern erlauben, ihre Identität mithilfe einer [Touch ID](https://support.apple.com/en-us/HT201371) statt einer PIN nachzuweisen. Wenn der Benutzer versucht, diese App mit seinem Geschäfts-, Schul- oder Unikonto zu nutzen, wird er aufgefordert, seine Identität per Fingerabdruck und nicht durch Eingabe einer PIN zu bestätigen. </li></ul>| PIN anfordern: Ja <br><br> Versuche zum Zurücksetzen der PIN: 5 <br><br> Einfache PIN zulassen: Ja <br><br> PIN-Länge: 4 <br><br> Fingerabdruckentsperrung zulassen: Ja |
| **Unternehmensanmeldeinformationen für Zugriff erforderlich** | Wählen Sie **Ja**, um anzufordern, dass sich der Benutzer für den Zugriff auf die App mit seinem Geschäfts-, Schul- oder Unikonto anmeldet, anstatt eine PIN einzugeben. Wenn Sie diese Einstellung auf **Ja** festlegen, sind PIN oder Fingerabdruckidentifizierung damit hinfällig.  | Nein |
| **Ausführen verwalteter Apps auf Geräten mit Jailbreak oder Rootzugriff blockieren** |  Wählen Sie **Ja** aus, um die Ausführung dieser App auf per Jailbreak oder Rootzugriff manipulierten Geräten zu verhindern. Der Benutzer kann diese App weiterhin für private Zwecke verwenden, muss jedoch für den Zugriff auf Geschäfts-, Schul- oder Unidaten ein anderes Gerät verwenden. | Ja |
| **Überprüfen der Zugriffsanforderungen nach (Minuten)** | Konfigurieren Sie die folgenden Einstellungen: <ul><li>**Timeout:** Geben Sie die Zeit (in Minuten) an, bevor die Zugriffsanforderungen der App erneut überprüft werden. Standardwert = **30** Minuten.</li><li>**Offline-Toleranzperiode**: Wenn das Gerät offline ist, geben Sie die Zeit (in Minuten) an, bevor die Zugriffsanforderungen für die App erneut geprüft werden. Standardwert = **720** Minuten (12 Stunden).</li></ul>| Timeout: 30 <br><br> Offline: 720 |
| **Offline-Intervall (in Tagen), bevor App-Daten zurückgesetzt werden** | Geschäfts-, Schul- oder Unidaten in dieser App können zurückgesetzt werden, wenn ein Gerät über einen bestimmten Zeitraum hinaus offline war. Legen Sie die Anzahl der Tage fest, die ein Gerät offline sein kann, ehe die Geschäfts-, Schul- oder Unidaten vom Gerät entfernt werden. <br><br> | 90 Tage |

##  <a name="add-ins-for-outlook-app"></a>Add-Ins für die Outlook-App

Outlook hat kürzlich Add-Ins für Outlook für iOS eingeführt, mit denen Sie beliebte Apps in den E-Mail-Client integrieren können. Add-Ins für Outlook sind im Internet, unter Windows und Mac und für Outlook für iOS verfügbar. Da Add-Ins über Microsoft Exchange verwaltet werden, können die Benutzer Daten und Nachrichten über Outlook und nicht verwaltete Add-In-Anwendungen freigeben, sofern diese Add-Ins von Exchange nicht für den Benutzer deaktiviert wurden.

Wenn Sie verhindern möchten, dass Endbenutzer auf Outlook-Add-Ins zugreifen und diese installieren (dies hat Auswirkungen auf alle Outlook-Clients), nehmen Sie im Exchange Admin Center die folgenden Änderungen an den Rollen vor:

- Um zu verhindern, dass Benutzer Office Store-Add-Ins installieren, entfernen Sie die Rolle My Marketplace.
- Um zu verhindern, dass Benutzer ein Sideloading von Add-Ins durchführen können, entfernen Sie die Rolle My Custom Apps.
- Um zu verhindern, dass Benutzer alle Add-Ins installieren, entfernen Sie beide Rollen – My Custom Apps und My Marketplace.

Diese Anweisungen gelten für Office 365, Exchange 2016, Exchange 2013 für Outlook im Web, unter Windows, auf Mac-PCs und mobil.

- Weitere Informationen finden Sie unter [Add-Ins für Outlook](https://technet.microsoft.com/library/jj943753(v=exchg.150).aspx).
- Weitere Informationen finden Sie unter [Angeben der Administratoren und Benutzer, die Add-Ins für die Outlook-App installieren und verwalten können](https://technet.microsoft.com/library/jj943754(v=exchg.150).aspx).

