---
title: Identifizieren von Intune-Anwendungsszenarien | Microsoft-Dokumentation
description: "Dieser Artikel hilft Ihnen, Szenarien zu Intune-Anwendungsfällen und untergeordneten Anwendungsfällen für eine reine Cloudimplementierung von Microsoft Intune zu identifizieren."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b3c9af9-78da-44d2-8bd2-3f0f8885952d
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 3c5744e7c1290bf9016bc03dcb2db9a1bd9f43dd
ms.openlocfilehash: 031820d505e0e9cb007e47a5397934d0e505aed4
ms.lasthandoff: 04/10/2017


---

# <a name="identify-intune-use-case-scenarios"></a>Identifizieren von Intune-Anwendungsszenarien

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

In Anwendungsszenarien zur Verwaltung mobiler Geräte werden der Benutzertyp oder die Rolle sowie der Besitz des Geräts (z.B. „Unternehmen“ oder „Persönlich“) beschrieben. Mithilfe von Anwendungsszenarien können Sie Ihre Benutzer in verwaltbare Gruppen unterteilen. Das Identifizieren Ihrer Anwendungsszenarien ist ein wichtiger Bestandteil des Planungsprozesses für eine erfolgreiche Intune-Bereitstellung.

Betrachten wir einige Beispiele, die Ihre Organisation beim Festlegen der Intune-Anwendungsszenarien sowie der Organisationsgruppen und der den einzelnen Anwendungsfällen zugeordneten mobilen Geräteplattformen unterstützen können.

## <a name="use-case-scenarios"></a>Anwendungsfallszenarien

Als Erstes können Sie die langfristigen und kurzfristigen Intune-Bereitstellungsziele Ihrer Organisation zurate ziehen, um die Hauptanwendungsszenarien für Ihre Bereitstellung zu identifizieren. Im Rahmen Ihres Intune-Bereitstellungsplans müssen Sie die folgenden Fragen beantworten:

-   Möchten Sie unternehmenseigene Geräte unterstützen?

-   Möchten Sie persönliche Geräte (BYOD) unterstützen?

### <a name="sub-use-case-scenarios"></a>Szenarien zu untergeordneten Anwendungsfällen

Nach dem Ermitteln der Hauptanwendungsszenarien müssen Sie bestimmen, ob jedes Anwendungsszenario auch untergeordnete Anwendungsfälle enthält. Zum Beispiel hat eine Organisation möglicherweise Anforderungen für die Unterstützung eines unternehmensweiten Anwendungsszenarios erkannt, das zusätzliche untergeordnete Anwendungsfälle enthält:

-   Information-Worker

-   Führungskräfte

-   Kiosk

Hier sind einige Beispiele für Szenarien zu Anwendungsfällen und untergeordneten Anwendungsfällen. Anhand der unten stehenden Tabelle können Sie die Szenarien zu Anwendungsfällen und untergeordneten Anwendungsfällen Ihres Unternehmens eingeben:

| **Anwendungsfälle** | **Untergeordnete Anwendungsfälle** |
|:---:|:---:|
| Unternehmen | Information-Worker |              
| Unternehmen | Führungskräfte |           
| Unternehmen | Kiosk |
| BYOD | Information-Worker |           
| BYOD | Führungskräfte |

## <a name="identify-organizational-groups-associated-with-use-case-scenarios"></a>Identifizieren von den Anwendungsszenarien zugeordneten Organisationsgruppen

Jetzt müssen Sie die Gruppen der Organisation festlegen, die den einzelnen Szenarien zu Anwendungsfällen und untergeordneten Anwendungsfällen zugeordnet werden. Hier sind einige Beispiele für Organisationsgruppen aufgeführt, die den Szenarien zu Anwendungsfällen und untergeordneten Anwendungsfällen zugeordnet sind. Diese können als Vorlage verwendet werden, in die Sie die Informationen Ihrer Organisation eintragen können:

| **Anwendungsfälle** | **Untergeordnete Anwendungsfälle** | **Organisationsgruppen** |
|:---:|:---:|:---:|
| Unternehmen | Information-Worker | Personalabteilung, Finanzabteilung |               
| Unternehmen | Management | Personalabteilung, Finanzabteilung |            
| Unternehmen | Kiosk | Einzelhandel |
| BYOD | Information-Worker | Marketing, Vertrieb |            
| BYOD | Management | Marketing, Vertrieb |

## <a name="identify-mobile-device-platforms-for-use-case-scenarios"></a>Identifizieren mobiler Geräteplattformen für Anwendungsszenarien

Hier identifizieren Sie die mobilen Geräteplattformen, die den einzelnen Anwendungsszenarien zugeordnet sind. Beispielsweise unterstützt das Anwendungsszenario Ihres Unternehmens iOS- und Android Samsung Knox-Geräteplattformen, und Ihre BYOD-Richtlinie umfasst die Unterstützung für weitere mobile Geräteplattformen wie Android (nicht Samsung Knox) und Windows 10 Mobile. Hier sehen Sie ein Beispiel für mobile Geräteplattformen, die den einzelnen Anwendungsszenarien zugeordnet sind. In der folgenden Tabelle können Sie die Geräteplattformen Ihrer Organisation eintragen, die den einzelnen Anwendungsszenarien zugeordnet sind:

| **Anwendungsfälle** | **Untergeordnete Anwendungsfälle** | **Gruppen** | **Geräteplattformen** |   
|:---:|:---:|:---:|:---:|
| Unternehmen | Information-Worker | Personalabteilung, Finanzabteilung | iOS |                                                           
| Unternehmen | Führungskräfte | Personalabteilung, Finanzabteilung | iOS |                                                           
| Unternehmen | Kiosk | Einzelhandel | Android |
| BYOD | Information-Worker | Marketing, Vertrieb | iOS |                                                           
| BYOD | Führungskräfte | Marketing, Vertrieb | iOS |

## <a name="next-steps"></a>Nächste Schritte

Der nächste Abschnitt enthält Hinweise für das [Identifizieren der Intune-Anforderungen für die einzelnen Anwendungsszenarien](section-3-determine-use-case-requirements.md).

