---
title: "Konfigurieren der Richtlinien für die Gerätekonformität und App-Verwaltung während einer Migration von Intune"
description: "Dieser Artikel gibt einen Überblick über die für das Konfigurieren der Richtlinien für die Gerätekompatibilität und die App-Verwaltung notwendigen Schritte während einer Migration von Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0062d08e-e5b3-4f73-8b64-5ad95adbe945
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5e848dda6643a28141a8f5f1d0bdc01f2bd9d390
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2017
---
# <a name="configure-device-compliance-and-app-management-policies"></a>Konfigurieren von Richtlinien für die Gerätekonformität und App-Verwaltung

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

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

Sie können Gerätegruppen erstellen, wenn Sie unterschiedlichste Verwaltungsaufgaben basierend auf Geräteidentität statt auf Benutzeridentität durchführen müssen.

Benutzergruppen sind nützlich bei der Verwaltung von Geräten ohne dedizierte Benutzer, wie z.B Kioskgeräte, oder von Geräten, die für Schichtarbeiter freigegeben oder einem bestimmtem Standort zugewiesen wurden.

Wenn Sie Gerätegruppen schon vor der Geräteregistrierung konfigurieren, können Sie Gerätekategorien nutzen, um Geräte bei der Registrierung automatisch zu gruppieren, um deren Geräterichtlinien automatisch zu erhalten. [Erste Schritte mit Gruppen](/intune/groups-get-started).

### <a name="task-2-use-resource-access-profiles-wi-fi-vpn-and-email-certificates"></a>Aufgabe 2: Verwenden von Profilen für den Ressourcenzugriff (WLAN, VPN und E-Mail-Zertifikate)

Profile für den Ressourcenzugriff stellen Zertifikate und Zugriffskonfigurationen für die Geräteregistrierung bereit.

Wie zuvor im Abschnitt „Einschätzen von MDM-Anforderungen“ erörtert, müssen Sie bei Verwenden der zertifikatbasierten Authentifizierung [Zertifikate konfigurieren](/intune/certificates-configure).

### <a name="task-3-create-and-deploy-device-configuration-profiles"></a>Aufgabe 3: Erstellen und Bereitstellen von Gerätekonfigurationsprofilen

Sie müssen ein Gerätekonfigurationsprofil erstellen, um Einstellungen auf der Geräteebene zu erzwingen,, wie z.B: Deaktivieren der Kamera, App Store, Konfigurieren des Einzelanwendungsmodus, Startbildschirm, etc.

- Erfahren Sie mehr über [Geräteprofile](/intune/device-profiles).

####  <a name="direct-import-of-ios-configuration-profiles-optional"></a>Direkter Import von iOS-Konfigurationsprofilen (optional)

-   **iOS-Profile von Apple Configurator (iOS 7.1 und höher):** Wenn Ihre vorhandene MDM-Projektmappe Apple Configurator-Profile verwendet (MOBILECONFIG-Dateien), kann Intune diese direkt als benutzerdefinierte Konfigurationsrichtlinien importieren.

-   **Richtlinien für die Konfiguration von mobilen iOS-Anwendungen:** Wenn Ihre vorhandene MDM-Lösung Richtlinien für die Konfiguration von mobilen iOS-Anwendungen verwendet, kann Intune diese direkt importieren, sofern sie dem XML-Format entsprechen, das von Apple für Eigenschaftenlisten festgelegt wurde.

- Erfahren Sie, wie Sie eine benutzerdefinierte Richtlinie für [iOS](/intune/custom-settings-ios) hinzufügen können.

### <a name="task-4-create-and-deploy-device-compliance-policies-optional"></a>Aufgabe 4: Erstellen und Bereitstellen einer Gerätekompatibilitätsrichtlinie (optional)

Gerätekonformitätsrichtlinien werten sicherheitsorientierte Einstellungen aus und bieten eine Berichterstattung, die anzeigt, ob die Geräte den Unternehmensansprüchen entsprechen. Gerätekompatibilitätsrichtlinien werten sicherheitsorientierte Faktoren wie die folgenden aus:

-   PIN-Länge

-   Status „Jail-broken“ (Nutzungsbeschränkungen entfernt)

-   Betriebssystemversion

Hier finden Sie weitere Ressourcen für die Einstellungen der Gerätekompatibilität:

-   Erfahren Sie mehr über [Gerätekompatibilitätsrichtlinien](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

-   Erfahren Sie, wie Sie eine [Gerätekompatibilitätsrichtlinie erstellen](/intune-classic/deploy-use/create-a-device-compliance-policy-in-microsoft-intune) können.

### <a name="task-5-publish-and-deploy-apps"></a>Aufgabe 5: Veröffentlichen und Bereitstellen von Apps

Wenn Sie MDM mit Intune verwenden, können Sie Apps bereitstellen, indem Sie entweder deren automatische Installation verlangen oder sie über das Unternehmensportal zur Verfügung stellen.

-   Erfahren Sie, wie Sie [Apps hinzufügen](/intune-classic/deploy-use/add-apps) können.

-   Erfahren Sie, wie Sie [Apps bereitstellen](/intune-classic/deploy-use/deploy-apps) können.

### <a name="task-6-enable-device-enrollment"></a>Aufgabe 6: Aktivieren der Geräteregistrierung

Die Registrierung stellt die Verwaltung durch die Bereitstellung von Steuerelementen auf dem Gerät her. Erfahren Sie, wie Sie sich [auf die Registrierung von firmeneigenen und persönlichen Geräten vorbereiten](/intune/device-enrollment) können.

## <a name="next-steps"></a>Nächste Schritte 

[Konfigurieren von App-Schutzrichtlinien (optional)](migration-guide-app-protection-policies.md)
