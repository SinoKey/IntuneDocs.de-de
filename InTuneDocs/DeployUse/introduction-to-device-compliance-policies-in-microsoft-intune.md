---
title: Einführung in die Compliance-Richtlinien für Geräte in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3
author: karthikaraman
---
# Einführung in die Compliance-Richtlinien für Geräte in Microsoft Intune
## Was ist eine Konformitätsrichtlinie?
Ein **Konformitätsrichtlinie** definiert die Regeln und Einstellungen, die ein Gerät erfüllen muss, damit kompatibel sein.  Compliance-Richtlinien schließen sicherheitsanforderungen und andere Eigenschaften wie die Anforderungen an die PIN, Verschlüsselung und Betriebssystem.

## Wie verwende ich die Compliance-Richtlinien?
Sie können Compliance-Richtlinien mit Richtlinien für bedingten Zugriff verwenden, um sicherzustellen, dass nur die Geräte, die diese Regeln einhalten Zugriff auf Unternehmen e-Mails und Daten zulässig sind.

Sie können auch unabhängig von bedingten Zugriffsrechten Compliance-Richtlinien.

Sie stellen Konformitätsrichtlinien für Benutzer und Geräte bereit. Wenn Sie eine Konformitätsrichtlinie für einen Benutzer bereitstellen, wird die Konformität aller Geräte des Benutzers überprüft.

Die folgende Tabelle enthält die von Konformitätsrichtlinien unterstützten Gerätetypen. Zudem ist darin angegeben, wie nicht konforme Einstellungen gehandhabt werden, wenn die Richtlinie mit einer bedingten Zugriffsrichtlinie verwendet wird.

--------------
| Richtlinie Setting| Windows 8.1 und later| Windows Phone 8.1 und Later|iOS 6.0 und later| Android 4.0 und later| Samsung KNOX Standard 4.0 und later|
|------|------|------|-----|-------|
|**PIN oder Kennwort Konfiguration** | Remediated| Remediated| Remediated| Quarantined| Quarantined|
|**Geräteverschlüsselung**| N/V | Remediated| Wiederhergestellt (durch Festlegen der PIN) | Quarantined| Quarantined|
|**Jailbreak oder Rooting manipuliertes Gerät**| N/V | N/V | Unter Quarantäne gestellt (keine Einstellung) | Unter Quarantäne gestellt (keine Einstellung) | Unter Quarantäne gestellt (keine Einstellung) |
|**E-Mail-Profil**| N/V | N/V | Quarantined| N/V | N/V |
|**Minimale Betriebssystemversion**| Quarantined| Quarantined| Quarantined| Quarantined| Quarantined|
|**Maximale Version des Betriebssystems**| Quarantined| Quarantined| Quarantined| Quarantined| Quarantined|
|**Windows-Bescheinigung**| Windows 10 und Windows 10 Mobile isoliert werden.<br /><br />Die Einstellung gilt nicht für Windows 8.1| N/V | N/V | N/V | N/V |
--------------
**Wiederhergestellt** = Konformität wird vom Betriebssystem Geräts erzwungen (werden z. B. der Benutzer gezwungen, eine PIN festzulegen).  Es gibt keinen Fall, wenn die Einstellung nicht konform ist.

**Isolierte** Gerät = Betriebssystem erzwingt keine Konformität (z. B. zwingen Android-Geräte nicht den Benutzer das Gerät zu verschlüsseln).  Dies bedeutet:

-   Das Gerät wird blockiert, wenn dem Benutzer eine bedingte Zugriffsrichtlinie zugewiesen wird.

-   Das Unternehmensportal benachrichtigt den Benutzer bezüglich aller Konformitätsprobleme.

## Nächste Schritte
[Erstellen Sie eine Konformitätsrichtlinie Gerät](create-a-device-compliance-policy-in-microsoft-intune.md)

[Bereitstellen einer Konformitätsrichtlinie Gerät](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### Weitere Informationen:
[Verwalten des Zugriffs auf E-Mail und SharePoint mit Microsoft Intune](manage-access-to-email-and-O365-services-with-intune.md)


<!--HONumber=Mar16_HO3-->


