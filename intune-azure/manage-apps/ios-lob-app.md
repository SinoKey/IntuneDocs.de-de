---
title: "Hinzufügen von iOS-Branchen-Apps in Intune"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie mehr über das Hinzufügen von iOS-Branchen-Apps in Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 099101e8-4b22-40ac-ba19-82ba5c71944c
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 141207ac61aade0816a66eb6e672596416bc0906
ms.lasthandoff: 02/18/2017

---

# <a name="how-to-add-ios-line-of-business-lob-apps-to-microsoft-intune"></a>Hinzufügen von branchenspezifischen iOS-Apps in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="step-1---specify-the-software-setup-file"></a>Schritt 1: Angeben der Softwaresetupdatei

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen sie auf dem Blatt „Intune“ die Option **Manage Apps** (Verwalten von Apps) aus.
4. Wählen Sie in der Workload **Mobile Apps** die Option „Verwalten“ > **Apps** aus.
5. Wählen Sie über der Liste der Apps **Hinzufügen** aus.
6. Wählen Sie auf dem Blatt **App hinzufügen** die Option **Softwaresetupdatei** aus.
7. Klicken Sie auf dem Blatt **Setupdatei auswählen** auf die Schaltfläche „Durchsuchen“, suchen Sie die Setupdatei für die iOS-App (mit der Erweiterung „.ipa“), und klicken Sie dann auf **OK**.

## <a name="step-2---configure-app-information"></a>Schritt 2: Konfigurieren von App-Informationen

1. Konfigurieren Sie auf dem Blatt **App bearbeiten** die folgenden Informationen. Klicken Sie abschließend auf **Hinzufügen**. Abhängig von der ausgewählten App werden einige der Werte auf diesem Blatt möglicherweise automatisch ausgefüllt:
    - **App-Name:** Geben Sie den Namen der App ein, wie er im Unternehmensportal angezeigt werden soll. Stellen Sie sicher, dass alle App-Namen eindeutig sind. Wenn ein App-Name zweimal vergeben wird, wird den Benutzern im Unternehmensportal nur eine der Apps angezeigt.
    - **App-Beschreibung:** Geben Sie eine Beschreibung für die App ein. Diese Beschreibung wird den Benutzern im Unternehmensportal angezeigt.
    - **Herausgeber:** Geben Sie den Namen des Herausgebers der App ein.
    - **Anwendbarer Gerätetyp:** Wählen Sie aus, ob diese App auf iPads, iPhones oder kompatiblen iPods installiert werden kann.
    - **Mindestens erforderliches Betriebssystem:** Wählen Sie in der Liste die mindestens erforderliche Betriebssystemversion aus, auf der die App installiert werden kann. Wenn Sie die App einem Gerät mit einem älteren Betriebssystem zuweisen, wird sie nicht installiert.
    - **Kategorie (optional):** Wählen Sie eine der integrierten oder von Ihnen erstellten App-Kategorien aus. Dadurch wird es für die Benutzer leichter, die App im Unternehmensportal zu finden.
    - **Diese App als ausgewählte App im Unternehmensportal anzeigen:** Zeigen Sie die App auf der Hauptseite des Unternehmensportal hervorgehoben an, wenn Benutzer nach Apps suchen.
    - **Informations-URL:** Geben Sie optional eine URL zu einer Website ein, die Informationen über diese App enthält. Diese URL wird den Benutzern im Unternehmensportal angezeigt.
    - **URL zu den Datenschutzbestimmungen:** Geben Sie optional eine URL zu einer Website ein, die Datenschutzinformationen für diese App enthält. Diese URL wird den Benutzern im Unternehmensportal angezeigt.
    - **Entwickler:** Geben Sie optional den Namen des App-Entwicklers ein.
    - **Besitzer:** Geben Sie optional einen Namen für den Besitzer dieser App ein, z.B. **Personalabteilung**.
    - **Anmerkungen:** Geben Sie Hinweise zu dieser App ein.
    - **Symbol hochladen:** Laden Sie ein Symbol hoch, das der App zugeordnet wird. Dies ist das Symbol, das gemeinsam mit der App angezeigt wird, wenn die Benutzer das Unternehmensportal durchsuchen.
2. Wenn Sie fertig sind, wählen Sie auf dem Blatt **App hinzufügen** die Option **Speichern** aus.

Die von Ihnen erstellte App wird in der Liste der Apps angezeigt, in der Sie sie ausgewählten Gruppen zuweisen können. Hilfe finden Sie unter [Zuweisen von Apps zu Gruppen](/intune-azure/manage-apps/deploy-apps).
