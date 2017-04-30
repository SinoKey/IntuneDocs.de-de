---
title: "Einstellungen für Geräteeinschränkungen für Android for Work in Intune"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie etwas über die Intune-Einstellungen zur Steuerung von Geräteeinstellungen und -funktionen auf Android for Work-Geräten."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1830720b-16cb-4f2f-a71a-62967f882563
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 03fec9d22e705ccb27f4eb1f8f82c7ace95e841e
ms.openlocfilehash: c5cff131e7bcedadbad42fe6ab8bf00017f933ff
ms.lasthandoff: 04/26/2017


---

# <a name="android-for-work-device-restriction-settings-in-microsoft-intune"></a>Einstellungen für Geräteeinschränkungen für Android for Work-Geräte in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="work-profile-settings"></a>Arbeitsprofileinstellungen
-     **Datenfreigabe zwischen Arbeitsprofilen und persönlichen Profilen**: Verwenden Sie diese Einstellung, um zu steuern, ob Apps im Arbeitsprofil Daten für Apps im persönlichen Profil freigeben können. Wählen Sie aus:
    - **Standardeinschränkungen für Freigabe**: Dies ist das standardmäßige Freigabeverhalten des Geräts, das abhängig von der ausgeführten Android-Version variiert. Standardmäßig ist die Freigabe vom persönlichen Profil aus für das Arbeitsprofil zulässig. Außerdem ist standardmäßig die Freigabe vom Arbeitsprofil aus für das persönliche Profil blockiert. Dies verhindert die Offenlegung von Daten des Arbeitsprofils im persönlichen Profil. Google bietet auf Geräten, die frühere Versionen als 6.0 ausführen, keine Möglichkeit, zu blockieren, dass Daten aus dem persönlichen Profil in das Arbeitsprofil gelangen.  
    - **Apps im Arbeitsprofil können Freigabeanforderungen vom persönlichen Profil verarbeiten**: Aktivieren Sie mit dieser Option das integrierte Android-Feature, dass die Freigabe vom persönlichen Profil aus im Arbeitsprofil ermöglicht. Wenn diese Option aktiviert ist, ermöglicht eine Freigabeanfrage, die von einer App im persönlichen Profil initiiert wird, die gemeinsame Nutzung von Daten mit Apps im Arbeitsprofil. Dies ist das Standardverhalten für Android-Geräte, die frühere Versionen als 6.0 ausführen.
    - **Apps in personal profile can handle sharing request from work profile** (Apps im persönlichen Profil können Freigabeanfragen aus dem Arbeitsprofil bearbeiten): Ermöglicht in beiden Richtungen die Freigabe über die Arbeitsprofilgrenzen hinweg. Wenn Sie diese Einstellung auswählen, können Apps im Arbeitsprofil Daten gemeinsam mit nicht verwalteten Apps im persönlichen Profil nutzen.  Verwenden Sie diese Einstellung mit Vorsicht, da sie die Übertragung verwalteter Daten im Arbeitsprofil an die nicht verwaltete Seite des Geräts ermöglicht.


-     **Arbeitsprofilbenachrichtigungen bei Gerätesperre**: Steuert, ob Apps im Arbeitsprofil Benachrichtigungen auf dem Bildschirm anzeigen können, wenn das Gerät gesperrt ist.
-     **Standardmäßige App-Berechtigungen**: Legt die Standardberechtigungsrichtlinie für alle Apps im Arbeitsprofil fest. Ab Android 6 wird der Endbenutzer während der Laufzeit zur Eingabe bestimmter Berechtigungen aufgefordert, die für Apps erforderlich sind. Diese Richtlinieneinstellung ermöglicht Ihnen, zu entscheiden, wie oder ob Benutzer aufgefordert werden, Berechtigungen für Apps im Arbeitsprofil zu gewähren.
Beispielsweise können Sie eine App mithilfe von Push in das Arbeitsprofil übertragen, die Speicherortzugriff benötigt. Normalerweise würde diese App den Benutzer in einem Popupdialogfeld fragen, ob er der App Speicherortzugriff gewähren möchte, und der Benutzer könnte dies genehmigen oder ablehnen. Mit dieser Richtlinie können Sie entscheiden, ob alle Berechtigungen automatisch ohne Aufforderung gewährt werden sollen, ohne Aufforderung automatisch verweigert werden sollen, oder ob der Endbenutzer entscheiden kann. Wählen Sie aus:
    -     **Gerätestandard**
    -     **Eingabeaufforderung**
    -     **Automatisch gewähren**
    -     **Automatisch verweigern**

## <a name="password"></a>Kennwort

