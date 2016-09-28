---
title: "Einrichten Ihres Abonnements für Lookout MTP | Microsoft Intune"
description: "In diesem Thema werden Details zum Konfigurieren von Lookout MTP erläutert."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 8477a2f1-2e1d-4d42-8bcb-e1181cc900bb
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 61480eb11cc8f4b6b336e48a50c2fe1b5fcd3fac
ms.openlocfilehash: 8e2c71127801afc21d52e08d13dd9099b263e801


---

# Einrichten Ihres Abonnements für Lookout Mobile Threat Protection
Um Ihr Abonnement für den Lookout MTP-Dienst vorzubereiten, benötigt der Lookout-Support (enterprisesupport@lookout.com) die folgenden Informationen über Ihr Azure Active Directory (Azure AD). 

* Azure AD-Mandanten-ID
* Objekt-ID der Azure AD-Gruppe für den Vollzugriff auf die Lookout MTP-Konsole
* Objekt-ID der Azure AD-Gruppe für den eingeschränkten Zugriff auf die Lookout MTP-Konsole (optional)

Verwenden Sie die Informationen im folgenden Abschnitt, um die Informationen zusammenzustellen, die Sie an das Lookout-Supportteam übergeben müssen.  

## Abrufen der Azure AD-Informationen
### Abrufen der Azure AD-Mandanten-ID
Melden Sie sich beim Azure AD-Verwaltungsportal „https://manage.windowsazure.com“ an, und wählen Sie Ihr Abonnement aus. 

