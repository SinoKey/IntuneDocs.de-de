---
title: "Löschen verwalteter Unternehmens-App-Daten | Microsoft Intune"
description: "Erfahren Sie, wie Sie selektiv Unternehmensdaten von Geräten entfernen können."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2742e1d5-d2d5-42cd-b719-665dd6e0a0e9
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: be1ebcdf2514e45d383dd49890e0e21acf6ede44
ms.openlocfilehash: 3d52345b043115185e667c41d3f09d8257792002


---

# Löschen verwalteter Unternehmensdaten aus Apps mit Microsoft Intune
Wenn ein Gerät verloren geht oder gestohlen wird oder wenn der Mitarbeiter das Unternehmen verlässt, müssen Sie sicherstellen, dass Unternehmensdaten in Apps vom Gerät entfernt werden. Allerdings sollten Sie persönliche Daten nicht vom Gerät entfernen, insbesondere dann nicht, wenn das Gerät dem Mitarbeiter gehört.

Um Unternehmensdaten aus Apps selektiv zu entfernen, erstellen Sie mithilfe der Schritte im Abschnitt **Erstellen einer Zurücksetzungsanforderung** in diesem Thema eine Zurücksetzungsanforderung.  Nach Abschluss der Anforderung werden die Unternehmensdaten beim nächsten Ausführen der Anwendung aus der App entfernt.
>[!NOTE]
> Direkt aus der App mit dem nativen Adressbuch synchronisierte Kontakte werden entfernt. Kontakte, die aus dem nativen Adressbuch mit einer anderen externen Quelle synchronisiert werden, können nicht zurückgesetzt werden. Dies gilt derzeit nur für die Microsoft Outlook-App.



## Erstellen einer Zurücksetzungsanforderung

1.  Wählen Sie auf dem Blatt **Mobile Anwendungsverwaltung mit Intune** die Kachel **Zurücksetzungsanforderungen** aus.

    ![Screenshot des Blatts „Mobile Anwendungsverwaltung mit Intune“ mit der Kachel „Zusammenfassung“](../media/AppManagement/AzurePortal_MAM_WipeRequests.png)

2.  Wählen Sie **Neue Zurücksetzungsanforderung**.

    ![Screenshot des Blatts „Neue Zurücksetzungsanforderung“](../media/AppManagement/AzurePortal_MAM_NewWipeRequest.png)

3.  Wählen Sie auf dem Blatt **Neue Zurücksetzungsanforderung** die Option **Benutzer** aus, um das Blatt **Benutzer** zu öffnen und den Benutzer auszuwählen, dessen App-Daten gelöscht werden sollen.

4.  Wählen Sie **Gerät** aus.  Daraufhin wird das Blatt **Gerät** geöffnet, auf dem alle dem ausgewählten Benutzer zugeordneten Geräte aufgeführt sind.  Wählen Sie das Gerät aus, das zurückgesetzt werden soll.

5.  Sie befinden sich nun wieder auf dem Blatt **Neue Zurücksetzungsanforderung**. Wählen Sie **OK** aus, um eine Zurücksetzungsanforderung zu erstellen. Der Dienst erstellt für jede geschützte App auf dem Gerät eine separate Löschanforderung und überwacht diese.


![Screenshot der Kachel „Zurücksetzungsanforderungen“ ](../media/AppManagement/AzurePortal_MAM_WipeRequestsSummary.png)

## Überwachen der Löschanforderungen
Auf dem Blatt **Intune Mobile Application Management** enthält die Kachel **Löschanforderung** einen zusammenfassenden Bericht.  Angezeigt wird der Gesamtstatus mit der Anzahl der ausstehenden Anforderungen und Fehlern. Weitere Informationen erhalten Sie mithilfe der im Folgenden beschriebenen Schritte:

1.  Wählen Sie auf dem Blatt **Mobile Anwendungsverwaltung mit Intune** die Kachel **Zurücksetzungsanforderung** aus, um das Blatt **Zurücksetzungsanforderung** zu öffnen.

2.  Auf dem Blatt **Löschanforderung** wird eine Liste mit Ihren Anforderungen, gruppiert nach Benutzer, angezeigt.  Da das System für jede geschützte App, die auf dem Gerät ausgeführt wird, eine Löschanforderung erstellt, werden möglicherweise für einen Benutzer mehrere Anforderungen angezeigt.  Der Status gibt an, ob eine Löschanforderung noch **aussteht**oder **fehlgeschlagen**ist bzw. **erfolgreich**ausgeführt wurde.

### Weitere Informationen:
[Schützen von App-Daten mithilfe der Verwaltungsrichtlinien für mobile Apps ](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Verwenden des Azure-Portals](azure-portal-for-microsoft-intune-mam-policies.md)



<!--HONumber=Jul16_HO5-->


