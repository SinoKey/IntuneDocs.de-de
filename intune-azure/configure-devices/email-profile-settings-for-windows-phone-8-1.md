---
title: "Intune-E-Mail-Einstellungen für Windows Phone 8.1 | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Erfahren Sie etwas über die Intune-Einstellungen, die Sie zum Konfigurieren von E-Mail-Verbindungen auf Windows Phone 8.1-Geräten verwenden können."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 352d6bd9-ec8c-439e-be3a-ad3daf307df2
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: ba745c2cefb159619b105d5b623849ba2766e8c8
ms.lasthandoff: 02/16/2017


---

# <a name="email-profile-settings-for-windows-phone-81-devices-in-microsoft-intune"></a>E-Mail-Profileinstellungen für Windows Phone 8.1-Geräte in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


- **Alle Einstellungen auf Windows Phone 8.1 anwenden:** Diese Einstellung können Sie im klassischen Intune-Portal konfigurieren. Im Azure-Portal kann diese Einstellung nicht geändert werden. Wenn hierfür **Konfiguriert** festgelegt wird, werden sämtliche Einstellungen nur auf Windows Phone 8.1-Geräte angewendet. Wenn hierfür **Nicht konfiguriert** festgelegt wird, gelten diese Einstellungen auch für Windows 10 Mobile-Geräte.
- **E-Mail-Server:** Der Hostname Ihres Exchange-Servers.
- **Kontoname:** Der Anzeigename für das E-Mail-Konto so, wie er den Benutzern auf ihren Geräten angezeigt wird.
- **Benutzernamensattribut aus AAD:** Dies ist das Attribut in Active Directory (AD) oder Azure AD, das verwendet wird, um den Benutzernamen für dieses E-Mail-Profil zu generieren. Wählen Sie **Primäre SMTP-Adresse** aus, z.B. **user1@contoso.com**, oder **Benutzerprinzipalname**, z.B. **user1** oder **user1@contoso.com**.
- **E-Mail-Adressattribut aus AAD:** Die Art der Generierung der E-Mail-Adresse für den Benutzer auf den einzelnen Geräten. Wählen Sie **Primäre SMTP-Adresse** aus, um die primäre SMTP-Adresse zum Anmelden bei Exchange zu verwenden. Verwenden Sie **Benutzerprinzipalname** aus, um den vollständigen Benutzerprinzipalnamen als E-Mail-Adresse zu verwenden.


## <a name="security-settings"></a>Sicherheitseinstellungen

- **SSL:** Verwenden Sie SSL-Kommunikation (Secure Sockets Layer) beim Senden und Empfangen von E-Mails sowie bei der Kommunikation mit dem Exchange-Server.



## <a name="synchronization-settings"></a>Synchronisierungseinstellungen

- **Menge an E-Mails für die Synchronisierung:** Wählen Sie die Anzahl der Tage von E-Mails aus, die synchronisiert werden sollen, oder wählen Sie **Unbegrenzt** aus, um alle verfügbaren E-Mail-Nachrichten zu synchronisieren.
- **Synchronisierungszeitplan:** Wählen Sie den Zeitplan aus, nach dem Geräte mit Daten vom Exchange-Server synchronisiert werden. Sie können auch **Beim Erhalt von Nachrichten** auswählen, wobei die Daten sofort beim Eintreffen synchronisiert werden, oder **Manuell**, wobei der Benutzer des Geräts die Synchronisierung initiieren muss.

## <a name="content-sync-settings"></a>Inhaltssynchronisierungseinstellungen

- **Zu synchronisierender Inhaltstyp:** Wählen Sie die Inhaltstypen aus, die auf Geräten synchronisiert werden sollen:
    - **Kontakte**
    - **Kalender**
    - **Aufgaben**

