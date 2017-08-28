---
title: "Festlegen der Autorität für die Verwaltung mobiler Geräte"
titleSuffix: Intune on Azure
description: "Erfahren Sie, wie die Autorität für die Verwaltung mobiler Geräte in Intune festlegen. \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dfcd7b97848ed68edb4572429abc53a1cc8f8558
ms.sourcegitcommit: 0b164f806165d312acfc88815a60e325e3d02672
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2017
---
# <a name="set-the-mobile-device-management-authority"></a>Festlegen der Autorität für die Verwaltung mobiler Geräte

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Die Einstellung für die Autorität für die Verwaltung mobiler Geräte (Mobile Device Management, MDM) bestimmt, wie Sie Ihre Geräte verwalten. Als IT-Administrator müssen Sie eine MDM-Autorität festlegen, damit Benutzer Geräte zur Verwaltung registrieren können.

Die möglichen Konfigurationen sind Folgende:

- **Intune Standalone:** Ausschließliche Verwaltung in der Cloud, die Sie mithilfe des Azure-Portals konfigurieren. Ihnen stehen alle Funktionen von Intune zur Verfügung. [Legen Sie die MDM-Autorität in der Intune-Konsole fest](#set-mdm-authority-to-intune).

- **Intune Hybrid:** Integration der Intune-Cloudlösung in System Center Configuration Manager. Sie konfigurieren Intune mithilfe der Configuration Manager-Konsole. [Legen Sie die MDM-Autorität im Configuration Manager fest](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Verwaltung mobiler Geräte für Office 365:** Integration von Office 365 in die Intune-Cloudlösung. Sie konfigurieren Intune über das Office 365 Admin Center. Ihnen steht eine Teilmenge der Funktionen von Intune Standalone zur Verfügung. Legen Sie die MDM-Autorität im Office 365 Admin Center fest.

>[!IMPORTANT]    
In Configuration Manager, Version 1610 oder höher, und Microsoft Intune, Version 1705, können Sie Ihre MDM-Autorität ändern, ohne sich an den Microsoft Support wenden und die Aufhebung der Registrierung sowie die erneute Registrierung vorhandener verwalteten Geräte durchführen zu müssen. Details finden Sie unter [Was Sie machen können, wenn Sie die falsche MDM-Autoritätseinstellung vorgenommen haben](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).

## <a name="set-mdm-authority-to-intune"></a>Festlegen der MDM-Autorität in Intune

1. Wählen Sie im [Azure-Portal](https://portal.azure.com) die Optionen **Weitere Dienste** > **Überwachung + Verwaltung** > **Intune** aus.
2. Wählen Sie auf dem Blatt „Intune“ die Option **Geräteregistrierung** und dann **Übersicht** aus.
![Screenshot vom Intune-Bildschirm zum Festlegen der Autorität für die mobile Geräteverwaltung](media/set-mdm-auth.png)

3. Wählen Sie unter **Autorität für die Verwaltung mobiler Geräte** Ihre MDM-Autorität aus den folgenden Optionen aus:
  - **Intune-MDM-Autorität**
  - **Configuration Manager-MDM-Autorität**
  - **Keine**

  Eine Meldung zeigt an, dass Sie die MDM-Autorität erfolgreich auf Intune festgelegt haben.

## <a name="enable-device-enrollment"></a>Aktivieren der Geräteregistrierung

Mit Intune als MDM-Autorität können Benutzer private Geräte registrieren und durch das Installieren der Unternehmensportal-App (iOS und Android), das Hinzufügen von Unternehmensanmeldeinformationen (Windows) oder das Zugreifen auf die Unternehmensportal-Website (iOS, Android, macOS) Zugriff auf Ressourcen wie E-Mails erhalten.

Verschiedene Plattformen haben die folgenden Anforderungen für das Aktivieren oder Vereinfachen der Registrierung:
- **iOS** – (erforderlich): [Rufen Sie ein MDM-Pushzertifikat von Apple ab](apple-mdm-push-certificate-get.md), und [registrieren Sie dann unternehmenseigene iOS-Geräte](ios-enroll.md) (optional).
- **Android** – (optional): [Aktivieren Sie Android-Arbeitsprofile.](android-enroll.md)
- **Windows** – (optional): Aktivieren Sie die [automatische Registrierung](windows-enroll.md) oder die [Massenregistrierung](windows-bulk-enroll.md).
- **macOS**: Keine Anforderungen


## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Bereinigen mobiler Geräte nach Ablauf des MDM-Zertifikats

Das MDM-Zertifikat wird automatisch erneuert, wenn mobile Geräte mit dem Intune-Dienst kommunizieren. Wenn mobile Geräte zurückgesetzt werden oder für längere Zeit keine Kommunikation mit dem Intune-Dienst stattfindet, wird das MDM-Zertifikat nicht erneuert. Das Gerät wird 180 Tage nach Ablauf des MDM-Zertifikats aus dem Azure-Portal entfernt.
