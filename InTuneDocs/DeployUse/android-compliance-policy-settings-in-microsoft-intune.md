---
title: "Einstellungen für Kompatibilitätsrichtlinien für Android-Geräte | Microsoft Intune"
description: "In diesem Thema werden die Gerätekompatibilitätsrichtlinien für Android-Geräte beschrieben."
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 359f76daa35a14e4107a9e03c6a1b1f4d1215777
ms.openlocfilehash: 38763f73ebb3e6d629c2e7ea43ad34514a8b3ad5


---


# Einstellungen für Kompatibilitätsrichtlinien für Android-Geräte in Microsoft Intune

Die in diesem Thema beschriebenen Richtlinieneinstellungen gelten für Geräte mit Android 4.0 und höher oder Samsung KNOX 4.0 und höher.

Wenn Sie Informationen zu anderen Plattformen suchen, wählen Sie eine der folgenden Optionen:
> [!div class="op_single_selector"]
- [Einstellungen für Kompatibilitätsrichtlinien für iOS-Geräte](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Einstellungen für Kompatibilitätsrichtlinien für Windows-Geräte](windows-compliance-policy-settings-in-microsoft-intune.md)

## Einstellungen für die Systemsicherheit
### Kennwort
- **Kennwort zum Entsperren mobiler Geräte erforderlich:** Legen Sie für diese Einstellung **Ja** fest, damit Benutzer ein Kennwort eingeben müssen, um auf ihre Geräte zugreifen zu können.

-  **Minimale Kennwortlänge:** Geben Sie die Mindestanzahl an Ziffern oder Zeichen an, die das Benutzerkennwort enthalten muss.

- **Kennwortstärke:** Aktivieren Sie diese Einstellung zum Konfigurieren des Domänenkennworts für Android-Geräte. Wählen Sie aus:
  -   **Biometrie auf niedriger Sicherheitsstufe**
  - **Erforderlich**
  -   **Mindestens numerisch**
  -   **Mindestens alphabetisch**
  -   **Mindestens alphanumerisch**
  -   **Alphanumerisch mit Symbolen**

- **Minuten der Inaktivität, bevor ein Kennwort erforderlich ist:** Gibt die Leerlaufzeit an, nach der ein Benutzer sein Kennwort erneut eingeben muss.

- **Kennwortablauf (Tage):** Wählen Sie die Anzahl von Tagen, bevor das Kennwort des Benutzers abläuft und er ein neues erstellen muss.

- **Kennwortverlauf speichern:** Verwenden Sie diese Einstellung in Verbindung mit **Wiederverwendung vorheriger Kennwörter verhindern**, um zu verhindern, dass der Benutzer zuvor bereits verwendete Kennwörter erstellt.

- **Wiederverwendung vorheriger Kennwörter verhindern:** Wenn **Kennwortverlauf speichern** aktiviert ist, geben Sie die Anzahl der zuvor verwendeten Kennwörter ein, die nicht erneut verwendet werden dürfen.

- **Kennworteingabe verlangen, wenn das Gerät aus dem Leerlauf zurückkehrt:** Diese Einstellung sollte zusammen mit der Einstellung **Minuten Inaktivität vor erneuter Anforderung des Kennworts** verwendet werden. Die Endbenutzer werden zur Eingabe eines Kennworts aufgefordert, um auf ein Gerät zugreifen zu können, das für die in der Einstellung **Minuten Inaktivität vor erneuter Anforderung des Kennworts** angegebene Zeit inaktiv war.

### Verschlüsselung
- **Verschlüsselung auf mobilen Geräten vorschreiben:** Legen Sie diese Einstellung auf **Ja** fest, damit Geräte verschlüsselt werden müssen, um eine Verbindung mit Ressourcen herzustellen. Wenn Sie die Einstellung **Kennwort zum Entsperren mobiler Geräte erforderlich** konfigurieren, werden Geräte verschlüsselt.

## Einstellungen für die Geräteintegrität

- **Gerät darf nicht gehackt und kein Quellgerät sein:** Wenn Sie diese Einstellung aktivieren, werden gehackte Geräte als nicht kompatibel eingestuft.

## Einstellungen für Geräteeigenschaften
- **Minimal erforderliches Betriebssystem:** Wenn ein Gerät die Anforderungen für die minimal erforderliche Betriebssystemversion nicht erfüllt, wird es als nicht kompatibel gemeldet.
  Ein Link zur Vorgehensweise zum Upgrade wird angezeigt. Die Endbenutzer können ein Upgrade des Geräts durchführen und anschließend auf die Unternehmensressourcen zugreifen.

- **Maximal zulässige Betriebssystemversion:** Wenn auf einem Gerät eine neuere Betriebssystemversion verwendet wird, als die Regel erlaubt, wird der Zugriff auf Unternehmensressourcen gesperrt, und der Benutzer wird gebeten, sich an den IT-Administrator zu wenden. Mit diesem Gerät kann solange nicht auf Unternehmensressourcen zugegriffen werden, bis die Regel geändert und die betreffende Betriebssystemversion zugelassen wird.



<!--HONumber=Jul16_HO3-->


