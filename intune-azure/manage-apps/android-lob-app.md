---
title: "Hinzufügen von Android-Branchen-Apps in Intune | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Erfahren Sie mehr über das Hinzufügen von Android-Branchen-Apps in Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 061d793c-c724-4cd9-9240-adb0cbda5661
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: dbeaabe0f119a0e819857ef7181bbf6de2b1dbd8
ms.lasthandoff: 02/16/2017

---

# <a name="how-to-add-android-line-of-business-lob-apps-to-microsoft-intune"></a>Hinzufügen von branchenspezifischen Android-Apps (LOB) in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="step-1---specify-the-software-setup-file"></a>Schritt 1: Angeben der Softwaresetupdatei

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Apps verwalten** aus.
4. Wählen Sie in der Workload **Mobile Apps** die Option **Verwalten** > **Apps** aus.
5. Wählen Sie über der Liste der Apps **Hinzufügen** aus.
6. Wählen Sie auf dem Blatt **App hinzufügen** die Option **Softwaresetupdatei** aus.
Klicken Sie auf dem Blatt **Setupdatei auswählen** auf die Schaltfläche „Durchsuchen“, suchen Sie die Setupdatei für die Android-App (mit der Erweiterung „.apk“), und klicken Sie dann auf **OK**.

## <a name="step-2---configure-app-information"></a>Schritt 2: Konfigurieren von App-Informationen

1. Wählen Sie auf dem Blatt **App hinzufügen** die Option **App-Informationen** aus.
2. Konfigurieren Sie auf dem Blatt **App bearbeiten** die folgenden Informationen. Klicken Sie abschließend auf **Hinzufügen**. Abhängig von der ausgewählten App werden einige der Werte auf diesem Blatt möglicherweise automatisch ausgefüllt:
    - **App-Name:** Geben Sie den Namen der App ein, wie er im Unternehmensportal angezeigt werden soll. Stellen Sie sicher, dass alle App-Namen eindeutig sind. Wenn ein App-Name zweimal vergeben wird, wird den Benutzern im Unternehmensportal nur eine der Apps angezeigt.
    - **App-Beschreibung:** Geben Sie eine Beschreibung für die App ein. Diese Beschreibung wird den Benutzern im Unternehmensportal angezeigt.
    - **Herausgeber:** Geben Sie den Namen des Herausgebers der App ein.
    - **Mindestens erforderliches Betriebssystem:** Wählen Sie in der Liste die mindestens erforderliche Betriebssystemversion aus, auf der die App installiert werden kann. Wenn Sie die App einem Gerät mit einem älteren Betriebssystem zuweisen, wird sie nicht installiert.
    - **Kategorie (optional):** Wählen Sie eine der integrierten oder von Ihnen erstellten App-Kategorien aus. Dadurch wird es für die Benutzer leichter, die App im Unternehmensportal zu finden.
    - **Diese App als ausgewählte App im Unternehmensportal anzeigen:** Zeigen Sie die App auf der Hauptseite des Unternehmensportal hervorgehoben an, wenn Benutzer nach Apps suchen.
    - **Informations-URL:** Geben Sie optional eine URL zu einer Website ein, die Informationen über diese App enthält. Diese URL wird den Benutzern im Unternehmensportal angezeigt.
    - **URL zu den Datenschutzbestimmungen:** Geben Sie optional eine URL zu einer Website ein, die Datenschutzinformationen für diese App enthält. Diese URL wird den Benutzern im Unternehmensportal angezeigt.
    - **Entwickler:** Geben Sie optional den Namen des App-Entwicklers ein.
    - **Besitzer:** Geben Sie optional einen Namen für den Besitzer dieser App ein, z.B. **Personalabteilung**.
    - **Anmerkungen:** Geben Sie Hinweise zu dieser App ein.
    - **Symbol hochladen:** Laden Sie ein Symbol hoch, das der App zugeordnet wird. Dies ist das Symbol, das gemeinsam mit der App angezeigt wird, wenn die Benutzer das Unternehmensportal durchsuchen.
3. Wenn Sie fertig sind, wählen Sie auf dem Blatt **App hinzufügen** die Option **Speichern** aus.

Die von Ihnen erstellte App wird in der Liste der Apps angezeigt, in der Sie sie ausgewählten Gruppen zuweisen können. Hilfe finden Sie unter [Zuweisen von Apps zu Gruppen](/intune-azure/manage-apps/deploy-apps).

