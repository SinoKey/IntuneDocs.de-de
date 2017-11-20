---
title: "Festlegen von Registrierungseinschränkungen in Intune"
titlesuffix: Azure portal
description: "Schränken Sie die Registrierung plattformbezogen ein, und legen Sie in Intune einen Grenzwert für die Geräteregistrierung fest. \""
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 11/6/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 463278e4dc9ad677f654754d4710b110b376cc2d
ms.sourcegitcommit: 5279a0bb8c5aef79aa57aa247ad95888ffe5a12b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2017
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
- Plattform-Betriebssystemversion für iOS, Android und Windows (es können nur Windows 10-Versionen verwendet werden; lassen Sie diese Einstellung leer, wenn Windows 8.1 zulässig ist)
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
  - **Versionen:** Geben Sie die **Minimal-** (Min) und **Maximalversion** (Max) des Plattformbetriebssystems für Android-, iOS- oder Windows-Geräte an. Android unterstützt major.minor.rev.build. iOS unterstützt major.minor.rev. Windows unterstützt major.minor.rev.build nur für Windows 10. Die Betriebssystemversionen gelten nicht für Apple-Geräte, die mit dem Programm zur Geräteregistrierung, dem Apple School Manager oder der App Apple Configurator registriert werden. 
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
