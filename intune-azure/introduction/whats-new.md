---
title: Neuigkeiten in der Vorschau von Microsoft Intune
titleSuffix: Intune Azure preview
description: Erfahren Sie, welche Neuigkeiten die Vorschau von Intune Azure bietet
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: deea78dcea9ade031441bf12b388a862235a8e9c
ms.openlocfilehash: 92bb81440b9374b2b0b433b32fc0a1301998ea80
ms.lasthandoff: 03/15/2017

---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>Neuigkeiten in der Vorschau von Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Im Laufe der öffentliche Vorschau werden weitere Features hinzugefügt, über die wir Sie hier informieren werden.

> [!Note]
> Wir führen gerade die auf dieser Seite aufgeführten Änderungen für die Vorschau des Azure-Portals ein. Aufgrund der Updatemethode des Intune-Diensts stehen die Änderungen jedoch möglicherweise nicht sofort zur Verfügung.  Mehrere Komponenten des Diensts müssen nacheinander aktualisiert werden, damit die neuen Portalfeatures verfügbar werden. Diese Änderungen werden im Laufe des Monats eingeführt.

## <a name="march-2017"></a>März 2017

### <a name="support-for-ios-lost-mode---431695--"></a>Unterstützung des iOS-Modus für verlorene Geräte <!--431695-->

Für Geräte unter iOS 9.3 (oder höher) wurde von Intune die Unterstützung des **Modus für verlorene Geräte** hinzugefügt. Nun können Sie ein Gerät sperren, um zu dessen Verwendung vollständig zu unterbinden, und auf dem Sperrbildschirm des Geräts eine Meldung und eine Kontakttelefonnummer anzeigen.

Der Endbenutzer kann das Gerät erst wieder entsperren, wenn ein Administrator den Modus für verlorene Geräte deaktiviert. Bei aktiviertem Modus für verlorene Geräte können Sie mithilfe der Aktion „Gerät suchen“ den geografischen Standort des Geräts auf einer Karte in der Intune-Konsole anzeigen.

Weitere Informationen finden Sie unter [Was ist die Microsoft Intune-Geräteverwaltung?](/intune-azure/manage-devices/what-is).

### <a name="improvements-to-device-actions-report---677150--"></a>Verbesserungen des Geräteaktionenberichts<!--677150-->

Wir haben die Leistung des Geräteaktionenberichts verbessert. Darüber hinaus können Sie jetzt den Bericht nach Status filtern. Beispielsweise könnten Sie den Bericht so filtern, dass nur Geräteaktionen angezeigt werden, die abgeschlossen wurden.

### <a name="actions-for-non-compliance---730266--"></a>Aktionen bei Inkompatibilität <!--730266-->

**Aktionen bei Inkompatibilität** ist ein neues Feature für Kompatibilitätsrichtlinien, mit der Sie Aktionen für Geräte einrichten können, die nicht kompatibel sind. Sie können eine oder mehrere Aktionen angeben und den Zeitraum festlegen, in dem diese Aktionen ausgeführt werden müssen. Sie können z.B. Benutzer von Geräten per E-Mail benachrichtigen, sobald ihr Gerät inkompatibel wurde. Sie können auch den Zugriff nicht kompatibler Geräte auf Unternehmensressourcen sperren, nachdem die Geräte während einer dreitägigen Karenzzeit per bedingtem Zugriff zugreifen konnten.

### <a name="custom-app-categories---748805--"></a>Benutzerdefinierte App-Kategorien <!--748805-->

Sie können jetzt Kategorien für in Intune hinzugefügte Apps erstellen, bearbeiten und zuweisen. Zurzeit können Kategorien nur auf Englisch angegeben werden.
Weitere Informationen finden Sie unter [How to add an app to Intune (Hinzufügen einer App zu Intune)](/intune-azure/manage-apps/add-apps).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>Zuweisen von Branchen-Apps für Benutzer nicht registrierter Geräte <!--748823-->

Sie können Benutzern jetzt Branchen-Apps aus dem Store zuweisen, unabhängig davon, ob die Benutzergeräte bei Intune registriert sind oder nicht. Wenn das Gerät eines Benutzers nicht bei Intune registriert ist, muss der Benutzer die App über die Unternehmensportal-Website statt über die Unternehmensportal-App installieren.