![Screenshot der Azure AD-Seite mit dem Namen des Mandanten](../media/mtp/aad_tenant_name.png) Wenn Sie den Namen Ihres Abonnements auswählen, schließt die resultierende URL die Abonnement-ID ein.  Wenn Sie Probleme haben, Ihre Abonnement-ID zu finden, finden Sie in diesem [Microsoft-Supportartikel](https://support.office.com/en-us/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b?ui=en-US&rs=en-US&ad=US) zusätzliche Tipps.   
### Abrufen der Azure AD-Gruppen-ID
Die Lookout MTP-Konsole unterstützt zwei Zugriffsebenen:  
* **Vollzugriff:** Azure AD-Administratoren können eine Gruppe für Benutzer erstellen, die Vollzugriff erhalten sollen, und optional eine Gruppe für Benutzer erstellen, die eingeschränkten Zugriff erhalten sollen.  Nur die Benutzer in diesen Gruppen sind dann in der Lage, sich bei der **Lookout MTP-Konsole** anzumelden.
* **Eingeschränkter Zugriff:** Kein Zugriff auf verschiedene Module der Lookout MTP-Konsole, die Konfiguration und Registrierung betreffen; schreibgeschützter Zugriff auf das Modul **Sicherheitsrichtlinie** der Lookout MTP-Konsole.  

Weitere Details zu den Berechtigungen finden Sie in [diesem Artikel](https://personal.support.lookout.com/hc/en-us/articles/114094105653) auf der Lookout-Website.

Die **Gruppenobjekt-ID** befindet sich auf der Eigenschaftenseite der Gruppe in der Azure AD-Verwaltungskonsole.

![Screenshot der Eigenschaftenseite mit hervorgehobenem Feld „GroupID“](../media/mtp/aad_group_object_id.png)

Nachdem Sie diese Informationen gesammelt haben, wenden Sie sich an den Lookout-Support (email: enterprisesupport@lookout.com).

Der Lookout-Support arbeitet mit Ihrem primären Kontakt zusammen, um Ihr Abonnement mithilfe der von Ihnen gesammelten Informationen zu integrieren und Ihr Lookout MTP Enterprise-Konto zu erstellen.


## Konfigurieren Ihres Abonnements für Lookout MTP
### Schritt 1: Einrichten Ihrer MTP
Nachdem der Lookout-Support Ihr Lookout MTP Enterprise-Konto erstellt hat, können Sie sich bei der Lookout MTP-Konsole anmelden.   Eine E-Mail wird von Lookout an den primären Kontakt Ihres Unternehmens gesendet, sie enthält einen Link zur Anmelde-URL: „https://aad.lookout.com/les?action=consent“

Bei der ersten Anmeldung bei der Lookout MTP-Konsole müssen Sie ein Benutzerkonto mit der Azure AD-Rolle „Globaler Administrator“ verwenden, da die Lookout MTP dies zum Registrieren Ihres Azure AD-Mandanten erfordert.   Bei nachfolgenden Anmeldungen muss der Benutzer nicht über diese Berechtigungsebene in Azure AD verfügen.  Bei dieser ersten Anmeldung wird eine Zustimmungsseite angezeigt. Wählen Sie **akzeptieren** aus, um die Registrierung abzuschließen.

![Screenshot der Seite für die erstmalige Anmeldung der Lookout MTP-Konsole](../media/mtp/lookout_mtp_initial_login.png) Sobald Sie akzeptiert und zugestimmt haben, werden Sie zur Lookout MTP-Konsole weitergeleitet. Nach der erstmaligen Registrierung können nachfolgende Anmeldungen über die URL: „https://aad.lookout.com“ erfolgen

Sollten bei der Anmeldung Probleme auftreten, lesen Sie den [Artikel zur Problembehandlung](https://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration).

In den nächsten Schritten werden die Aufgaben vorgestellt, die zum Abschließen der Lookout MTP-Einrichtung in der [Lookout MTP-Konsole](https://aad.lookout.com) abgeschlossen werden müssen.

### Schritt 2: Konfigurieren des Intune-Connectors

Gehen Sie in der Lookout MTP-Konsole zum Modul **System**, wählen Sie die Registerkarte **Connectors** und dann **Intune** aus.

![Screenshot der Lookout MTP-Konsole mit geöffneter Registerkarte „Connectors“ und hervorgehobener Option „Intune“](../media/mtp/lookout_mtp_setup-intune-connector.png)

Konfigurieren Sie in der Verbindungseinstellungsoption die Taktfrequenz in Minuten.  Mit Abschluss dieses Schritts ist Ihr Intune-Connector jetzt bereit.  

![Screenshot der Registerkarte „Verbindungseinstellungen“ mit konfigurierter Taktfrequenz](../media/mtp/lookout-mtp-connection-settings.png)

### Schritt 3: Konfigurieren von Registrierungsgruppen
Definieren Sie in der Option **Registrierungsverwaltung** eine Menge von Benutzern, deren Geräte bei Lookout registriert werden sollen.   Eine bewährte Methode ist das Registrieren einer kleinen Gruppe von Benutzern, um die Funktionsweise der Integration zu testen und sich mit ihr vertraut zu machen.  Sobald Sie mit den Ergebnissen Ihrer Tests zufrieden sind, können Sie die Registrierung auf weitere Gruppen von Benutzern ausweiten.

Um in Registrierungsgruppen einzusteigen, definieren Sie zuerst eine Azure AD-Sicherheitsgruppe, die eine geeignete Menge von Benutzern bildet, für die Registrierung bei Lookout MTP. Nachdem Sie die Gruppe in Azure AD erstellt haben, navigieren Sie in der Lookout MTP-Konsole zur Option **Registrierungsverwaltung**, und fügen Sie die Azure AD-Sicherheitsgruppe **Anzeigename(n)** für die Registrierung hinzu.

Wenn sich ein Benutzer in einer Registrierungsgruppe befindet, werden alle Geräte der Gruppe, die in Azure AD unterstützt werden, registriert und stehen für die Aktivierung in Lookout MTP zur Verfügung.  Beim ersten Öffnen der Lookout for Work-App auf einem unterstützten Gerät wird es dann in Lookout MTP aktiviert.
![Screenshot der Intune-Seite zur Connectorregistrierung](../media/mtp/lookout-mtp-enrollment.png)

Eine bewährte Methode ist das Beibehalten des Standardwerts von 5 Minuten für die Überprüfung auf neue Geräte.

>[!IMPORTANT]
> Beim Anzeigenamen wird Groß-/Kleinschreibung berücksichtigt.  Verwenden Sie den **Anzeigenamen**, wie auf der Seite **Eigenschaften** der Sicherheitsgruppe im Azure-Portal dargestellt. Beachten Sie in der Abbildung unten, dass auf der Seite **Eigenschaften** der Sicherheitsgruppe der Anzeigename mit Binnenmajuskel geschrieben ist.  Der Titel wird jedoch in konsequenter Kleinschreibung angezeigt und sollte nicht als Eingabe für die Lookout MTP-Konsole verwendet werden.
>![Screenshot des Azure-Portals, Azure Active Directory-Dienst, Seite „Eigenschaften“](../media/mtp/aad-group-display-name.png)

Die aktuelle Version unterliegt den folgenden Einschränkungen:  
* Es findet keine Überprüfung der Anzeigenamen der Gruppen statt.  Achten Sie darauf, den Wert im Feld **ANZEIGENAME** zu verwenden, der im Azure-Portal für die Azure AD-Sicherheitsgruppe angezeigt wird.
* Das Erstellen von Gruppen innerhalb von Gruppen wird aktuell nicht unterstützt.  Die angegebenen Azure AD-Sicherheitsgruppen sollten nur Benutzer und keine verschachtelten Gruppen enthalten.


### Schritt 4: Konfigurieren der Statussynchronisierung
Geben Sie in der Option **Statussynchronisierung** den Typ Daten an, die an Intune gesendet werden sollen.  Aktuell müssen Sie sowohl den Gerätestatus als auch den Bedrohungsstatus aktivieren, damit die Lookout-Intune-Integration ordnungsgemäß funktioniert.  Diese sind standardmäßig aktiviert.
### Schritt 5: Konfigurieren von Empfängerinformationen für Fehlerberichts-E-Mails
Geben Sie in der Option **Fehlerverwaltung** die E-Mail-Adresse ein, an die die Fehlerberichte gesendet werden sollen.

![Screenshot der Intune-Seite zur Connector-Fehlerverwaltung](../media/mtp/lookout-mtp-connector-error-notifications.png)

### Schritt 6: Konfigurieren von E-Mail-Benachrichtigungen
Wenn Sie bei Bedrohungen Warnungen per E-Mail erhalten möchten, melden Sie sich bei der [Lookout MTP-Konsole](https://aad.lookout.com) mit dem Benutzerkonto an, das die Benachrichtigungen erhalten soll.  Wechseln Sie zum Modul **System**, wählen Sie auf der Registerkarte **Einstellungen** die gewünschten Benachrichtigungen aus, und setzen Sie sie auf **EIN**. Speichern Sie die Änderungen.

![Screenshot der Seite „Einstellungen“ mit angezeigtem Benutzerkonto](../media/mtp/lookout-mtp-email-notifications.png) Wenn Sie keine E-Mail-Benachrichtigungen mehr empfangen möchten, stellen Sie die Benachrichtigungen auf **AUS**, und speichern Sie Ihre Änderungen.
### Schritt 7: Konfigurieren der Bedrohungsklassifizierung
Lookout MTP klassifiziert verschiedene Typen von Bedrohungen für mobile Geräte. Den [Lookout MTP-Bedrohungsklassifizierungen](http://personal.support.lookout.com/hc/en-us/articles/114094130693) sind Standardrisikostufen zugeordnet. Sie können diese jederzeit gemäß den Anforderungen Ihres Unternehmens ändern.

![Screenshot der Richtlinienseite mit Bedrohung und Klassifikationen](../media/mtp/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> Die hier angegebenen Risikostufen bilden einen wichtigen Aspekt von MTP, da die Intune-Integration die Gerätekompatibilität zur Laufzeit anhand dieser Risikostufen berechnet. Anders ausgedrückt legt der Intune-Administrator eine Regel in der Richtlinie fest, um zu bestimmen, dass ein Gerät nicht kompatibel ist, wenn auf ihm eine aktive Bedrohung mit einer Mindeststufe von gering, mittel oder hoch erkannt wird. Die Richtlinie zur Bedrohungsklassifizierung in MTP bildet unmittelbar die Grundlage zur Berechnung der Gerätekompatibilität in Intune.

## Beobachten der Registrierung
Nachdem das Setup abgeschlossen wurde, beginnt Lookout MTP Azure AD nach Geräten abzufragen, die den angegebenen Registrierungsgruppen entsprechen.  Die Informationen zu den registrierten Geräten befinden sich im Modul „Geräte“.  Der Ausgangsstatus für Geräte wird als „ausstehend“ angezeigt.  Der Gerätestatus ändert sich, sobald die Lookout for Work-App auf dem Gerät installiert, geöffnet und aktiviert wurde.  Details zur Übertragung der Lookout for Work-App per Push an die Geräte finden Sie im Thema [Konfigurieren und Bereitstellen von Lookout for Work-Apps](configure-and-deploy-lookout-for-work-apps.md).
## Nächste Schritte
[Aktivieren der Lookout MTP-Verbindung mit Intune](enable-lookout-mtp-connection-in-intune.md)



<!--HONumber=Sep16_HO2-->


