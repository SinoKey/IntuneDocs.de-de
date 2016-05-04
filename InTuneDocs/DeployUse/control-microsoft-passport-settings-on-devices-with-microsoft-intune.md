---
title: Steuern von Microsoft Passport-Einstellungen auf Geräten mit Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 402bc5a1-ada3-4c4c-a0de-292d026b4444
author: robstackmsft
---
# Steuern von Microsoft Passport-Einstellungen auf Geräten mit Microsoft Intune
Microsoft Intune können Sie die Integration in Microsoft Passport for Work eine alternative Methode anmelden, die Active Directory oder Azure Active Directory-Konto verwendet ist, um ein Kennwort, Smartcard oder virtuelle Smartcard ersetzt werden.

Passport-Konto können Sie mithilfe einer **Benutzeraktion** Anmeldung, anstelle eines Kennworts. Eine Benutzeraktion kann eine einfache PIN, eine biometrische Authentifizierung wie Windows Hello oder ein externes Gerät sein, z. B. ein Fingerabdruckleser.

Intune integriert mit Passport for Work auf zwei Arten:

-   Mithilfe einer Gruppenrichtlinie Intune steuern, welche Benutzer Gesten können und können nicht für die Anmeldung.

-   Sie können Authentifizierungszertifikate im Passport for Work-Schlüsselspeicheranbieter (Key Storage Provider, KSP) speichern. Weitere Informationen finden Sie unter [ermöglichen den Zugriff auf Unternehmensressourcen mithilfe von zertifikatprofilen in Microsoft Intune](enable-access-to-company-resources-using-certificate-profiles-with-microsoft-intune.md).

## Um einen Passport-Richtlinie zu erstellen.

1.  In der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com), klicken Sie auf **Admin** & Gt; **Verwaltung mobiler Geräte** & Gt; **Windows** & Gt; **Passport for Work**.

2.  Wählen Sie die folgenden Werte, die für alle registrierten Windows 10 und Windows 10 Mobile Geräte gelten:

