---
title: "Festlegen von Registrierungseinschränkungen in Intune"
titlesuffix: Azure portal
description: "Schränken Sie die Registrierung plattformbezogen ein, und legen Sie in Intune einen Grenzwert für die Geräteregistrierung fest. \""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0117d3249f7fd2568201762b7dd16af9cc26392c
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2017
---
# <a name="set-enrollment-restrictions"></a>Festlegen von Registrierungseinschränkungen

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Als Intune-Administrator können Sie bestimmen, welche Geräte sich für die Verwaltung mit Intune registrieren können. Verwenden Sie das Azure-Portal, um die folgenden Einschränkungen für die Geräteregistrierung festzulegen:

- Maximale Anzahl registrierter Geräte
- Geräteplattformen, die registriert werden können:
  - Android
  - iOS
  - macOS
  - Windows
- Betriebssystemversion der Plattform (nur iOS und Android)
  - Mindestversion
  - Maximalversion
- Private Geräte einschränken (nur iOS und Android)

>[!NOTE]
>Registrierungseinschränkungen stellen keine Sicherheitsfunktionen dar. Gefährdete Geräte können falsche Angaben zu ihren Eigenschaften enthalten. Diese Einschränkungen sind eine bestmögliche Barriere für nicht böswillige Benutzer.

## <a name="set-device-type-restrictions"></a>Festlegen von Gerätetypbeschränkungen
Die Standardregistrierungseinschränkungen gelten für alle Benutzer und benutzerlosen Registrierungen.
1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Klicken Sie auf **Geräteregistrierung** > **Registrierungsbeschränkungen**.
4. Wählen Sie unter **Registrierungseinschränkungen** > **Gerätetypeinschränkungen** die Option **Standard** aus.
5. Wählen Sie unter **Alle Benutzer** die Option **Plattformen** aus. Wählen Sie für jede Plattform **Zulassen** oder **Blockieren** aus:
  - **Android**
  - **iOS**
  - **macOS**
  - **Windows**

  Klicken Sie auf **Speichern**.
6. Wählen Sie unter **Alle Benutzer** die Option **Plattformkonfigurationen** und dann die folgenden Konfigurationen aus. Für jede zugelassene Plattform können Sie die folgenden Optionen konfigurieren:
  - **Versionen:** Geben Sie die **Mindest-** (Min) und die **Maximalversion** (Max) des Plattformbetriebssystems für Android- und iOS-Geräte an. Die Betriebssystemversionen gelten nicht für Geräte, die mit dem Programm zur Geräteregistrierung, dem Apple School Manager oder der App Apple Configurator registriert werden.
  - **Persönliches Eigentum:** Wählen Sie für Android-, iOS- und macOS-Geräte **Zulassen** oder **Blockieren** aus.
  ![Screenshot des Arbeitsbereichs „Geräteeinschränkungen“ mit den standardmäßigen Geräteplattformkonfigurationen für die konfigurierten Einstellungen persönlicher Geräte.](media/device-restrictions-platform-configurations.png)
  Klicken Sie auf **Speichern**.

>[!NOTE]
>Wenn Sie die Registrierung privater Android-Geräte blockieren, können private Android for Work-Geräte weiterhin registriert werden.

## <a name="set-device-limit-restrictions"></a>Festlegen von Einschränkungen zum Gerätelimit
Die standardmäßigen Registrierungseinschränkungen gelten für alle Benutzer.
1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Klicken Sie auf **Geräteregistrierung** > **Registrierungsbeschränkungen**.
4. Wählen Sie im Azure-Portal die Option **Geräteregistrierung** und dann **Registrierungseinschränkungen** aus.
5. Klicken Sie auf **Registrierungseinschränkungen** > **Einschränkungen zum Gerätelimit**.
6. Wählen Sie unter **Alle Benutzer** die Option **Gerätelimit** aus. Geben Sie die maximale Anzahl registrierter Geräte pro Benutzer ein.  
![Screenshot des Blatts „Einschränkungen zum Gerätelimit“ mit den Einschränkungen zur Gerätebeschränkung.](./media/device-restrictions-limit.png)

  Klicken Sie auf **Speichern**.
