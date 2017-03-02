---
title: Einrichten eines TEM-Diensts (Telecom Expense Management)
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Konfigurieren Sie den Saaswedo-TEM-Dienst für die Integration mit Intune."
keywords: Saaswedo
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: sumitp
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: aa2e668641da1a87e6145fe826d88c2ca5b184a2
ms.lasthandoff: 02/18/2017

---

# <a name="set-up-a-telecom-expense-management-service-in-intune-azure-preview"></a>Einrichten eines TEM-Diensts (Telecom Expense Management) in der Vorschau von Intune in Azure
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune ermöglicht es Ihnen, durch Datenverwendung auf firmeneigenen mobilen Geräten Telekommunikationsausgaben zu verwalten. Die TEM-Lösung Datalert des Drittanbieter-Softwareentwicklers Saaswedo wurde in Intune integriert, um diese Funktion zu aktivieren. Datalert ist eine TEM-Software, mit der Sie Ihre Telekommunikationsdatennutzung verwalten und kostenintensive und unerwartete Daten- und Roamingzuschläge für mit Intune verwaltete Geräte vermeiden können. 

Durch die Intune-Integration mit Datalert können Sie Datennutzungsgrenzwerte im In- und Ausland zentral festlegen, überwachen und erzwingen, sobald definierte Schwellenwerte überschritten werden. Sie können den Dienst so konfigurieren, dass verschiedene Aktionen für Einzelpersonen oder Gruppen von Endbenutzern ausgeführt werden, darunter das Deaktivieren von Roaming, wenn ein Benutzer den Schwellenwert überschreitet. Berichte für Datennutzungs- und Überwachungsinformationen stehen in der Datalert-Verwaltungskonsole zur Verfügung.

Das folgende Diagramm zeigt, wie Intune mit Datalert integriert.

  ![Diagramm der Integration von Intune und Datalert](../media/tem-datalert-intune-solution-diagram.png)

Bevor Sie den Datalert-Dienst mit Intune verwenden können, müssen Sie in der Datalert-Konsole und in Intune Einstellungen konfigurieren. Die Verbindung muss für den Datalert-Dienst und für Intune aktiviert werden. Wenn die Datalert-Seite der Verbindung aktiviert ist, aber nicht die Intune-Seite, empfängt Intune die Kommunikation, ignoriert sie jedoch.

## <a name="supported-platforms"></a>Unterstützte Plattformen

- Samsung KNOX
- iOS 8.0 und höher

## <a name="prerequisites"></a>Voraussetzungen

- Ein Abonnement für Microsoft Intune und Zugriff auf das Azure-Portal, das sich derzeit in öffentlicher Vorschau befindet.
- Ein Abonnement des TEM-Diensts Datalert

## <a name="list-of-telecom-expense-management-providers"></a>Liste von TEM-Anbietern

In Intune sind derzeit die folgenden TEM-Anbieter integriert:

