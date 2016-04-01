---
Titel: Vorteile von Intune App-SDK
MS.Custom: Na
MS.Reviewer: Na
MS.Suite: Na
MS.tgt_pltfrm: Na
MS.topic: Artikel
MS.AssetId: cd9f05e7-26e6-45e0-8d38-67d8232b1cae
Autor: Msmbaldwin
---
# Vorteile der Intune-App-SDK
Das Intune App Software Development Kit (SDK) ist für iOS- und Android-Plattformen erhältlich und ermöglicht Verwaltungsfunktionen für mobile Anwendungen mit Microsoft Intune. Darüber hinaus bemühen wir uns, die Menge der Codeänderungen für Entwickler zu reduzieren. Sie werden feststellen, dass Sie die meisten SDK-Funktionen aktivieren können, ohne das Verhalten Ihrer App ändern zu müssen. Um die Anwendung für Endbenutzer und IT-Administratoren zu verbessern, können Sie unsere APIs verwenden und so das App-Verhalten für Funktionen anpassen, die Ihre Mitwirkung erfordern. 
Nachdem Sie Ihre App aktiviert haben, können IT-Administratoren Richtlinien für von Intune verwaltete Apps bereitstellen und die Vorteile dieser Features nutzen, um die Unternehmensdaten zu schützen.

## Regular Features

### Steuern der Möglichkeit von Benutzern, Unternehmensdaten zu verschieben
IT-Administratoren können die Verlagerung von Dateien mit Unternehmensdaten in von Intune verwalteten Apps steuern. So kann beispielsweise eine Richtlinie bereitgestellt werden, mit verhindert wird, dass Unternehmensdaten mit Datensicherungs-Apps in der Cloud gespeichert werden.

### Konfigurieren von Einschränkungen für die Zwischenablage
IT-Administratoren können in von Intune verwalteten Apps das Verhalten der Zwischenablage konfigurieren. So können sie beispielsweise eine Richtlinie implementieren, die dafür sorgt, dass Endbenutzer nicht in der Lage sind, die Zwischenablage zu verwenden, um Daten aus von Intune verwalteten Apps auszuschneiden/zu kopieren und in eine nicht verwaltete App zu kopieren.

### Konfigurieren von Einschränkungen für Bildschirmaufnahmen
IT-Administratoren könne verhindern, dass Benutzer eine Bildschirmaufnahme erstellen, wenn eine von Intune verwaltete App angezeigt wird. Mit dieser Einschränkung werden die Erfassung und Weitergabe von vertraulichen Unternehmensinhalten verhindert. Dieses Feature steht nur für Android-Geräte zur Verfügung.

### Erzwingen der Verschlüsselung von gespeicherten Daten
IT-Administratoren können mit einer Richtlinie erzwingen, dass auf dem Gerät gespeicherte Daten verschlüsselt werden.

### Remotezurücksetzung von Unternehmensdaten
IT-Administratoren können Unternehmensdaten von einem mit Intune verwalteten Gerät löschen, wenn die Registrierung des Geräts in Microsoft Intune aufgehoben wurde. Dieses Feature basiert auf der Identität, und es werden nur Dateien gelöscht, die mit der Unternehmensidentität des Benutzers verbunden sind. Hierfür ist die Mitwirkung der App erforderlich. Die App kann die Identität, für die die Zurücksetzung erfolgen soll, basierend auf den Benutzereinstellungen festlegen. Fehlen solche spezifischen Benutzereinstellungen in der App, wird gemäß dem Standardverhalten vorgegangen, d. h. das Anwendungsverzeichnis wird gelöscht, und der Benutzer wird informiert, dass der Zugriff auf Unternehmensressourcen entfernt wurde.

### Erzwingen der Verwendung eines verwalteten Browsers
IT-Administratoren können die Verwendung eines verwalteten Browsers („Managed Browser“) beim Öffnen von Links in von Intune verwalteten Apps erzwingen. Die Verwendung von von Microsoft Intune verwalteten Browsern trägt zur Sicherstellung bei, dass Links in E-Mails (die sich in einem von Intune verwalteten Mailclient befinden) innerhalb der Domäne der von Intune verwalteten Apps verbleiben.

### Erzwingen einer PIN-Richtlinie
IT-Administratoren können eine PIN-Richtlinie beim Starten einer von Intune verwalteten App erzwingen. Diese Richtlinie trägt zur Sicherstellung bei, dass es sich bei den Endbenutzern, die ihre Geräte bei Microsoft Intune registriert haben, um die gleichen Personen handelt, die die Apps starten. Wenn Benutzer ihre PIN konfigurieren, verwendet Intune App-SDK, Azure Active Directory die Anmeldeinformationen von Endbenutzern für die Anmeldeinformationen des Geräts Registrierung überprüfen

