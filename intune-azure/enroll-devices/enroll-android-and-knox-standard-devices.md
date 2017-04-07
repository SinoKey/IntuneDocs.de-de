---
title: "Registrieren von Android-Geräten in Intune"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie Android-Geräte in der Vorschau von Intune in Azure registrieren."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: b664620f424f9ef612d17beb810564dbdd68ff79
ms.lasthandoff: 03/22/2017


---

# <a name="enroll-android-devices"></a>Registrieren von Android-Geräten

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Mit Intune können Sie Android-Geräte, einschließlich Samsung Knox Standard-Geräte, verwalten. Um die Geräteverwaltung zu aktivieren, müssen die Benutzer ihre Geräte durch Herunterladen der Intune-Unternehmensportal-App, die bei Google Play verfügbar ist, registrieren und anschließend die App öffnen und den Anweisungen zum Registrieren folgen. Sobald sich Android-Geräte unter Verwaltung befinden, können Sie [Konformitätsrichtlinien erstellen](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android), [Apps verwalten](https://docs.microsoft.com/intune-azure/manage-apps/what-is-app-management) und mehr.

## <a name="prerequisite"></a>Voraussetzung

Sie müssen die MDM-Autorität auf **Microsoft Intune** festlegen, um die Verwaltung mobiler Geräte vorzubereiten. Anweisungen finden Sie unter [Festlegen der MDM-Autorität](set-mdm-authority.md). Sie legen dieses Element nur einmal fest, wenn Sie die Ersteinrichtung von Intune für die Verwaltung mobiler Geräte durchführen, sodass dies eventuell bereits erfolgt ist.

## <a name="set-up-android-enrollment"></a>Einrichten der Android-Registrierung

Standardmäßig erlaubt Intune bereits die Registrierung von Android- und Samsung KNOX Standard-Geräten.

Um Android-Geräte oder nur die Registrierung von persönlichen Android-Geräten zu blockieren, gehen Sie unter [Festlegen von Gerätetypbeschränkungen](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-type-restrictions).

Um die maximale Anzahl von Geräten festzulegen, die ein Benutzer registrieren kann, sehen Sie sich das Thema [Festlegen von Einschränkungen zum Gerätelimit](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-limit-restrictions) an.

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Kommunizieren der Geräteregistrierung für den Zugriff auf Unternehmensressourcen an die Benutzer

Ihre Endbenutzer müssen unter Google Play die Intune-Unternehmensportal-App herunterladen, sie dann öffnen und den Aufforderungen folgen, um ihr Gerät zu registrieren. Im Laufe des von der App geführten Registrierungsprozesses werden Benutzer darüber informiert, was sie erwarten können und was IT-Administratoren auf ihren Geräten sehen können und was nicht.

Sie können auch einen Link für Online-Registrierungsschritte senden: [Registrieren Ihres Android-Geräts bei Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android).

Informationen zu anderen Endbenutzeraufgaben finden Sie in den folgenden Artikeln:

- [Ressourcen zu Endbenutzerszenarios in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune)
- [Verwenden Ihres Android-Geräts mit Intune](https://docs.microsoft.com/intune/enduser/using-your-android-device-with-intune)

