---
title: "Einstellungen für Kompatibilitätsrichtlinien für Android-Geräte | Microsoft Intune"
description: "In diesem Thema werden die Gerätekompatibilitätsrichtlinien für Android-Geräte beschrieben."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 777c0ac6ea309db81b127fb254e0c5f88444e475
ms.openlocfilehash: cf1fde5b5ed55552e573c724b6165203033683da


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

## Einstellungen für Geräteintegrität und Sicherheit

- **Gerät darf nicht gehackt und kein Quellgerät sein:** Wenn Sie diese Einstellung aktivieren, werden gehackte Geräte als nicht kompatibel eingestuft.
- **Installation von Apps aus unbekannten Quellen muss auf Geräten gesperrt sein (Android 4.0 oder höher)** Um Geräte zu blockieren, bei denen die Option **Sicherheit > Unbekannte Quellen** auf dem Gerät aktiviert ist, aktivieren Sie diese Einstellung, und legen Sie **Ja** fest.  
>[!IMPORTANT]
>Das Sideloading von Anwendungen erfordert, dass die Einstellung **Unbekannte Quellen** aktiviert ist.  Sie sollten diese Kompatibilitätsrichtlinie nur erzwingen, wenn Sie kein Sideloading von Android-Apps auf Geräten durchführen.

- **USB-Debuggen muss deaktiviert sein (Android 4.2 oder höher)**: Diese Einstellung gibt an, ob die Option für USB-Debuggen auf dem Gerät aktiviert ist.
- **Aktivierung von „Gerät auf Sicherheitsbedrohungen überprüfen“ auf Geräten erforderlich (Android 4.2-4.4)**: Diese Einstellung gibt an, dass die Option **Apps überprüfen** auf dem Gerät aktiviert ist.
- **Niedrigste zulässige Android-Sicherheitspatchebene (Android 6.0 und höher)**: Geben Sie mit dieser Einstellung die niedrigste Android-Patchebene an.  Geräte, die nicht mindestens diese Patchebene aufweisen, sind nicht kompatibel. Das Datum muss im folgenden Format angegeben werden: JJJJ-MM-TT.
- **Schutz vor Gerätebedrohungen muss aktiviert sein**: Verwenden Sie diese Einstellung, um die Risikobewertung mit der Lookout MTP-Lösung als Kompatibilitätsvoraussetzung zu fordern. Wählen Sie aus den folgenden Optionen die maximal zulässige Bedrohungsstufe aus:

  - **Keine (geschützt)**: Dies ist die sicherste Einstellung. Dies bedeutet, dass das Gerät keinerlei Bedrohungen unterliegen darf. Wenn auf dem Gerät Bedrohungen jeglicher Stufe erkannt werden, wird es als nicht kompatibel bewertet.
  - **Niedrig**: Das Gerät wird als kompatibel bewertet, wenn nur Bedrohungen niedriger Stufen vorliegen. Durch Bedrohungen höherer Stufen wird das Gerät in einen nicht kompatiblen Status versetzt.
  - **Mittel**: Das Gerät wird als kompatibel bewertet, wenn die auf dem Gerät gefundenen Bedrohungen niedriger oder mittlerer Stufe sind. Wenn auf dem Gerät Bedrohungen hoher Stufen erkannt werden, wird es als nicht kompatibel bewertet.
  - **Hoch**: Dies ist die unsicherste Einstellung. Mit dieser Einstellung werden grundsätzlich alle Bedrohungsstufen zugelassen. Sie ist daher wahrscheinlich nur für Berichtszwecke sinnvoll.

  Weitere Informationen finden Sie unter [Aktivieren der Regel zum Schutz vor Bedrohungen auf dem Gerät in der Kompatibilitätsrichtlinie](enable-device-threat-protection-rule-in-compliance-policy.md).

## Einstellungen für Geräteeigenschaften
- **Minimal erforderliches Betriebssystem:** Wenn ein Gerät die Anforderungen für die minimal erforderliche Betriebssystemversion nicht erfüllt, wird es als nicht kompatibel gemeldet.
  Ein Link zur Vorgehensweise zum Upgrade wird angezeigt. Die Endbenutzer können ein Upgrade des Geräts durchführen und anschließend auf die Unternehmensressourcen zugreifen.

- **Maximal zulässige Betriebssystemversion:** Wenn auf einem Gerät eine neuere Betriebssystemversion verwendet wird, als die Regel erlaubt, wird der Zugriff auf Unternehmensressourcen gesperrt, und der Benutzer wird gebeten, sich an den IT-Administrator zu wenden. Mit diesem Gerät kann solange nicht auf Unternehmensressourcen zugegriffen werden, bis die Regel geändert und die betreffende Betriebssystemversion zugelassen wird.



<!--HONumber=Sep16_HO3-->