### Erzwingen, dass Benutzer vor dem Starten von Apps Anmeldeinformationen eingeben
IT-Administratoren können erzwingen, dass Benutzer ihre Anmeldeinformationen eingeben, bevor sie eine von Intune verwaltete App starten können. Das Intune App SDK verwendet Azure Active Directory für die Bereitstellung von einmaligem Anmelden (SSO), damit die einmal eingegebenen Anmeldeinformationen auch für nachfolgende Anmeldungen gelten. Wir unterstützen auch die Authentifizierung mit der Identität [Verbund mit Azure Active Directory](https://msdn.microsoft.com/en-us/library/azure/jj679342.aspx).

### Überprüfen der Geräteintegrität und -compliance
IT-Administratoren können die Integrität des Geräts und dessen Compliance mit den Unternehmensrichtlinien abgleichen, bevor Endbenutzer auf von Intune verwaltete Apps zugreifen. Auf der iOS-Plattform überprüft diese Richtlinie, ob es sich um ein Gerät handelt, auf das ein Jailbreak angewendet wurde. Auf der Android-Plattform überprüft diese Richtlinie, ob es sich um ein Gerät handelt, das gerootet wurde.

## Features in der Preview
Das Microsoft Intune App SDK enthält einige Features, die sich noch in der "Preview" befinden. Sie können mit der Integration von Preview-APIs beginnen, jedoch nur zu Testzwecken. Beachten Sie, dass mit diesen Previews vorhandene Szenarien ergänzen und nicht ersetzen.

### Microsoft Intune App SDK – Unterstützung für mehrere Identitäten
Die Unterstützung von mehreren Identitäten (Multi-Identity Support) ist ein Feature, das die Koexistenz von per Richtlinie verwalteten Geschäftskonten und nicht verwalteten Privatkonten in einer App gestattet.

### Beispiel für ein Szenario mit mehreren Identitäten
Viele Benutzer konfigurieren in der Outlook-App für iOS und Android sowohl Firmen-E-Mail-Konten als auch private E-Mail-Konten. Wenn ein Benutzer auf Daten im Firmenkonto zugreift, muss der IT-Administrator sicher sein, dass die MAM-Richtlinienverwaltung angewendet wird. Wenn ein Benutzer jedoch auf ein privates E-Mail-Konto zugreift, sollten sich diese Daten außerhalb der Kontrolle des IT-Administrators befinden. In Microsoft Intune wird dies erreicht, indem die Verwaltungsrichtlinie nur auf das Unternehmenskonto in der Anwendung abzielt. Das Feature für mehrere Identitäten hilft Ihnen, das Datenschutzproblem zu lösen, mit dem sich Organisation auseinandersetzen müssen, die Geräte und Apps mit privaten und Geschäftskonten unterstützen.

### Unterstützung für mehrere Identitäten
Preview-APIs ermöglichen die Angabe eines UPNs (User Principal Name) für bestimmte Datenvorgänge wie Kopieren in und Auslesen aus der Zwischenablage und andere Dateivorgänge. Das Microsoft Intune App SDK verwendet den UPN, der zum Registrieren des Geräts bei Microsoft Intune verwendet wurde. Wenn sich die UPNs entsprechen, wird der Aufruf als ein Aufruf von Unternehmensdaten behandelt, und die Daten werden geschützt; wenn sich die UPNs nicht entsprechen, wird der Aufruf als Aufruf von privaten Daten behandelt, und die Daten werden nicht geschützt.

### App-Verwaltung ohne Geräteregistrierung
Viele Benutzer von privaten Geräten möchten Unternehmensdaten anzeigen und verwenden können, ohne ihr privates Gerät bei einem MDM-Produkt (Mobile Device Management, Verwaltung von mobilen Geräten) registrieren zu müssen. Da die MDM-Registrierung eine globale Kontrolle des Geräts voraussetzt, sind viele Benutzer unsicher, ob sie diese globale Kontrolle über ihr privates Gerät an das Unternehmen übertragen können.

Dank der App-Verwaltung ohne Geräteregistrierung kann Microsoft Intune MAM-Richtlinien direkt in einer App bereitstellen, ohne den MDM-Kanal für diese Bereitstellung zu nutzen. Da kein MDM-Kanal benötigt wird, ist auch keine MDM-Registrierung erforderlich.



<!--HONumber=Mar16_HO1-->


