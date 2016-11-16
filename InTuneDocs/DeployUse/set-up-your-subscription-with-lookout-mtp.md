---
title: "Einrichten Ihres Abonnements für Lookout | Microsoft Intune"
description: "In diesem Thema werden Details zum Konfigurieren des Lookout-Schutzes vor Gerätebedrohungen erläutert."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8477a2f1-2e1d-4d42-8bcb-e1181cc900bb
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1187ad3fdd4a427333d610686698c1f806c6ee33
ms.openlocfilehash: 1d8cdaa36a852fba5912c250daa500e16bd3b661


---

# <a name="set-up-your-subscription-for-lookout-device-threat-protection"></a>Einrichten Ihres Abonnements für den Lookout-Schutz vor Gerätebedrohungen
Um Ihr Abonnement für den Lookout-Dienst für den Schutz vor Gerätebedrohungen vorzubereiten, benötigt der Lookout-Support (enterprisesupport@lookout.com) die folgenden Informationen zu Ihrem Azure Active Directory-Abonnement (Azure AD). Ihr Lookout Mobile Endpoint Security-Mandant wird zur Integration von Lookout in Intune Ihrem Azure AD-Abonnement zugeordnet. 

* **Azure AD-Mandanten-ID**
* **Objekt-ID der Azure AD-Gruppe** für den **Vollzugriff** auf die Lookout-Konsole
* **Objekt-ID der Azure AD-Gruppe** für den **eingeschränkten** Zugriff auf die Lookout-Konsole (optional)

> [!IMPORTANT]
> Ein bestehender Lookout Mobile Endpoint Security-Mandant, der nicht bereits Ihrem Azure AD-Mandanten zugeordnet ist, kann nicht für die Integration in Azure AD und Intune verwendet werden. Wenden Sie sich an den Lookout-Support, um einen neuen Lookout Mobile Endpoint Security-Mandanten zu erstellen. Verwenden Sie den neuen Mandanten zur Integration Ihrer Azure AD-Benutzer.

Verwenden Sie den folgenden Abschnitt, um die Informationen zusammenzustellen, die Sie an das Lookout-Supportteam übermitteln müssen.  

