---
title: "Intune-VPN-Einstellungen für Android-Geräte | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Erfahren Sie etwas über die Intune-Einstellungen, die Sie zum Konfigurieren von VPN-Verbindungen auf Android-Geräten verwenden können."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16c056ca-320e-4107-ad03-a0cf96c28885
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6cd3069a63bd657d1c9f5e33b96db39a3b3f98d2
ms.openlocfilehash: f93ab44889837fe8acc5dd5287b63f3b30678159


---

# <a name="vpn-settings-for-android-devices-in-intune-azure-preview"></a>VPN-Einstellungen für Android-Geräte in der Vorschau von Intune in Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Je nach den ausgewählten Einstellungen können nicht alle Werte in der folgenden Liste konfiguriert werden.

**Verbindungsname:** Geben Sie einen Namen für diese Verbindung ein. Endbenutzern wird dieser Name angezeigt, wenn sie auf ihrem Gerät die Liste der verfügbaren VPN-Verbindungen durchsuchen.
- **IP-Adresse oder FQDN:** Geben Sie die IP-Adresse oder den vollqualifizierten Domänennamen des VPN-Servers an, mit dem Geräte eine Verbindung herstellen. Beispiele: **192.168.1.1**, **vpn.contoso.com**.
- **Authentifizierungsmethode:** Wählen Sie unter folgenden Optionen aus, wie sich Geräte beim VPN-Server authentifizieren:
    - **Zertifikate:** Wählen Sie ein zuvor erstelltes SCEP- oder PKCS-Zertifikatprofil zum Authentifizieren der Verbindung aus. Ausführliche Informationen zu Zertifikatprofilen finden Sie unter [Konfigurieren von Zertifikaten](how-to-configure-certificates.md).
    - **Benutzername und Kennwort:** Endbenutzer müssen einen Benutzernamen und ein Kennwort für die Anmeldung beim VPN-Server angeben.
- **Verbindungstyp:** Wählen Sie den VPN-Verbindungstyp in der folgenden Liste von Anbietern aus:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Citrix**

- **Fingerabdruck** (nur Check Point Capsule VPN): Geben Sie eine Zeichenfolge (z.B. „Contoso-Fingerabdruckcode“) an, mit der überprüft wird, ob der VPN-Server vertrauenswürdig ist. Ein Fingerabdruck kann an den Client gesendet werden, damit dieser weiß, dass alle Server vertrauenswürdig sind, die beim Verbinden den betreffenden Fingerabdruck vorweisen. Wenn das Gerät noch nicht über den Fingerabdruck verfügt, wird der Benutzer aufgefordert, dem VPN-Server zu vertrauen, mit dem eine Verbindung hergestellt wird, während der Fingerabdruck angezeigt wird. (Der Benutzer überprüft den Fingerabdruck manuell und klickt auf „Vertrauen“, um die Verbindung herzustellen.)
- **Geben Sie Schlüssel-Wert-Paare für die Citrix-VPN-Attribute ein** (nur Citrix): Geben Sie von Citrix bereitgestellte Schlüssel-Wert-Paare ein, um die Eigenschaften der VPN-Verbindung zu konfigurieren.



<!--HONumber=Feb17_HO2-->


