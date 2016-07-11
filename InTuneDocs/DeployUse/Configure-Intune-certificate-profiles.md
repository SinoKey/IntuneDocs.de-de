---
title: Konfigurieren von Zertifikatprofilen | Microsoft Intune
description: 
keywords: 
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175
ms.reviewer: kmyrup
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ee6b3607688cb02be7316b83e10424dfbea9746b
ms.openlocfilehash: 8343abe8861468bbba27272aa1f3569390cb826b


---

# Konfigurieren von Intune-Zertifikatprofilen
Nachdem Sie Ihre Infrastruktur und Zertifikate konfiguriert haben (gemäß der Beschreibung in [Konfigurieren der Zertifikatinfrastruktur für SCEP](configure-certificate-infrastructure-for-scep.md) oder [Konfigurieren der Zertifikatinfrastruktur für PFX](configure-certificate-infrastructure-for-pfx.md)), können Sie Zertifikatprofile konfigurieren:

**Aufgabe 1**: Exportieren des vertrauenswürdigen Stammzertifizierungsstellenzertifikats **Aufgabe 2**: Erstellen von Zertifikatprofilen der vertrauenswürdigen Zertifizierungsstelle**Aufgabe 3**: Eine der Optionen:

Erstellen von SCEP-Zertifikatprofilen

Erstellen von PFX-Zertifikatprofilen

### Aufgabe 1: Exportieren des vertrauenswürdigen Stammzertifizierungsstellenzertifikats
Exportieren Sie das vertrauenswürdige Stammzertifizierungsstellenzertifikat als eine **CER** -Datei von der ausstellenden Zertifizierungsstelle oder von einem Gerät, das die ausstellenden Zertifizierungsstelle als vertrauenswürdig erachtet. Sie exportieren den privaten Schlüssel nicht.

Sie importieren dieses Zertifikat, wenn Sie ein Zertifikatprofil der vertrauenswürdigen Zertifizierungsstelle konfigurieren.

### Aufgabe 2: Erstellen von Zertifikatprofilen der vertrauenswürdigen Zertifizierungsstelle
Sie müssen ein **Profil mit einem vertrauenswürdigen Zertifikat** erstellen, bevor Sie ein SCEP- oder PFX-Zertifikatprofil erstellen können. Sie benötigen ein Profil mit einem vertrauenswürdigen Zertifikat und ein SCEP- oder PFS-Profil für jede mobile Geräteplattform.

##### So erstellen Sie ein vertrauenswürdiges Zertifikatprofil

