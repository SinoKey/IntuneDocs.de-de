---
title: "Konfigurieren der App-Schutzrichtlinien während einer Migration von Intune | Microsoft-Dokumentation"
description: "Dieser Artikel gibt einen Überblick über die für die Einrichtung der App-Schutzrichtlinien notwendigen Schritte während einer Migration von Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 35543604ed68393e859517e32f5186247be001df
ms.lasthandoff: 03/27/2017


---

# <a name="phase-1-configure-app-protection-policies-optional"></a>Phase 1: Konfigurieren von App-Schutzrichtlinien (optional)

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

App-Schutzrichtlinien geben Ihnen u.a. die Möglichkeit, Apps zu verschlüsseln, eine PIN für den Zugriff auf die App zu definieren und das Ausführen von Apps auf Geräten mit entfernten Nutzungsbeschränkungen oder gerooteten Geräten zu blockieren. Wenn das Gerät des Benutzer verloren geht oder geklaut wurde, können Sie die Unternehmensdaten remote selektiv zurücksetzen, ohne dass die persönlichen Daten davon betroffen wären; dies ist mit mobilen App-Schutzrichtlinien möglich.

App-Schutzrichtlinien wenden Sicherheitsmaßnahmen auf der Geräteebene an und erfordern keine Geräteregistrierung. Sie können sowohl für Geräte, die in Intune registriert sind, als auch für nicht registrierte Geräte verwendet werden. Des Weiteren können Sie auch für Geräte verwendet werden, die für Drittanbieter-MDM registriert sind.

## <a name="app-protection-policies-with-lob-apps"></a>App-Schutzrichtlinien für branchenspezifische Apps

Sie können die App-Schutzrichtlinien auch auf branchenspezifische Apps ausweiten, indem Sie das [Microsoft Intune App SDK](https://docs.microsoft.com/intune/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management) oder das Microsoft Intune App Wrapping Tool sowohl für [iOS](https://www.microsoft.com/en-us/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True)- als auch für [Android](https://www.microsoft.com/en-us/download/details.aspx?id=47267)-Plattformen verwenden.

## <a name="how-do-app-protection-policies-help-during-migration"></a>Wie helfen App-Schutzrichtlinien bei der Migration?

Bei der Migration müssen Geräte vom alten MDM-Anbieter entfernt und in Intune registriert werden. Dies sollten Sie berücksichtigen und Ihre Endbenutzer dazu anhalten, den alten MDM-Anbieter zu verlassen und sich umgehend in Intune zu registrieren. Bei der Migration kann es allerdings Benutzer geben, die den Abschluss des Registrierungsprozesses verzögern, weil Ihre Geräte von keinem der beiden MDM-Anbieter verwaltet werden.

In diesem Zeitraum kann Ihre Organisation anfälliger sein für den Geräteklau und den Verlust von Unternehmensdaten, wenn der Zugriff auf Unternehmensressourcen immer noch möglich ist. Außerdem kann die Benutzerproduktivität abnehmen, wenn der Zugriff auf Unternehmensressourcen blockiert ist.

Intune bietet Schutz für Unternehmensdaten während der Migration, damit Ihre Unternehmensdaten weiterhin geschützt sind, auch wenn es gerade keine Verwaltung auf der Geräteebene gibt.

Wenn Sie den bedingten Zugriff beim alten MDM-Anbieter deaktivieren, können die Benutzer immer noch produktiv sein, während Sie sie zu Intune überführen.

## <a name="task-list-for-app-protection-policies"></a>Aufgabenliste für App-Schutzrichtlinien

-   Aufgabe 1: Erfahren Sie, welche [Vorbereitungen für das Konfigurieren von App-Schutzrichtlinien](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) Sie treffen müssen

-   Aufgabe 2: Erfahren Sie, wie Sie [Schutzrichtlinien für mobile Apps erstellen und bereitstellen](https://docs.microsoft.com/en-us/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) können

## <a name="next-steps"></a>Nächste Schritte 

[Phase 1: Besondere Überlegungen bei der Migration](https://docs.microsoft.com/intune/plan-design/migration-phase1-special-migration-considerations)