- **Minimale Kennwortlänge:** Geben Sie die Mindestanzahl (von **4**-**14**) an Ziffern oder Zeichen an, die das Benutzerkennwort enthalten muss.
- **Maximaler Zeitraum der Inaktivität (in Minuten) bis zur Bildschirmsperrung**: Wählen Sie den Zeitraum, nach dessen Verstreichen ein inaktives Gerät automatisch gesperrt wird.
- **Anzahl von Anmeldefehlern, bevor das Gerät zurückgesetzt wird**: Geben Sie an, wie häufig ein falsches Kennwort eingegeben werden kann, bevor alle Daten auf dem Gerät gelöscht werden.
- **Kennwortablauf (Tage)**: Geben Sie die Anzahl der Tage an (von **1**-**255**), nach deren Verstreichen das Kennwort eines Endbenutzers geändert werden muss.
- **Erforderlicher Kennworttyp**: Wählen Sie den Typ des Kennworts, das auf dem Gerät festgelegt werden muss. Wählen Sie aus:
    - **Gerätestandard**
    - **Biometrie auf niedriger Sicherheitsstufe**
    - **Erforderlich**
    - **Mindestens numerisch**
    - **Numerisch komplex**: (sich wiederholende oder fortlaufende Ziffern wie „1111“ oder „1234“ sind nicht zulässig)
    - **Mindestens alphabetisch**
    - **Mindestens alphanumerisch**
    - **Mindestens alphanumerisch mit Symbolen**
- **Wiederverwendung vorheriger Kennwörter verhindern**: Geben Sie die Anzahl neuer Kennwörter ein (von **1**-**24**), die verwendet werden müssen, bevor ein altes wiederverwendet werden kann.
- **Entsperrung durch Fingerabdruck**: Verhindert, dass ein Endbenutzer das Gerät mithilfe des Fingerabdruckscanners entsperren kann.
- **Smart Lock und andere Vertrauens-Agents**: Ermöglicht Ihnen die Steuerung des Smart Lock-Features auf kompatiblen Geräten. Diese Telefonfunktion wird manchmal als Vertrauens-Agent bezeichnet und ermöglicht Ihnen das Deaktivieren oder Umgehen des Kennworts für den Gerätesperrbildschirm, wenn sich das Gerät an einem vertrauenswürdigen Standort befindet, (wenn es z.B. mit einem bestimmten Bluetooth-Gerät verbunden ist oder sich in der Nähe eines NFC-Tags befindet). Sie können mit dieser Einstellung verhindern, dass Benutzer Smart Lock konfigurieren.

## <a name="custom-policy-settings"></a>Benutzerdefinierte Richtlinieneinstellungen
Stellen Sie mithilfe der **benutzerdefinierten Android for Work-Konfigurationsrichtlinie** von Microsoft Intune die Einstellungen für OMA-URI bereit, um Features auf Android for Work-Geräten zu steuern. Dies sind die Standardeinstellungen, die viele Hersteller von mobilen Geräten verwenden, um Gerätefunktionen zu steuern.

Diese Funktion soll es Ihnen ermöglichen, Android-Einstellungen bereitzustellen, die nicht mit Intune-Richtlinien konfigurierbar sind.
Intune unterstützt zurzeit eine begrenzte Anzahl von benutzerdefinierten Android-Richtlinien. Mit den Beispielen in diesem Thema finden Sie heraus, welche Richtlinien Sie konfigurieren können.

### <a name="general-settings"></a>Allgemeine Einstellungen

|Name der Einstellung|Details|
    |----------------|--------------------|
    |**Name** |Geben Sie einen eindeutigen Namen für die benutzerdefinierte Android-Richtlinie ein, damit Sie sie leichter in der Intune-Konsole identifizieren können.|
    |**Beschreibung** |Geben Sie eine Beschreibung ein, die einen Überblick über die Richtlinie bietet, und andere relevante Informationen, die Ihnen die Suche danach erleichtern.|

### <a name="oma-uri-settings"></a>OMA-URI-Einstellungen

  |Name der Einstellung|Details|
  |--------|--------------------|
  |**Name** |Geben Sie einen eindeutigen Namen für die OMA-URI-Einstellung ein, damit Sie sie in der Liste der Einstellungen leichter identifizieren können.|
  |**Beschreibung** |Geben Sie eine Beschreibung ein, die einen Überblick über die Einstellung bietet, und andere relevante Informationen, die Ihnen die Suche danach erleichtern.|
    |**OMA-URI (Groß-/Kleinschreibung beachten)** |Geben Sie den OMA-URI an, für den Sie eine Einstellung festlegen möchten.|
  |**Datentyp** |Wählen Sie den Datentyp aus, in dem Sie diese OMA-URI-Einstellung angeben. Wählen Sie aus **Zeichenfolge, Zeichenfolge (XML), Datum und Uhrzeit, ganze Zahl, Gleitkomma** oder **Boolesch** aus.|
  |**Wert** |Geben Sie den mit der zuvor festgelegten OMA-URI-Einstellung zu verknüpfenden Wert an.|

