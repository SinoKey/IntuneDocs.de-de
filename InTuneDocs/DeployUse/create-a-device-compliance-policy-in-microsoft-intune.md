---
title: "Erstellen einer Kompatibilitätsrichtlinie für Geräte in Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5336dac0-a2cc-4cd4-8511-67e4f95bd700
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ded7bd6c971a9448ad6e6492ebc5e42dfcb5d76e
ms.openlocfilehash: f4f036fc1b6fe2394e05907e2d14289c9fba3426


---

# Erstellen einer Kompatibilitätsrichtlinie für Geräte in Microsoft Intune
Dieses Thema beschreibt die Schritte, die zum Erstellen einer Kompatibilitätsrichtlinie für ein Gerät verwendet werden können, und der ein Gerät entsprechen muss, um als kompatibel angesehen zu werden.

##  Schritt 1: Hinzufügen einer neuen Richtlinie
  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Optionen **Richtlinie** &gt; **Konformitätsrichtlinien** &gt; **Hinzufügen**.

  ![Screenshot der Kompatibilitätsrichtlinienseite in der Intune-Verwaltungskonsole mit der Option „Hinzufügen“ im Menü oben auf der Seite](./media/intune-sa-3a-add-compliance-policy.png)

##  Schritt 2: Konfigurieren von Einstellungen
Aktivieren Sie auf der Seite **Richtlinie erstellen** die folgenden Einstellungen nach Bedarf:
  -   Die Einstellungen für die Systemsicherheit, wie Kennwort, Verschlüsselung
  -   Einstellungen für die Geräteintegrität, etwa ob ein Gerät per Jailbreak manipuliert wurde oder vom Windows-Dienst für den Nachweis der Geräteintegrität als intakt gemeldet wird.
  -   Einstellungen von Geräteeigenschaften, etwa die erforderliche minimale oder die zulässige maximale Betriebssystemversion.
![Screenshot der Registerkarte „Allgemein“ auf der Seite „Richtlinie erstellen“ ](./media/intune-sa-3b-create-policy.png)

##  Schritt 3: Speichern der Richtlinie
Wählen Sie danach die Option **Richtlinie speichern**.

Sie haben die Möglichkeit, die Richtlinie direkt nach dem Speichern bereitzustellen oder können sich für die spätere Bereitstellung entscheiden. Die neue Richtlinie wird im Knoten **Konformitätsrichtlinien** des Arbeitsbereichs **Richtlinie** angezeigt.

## Unterstützte Richtlinieneinstellungen
In der folgenden Tabelle sind die Einstellungen für die Kompatibilitätsrichtlinie und die Plattformen aufgelistet, auf denen sie unterstützt werden.

-------------
|Einstellung|iOS|Android|Windows|
|-----|----|-----|-----|
|Anfordern eines Kennworts zum Entsperren mobiler Geräte|iOS 6 und höher|Android 4,0 und höher <br>Samsung KNOX Standard 4.0 und höher|Windows Phone 8 und höher|
|Einfache Kennwörter zulassen|iOS 6 und höher|Nicht unterstützt|Windows Phone 8 und höher|
|Minimale Kennwortlänge|iOS 6 und höher| Android 4,0 und höher<br>Samsung KNOX Standard 4.0 und höher| Windows Phone 8 und höher<br>Windows 8.1|
|Erforderlicher Kennworttyp|iOS 6 und höher|Nicht verfügbar|Windows Phone 8 und höher <br>Windows RT<br> Windows RT 8.1 <br>Windows 8.1|
|Minimale Anzahl von Zeichensätzen|iOS 6 und höher|Nicht verfügbar|Windows Phone 8 und höher <br>Windows RT<br> Windows RT 8.1 <br>Windows 8.1|
|Kennwortqualität|Nicht verfügbar|Android 4,0 und höher <br>Samsung KNOX Standard 4.0 und höher|Nicht verfügbar|
|Minuten der Inaktivität, bevor ein Kennwort erforderlich ist|iOS 6 und höher|Android 4,0 und höher<br>Samsung KNOX Standard 4.0 und höher|Windows Phone 8 und höher<br>Windows RT und Windows RT 8.1<br>Windows 8.1|
|Kennwortablauf (Tage)|iOS 6 und höher|Android 4,0 und höher<br>Samsung KNOX Standard 4.0 und höher|Windows Phone 8 und höher<br>Windows RT und Windows RT 8.1<br>Windows 8.1|
|Kennwortverlauf speichern|iOS 6 und höher|Android 4,0 und höher<br>Samsung KNOX Standard 4.0 und höher|Windows Phone 8 und höher<br>Windows RT und Windows RT 8.1<br>Windows 8.1|
|Wiederverwendung vorheriger Kennwörter verhindern|iOS 6 und höher|Android 4,0 und höher<br>Samsung KNOX Standard 4.0 und höher|Windows Phone 8 und höher<br>Windows RT und Windows RT 8.1<br>Windows 8.1|
|Kennwort anfordern, wenn das Gerät aus dem Leerlauf zurückkehrt| Nicht verfügbar| Nicht verfügbar|Windows 10 Mobile|
|Verschlüsselung auf mobilem Gerät anfordern|Nicht verfügbar|Android 4,0 und höher<br>Samsung KNOX Standard 4.0 und höher|Windows Phone 8 und höher<br> Windows 8.1|
|Anforderung, dass Geräte als fehlerfrei gemeldet werden| Nicht verfügbar| Nicht verfügbar|Windows <br>Windows 10 Mobile|
|Gerät darf nicht per Jailbreak oder Rooting manipuliert worden sein|iOS 6 und höher|Android 4,0 und höher<br>Samsung KNOX Standard 4.0 und höher|Nicht verfügbar|
|E-Mail-Konto muss von Intune verwaltet werden|iOS 6 und höher|Nicht verfügbar| Nicht verfügbar|
|Wählen Sie das E-Mail-Profil aus, das von Intune verwaltet werden muss|iOS 6 und höher|Nicht verfügbar| Nicht verfügbar|
|Minimal erforderliches Betriebssystem|iOS 6 und höher|Android 4,0 und höher<br>Samsung KNOX Standard 4.0 und höher| Windows Phone 8 und höher<br>Windows 8.1|
|Maximal zulässige Betriebssystemversion|iOS 6 und höher|Android 4,0 und höher<br>Samsung KNOX Standard 4.0 und höher|Windows Phone 8 und höher<br>Windows 8.1|

Weitere Informationen über die Kompatibilitätseinstellungen, die auf den einzelnen Plattformen unterstützt werden, finden Sie in den folgenden Themen:
> [!div class="op_single_selector"]
- [Einstellungen für Kompatibilitätsrichtlinien für iOS-Geräte](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Einstellungen für Kompatibilitätsrichtlinien für Android-Geräte](android-compliance-policy-settings-in-microsoft-intune.md)
- [Einstellungen für Kompatibilitätsrichtlinien für Windows- und Windows Phone-Geräte ](windows-compliance-policy-settings-in-microsoft-intune.md)


## Nächste Schritte
[Bereitstellen und Überwachen einer Kompatibilitätsrichtlinie](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### Weitere Informationen:
[Einführung in Richtlinien zur Gerätekompatibilität](introduction-to-device-compliance-policies-in-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


