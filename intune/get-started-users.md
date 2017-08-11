---
title: Erste Schritte mit Benutzern
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
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e711f32ebd77a83b17e6db468f8cb23a409c8d31
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2017
---
# <a name="get-started-with-users"></a>Erste Schritte mit Benutzern

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Azure Active Directory verwaltet die Objektgruppen – wie Geräte und Apps – und Benutzergruppen Ihrer Organisation. Sie können Benutzer oder Geräte in Gruppen zusammenfassen, statt sie jeweils einzeln verwalten zu müssen. So können Sie Apps und Einstellungen leicht einer großen Menge von Benutzern und Geräten zuweisen.

## <a name="how-do-i-create-a-user"></a>Wie erstelle ich einen Benutzer?

1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.
2. Suchen Sie über **Ressourcen durchsuchen** nach **Benutzer und Gruppen**.
3. Wenn Sie das Blatt **Benutzer und Gruppen** geöffnet haben, klicken Sie auf **Alle Benutzer** und dann auf **+ Neuer Benutzer**.
4. Machen Sie genauere Angaben zum Benutzer: geben Sie z.B. einen **Namen** und einen **Benutzernamen** ein. Der Domänennamenteil des Benutzernamens muss entweder der anfängliche Standarddomänenname „contoso.onmicrosoft.com“ oder ein verifizierter Domänenname ohne Verbund wie z.B. „contoso.com“ sein.
5. Wählen Sie unter **Gruppen** die Testgruppe, die Sie dem Benutzer hinzufügen möchten.
6. Speichern Sie das automatisch generierte Benutzerkennwort, das Sie zur Anmeldung bei einem Testgerät benötigen. Dieses Kennwort müssen Sie Benutzern geben, damit sie es in ein normales Kennwort ändern können, das sie sich leichter merken können.
7. Klicken Sie auf dem Blatt **Benutzer** auf **Erstellen**.

## <a name="assigning-licenses-to-users"></a>Zuweisen von Lizenzen zu Benutzern

Nachdem Sie einen Benutzer erstellt haben, können Sie über das [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) einem Benutzer eine Intune-Lizenz zuweisen. Wenn ein Benutzer keine Lizenz hat, kann er sein Gerät auch nicht für die Verwaltung registrieren.

1. Melden Sie sich im [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) mit den gleichen Anmeldeinformationen an, die Sie auch zur Anmeldung in Intune verwendet haben.
2. Klicken Sie auf **Benutzer** > **Aktive Benutzer**, und klicken Sie anschließend auf den Benutzer, den Sie erstellt haben.
3. Möglicherweise nimmt das Laden aller Informationen des Benutzers einige Zeit in Anspruch. Sobald Sie geladen wurden, klicken Sie für die **Produktlizenzen** des Benutzers auf **Bearbeiten**.
4. Weisen Sie dem Benutzer einen **Ort** zu und stellen Sie Intune auf **ein**.

 > [!NOTE]
 > Dadurch wird eine Ihrer Lizenzen für den Benutzer verwendet. Wenn Sie ihre dynamische Umgebung verwenden, können Sie später die Verwendung dieser Lizenz rückgängig machen, um Sie einem echten Benutzer zuzuweisen.

5. Wählen Sie **Speichern** aus.
