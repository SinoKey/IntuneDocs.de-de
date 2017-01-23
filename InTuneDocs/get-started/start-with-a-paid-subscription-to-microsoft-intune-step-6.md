---
title: Bereitstellen von Richtlinien und Apps | Microsoft-Dokumentation
description: "Sie können Richtlinieneinstellungen aktivieren und Apps bereitstellen, die angewendet werden, sobald die Geräte für die Verwaltung registriert wurden."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 9f75020a6d8a3e2aeb278fb99f54516253abf3dd


---

# <a name="create-policies-and-publish-apps"></a>Erstellen von Richtlinien und Veröffentlichen von Apps

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bevor Sie Apps in Intune registrieren, können Sie Richtlinieneinstellungen und Apps aktivieren, die bereitgestellt werden, sobald diese Geräte der Verwaltung hinzugefügt werden. Mit Intune-Richtlinien stehen Einstellungen bereit, mit deren Hilfe Sie die Sicherheitseinstellungen auf mobilen Geräten steuern, die Windows-Firewall- und Endpoint Protection-Einstellungen für Computer warten und Anwendungen bereitstellen können. Sie können Richtlinien konfigurieren, Apps hinzufügen und diese Apps bereitstellen, damit Geräte die Einstellungen und Apps empfangen, sobald sie in Intune registriert werden.

Richtlinien und Apps sind plattformspezifisch.

## <a name="manage-device-settings"></a>Verwalten von Geräteeinstellungen

 Richtlinieneinstellungen für Geräte werden plattformbasiert konfiguriert und verwaltet. Sie können Richtlinien für die folgenden Plattformen konfigurieren:

- [iOS](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune)
- [Android und Samsung KNOX Standard](https://docs.microsoft.com/intune/deploy-use/android-policy-settings-in-microsoft-intune)
- [Android for Work](https://docs.microsoft.com/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)
- [Windows 10 (PC und mobil)](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)
- [Windows 8.1](https://docs.microsoft.com/intune/deploy-use/windows-configuration-policy-settings-in-microsoft-intune)
- [Windows Phone 8.1](https://docs.microsoft.com/intune/deploy-use/windows-phone-8-1-policy-settings-in-microsoft-intune)
- [Windows Team](https://docs.microsoft.com/intune/deploy-use/windows-team-configuration-policy-settings-in-microsoft-intune)
- [Windows-PCs, auf denen die Intune-Clientsoftware ausgeführt wird](https://docs.microsoft.com/intune/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)

Weitere Informationen finden Sie unter [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).

## <a name="add-and-deploy-apps"></a>Hinzufügen und Bereitstellen von Apps

Sie können Apps zu Intune hinzufügen und sie dann auf zwei Arten auf verwalteten Geräten bereitstellen:
- **Erforderliche Installation**: Die Apps werden automatisch auf den verwalteten Geräten installiert.
- **Verfügbare Installation**: Die Apps werden im Intune-Unternehmensportal angezeigt und die Benutzer können auswählen, ob sie die Apps auf ihren Geräten installieren möchten.

### <a name="add-apps"></a>Hinzufügen von Apps

Zunächst müssen Sie die Apps mithilfe einer der folgenden Methoden in Intune verfügbar machen:
- [Hinzufügen von Apps für registrierte Geräte](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)
- [Hinzufügen von Apps für Intune-Softwareclient-PCs](https://docs.microsoft.com/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)

### <a name="deploy-apps"></a>Bereitstellen von Apps

Sobald die App in Intune zur Verfügung steht, können Sie sie auf verwalteten Geräten bereitstellen:
- [Bereitstellen von Apps auf Geräten](https://docs.microsoft.com/intune/deploy-use/deploy-use/deploy-apps-in-microsoft-intune)
- Bereitstellen von Apps aus einem Volumenprogramm:
    - [iOS: Volume Purchase Program (VPP)](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)
    - [Windows Store für Unternehmen](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)
    - [Android for Work](https://docs.microsoft.com/en-us/Intune/deploy-use/android-for-work-apps)

    Nachdem Sie die Apps für die Bereitstellung konfiguriert haben, können Sie [Apps konfigurieren](https://docs.microsoft.com/intune/deploy-use/update-apps-using-microsoft-intune) und [Apps überwachen](https://docs.microsoft.com/intune/deploy-use/monitor-apps-in-microsoft-intune).

>[!div class="step-by-step"]

>[&larr; **Organisieren von Benutzern und Geräten**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)[**Anpassen des Unternehmensportals** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-7.md)  



<!--HONumber=Dec16_HO2-->


