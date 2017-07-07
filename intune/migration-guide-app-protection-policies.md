---
title: "Konfigurieren von App-Schutzrichtlinien während einer Migration von Intune"
description: "Dieser Artikel gibt einen Überblick über die für die Einrichtung der App-Schutzrichtlinien notwendigen Schritte während einer Migration von Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cbe2c794a68ab37722c56448560a3c64f6087969
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2017
---
# <a name="configure-app-protection-policies-optional"></a>Konfigurieren von App-Schutzrichtlinien (optional)

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

App-Schutzrichtlinien geben Ihnen u.a. die Möglichkeit, Apps zu verschlüsseln, eine PIN für den Zugriff auf die App zu definieren und das Ausführen von Apps auf Geräten mit entfernten Nutzungsbeschränkungen oder gerooteten Geräten zu blockieren. Wenn das Gerät des Benutzer verloren geht oder geklaut wurde, können Sie die Unternehmensdaten remote selektiv zurücksetzen, ohne dass die persönlichen Daten davon betroffen wären; dies ist mit mobilen App-Schutzrichtlinien möglich.

App-Schutzrichtlinien wenden Sicherheitsmaßnahmen auf der Geräteebene an und erfordern keine Geräteregistrierung. Sie können sowohl für Geräte, die in Intune registriert sind, als auch für nicht registrierte Geräte verwendet werden. Des Weiteren können Sie auch für Geräte verwendet werden, die für Drittanbieter-MDM registriert sind.

## <a name="app-protection-policies-with-lob-apps"></a>App-Schutzrichtlinien für branchenspezifische Apps

Sie können die App-Schutzrichtlinien auch auf branchenspezifische Apps ausweiten, indem Sie das [Microsoft Intune App SDK](/intune-classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management) oder das Microsoft Intune App Wrapping Tool sowohl für [iOS](https://www.microsoft.com/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True)- als auch für [Android](https://www.microsoft.com/download/details.aspx?id=47267)-Plattformen verwenden.

## <a name="how-do-app-protection-policies-help-during-migration"></a>Wie helfen App-Schutzrichtlinien bei der Migration?

Bei der Migration müssen Geräte vom alten MDM-Anbieter entfernt und in Intune registriert werden. Dies sollten Sie berücksichtigen und Ihre Endbenutzer dazu anhalten, den alten MDM-Anbieter zu verlassen und sich umgehend in Intune zu registrieren. Bei der Migration kann es allerdings Benutzer geben, die den Abschluss des Registrierungsprozesses verzögern, weil Ihre Geräte von keinem der beiden MDM-Anbieter verwaltet werden.

In diesem Zeitraum kann Ihre Organisation anfälliger sein für den Geräteklau und den Verlust von Unternehmensdaten, wenn der Zugriff auf Unternehmensressourcen immer noch möglich ist. Außerdem kann die Benutzerproduktivität abnehmen, wenn der Zugriff auf Unternehmensressourcen blockiert ist.

Intune bietet Schutz für Unternehmensdaten während der Migration, damit Ihre Unternehmensdaten weiterhin geschützt sind, auch wenn es gerade keine Verwaltung auf der Geräteebene gibt.

Wenn Sie den bedingten Zugriff beim alten MDM-Anbieter deaktivieren, können die Benutzer immer noch produktiv sein, während Sie sie zu Intune überführen.

## <a name="task-list-for-app-protection-policies"></a>Aufgabenliste für App-Schutzrichtlinien

1. [Erstellen einer App-Schutzrichtlinie](/intune/app-protection-policies#create-an-app-protection-policy)
2. [Bereitstellen einer Richtlinie](/intune/app-protection-policies#deploy-a-policy-to-users)


## <a name="next-steps"></a>Nächste Schritte 

[Besondere Überlegungen bei der Migration](migration-guide-considerations.md)