[TEM-Dienst Saaswedo Datalert](http://www.datalert.biz/)

## <a name="deploy-the-intune-and-datalert-integrated-solution"></a>Bereitstellen von integrierten Intune- und Datalertlösungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie bereits ein TEM-Dienst-Abonnement für Intune und Datalert haben.

### <a name="step-1-connect-the-datalert-service-to-microsoft-intune"></a>Schritt 1: Verbinden des Datalert-Diensts mit Microsoft Intune

1. Melden Sie sich in der Datalert-Verwaltungskonsole mit Ihren Administratoranmeldeinformationen an.

2. Gehen Sie in der Datalert-Verwaltungskonsole zur Registerkarte **Einstellungen** und anschließend zu **MDM-Konfiguration**.

3. Wählen Sie **Blockierung aufheben** aus, damit Sie die Einstellungen auf der Seite eingeben können.

4. Wählen Sie für **Server-MDM** die Option **Microsoft Intune** aus.

5. Geben Sie für die **Azure AD-Domäne** Ihre Azure-Mandanten-ID ein, und wählen Sie dann die Schaltfläche **Verbindung**.

    Durch das Auswählen von **Verbindung** überprüft Datalert Intune, um sicherzustellen, dass nicht bereits Verbindungen zwischen Datalert und Intune bestehen. Nach wenigen Sekunden wird eine Microsoft-Anmeldeseite angezeigt, gefolgt von der Datalert-Azure-Authentifizierung.

6. Wählen Sie auf Microsoft-Authentifizierungsseite **Annehmen** aus. Sie werden zu einer Seite von Datalert mit dem Inhalt „Danke“ umgeleitet, die nach einigen Sekunden geschlossen wird. Datalert überprüft die Verbindung und zeigt grüne Häkchen neben einer Liste von bereits überprüften Elementen an. Wenn bei der Validierung ein Fehler auftritt, wird eine Meldung in Rot angezeigt. In diesem Fall erhalten Sie beim Datalert-Support Hilfe.

    Der folgende Screenshot zeigt die grünen Häkchen, die angezeigt werden, sobald die Verbindung erfolgreich aufgebaut wurde.

  ![Die Datalert-Seite, die eine erfolgreiche Verbindung anzeigt](../media/tem-mdm-configuration-mdm-server-page.png)

### <a name="step-2-check-that-the-telecom-expense-management-feature-is-active-in-intune"></a>Schritt 2: Überprüfen Sie, ob die TEM-Funktion in Intune „Aktiv“ ist

Nach Abschluss von Schritt 1 sollte die Verbindung automatisch aktiviert werden und der Verbindungsstatus **Aktiv** im Azure-Portal angezeigt werden. Diese Schritte zeigen Ihnen, wie Sie auf den Status **Aktiv** prüfen.

1. Melden Sie sich im Azure-Portal an.

2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte konfigurieren** aus.

4. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Setup** > **Telecom Expense Management** aus. 

   Suchen Sie nach dem Verbindungsstatus **Aktiv** oben auf der Seite.

  ![Das Azure-Portal mit Verbindungsstatus „aktiv“ für Datalert](../media/tem-azure-portal-enable-service.png)

### <a name="step-3-deploy-the-datalert-app-to-corporate-enrolled-devices"></a>Schritt 3: Bereitstellen der Datalert-App für in Unternehmen registrierte Geräte

Um sicherzustellen, dass die Datennutzung nur von firmeneigenen Leitungen gesammelt wird, müssen Sie Gerätekategorien in Intune erstellen und dann die Datalert-App nur für Firmentelefone zum Ziel stellen. Führen Sie die Schritte in folgenden Unterabschnitten durch.

#### <a name="define-device-categories-and-device-groups-mapped-to-the-categories"></a>Definieren Sie Gerätekategorien und Gerätegruppen, die den Kategorien zugeordnet sind

Abhängig von Ihren organisatorischen Bedürfnissen müssen Sie mindestens zwei Gerätekategorien (z.B. Unternehmen und Privat) und dynamische Gerätegruppen für jede Kategorie erstellen. Sie können je nach Bedarf weitere Kategorien für Ihre Organisation erstellen. 

Diese Kategorien werden Benutzern während der Registrierung angezeigt. Je nachdem, welche Kategorie Benutzer auswählen, wird das registrierte Gerät in die entsprechende Gerätegruppe verschoben. Anweisungen zum Erstellen von Gerätekategorien finden Sie unter [Zuweisen von Geräten zu Gruppen](https://docs.microsoft.com/intune-azure/enroll-devices/how-to-use-device-group-mapping).

  ![Screenshot des Blatts „Richtlinie hinzufügen“](../media/tem-dynamic-membership-rules.png)

#### <a name="create-the-datalert-app-in-intune"></a>Erstellen einer Datalert-App in Intune

Um die Datalert-App in Intune für jede Plattform zu erstellen, gehen Sie wie folgt vor. iOS wird in den folgenden Schritten als Beispiel verwendet.

1. Wählen Sie im Azure-Portal auf dem Blatt **Intune** die Option **Apps verwalten** aus.

2. Wählen Sie auf dem Blatt **App verwalten** die Option **Verwalten** > **Apps** aus. 

3. Wählen Sie **Hinzufügen** aus, um eine App hinzuzufügen.

4. Wählen Sie den Anwendungstyp aus. Für iOS würden Sie zum Beispiel **iOS Store-App** auswählen.

5. Suchen Sie unter **App Store durchsuchen** nach der Datalert-App, indem Sie **Dataltert** in das Suchfenster eingeben.

6. Wählen Sie die **Datalert**-App und dann **OK** aus.

  ![Screenshot des Blatts „Richtlinie hinzufügen“](../media/tem-select-app-from-apple-app-store.png)

7. Schließen Sie die verbleibenden Schritte zum Erstellen einer App für iOS ab.

  ![Screenshot des Blatts „Richtlinie hinzufügen“](../media/tem-steps-to-create-the-app.png)

#### <a name="assign-the-datalert-app-to-the-corporate-device-group"></a>Zuweisen der Datalert-App zur Unternehmensgerätegruppe

1. Wählen Sie die Datalert-App für iOS aus, die Sie im vorherigen Schritt erstellt haben.

2. Gehen Sie auf dem **Apps**-Blatt zu **Verwalten** > **Zuweisungen**. 

3. Wählen Sie **Gruppen auswählen** aus, und befolgen Sie die Schritte zum Auswählen der Unternehmensgerätegruppe.

4. Legen Sie fest, ob die Installation der App für die Gruppe erforderlich oder optional ist. Auf dem folgenden Beispiel-Screenshot wird die Installation als erforderlich angezeigt, was bedeutet, dass Benutzer die Datalert-App nach der Registrierung ihres Geräts installieren müssen.

  ![Screenshot des Blatts „Richtlinie hinzufügen“](../media/tem-assign-datalert-app-to-device-group.png)

### <a name="step-4-add-corporate-paid-phone-lines-to-the-datalert-console"></a>Schritt 4: Hinzufügen von kostenpflichtigen Firmentelefonleitungen zur Datalert-Konsole 

Sie haben nun die Intune- und Datalert-Dienste so konfiguriert, dass sie miteinander kommunizieren können. Sie müssen jetzt die kostenpflichtigen Firmentelefonleitungen zur Datalert-Konsole hinzufügen und Schwellenwerte und Aktionen für alle Funk- oder Roaming-Verwendungsverstöße definieren. 

Um diese Elemente festzulegen, gehen Sie zur [Datalert-Setup für Microsoft Intune Seite](http://www.datalert.fr/microsoft-intune/intune-setup) (http://www.datalert.fr/microsoft-intune/intune-setup), und führen Sie unter der Registerkarte **Einstellungen** die Schritte im Setup-Assistenten aus.

  ![Screenshot des Blatts „Richtlinie hinzufügen“](../media/tem-add-phone-lines-to-datalert-console.png)


Der Datalert-Dienst ist jetzt aktiv, und es wird damit begonnen, die Datennutzung zu überwachen und auf Geräten, die die Verwendung der konfigurierten Grenzwerte überschreiten, Mobilfunk- und Roamingdaten zu deaktivieren.

## <a name="turning-off-the-datalert-service"></a>Deaktivieren des Datalert-Diensts

Wenn Sie den Datalert-Dienst im Azure-Portal zu deaktivieren, geschieht Folgendes:

- Alle Aktionen, die aufgrund vergangener Verstöße gegen die Nutzungsgrenzwerte auf Geräte angewendet wurden, werden rückgängig gemacht.
- Datenzugriffe und Roaming werden für Benutzer nicht mehr blockiert.
- Intune weiterhin empfängt die Signale vom Dienst, ignoriert diese jedoch.

**So deaktivieren Sie den Dienst**

1. Wählen Sie auf dem Blatt **Telecom Expense Management** im Azure-Portal die Option **Deaktivieren** aus.

2. Wählen Sie **Speichern** aus.

## <a name="viewing-data-usage-and-roaming-reports"></a>Anzeigen der Datennutzungs- und Roamingberichte

Zum aktuellen Zeitpunkt sind Nutzungsberichte nur in der Datalert-Verwaltungskonsole von Saaswedo verfügbar.

Die Anweisungen, denen Ihre Endbenutzer befolgen, um die Datalert-App zu installieren, werden bald verfügbar sein.
