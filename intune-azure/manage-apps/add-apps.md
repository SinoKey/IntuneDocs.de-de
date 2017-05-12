---
title: "Hinzufügen von Apps zu Microsoft Intune | Microsoft-Dokumentation"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Anhand dieser Vorgehensweisen können Sie Ihre Apps in Intune für die Zuweisung zu Benutzern und Geräten vorbereiten. "
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 529a3e91e1f86129de77df0529f48a42f86a6521
ms.openlocfilehash: 69ae0926631edc00cc2dc12be559d366e1623140
ms.contentlocale: de-de
ms.lasthandoff: 05/11/2017

---

# <a name="how-to-add-an-app-to-microsoft-intune"></a>So fügen Sie eine App zu Microsoft Intune hinzu

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Bevor Sie Apps verwalten und Benutzern zuweisen können, müssen Sie diese in Intune hinzufügen. Intune unterstützt eine ganze Palette unterschiedlicher App-Typen, die Optionen können sich je nach Typ unterscheiden.

Über Intune können Sie folgende App-Typen hinzufügen und zuweisen:

![Von Intune unterstützte App-Typen](./media/app-types.png)

Die folgenden Plattformen werden unterstützt.

- Android Store-Apps
- Branchenspezifische Android-Apps
- iOS Store-Apps
- Branchenspezifische iOS-Apps
- Web-Apps
- Windows Phone 8.1 Store-Apps
- Branchenspezifische Windows Phone-Apps (XAP-Dateien)
- Windows Store-Apps
- Branchenspezifische Windows-Apps (nur MSI-Dateien)

>[!TIP]
> Eine branchenspezifische App ist eine App, die Sie nicht über einen App Store, sondern über die App-Installationsdatei installieren. Um beispielsweise eine branchenspezifische iOS-App zu installieren, fügen Sie die Anwendungsarchivdatei (mit der Erweiterung „.ipa“) hinzu. In der Regel handelt es sich um Apps, die intern geschrieben wurden.

## <a name="before-you-start"></a>Vorbereitung

Beachten Sie die folgenden Punkte, bevor Sie damit beginnen, Apps hinzuzufügen und zuzuweisen.

- Wenn Sie eine App aus einem Store hinzufügen und zuweisen, müssen Endbenutzer über ein Konto bei diesem Store verfügen, um die App installieren zu können.
- Einige von Ihnen zugewiesenen Apps oder Elemente sind möglicherweise von integrierten iOS-Apps abhängig. Wenn Sie z. B. ein Buch aus dem iOS-Store zuweisen, muss die iBooks-App auf dem Gerät vorhanden sein. Wenn Sie die integrierte iBooks-App entfernt haben, können Sie Intune nicht dazu verwenden, sie wieder zu aktivieren.

## <a name="cloud-storage-space"></a>Cloudspeicherplatz
Alle Apps, die Sie mithilfe des Software-Installationsprogrammtyps erstellen (beispielsweise eine branchenspezifische App), werden paketiert und in den Intune-Cloudspeicher hochgeladen. Ein Testabonnement von Intune enthält 2 GB cloudbasierten Speicher, der zum Speichern von verwalteten Apps und Updates verwendet wird. Ein vollständiges Abonnement enthält 20 GB Speicherplatz.

Sie können zusätzlichen Speicher für Intune mit Ihrer ursprünglichen Zahlungsweise erwerben.  Wenn Sie per Rechnung oder Kreditkarte gezahlt haben, besuchen Sie das [Portal zur Abonnementverwaltung](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).  Wenden Sie sich alternativ an Ihren Partner oder Vertriebsmitarbeiter.

Anforderungen für Cloudspeicherplatz:

-   Alle App-Installationsdateien müssen sich im selben Ordner befinden.
-   Die maximale Dateigröße für hochgeladene Dateien beträgt 2 GB.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Erstellen und Bearbeiten von Kategorien für Apps