|Einstellung|Beschreibung|
    |-----------|---------------|
    |-   **Deaktivieren Passport for Work auf registrierten Geräten**<br />-   **Aktivieren Passport for Work auf registrierten Geräten**|Aktiviert oder deaktiviert die Verwendung von Passport für die Arbeit an alle registrierten Windows 10 und Windows 10 mobile Geräte. **Wichtig:** diese Richtlinie ist standardmäßig aktiviert und für alle Windows 10-Geräte angewendet werden, wenn sie registrieren.|
    |**Trusted Platform Module (TPM) verwenden**|Ein Trusted Platform Module-Chip bietet eine zusätzliche Sicherheitsebene für Daten.<br /><br />Wählen Sie einen der folgenden Werte aus:<br /><br />-   **Erforderliche** (Standard) – nur Geräte mit einem TPM zugegriffen werden kann Passport for Work bereitstellen können.<br />-   **Bevorzugte** -Geräten versucht zunächst, ein TPM zu verwenden. Wenn diese Option nicht verfügbar ist, können sie die Softwareverschlüsselung verwenden.|
    |**Mindestlänge für PIN erfordern**|Geben Sie die Mindestanzahl von Zeichen an, die für die Passport for Work-PIN erforderlich ist. Sie müssen mindestens 4 Zeichen verwenden (der Standardwert ist 6 Zeichen). ​|
    |**Maximale Länge für PIN erfordern**|Geben Sie die maximale Anzahl von Zeichen an, die für die Passport for Work-PIN zulässig ist. Sie können bis zu 127 Zeichen verwenden.|
    |**Kleinbuchstaben in PIN erfordern**|Gibt an, ob in der Passport for Work-PIN Kleinbuchstaben verwendet werden müssen. Wählen Sie aus:<br /><br />-   **Zugelassen** -Benutzer können Kleinbuchstaben in ihre PIN.<br />-   **Erforderliche** -Benutzer müssen über mindestens einen Kleinbuchstaben enthalten, ihre PIN.<br />-   **Nicht zulässig,** (Standard) - Benutzer müssen keine Kleinbuchstaben in ihre PIN verwenden.|
    |**Großbuchstaben in PIN erfordern**|Gibt an, ob in der Passport for Work-PIN Großbuchstaben verwendet werden müssen. Wählen Sie aus:<br /><br />-   **Zugelassen** -Benutzer können Großbuchstaben in ihre PIN.<br />-   **Erforderliche** -Benutzer müssen mindestens einen Großbuchstaben in ihre PIN einschließen.<br />-   **Nicht zulässig,** (Standard) - Benutzer müssen Großbuchstaben in ihre PIN nicht verwenden.|
    |**Sonderzeichen in PIN erforderlich**|Gibt die Verwendung von Sonderzeichen in der PIN an. Wählen Sie aus:<br /><br />Sonderzeichen enthalten: **! "# $ % & Amp;" () & #42; + , - . / : ; & Lt; = & Gt;? @ [\] ^ _ & #96; {& #124;} ~**.<br /><br />-   **Zugelassen** -Benutzer können Sonderzeichen in ihre PIN.<br />-   **Erforderliche** -Benutzer müssen mindestens ein Sonderzeichen in ihre PIN einschließen.<br />-   **Nicht zulässig,** (Standard) - Benutzer müssen die Sonderzeichen in ihre PIN (Dies ist auch das Verhalten, wenn die Einstellung nicht konfiguriert ist) nicht verwenden.|
    |**PIN-Ablauf (Tage)**|Gibt die Anzahl der Tage an, bevor die Geräte-PIN geändert werden muss. Die Standardeinstellung ist 41 Tage.|
    |**Beachten Sie die PIN-Verlauf**|Verwenden Sie diese Einstellung, um die Wiederverwendung von zuvor verwendete PINs einzuschränken. Standardmäßig können die letzten fünf PINs nicht erneut verwendet werden.|
    |**Biometrischen Authentifizierung zulassen**|Aktiviert die biometrische Authentifizierung, z. B. die Gesichtserkennung oder Fingerabdrücke, als Alternative zu einer PIN für Passport for Work. Benutzer müssen für den Fall dennoch eine PIN konfigurieren, dass die biometrische Authentifizierung fehlschlägt.<br /><br />Wenn auf festgelegt **Ja**, Passport for Work biometrischen Authentifizierung ermöglicht.  Wenn auf festgelegt **keine**, Passport for Work verhindert die biometrischen Authentifizierung (für alle Arten von Konten).|
    |**Verbessertes Antispoofing verwenden, sofern verfügbar**|Konfiguriert, ob das erweiterte Antispoofing auf Geräten verwendet wird, die diese Option unterstützen.<br /><br />Wenn auf festgelegt **Ja**, Windows, müssen alle Benutzer mit Anti-spoofing Gesichtszüge unterstützt.|
    |**Remote Passport verwenden**|Wenn diese Option, um festgelegt ist **Ja**, können Sie einen Remoteserver als tragbare Begleiter Gerät zum Desktopcomputer Authentifizierung dienen. Der Desktopcomputer muss Azure Active Directory angehören, und das Begleitgerät muss mit einer Passport for Work-PIN konfiguriert werden.|

3.  Wenn Sie fertig sind, klicken Sie auf **Speichern**.

## Weitere Informationen
Weitere Informationen zu Microsoft Passport, finden Sie unter der [Microsoft Passport-Handbuch](https://technet.microsoft.com/library/mt589441(v=vs.85).aspx) in der Dokumentation zu Windows 10.

### Siehe auch
[Schützen von Daten und Geräten mit Microsoft Intune](protect-data-and-devices-with-microsoft-intune.md)



<!--HONumber=Mar16_HO4-->


