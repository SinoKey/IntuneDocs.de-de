---
title: "Ermitteln von Anforderungen für Intune-Anwendungsszenarien | Microsoft-Dokumentation"
description: "Dieser Artikel hilft Ihnen beim Ermitteln von Anforderungen für Intune-Szenarien zu Anwendungsfällen und untergeordneten Anwendungsfällen für eine reine Cloudimplementierung von Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fd8cb5f7-19f0-4d80-8825-2bafa49624af
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: a56b683e57997171053f35414289d5b782c8fc2d
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---

# <a name="determine-intune-use-case-scenario-requirements"></a>Ermitteln von Anforderungen für Intune-Anwendungsszenarien

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

In diesem Abschnitt ermitteln Sie die Anforderungen für jede Organisationsgruppe innerhalb der einzelnen Anwendungsszenarien. Dieser Prozess hilft Ihnen bei der Vorbereitung der übrigen Planungsbereiche der Intune-Bereitstellung wie Architektur und Entwurf, Onboarding und Rollout. Zudem unterstützt er Sie beim Identifizieren möglicher Lücken und Herausforderungen im Zusammenhang mit Ihrem Intune-Bereitstellungsprojekt.

Möglicherweise liegen für die einzelnen Szenarien zu Anwendungsfällen und untergeordneten Anwendungsfällen sowie für die zugeordneten Organisationsgruppen und mobilen Geräteplattformen unterschiedliche Sätze von Anforderungen vor. Beispielsweise verlangen die Anforderungen des Unternehmensanwendungsszenarios, dass Gerate sich bei Intune mit einem restriktiveren Satz von Geräteeinstellungen registrieren (z.B. PIN aus 6 Zeichen und deaktivierte Cloudsicherung) als beim BYOD-Anwendungsszenario (Bring Your Own Device), in dem weniger restriktive Einstellungen erforderlich sind (z.B. PIN aus 4 Zeichen, aktivierte Cloudsicherung).

Möglicherweise verwenden Sie auch Organisationsgruppen für das Unternehmensanwendungsszenario, die unterschiedliche Anforderungssätze aufweisen (z.B. PIN-Einstellungen, WLAN- oder VPN-Profil, bereitgestellte Apps). Darüber hinaus werden Ihre Anforderungen durch die Funktionen der mobilen Geräteplattform definiert (z.B. Fingerabdruckleser, E-Mail-Profil).

Hier sehen Sie einige Beispiele für die Anwendungsfallanforderungen einer Organisation mit verschiedenen Anforderungssätzen für jedes Szenario aus Anwendungsfällen und untergeordneten Anwendungsfällen sowie für jede Organisationsgruppe und jede mobile Geräteplattform. In der unten aufgeführten Tabelle können Sie außerdem die Anwendungsfallanforderungen Ihrer Organisation angeben:

| **Anwendungsfälle** | **Untergeordnete Anwendungsfälle** | **Gruppen** | **Betriebssystemplattformen der Geräte** | **Anforderungen** |
|:---:|:---:|:---:|:---:|:---:|
| Unternehmen | Information-Worker | Personalabteilung, Finanzabteilung | iOS | Sichere E-Mail, Geräteeinstellungen, Profile, Apps |                                                          
| Unternehmen | Führungskräfte | Personalabteilung, Finanzabteilung | iOS | Sichere E-Mail, Geräteeinstellungen, Profile, Apps |                                                         
| Unternehmen | Kiosk | Einzelhandel | Android | Geräteeinstellungen, Profile, Apps |
| BYOD | Information-Worker | Marketing, Vertrieb | iOS | Sichere E-Mail, Geräteeinstellungen, Profile, Apps |                                                         
| BYOD | Führungskräfte | Marketing, Vertrieb | iOS | Sichere E-Mail, Geräteeinstellungen, Profile, Apps |

## <a name="examples-of-requirements"></a>Beispiele für Anforderungen

Hier sind einige weitere Beispiele, die in der Spalte „Anforderungen“ in der oben gezeigten Tabelle verwendet werden können:

- **Sichere E-Mail**
    - Bedingter Zugriff für Exchange Online/lokal
    - Outlook-App-Schutzrichtlinien
<br></br>
- **Geräteeinstellungen**
    - PIN-Einstellung mit vier oder sechs Zeichen
    - Cloudsicherung einschränken
<br></br>
- **Profile**
    - WLAN
    - VPN
    - E-Mail (Windows 10 Mobile)
<br></br>
- **Apps**
    - Office 365 mit App-Schutzrichtlinien
    - Branchenspezifisch (LOB) mit App-Schutzrichtlinien

## <a name="next-section"></a>Nächster Abschnitt

Der nächste Abschnitt enthält Hinweise für das [Entwickeln eines Intune-Rolloutplans](section-4-develop-a-rollout-plan.md).

