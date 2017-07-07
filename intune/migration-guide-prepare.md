---
title: "Vorbereitung von Intune für die Verwaltung mobiler Geräte (MDM)"
description: "Dieser Artikel soll den Lesern dabei helfen, Ihre geschäftlichen und technischen Anforderungen vor der Migration zu Intune zu evaluieren."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58591442-6606-4f39-a06b-f17a1f25af25
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 65e3bb4b6a4e6e8dcfa1dd16738ae47758f4fb9b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2017
---
# <a name="phase-1-prepare-intune-for-mobile-device-management-mdm"></a>Phase 1: Vorbereitung von Intune für die Verwaltung mobiler Geräte (MDM)

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Bevor wir uns mit den Details zum Einrichten von Intune befassen, werfen wir einen Blick auf die Anforderungen Ihres Unternehmens an die Verwaltung mobiler Geräte. Es könnte hilfreich sein, Berichte von aktiven Benutzern in Ihrem aktuellen MDM-Anbieter auszuführen, um die entscheidenden Benutzergruppen zu identifizieren. Anschließend können Sie sich um die Fragen im Abschnitt [Einschätzen von MDM-Anforderungen](migration-guide-prepare.md#assess-mdm-requirements) kümmern.

## <a name="assess-mdm-requirements"></a>Einschätzen von MDM-Anforderungen

### <a name="what-kinds-of-devices-do-you-need-to-manage"></a>Welche Arten von Geräten müssen Sie verwalten?

-   Welche [Plattformen](/intune-classic/get-started/supported-mobile-devices-and-computers) müssen Sie unterstützen?

-   Handelt es sich bei den Geräten, die unterstützt werden müssen, um unternehmenseigene oder BYOD-Geräte?

-   Welche Art von Verbindung wird verwendet? WLAN, Mobiltelefone, VPN?

### <a name="what-do-your-users-need-to-do-on-managed-devices"></a>Was müssen die Benutzer auf den verwalteten Geräten tun?

-   Müssen Sie den Endbenutzern Apps bereitstellen?

-   Verwenden Sie benutzerdefinierte, branchenspezifische Apps? Oder benötigen Sie nur öffentliche Store-Apps?

-   Müssen Sie E-Mail-Konten bereitstellen?

### <a name="what-kinds-of-users"></a>Um welche Arten von Benutzern handelt es sich?

-   Wie viele Benutzer werden ein einzelnes Gerät verwenden?

-   Welche Nutzungsbedingungen benötigen Sie?

    -   Stellen Sie sicher, dass Sie Ihre Rechtsabteilung frühzeitig heranziehen.

    -   Welche Lokalisierung ist erforderlich?

-   Sind die Benutzer mit Technologie und IT im Allgemeinen vertraut?

### <a name="what-is-your-device-security-policy"></a>Welche Sicherheitsrichtlinie für Geräte haben Sie?

-   Ist Verschlüsselung auf Geräteebene erforderlich?

-   Wie lang sind die Passwörter/PIN-Codes der Geräte?

-   Müssen Sie Gerätefunktionen deaktivieren oder bestimmtes Geräteverhalten einschränken?

    -   Sie können eine Reihe von plattformspezifischen Einstellungen mit Konfigurationsprofilen für Geräte steuern, zum Beispiel die Kamera deaktivieren oder nur Einzelanwendungsmodus zulassen.
<br></br>
-   Welche Arten von Authentifizierung müssen Sie unterstützen?

    -   Welche Zertifikate müssen bereitgestellt werden, wenn Sie zertifikatbasierte Authentifizierung benötigen?

        -   Intune kann Zertifikate mit Ressourcenzugriffsprofilen für registrierte Geräte bereitstellen.
<br></br>
    -   Welche Art von Public Key-Infrastruktur (PKI) müssen Sie unterstützen?
<br></br>
-   Müssen Sie virtuelles privates Netzwerk (VPN) auf Geräte- oder App-Ebene unterstützen?

    -   Intune kann VPN-Konfigurationen für VPN-Drittanbieter bereitstellen.
<br></br>
-   Können vorübergehende Ausnahmen für bestimmte Anforderungen gemacht werden, um Ausfallzeiten zu vermeiden? Oder müssen Geräte mit Zugriff immer alle Sicherheitsanforderungen erfüllen?

## <a name="additional-information"></a>Weitere Informationen

-   Ausführlichere Beispiele finden Sie in diesen [Fallstudien](https://customers.microsoft.com/story/mwh-global-now-part-of-stantec-secures-mobile-devices-with-intune) aus verschiedenen Branchen, die Ihnen zeigen, wie Organisationen ihre Anforderungen an die Verwaltung mobiler Geräte eingeschätzt haben.

## <a name="next-steps"></a>Nächste Schritte

[Grundlegende Einrichtung](migration-guide-setup.md)
