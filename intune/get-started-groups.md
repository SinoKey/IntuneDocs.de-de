---
title: Erste Schritte mit Gruppen
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 04843a918a3c661ab69dfa711f4d22a8feedf5f3
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2017
---
# <a name="get-started-with-groups"></a>Erste Schritte mit Gruppen

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

[](./media/generic-users-groups.png)

Microsoft Intune verwendet Azure Active Directory (Azure AD) zum [Verwalten des Zugriffs auf Unternehmensressourcen](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups). Dieser Zugriff wird mithilfe von Rollen im Verzeichnis gesteuert. Intune verwaltet dann diesen Zugriff für mobile Geräte, wodurch Mitgliedern dieser Gruppe der Zugriff auf Ressourcen gewährt wird.

__Wie erstelle ich eine Gruppe?__

1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.
2. Suchen Sie über **Ressourcen durchsuchen** nach **Benutzer und Gruppen**.
3. Wenn Sie das Blatt **Benutzer und Gruppen** geöffnet haben, klicken Sie auf **Alle Gruppen**.
4. Wählen Sie auf dem Blatt **Users and Groups – All Groups** (Benutzer und Gruppen – Alle Gruppen) die Option **Neue Gruppe** aus.
5. Fügen Sie auf dem Blatt **Gruppe** einen **Namen** und eine **Beschreibung** für die Gruppe hinzu.
6. Legen Sie den **Mitgliedschaftstyp** auf **Zugewiesen** fest. Für die Testgruppe sollten Sie **Office-Features nicht aktivieren**.
7. Klicken Sie auf **Erstellen**.

Wenn Sie eine Gruppe erfolgreich erstellt haben, sollte sie in der Liste **Alle Gruppen** angezeigt werden. Versuchen Sie andernfalls, eine andere Gruppe zu erstellen.
