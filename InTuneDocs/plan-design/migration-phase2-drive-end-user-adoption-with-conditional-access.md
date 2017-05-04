---
title: "Fördern der Einführung mit bedingtem Zugriff für Endbenutzer | Microsoft-Dokumentation"
description: "Dieser Artikel soll Einblicke geben, wie der bedingte Zugriff verwendet werden kann, um die Registrierung in Intune zu fördern."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e10453155343bb7fd91a4fd3874d393ef78d0b1a
ms.openlocfilehash: 12584743534a76d0b2ce92e5de6cb5f916453938
ms.lasthandoff: 04/25/2017


---

# <a name="phase-2-drive-end-user-adoption-with-conditional-access"></a>Phase 2: Fördern der Einführung mit bedingtem Zugriff für Endbenutzer

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Funktionen für bedingten Zugriff wie das Blockieren von E-Mails für nicht registrierte Geräte mit Intune zu aktivieren, kann die Registrierung und Kompatibilität fördern, ist aber keine Voraussetzung für eine erfolgreiche Migration. Ihre Ziele bei der Einführung der Migration und die Sicherheitsanforderungen sollten den Erfolg bestimmen.

## <a name="migration-campaign-with-conditional-access"></a>Migrationskampagne mit bedingtem Zugriff

Hier ist ein typischer Ansatz, wie eine Migrationskampagne durch bedingten Zugriff erweitert werden kann:

1.  Legen Sie Regeln für bedingten Zugriff fest, der für alle Benutzer erzwungen wird, aber schließen Sie speziell die Benutzer aus, die vom alten MDM-Anbieter migrieren müssen. Sie können eine Azure AD-Benutzergruppe mit allen Benutzern erstellen, die vom bedingten Zugriff ausgeschlossen sind.

2.  Entfernen Sie die Benutzer aus dieser Gruppe, wenn sie migriert haben.

3.  Konfigurieren Sie nach dem Abschluss der Migration alle Richtlinien für bedingten Zugriff so, dass sie standardmäßig blockieren, wenn Intune den Zugriff nicht erlaubt.

### <a name="advantages"></a>Vorteile

-   Bietet Zugriffsteuerung für neue Benutzerkonten oder Benutzerkonten, die von der vorherigen Lösung nicht verwaltet wurden.

-   Bietet Benutzern der vorherigen Lösung einen Toleranzzeitraum für die Migration.

-   Produktivitätsverluste werden minimiert

### <a name="disadvantages"></a>Nachteile

-   Benutzer der vorherigen Lösung können möglicherweise über nicht verwaltete Geräte auf Ressourcen zugreifen, bis der bedingte Zugriff für diese Benutzer aktiviert ist.

> [!TIP]
> Dies ist ein Ansatz unter vielen. Sie können auch einen einfacheren Prozess auswählen, der jeglichen bedingten Zugriff aufschiebt, bis in jeder Phase die Registrierung angewiesen wurde, oder einen strengeren Prozess, der bedingten Zugriff von Anfang an erzwingt und für jeden Zugriff vollständige Kompatibilität erfordert.

-   Weitere Informationen zum [bedingten Zugriff](https://docs.microsoft.com/intune-azure/conditional-access/what-is-conditional-access).

## <a name="task-list-for-conditional-access"></a>Aufgabenliste für bedingten Zugriff

### <a name="task-1-get-ready-for-intune-conditional-access"></a>Aufgabe 1: Machen Sie sich bereit für bedingten Zugriff für Intune

-   Erfahren Sie, [wie Sie den bedingten Zugriff konfigurieren](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

### <a name="task-2-set-up-intune-conditional-access"></a>Aufgabe 2: Richten Sie den bedingten Zugriff für Intune ein.

Wählen Sie eine der folgenden Arten von Richtlinien für bedingten Zugriff aus, um mehr darüber zu erfahren:

-   [Exchange Online und Exchange Online Dedicated (neu)](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)

-   [Lokales Exchange und Exchange Online Dedicated (älter)](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)

-   [SharePoint Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)

-   [Skype for Business Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)

-   [Dynamics CRM Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)

-   [Beispielszenarios für den E-Mail-Zugriff](https://docs.microsoft.com/intune/deploy-use/restrict-email-access-example-scenarios)

## <a name="next-steps"></a>Nächste Schritte

[Phase 2: Typischer Migrationszyklus](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle)

