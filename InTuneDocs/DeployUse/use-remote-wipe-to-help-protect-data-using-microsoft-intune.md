---
# required metadata

title: Remotezurücksetzung zum Schützen von Daten | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8519e411-3d48-44eb-9b41-3e4fd6a93112

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Schützen von Daten durch vollständiges oder selektives Zurücksetzen mit Microsoft Intune
Genauso wie Geräte möchten oder müssen Sie mitunter auch Apps [außer Betrieb nehmen](retire-apps-using-microsoft-intune.md), die auf PCs und mobilen Geräten bereitgestellt sind. Dies ist z. B. der Fall, wenn sie nicht mehr benötigt werden. Außerdem möchten Sie u. U. auch Unternehmensdaten von dem Gerät entfernen. Zu diesem Zweck enthält Intune Funktionen zum vollständigen oder selektiven Zurücksetzen. Da auf mobilen Geräten sensible Unternehmensdaten gespeichert sein können und die Geräte mitunter Zugriff auf zahlreiche Unternehmensressourcen bieten, haben Sie über die Intune die Möglichkeit, bei Verlust oder Diebstahl eines Geräts einen Remotebefehl zum Zurücksetzen des Geräts zu erteilen. Für private Geräte, die in Intune registriert sind, können die Benutzer über Intune einen Remotebefehl zum Zurücksetzen des Geräts erteilen.

  > [!NOTE]
  > In diesem Thema wird das Zurücksetzen von Geräten behandelt, die von Intune verwaltet werden. Sie können auch das [Azure-Vorschauportal](https://portal.azure.com) zum [Entfernen von Unternehmensdaten aus Apps](wipe-managed-company-app-data-with-microsoft-intune.md) verwenden.

## Vollständiges Zurücksetzen


**Vollständiges Zurücksetzen** setzt ein Gerät auf die werkseitigen Standardeinstellungen zurück, wobei alle Unternehmens- und Benutzerdaten und -einstellungen entfernt werden. Das Gerät wird aus Intune entfernt. Das vollständige Zurücksetzen ist hilfreich, wenn Sie ein Gerät vor der Übergabe an einen neuen Benutzer zurücksetzen möchten oder wenn ein Gerät verloren oder gestohlen wurde.  Überlegen Sie sich genau, ob Sie ein Gerät wirklich vollständig zurücksetzen möchten.

## Die Daten auf dem Gerät können anschließend nicht wiederhergestellt werden.

Selektives Zurücksetzen Beim **selektiven Zurücksetzen** werden die Unternehmensdaten und bei Bedarf auch die Daten für die Verwaltung mobiler Apps (MAM, Mobile App Management) vom Gerät entfernt. Außerdem werden Einstellungen und E-Mail-Profile entfernt. Die persönlichen Daten des Benutzers bleiben beim selektiven Zurücksetzen auf dem Gerät erhalten. Das Gerät wird aus Intune entfernt.

**In der folgenden Tabelle wird nach Plattform sortiert beschrieben, welche Daten bei einem selektiven Zurücksetzen entfernt werden und mit welchen Auswirkungen auf verbleibende Daten zu rechnen ist.**

|iOS|Datentyp|
|-------------|-------|
|iOS|Unternehmensanwendungen und zugehörige Daten, die von Intune installiert wurden. Apps werden deinstalliert.<br /><br />Daten von Unternehmens-Apps werden entfernt. App-Daten aus Microsoft-Anwendungen, die die Verwaltung von mobilen Anwendungen verwenden, werden entfernt.|
|Die App wird nicht entfernt.|Einstellungen|
|Konfigurationen, die von der Intune-Richtlinie festgelegt wurden, werden nicht mehr erzwungen, und Benutzer können die Einstellungen ändern.|Einstellungen für WLAN- und VPN-Profil|
|Entfernt|Zertifikatprofil-Einstellungen|
|Zertifikate wurden entfernt und gesperrt.|Verwaltungs-Agent|
|Das Verwaltungsprofil wird entfernt.|E-Mail|
|E-Mail-Profile, die über Intune bereitgestellt werden, werden entfernt und zwischengespeicherte E-Mails auf dem Gerät gelöscht.|Azure Active Directory (AAD)-Verbindung aufgehoben|
|AAD-Datensatz entfernt | Kontakte  Direkt aus der App mit dem nativen Adressbuch synchronisierte Kontakte werden entfernt. <br /> <br />Kontakte, die aus dem nativen Adressbuch mit einer anderen externen Quelle synchronisiert werden, können nicht zurückgesetzt werden.

**Derzeit wird nur die Outlook-App unterstützt.**

|Android|Datentyp|Android|
|-------------|-----------|------------------------|
|Android Samsung KNOX|Weblinks|Entfernt.|
|Entfernt|Nicht verwaltete Google Play-Apps|Apps und Daten bleiben installiert.|
|Apps und Daten bleiben installiert.|Nicht verwaltete Geschäftssparten-Apps|Apps und Daten bleiben installiert. Apps werden deinstalliert, und lokale App-Daten werden daher entfernt.|
|Es werden keine Daten außerhalb der App (SD-Karte usw.) entfernt.|Verwaltete Google Play-Apps App-Daten werden entfernt. App wird nicht entfernt.|Daten, die von der MAM-Verschlüsselung außerhalb der App (SD-Karte usw.) geschützt sind, bleiben verschlüsselt, werden aber nicht entfernt. App-Daten werden entfernt. App wird nicht entfernt.|
|Daten, die von der MAM-Verschlüsselung außerhalb der App (SD-Karte usw.) geschützt sind, bleiben verschlüsselt, werden aber nicht entfernt.|Verwaltete Geschäftssparten-Apps App-Daten werden entfernt. App wird nicht entfernt.|Daten, die von der MAM-Verschlüsselung außerhalb der App (SD-Karte usw.) geschützt sind, bleiben verschlüsselt, werden aber nicht entfernt. App-Daten werden entfernt. App wird nicht entfernt.|
|Daten, die von der MAM-Verschlüsselung außerhalb der App (SD-Karte usw.) geschützt sind, bleiben verschlüsselt, werden aber nicht entfernt.|Einstellungen|Konfigurationen, die von der Intune-Richtlinie festgelegt wurden, werden nicht mehr erzwungen, und Benutzer können die Einstellungen ändern.|
|Konfigurationen, die von der Intune-Richtlinie festgelegt wurden, werden nicht mehr erzwungen, und Benutzer können die Einstellungen ändern.|Einstellungen für WLAN- und VPN-Profil|Entfernt|
|Entfernt|Zertifikatprofil-Einstellungen|Zertifikate gesperrt, aber nicht entfernt.|
|Zertifikate wurden entfernt und gesperrt.|Verwaltungs-Agent|Die Berechtigung „Geräteadministrator“ wird gesperrt.|
|Die Berechtigung „Geräteadministrator“ wird gesperrt.|E-Mail|E-Mails, die über die Microsoft Outlook-App für Android empfangen wurden, werden entfernt.|
|E-Mail-Profile, die über Intune bereitgestellt werden, werden entfernt und zwischengespeicherte E-Mails auf dem Gerät gelöscht.|Azure Active Directory (AAD)-Verbindung aufgehoben|AAD-Datensatz entfernt|
|AAD-Datensatz entfernt | Kontakte  Direkt aus der App mit dem nativen Adressbuch synchronisierte Kontakte werden entfernt. <br /> <br />Kontakte, die aus dem nativen Adressbuch mit einer anderen externen Quelle synchronisiert werden, können nicht zurückgesetzt werden.|Derzeit wird nur die Outlook-App unterstützt.  Direkt aus der App mit dem nativen Adressbuch synchronisierte Kontakte werden entfernt. <br /> <br />Kontakte, die aus dem nativen Adressbuch mit einer anderen externen Quelle synchronisiert werden, können nicht zurückgesetzt werden.

**Derzeit wird nur die Outlook-App unterstützt.**

|Windows|Datentyp|Windows 8.1 (MDM) und Windows RT 8.1|Windows RT|Windows Phone 8 und Windows Phone 8.1|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Windows 10|Unternehmensanwendungen und zugehörige Daten, die von Intune installiert wurden.|Bei Dateien, die durch ein EFS geschützt sind, wird der Schlüssel gesperrt, und der Benutzer kann die Dateien nicht mehr öffnen.|Unternehmensanwendungen werden nicht entfernt. Ursprünglich über das Unternehmensportal installierte Anwendungen werden deinstalliert.|Daten von Unternehmens-Apps werden entfernt.|
|Anwendungen werden deinstalliert, und Sideload-Schlüssel werden entfernt.|Einstellungen|Konfigurationen, die von der Intune-Richtlinie festgelegt wurden, werden nicht mehr erzwungen, und Benutzer können die Einstellungen ändern.|Konfigurationen, die von der Intune-Richtlinie festgelegt wurden, werden nicht mehr erzwungen, und Benutzer können die Einstellungen ändern.|Konfigurationen, die von der Intune-Richtlinie festgelegt wurden, werden nicht mehr erzwungen, und Benutzer können die Einstellungen ändern.|
|Konfigurationen, die von der Intune-Richtlinie festgelegt wurden, werden nicht mehr erzwungen, und Benutzer können die Einstellungen ändern.|Einstellungen für WLAN- und VPN-Profil|Entfernt|Entfernt|Nicht unterstützt|
|Entfernt|Zertifikatprofil-Einstellungen|Zertifikate wurden entfernt und gesperrt.|Zertifikate wurden entfernt und gesperrt.|Nicht unterstützt|
|Zertifikate wurden entfernt und gesperrt.|E-Mail|Entfernt EFS-aktivierte E-Mails, darunter die E-Mail-App für Windows-E-Mails und -Anlagen.|Nicht unterstützt|E-Mail-Profile, die über Intune bereitgestellt werden, werden entfernt und zwischengespeicherte E-Mails auf dem Gerät gelöscht. Entfernt EFS-aktivierte E-Mails, darunter die E-Mail-App für Windows-E-Mails und -Anlagen.|
|Entfernt E-Mail-Konten, die von Intune bereitgestellt wurden.|Azure Active Directory (AAD)-Verbindung aufgehoben|Nein|Nein|AAD-Datensatz entfernt Nicht zutreffend.|

### Windows 10 unterstützt kein selektives Zurücksetzen für Geräte, die in Azure Active Directory eingebunden wurden.

1.  Remotezurücksetzen eines Geräts über die Intune-Administratorkonsole Wählen Sie Geräte aus, die zurückgesetzt werden sollen.

    -   **Sie können diese nach Benutzer oder Gerät suchen.**

        1.  Nach Benutzer:

        2.  Klicken Sie in der [Intune-Administratorkonsole](https://manage.microsoft.com/) auf **Gruppen** &gt; **Alle Benutzer**. Klicken Sie auf den Namen des Benutzers, dessen mobiles Gerät Sie zurücksetzen möchten.

        3.  Klicken Sie auf **Eigenschaften anzeigen**. Klicken Sie auf der Seite **Eigenschaften** des Benutzers auf **Geräte** und dann auf den Namen des mobilen Geräts, das Sie zurücksetzen möchten.

    -   **Halten Sie die STRG-Taste gedrückt, und klicken Sie, um mehrere Geräte auszuwählen.**

        1.  Nach Gerät:

      ![Klicken Sie in der [Intune-Administratorkonsole](https://manage.microsoft.com/) auf **Gruppen** &gt; **Alle mobilen Geräte**.](../media/dev-sa-wipe.png)

        2.  Starten eines Vorgangs zum Abkoppeln oder Zurücksetzen Klicken Sie auf **Geräte** und dann auf den Namen des mobilen Geräts, das Sie zurücksetzen möchten.

2.  Halten Sie die STRG-Taste gedrückt, und klicken Sie, um mehrere Geräte auszuwählen.

3.  Klicken Sie auf **Abkoppeln/Zurücksetzen**.

    -   Durch eine Meldung werden Sie aufgefordert, zu bestätigen, ob Sie das Gerät abkoppeln möchten.

    -   Klicken Sie zum Ausführen einer **selektiven Zurücksetzung**, bei der nur unternehmenseigene Apps und Daten entfernt werden, auf **Ja**. Wählen Sie zum Ausführen einer **vollständigen Zurücksetzung**, bei der alle Apps und Daten gelöscht werden und das Gerät auf die werkseitigen Standardeinstellungen zurückgesetzt wird, auf **Gerät vor dem Abkoppeln zurücksetzen**. Diese Aktion gilt für alle Plattformen außer Windows 8.1.

Daten, die durch ein vollständiges Zurücksetzen entfernt wurden, können nicht wiederhergestellt werden.

## Das Verteilen des Zurücksetzens über alle Gerätetypen dauert höchstens 15 Minuten.
Zurücksetzen EFS-aktivierter Inhalte Das selektive Zurücksetzen von EFS-verschlüsselten Inhalten wird von Windows 8.1 und Windows RT 8.1 unterstützt.

-   Folgendes gilt für das selektive Zurücksetzen von EFS-aktivierten Inhalten: Nur Apps und Daten, die mit dem verschlüsselnden Dateisystem (EFS, Encrypting File System) geschützt sind und die die gleiche Internetdomäne wie das Intune-Konto verwenden, werden selektiv zurückgesetzt.

-   Weitere Informationen finden Sie unter [Windows Selective Wipe for Device Data Management (Selektives Zurücksetzen bei der Gerätedatenverwaltung in Windows)](http://technet.microsoft.com/library/dn486874.aspx).

-   Wenn Änderungen an der EFS zugeordneten Domäne vorgenommen werden, können die Änderungen bis zu 48 Stunden dauern, bevor Apps und Daten selektiv zurückgesetzt werden können, die die neue Domäne verwenden.

Jede bei Intune registrierte Domäne wird zurückgesetzt.

-   Folgende Daten und Apps werden derzeit vom selektiven Zurücksetzen mit EFS unterstützt:

-   E-Mail-App für Windows

-   Arbeitsordner Von EFS verschlüsselte Dateien und Ordner

-   Weitere Informationen finden Sie unter [Vorgehensweisen bei Verwendung des verschlüsselnden Dateisystems](http://support.microsoft.com/kb/223316).  Wenn Ihr Unternehmen seine Identität in Active Directory verwaltet, muss das Tool Verzeichnissynchronisierung (DirSync) verwendet werden, um Informationen in AAD zu synchronisieren, damit das selektive EFS-Zurücksetzen ordnungsgemäß funktioniert.

## Weitere Informationen zu DirSync finden Sie unter [Verzeichnissynchronisierungsszenario](http://technet.microsoft.com/library/dn441212.aspx) in der Azure Active Directory-Dokumentation.
Überwachen von Abkopplungs-, Zurücksetzungs- und Löschaktionen

1.  So erhalten Sie einen Bericht zu Geräten, die abgekoppelt, zurückgesetzt oder gelöscht wurde, und zum Zuständigen für die Aktion

2.  Klicken Sie in der [Intune-Administratorkonsole](https://manage.microsoft.com/) auf **Berichte** &gt; **Geräteverlaufsberichte**.


### Geben Sie ein Start- und Enddatum für den Bericht ein, und klicken Sie dann auf **Bericht anzeigen**.
[Weitere Informationen:](retire-devices-from-microsoft-intune-management.md)

[Abkoppeln von Geräten](http://technet.microsoft.com/library/dn486874.aspx)


<!--HONumber=May16_HO2-->


