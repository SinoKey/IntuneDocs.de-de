---
title: "Hinzufügen von Store-Apps für iOS in Intune | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Erfahren Sie mehr über das Hinzufügen von Store-Apps für iOS in Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 01e5bfeb98aee9314fa04679cc27c8aba0e18fb0
ms.openlocfilehash: b29374c3abcca90de6cba7ed83866c04350f69c5

---

# <a name="how-to-add-ios-store-apps-to-intune"></a>Hinzufügen von Store-Apps für iOS in Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="step-1---search-for-the-app-in-the-store"></a>Schritt 1: Suchen der App im Store

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Apps verwalten** aus.
4. Wählen Sie in der Workload **Mobile Apps** die Option **Verwalten** > „Apps“ aus.
5. Wählen Sie über der Liste der Apps **Hinzufügen** aus.
6. Wählen Sie auf dem Blatt **App hinzufügen** die Option **App Store durchsuchen** aus.
7. Geben Sie auf dem Blatt **Apple App Store** den Namen (oder einen Teil des Namens) in das Suchfeld ein. Intune durchsucht den Store und gibt eine Liste mit relevanten Ergebnissen zurück.
8. Wählen Sie in der Liste die gewünschte App aus, und klicken Sie dann auf **OK**.

## <a name="step-2---configure-app-information"></a>Schritt 2: Konfigurieren von App-Informationen

1. Wählen Sie auf dem Blatt **App hinzufügen** die Option **App-Informationen** aus.
2. Konfigurieren Sie auf dem Blatt **App bearbeiten** die folgenden Informationen. Klicken Sie abschließend auf **Hinzufügen**. Abhängig von der ausgewählten App werden einige der Werte auf diesem Blatt möglicherweise automatisch ausgefüllt:
- **App-Name:** Geben Sie den Namen der App ein, wie er im Unternehmensportal angezeigt werden soll. Stellen Sie sicher, dass alle App-Namen eindeutig sind. Wenn ein App-Name zweimal vergeben wird, wird den Benutzern im Unternehmensportal nur eine der Apps angezeigt.
    - **App-Beschreibung:** Geben Sie eine Beschreibung für die App ein. Diese Beschreibung wird den Benutzern im Unternehmensportal angezeigt.
- **Herausgeber:** Geben Sie den Namen des Herausgebers der App ein.
- **App Store-URL:** Geben Sie die App Store-URL der App an, die Sie erstellen möchten.
- **Mindestens erforderliches Betriebssystem:** Wählen Sie in der Liste die mindestens erforderliche Betriebssystemversion aus, auf der die App installiert werden kann. Wenn Sie die App einem Gerät mit einem älteren Betriebssystem zuweisen, wird sie nicht installiert.
- **Kategorie** (optional). Wählen Sie eine der integrierten oder von Ihnen erstellten App-Kategorien aus. Dadurch wird es für die Benutzer leichter, die App im Unternehmensportal zu finden.
- **Diese App als ausgewählte App im Unternehmensportal anzeigen:** Zeigen Sie die App auf der Hauptseite des Unternehmensportal hervorgehoben an, wenn Benutzer nach Apps suchen.
- **Informations-URL:** Geben Sie optional eine URL zu einer Website ein, die Informationen über diese App enthält. Diese URL wird den Benutzern im Unternehmensportal angezeigt.
- **URL zu den Datenschutzbestimmungen:** Geben Sie optional eine URL zu einer Website ein, die Datenschutzinformationen für diese App enthält. Diese URL wird den Benutzern im Unternehmensportal angezeigt.
- **Entwickler:** Geben Sie optional den Namen des App-Entwicklers ein.
- **Besitzer:** Geben Sie optional einen Namen für den Besitzer dieser App ein, z.B. **Personalabteilung**.
- **Anmerkungen:** Geben Sie Hinweise zu dieser App ein.
- **Symbol hochladen:** Laden Sie ein Symbol hoch, das der App zugeordnet wird. Dies ist das Symbol, das gemeinsam mit der App angezeigt wird, wenn die Benutzer das Unternehmensportal durchsuchen.
3. Wenn Sie fertig sind, wählen Sie auf dem Blatt **App hinzufügen** die Option **Speichern** aus.

Die von Ihnen erstellte App wird in der Liste der Apps angezeigt, in der Sie sie ausgewählten Gruppen zuweisen können. Hilfe finden Sie unter [Zuweisen von Apps zu Gruppen](/intune-azure/manage-apps/deploy-apps).


<!--HONumber=Feb17_HO1-->