### <a name="new-compliance-reports---846671--"></a>Neue Kompatibilitätsberichte <!--846671-->

Jetzt informieren Kompatibilitätsberichte Sie über die Kompatibilitätsstellung von Geräten in Ihrem Unternehmen, sodass sie schnell kompatibilitätsbezogene Probleme beheben können, von denen Ihre Benutzer betroffen sind. Sie können Informationen anzeigen zu:

- Gesamter Kompatibilitätsstatus von Geräten
- Kompatibilitätsstatus für eine einzelne Einstellung
- Kompatibilitätsstatus für eine einzelne Richtlinie

Sie können mit diesen Berichten auch Detailinformationen zu einzelnen Geräten erhalten, um bestimmte Einstellungen und Richtlinien anzuzeigen, die sich auf das Gerät auswirken.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Direkter Zugriff auf Apple-Registrierungsszenarien <!--951869-->

Für Intune-Konten, die nach Januar 2017 erstellt wurden, hat Intune direkten Zugriff auf Apple-Registrierungsszenarien mithilfe der Workload „Geräte registrieren“ im Azure-Vorschauportal aktiviert. Bisher konnte nur über Links im klassischen Intune-Portal auf die Apple-Registrierungsvorschau zugegriffen werden. Vor Januar 2017 erstellte Intune-Konten erfordern eine einmalige Migration, bevor diese Features in Azure verfügbar sind. Der Zeitplan für die Migration wurde noch nicht angekündigt, aber Sie erfahren so bald wie möglich Näheres. Wir empfehlen Ihnen dringend, ein Testkonto zu erstellen, um die neue Oberfläche zu testen, wenn Sie mit Ihrem vorhandenen Konto nicht auf die Vorschau zugreifen können.


## <a name="february-2017"></a>Februar 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Einschränken der Registrierung von Mobilgeräten <!--747600, 795782-->
Es wurden neue Registrierungseinschränkungen zu Intune hinzugefügt, mit denen sich kontrollieren lässt, welche Mobilgeräteplattformen für die Registrierung zugelassen werden. Intune unterscheidet dabei zwischen den Mobilgeräteplattformen iOS, macOS, Android, Windows und Windows Mobile.

* Durch das Einschränken der Registrierung von Mobilgeräten wird die Registrierung von PC-Clients nicht eingeschränkt.  
* Für iOS und Android gibt es eine zusätzliche Option, mit der die Registrierung persönlicher Geräte blockiert werden kann.

Intune kennzeichnet alle neuen Geräte als persönlich, es sei denn, der IT-Administrator kennzeichnet sie als unternehmenseigen – wie in [diesem Artikel](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices) beschrieben.

