---
title: "Überwachen von MAM-Richtlinien mit Microsoft Intune | Microsoft Intune"
description: "Finden Sie heraus, für wie viele Benutzer die Richtlinie gilt, und zeigen Sie weitere Details an."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 07/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 389daf0ed39fa2cd4b2e5d6e52cbd6809a568c9e
ms.openlocfilehash: bc68a13b8d5694908cd00e5e615f81f6e15cfe22


---

# Überwachen der Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune
Nachdem Sie eine MAM-Richtlinie konfiguriert und auf die Benutzer angewendet haben, können Sie den Kompatibilitätsstatus im [Azure-Portal](https://portal.azure.com) überwachen. Das Azure-Portal enthält Informationen über die Benutzer, die von der Richtlinie betroffen sind, den Kompatibilitätsstatus sowie über Probleme, die bei Ihren Endbenutzer möglicherweise auftreten.
## Zusammenfassungsansicht
Auf dem Blatt **Mobile Anwendungsverwaltung mit Intune** sehen Sie eine Zusammenfassung des Kompatibilitätsstatus wie unten beschrieben:


![Kachel „Zusammenfassung“ auf dem Blatt „Mobile Anwendungsverwaltung mit Intune“](../media/mam-azure-portal-user-status-summary.png)

-   **BENUTZER:** Die Gesamtzahl der Benutzer in Ihrem Unternehmen, die die der Richtlinie zugeordneten Apps verwenden.

-   **VERWALTET DURCH RICHTLINIE:** Die Anzahl der Benutzer, die mindestens eine der Apps im Arbeitskontext verwendet haben.

-   **KEINE RICHTLINIE:** Die Anzahl der Benutzer, die die der Richtlinie zugeordneten Apps verwenden, jedoch nicht von der Richtlinie betroffen sind.  Sie sollten erwägen, diese Benutzer der Richtlinie hinzuzufügen.

- **Gekennzeichnete Benutzer:** Die Anzahl der Benutzer, die Probleme feststellen. Derzeit werden nur Benutzer mit per Jailbreak manipulierten Geräten unter **Gekennzeichnete Benutzer** gemeldet.


## Detailansicht
Sie können zur detaillierten Ansicht der Zusammenfassung gelangen, indem Sie auf die Kachel **Benutzerstatus** und dann auf die Kachel **Gekennzeichnete Benutzer** klicken.

### Benutzerstatus
Sie können nach einem einzelnen Benutzer suchen und sich den Kompatibilitätsstatus für diesen Benutzer ansehen. Auf dem Blatt **App-Berichterstellung** werden für einen ausgewählten Benutzer die folgenden Informationen angezeigt:
- Geräte, die dem Benutzerkonto zugeordnet sind
- Apps mit MAM-Richtlinie auf dem Gerät
- Status:

  **Eingecheckt:** Dies bedeutet, dass die Richtlinie für den Benutzer bereitgestellt wurde und dass die App mindestens einmal im Arbeitskontext verwendet wurde.

  **Nicht eingecheckt:** Dies bedeutet, dass die Richtlinie für den Benutzer bereitgestellt wurde, die App seitdem aber nicht im Arbeitskontext verwendet wurde.

>[!NOTE]
> Wenn für den gesuchten Benutzer keine MAM-Richtlinie bereitgestellt wurde, wird Ihnen eine Meldung angezeigt, dass auf den Benutzer keine App-Richtlinien angewendet werden.

Um die Berichterstattung für einen Benutzer anzuzeigen, gehen Sie folgendermaßen vor:

**Schritt 1:** Um einen Benutzer auszuwählen, klicken Sie auf die Kachel „Zusammenfassung“, oder wählen Sie die Option **APP-BERICHTERSTELLUNG NACH BENUTZER** auf dem Blatt **Einstellungen**, wie unten dargestellt:

![Option „App-Berichterstellung“ auf dem Blatt „Einstellungen“](../media/mam-azure-portal-app-reporting-by-user-settings-blade.png)

**Schritt 2:** Daraufhin wird das Blatt **App-Berichterstellung** geöffnet. Wählen Sie **Benutzer auswählen**, um nach einem Azure Active Directory-Benutzer zu suchen.

![Option zum Auswählen des Benutzers auf dem Blatt „App-Berichterstellung“](../media/mam-azure-portal-app-reporting-select-user.png)

**Schritt 3:** Nach dem Auswählen des Benutzers aus der Liste werden die Details des Kompatibilitätsstatus für diesen Benutzer angezeigt.

![Details der App-Berichterstellung](../media/mam-azure-portal-app-reporting-by-user.png)
### Gekennzeichnete Benutzer
In der Detailansicht werden die Fehlermeldung, die App, auf die bei Auftreten des Fehlers zugegriffen wurde, die Plattform des Geräts und ein Zeitstempel angezeigt.  

### Weitere Informationen:
[Verwalten der Datenübertragung zwischen iOS-Apps](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [Was Sie erwartet, wenn Ihre Android-App von MAM-Richtlinien verwaltet wird](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
* [Was Sie erwartet, wenn Ihre iOS-App von MAM-Richtlinien verwaltet wird](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


