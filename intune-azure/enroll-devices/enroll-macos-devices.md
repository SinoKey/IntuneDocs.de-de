---
title: "Registrieren von macOS-Geräten in Intune | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie macOS-Geräte in der Vorschau von Intune in Azure registrieren."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 1/3/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ba2affcdbcdfcd690d671c7b20f9d1e14a74f764
ms.openlocfilehash: 171175689adca027181f3da4d05222117de97e13


---

# <a name="enroll-macos-devices-in-intune-azure-preview"></a>Registrieren von macOS-Geräten in der Vorschau von Intune in Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Als Intune-Administrator können Sie die macOS-Geräte verwalten. Standardmäßig ermöglicht das Azure-Portal Benutzern die Registrierung ihrer macOS-Geräte. Sie müssen den Benutzern nur auf die [Unternehmensportal-Website](http://portal.manage.microsoft.com) verweisen, damit sie dort ihre macOS-Gerät registrieren. 

## <a name="prerequisites"></a>Voraussetzungen

Die folgenden Voraussetzungen müssen vor dem Einrichten der Registrierung von macOS-Geräten erfüllt sein:

- [Konfigurieren von Domänen](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Festlegen der MDM-Autorität](set-mdm-authority.md)
- [Erstellen von Gruppen](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Konfigurieren des Unternehmensportals](/intune-azure/manage-apps/company-portal-app.md)
- Zuweisen von Benutzerlizenzen im [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Abrufen eines Apple-MDM-Push-Zertifikats](get-an-apple-mdm-push-certificate.md)

## <a name="set-up-macos-enrollment"></a>Einrichten der macOS-Registrierung

Standardmäßig ist Intune bereits dafür eingerichtet, die Registrierung von macOS-Geräten zu erlauben. 

Um die Einstellung zum Zulassen oder Blockieren der Registrierung von macOS-Geräten anzuzeigen, wechseln Sie im Azure-Portal zum Blatt „Intune“ und wählen **Registrierung** > **Registrierungsbeschränkungen** aus. 

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Kommunizieren der Geräteregistrierung für den Zugriff auf Unternehmensressourcen an die Benutzer

Registrierungsanleitungen für Endbenutzer finden Sie unter [Registrieren Ihres macOS-Geräts bei Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-macos). Im Laufe des Registrierungsprozesses werden Benutzer darüber informiert, was sie erwarten können und was IT-Administratoren auf ihren Geräten sehen können und was nicht.

Informationen zu anderen Endbenutzeraufgaben finden Sie in den folgenden Artikeln:

- [Ressourcen zu Endbenutzerszenarios in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Verwenden Ihres iOS- oder Mac OS-Geräts mit Intune](https://docs.microsoft.com/intune/enduser/using-your-ios-or-mac-os-x-device-with-intune)


<!--HONumber=Feb17_HO1-->


