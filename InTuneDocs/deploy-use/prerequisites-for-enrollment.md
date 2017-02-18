---
title: "Voraussetzungen für die Registrierung von mobilen Geräten | Microsoft-Dokumentation"
description: "Einrichten der Voraussetzungen für die Verwaltung mobiler Geräte (Mobile Device Management, MDM) und Vorbereiten der Registrierung für verschiedene Betriebssysteme."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 2b7fe00a2f3b289958aa77df5eaffd35de7c8c97


---

# <a name="prerequisites-for-mobile-device-management-in-intune"></a>Voraussetzungen für die Verwaltung von mobilen Geräten in Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Damit Mitarbeiter ihre mobilen Geräten bei Intune registrieren können, sind die folgenden Schritte erforderlich. Dieselben Schritte müssen auch ausgeführt werden, um unternehmenseigene Geräte verwalten zu können.

|Schritte|Details|  
|-----------|-------------|  
|**Schritt 1:** [Aktivieren von Verbindungen](#step-1-enable-connections)|Stellen Sie sicher, dass der benutzerdefinierte Domänenname konfiguriert und die Netzwerkkommunikation eingerichtet ist.|  
|**Schritt 2:** [Festlegen der MDM-Autorität](#step-2-set-mdm-authority)|Die Autorität für die Verwaltung mobiler Geräte definiert den Dienst, der Ihren Geräten zugewiesen ist.|
|**Schritt 3:** [Erstellen von Gruppen](#step-3-create-groups)|Konfigurieren Sie benutzerseitige Einstellungen für die Unternehmensportal-App.|  
|**Schritt 4:** [Konfigurieren des Unternehmensportals](#step-4-configure-company-portal)|Konfigurieren Sie benutzerseitige Einstellungen für die Unternehmensportal-App.|  
|**Schritt 5:** [Zuweisen von Benutzerlizenzen](#step-5-assign-user-licenses)|Weisen Sie den Benutzern Intune-Lizenzen zu, damit sie ihre Geräte registrieren können.|
|**Schritt 6:** [Aktivieren der Registrierung](#step-6-enable-enrollment)|Aktivieren Sie plattformspezifische Einstellungen für die iOS- und Windows-Verwaltung. Für Android-Geräte ist keine weitere Konfiguration erforderlich.|
|**Schritt 7:** [Nächste Schritte](#step-7-next-steps)|Aktivieren Sie plattformspezifische Einstellungen für die iOS- und Windows-Verwaltung. Für Android-Geräte ist keine weitere Konfiguration erforderlich.|

Suchen Sie nach Intune mit Configuration Manager?
> [!div class="button"]
[SCCM-Dokumentation anzeigen >](https://docs.microsoft.com/sccm/mdm/deploy-use/setup-hybrid-mdm)

## <a name="step-1-enable-connections"></a>Schritt 1: Aktivieren von Verbindungen

Bevor Sie die Registrierung mobiler Geräte aktivieren, müssen Sie die folgenden Aufgaben ausgeführt haben:
- [Überprüfen der erforderlichen Netzwerk-URLs und -ports](../get-started/network-infrastructure-requirements-for-microsoft-intune.md)
- [Hinzufügen und Überprüfen Ihres Domänennamens](../get-started/domain-names-for-microsoft-intune.md)

## <a name="step-2-set-mdm-authority"></a>Schritt 2: Festlegen der MDM-Autorität
Die MDM-Autorität definiert den Verwaltungsdienst, der über die Berechtigung zum Verwalten einer Gruppe von Geräten verfügt. Die Optionen für die MDM-Autorität umfassen Intune selbst und Configuration Manager mit Intune. Wenn Sie Configuration Manager als Verwaltungsautorität festlegen, kann kein anderer Dienst für die Verwaltung mobiler Geräte verwendet werden.

>[!IMPORTANT]
> Sie sollten sorgfältig überlegen, ob Sie mobile Geräte nur mit Intune (Onlinedienst) oder mit System Center Configuration Manager mit Intune (lokale Softwarelösung in Verbindung mit dem Onlinedienst) verwalten möchten. Nachdem Sie die Autorität für die Verwaltung mobiler Geräte festgelegt haben, kann sie nicht mehr geändert werden.



1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) die Optionen **Verwaltung** &gt; **Verwaltung mobiler Geräte** aus.

2.  Klicken Sie in der Liste **Aufgaben** auf **Autorität für die Verwaltung mobiler Geräte festlegen**. Das Dialogfeld **MDM-Autorität festlegen** wird geöffnet.

    ![Dialogfeld „MDM-Autorität festlegen“](../media/intune-mdm-authority.png)

3.  Intune erfordert eine Bestätigung, dass es als MDM-Autorität verwendet werden soll. Aktivieren Sie das Kontrollkästchen, und wählen Sie dann **Ja** aus, um Microsoft Intune zum Verwalten mobiler Geräte zu verwenden.

## <a name="step-3-create-groups"></a>Schritt 3: Erstellen von Gruppen

Sie können Benutzer- und Gerätegruppen erstellen, um die Verwaltung zu vereinfachen und die Zielauswahl für bereitgestellte Apps, Richtlinien und Unternehmensressourcen zu verbessern. [Erfahren Sie, wie Sie Gruppen erstellen](use-groups-to-manage-users-and-devices-with-microsoft-intune.md#create-groups).

## <a name="step-4-configure-company-portal"></a>Schritt 4: Konfigurieren des Unternehmensportals

Im Intune-Unternehmensportal können Benutzer auf Unternehmensdaten zugreifen, häufige Aufgaben wie das Registrieren von Geräten und das Installieren von Apps ausführen und sich über Unterstützungsmöglichkeiten durch Ihre IT-Abteilung informieren.

> [!TIP]
> Wenn Sie das Unternehmensportal anpassen, gelten die Konfigurationen sowohl für die Unternehmensportalwebsite als auch für die Unternehmensportal-Apps.

Durch Anpassen des Unternehmensportals können Sie Ihren Endbenutzern eine vertraute und hilfreiche Benutzeroberfläche bereitstellen. Melden Sie sich zu diesem Zweck einfach als Mandanten- oder Dienstadministrator bei der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) an, wählen Sie **Verwaltung** &gt; **Unternehmensportal** aus, und konfigurieren Sie die Einstellungen für das Unternehmensportal.

![admin-console-admin-workspace-comp-portal-settings](../media/cp_sa_cpsetup.PNG)

### <a name="company-contact-information-and-privacy-statement"></a>Kontaktdaten und Datenschutzerklärung des Unternehmens

Der Unternehmensname wird als Titel des Unternehmensportals angezeigt. Die Kontaktinformationen werden Benutzern im Unternehmensportal auf dem Bildschirm für die Kontaktaufnahme mit der IT-Abteilung angezeigt. Die Datenschutzerklärung wird angezeigt, wenn ein Benutzer auf den Datenschutzlink klickt.

|Feldname|Max. Länge|Weitere Informationen|
    |----------|------------------------|----------------|
    |Firmenname|40|Dieser Name wird als Titel des Unternehmensportals angezeigt. **Hinweis**: Nur alphanumerische Zeichen. Dieses Feld unterstützt keine Sonderzeichen.|
    |Kontaktname für IT-Abteilung|40|Dieser Name wird auf der Seite **An IT-Abteilung wenden** angezeigt.|
    |Telefonnummer der IT-Abteilung|20|Diese Telefonnummer wird auf der Seite **An IT-Abteilung wenden** angezeigt.|
    |E-Mail-Adresse der IT-Abteilung|40|Diese Kontaktadresse wird auf der Seite **An IT-Abteilung** wenden angezeigt. Sie müssen eine gültige E-Mail-Adresse im Format **alias@domainname.com** eingeben.|
    |Weitere Informationen|120|Diese Informationen werden auf der Seite **An IT wenden** angezeigt.|
    |URL der Datenschutzrichtlinie des Unternehmens|79|Sie können eine eigene Datenschutzerklärung für Ihr Unternehmen angeben. Diese wird angezeigt, wenn die Benutzer im Unternehmensportal auf die Datenschutzlinks klicken. Sie müssen eine gültige URL im Format https://www.contoso.com eingeben.|

### <a name="support-contacts"></a>Supportkontakte
Die Supportwebsite wird Benutzern im Unternehmensportal angezeigt, um ihnen Zugriff auf Onlinesupport zu ermöglichen.

|Feldname|Max. Länge|Weitere Informationen|
    |----------|------------------------|----------------|
    |URL der Supportwebsite|150|Wenn Sie über eine Supportwebsite verfügen, die Ihre Benutzer verwenden sollen, geben Sie hier die URL an. Die URL muss das Format https://www.contoso.com aufweisen. Wenn Sie keine URL angeben, wird im Unternehmensportal auf der Seite **An IT-Abteilung wenden** keine Supportwebsite angezeigt.|
    |Name der Website|40|Dies ist der Anzeigename der URL für die Supportwebsite. Wenn Sie für die Supportwebsite eine URL, aber keinen Anzeigenamen angeben, wird im Unternehmensportal auf der Seite **An IT-Abteilung wenden** der Text **Zur IT-Website wechseln** angezeigt.|


### <a name="company-branding-customization"></a>Anpassen des Unternehmensbrandings

Sie können Ihr Unternehmensportal mit Ihrem Firmenlogo, Firmennamen, Farbdesign und Hintergrund anpassen.

|Feldname|Weitere Informationen|
    |----------|----------------|
    |Farbdesign|Wählen Sie ein Farbdesign aus, das auf das Unternehmensportal angewendet werden soll.|
    |Firmenlogo einschließen|Wenn Sie diese Option aktivieren, können Sie Ihr Firmenlogo hochladen. Dieses wird dann im Unternehmensportal angezeigt. Sie können zwei Logos hochladen: ein Logo, das angezeigt wird, wenn der Hintergrund des Unternehmensportals weiß ist, und eines, das angezeigt wird, wenn für den Hintergrund des Unternehmensportals das von Ihnen ausgewählte Farbdesign verwendet wird. Die Logos müssen als PNG- oder JPG-Dateien vorliegen. Ihre Auflösung darf maximal 400 x 100 Pixel betragen, und die Größe darf 750 KB nicht überschreiten.|
    |Hintergrund für die Unternehmensportal-App auswählen|Diese Einstellung betrifft nur den Hintergrund der Unternehmensportal-App.|


Nach dem Speichern Ihrer Änderungen können Sie über die Links, die am unteren Rand der Seite **Unternehmensportal** in der Verwaltungskonsole angegeben sind, die Unternehmensportalwebsite anzeigen. Diese Links können nicht geändert werden. Wenn ein Benutzer sich anmeldet, werden über diese Links Ihre Abonnements im Unternehmensportal angezeigt.

## <a name="step-5-assign-user-licenses"></a>Schritt 5: Zuweisen von Benutzerlizenzen

Verwenden Sie das **Office 365-Verwaltungsportal**, um cloudbasierte Benutzer manuell hinzuzufügen und um sowohl cloudbasierten Benutzerkonten als auch Konten, die aus Ihrem lokalen Active Directory mit Azure Active Directory (Azure AD) synchronisiert wurden, Lizenzen zuzuweisen. Sie können [lokale Benutzer mit Azure AD synchronisieren](../get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3.md#how-to-sync-on-premises-users-with-azure-ad).

1.  Melden Sie sich mit den Anmeldeinformationen Ihres Mandantenadministrators beim [Office 365-Verwaltungsportal](https://portal.office.com/Admin/Default.aspx) an.

2.  Wählen Sie das Benutzerkonto aus, dem Sie eine Intune-Benutzerlizenz zuweisen möchten, und aktivieren Sie in den Eigenschaften des Benutzerkontos das Kontrollkästchen **Microsoft Intune**.

3.  Das Benutzerkonto wird jetzt der Microsoft Intune-Benutzergruppe zugewiesen, die dem Benutzer Berechtigungen zur Verwendung des Diensts und zur Registrierung von Geräten für die Verwaltung gewährt.

### <a name="to-synchronize-on-premises-users-with-azure-ad"></a>So synchronisieren Sie lokale Benutzer mit Azure AD

1. [Fügen Sie das UPN-Suffix](https://technet.microsoft.com/en-us/library/cc772007.aspx) für Ihre benutzerdefinierte Domäne in Ihrem lokalen Active Directory hinzu.
2. Legen Sie das neue UPN-Suffix für die lokalen Benutzer fest, die Sie importieren möchten.
3. Führen Sie die [Azure AD Connect-Synchronisierung](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/) aus, um Ihre lokalen Benutzer mit Azure AD zu integrieren.
4. Sobald die Informationen des Benutzerkontos erfolgreich synchronisiert wurden, können Sie mithilfe des [Verwaltungsportals für Office 365](https://portal.office.com/Admin/Default.aspx) Microsoft Intune-Lizenzen zuweisen.

## <a name="step-6-enable-enrollment"></a>Schritt 6: Aktivieren der Registrierung
Nach dem Einrichten der MDM-Autorität müssen Sie die Geräteverwaltung für die Betriebssysteme einrichten, die Ihre Organisation unterstützen möchte. Die zum Einrichten der Geräteverwaltung erforderlichen Schritte unterscheiden sich je nach Betriebssystem. Beispielsweise müssen Sie für Android-Betriebssysteme keinerlei Aktivitäten in der Intune-Verwaltungskonsole ausführen. Andererseits setzen Windows und iOS eine Vertrauensbeziehung zwischen den Geräten und Intune voraus, um die Verwaltung zu ermöglichen.

Richten Sie Verwaltung für die folgenden Plattformen ein:
- [iOS und Mac](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Android](set-up-android-management-with-microsoft-intune.md)
- [Android for Work](set-up-android-for-work.md)
- [Windows-PCs und -Laptops](set-up-windows-device-management-with-microsoft-intune.md)
- [Windows 10 Mobile und Windows Phone](set-up-windows-phone-management-with-microsoft-intune.md)

Sie können auch die [Registrierung von unternehmenseigenen Geräten](manage-corporate-owned-devices.md) aktivieren.

## <a name="step-7-next-steps"></a>Schritt 7: Nächste Schritte

Nachdem nun die Registrierung aktiviert ist, sollten Sie die Verwaltung einrichten, um Ihre geschäftlichen Anforderungen zu erfüllen. Im Folgenden finden Sie einige Verwaltungsoptionen:

- [Bereitstellen von Richtlinien zum Verwalten von Einstellungen und Features auf Geräten](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
- [Aktivieren des Zugriffs auf Unternehmensressourcen wie E-Mail, WLAN und VPN](enable-access-to-company-resources-with-microsoft-intune.md)
- [Hinzufügen von Apps](add-apps.md) und [Bereitstellen von Apps](deploy-apps.md) auf verwalteten Geräten
- [Erstellen von Gerätekompatibilitätsrichtlinien](introduction-to-device-compliance-policies-in-microsoft-intune.md) und [Beschränken des Zugriffs basierend auf Kompatibilität](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


