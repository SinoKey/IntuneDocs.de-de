---
title: "Festlegen von Registrierungseinschränkungen in Intune | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Einschränken der Registrierung nach Plattform und Festlegen eines Grenzwerts für die Geräteregistrierung in Intune "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: 1bdefce35c20ce24b94ee701a2d13b5408f435ce

---

# <a name="set-enrollment-restrictions"></a>Festlegen von Registrierungseinschränkungen 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Sie können die Gerätetypen einschränken, die sich in Intune registrieren können, indem Sie die zulässigen Plattformen angeben. Sie können auch die maximale Anzahl der Geräte festlegen, die ein Benutzer registrieren darf.

## <a name="set-device-type-restrictions"></a>Festlegen von Gerätetypbeschränkungen

1. Wählen Sie im Azure-Portal **Weitere Dienste** aus, geben Sie **Intune** in das Textfeld ein, und wählen Sie dann **Andere** > **Intune** aus.

2. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Registrierungseinschränkungen** aus.

3. Wählen Sie unter **Gerätetypbeschränkungen** die Option **Standard** aus.

4. Auf dem Blatt **Alle Benutzer** wählen Sie **Plattformen** aus.

5. Wählen Sie für Plattformen, die in Intune registriert werden dürfen, **Zulassen** aus. Wählen Sie für Plattformen, die Sie von der Registrierung blockieren möchten, **Blockieren** aus.

6. Wählen Sie **Speichern** aus.

7. Wählen Sie **Plattformkonfigurationen** aus.

8. Wählen Sie aus, ob Sie persönliche iOS-Geräte zur Registrierung „Zulassen“ oder „Blockieren“ möchten.

9. Wählen Sie **Speichern** aus.

## <a name="set-device-limit-restrictions"></a>Festlegen von Einschränkungen zum Gerätelimit

1. Wählen Sie im Azure-Portal auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Registrierungseinschränkungen** aus.

2. Wählen Sie unter **Einschränkungen zum Gerätelimit** die Option **Standard** aus.

3. Auf dem Blatt **Alle Benutzer** wählen Sie **Gerätegrenzwert** aus.

4. Wählen Sie die maximale Anzahl der Geräte aus, die ein Benutzer registrieren kann, und klicken Sie dann auf **Speichern**.



<!--HONumber=Feb17_HO1-->


