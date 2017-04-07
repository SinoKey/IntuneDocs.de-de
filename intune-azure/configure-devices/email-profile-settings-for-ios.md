---
title: "E-Mail-Einstellungen für iOS-Geräte in Intune"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie etwas über die Intune-Einstellungen, die Sie zum Konfigurieren von E-Mail-Verbindungen auf iOS-Geräten verwenden können."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9f0fa6af-3669-439a-bd0d-75d8b1a0b135
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 78f99bba07180c06f979fec997a7bfb749d879c8
ms.openlocfilehash: f18fd3ceee5c73a96444092691c590c7d9a7419c
ms.lasthandoff: 02/24/2017


---

# <a name="email-profile-settings-for-ios-devices-in-microsoft-intune"></a>Einstellungen für das E-Mail-Profil für iOS-Geräte in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]



- **E-Mail-Server:** Der Hostname Ihres Exchange-Servers.
- **Kontoname:** Der Anzeigename für das E-Mail-Konto so, wie er den Benutzern auf ihren Geräten angezeigt wird.
- **Benutzernamensattribut aus AAD:** Dies ist das Attribut in Active Directory (AD) oder Azure AD, das verwendet wird, um den Benutzernamen für dieses E-Mail-Profil zu generieren. Wählen Sie **Primäre SMTP-Adresse** aus, z.B. **user1@contoso.com**, oder **Benutzerprinzipalname**, z.B. **user1** oder **user1@contoso.com**.
- **E-Mail-Adressattribut aus AAD:** Die Art der Generierung der E-Mail-Adresse für den Benutzer auf den einzelnen Geräten. Wählen Sie **Primäre SMTP-Adresse** aus, um die primäre SMTP-Adresse zum Anmelden bei Exchange zu verwenden. Verwenden Sie **Benutzerprinzipalname** aus, um den vollständigen Benutzerprinzipalnamen als E-Mail-Adresse zu verwenden.
- **Authentifizierungsmethode:** Wählen Sie entweder **Benutzername und Kennwort** oder **Zertifikate** als Authentifizierungsmethode aus, die vom E-Mail-Profil verwendet werden soll.
    - Wenn Sie **Zertifikat** ausgewählt haben, wählen Sie ein zuvor erstelltes SCEP- oder PKCS-Zertifikatprofil aus, das zur Authentifizierung der Exchange-Verbindung verwendet werden soll.
- **SSL:** Verwenden Sie SSL-Kommunikation (Secure Sockets Layer) beim Senden und Empfangen von E-Mails sowie bei der Kommunikation mit dem Exchange-Server.
- **S/MIME**: Ausgehende E-Mails werden mithilfe der S/MIME-Signatur gesendet.
    - Wenn Sie **Zertifikat** ausgewählt haben, wählen Sie ein zuvor erstelltes SCEP- oder PKCS-Zertifikatprofil aus, das zur Authentifizierung der Exchange-Verbindung verwendet werden soll.
- **Menge an E-Mails für die Synchronisierung:** Wählen Sie die Anzahl der Tage von E-Mails aus, die synchronisiert werden sollen, oder wählen Sie **Unbegrenzt** aus, um alle verfügbaren E-Mail-Nachrichten zu synchronisieren.
- **Verschieben von Nachrichten in andere E-Mail-Konten zulassen:** Hiermit können Benutzer E-Mail-Nachrichten zwischen verschiedenen Konten verschieben, die auf ihrem Gerät konfiguriert sind.
- **E-Mail-Versand aus Drittanbieteranwendungen zulassen:** erlaubt dem Benutzer die Auswahl dieses Profils als das Standardkonto für das Senden von E-Mails und erlaubt Anwendungen von Drittanbietern das Öffnen von E-Mails in der nativen E-Mail-App, um beispielsweise Dateien an E-Mails anzuhängen.
- **Kürzlich verwendete E-Mail-Adressen synchronisieren:** Mit diesem Feature können Benutzer die Liste der E-Mail-Adressen, die vor Kurzem auf dem Gerät verwendet wurden, mit dem Server synchronisieren.

