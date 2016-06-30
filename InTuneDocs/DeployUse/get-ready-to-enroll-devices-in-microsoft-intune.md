---
title: "Vorbereiten der Registrierung von Geräten | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40
ms.reviewer: jeffgilb
ms.suite: ems
ms.sourcegitcommit: 71077d9f86a53cc66536928e4799fa4b1a51cdf0
ms.openlocfilehash: 86d3b7894eca70454fa82393c4d06eab5a99246f


---

# Vorbereiten der Registrierung von Geräten in Microsoft Intune
Damit Mitarbeiter mobile Geräte (einschließlich [Android](set-up-android-management-with-microsoft-intune.md), [iOS und Mac](set-up-ios-and-mac-management-with-microsoft-intune.md), [Windows Phone](set-up-windows-phone-management-with-microsoft-intune.md) und [Windows PCs](set-up-windows-device-management-with-microsoft-intune.md)) bei Intune registrieren können, müssen Sie die Geräteregistrierung aktivieren. Um die Registrierung zu ermöglichen, müssen Sie eine Autorität zur Verwaltung mobiler Geräte festlegen, das Intune-Unternehmensportal konfigurieren, Lizenzen zuweisen und die Registrierung für die Geräteplattform aktivieren.

## Festlegen der Autorität zur Verwaltung mobiler Geräte
Die Autorität für die Verwaltung mobiler Geräte definiert den Verwaltungsdienst mit der Berechtigung zum Verwalten einer Gruppe von Geräten. Die Optionen für die MDM-Autorität (Mobile Device Management, Verwaltung mobiler Geräte) umfassen Intune selbst und Configuration Manager mit Intune. Wenn Sie Configuration Manager als Verwaltungsautorität festlegen, kann kein anderer Dienst für die Verwaltung mobiler Geräte verwendet werden.

>[!IMPORTANT]
> Sie sollten sorgfältig überlegen, ob Sie mobile Geräte nur mit Intune (Onlinedienst) oder mit System Center Configuration Manager mit Intune (lokale Softwarelösung in Verbindung mit einem Onlinedienst) verwalten möchten. Nachdem Sie die Autorität für die Verwaltung mobiler Geräte festgelegt haben, kann sie nicht mehr geändert werden.



1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) die Optionen **Admin** &gt; **Verwaltung mobiler Geräte** aus.

2.  Klicken Sie in der Liste **Aufgaben** auf **Autorität für die Verwaltung mobiler Geräte festlegen**. Das Dialogfeld **MDM-Autorität festlegen** wird geöffnet.

    ![Dialogfeld „MDM-Autorität festlegen“](../media/intune-mdm-authority.png)

3.  Intune erfordert eine Bestätigung, dass es als MDM-Autorität verwendet werden soll. Aktivieren Sie das Kontrollkästchen, und wählen Sie dann **Ja** aus, um Microsoft Intune zum Verwalten mobiler Geräte zu verwenden.

## Konfigurieren des Intune-Unternehmensportals

Im Intune-Unternehmensportal können Benutzer auf Unternehmensdaten zugreifen, häufige Aufgaben wie das Registrieren von Geräten und das Installieren von Apps ausführen und sich über Unterstützungsmöglichkeiten durch Ihre IT-Abteilung informieren.

> [!TIP] Wenn Sie das Unternehmensportal anpassen, gelten die Konfigurationen sowohl für die Unternehmensportal-Website als auch für die Unternehmensportal-Apps.

Durch Anpassen des Unternehmensportals können Sie Ihren Endbenutzern eine vertraute und sinnvolle Benutzeroberfläche bereitstellen. Melden Sie sich zu diesem Zweck einfach als Mandanten- oder Dienstadministrator bei der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) an, wählen Sie **Admin** &gt; **Unternehmensportal** aus, und konfigurieren Sie die Einstellungen für das Unternehmensportal.

![admin-console-admin-workspace-comp-portal-settings](../media/cp_sa_cpsetup.PNG)

#### Kontaktdaten und Datenschutzerklärung des Unternehmens

Der Unternehmensname wird als Titel des Unternehmensportals angezeigt. Die Kontaktinformationen werden Benutzern im Unternehmensportal auf dem Bildschirm für die Kontaktaufnahme mit der IT-Abteilung angezeigt. Die Datenschutzerklärung wird angezeigt, wenn ein Benutzer auf den Datenschutzlink klickt.

|Feldname|Max. Länge|Weitere Informationen|
    |----------|------------------------|----------------|
    |Firmenname|40|Dieser Name wird als Titel des Unternehmensportals angezeigt.|
    |Kontaktname für IT-Abteilung|40|Dieser Name wird auf der Seite **An IT-Abteilung wenden** angezeigt.|
    |Telefonnummer der IT-Abteilung|20|Diese Telefonnummer wird auf der Seite **An IT-Abteilung wenden** angezeigt.|
    |E-Mail-Adresse der IT-Abteilung|40|Diese Kontaktadresse wird auf der Seite **An IT-Abteilung** wenden angezeigt. Sie müssen eine gültige E-Mail-Adresse im Format **Alias@Domänenname.com** eingeben.|
    |Weitere Informationen|120|Dies wird auf der Seite **An IT-Abteilung wenden** angezeigt.|
    |URL der Datenschutzrichtlinie des Unternehmens|79|Sie können eine eigene Datenschutzerklärung für Ihr Unternehmen angeben. Diese wird angezeigt, wenn die Benutzer im Unternehmensportal auf die Datenschutzlinks klicken. Sie müssen eine gültige URL im Format https://www.contoso.com eingeben.|

