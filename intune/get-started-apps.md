---
title: Erste Schritte mit Apps
titleSuffix: Intune on Azure
description: "Suchen Sie Apps, und fügen Sie sie auf Geräten hinzu, um Ihren Mitarbeitern die Arbeit zu erleichtern."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7ac2a6f027a78c6b0093a0d299a7cae3265e5954
ms.sourcegitcommit: 45204e0fb8cb4cce449e65f2f1d7bb6f6ac4ccf5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2017
---
# <a name="get-started-with-adding-apps"></a>Erste Schritte mit dem Hinzufügen von Apps

Intune unterstützt einige unterschiedliche Bereitstellungsmethoden für Apps auf Ihren Unternehmensgeräten:

* **Softwareinstallationsprogramme**: Hochladen einer heruntergeladenen Datei auf das Gerät Ihres Benutzers
* __Externe Links__: für eine App in einem öffentlichen App-Store oder eine Web-App
* **Verwaltete Apps**: für iOS-Geräte, für die zusätzliche mobile Anwendungsverwaltung für im App-Store verfügbare Apps erforderlich ist

Eine der schnelleren Bereitstellungsmethoden für Apps ist das Zuweisen einer öffentlichen Store-App.

## <a name="how-do-i-assign-a-public-store-app"></a>Wie weise ich eine öffentliche Store-App zu?

1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.
2. Suchen Sie über **Ressourcen durchsuchen** nach **Intune**.
3. Klicken Sie auf **Mobile Apps** und dann auf **Apps**.
4. Klicken Sie auf **Hinzufügen**, und wählen Sie dann **iOS Store-App** als **App-Typ** aus.
5. Suchen Sie über das Textfeld nach einer App, die Sie dem Gerät zuweisen können. Wählen Sie die App, und klicken Sie dann auf **OK**.
6. Klicken Sie auf dem Blatt **App hinzufügen** auf **App-Information**, und stellen Sie dann sicher, dass alle App-Informationen ausgefüllt wurden. Sie können andere optionale Details hinzufügen, um diese App zu organisieren, wie z.B. **Besitzer**, **Anmerkungen**, **Entwickler** und **URL zu den Datenschutzbestimmungen** für die Datenschutzrichtlinie Ihres Unternehmens.
7. Achten Sie darauf, dass Sie für „Als empfohlene App anzeigen“ „Ja“ im Unternehmensportal ausgewählt haben, und klicken Sie dann auf „OK“.
8. Klicken Sie auf **Hinzufügen**, um eine App hinzuzufügen. Dann werden Sie zur **Übersicht** der App weitergeleitet. Klicken Sie auf **Zuweisungen** und dann auf **Gruppe auswählen**, um sie Ihrer Testgruppe hinzuzufügen. Machen Sie die App zum Herunterladen **verfügbar**. Dann sollte die App als **Empfohlene App** auf Ihrem Testgerät angezeigt werden.

## <a name="learn-more"></a>Weitere Informationen

* [Was ist die Microsoft Intune App-Verwaltung?](app-management.md)
* [Übersicht über den App-Lebenszyklus](app-lifecycle.md)
* [Was sind App-Schutzrichtlinien?](app-protection-policy.md)
