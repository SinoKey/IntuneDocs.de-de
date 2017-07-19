---
title: Bestimmen von Anforderungen von Anwendungsfallszenarien
description: "Dieser Artikel hilft Ihnen beim Ermitteln von Anforderungen von Intune-Szenarien für Anwendungsfälle und untergeordnete Anwendungsfälle für eine reine Cloudimplementierung von Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fd8cb5f7-19f0-4d80-8825-2bafa49624af
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 032427a9965f368d7be17339e3cbe5b426800347
ms.sourcegitcommit: ce363409d1206e4a3d669709863ccc9eb22b7d5f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2017
---
# Bestimmen von Anforderungen von Anwendungsfallszenarien
<a id="determine-use-case-scenario-requirements" class="xliff"></a>

In diesem Abschnitt ermitteln Sie die Anforderungen für jede Organisationsgruppe innerhalb der einzelnen Anwendungsfallszenarien. Dieser Prozess hilft Ihnen bei der Vorbereitung der übrigen Planungsbereiche der Intune-Bereitstellung wie Architektur und Entwurf, Onboarding und Rollout. Zudem unterstützt er Sie beim Bestimmen möglicher Lücken und Herausforderungen im Zusammenhang mit Ihrem Intune-Bereitstellungsprojekt.

Möglicherweise liegen für die einzelnen Szenarien zu Anwendungsfällen und untergeordneten Anwendungsfällen sowie für die zugeordneten Organisationsgruppen und mobilen Geräteplattformen unterschiedliche Anforderungskonstellationen vor. Angenommen, die Anforderungen an das Anwendungsfallszenario Ihres Unternehmens sehen vor, dass sich Geräte bei Intune mit restriktiveren Geräteeinstellungen registrieren, z.B. mit einer PIN mit 6 Zeichen oder deaktivierter Cloudsicherung. Das Anwendungsfallszenario BYOD (Bring Your Own Device, Nutzung privater Geräte für berufliche Zwecke) kann dagegen weniger restriktiv sein und eine PIN mit 4 Zeichen und Cloudsicherung vorsehen.

Möglicherweise gibt es auch Organisationsgruppen für das unternehmensweite Anwendungsfallszenario, die unterschiedliche Anforderungskonstellationen aufweisen (z.B. PIN-Einstellungen, WLAN- oder VPN-Profil, bereitgestellte Apps). Ihre Anforderungen können auch von den Möglichkeiten der Plattform für mobile Geräte bestimmt werden (z.B. Fingerabdruckleser, E-Mail-Profil).

Hier sehen Sie einige Beispiele für die Anwendungsfallanforderungen einer Organisation mit verschiedenen Anforderungskonstellationen für jedes Szenario aus Anwendungsfällen und untergeordneten Anwendungsfällen sowie für jede Organisationsgruppe und mobile Geräteplattform. In der folgenden Tabelle können Sie außerdem die Anwendungsfallanforderungen Ihrer Organisation eintragen:

| **Anwendungsfälle** | **Untergeordnete Anwendungsfälle** | **Gruppen** | **Geräteplattformen** | **Anforderungen** |
|:---:|:---:|:---:|:---:|:---:|
| Unternehmen | Information-Worker | Personalabteilung, Finanzabteilung | iOS | Sichere E-Mail, Geräteeinstellungen, Profile, Apps |                                                          
| Unternehmen | Führungskräfte | Personalabteilung, Finanzabteilung | iOS | Sichere E-Mail, Geräteeinstellungen, Profile, Apps |                                                         
| Unternehmen | Kiosk | Einzelhandel | Android | Geräteeinstellungen, Profile, Apps |
| BYOD | Information-Worker | Marketing, Vertrieb | iOS | Sichere E-Mail, Geräteeinstellungen, Profile, Apps |                                                         
| BYOD | Führungskräfte | Marketing, Vertrieb | iOS | Sichere E-Mail, Geräteeinstellungen, Profile, Apps |

Sie können [eine Vorlage der obigen Tabelle herunterladen](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0), um die Anforderungen an die Szenarien für Anwendungsfälle und untergeordnete Anwendungsfälle Ihrer Organisation einzutragen.


## Beispiele für Anforderungen
<a id="examples-of-requirements" class="xliff"></a>

Hier sind einige weitere Beispiele, die in der Spalte „Anforderungen“ verwendet werden können:

- **Sichere E-Mail**
    - Bedingter Zugriff für Exchange Online/lokales Exchange
    - Outlook-App-Schutzrichtlinien

- **Geräteeinstellungen**
    - PIN-Einstellung mit vier oder sechs Zeichen
    - Cloudsicherung einschränken

- **Profile**
    - WLAN
    - VPN
    - E-Mail (Windows 10 Mobile)

- **Apps**
    - Office 365 mit App-Schutzrichtlinien
    - Branchenspezifisch (LOB) mit App-Schutzrichtlinien

## Nächste Schritte
<a id="next-steps" class="xliff"></a>

Der nächste Abschnitt enthält Hinweise für das [Entwickeln eines Intune-Rolloutplans](planning-guide-rollout-plan.md).