#### Supportkontakte
Die Supportwebsite wird Benutzern im Unternehmensportal angezeigt, um ihnen Zugriff auf Onlinesupport zu ermöglichen.

|Feldname|Max. Länge|Weitere Informationen|
    |----------|------------------------|----------------|
    |URL der Supportwebsite|150|Wenn Sie über eine Supportwebsite verfügen, die Ihre Benutzer verwenden sollen, geben Sie hier die URL an. Die URL muss das Format https://www.contoso.com aufweisen. Wenn Sie keine URL angeben, wird im Unternehmensportal auf der Seite **An IT-Abteilung wenden** keine Supportwebsite angezeigt.|
    |Websitename|40|Dies ist der Anzeigename der URL für die Supportwebsite. Wenn Sie für die Supportwebsite eine URL, aber keinen Anzeigenamen angeben, wird im Unternehmensportal auf der Seite **An IT-Abteilung wenden** der Text **Zur IT-Website wechseln** angezeigt.|


#### Anpassen des Unternehmensbrandings

Sie können Ihr Unternehmensportal mit Ihrem Firmenlogo, Firmennamen, Farbdesign und Hintergrund anpassen.

|Feldname|Weitere Informationen|
    |----------|----------------|
    |Farbdesign|Wählen Sie ein Farbdesign aus, das auf das Unternehmensportal angewendet werden soll.|
    |Firmenlogo einschließen|Wenn Sie diese Option aktivieren, können Sie Ihr Firmenlogo hochladen. Dieses wird dann im Unternehmensportal angezeigt. Sie können zwei Logos hochladen: ein Logo, das angezeigt wird, wenn der Hintergrund des Unternehmensportals weiß ist, und eines, das angezeigt wird, wenn für den Hintergrund des Unternehmensportals das von Ihnen ausgewählte Farbdesign verwendet wird. Die Logodateien müssen PNG- oder JPG-Dateien sein. Ihre Auflösung darf maximal 400 x 100 Pixel betragen, und die Größe darf 750 KB nicht überschreiten.|
    |Hintergrund für die [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)]-Unternehmensportal- App auswählen|Diese Einstellung betrifft nur den Hintergrund der Unternehmensportal-App für [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)].|


Nach dem Speichern Ihrer Änderungen können Sie über die Links, die am unteren Rand der Seite **Unternehmensportal** in der Verwaltungskonsole angegeben sind, die Unternehmensportalwebsite anzeigen. Diese Links können nicht geändert werden. Wenn ein Benutzer sich anmeldet, werden über diese Links Ihre Abonnements im Unternehmensportal angezeigt.

## Zuweisen einer Intune-Benutzerlizenz

Verwenden Sie das **Verwaltungsportal von Office 365**, um cloudbasierte Benutzer manuell hinzuzufügen und um sowohl cloudbasierten Benutzerkonten als auch Konten, die aus Ihrem lokalen Active Directory mit Azure AD synchronisiert wurden, Lizenzen zuzuweisen.

1.  Melden Sie sich mit den Anmeldeinformationen Ihres Mandantenadministrators beim [Verwaltungsportal von Office 365](https://portal.office.com/Admin/Default.aspx) an.

2.  Wählen Sie das Benutzerkonto aus, dem Sie eine Intune-Benutzerlizenz zuweisen möchten, und aktivieren Sie in den Eigenschaften des Benutzerkontos das Kontrollkästchen **Microsoft Intune**.

3.  Das Benutzerkonto wird jetzt der Microsoft Intune-Benutzergruppe zugewiesen, die dem Benutzer Berechtigungen zur Verwendung des Diensts und zur Registrierung von Geräten für die Verwaltung gewährt.

## Einrichten der Geräteverwaltung
Nach dem Einrichten der MDM-Autorität müssen Sie die Geräteverwaltung für die Betriebssysteme einrichten, die Ihre Organisation unterstützen möchte. Die zum Einrichten der Geräteverwaltung erforderlichen Schritte unterscheiden sich für die verschiedenen Betriebssysteme. Beispielsweise brauchen Sie für Android OS keinerlei Aktivitäten in der Intune-Verwaltungskonsole auszuführen. Andererseits setzen Windows und iOS eine Vertrauensbeziehung zwischen den Geräten und Intune voraus, um die Verwaltung zu ermöglichen.

> [!div class="op_single_selector"]
- [Einrichten der Android-Verwaltung mit Microsoft Intune](set-up-android-management-with-microsoft-intune.md)
- [Set up iOS and Mac management with Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Einrichten der Windows Phone-Verwaltung mit Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md)
- [Einrichten der Windows-Geräteverwaltung mit Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md)

Sie haben auch folgende Möglichkeiten:
 - Verwenden des [Kontos für den Geräteregistrierungs-Manager](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md), wenn viele Geräte registriert werden sollen
 - [Angeben von Geräten im Besitz des Unternehmens mithilfe von IMEI-Nummern](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md), um Geräte zu registrieren und Zielrichtlinien festzulegen



<!--HONumber=Jun16_HO1-->


