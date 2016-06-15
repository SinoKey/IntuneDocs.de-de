---
# required metadata

title: Einstellungen für Kompatibilitätsrichtlinien für iOS-Geräte | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4a59d24f-ed58-49b1-b874-b2d4aea3ec76

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Einstellungen für Kompatibilitätsrichtlinien für iOS-Geräte in Microsoft Intune

Die in diesem Thema beschriebenen Richtlinieneinstellungen gelten für Geräte mit iOS 6 und höher.

Wenn Sie Informationen zu anderen Plattformen suchen, wählen Sie eine der folgenden Optionen:
> [!div class="op_single_selector"]
- [Einstellungen für Kompatibilitätsrichtlinien für Android-Geräte](android-compliance-policy-settings-in-microsoft-intune.md)
- [Einstellungen für Kompatibilitätsrichtlinien für Windows-Geräte](windows-compliance-policy-settings-in-microsoft-intune.md)

## Einstellungen für die Systemsicherheit
### Kennwort
- **Kennwort zum Entsperren mobiler Geräte erforderlich:** Legen Sie diese Einstellung auf **Ja** fest, damit der Benutzer ein Kennwort eingeben muss,
  bevor er auf sein Gerät zugreifen kann. iOS-Geräte mit Kennwort sind verschlüsselt.

- **Einfache Kennwörter zulassen:** Legen Sie diese Einstellung
   auf **Ja** fest, damit Benutzer einfache Kennwörter wie
   **1234** oder **1111** verwenden können.

-  **Minimale Kennwortlänge:**
  Geben Sie die Mindestanzahl von Ziffern oder Zeichen an, die
  das Kennwort des Benutzers enthalten muss.
- **Erforderlicher Kennworttyp:** Geben Sie an, ob Benutzer
ein **alphanumerisches** oder ein **numerisches** Kennwort erstellen müssen.

- **Minimale Anzahl von Zeichensätzen:** Wenn **Erforderlicher Kennworttyp** auf
**Alphanumerisch** festgelegt ist, gibt diese Einstellung die minimale Anzahl von
Zeichensätzen an, die das Kennwort enthalten muss. Es gibt vier Zeichensätze:
  -   Kleinbuchstaben
  -   Großbuchstaben
  -   Symbole
  -   Zahlen

  Wenn Sie eine höhere Zahl für diese Einstellung festlegen, müssen Benutzer komplexere Kennwörter erstellen.

  Bei iOS-Geräten bezieht sich diese Einstellung auf die Anzahl an Sonderzeichen (z. B. **!**, **#**, **&amp;**), die im Kennwort enthalten sein müssen.
- **Minuten Inaktivität vor erneuter Anforderung des Kennworts**: Gibt die Leerlaufzeit an, nach der ein Benutzer sein Kennwort erneut eingeben muss.

- **Kennwortablauf (Tage):** Wählen Sie die Anzahl der Tage aus, bevor das Kennwort des Benutzers abläuft
und er ein neues erstellen muss.

- **Kennwortverlauf speichern:** Verwenden Sie diese Einstellung in Verbindung mit **Wiederverwendung vorheriger Kennwörter verhindern**, um zu verhindern,
dass der Benutzer zuvor bereits verwendete Kennwörter erstellt.

- **Wiederverwendung vorheriger Kennwörter verhindern:** Wenn **Kennwortverlauf speichern** ausgewählt ist, geben Sie
die Anzahl der zuvor verwendeten Kennwörter an, die nicht erneut verwendet werden können.

- **Kennworteingabe verlangen, wenn das Gerät aus dem Leerlauf zurückkehrt:**
Diese Einstellung sollte zusammen mit der Einstellung **Minuten der Inaktivität, bevor ein Kennwort erforderlich ist** verwendet werden. Die Endbenutzer werden zur Eingabe eines Kennworts aufgefordert, um auf ein Gerät zugreifen zu können, das für die in
der Einstellung **Minuten Inaktivität vor erneuter Anforderung des Kennworts** angegebene Zeit inaktiv war.

### E-Mail-Profil
- **E-Mail-Konto muss von Intune verwaltet werden:** Wenn diese Option auf **Ja** festgelegt ist, muss das Gerät die nicht kompatible E-Mail-Adresse verwenden, die auf dem Gerät bereitgestellt ist. Das Gerät wird in den folgenden Situationen als nicht kompatibel betrachtet:
  - Das E-Mail-Profil muss auch für dieselbe Benutzergruppe wie für die Zielgruppe der Kompatibilitätsrichtlinie bereitgestellt werden. Andernfalls gelten die Geräte der Benutzer als nicht kompatibel.
  - Das Gerät wird als nicht kompatibel gemeldet, wenn der Benutzer bereits ein E-Mail-Konto auf dem Gerät eingerichtet hat, das dem auf dem Gerät bereitgestellten Intune-E-Mail-Profil entspricht. Intune kann das vom Benutzer bereitgestellte Profil nicht überschreiben und daher
  nicht verwalten. Zum Sicherstellen der Kompatibilität muss der Benutzer die
  vorhandenen E-Mail-Einstellungen entfernen. Anschließend kann Intune das verwaltete
  E-Mail-Profil installieren.


- **Wählen Sie das E-Mail-Profil aus, das von Intune verwaltet werden soll:**
     Wenn die Einstellung **E-Mail-Konto muss von Intune verwaltet werden** aktiviert ist,
     wählen Sie **Auswählen** aus, um das Intune-E-Mail-Profil anzugeben. Das E-Mail-Profil muss auf dem Gerät vorhanden sein.

     Ausführliche Informationen zu E-Mail-Profilen finden Sie unter [Konfigurieren des Zugriffs auf
     Unternehmens-E-Mail mithilfe von E-Mail-Profilen in Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md)..

## Einstellungen für die Geräteintegrität

- **Gerät darf nicht gehackt und kein Quellgerät sein:** Wenn Sie diese Einstellung aktivieren,
sind gehackt Geräte nicht kompatibel.

##  Geräteeigenschaften
- **Minimal erforderliches Betriebssystem:** Wenn ein Gerät nicht die Mindestanforderungen
an die Betriebssystemversion erfüllt, wird es als nicht kompatibel gemeldet.
Ein Link zur Vorgehensweise zum Upgrade wird angezeigt. Die Endbenutzer können ein Upgrade des Gerätes durchführen und sollten anschließend wieder auf die Unternehmensressourcen zugreifen können.

- **Maximal zulässige Betriebssystemversion:** Wenn auf einem Gerät
eine neuere Betriebssystemversion verwendet wird, als die Regel erlaubt, wird der Zugriff auf Unternehmensressourcen gesperrt, und der Benutzer wird gebeten, sich an den IT-Administrator zu wenden. Mit diesem Gerät kann solange nicht auf Unternehmensressourcen zugegriffen werden, bis die Regel geändert und die betreffende Betriebssystemversion zugelassen wird.


<!--HONumber=May16_HO1-->