Mithilfe von App-Kategorien können Sie Apps sortieren, damit Endbenutzer sie einfacher im Unternehmensportal finden können. Sie können einer App auch mehrere Kategorien zuweisen, z.B. **Entwickler-Apps** oder **Kommunikations-Apps**.
Wenn Sie eine App in Intune hinzufügen, können Sie die gewünschte Kategorie auswählen. Verwenden Sie die plattformspezifischen Themen, um eine App hinzuzufügen und Kategorien zuzuweisen. Gehen Sie zum Erstellen und Bearbeiten Ihre eigenen Kategorien folgendermaßen vor:

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Mobile Apps** aus.
4. Wählen Sie in der Workload **Mobile Apps** die Option **Setup** > **App-Kategorien** aus.
5. Auf dem Blatt **App-Kategorien** wird eine Liste der aktuellen Kategorien angezeigt. Wählen Sie eine der folgenden Aktionen aus:
    - **Erstellen einer Kategorie:** Geben Sie auf dem Blatt **Kategorie erstellen** einen Namen für die neue Kategorie ein. Namen können in nur einer Sprache eingegeben werden, und werden von Intune nicht übersetzt. Klicken Sie auf **Erstellen**, wenn Sie fertig sind.
    - **Bearbeiten einer Kategorie:** Wählen Sie für jede Kategorie in der Liste „**...**“ aus. Auf dem Blatt **Eigenschaften** können Sie einen neuen Namen für die Kategorie eingeben oder die Kategorie löschen.


## <a name="apps-added-automatically-by-intune"></a>Von Intune automatisch hinzugefügte Apps

Die folgenden von Microsoft veröffentlichten Apps sind in Intune integriert und können sofort von Ihnen zugewiesen werden:

|||
|-|-|
|Name|Plattform|App-Typ|
|Azure Information Protection|Android|Verwaltete Android Store-App|
|Dynamics CRM für Smartphones|Android|Verwaltete Android Store-App|
|Dynamics CRM für Tablets|Android|Verwaltete Android Store-App|
|Excel|iOS|Verwaltete iOS Store-App|
|Excel|Android|Verwaltete Android Store-App|
|Managed Browser|Android|Verwaltete Android Store-App|
|Managed Browser|iOS|Verwaltete iOS Store-App|
|Microsoft Dynamics CRM auf Smartphones|iOS|Verwaltete iOS Store-App|
|Microsoft Dynamics CRM auf Tablets|iOS|Verwaltete iOS Store-App|
|Microsoft Power BI|iOS|Verwaltete iOS Store-App|
|Microsoft Power BI|Android|Verwaltete Android Store-App|
|Microsoft SharePoint|iOS|Verwaltete iOS Store-App|
|Microsoft SharePoint|Android|Verwaltete Android Store-App|
|Microsoft Teams|Android|Verwaltete Android Store-App|
|Microsoft Teams|iOS|Verwaltete iOS Store-App|
|OneDrive|iOS|Verwaltete iOS Store-App|
|OneDrive|Android|Verwaltete Android Store-App|
|OneNote|iOS|Verwaltete iOS Store-App|
|Outlook|Android|Verwaltete Android Store-App|
|Outlook|iOS|Verwaltete iOS Store-App|
|Outlook-Gruppen|Android|Verwaltete Android Store-App|
|Outlook-Gruppen|iOS|Verwaltete iOS Store-App|
|PowerPoint|iOS|Verwaltete iOS Store-App|

## <a name="next-steps"></a>Nächste Schritte

Wählen Sie eines der folgenden Themen, um zu erfahren, wie Sie Apps für jede Plattform in Intune hinzufügen:

- [Android Store-Apps](android-store-app.md)
- [Android-Branchen-Apps](android-lob-app.md)
- [iOS Store-Apps](ios-store-app.md)
- [iOS-Branchen-Apps](ios-lob-app.md)
- [Web-Apps (für alle Plattformen)](web-app.md)
- [Windows Phone 8.1 Store-Apps](windows-phone-8-1-store-app.md)
- [Branchenspezifische Windows Phone-Apps](windows-phone-line-of-business-app.md)
- [Windows Store-Apps](windows-store-app.md)
- [Branchenspezifische Windows-Apps](windows-line-of-business-app.md)

