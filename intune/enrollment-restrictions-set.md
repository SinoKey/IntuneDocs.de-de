---
title: "Festlegen von Registrierungseinschränkungen in Intune"
titleSuffix: Intune on Azure
description: "Schränken Sie die Registrierung plattformbezogen ein, und legen Sie in Intune einen Grenzwert für die Geräteregistrierung fest. \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2dfcba8c788f262ce816dcd23dc2921fd57f331b
ms.sourcegitcommit: d1ad84edf4f03cb4c11fe55131556b43fc3a4500
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2017
---
# <a name="set-enrollment-restrictions"></a>Festlegen von Registrierungseinschränkungen

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Als Intune-Administrator können Sie bestimmen, welche Geräte sich für die Verwaltung mit Intune registrieren können. Verwenden Sie das Intune-Portal, um die folgenden Einschränkungen für die Geräteregistrierung festzulegen:

- Maximale Anzahl registrierter Geräte
- Geräteplattformen, die registriert werden können:
  - Android
  - iOS
  - macOS
  - Windows
- Private Geräte (nur iOS und Android) einschränken

>[!NOTE]
>Registrierungseinschränkungen stellen keine Sicherheitsfunktion dar. Gefährdete Geräte können falsche Angaben zu ihren Eigenschaften enthalten. Diese Einschränkungen sind eine bestmögliche Barriere für nicht böswillige Benutzer.

## <a name="set-device-type-restrictions"></a>Festlegen von Gerätetypbeschränkungen
Die Standard-Registrierungseinschränkungen gelten für alle Benutzer, denen keine Registrierungseinschränkungen mit höherer Priorität zugewiesen sind.  
1. Wählen Sie im Intune-Portal die Option **Geräteregistrierung** und dann **Registrierungseinschränkungen** aus.
![Screenshot des Arbeitsbereichs „Geräteeinschränkungen“ mit den standardmäßigen Gerätetypeinschränkungen und Einschränkungen zum Gerätelimit.](media/device-restrictions-set-default.png)
2. Wählen Sie unter **Registrierungseinschränkungen** > **Gerätetypeinschränkungen** die Option **Standard** aus.
3. Wählen Sie unter **Alle Benutzer** die Option **Plattformen** aus. Wählen Sie für jede Plattform **Zulassen** oder **Blockieren** aus:
  - **Android**
  - **iOS**
  - **macOS**
  - **Windows**

  Klicken Sie auf **Speichern**.
4. Wählen Sie unter **Alle Benutzer** die Option **Plattformkonfigurationen** aus, und wählen Sie die folgenden Konfigurationen:
  - **Privat**: Wählen Sie **Zulassen** oder **Blockieren** für Android und iOS-Geräte aus.
  ![Screenshot des Arbeitsbereichs „Geräteeinschränkungen“ mit den standardmäßigen Geräteplattformkonfigurationen für die konfigurierten Einstellungen persönlicher Geräte.](media/device-restrictions-platform-configurations.png)
  Klicken Sie auf **Speichern**.

>[!NOTE]
>Wenn Sie die Registrierung privater Android-Geräte blockieren, können Android for Work-Geräte weiterhin registriert werden.

## <a name="set-device-limit-restrictions"></a>Festlegen von Einschränkungen zum Gerätelimit
Die Standard-Registrierungseinschränkungen gelten für alle Benutzer, denen keine Registrierungseinschränkungen mit höherer Priorität zugewiesen sind.  
1. Wählen Sie im Intune-Portal die Option **Geräteregistrierung** und dann **Registrierungseinschränkungen** aus.
2. Klicken Sie auf **Registrierungseinschränkungen** > **Einschränkungen zum Gerätelimit**.
3. Wählen Sie unter **Alle Benutzer** die Option **Gerätelimit** aus. Geben Sie die maximale Anzahl registrierter Geräte pro Benutzer ein.  
![Screenshot des Blatts „Einschränkungen zum Gerätelimit“ mit den Einschränkungen zur Gerätebeschränkung.](./media/device-restrictions-limit.png)

  Klicken Sie auf **Speichern**.
