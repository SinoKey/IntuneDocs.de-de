---
title: "Hinzufügen von Web-Apps in Intune"
titleSuffix: Azure portal
description: "Erfahren Sie mehr über das Hinzufügen von Web-Apps in Intune.\""
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cfa70879a460826d22eb6fab2e0d08603e567d6e
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Hinzufügen von Web-Apps in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bevor Sie eine App verwalten und Benutzern zuweisen können, müssen Sie diese in Intune hinzufügen. Intune unterstützt eine Vielzahl von App-Typen, einschließlich Web-Apps.

> [!Note]
> Web-Apps werden nicht für Android for Work-Geräte unterstützt.

Führen Sie die folgenden Schritte durch, um eine App als Verknüpfung zu einer App im Internet zu Intune hinzuzufügen:

1. Melden Sie sich beim Azure-Portal an.
2. Suchen Sie über **Mehr Ressourcen** nach **Intune**, und wählen Sie die App aus.
3. Wählen Sie auf dem Blatt **Microsoft Intune** die Option **Mobile Apps** aus.
4. Wählen Sie auf dem Blatt **Mobile Apps** die Option **Apps** aus.
5. Wählen Sie oberhalb der App-Liste **Hinzufügen** aus. Das Blatt **App hinzufügen** wird angezeigt.
6. Wählen Sie auf dem Blatt **App hinzufügen** den Typ **Web-App** aus der Dropdownliste **App-Typ** aus.
7. Wählen Sie auf dem Blatt **App-Informationen** die Option **Konfigurieren** aus.
8. Fügen Sie auf dem Blatt **App-Informationen** die folgenden Informationen hinzu:
    - **Name**: Geben Sie den Namen der App ein, wie er im Unternehmensportal angezeigt wird.
    - **Beschreibung:** Geben Sie eine Beschreibung für die App ein. Diese Beschreibung wird den Endbenutzern im Unternehmensportal angezeigt.
    - **Herausgeber:** Geben Sie den Namen des Herausgebers dieser App ein.
    - **App-URL:** Geben Sie die URL der Website an, auf der die zuzuweisende App gehostet wird.
    - **Kategorie (optional):** Wählen Sie eine der integrierten oder von Ihnen erstellten App-Kategorien aus. Durch diese Auswahl ist es für Benutzer einfacher, die App im Unternehmensportal zu finden.
    - **Diese App als ausgewählte App im Unternehmensportal anzeigen:** Zeigen Sie die App auf der Hauptseite des Unternehmensportal hervorgehoben an, wenn Benutzer nach Apps suchen.
    - **Managed Browser zum Öffnen dieses Links anfordern:** Wenn Sie Benutzern einen Link zu einer Website oder Web-App zuweisen, können sie diesen in Intune Managed Browser öffnen. Dieser Browser muss auf ihrem Gerät installiert sein.
    - **Logo**: Laden Sie ein Logo für die App hoch. Dieses Logo wird gemeinsam mit der App angezeigt, wenn der Benutzer das Unternehmensportal durchsucht.
9. Wählen Sie dann auf dem Blatt **Informationen hinzufügen** die Option **OK** aus.
10. Wählen Sie anschließend **Hinzufügen** auf dem Blatt **App hinzufügen** aus.

Die von Ihnen erstellte App wird in der Liste der Apps angezeigt, in der Sie sie den ausgewählten Gruppen zuweisen können. Hilfe finden Sie unter [Zuweisen von Apps zu Gruppen](apps-deploy.md).