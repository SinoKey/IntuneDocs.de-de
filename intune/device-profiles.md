---
title: "Was sind Geräteprofile in Microsoft Intune? | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie mehr über Intune-Geräteprofile und wie sie Ihnen helfen können, Geräte in Ihrem Unternehmen zu verwalten und zu schützen."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 54b20d405613a67e54e9d22df45a3055f093fafa
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---

# <a name="what-are-microsoft-intune-device-profiles"></a>Was sind Microsoft Intune Geräteprofile?

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Verwenden Sie die Workload **Gerätekonfiguration** von Microsoft Intune, um Einstellungen und Features auf allen Geräten zu verwalten. Sie werden diesen Workload größtenteils verwenden, um Geräteprofile zu erstellen, die Ihnen die Verwaltung und Steuerung von einer Vielzahl von unterschiedlichen Features und Funktionen auf den von Ihnen verwalteten Geräten erlauben.

Wenn Sie diese Workload öffnen, werden die folgenden Optionen angezeigt:

- **Übersicht:** Auf dieser Seite finden Sie den Status und Berichte, mit denen Sie Gerätekonfigurationen, die Sie Benutzern und Geräten zugewiesen haben, überwachen.
- **Profile verwalten:** In diesem Abschnitt erstellen Sie Gerätekonfigurationsprofile. Unten finden Sie eine Liste aller Profiltypen, die Sie erstellen können.
- **Zertifizierungsstelle einrichten:** Dieser Workflow führt Sie durch die erforderlichen Schritte zum Konfigurieren von Zertifikaten. Sie müssen ihn durchführen, wenn Sie mit Intune-Zertifikatprofilen arbeiten möchten.

## <a name="getting-started"></a>Erste Schritte

Der Workflow zum Erstellen von Geräteprofilen ist für alle Profile ähnlich. Weitere Informationen zum Erstellen von Profilen finden Sie unter [Erstellen von Microsoft Intune-Gerätekonfigurationsprofilen](device-profile-create.md). Lesen Sie anschließend weitere spezifische Informationen zu den Einstellungen für die einzelnen Profiltypen.

Sie können die folgenden Funktionen auf Ihren Geräten verwalten:

## <a name="device-features"></a>Gerätefunktionen

Mit Gerätefunktionen können Sie Funktionen auf iOS- und macOS-Geräten wie AirPrint, Benachrichtigungen und freigegebene Gerätekonfigurationen steuern.
Weitere Informationen finden Sie unter [How to configure device feature settings (Konfigurieren der Gerätefunktionseinstellungen)](device-features-configure.md). Unterstützt iOS und macOS.

## <a name="device-restrictions"></a>Geräteeinschränkungen
Mit Geräteeinschränkungen können Sie eine Vielzahl von Einstellungen auf Geräten für eine ganze Reihe von Kategorien steuern, einschließlich Sicherheit, Browser, Hardware und Einstellungen zur Datenfreigabe. Sie könnten beispielsweise ein Geräteeinschränkungsprofil erstellen, das verhindert, dass Benutzer von iOS-Geräten auf die Kamera des Geräts zugreifen.
Weitere Informationen finden Sie unter [Konfigurieren von Einstellungen für Geräteeinschränkungen](device-restrictions-configure.md). Unterstützt: Android, iOS, macOS, Windows 10 und Windows 10 Team.

## <a name="email"></a>E-Mail
Mit E-Mail-Profilen können Sie Exchange ActiveSync-E-Mail-Einstellungen auf Ihren verwalteten Geräten erstellen, zuweisen und überwachen. Durch das Zuweisen dieser Einstellungen stellen Sie Einheitlichkeit sicher, reduzieren die Anzahl von Supportanfragen und erlauben Endbenutzern den Zugriff auf Unternehmens-E-Mails auf ihren persönlichen Geräten, ohne dass ihrerseits eine Konfiguration erforderlich wäre.
Weitere Informationen finden Sie unter [Konfigurieren von E-Mail-Einstellungen](email-settings-configure.md). Unterstützt: Android, iOS, Windows 8.1 und Windows 10.

