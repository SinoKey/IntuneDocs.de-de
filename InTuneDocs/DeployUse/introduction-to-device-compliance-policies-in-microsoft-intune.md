---
title: "Gerätekompatibilitätsrichtlinien | Microsoft Intune"
description: "In diesem Thema werden die Konzepte erläutert, die Sie kennen müssen, um zu verstehen, was Gerätekompatibilitätsrichtlinien sind und wie sie funktionieren."
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c72c8e1a764af73ba4d421ca6637ee91ab7bca0a
ms.openlocfilehash: f34ff402ae1012a471219647e94bc1f5225a6f07


---

# Gerätekompatibilitätsrichtlinien in Microsoft Intune
## Was ist eine Kompatibilitätsrichtlinie?
Um Unternehmensdaten zu schützen, müssen Sie sicherstellen, dass die Geräte, die für den Zugriff auf Unternehmens-Apps und -daten verwendet werden, mit bestimmten Regeln, z. B. Verwenden einer PIN für den Zugriff auf das Gerät, und der Verschlüsselung von Daten kompatibel sind, die auf dem Gerät gespeichert sind. Eine Gruppe solcher Regeln wird als Kompatibilitätsrichtlinie bezeichnet.

## Wie verwende ich Kompatibilitätsrichtlinien?
Sie können Kompatibilitätsrichtlinien mit Richtlinien für den bedingten Zugriff verwenden, um nur Geräte zuzulassen, die Kompatibilitätsrichtlinienregeln für den Zugriff auf E-Mail und andere Dienste entsprechen. Lesen Sie den Artikel [Einschränken des Zugriffs auf E-Mail- und Office 365-Dienste](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), um zu verstehen, wie die beiden Richtlinien zusammen verwendet werden können.

Sie können Kompatibilitätsrichtlinien auch unabhängig vom bedingten Zugriff nutzen. Bei unabhängiger Nutzung werden die Zielgeräte ausgewertet und mit ihrem Kompatibilitätsstatus gemeldet. Sie können beispielsweise einen Bericht dazu erstellen, wie viele Geräte nicht verschlüsselt sind oder per Jailbreak oder Rootzugriff manipuliert wurden. Allerdings gelten bei unabhängiger Nutzung keine Zugriffsbeschränkungen für Unternehmensressourcen.

Sie stellen Kompatibilitätsrichtlinien für Benutzer bereit. Wenn Sie eine Kompatibilitätsrichtlinie für einen Benutzer bereitstellen, wird die Kompatibilität der Geräte des Benutzers überprüft.

Die folgende Tabelle enthält die von Konformitätsrichtlinien unterstützten Gerätetypen. Zudem ist darin angegeben, wie nicht konforme Einstellungen gehandhabt werden, wenn die Richtlinie mit einer bedingten Zugriffsrichtlinie verwendet wird.

--------------

|Richtlinieneinstellung| Windows 8.1 und höher| Windows Phone 8.1 und höher| iOS 6.0 und höher|Android 4,0 und höher<br/>Samsung KNOX Standard 4.0 und höher|
|-----|----|----|----|
|**PIN- oder Kennwortkonfiguration** |Wiederhergestellt|Wiederhergestellt|Wiederhergestellt|Isoliert|
|**Geräteverschlüsselung**|N/V|Wiederhergestellt|Wiederhergestellt (durch Festlegen der PIN)|Isoliert|
|**Per Jailbreak oder Rootzugriff manipuliertes Gerät**|N/V|N/V|Unter Quarantäne gestellt (keine Einstellung)|Unter Quarantäne gestellt (keine Einstellung)|
|**E-Mail-Profil**|N/V|N/V|Isoliert|N/V|
|**Minimale Version des Betriebssystems**|Isoliert|Isoliert|Isoliert|Isoliert|
|**Maximale Version des Betriebssystems**|Isoliert| Isoliert| Isoliert| Isoliert|
|**Windows-Integritätsnachweis**|Windows 10 und Windows 10 Mobile sind isoliert.<br /><br />Einstellung gilt nicht für Windows 8.1|N/V|N/V|N/V|
--------------
**Wiederhergestellt** = Konformität wird vom Betriebssystem des Geräts erzwungen (z. B. wird der Benutzer gezwungen, eine PIN festzulegen).  Es ist nie der Fall, wenn die Einstellung nicht kompatibel ist.

**Unter Quarantäne** = Das Betriebssystem des Geräts erzwingt keine Konformität (z. B. zwingen Android-Geräte den Benutzer nicht dazu, das Gerät zu verschlüsseln). Wenn die Geräte nicht kompatibel sind, erfolgen die folgenden Aktionen:

-   Das Gerät wird blockiert, wenn dem Benutzer eine bedingte Zugriffsrichtlinie zugewiesen wird.

-   Das Unternehmensportal benachrichtigt den Benutzer über Kompatibilitätsprobleme.

## Nächste Schritte
[Erstellen einer Kompatibilitätsrichtlinie](create-a-device-compliance-policy-in-microsoft-intune.md)

[Bereitstellen und Überwachen einer Kompatibilitätsrichtlinie für Geräte](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### Weitere Informationen:
[Beschränken des Zugriffs auf E-Mail- und Office 365-Dienste](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


