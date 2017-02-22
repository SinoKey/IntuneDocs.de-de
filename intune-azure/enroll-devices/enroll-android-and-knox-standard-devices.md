---
title: "Registrieren von Android-Geräten in Intune | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie Android-Geräte in der Vorschau von Intune in Azure registrieren."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: edd6303f3bb05dfff758cbb7d4bd08e21f083998


---

# <a name="enroll-android-devices"></a>Registrieren von Android-Geräten

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Als Intune-Administrator können Sie die Verwaltung von Android-Geräten, einschließlich Samsung KNOX Standard-Geräten, über das Unternehmensportal aktivieren. Benutzer können ihre Geräte anschließend über die Unternehmensportal-App registrieren, die in Google Play zur Verfügung steht.

## <a name="prerequisite"></a>Voraussetzung

Sie müssen die MDM-Autorität auf **Microsoft Intune** festlegen, um die Verwaltung mobiler Geräte vorzubereiten. Anweisungen finden Sie unter [Festlegen der MDM-Autorität](set-mdm-authority.md). Sie legen dieses Element nur einmal fest, wenn Sie die Ersteinrichtung von Intune für die Verwaltung mobiler Geräte durchführen, sodass dies eventuell bereits erfolgt ist. 

## <a name="set-up-android-enrollment"></a>Einrichten der Android-Registrierung

Standardmäßig ist Intune so eingerichtet, dass die Registrierung von Android- und Samsung KNOX Standard-Geräte zugelassen wird. 

Um die Einstellung zum Zulassen oder Blockieren der Registrierung von Android-Geräten anzuzeigen, wechseln Sie im Azure-Portal zum Blatt „Intune“ und wählen **Registrierung** > **Registrierungsbeschränkungen** aus. 

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Kommunizieren der Geräteregistrierung für den Zugriff auf Unternehmensressourcen an die Benutzer

Registrierungsanleitungen für Endbenutzer finden Sie unter [Registrieren Ihres Android-Geräts bei Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android). Im Laufe des Registrierungsprozesses werden Benutzer darüber informiert, was sie erwarten können und was IT-Administratoren auf ihren Geräten sehen können und was nicht.

Informationen zu anderen Endbenutzeraufgaben finden Sie in den folgenden Artikeln:

- [Ressourcen zu Endbenutzerszenarios in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Verwenden Ihres Android-Geräts mit Intune](https://docs.microsoft.com/intune/enduser/using-your-android-device-with-intune)


<!--HONumber=Feb17_HO1-->