## <a name="wi-fi"></a>WLAN
Verwenden Sie WLAN-Profile, um Benutzern und Geräten in Ihrer Organisation Einstellungen für Drahtlosnetzwerke zuzuweisen. Wenn Sie ein WLAN-Profil zuweisen, erhalten Ihre Benutzer Zugriff auf Ihr Unternehmens-WLAN, ohne es selbst konfigurieren zu müssen.
Weitere Informationen finden Sie unter [Konfigurieren von WLAN-Einstellungen](wi-fi-settings-configure.md). Unterstützt: Android, iOS, macOS und Windows 8.1 (nur Import).

## <a name="vpn"></a>VPN
Virtuelle private Netzwerke (virtual private networks, VPNs) bieten Ihren Benutzern sicheren Remotezugriff auf Ihr Unternehmensnetzwerk. Geräte verwenden ein VPN-Verbindungsprofil, um eine Verbindung mit dem VPN-Server zu initiieren. VPN-Profile ermöglichen Ihnen die Zuweisung von VPN-Einstellungen für Benutzer und Geräte in Ihrer Organisation, damit diese einfach eine sichere Verbindung mit dem Netzwerk herstellen können.
Weitere Informationen finden Sie unter [Konfigurieren von VPN-Einstellungen](vpn-settings-configure.md).
Unterstützt: Android, iOS, macOS, Windows Phone 8.1, Windows 8.1 und Windows 10.

## <a name="education"></a>Education
Damit können Sie Optionen für die Windows Take a Test-App konfigurieren. Wenn Sie diese Optionen konfigurieren, können keine anderen Apps auf dem Gerät ausgeführt werden, bis der Test abgeschlossen ist.
Weitere Informationen finden Sie unter [How to configure education settings (Konfigurieren von Education-Einstellungen)](education-settings-configure.md).

## <a name="certificates"></a>Zertifikate
Mit diesem Profiltyp können Sie vertrauenswürdige SCEP- und PKCS-Zertifikate konfigurieren, die Geräten zugewiesen und zum Authentifizieren von WLAN-, VPN- und E-Mail-Profilen verwendet werden können.
Weitere Informationen finden Sie unter [Konfigurieren von Zertifikaten](certificates-configure.md). Unterstützt: Android, iOS, Windows Phone 8.1, Windows 8.1 und Windows 10.

## <a name="edition-upgrade"></a>Upgrade der Edition
Mit diesem Profiltyp können Sie automatisch Geräte, die eine Version von Windows 10 ausführen, auf eine neuere Version aktualisieren. Weitere Informationen finden Sie unter [Konfigurieren von Upgrades für Windows 10-Editionen](edition-upgrade-configure-windows-10.md). Unterstützt: nur Windows 10.

## <a name="windows-information-protection"></a>Windows Information Protection
Windows Information Protection unterstützt Sie dabei, das Unternehmen vor Datenlecks zu schützen, ohne gleichzeitig die Benutzerfreundlichkeit für die Mitarbeiter einzuschränken. Die Lösung schützt auch Unternehmens-Apps und -Daten vor versehentlichen Datenlecks auf unternehmenseigenen sowie auf persönlichen Geräten, die die Mitarbeiter zur Arbeit mitbringen – ohne dass Sie Ihre Umgebung oder andere Apps ändern müssen.
Weitere Informationen finden Sie unter [Konfigurieren von Windows Information Protection](windows-information-protection-configure.md). Unterstützt: nur Windows 10.

## <a name="custom"></a>Benutzerdefiniert
Mithilfe von benutzerdefinierten Einstellungen können Sie Geräteeinstellungen zuweisen, die nicht in Intune integriert sind. Auf Android-Geräten können Sie z.B. OMA-URI-Werte angeben, die das Gerät konfigurieren. Auf iOS-Geräten können Sie eine Konfigurationsdatei importieren, die Sie in Apple Configurator erstellt haben.
Weitere Informationen finden Sie unter [Konfigurieren von benutzerdefinierten Einstellungen](custom-settings-configure.md). Unterstützt: Android, iOS, macOS und Windows Phone 8.1.

