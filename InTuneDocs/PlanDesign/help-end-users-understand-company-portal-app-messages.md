---
# required metadata

title: Grundlegendes zum Verständnis von Meldungen in der Unternehmensportal-App | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3df993aa-48c5-4799-b68d-c85fe4f7b02c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Grundlegendes zum Verständnis von Meldungen in der Unternehmensportal-App

Die folgenden Informationen gelten nur für Geräte mit Android 6.0 und höher. Während der Geräteregistrierung werden Endbenutzern zwei Meldungen angezeigt:

- Zulassen, dass das Unternehmensportal Telefonanrufe tätigt und verwaltet?
- Unternehmensportal den Zugriff auf Fotos, Medien und Dateien auf Ihrem Gerät erlauben?

In den folgenden Abschnitten finden Sie weitere Informationen zu diesen Meldungen und dazu, welche Informationen Sie den Endbenutzer mitteilen können.

## Zulassen, dass das Unternehmensportal Telefonanrufe tätigt und verwaltet?

### Meldungstext und Position auf der Oberfläche
Wenn Benutzer sich bei der Unternehmensportal-App anmelden, um Ihr Gerät erstmals zu registrieren, wird die Meldung **Zulassen, dass das Unternehmensportal Telefonanrufe tätigt und verwaltet?** angezeigt.

### Bedeutung der Meldung
Die Meldungen fordert Benutzer auf zu erlauben, dass die Telefonnummer und IMEI ihres Geräts an den Intune-Dienst gesendet und in der Verwaltungskonsole auf der Seite „Hardware“ angezeigt werden.

> [!NOTE]
> **Die Unternehmensportal-App tätigt oder verwaltet keine Telefonanrufe!** Der Meldungstext wird von Google gesteuert und kann nicht geändert werden.

Zum Anzeigen der Seite **Hardware** wechseln Sie zu **Gruppen** > **Alle mobilen Geräte** > **Geräte**. Wählen Sie das Gerät des Benutzers aus, und wechseln Sie zu **Eigenschaften anzeigen** > **Hardware**.

### Was geschieht, wenn Benutzer den Zugriff erlauben oder verweigern?
Wenn Benutzer den Zugriff erlauben, werden Telefonnummer und IMEI des Geräts in der Verwaltungskonsole auf der Seite „Hardware“ angezeigt.

Wenn Benutzer den Zugriff verweigern, können sie die Unternehmensportal-App weiterhin verwenden und ihr Gerät registrieren. Die Felder für Telefonnummer und IMEI des Geräts des Benutzers auf der Seite „Hardware“ in der Verwaltungskonsole bleiben jedoch leer. Wenn Benutzer den Zugriff verweigern und sich dann das nächste Mal bei der Unternehmensportal-App anmelden, wird in der Meldung ein Kontrollkästchen **Nicht mehr nachfragen** angezeigt, das die Benutzer aktivieren können, damit diese Meldung nicht mehr angezeigt wird.

Wenn Benutzer den Zugriff zunächst erlauben, später aber verweigern, wird die Meldung wieder angezeigt, wenn sie sich nach der Registrierung das nächste Mal bei der Unternehmensportal-App anmelden.</br></br>Wenn Benutzer den Zugriff später erlauben möchten, müssen sie zu **Einstellungen** > **Apps** > ** Unternehmensportal** > **Berechtigungen** > **Telefon** wechseln, um die Berechtigung zu aktivieren.

### Wo erhalten die Benutzer weitere Informationen?
In Schritt 5 zum [Registrieren Ihres Android-Geräts bei Intune](/Intune/EndUser/enroll-your-device-in-intune-android)

## Unternehmensportal den Zugriff auf Fotos, Medien und Dateien auf Ihrem Gerät erlauben?

### Meldungstext und Position auf der Oberfläche
Der Meldungstext lautet **Unternehmensportal den Zugriff auf Fotos, Medien und Dateien auf Ihrem Gerät erlauben?** und wird angezeigt, wenn der Benutzer auf **Daten senden** tippt, um Datenprotokolle an den IT-Administrator zu senden.

### Bedeutung der Meldung
Die Meldung fordert Benutzer auf, ihrem Gerät zu erlauben, Datenprotokolle auf die SD-Karte des Geräts zu schreiben und das Verschieben dieser Protokolle mithilfe eines USB-Kabels zu ermöglichen.   

> [!NOTE]
> **Die Unternehmensportal-App greift nicht auf Fotos, Medien und Dateien der Benutzer zu.** Der Meldungstext wird von Google gesteuert und kann nicht geändert werden.

### Was geschieht, wenn Benutzer den Zugriff erlauben oder verweigern?
Wenn Benutzer den Zugriff erlauben, werden die Protokolle auf die SD-Karte kopiert.

Wenn Benutzer den Zugriff verweigern, können sie weiterhin Datenprotokolle senden, aber die Protokolle werden nicht auf die SD-Karte des Geräts kopiert.

Wenn Benutzer den Zugriff verweigern und sich dann das nächste Mal bei der Unternehmensportal-App anmelden, wird in der Meldung ein Kontrollkästchen **Nicht mehr nachfragen** angezeigt, das die Benutzer aktivieren können, damit diese Meldung nicht mehr angezeigt wird. Wenn Benutzer den Zugriff zunächst erlauben, später aber verweigern, wird die Meldung wieder angezeigt, wenn sie das nächste Mal Protokolle senden. Wenn Benutzer den Zugriff später erlauben möchten, müssen sie zu **Einstellungen** > **Apps** > ** Unternehmensportal** > **Berechtigungen** > **Speicherung** wechseln, um die Berechtigung zu aktivieren.

### Wo erhalten die Benutzer weitere Informationen?
[Senden von Diagnosedatenprotokollen an Ihren IT-Administrator per E-Mail](/Intune/EndUser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)


### Weitere Informationen:
[Informieren der Endbenutzer über den Einsatz von Intune](/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune.md)


<!--HONumber=May16_HO2-->


