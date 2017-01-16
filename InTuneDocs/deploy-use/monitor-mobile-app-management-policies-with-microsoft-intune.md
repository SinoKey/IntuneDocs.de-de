---
title: "Überwachen von MAM-Richtlinien mit Microsoft Intune | Microsoft-Dokumentation"
description: "Finden Sie heraus, für wie viele Benutzer die Richtlinie gilt, und zeigen Sie weitere Details an."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9e208608d50c9b5f7fe66743de0d3c7e741dbfbd
ms.openlocfilehash: 2a18ad7226c6fc6de0277f1f20443ea64dc8b918


---

# <a name="monitor-mobile-app-management-policies-with-microsoft-intune"></a>Überwachen der Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Nachdem Sie eine MAM-Richtlinie (Mobile App Management, Verwaltung mobiler Apps) eingerichtet und auf Benutzer angewendet haben, können Sie den Kompatibilitätsstatus im [Azure-Portal](https://portal.azure.com) überwachen. Das Azure-Portal enthält Informationen über die Benutzer, die von der Richtlinie betroffen sind, den Kompatibilitätsstatus sowie über Probleme, die bei den Benutzern möglicherweise auftreten.
## <a name="summary-view"></a>Zusammenfassungsansicht
Auf dem Blatt **Mobile Anwendungsverwaltung mit Intune** sehen Sie eine Zusammenfassung des Kompatibilitätsstatus:


![Kachel „Zusammenfassung“ auf dem Blatt „Mobile Anwendungsverwaltung mit Intune“](../media/mam-azure-portal-user-status-summary.png)

-   **Benutzer:** Die Gesamtzahl von Benutzern in Ihrem Unternehmen, die die der Richtlinie zugeordneten Apps verwenden.

-   **VERWALTET DURCH RICHTLINIE:** Die Anzahl von Benutzern, die mindestens eine der Apps im Arbeitskontext verwendet haben.

-   **KEINE RICHTLINIE:** Die Anzahl von Benutzern, die die der Richtlinie zugeordneten Apps verwenden, jedoch nicht von der Richtlinie betroffen sind. Sie sollten erwägen, diese Benutzer zur Richtlinie hinzuzufügen.

- **Gekennzeichnete Benutzer:** Die Anzahl von Benutzern, die Probleme feststellen. Derzeit werden nur Benutzer mit per Jailbreak manipulierten Geräten unter **Gekennzeichnete Benutzer** gemeldet.


## <a name="detailed-view"></a>Detailansicht
Sie können zur detaillierten Ansicht der Zusammenfassung gelangen, indem Sie auf die Kachel **Benutzerstatus** und dann auf die Kachel **Gekennzeichnete Benutzer** klicken.

### <a name="user-status"></a>Benutzerstatus
Sie können nach einem einzelnen Benutzer suchen und den Kompatibilitätsstatus für diesen Benutzer überprüfen. Auf dem Blatt **App-Berichterstellung** werden für einen ausgewählten Benutzer die folgenden Informationen angezeigt:
- Geräte, die dem Benutzerkonto zugeordnet sind

- Apps mit MAM-Richtlinie auf dem Gerät

- Status:

  - **Eingecheckt:** Die Richtlinie wurde für den Benutzer bereitgestellt, und die App wurde mindestens einmal im Arbeitskontext verwendet.

  - **Nicht eingecheckt:** Die Richtlinie wurde für den Benutzer bereitgestellt, die App seitdem aber nicht im Arbeitskontext verwendet.

>[!NOTE]
> Wenn für den gesuchten Benutzer keine MAM-Richtlinie bereitgestellt wurde, wird Ihnen eine Meldung angezeigt, dass auf den Benutzer keine App-Richtlinien angewendet werden.

Um die Berichterstattung für einen Benutzer anzuzeigen, gehen Sie folgendermaßen vor:

1.  Um einen Benutzer auszuwählen, klicken Sie auf die Kachel **Zusammenfassung**, oder wählen Sie auf dem Blatt **Einstellungen** die Option **APP-BERICHTERSTELLUNG NACH BENUTZER**:

    ![Option „App-Berichterstellung“ auf dem Blatt „Einstellungen“](../media/mam-azure-portal-app-reporting-by-user-settings-blade.png)

2. Wählen Sie auf dem Blatt **App-Berichterstellung**, das geöffnet wird, **Benutzer auswählen**, um nach einem Azure Active Directory-Benutzer zu suchen.

    ![Option „Benutzer auswählen“ auf dem Blatt „App-Berichterstellung“](../media/mam-azure-portal-app-reporting-select-user.png)

3. Wählen Sie den Benutzer in der Liste aus. Es werden Details zum Kompatibilitätsstatus für diesen Benutzer angezeigt.

    ![Details der App-Berichterstellung](../media/mam-azure-portal-app-reporting-by-user.png)

### <a name="flagged-users"></a>Gekennzeichnete Benutzer
In der Detailansicht werden die Fehlermeldung, die App, auf die bei Auftreten des Fehlers zugegriffen wurde, die Plattform des Geräts und ein Zeitstempel angezeigt.  

### <a name="see-also"></a>Weitere Informationen:
[Verwalten der Datenübertragung zwischen iOS-Apps](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [Was Sie erwartet, wenn Ihre Android-App von MAM-Richtlinien verwaltet wird](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
* [Was Sie erwartet, wenn Ihre iOS-App von MAM-Richtlinien verwaltet wird](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)



<!--HONumber=Dec16_HO3-->