## <a name="get-your-azure-ad-information"></a>Abrufen der Azure AD-Informationen
### <a name="azure-ad-tenant-id"></a>Azure AD-Mandanten-ID
Melden Sie sich beim [Azure AD-Verwaltungsportal](https://manage.windowsazure.com) an, und wählen Sie Ihr Abonnement aus. 

![Screenshot der Azure AD-Seite mit dem Namen des Mandanten](../media/mtp/aad_tenant_name.png) Wenn Sie den Namen Ihres Abonnements auswählen, schließt die resultierende URL die Abonnement-ID ein.  Wenn Sie Probleme haben, Ihre Abonnement-ID zu finden, finden Sie in diesem [Microsoft-Supportartikel](https://support.office.com/en-us/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b?ui=en-US&rs=en-US&ad=US) entsprechende Tipps.   
### <a name="azure-ad-group-id"></a>Azure AD-Gruppen-ID
Die Lookout-Konsole unterstützt zwei Zugriffsebenen:  
* **Vollzugriff:** Der Azure AD-Administrator kann eine Gruppe für Benutzer erstellen, die Vollzugriff erhalten sollen, und optional eine Gruppe für Benutzer erstellen, die eingeschränkten Zugriff erhalten sollen.  Nur die Benutzer in diesen Gruppen können sich dann bei der **Lookout-Konsole** anmelden.
* **Eingeschränkter Zugriff:** Die Benutzer in dieser Gruppe haben keinen Zugriff auf verschiedene Module der Lookout-Konsole für die Konfiguration und Registrierung und schreibgeschützten Zugriff auf das Modul **Sicherheitsrichtlinie** der Lookout-Konsole.  

Weitere Details zu den Berechtigungen finden Sie in [diesem Artikel](https://personal.support.lookout.com/hc/en-us/articles/114094105653) auf der Lookout-Website.

Die **Gruppenobjekt-ID** befindet sich in der **Azure AD-Verwaltungskonsole** auf der Seite **Eigenschaften** der Gruppe.

![Screenshot der Eigenschaftenseite mit hervorgehobenem Feld „GroupID“](../media/mtp/aad_group_object_id.png)

Nachdem Sie diese Informationen gesammelt haben, wenden Sie sich an den Lookout-Support (email: enterprisesupport@lookout.com).

Der Lookout-Support arbeitet mit Ihrem primären Kontakt zusammen, um Ihr Abonnement mithilfe der von Ihnen gesammelten Informationen zu integrieren und Ihr Lookout Enterprise-Konto zu erstellen.


## <a name="configure-your-subscription-with-lookout-device-threat-protection"></a>Konfigurieren Ihres Abonnements für den Lookout-Schutz vor Gerätebedrohungen
### <a name="step-1-set-up-your-device-threat-protection"></a>Schritt 1: Einrichten des Schutzes vor Gerätebedrohungen
Nachdem der Lookout-Support Ihr Lookout Enterprise-Konto erstellt hat, können Sie sich bei der Lookout-Konsole anmelden.   Eine E-Mail wird von Lookout an den primären Kontakt Ihres Unternehmens gesendet, sie enthält einen Link zur Anmelde-URL: „https://aad.lookout.com/les?action=consent“

Bei der ersten Anmeldung bei der Lookout MTP-Konsole müssen Sie ein Benutzerkonto mit der Azure AD-Rolle „Globaler Administrator“ verwenden, da Lookout diese Informationen zum Registrieren Ihres Azure AD-Mandanten erfordert.   Bei nachfolgenden Anmeldungen muss der Benutzer nicht über diese Berechtigungsebene in Azure AD verfügen.  Bei dieser ersten Anmeldung wird eine Zustimmungsseite angezeigt. Wählen Sie **Akzeptieren** aus, um die Registrierung abzuschließen.

![Screenshot der Seite für die erstmalige Anmeldung der Lookout-Konsole](../media/mtp/lookout_mtp_initial_login.png) Sobald Sie akzeptiert und zugestimmt haben, werden Sie zur Lookout-Konsole weitergeleitet. Nach der erstmaligen Registrierung können nachfolgende Anmeldungen über die URL „https://aad.lookout.com“ erfolgen.

Sollten bei der Anmeldung Probleme auftreten, lesen Sie den [Artikel zur Problembehandlung](https://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration).

In den nächsten Schritten werden die Aufgaben vorgestellt, die zum Abschließen der Lookout-Einrichtung in der [Lookout-Konsole](https://aad.lookout.com) abgeschlossen werden müssen.

### <a name="step-2-configure-the-intune-connector"></a>Schritt 2: Konfigurieren des Intune-Connectors

1.  Wählen Sie in der Lookout-Konsole vom Modul **System** die Registerkarte **Connectors** und dann **Intune** aus.

  ![Screenshot der Lookout-Konsole mit geöffneter Registerkarte „Connectors“ und hervorgehobener Option „Intune“](../media/mtp/lookout_mtp_setup-intune-connector.png)

2.  Konfigurieren Sie in der Verbindungseinstellungsoption die Taktfrequenz in Minuten.  Ihr Intune-Connector ist nun betriebsbereit.  

  ![Screenshot der Registerkarte „Verbindungseinstellungen“ mit konfigurierter Taktfrequenz](../media/mtp/lookout-mtp-connection-settings.png)

### <a name="step-3-configure-enrollment-groups"></a>Schritt 3: Konfigurieren von Registrierungsgruppen
Definieren Sie in der Option **Registrierungsverwaltung** eine Menge von Benutzern, deren Geräte bei Lookout registriert werden sollen. Die bewährte Methode ist das Registrieren einer kleinen Gruppe von Benutzern, um die Funktionsweise der Integration zu testen und sich mit ihr vertraut zu machen.  Sobald Sie mit den Ergebnissen Ihrer Tests zufrieden sind, können Sie die Registrierung auf weitere Gruppen von Benutzern ausweiten.

Um in Registrierungsgruppen einzusteigen, definieren Sie zuerst eine Azure AD-Sicherheitsgruppe, die eine geeignete Menge von Benutzern bildet, für die Registrierung für den Lookout-Schutz vor Gerätebedrohungen. Nachdem Sie die Gruppe in Azure AD erstellt haben, navigieren Sie in der Lookout-Konsole zur Option **Registrierungsverwaltung** und fügen die Azure AD-Sicherheitsgruppe **Anzeigename(n)** zur Registrierung hinzu.

Wenn sich ein Benutzer in einer Registrierungsgruppe befindet, werden alle Geräte der Gruppe, die in Azure AD unterstützt werden, registriert und sind dann für die Aktivierung für den Lookout-Schutz vor Gerätebedrohungen berechtigt.  Beim ersten Öffnen der Lookout for Work-App auf einem unterstützten Gerät wird das Gerät in Lookout aktiviert.

![Screenshot der Intune-Seite zur Connectorregistrierung](../media/mtp/lookout-mtp-enrollment.png)

Die bewährte Methode ist das Verwenden des Standardwerts (5 Minuten) für die Überprüfung auf neue Geräte.

>[!IMPORTANT]
> Beim Anzeigenamen wird Groß-/Kleinschreibung berücksichtigt.  Verwenden Sie den **Anzeigenamen**, wie auf der Seite **Eigenschaften** der Sicherheitsgruppe im Azure-Portal dargestellt. Beachten Sie in der Abbildung unten, dass auf der Seite **Eigenschaften** der Sicherheitsgruppe der Anzeigename mit Binnenmajuskel geschrieben ist.  Der Titel wird jedoch in konsequenter Kleinschreibung angezeigt und sollte nicht als Eingabe für die Lookout-Konsole verwendet werden.
>![Screenshot des Azure-Portals, Azure Active Directory-Dienst, Seite „Eigenschaften“](../media/mtp/aad-group-display-name.png)

Die aktuelle Version unterliegt den folgenden Einschränkungen:  
* Es findet keine Überprüfung der Anzeigenamen der Gruppen statt.  Achten Sie darauf, den Wert im Feld **ANZEIGENAME** zu verwenden, der im Azure-Portal für die Azure AD-Sicherheitsgruppe angezeigt wird.
* Das Erstellen von Gruppen innerhalb von Gruppen wird aktuell nicht unterstützt.  Die angegebenen Azure AD-Sicherheitsgruppen dürfen nur Benutzer und keine geschachtelten Gruppen enthalten.


### <a name="step-4-configure-state-sync"></a>Schritt 4: Konfigurieren der Statussynchronisierung
Geben Sie in der Option **Statussynchronisierung** den Typ von Daten an, die an Intune gesendet werden sollen.  Aktuell müssen Sie sowohl den Gerätestatus als auch den Bedrohungsstatus aktivieren, damit die Lookout-Intune-Integration ordnungsgemäß funktioniert.  Diese sind standardmäßig aktiviert.
### <a name="step-5-configure-error-report-email-recipient-information"></a>Schritt 5: Konfigurieren von Empfängerinformationen für Fehlerberichts-E-Mails
Geben Sie in der Option **Fehlerverwaltung** die E-Mail-Adresse ein, an die die Fehlerberichte gesendet werden sollen.

![Screenshot der Intune-Seite zur Connector-Fehlerverwaltung](../media/mtp/lookout-mtp-connector-error-notifications.png)

### <a name="step-6-configure-enrollment-settings"></a>Schritt 6: Konfigurieren von Registrierungseinstellungen
Geben Sie im Modul **System** auf der Seite **Connectors** die Anzahl von Tagen an, bevor ein Gerät als getrennt bezeichnet werden kann.  Nicht verbundene Geräte gelten als nicht kompatibel und der Zugriff auf Unternehmensanwendungen wird ihnen auf Grundlage der Intune-Richtlinien für den bedingten Zugriff verwehrt. Sie können Werte zwischen 1 und 90 Tagen angeben.

![](../media/mtp/lookout-console-enrollment-settings.png)

### <a name="step-7-configure-email-notifications"></a>Schritt 7: Konfigurieren von E-Mail-Benachrichtigungen
Wenn Sie bei Bedrohungen Warnungen per E-Mail erhalten möchten, melden Sie sich bei der [Lookout-Konsole](https://aad.lookout.com) mit dem Benutzerkonto an, das die Benachrichtigungen erhalten soll. Wählen Sie im Modul **System** auf der Registerkarte **Einstellungen** die gewünschten Benachrichtigungen aus, und legen Sie sie auf **EIN** fest. Speichern Sie die Änderungen.

![Screenshot der Seite „Einstellungen“ mit angezeigtem Benutzerkonto](../media/mtp/lookout-mtp-email-notifications.png) Wenn Sie keine E-Mail-Benachrichtigungen mehr empfangen möchten, legen Sie die Benachrichtigungen auf **AUS** fest, und speichern Sie Ihre Änderungen.
### <a name="step-8-configure-threat-classification"></a>Schritt 8: Konfigurieren der Bedrohungsklassifizierung
Der Lookout-Schutz vor Gerätebedrohungen klassifiziert verschiedene Typen von Bedrohungen für mobile Geräte. Den [Lookout-Bedrohungsklassifizierungen](http://personal.support.lookout.com/hc/en-us/articles/114094130693) sind Standardrisikostufen zugeordnet. Sie können diese jederzeit gemäß den Anforderungen Ihres Unternehmens ändern.

![Screenshot der Richtlinienseite mit Bedrohung und Klassifikationen](../media/mtp/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> Die hier angegebenen Risikostufen bilden einen wichtigen Aspekt des Schutzes vor Gerätebedrohungen, da die Intune-Integration die Gerätekompatibilität zur Laufzeit anhand dieser Risikostufen berechnet. Der Intune-Administrator legt also eine Regel in der Richtlinie fest, um zu bestimmen, dass ein Gerät nicht kompatibel ist, wenn auf ihm eine aktive Bedrohung mit einer Mindeststufe erkannt wird: Gering, Mittel oder Hoch. Die Richtlinie zur Bedrohungsklassifizierung des Lookout-Schutzes vor Gerätebedrohungen bildet unmittelbar die Grundlage zur Berechnung der Gerätekompatibilität in Intune.

## <a name="watching-enrollment"></a>Beobachten der Registrierung
Nachdem das Setup abgeschlossen wurde, beginnt der Lookout-Schutz vor Gerätebedrohungen mit der Abfrage von Azure AD nach Geräten, die den angegebenen Registrierungsgruppen entsprechen.  Informationen zu den registrierten Geräten finden Sie im Modul „Geräte“.  Der Ausgangsstatus für Geräte wird als „ausstehend“ angezeigt.  Der Gerätestatus ändert sich, sobald die Lookout for Work-App auf dem Gerät installiert, geöffnet und aktiviert wurde.  Details zur Übertragung der Lookout for Work-App per Push an die Geräte finden Sie im Thema [Konfigurieren und Bereitstellen von Lookout for Work-Apps](configure-and-deploy-lookout-for-work-apps.md).
## <a name="next-steps"></a>Nächste Schritte
[Aktivieren der Lookout MTP-Verbindung mit Intune](enable-lookout-mtp-connection-in-intune.md)



<!--HONumber=Nov16_HO1-->


