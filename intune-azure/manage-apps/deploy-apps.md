---
title: Zuweisen von Apps zu Gruppen
titleSuffix: Intune Azure preview
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
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b372d4ee505ca39a4739069e5798918ecde134ea
ms.openlocfilehash: abf45b835d13ef5fe4acb769194542611448504e
ms.lasthandoff: 02/18/2017

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

## <a name="changes-to-how-you-assign-apps-to-groups-in-the-intune-preview"></a>Änderungen für das Zuweisen von Apps zu Gruppen in der Intune-Vorschau

In Intune in Azure (Vorschau) verwenden Sie nicht länger Intune-Gruppen zum Zuweisen von Apps, sondern Sicherheitsgruppen von Azure Active Directory (Azure AD). Aus diesem Grund müssen Sie einige Änderungen kennen, inwiefern die App-Zuweisung funktioniert, ganz besonders, wenn Sie Apps zu untergeordneten Gruppen von Intune zugewiesen haben.
Es ist sehr wichtig, dass Sie wissen, dass das Konzept der untergeordneten Gruppen nicht in Azure AD existiert. Einige Gruppen können jedoch die gleichen Elemente enthalten. In diesem Fall unterscheidet sich das Verhalten zwischen klassischen Intune und Intune in Azure (Vorschau). Dies wird in der folgenden Tabelle veranschaulicht:

||||||
|-|-|-|-|-|
|**Intune (klassisch) (vor der Mandantenmigration)**|-|**Intune Azure (nach Abschluss der Migration von Mandanten)**|-|**Weitere Informationen**|
|**Bereitstellungsabsicht der übergeordneten Gruppe**|**Bereitstellungsabsicht der untergeordneten Gruppe**|**Resultierende Zuweisungsabsicht für häufige Elemente der vorherigen übergeordneten und untergeordneten Gruppe**|**Resultierende Zuweisungsabsicht für Elemente der übergeordneten Gruppe**|-|    
|Verfügbar|Erforderlich|Erforderlich und Verfügbar|Verfügbar|Erforderlich und Verfügbar bedeutet, dass als erforderlich zugewiesene Apps auch in der Unternehmensportal-App gesehen werden können.
|Nicht zutreffend|Verfügbar|Nicht zutreffend|Nicht zutreffend|Problemlösung: Entfernen Sie die Bereitstellungsabsicht „Nicht zutreffend“ aus der übergeordneten Intune-Gruppe.
|Erforderlich|Verfügbar|Erforderlich und Verfügbar|Erforderlich|-|
|Erforderlich und Verfügbar<sup>1</sup>|Verfügbar|Erforderlich und Verfügbar|Erforderlich und Verfügbar|-|    
|Erforderlich|Nicht zutreffend|Erforderlich|Erforderlich|-|    
|Erforderlich und Verfügbar|Nicht zutreffend|Erforderlich und Verfügbar|Erforderlich und Verfügbar|-|    
|Erforderlich|Deinstallieren|Erforderlich|Erforderlich|-|    
|Erforderlich und Verfügbar|Deinstallieren|Erforderlich und Verfügbar|Erforderlich und Verfügbar|-|
<sup>1</sup> Nur für verwaltete iOS Store-Apps, wenn Sie diese Intune hinzufügen und als „Erforderlich“ bereitstellen, wenn sie automatisch jeweils mit der Absicht „Erforderlich“ und „Verfügbar“ erstellt wurden.

Sie können die folgenden Maßnahmen durchführen, um Bereitstellungskonflikte zu vermeiden:

1.    Wenn Sie zuvor Apps für verknüpfte übergeordnete und untergeordnete Intune-Gruppen bereitgestellt haben, erwägen Sie, diese Bereitstellungen zu entfernen, bevor Ihre Mandantenmigration beginnt.
2.    Entfernen Sie untergeordneten Gruppen von den übergeordneten Gruppen, und erstellen Sie eine neue Gruppe, die die Elemente der alten untergeordnete Gruppe enthält. Sie können dann eine neue App-Bereitstellung zu dieser Gruppe erstellen.
Hinweise: Wenn die vorherige übergeordnete Gruppe „Alle Benutzer“ war, müssen Sie eine neue dynamische Gruppe erstellen, die keine Elemente der untergeordneten Gruppe enthält.
Sie müssen keine Änderungen an Gruppen im [Azure-Portal](https://portal.azure.com/) für Benutzer- und Gerätegruppen durchführen. Das [klassische Azure-Portal](https://manage.windowsazure.com/) erlaubt Ihnen nur Änderungen an den Benutzergruppen.


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

