---

title: Android for Work-Richtlinieneinstellungen | Microsoft Intune
description: "Erstellen Sie Richtlinien, die Einstellungen und Features auf Android for Work-Geräten steuern, die Sie mit Intune verwalten."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 35a53076-74d6-486d-b201-e0da2e170008
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 748b9b74b65e8d17bb3956d0ce1859c160d8c10a


---

# <a name="android-for-work-policy-settings-in-microsoft-intune"></a>Einstellungen für Android for Work-Richtlinien in Microsoft Intune

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

Intune bietet eine Vielzahl von integrierten allgemeinen Einstellungen, die Sie auf Android for Work-Geräten konfigurieren können.

## <a name="general-configuration-policy"></a>Allgemeine Konfigurationsrichtlinie

Verwenden Sie die **Richtlinie für die allgemeine Konfiguration von Intune Android for Work** zum Konfigurieren von Sicherheits- und Arbeitsprofileinstellungen für Ihre Android for Work-Geräte.

Wenn die gesuchte Einstellung nicht in diesem Thema enthalten ist, können Sie sie ggf. mithilfe einer benutzerdefinierten Android-Richtlinie erstellen, die Ihnen das Steuern des Geräts mithilfe von OMA-URI-Einstellungen erlaubt. Weitere Informationen finden Sie weiter unten in diesem Thema unter [Benutzerdefinierte Richtlinieneinstellungen](#custom-policy-settings).

> [!TIP]
> Geräte werden beim Bereitstellen eines Arbeitsprofils automatisch verschlüsselt. Diese Einstellung kann nicht geändert werden.

### <a name="password-settings"></a>Kennworteinstellungen

|Name der Einstellung|Details|
|----------------|-|
|**Anfordern eines Kennworts zum Entsperren mobiler Geräte**|Gibt an, ob auf verwalteten Geräten ein Kennwort erforderlich ist. Wählen Sie aus:<br><br>- **Komplex**: erfordert mindestens einen Buchstaben, eine Zahl und ein Symbol<br>- **Alphanumerisch**: erfordert mindestens eine Zahl und ein alphabetisches Zeichen<br>- **Alphabetisch**: erfordert mindestens Buchstaben oder Symbole<br>- **Numerisch, komplex**: erfordert numerische Zeichen, die sich nicht wiederholen oder fortlaufend sind<br>- **Numerisch**<br><br>Wenn diese Einstellung nicht aktiviert ist, gelten keine Anforderungen an die Kennwortkomplexität.|
|**Minimale Kennwortlänge**|Gibt die Mindestanzahl von Zahlen oder Zeichen an, die das Kennwort enthalten muss.|
|**Inaktivität in Minuten, bevor das Gerät gesperrt wird**|Gibt die Anzahl der Minuten ohne Benutzeraktivität an, bevor das Gerät automatisch gesperrt wird.|
|**Smart Lock und andere Vertrauens-Agents zulassen**<br>(Android 6 und höher)|Ermöglicht Ihnen die Steuerung der Smart Lock-Funktion auf kompatiblen Android-Geräten. Diese Telefonfunktion wird manchmal als Vertrauens-Agent bezeichnet und ermöglicht Ihnen das Deaktivieren oder Umgehen des Kennworts für den Gerätesperrbildschirm, wenn sich das Gerät an einem vertrauenswürdigen Standort befindet, (wenn es z. B. mit einem bestimmten Bluetooth-Gerät verbunden ist oder sich in der Nähe eines NFC-Tags befindet). Mit dieser Einstellung können Sie verhindern, dass Benutzer Smart Lock konfigurieren.|
|**Anzahl wiederholter Anmeldefehler, bevor das Arbeitsprofil entfernt wird**|Gibt die Anzahl zulässiger Anmeldefehler an, bevor das Arbeitsprofil auf dem Gerät entfernt wird. Dabei wird keine vollständige Gerätezurücksetzung durchgeführt.|
|**Kennwortverlauf speichern**|Verhindert die Wiederverwendung zuvor verwendeter Kennwörter.|
|**Kennwortverlauf speichern** - **Wiederverwendung vorheriger Kennwörter verhindern**|Gibt die Anzahl der zuvor bereits verwendeten Kennwörter an, die gespeichert werden sollen.|
|**Kennwortablauf (Tage)**|Gibt die Anzahl der Tage an, bevor das Gerätekennwort geändert werden muss.|
|**Fingerabdruckentsperrung zulassen**<br>(Android 6 und höher)|Ermöglicht Ihnen die Verwendung eines Fingerabdrucks zum Entsperren von Geräten mit dieser Funktion.|


### <a name="work-profile-settings"></a>Arbeitsprofileinstellungen

|Name der Einstellung|Details|
|----------------|-|
|**Datenaustausch zwischen Arbeitsprofilen und persönlichen Profilen zulassen**|Lässt zu, dass Apps im Arbeitsprofil Daten mit Apps im persönlichen Profil des Benutzers austauschen. Wählen Sie aus:<br><br>- **Freigabe über Grenzen hinweg verhindern**<br>- **Apps im Arbeitsprofil können Freigabeanforderungen vom persönlichen Profil verarbeiten**<br>- **Keine Einschränkungen bei Freigabe**|
|**Benachrichtigungen des Arbeitsprofils ausblenden, wenn das Gerät gesperrt ist**<br>(Android 6 und höher)|Legt fest, ob Benachrichtigungen aus dem Arbeitsprofil angezeigt werden, wenn das Gerät gesperrt ist.|
|**Standardberechtigungsrichtlinie für Apps festlegen**<br>(Android 6 und höher)|Legt die Standardberechtigungsrichtlinie für alle Apps im Arbeitsprofil fest.|




## <a name="custom-policy-settings"></a>Benutzerdefinierte Richtlinieneinstellungen
Stellen Sie mithilfe der **benutzerdefinierten Android for Work-Konfigurationsrichtlinie** von Microsoft Intune die Einstellungen für OMA-URI bereit, um Features auf Android for Work-Geräten zu steuern. Dies sind die Standardeinstellungen, die viele Hersteller von mobilen Geräten verwenden, um Gerätefunktionen zu steuern.

Diese Funktion soll es Ihnen ermöglichen, Android-Einstellungen bereitzustellen, die nicht mit Intune-Richtlinien konfigurierbar sind.

> [!NOTE]
> Derzeit unterstützen benutzerdefinierte Android-Richtlinien unterstützt nur das Konfigurieren von WLAN-Einstellungen für Android-Geräte, die einen vorinstallierten Schlüssel enthalten.

### <a name="general-settings"></a>Allgemeine Einstellungen

|Name der Einstellung|Details|
    |----------------|--------------------|
    |**Name**|Geben Sie einen eindeutigen Namen für die benutzerdefinierte Android-Richtlinie ein, damit Sie sie leichter in der Intune-Konsole identifizieren können.|
    |**Beschreibung**|Geben Sie eine Beschreibung ein, die einen Überblick über die Richtlinie bietet, und andere relevante Informationen, die Ihnen die Suche danach erleichtern.|

### <a name="oma-uri-settings"></a>OMA-URI-Einstellungen

   |Name der Einstellung|Details|
    |--------|--------------------|
    |**Einstellungsname**|Geben Sie einen eindeutigen Namen für die OMA-URI-Einstellung ein, damit Sie sie in der Liste der Einstellungen leichter identifizieren können.|
    |**Einstellungsbeschreibung**|Geben Sie eine Beschreibung ein, die einen Überblick über die Einstellung bietet, und andere relevante Informationen, die Ihnen die Suche danach erleichtern.|
    |**Datentyp**|Wählen Sie den Datentyp aus, in dem Sie diese OMA-URI-Einstellung angeben. Wählen Sie aus **Zeichenfolge, Zeichenfolge (XML), Datum und Uhrzeit, ganze Zahl, Gleitkomma** oder **Boolesch** aus.|
    |**OMA-URI (Groß-/Kleinschreibung beachten)**|Geben Sie den OMA-URI an, für den Sie eine Einstellung festlegen möchten.|
    |**Wert**|Geben Sie den mit der zuvor festgelegten OMA-URI-Einstellung zu verknüpfenden Wert an.|

### <a name="examples"></a>Beispiele

- [Erstellen eines WLAN-Profils über einen vorinstallierten Schlüssel](pre-shared-key-wi-fi-profile.md)
- [Verwenden einer benutzerdefinierten Richtlinie zum Erstellen eines Profils für ein App-bezogenes VPN für Android-Geräte](per-app-vpn-for-android-pulse-secure.md)

### <a name="see-also"></a>Weitere Informationen:
[Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Nov16_HO1-->