### <a name="view-all-actions-on-managed-devices---677150--"></a>Anzeigen aller Aktionen auf verwalteten Geräten <!--677150-->
Ein neuer Bericht über __Geräteaktionen__ zeigt, wer Remoteaktionen wie das Zurücksetzen auf Werkseinstellungen auf Geräten ausgeführt hat sowie den Status dieser Aktion. Weitere Informationen finden Sie unter [Was ist die Geräteverwaltung?](https://docs.microsoft.com/intune-azure/manage-devices/what-is)

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Nicht verwaltete Geräte können auf zugewiesene Apps zugreifen <!--664691-->
Als Teil der Designänderungen auf der Unternehmensportal-Website können iOS- und Android-Benutzer Apps installieren, die ihnen als „Verfügbar ohne Registrierung“ auf Ihren nicht verwalteten Geräten zugewiesen sind. Benutzer können sich mit ihren Intune-Anmeldeinformationen auf der Unternehmensportal-Website anmelden und die Liste der ihnen zugewiesenen Apps anzeigen. Die App-Pakete der Apps des Typs „Verfügbar ohne Registrierung“ werden zum Download über die Unternehmensportal-Website verfügbar gemacht. Apps, für die die Registrierung für die Installation erforderlich ist, sind durch diese Änderung nicht betroffen, da Benutzer aufgefordert werden, ihr Gerät zu registrieren, wenn sie diese Apps installieren möchten.

### <a name="custom-app-categories---748805--"></a>Benutzerdefinierte App-Kategorien <!--748805-->
Sie können jetzt Kategorien für in Intune hinzugefügte Apps erstellen, bearbeiten und zuweisen. Zurzeit können Kategorien nur auf Englisch angegeben werden.
Weitere Informationen finden Sie unter [How to add an app to Intune (Hinzufügen einer App zu Intune)](/intune-azure/manage-apps/add-apps).

### <a name="display-device-categories---814654--"></a>Anzeigen von Gerätekategoriern <!--814654-->
Sie können nun die Gerätekategorie als Spalte in der Geräteliste anzeigen. Sie können die Kategorie auch im Abschnitt „Eigenschaften“ des Blatts „Geräteeigenschaften“ bearbeiten. Weitere Informationen finden Sie unter [How to add an app to Intune (Hinzufügen einer App zu Intune)](/intune-azure/manage-apps/add-apps).

### <a name="configure-windows-update-for-business-settings---776716--"></a>Konfigurieren von Einstellungen für Windows Update for Business <!--776716-->

Windows als Dienst ist die neue Methode zur Bereitstellung von Updates für Windows 10. Ab Windows 10 enthalten neue Funktions- und Qualitätsupdates die Inhalte aller früheren Updates. Das bedeutet, dass Ihre Windows 10-Geräte nach der Installation des neuesten Updates vollständig auf dem neuesten Stand sind. Im Gegensatz zu früheren Versionen von Windows müssen Sie nun anstelle eines Teilupdates das gesamte Update installieren.

Mithilfe von Windows Update for Business können Sie die Updateverwaltung vereinfachen, sodass Sie für Gruppen von Geräten keine einzelnen Updates genehmigen müssen. Sie können weiterhin eine Updaterolloutstrategie konfigurieren, um das Risiko in Ihren Umgebungen zu managen und sicherzustellen, dass Updates zur richtigen Zeit installiert werden. Mit Microsoft Intune können Sie Updateeinstellungen auf Geräten konfigurieren und die Updateinstallation zurückstellen. Intune speichert nur die Updaterichtlinienzuweisung, nicht die Updates. Geräte greifen direkt auf Windows Update zu, um die Updates zu beziehen. Intune dient zum Konfigurieren und Verwalten der **Windows 10-Updateringe**. Ein Updatering enthält eine Reihe von Einstellungen, die festlegen, wann und wie Updates für Windows 10 installiert werden. Ausführlichere Informationen finden Sie unter [Konfigurieren von Einstellungen für Windows Update for Business](/intune-azure/configure-devices/how-to-configure-windows-update-for-business).

## <a name="january-2017"></a>Januar 2017

### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--"></a>Zuweisen von Branchen-Apps unabhängig vom Registrierungsstatus von Geräten <!--748823-->
Sie können Benutzern jetzt Branchen-Apps aus dem Store zuweisen, unabhängig davon, ob die Benutzergeräte bei Intune registriert sind oder nicht. Wenn ein Benutzergerät nicht bei Intune registriert ist, muss der Benutzer die App über die Unternehmensportal-Website statt über die Unternehmensportal-App installieren. Siehe [Was ist die App-Verwaltung?](/intune-azure/manage-apps/what-is-app-management).

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Lösen von Problemen, wenn iOS-Geräte inaktiv sind oder die Verwaltungskonsole nicht mit ihnen kommunizieren kann
Wenn Geräte von Benutzern keinen Kontakt mehr mit Intune haben, können Sie neue Schritte zur Problembehandlung bereitstellen, damit sie erneuten Zugriff auf Unternehmensressourcen gewinnen können. Weitere Informationen finden Sie unter [Geräte sind inaktiv oder die Verwaltungskonsole kann nicht mit ihnen kommunizieren](/intune-azure/enroll-devices/troubleshoot-device-enrollment#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="december-2016-initial-release"></a>Dezember 2016 (erste Version)

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integration der Telekommunikationsausgaben in der öffentlichen Vorschau des Azure-Portals<!--747605-->
Aktuell beginnt die Vorschau der Integration mit TEM-Diensten (Telecom Expense Management) von Drittanbietern im Azure-Portal. Mit Intune können Sie Beschränkungen für das Datenroaming im In- und Ausland erzwingen. Diese Integrationen starten mit [Saaswedo](http://www.saaswedo.com). Wenn Sie dieses Feature in Ihrem Testmandanten aktivieren möchten, [wenden Sie sich bitte an den Microsoft-Support](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

- Bereitstellen und Verwalten von Apps aus einem Store auf iOS-, Android- und Windows-Geräten
- Bereitstellen und Verwalten von branchenspezifischen Apps auf iOS-, Android- und Windows-Geräten
- Bereitstellen und Verwalten von per Volumenlizenz erworbenen Apps auf iOS- und Windows-Geräten
- Bereitstellen und Verwalten von Web-Apps auf Android-, iOS- und Windows-Geräten
- In iOS verwaltete App-Konfigurationsprofile
- Konfigurieren von App-Schutzrichtlinien und Bereitstellen von branchenspezifischen Apps auf Geräten, die nicht in Intune registriert sind
- VPN-Profile, VPN pro App, WLAN, E-Mail und Zertifikatprofile
- Konformitätsrichtlinien
- Bedingter Zugriff für Azure AD
- Bedingter Zugriff auf lokales Exchange
- Geräteregistrierung
- Rollenbasierte Zugriffssteuerung

## <a name="deprecated-features-in-the-azure-portal"></a>Veraltete Features im Azure-Portal

### <a name="support-for-row-by-row-review-of-hardware-identifiers"></a>Unterstützung für die zeilenweise Überprüfung von Hardware-IDs
Das Azure-Portal unterstützt keine zeilenweise Überprüfung von Hardware-IDs für IMEI-Nummern und Apple-Seriennummern. In der klassischen Intune-Konsole können Sie Informationen aus einer durch Trennzeichen getrennten Datei (CSV) importieren und die vorhandenen Daten für einzelne Hardware-IDs überschreiben. Das Azure-Portal bietet eine optimierte Option, durch die automatisch die Daten für alle Hardware-IDs überschrieben oder neue Daten für vorhandene IDs ignoriert werden.

#### <a name="how-this-affects-you"></a>Auswirkungen für Sie
Sie können im Azure-Portal nicht zeilenweise entscheiden, welche IMEI-Geräte (International Mobile Equipment Identity) aktualisiert werden sollen. In der klassische Intune-Konsole wird diese Funktion weiterhin unterstützt.

#### <a name="how-to-get-ready-for-this-change"></a>Vorbereitungen für diese Änderung
Wir teilen Ihnen diese Informationen im Voraus mit, damit Sie Ihre Support-Administratoren über diese Änderung informieren können, sofern diese Änderung Sie betrifft. Diese Änderung tritt mit dem Umstieg auf das Azure-Portal in Kraft, der für die erste Hälfte des Jahres 2017 vorgesehen ist.


### <a name="support-for-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Unterstützung für Standardprofile für Unternehmensgeräteregistrierungen in Apple DEP
Das Azure-Portal unterstützt nicht das Standardprofil für Unternehmensgeräteregistrierungen für Geräteseriennummern in Apple DEP (Device Enrollment Programm). Diese Funktion, die in der klassischen Intune-Konsole zur Verfügung steht, wird nicht fortgeführt, damit nicht versehentlich Profile zugewiesen werden. Im Azure-Portal wird Seriennummern, die aus einem Apple DEP-Konto synchronisiert werden, zunächst keine Profil für die Unternehmensgeräteregistrierung zugewiesen.

#### <a name="how-this-affects-you"></a>Auswirkungen für Sie
Sie können im Azure-Portal keine Standardprofilrichtlinie für alle Apple-Geräte festlegen. In der klassische Intune-Konsole wird diese Funktion weiterhin unterstützt.

#### <a name="how-to-get-ready-for-this-change"></a>Vorbereitungen für diese Änderung
Wir teilen Ihnen diese Informationen im Voraus mit, damit Sie Ihre Support-Administratoren über diese Änderung informieren können, sofern diese Änderung Sie betrifft. Dies tritt mit dem Umstieg auf das Azure-Portal in Kraft, der für die erste Hälfte des Jahres 2017 vorgesehen ist.

