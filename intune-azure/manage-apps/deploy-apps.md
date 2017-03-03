---
title: Zuweisen von Apps zu Gruppen | Intune in Azure (Vorschau) | Microsoft Docs
description: "Intune in Azure (Vorschau): Nachdem Sie eine App in Intune hinzugefügt haben, sollten Sie sie Gruppen von Benutzern oder Geräten zuweisen."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 638ad0d87c19c9e40e96b42d18e5c4342f40a156
ms.lasthandoff: 02/16/2017

---

# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Zuweisen von Apps zu Gruppen mit Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Nachdem Sie eine App in Intune hinzugefügt haben, sollten Sie sie an Benutzer und Geräte verteilen. Dazu weisen Sie sie zu.

Apps können Geräten zugewiesen werden, und zwar unabhängig davon, ob sie von Intune verwaltet werden. In der folgenden Tabelle werden die verschiedenen Optionen für die Zuweisung von Apps zu Benutzern und Geräten erläutert:

||||
|-|-|-|-|
|&nbsp;|Bei Intune registrierte Geräte|Nicht bei Intune registrierte Geräte|
|Zuweisen zu Benutzern|Ja|Ja|
|Zuweisen zu Geräten|Ja|Nein|
|Zuweisen umschlossener Apps oder von Apps aus dem Intune SDK (für App-Schutzrichtlinien)|Ja|Ja|
|Zuweisen von Apps als verfügbar|Ja|Ja|
|Zuweisen von Apps als erforderlich|Ja|Nein|
|Deinstallieren von Apps|Ja|Ja|
|Endbenutzer installieren verfügbare Apps über die Unternehmensportal-App|Ja|Nein|
|Endbenutzer installieren verfügbare Apps über das webbasierte Unternehmensportal|Ja|Ja|

> [!NOTE]
> Derzeit können Sie iOS- und Android-Apps (Branchen-Apps und Apps aus dem Store) Geräten zuweisen, die nicht bei Intune registriert sind.

## <a name="how-to-assign-an-app"></a>Zuweisen einer App

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Apps verwalten** aus.
1. Wählen Sie in der Workload **Apps verwalten** die Option **Verwalten** > **Apps** aus.
2. Klicken Sie auf dem Blatt mit der Liste der Apps auf die App, die Sie zuweisen möchten.
3. Wählen Sie auf dem Blatt <*App-Name*> – **Übersicht** die Option **Verwalten** > **Zuweisungen** aus.
4. Wählen Sie **Gruppen auswählen** und dann auf dem Blatt **Gruppen auswählen** die Azure AD-Gruppen aus, denen Sie die App zuweisen möchten.
5. Wählen Sie für jede ausgewählte App einen **Zuweisungstyp** aus:
    - **Verfügbar:** Benutzer installieren die App über die Unternehmensportal-App oder -Website.
    - **Nicht verfügbar:** Die App wird nicht installiert und nicht im Unternehmensportal angezeigt.
    - **Erforderlich:** Die App wird auf Geräten in den ausgewählten Gruppen installiert.
    - **Deinstallieren:** Die App wird auf Geräten in den ausgewählten Gruppen deinstalliert.
    - **Verfügbar ohne Registrierung:** Weisen Sie diese App Benutzergruppen zu, deren Geräte nicht bei Intune registriert sind. Hilfe finden Sie in der Tabelle oben.
6. Wählen Sie abschließend **Speichern** aus.

Die App wird jetzt der von Ihnen ausgewählten Gruppe zugewiesen.

Weitere Informationen zum Überwachen von App-Zuweisungen finden Sie unter [Überwachen von Apps](monitor-apps.md).

