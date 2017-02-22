---
title: Einrichten eines TEM-Diensts (Telecom Expense Management) | Intune in Azure (Vorschau) | Microsoft Docs
description: "Intune in Azure (Vorschau): Konfigurieren Sie den Saaswedo-TEM-Dienst für die Integration mit Intune."
keywords: Saaswedo
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: sumitp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 915d61344a3c1d388305dd51b1e2463bd2e32770
ms.openlocfilehash: 8d94fec099e1dc8918077062fb73b94a5973ea96

---

# <a name="set-up-a-telecom-expense-management-service-in-intune-azure-preview"></a>Einrichten eines TEM-Diensts (Telecom Expense Management) in der Vorschau von Intune in Azure
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Die TEM-Lösung (Telecom Expense Management) Datalert des Drittanbieter-Softwareentwicklers Saaswedo wurde in Intune integriert. Datalert ist eine TEM-Software, mit der Sie Ihre Telekommunikationsdatennutzung verwalten und kostenintensive und unerwartete Daten- und Roamingzuschläge für mit Intune verwaltete Geräte vermeiden können. Durch die Intune-Integration mit Datalert können Sie Datennutzungsgrenzwerte im In- und Ausland zentral festlegen, überwachen und erzwingen, sobald definierte Schwellenwerte überschritten werden. Sie können den Dienst so konfigurieren, dass verschiedene Aktionen für Einzelpersonen oder Gruppen von Endbenutzern ausgeführt werden, darunter das Deaktivieren von Roaming, wenn ein Benutzer den Schwellenwert überschreitet. Berichte für Datennutzungs- und Überwachungsinformationen stehen in der Datalert-Verwaltungskonsole zur Verfügung.

Bevor Sie den Datalert-Dienst mit Intune verwenden können, müssen Sie in der Datalert-Konsole und in Intune Einstellungen konfigurieren. Die Verbindung muss für den Datalert-Dienst und für Intune aktiviert werden. Wenn die Datalert-Seite der Verbindung aktiviert ist, aber nicht die Intune-Seite, empfängt Intune die Kommunikation, ignoriert sie jedoch.

>[!NOTE]
>Um dieses Feature in Ihrer Mandantentestversion zu aktivieren und Datalert für die erforderlichen Softwarelizenzen zu unterstützen, [wenden Sie sich an Microsoft Support Services](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

## <a name="supported-platforms"></a>Unterstützte Plattformen

- Samsung KNOX
- iOS 8.0 und höher

## <a name="prerequisites"></a>Voraussetzungen

- Ein Microsoft Intune-Abonnement
- Ein Abonnement des TEM-Diensts Datalert

## <a name="list-of-telecom-expense-management-providers"></a>Liste von TEM-Anbietern

In Intune sind derzeit die folgenden TEM-Anbieter integriert:

[TEM-Dienst Saaswedo Datalert](http://www.datalert.biz/)

## <a name="configure-intune-to-work-with-the-datalert-service"></a>Konfigurieren von Intune für die Arbeit mit dem Datalert-Dienst

 

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Andere** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte konfigurieren** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Setup** > **Telecom Expense Management** aus.
2. Klicken Sie unter **Telecom Expense Management**auf **Verbindungsstatus**.

3. Wählen Sie **Liste der TEM-Dienstanbieter** aus, und wählen Sie dann in der angezeigten Liste Ihren Anbieter aus. Eine spezifische Seite für Ihren Anbieter wird geöffnet. Für Saaswedo wird die Datalert-Seite geöffnet. Sie müssen bei Saaswedo Datalert ein Abonnement erwerben.

4. Gehen Sie in der **Datalert**-Verwaltungskonsole folgendermaßen vor:

    a. Wechseln Sie zur Registerkarte **Einstellungen**, und besuchen Sie den Abschnitt **MDM-Konfiguration**.

    b. Wählen Sie **Entsperren** aus, damit Sie die Einstellungen auf der Seite eingeben können.

    c. Wählen Sie für **Server-MDM** die Option **Microsoft Intune** aus.

    d. Geben Sie für **Mandanten-ID**, geben Sie Ihre Intune-Mandanten-ID ein, und wählen Sie die Schaltfläche **Verbindung** aus. Durch das Auswählen von **Verbindung** überprüft Datalert Intune, um sicherzustellen, dass nicht bereits Verbindungen zwischen Datalert und Intune bestehen. Nach wenigen Sekunden wird eine Microsoft-Anmeldeseite angezeigt, gefolgt von der Datalert-Azure-Authentifizierung.

    e. Wählen Sie auf Microsoft-Authentifizierungsseite **Annehmen** aus. Sie werden zu einer Seite von Datalert mit dem Inhalt „Danke“ umgeleitet, die nach einigen Sekunden geschlossen wird. Datalert überprüft die Verbindung und zeigt grüne Häkchen neben einer Liste von bereits überprüften Elementen an. Wenn bei der Validierung ein Fehler auftritt, wird eine Meldung in Rot angezeigt. In diesem Fall erhalten Sie beim Datalert-Support Hilfe.

5. Warten Sie einige Minuten, wechseln Sie zum Azure-Portal, und vergewissern Sie sich, dass als Status der Verbindung **Aktiv** angezeigt wird. 

    >[!NOTE]
    >Wenn Sie dieses Feature in Ihrem Testmandanten aktivieren möchten, [wenden Sie sich bitte an den Microsoft-Support](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

6. Kehren Sie zur Datalert-Verwaltungskonsole zurück, und konfigurieren Sie Ihre Datenzeilen:

    a. Wechseln Sie zur Registerkarte **Einstellungen**.

    b. Wechseln Sie zum **Setup**-Assistenten, und befolgen Sie die Schritte des Assistenten.



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



<!--HONumber=Feb17_HO2-->


