---
title: "Entfernen eines Benutzers von einem iOS-Gerät mit Intune"
titleSuffix: Intune on Azure
description: "Erfahren Sie, wie Sie einen Benutzer von einem gemeinsam genutzten iOS-Gerät mit Intune entfernen."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 00f5898d0f2cc167a66026dd108d6bbd54c39cec
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2017
---
# <a name="remove-a-user-from-a-shared-ios-device-with-intune"></a>Entfernen eines Benutzers von einem gemeinsam genutzten iOS-Gerät mit Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Die Aktion **Benutzer entfernen** löscht den von Ihnen ausgewählten Benutzer aus dem lokalen Cache auf einem freigegebenen iPad-Gerät ab, das für die Verwaltung der iOS Classroom-App mit einem [iOS-Bildungsprofil](education-settings-configure-ios.md) konfiguriert ist. 

## <a name="supported-platforms"></a>Unterstützte Plattformen

- Windows – Nicht unterstützt
- Windows Phone 8.1 – Nicht unterstützt
- iOS – Unterstützt auf iOS 9.3 und höher (nur freigegebene iPad-Geräte)
- macOS – Nicht unterstützt
- Android – Nicht unterstützt

## <a name="how-to-remove-a-user"></a>So entfernen Sie einen Benutzer

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.
4. Wählen Sie auf dem Blatt **Geräte** die Option **Alle Geräte** aus.
5. Wählen Sie aus der Liste der von Ihnen verwalteten Geräten ein iOS-Gerät aus.
6. Wählen Sie auf dem Blatt für dieses Gerät **Benutzer** aus.
7. Klicken Sie über die Liste mit der rechten Maustaste auf den Benutzer, den Sie entfernen möchten, und wählen Sie dann **Benutzer entfernen** aus.

## <a name="next-steps"></a>Nächste Schritte

Um den Status der gerade ausgeführten Aktion anzuzeigen, wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Geräteaktionen** aus.
