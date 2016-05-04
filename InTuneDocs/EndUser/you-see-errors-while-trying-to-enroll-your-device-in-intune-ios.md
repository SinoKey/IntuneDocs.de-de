Titel: finden Sie unter Fehler beim Versuch, Ihr Gerät in Intune registrieren
MS.Custom: Na
MS.Reviewer: Na
MS.Service: Microsoft Intune
MS.Suite: Na
MS.tgt_pltfrm: Na
MS.topic: Artikel
MS.AssetId: 
Autor: Staciebarker
Roboter: Noindex

# Fehler beim Versuch, Ihr Gerät in Intune registrieren angezeigt

Die folgende Tabelle enthält Fehler, die beim Registrieren von Geräten in Intune angezeigt werden kann.

|Fehlermeldung|Problem|Auflösung für den IT-Administrator über diesen Fehler<br /><br />Hinweis für IT-Administratoren nur: Diese Lösungen gelten auch für System Center 2012 R2 Configuration Manager|
|-----------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|DeviceCapReached|Sie haben zu viele mobile Geräte, die bereits registriert.|Der Benutzer muss eine seiner entfernen, oder ihr derzeit mobile Geräte über das Unternehmensportal registriert wurden vor der Registrierung von einer anderen.|
|APNSCertificateNotValid|Es ist ein Problem mit dem Zertifikat, das Ihr mobile Gerät zur Kommunikation mit Ihrem Unternehmensnetzwerk ermöglicht.<br /><br />Wenden Sie sich an Ihre IT-Administratoren und mitteilen, dass die Meldung **APNSCertificateNotValid** bei dem Versuch, Ihr mobile Gerät zu registrieren auszuführen, und teilen sie die Auflösung in dieser Tabelle finden Sie unter.|Über den Apple Push Notification Service (APNS) ist der Zugriff auf registrierte iOS-Geräte möglich. Wenn die Schritte zum Abrufen eines APNS-Zertifikats nicht ausgeführt wurden oder das APNS-Zertifikat ist abgelaufen, Anmeldeversuchen schlägt fehl, und diese Meldung wird angezeigt.<br /><br />Lesen Sie den Abschnitt "Vorbereiten des mobilen iOS-Geräte mit Microsoft Intune verwalten" im [ios- und Mac-Verwaltung mit Microsoft Intune einrichten](set-up-ios-and-mac-management-with-microsoft-intune.md).|
|AccountNotOnboarded|Es ist ein Problem mit dem Zertifikat, das Ihr mobile Gerät zur Kommunikation mit Ihrem Unternehmensnetzwerk ermöglicht.<br /><br />Wenden Sie sich an Ihre IT-Administratoren und mitteilen, dass die Meldung **APNSNotOnboarded** bei dem Versuch, Ihr mobile Gerät zu registrieren auszuführen, und teilen sie die Auflösung in dieser Tabelle finden Sie unter.|Über den Apple Push Notification Service (APNS) ist der Zugriff auf registrierte iOS-Geräte möglich. Wenn die Schritte zum Abrufen eines APNS-Zertifikats nicht ausgeführt wurden oder das APNS-Zertifikat ist abgelaufen, Anmeldeversuchen schlägt fehl, und diese Meldung wird angezeigt.<br /><br />Lesen Sie den Abschnitt "Vorbereiten des mobilen iOS-Geräte mit Microsoft Intune verwalten" im [ios- und Mac-Verwaltung mit Microsoft Intune einrichten](set-up-ios-and-mac-management-with-microsoft-intune.md).|
|DeviceTypeNotSupported|Sie haben möglicherweise versucht, mit einem nicht-iOS-Gerät zu registrieren. Der Typ des mobilen Geräts, den Sie registrieren möchten, wird nicht unterstützt.<br /><br />Stellen Sie sicher, dass Ihr Gerät iOS Version 7.1 oder höher ausgeführt wird.<br /><br />Wenden Sie sich an Ihre IT-Administratoren und mitteilen, dass die Meldung **DeviceTypeNotSupported** bei dem Versuch, Ihr mobile Gerät zu registrieren auszuführen, und teilen sie die Auflösung in dieser Tabelle finden Sie unter.|Stellen Sie sicher, dass Ihre Benutzer Gerät iOS Version 7.1 oder höher ausgeführt wird.|
|UserLicenseTypeInvalid|Sie können nicht Ihr mobile Gerät registrieren, da Ihr Benutzerkonto noch nicht Mitglied einer erforderlichen Benutzergruppe ist.<br /><br />Wenden Sie sich an Ihre IT-Administratoren und mitteilen, dass die Meldung **UserLicenseTypeInvalid** bei dem Versuch, Ihr mobile Gerät zu registrieren auszuführen, und teilen sie die Auflösung in dieser Tabelle finden Sie unter.|Bevor Benutzer ihre Geräte registrieren können, müssen sie Mitglied der Gruppe der richtigen Benutzer sein. Diese Meldung bedeutet, dass sie den falschen Lizenztyp für die festgelegte Autorität. Zum Beispiel wenn [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)] als die Autorität für die Verwaltung mobiler Geräte festgelegt wurde und eine Lizenz für System Center 2012 R2 Configuration Manager verwenden, wird dieser Fehler.<br /><br />Überprüfen Sie die folgenden Informationen ein:<br /><br />Die Schritte zum Hinzufügen von Benutzern und Gruppen im Abschnitt "Vorbereiten der Verwaltung von mobilen iOS-Geräte mit Microsoft Intune" in [ios- und Mac-Verwaltung mit Microsoft Intune einrichten](set-up-ios-and-mac-management-with-microsoft-intune.md).<br /><br />"Schritt 2: Benutzer zu Intune hinzufügen" und "Schritt 3: Erstellen von Gruppen zum Organisieren von Benutzern und Geräten" in [Erste Schritte mit einer 30-Tage-Testversion von Microsoft Intune](Get-started-with-a-30-day-trial-of-microsoft-intune.md).<br /><br />"Schritt 5: Erstellen von Gruppen zum Organisieren von Benutzern und Geräten" in [Einstieg in ein bezahltes Abonnement von Microsoft Intune](get-started-with-a-paid-subscription-to-microsoft-intune.md).|
|MdmAuthorityNotDefined|Der IT-Administrator muss können Sie konfigurieren, dass mobile Geräte in Ihrem Unternehmen verwaltet werden.<br /><br />Wenden Sie sich an Ihre IT-Administratoren und mitteilen, dass die Meldung **MdmAuthorityNotDefined** bei dem Versuch, Ihr mobile Gerät zu registrieren auszuführen, und teilen sie die Auflösung in dieser Tabelle finden Sie unter.|Die Autorität nicht festgelegt wurde [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)].<br /><br />Lesen Sie Artikel #1 im Abschnitt "Schritt 6: Registrieren von mobilen Geräten und Installieren einer app" in [Erste Schritte mit einer 30-Tage-Testversion von Microsoft Intune](Get-started-with-a-30-day-trial-of-microsoft-intune.md).|

### Weitere Informationen:
[Verwenden IOS- oder Mac OS X-Geräte mit Intune] (using-your-ios-or-mac-os-x Gerät mit intune.md)

<!--HONumber=Mar16_HO3-->


