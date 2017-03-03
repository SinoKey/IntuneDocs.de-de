---
title: "Intune-E-Mail-Einstellungen für Android-Geräte | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Erfahren Sie etwas über die Intune-Einstellungen, die Sie zum Konfigurieren von E-Mail-Verbindungen auf Android-Geräten verwenden können."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4d3458cc-fcaa-4648-b13f-bf1f0616c1c5
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 29a4346a04470192553ad2d4f0962a2a21d637ec
ms.lasthandoff: 02/16/2017


---

# <a name="email-profile-settings-for-android-devices-in-microsoft-intune"></a>E-Mail-Profileinstellungen für Android-Geräte in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]



- **E-Mail-Server:** Der Hostname Ihres Exchange-Servers.
- **Kontoname:** Der Anzeigename für das E-Mail-Konto so, wie er den Benutzern auf ihren Geräten angezeigt wird.
- **Benutzernamensattribut aus AAD:** Dies ist das Attribut in Active Directory (AD) oder Azure AD, das verwendet wird, um den Benutzernamen für dieses E-Mail-Profil zu generieren. Wählen Sie **Primäre SMTP-Adresse** aus, z.B. user1@contoso.com, oder **Benutzerprinzipalname**, z.B. „user1“ oder user1@contoso.com.
- **E-Mail-Adressattribut aus AAD:** Die Art der Generierung der E-Mail-Adresse für den Benutzer auf den einzelnen Geräten. Wählen Sie **Primäre SMTP-Adresse** aus, um die primäre SMTP-Adresse zum Anmelden bei Exchange zu verwenden. Verwenden Sie **Benutzerprinzipalname** aus, um den vollständigen Benutzerprinzipalnamen als E-Mail-Adresse zu verwenden.
- **Authentifizierungsmethode:** Wählen Sie entweder **Benutzername und Kennwort** oder **Zertifikate** als Authentifizierungsmethode aus, die vom E-Mail-Profil verwendet werden soll.
    - Wenn Sie **Zertifikat** ausgewählt haben, wählen Sie ein zuvor erstelltes SCEP- oder PKCS-Zertifikatprofil aus, das zur Authentifizierung der Exchange-Verbindung verwendet werden soll.

## <a name="security-settings"></a>Sicherheitseinstellungen

- **SSL:** Verwenden Sie SSL-Kommunikation (Secure Sockets Layer) beim Senden und Empfangen von E-Mails sowie bei der Kommunikation mit dem Exchange-Server.
- **S/MIME:** Ausgehende E-Mails werden mit S/MIME-Verschlüsselung gesendet.
    - Wenn Sie **Zertifikat** ausgewählt haben, wählen Sie ein zuvor erstelltes SCEP- oder PKCS-Zertifikatprofil aus, das zur Authentifizierung der Exchange-Verbindung verwendet werden soll.

## <a name="synchronization-settings"></a>Synchronisierungseinstellungen

- **Menge an E-Mails für die Synchronisierung:** Wählen Sie die Anzahl der Tage von E-Mails aus, die synchronisiert werden sollen, oder wählen Sie **Unbegrenzt** aus, um alle verfügbaren E-Mail-Nachrichten zu synchronisieren.
- **Synchronisierungszeitplan:** Wählen Sie den Zeitplan aus, nach dem Geräte mit Daten vom Exchange-Server synchronisiert werden. Sie können auch **Beim Erhalt von Nachrichten** auswählen, wobei die Daten sofort beim Eintreffen synchronisiert werden, oder **Manuell**, wobei der Benutzer des Geräts die Synchronisierung initiieren muss.

## <a name="content-sync-settings"></a>Inhaltssynchronisierungseinstellungen

- **Zu synchronisierender Inhaltstyp:** Wählen Sie die Inhaltstypen aus, die auf Geräten synchronisiert werden sollen:
    - **Kontakte**
    - **Kalender**
    - **Aufgaben**

