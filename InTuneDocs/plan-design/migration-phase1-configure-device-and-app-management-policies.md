---
title: "Konfigurieren der Richtlinien für die Gerätekompatibilität und die App-Verwaltung während einer Migration von Intune | Microsoft-Dokumentation"
description: "Dieser Artikel gibt einen Überblick über die für das Konfigurieren der Richtlinien für die Gerätekompatibilität und die App-Verwaltung notwendigen Schritte während einer Migration von Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0062d08e-e5b3-4f73-8b64-5ad95adbe945
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 5904b117ccab9046d2afde4a761b4724431a6302
ms.lasthandoff: 03/27/2017


---

# <a name="phase-1-configure-device-compliance-and-app-management-policies"></a>Phase 1: Konfigurieren von Richtlinien für die Gerätekompatibilität und die App-Verwaltung

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Das Hauptziel der Migration zu Intune ist die Registrierung aller Geräte und die Kompatibilität aller Geräte mit ihren Richtlinien. Geräterichtlinien helfen Ihnen nicht nur dabei, firmeneigene Geräte mit nur einem Benutzer zu verwalten, sondern auch bei der Verwaltung persönlicher (Bring-Your-Own-Device, BYOD) und freigegebener Geräte, wie z.B. Kiosks, Verkaufsortcomputer, Tablets, die von mehreren Schülern in einem Klassenzimmer verwendet werden, oder Geräte ohne Benutzer (nur iOS).

Jede Geräteplattform hat möglicherweise unterschiedliche Einstellungen, aber Geräterichtlinien von Intune funktionieren durch folgende MDM-Funktionen mit jeder Geräteplattform:

-   Regulierung der Zahl von Geräten, die jeder Benutzer registriert

-   Verwalten der Geräteeinstellungen (z.B Verschlüsselung auf der Geräteebene, Länge des Kennworts, Kameragebrauch)

-   Bereitstellen von Apps, E-Mail-Profilen, VPN-Profilen, etc.

-   Auswerten der Kriterien für Sicherheitskompatibilitätsrichtlinien auf der Geräteebene

> [!IMPORTANT]
> Geräteverwaltungsrichtlinien werden einzelnen Geräten oder Benutzern nicht direkt zugewiesen, sondern ganzen Benutzergruppen. Die Richtlinien können direkt auf Benutzergruppen und somit auch auf das Benutzergerät angewendet werden; die Richtlinien können auch auf eine Gerätegruppe und somit auch auf Gruppenmitglieder angewendet werden.

## <a name="task-list-for-device-compliance-policies"></a>Aufgabenliste für Gerätekompatibilitätsrichtlinien

### <a name="task-1-add-device-groups-optional"></a>Aufgabe 1: Mobile Gerätegruppen hinzufügen (optional)

