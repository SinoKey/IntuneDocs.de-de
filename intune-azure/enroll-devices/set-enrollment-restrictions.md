---
title: "Festlegen von Registrierungseinschränkungen in Intune | Intune Azure-Vorschau | Microsoft-Dokumentation"
description: "Intune Azure-Vorschau: Einschränken der Registrierung nach Plattform und Festlegen eines Grenzwerts für die Geräteregistrierung in Intune "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: c4fa22fad4df9c0e4699cf258eb9518a1534bb94

---

# <a name="set-enrollment-restrictions"></a>Festlegen von Registrierungseinschränkungen 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Sie können die Typen und die maximale Anzahl von Geräten festlegen, die für die Registrierung zugelassen werden. Sie können auf dem Blatt „Registrierungsbeschränkungen“ Folgendes festlegen:

- Die Plattformen, die für die Registrierung zulässig sind, und ob die Registrierung von persönlichen Geräten für Android und iOS blockiert werden soll

- Die maximale Anzahl der Geräte, die ein Benutzer registrieren darf

## <a name="set-device-type-restrictions"></a>Festlegen von Gerätetypbeschränkungen

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

2. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Registrierungseinschränkungen** aus.

3. Wählen Sie unter **Gerätetypbeschränkungen** die Option **Standard** aus.

4. Auf dem Blatt **Alle Benutzer** wählen Sie **Plattformen** aus.

5. Wählen Sie für Plattformen, die in Intune registriert werden dürfen, **Zulassen** aus. Wählen Sie für Plattformen, die Sie von der Registrierung blockieren möchten, **Blockieren** aus. Für Plattformen wird standardmäßig **Zulassen** festgelegt. 

    >[!NOTE]
    >Diese Einstellungen gelten nicht für bzw. blockieren keine Windows-Registrierungen, die den Intune-Softwareclient verwenden. Diese Einstellungen betreffen nur die Registrierung mithilfe der Verwaltung mobiler Geräte. 

6. Wählen Sie **Speichern** aus.

7. Wählen Sie **Plattformkonfigurationen** aus.

8. Wählen Sie aus, ob Sie persönliche iOS- und Android-Geräte zur Registrierung **Zulassen** oder **Blockieren** möchten.

9. Wählen Sie **Speichern** aus.

## <a name="set-device-limit-restrictions"></a>Festlegen von Einschränkungen zum Gerätelimit

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

2. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Registrierungseinschränkungen** aus.

3. Wählen Sie unter **Einschränkungen zum Gerätelimit** die Option **Standard** aus.

4. Auf dem Blatt **Alle Benutzer** wählen Sie **Gerätegrenzwert** aus.

5. Wählen Sie die maximale Anzahl der Geräte aus, die ein Benutzer registrieren kann, und klicken Sie dann auf **Speichern**.



<!--HONumber=Feb17_HO3-->