1.  Öffnen Sie die [Intune-Verwaltungskonsole](https://manage.microsoft.com), und klicken Sie auf **Richtlinie** &gt; **Richtlinie hinzufügen**.

2.  Konfigurieren Sie einen der folgenden Richtlinientypen:

    **Android &gt; Profil des vertrauenswürdigen Zertifikats (Android 4 und höher)**

    **iOS &gt; Profil des vertrauenswürdigen Zertifikats (iOS 7.1 und höher)**

    **Mac OS X &gt; Vertrauenswürdiges Zertifikatprofil (Mac OS X 10.9 und höher)**

    **Windows &gt; Vertrauenswürdiges Zertifikatprofil (Windows 8.1 und höher)**

    **Windows &gt; Vertrauenswürdiges Zertifikatprofil (Windows Phone 8.1 und höher)**

    Weitere Informationen finden Sie unter [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Stellen Sie die angeforderten Informationen bereit, um die Profileinstellungen vertrauenswürdiger Zertifikate für Android, iOS, Mac OS X, Windows 8.1 oder Windows Phone 8.1 zu konfigurieren: Importieren Sie in der Einstellung **Zertifikatdatei** das Zertifikat der vertrauenswürdigen Stammzertifizierungsstelle (**.cer**), das Sie von der ausstellenden Zertifizierungsstelle exportiert haben. Die Einstellung **Zielspeicher** gilt nur für Geräte mit Windows 8.1 und höher und auch nur, wenn das Gerät über mehr als einen Zertifikatspeicher verfügt.


4.  Klicken Sie danach auf **Richtlinie speichern**.

Die neue Richtlinie wird im Arbeitsbereich **Richtlinie** angezeigt und kann nun bereitgestellt werden.

### Aufgabe 3: Erstellen von SCEP- oder PFX-Zertifikatprofilen
Nachdem Sie ein Zertifikatprofil der vertrauenswürdigen Zertifizierungsstelle erstellt haben, erstellen Sie SCEP- oder PFX-Zertifikatprofile für jede Plattform, die Sie verwenden möchten. Wenn Sie ein SCEP-Zertifikatprofil erstellen, müssen Sie ein vertrauenswürdiges Zertifikatprofil für dieselbe Plattform angeben. Auf diese Weise werden die beiden Zertifikatprofile verknüpft. Sie müssen jedoch weiterhin jedes Profil separat bereitstellen.

##### Erstellen eines SCEP-Zertifikatprofils

1.  Klicken Sie in der [Intune-Verwaltungskonsole](https://manage.microsoft.com) auf **Richtlinie** &gt; **Richtlinie hinzufügen**.

2.  Konfigurieren Sie einen der folgenden Richtlinientypen:

    **Android &gt; SCEP-Zertifikatprofil (Android 4 und höher)**

    **iOS &gt; SCEP-Zertifikatprofil (iOS 7.1 und höher)**

    **Mac OS X &gt; SCEP-Zertifikatprofil (Mac OS X 10.9 und höher)**

    **Windows &gt; SCEP-Zertifikatprofil (Windows 8.1 und höher)**

    **Windows &gt; SCEP-Zertifikatprofil (Windows Phone 8.1 und höher)**

    Weitere Informationen finden Sie unter [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Befolgen Sie die Anweisungen auf der Profilkonfigurationsseite, um die SCEP-Zertifikatprofileinstellungen zu konfigurieren.

4.  Klicken Sie danach auf **Richtlinie speichern**.

Die neue Richtlinie wird im Arbeitsbereich **Richtlinie** angezeigt und kann nun bereitgestellt werden.

##### So erstellen Sie ein PFX-Zertifikatprofil

1.  Klicken Sie in der [Intune-Verwaltungskonsole](https://manage.microsoft.com) auf **Richtlinie** &gt; **Richtlinie hinzufügen**.

2.  Konfigurieren Sie einen der folgenden Richtlinientypen:



-   **Android &gt; PFX-Zertifikatprofil (Android 4 und höher)**

    -   **Windows &gt; PKCS #12 (.PFX) Zertifikatprofil (Windows 10 und höher)**

    -   **Windows &gt; PKCS #12 (.PFX) Zertifikatprofil (Windows Phone 10 und höher)**

    -    **iOS > PKCS #12 (.PFX) Zertifikatprofil (iOS 7.1 und höher)**    

    Weitere Informationen finden Sie unter [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Stellen Sie die Informationen zur Verfügung, die auf dem Richtlinienformular angefordert werden.

4.  Klicken Sie danach auf **Richtlinie speichern**.

Die neue Richtlinie wird im Arbeitsbereich **Richtlinie** angezeigt und kann nun bereitgestellt werden.

## Bereitstellen von Zertifikatprofilen
Wenn Sie Zertifikatprofile bereitstellen, wird die Zertifikatdatei aus dem Zertifikatprofil der vertrauenswürdigen Zertifizierungsstelle auf Geräten installiert. Das SCEP- oder PFX-Zertifikatprofil wird vom Gerät verwendet, um eine Zertifikatsanforderung zu erstellen.

Zertifikatprofile werden nur auf den Geräten installiert, die der beim Erstellen des Profils verwendeten Plattform entsprechen.

-   Sie können Zertifikatprofile für Benutzer- oder Gerätesammlungen bereitstellen.

    > [!TIP]
    > Damit Zertifikate möglichst schnell auf Geräten nach deren Registrierung veröffentlicht werden können, stellen Sie dieses Zertifikatprofil für eine Benutzergruppe (nicht für eine Gerätegruppe) bereit. Wenn Sie es für eine Gerätegruppe bereitstellen, muss eine vollständige Geräteregistrierung stattfinden, bevor das Gerät die Richtlinie empfängt.

-   Obwohl jedes Profil einzeln bereitgestellt wird, muss sowohl das vertrauenswürdige Stamm- als auch das SCEP/PFX-Profil bereitgestellt werden, da bei der SCEP/PFX-Zertifikatrichtlinie sonst ein Fehler auftritt.

Sie stellen Zertifikatprofile auf die gleiche Weise bereit wie andere Richtlinien für Intune.

1.  Wählen Sie im Arbeitsbereich **Richtlinie** die Richtlinie aus, die Sie bereitstellen möchten, und klicken Sie dann auf **Bereitstellung verwalten**.

2.  Führen Sie im Dialogfeld **Bereitstellung verwalten** folgende Schritte aus:

    -   **Zum Bereitstellen der Richtlinie**: Wählen Sie mindestens eine Gruppe aus, für die Sie die Richtlinie bereitstellen möchten, und klicken Sie auf **Hinzufügen** &gt; **OK**.

    -   **Wenn Sie das Dialogfeld schließen möchten, ohne die Richtlinie bereitzustellen:** Klicken Sie auf **Abbrechen**.

Wenn Sie eine bereitgestellte Richtlinie auswählen, können Sie weitere Informationen zur Bereitstellung im unteren Teil der Richtlinienliste anzeigen.
###  Nächste Schritte

Sie können jetzt Zertifikate verwenden, um E-Mail-, WLAN- und VPN-Profile zu schützen:

-  [Konfigurieren des Zugriffs auf Unternehmens-E-Mail mithilfe von E-Mail-Profilen](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [WLAN-Verbindungen in Microsoft Intune](wi-fi-connections-in-microsoft-intune.md)
-  [VPN-Verbindungen in Microsoft Intune](vpn-connections-in-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