Das [klassische Intune-Portal](https://manage.microsoft.com/) ermöglicht es Ihnen, Gerätegruppen zu erstellen, wenn Sie unterschiedlichste Verwaltungsaufgaben basierend auf Geräteidentität statt auf Benutzeridentität durchführen müssen.

Benutzergruppen sind nützlich bei der Verwaltung von Geräten ohne dedizierte Benutzer, wie z.B Kioskgeräte, oder von Geräten, die für Schichtarbeiter freigegeben oder einem bestimmtem Standort zugewiesen wurden.

Wenn Sie Gerätegruppen schon vor der Geräteregistrierung konfigurieren, können Sie Gerätekategorien nutzen, um Geräte bei der Registrierung automatisch zu gruppieren, um deren Geräterichtlinien automatisch zu erhalten.

-   Erfahren Sie, wie Sie [Gerätegruppen hinzufügen](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5) können.

-   Erfahren Sie, wie Sie [Gerätekategorien konfigurieren](https://docs.microsoft.com/intune/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune) können.

### <a name="task-2-use-resource-access-profiles-wi-fi-vpn-and-email-certificates"></a>Aufgabe 2: Verwenden von Profilen für den Ressourcenzugriff (WLAN, VPN und E-Mail-Zertifikate)

Profile für den Ressourcenzugriff stellen Zertifikate und Zugriffskonfigurationen für die Geräteregistrierung bereit.

Wie schon weiter oben im Abschnitt „MDM-Anforderungen analysieren“ besprochen, benötigen Sie eine [PKI-Infrastruktur](https://docs.microsoft.com/intune/deploy-use/secure-resource-access-with-certificate-profiles), um VPN-, WLAN- und E-Mail-Zertifikate bereitzustellen, wenn Sie die zertifikatbasierte Authentifizierung verwenden.

#### <a name="direct-import-of-resource-access-profiles-optional"></a>Direktes Importieren von Profilen für den Ressourcenzugriff (optional)

Wenn Ihre vorhandene MDM-Projektmappe einen Mechanismus für den Export von E-Mail-, WLAN- und VPN-Profilen ins XML-Format bietet, können Sie möglicherweise die XML-Datei nutzen und sie einfach nur in Intune importieren; dazu können Sie OMA-URI verwenden, um benutzerdefinierte Profile für iOS-, Android- und Windows-Geräte zu erstellen.

-   Erfahren Sie, wie Sie eine benutzerdefinierte Richtlinie für [iOS](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune)-, [Android](https://docs.microsoft.com/intune/deploy-use/android-policy-settings-in-microsoft-intune)- und [Windows](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)-Geräte hinzufügen können.

### <a name="task-3-create-and-deploy-device-configuration-profiles"></a>Aufgabe 3: Erstellen und Bereitstellen von Gerätekonfigurationsprofilen

Sie müssen ein Gerätekonfigurationsprofil erstellen, um Einstellungen auf der Geräteebene zu erzwingen,, wie z.B: Deaktivieren der Kamera, App Store, Konfigurieren des Einzelanwendungsmodus, Startbildschirm, etc.

- Erfahren Sie, wie Sie [Gerätekonfigurationsprofile erstellen](https://docs.microsoft.com/intune-azure/configure-devices/how-to-create-device-profiles) können.

####  <a name="direct-import-of-ios-configuration-profiles-optional"></a>Direkter Import von iOS-Konfigurationsprofilen (optional)

-   **iOS-Profile von Apple Configurator (iOS 7.1 und höher):** Wenn Ihre vorhandene MDM-Projektmappe Apple Configurator-Profile verwendet (MOBILECONFIG-Dateien), kann Intune diese direkt als benutzerdefinierte Konfigurationsrichtlinien importieren.

-   **Richtlinien für die Konfiguration von mobilen iOS-Anwendungen:** Wenn Ihre vorhandene MDM-Lösung Richtlinien für die Konfiguration von mobilen iOS-Anwendungen verwendet, kann Intune diese direkt importieren, sofern sie dem XML-Format entsprechen, das von Apple für Eigenschaftenlisten festgelegt wurde.

- Erfahren Sie, wie Sie eine benutzerdefinierte Richtlinie für [iOS](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune#custom-policy-settings) hinzufügen können.

### <a name="task-4-create-and-deploy-device-compliance-policies-optional"></a>Aufgabe 4: Erstellen und Bereitstellen einer Gerätekompatibilitätsrichtlinie (optional)

Gerätekonformitätsrichtlinien werten sicherheitsorientierte Einstellungen aus und bieten eine Berichterstattung, die anzeigt, ob die Geräte den Unternehmensansprüchen entsprechen. Gerätekompatibilitätsrichtlinien werten sicherheitsorientierte Faktoren wie die folgenden aus:

-   PIN-Länge

-   Status „Jail-broken“ (Nutzungsbeschränkungen entfernt)

-   Betriebssystemversion

Hier finden Sie weitere Ressourcen für die Einstellungen der Gerätekompatibilität:

-   Erfahren Sie mehr über [Gerätekompatibilitätsrichtlinien](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

-   Erfahren Sie, wie Sie eine [Gerätekompatibilitätsrichtlinie erstellen](https://docs.microsoft.com/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune) können.

### <a name="task-5-publish-and-deploy-apps"></a>Aufgabe 5: Veröffentlichen und Bereitstellen von Apps

Wenn Sie MDM mit Intune verwenden, können Sie Apps bereitstellen, indem Sie entweder deren automatische Installation verlangen oder sie über das Unternehmensportal zur Verfügung stellen.

-   Erfahren Sie, wie Sie [Apps hinzufügen](https://docs.microsoft.com/intune/deploy-use/add-apps) können.

-   Erfahren Sie, wie Sie [Apps bereitstellen](https://docs.microsoft.com/intune/deploy-use/deploy-apps) können.

### <a name="task-6-enable-device-enrollment"></a>Aufgabe 6: Aktivieren der Geräteregistrierung

Die Registrierung stellt die Verwaltung durch die Bereitstellung von Steuerelementen auf dem Gerät her.

-   Erfahren Sie, wie Sie sich [auf die Registrierung von firmeneigenen und persönlichen Geräten vorbereiten](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune) können.

-   Erfahren Sie, wie Sie [unternehmenseigene iOS-Geräte registrieren](https://docs.microsoft.com/intune/deploy-use/manage-corporate-owned-devices) können.

Wenn Sie freigegebene oder benutzerunabhängige Geräte registrieren müssen, können Sie ein [Geräteregistrierungsmanager-Konto (DEM)](https://docs.microsoft.com/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) verwenden.

## <a name="next-steps"></a>Nächste Schritte 

[Phase 1: Konfigurieren von App-Schutzrichtlinien (optional)](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-app-protection-policies)

