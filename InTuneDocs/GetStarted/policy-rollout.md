---
# required metadata

title: Richtlinienrollout | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 390d5adf-86d2-4e23-ba93-1e61e6b1028b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Richtlinienrollout
Dieses Thema enthält spezifische Empfehlungen für ein phasenweises Rollout von Richtlinien in Microsoft Intune. Dieser Ansatz gilt für die ersten Richtlinien, die Sie in einer neuen Intune-Bereitstellung anwenden, oder für Richtlinien, die Sie einer vorhandenen Bereitstellung hinzufügen.

Allgemeine Informationen über die Phasen des Rollouts finden Sie unter [Rolloutphasen für die Bereitstellung von Microsoft Intune](rollout-phases-for-microsoft-intune-deployment.md).

### Phasen des Richtlinienrollouts
Das Richtlinienrollout umfasst folgende Phasen:

-   Projektumfang

-   Proof of Concept

-   Pilotphase

-   Rollout im gesamten Unternehmen

-   Betrieb und Wartung

## Projektumfang
Definieren Sie den Umfang Ihrer Bereitstellung von Intune-Richtlinien:

-   Für eine neue Implementierung müssen Sie alle gewünschten Geräteverhalten und Sicherheitsanforderungen definieren, die Sie für Ihren Richtliniensatz erstellen möchten.

-   Entscheiden Sie, für welche Benutzer und Geräte diese Richtlinien gelten sollen.

-   Entwerfen Sie Ihre Benutzer- und Gerätegruppen so, dass Sie die neuen Richtlinien angemessen anwenden können.

-   Überprüfen Sie, ob Einschränkungen oder Anforderungen für die einzelnen Betriebssysteme gelten, die den Zweck der Richtlinie beeinträchtigen.

-   Berücksichtigen Sie Besonderheiten für den Richtlinienentwurf, wie z. B. den zu verwendenden Richtlinientyp und die Vorlage.

-   Unabhängig davon, ob Sie Ihren ersten Satz von Richtlinien starten oder einem vorhandenen Richtliniensatz neue Richtlinien hinzufügen, sollten Sie erwägen, wie verschiedene Richtlinien interagieren und welches Geräteverhalten wahrscheinlich daraus resultiert. Probleme mit Richtlinieninteraktionen und -konflikten können in der Pilotphase ermittelt werden. Wenn Sie Richtlinienkonflikte aber bereits in der frühen Planungsphase abfangen, vereinfachen Sie damit die Ausführung des Pilotprojekts.

## Proof of Concept
In der Proof of Concept-Phase testen Sie Ihre Richtlinienbereitstellung in einer Laborumgebung mit Geräten und Benutzern, die Sie ausschließlich für Testzwecke konfiguriert haben.

-   Lassen Sie Ihre Helpdeskmitarbeiter an dieser Phase teilnehmen, damit diese erfahren, welche Probleme während der Pilotphase und der Bereitstellung in der Produktion auftreten können. Informationen zur Problembehandlung finden Sie unter [Behandlung von Problemen mit Richtlinien in Microsoft Intune](/intune/troubleshoot/troubleshoot-policies-in-microsoft-intune)..

-   An dieser Stelle des Verfahrens sollten Sie Kommunikationspläne für Benutzer in der Pilotphase und in der Produktion entwickeln. Der Plan sollte mindestens beinhalten, welche Verhaltensweisen der Geräte sich wann ändern werden, welcher geschäftliche Anlass für die Änderung vorliegt und welche Aktionen durchgeführt werden sollten, wenn bei Benutzern oder IT-Mitarbeitern Probleme auftreten. Dabei sollten sowohl Informationen zur Selbsthilfe als auch Kontaktinformationen des Helpdesks aufgeführt werden.

## Pilotphase
Während der Pilotphase stellen Sie die Richtlinie für eine kleine Gruppe von Testbenutzern und -geräten bereit. Bei der Pilotphase für Richtlinien in Intune gibt es bestimmte Aspekte zu berücksichtigen:

-   Die Testgruppe sollte für die Gruppe repräsentativ sein, auf die die Richtlinie bei der Einführung in die Produktion angewendet werden soll.

-   Informieren Sie den Helpdesk in Bezug auf die Änderungen in der Richtlinie, und stellen Sie sicher, dass die Mitarbeiter auf die Hilfestellung für Benutzer in der Testgruppe vorbereitet sind.

-   Aktivieren Sie den Kommunikationsplan für Benutzer in der Pilotphase.

-   Das Pilotprojekt kann zuerst im isolierten Modus ausgeführt werden. In diesem Modus unterliegt das Gerät keinen anderen Richtlinien, die zu Konflikten und unerwartetem Verhalten führen können.

-   Im letzten Test müssen die neue Richtlinie und alle vorhandenen Richtlinien berücksichtigt werden, die auf dasselbe Gerät angewendet werden.

## Rollout im gesamten Unternehmen

-   Passen Sie Ihre geplante Richtlinie anhand der Ergebnisse des Pilotprojekts an, um Richtlinienkonflikte und unerwartetes Verhalten zu korrigieren.

-   Benachrichtigen Sie Ihren Helpdesk über den Zeitplan des Rollouts im gesamten Unternehmen. Halten Sie Mechanismen bereit, um auf Hilfeanforderungen zu reagieren und das Rollout nach Bedarf anzupassen.

-   Bereiten Sie sich auf die Problembehandlung für die Richtlinie vor, falls Probleme auftreten.

-   Aktivieren Sie den Kommunikationsplan für Benutzer in der Produktion.

-   Wenden Sie die Richtlinien inkrementell für weitere Gruppen an. Überwachen Sie dabei den Richtlinienzustand für betroffene Geräte, und verfolgen Sie Helpdeskanfragen, die sich auf die neue Richtlinie beziehen könnten.

## Betrieb und Wartung
**Betrieb:** Überwachen Sie Ihre Intune-Konsole auf Warnungen und Benutzer- oder Geräteprobleme, und prüfen Sie, ob Richtlinien Ihrem Entwurf entsprechend durchgeführt werden.

**Helpdesk:** Stellen Sie sicher, dass Ihr Helpdesk über Richtlinienänderungen informiert ist, die sich auf die Benutzeroberfläche auswirken, da diese zu Supportanfragen führen können.


### Weitere Informationen:
[Vorbereiten der Konfiguration von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)

[Behandlung von Problemen mit Richtlinien in Microsoft Intune](/intune/troubleshoot/troubleshoot-policies-in-microsoft-intune)


<!--HONumber=May16_HO1-->


