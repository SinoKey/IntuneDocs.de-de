---
title: "Hinzufügen von Apps in Windows Intune | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Anhand dieser Vorgehensweisen können Sie Ihre Apps in Intune für die Zuweisung zu Benutzern und Geräten vorbereiten. "
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 472e65be196d1090e89b46271bb97a82b6fb1a9c
ms.lasthandoff: 02/16/2017

---

# <a name="how-to-add-an-app-to-microsoft-intune"></a>So fügen Sie eine App zu Microsoft Intune hinzu

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Bevor Sie Apps verwalten und Benutzern zuweisen können, müssen Sie diese in Intune hinzufügen. Intune unterstützt eine ganze Palette unterschiedlicher App-Typen, die Optionen können sich je nach Typ unterscheiden.

Intune unterstützt das Hinzufügen und Zuweisen der folgenden App-Typen:

![Von Intune unterstützte App-Typen](./media/app-types.png)

Die folgenden Plattformen werden unterstützt. Klicken Sie auf eines der Themen, um weitere Informationen zum Hinzufügen der einzelnen App-Typen zu erhalten.

- [Branchenspezifische Android-Apps](/intune-azure/manage-apps/android-lob-app)
- [Android Store-Apps](/intune-azure/manage-apps/android-store-app)
- [Branchenspezifische iOS-Apps](/intune-azure/manage-apps/ios-lob-app)
- [iOS Store-Apps](/intune-azure/manage-apps/ios-store-app)
- [Web-Apps (für alle Plattformen)](/intune-azure/manage-apps/web-app)
- [Windows Phone 8.1 Store-Apps](/intune-azure/manage-apps/windows-phone-8-1-store-app)
- [Windows Store-Apps](/intune-azure/manage-apps/windows-store-app)

> [!NOTE]
> Wenn Sie eine App aus einem Store hinzufügen und bereitstellen, müssen Endbenutzer über ein Konto bei diesem Store verfügen, um die App installieren zu können.

## <a name="cloud-storage-space"></a>Cloudspeicherplatz
Alle Apps, die Sie mithilfe des Software-Installationsprogrammtyps erstellen (beispielsweise eine branchenspezifische App), werden verpackt und in den Microsoft Intune-Cloudspeicher hochgeladen. Ein Testabonnement von Intune enthält 2 GB cloudbasierten Speicher, der zum Speichern von verwalteten Apps und Updates verwendet wird. Ihr vollständiges Abonnement enthält 20 GB Speicherplatz.

Sie können zusätzlichen Speicher für Intune mit Ihrer ursprünglichen Zahlungsweise erwerben.  Wenn Sie per Rechnung oder Kreditkarte gezahlt haben, besuchen Sie das [Portal zur Abonnementverwaltung](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).  Wenden Sie sich alternativ an Ihren Partner oder Vertriebsmitarbeiter.

Anforderungen für Cloudspeicherplatz:

-   Alle App-Installationsdateien müssen sich im selben Ordner befinden.
-   Die maximale Dateigröße für hochgeladene Dateien beträgt 2 GB.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Erstellen und Bearbeiten von Kategorien für Apps 

Mithilfe von App-Kategorien können Sie Apps sortieren, damit Endbenutzer sie einfacher im Unternehmensportal finden können. Sie können einer App auch mehrere Kategorien zuweisen, z.B. **Entwickler-Apps** oder **Kommunikations-Apps**. Wenn Sie eine App in Intune hinzufügen, können Sie die gewünschte Kategorie auswählen. Verwenden Sie die plattformspezifischen Themen, um eine App hinzuzufügen und Kategorien zuzuweisen. Gehen Sie zum Erstellen und Bearbeiten Ihre eigenen Kategorien folgendermaßen vor: 

1. Melden Sie sich beim Azure-Portal an. 
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus. 
3. Wählen Sie auf dem Blatt **Intune** die Option **Apps verwalten** aus. 
4. Wählen Sie in der Workload **Mobile Apps** die Option **Setup** > **App-Kategorien** aus. 
5. Auf dem Blatt **App-Kategorien** wird eine Liste der aktuellen Kategorien angezeigt. Wählen Sie eine der folgenden Aktionen aus: 
    - **Erstellen einer Kategorie:** Geben Sie auf dem Blatt **Kategorie erstellen** einen Namen für die neue Kategorie ein. Namen können in nur einer Sprache eingegeben werden, und werden von Intune nicht übersetzt. Klicken Sie auf **Erstellen**, wenn Sie fertig sind.
    - **Bearbeiten einer Kategorie:** Wählen Sie für jede Kategorie in der Liste „**...**“ aus. Auf dem Blatt **Eigenschaften** können Sie einen neuen Namen für die Kategorie eingeben oder die Kategorie löschen.




