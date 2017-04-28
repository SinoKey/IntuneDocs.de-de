---
title: Wie Ihre iOS-Benutzer Apps erhalten | Microsoft-Dokumentation
description: "Methoden, um iOS-Apps für Endbenutzer verfügbar zu machen."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 02e54d4ae2ffa860fb95725c74fdff913e88365b
ms.lasthandoff: 04/24/2017


---


# <a name="how-your-ios-users-get-their-apps"></a>Wie Ihre iOS-Benutzer Apps erhalten

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Verwenden Sie diese Informationen, um zu verstehen, wie und wo Ihre Endbenutzer die Apps erhalten, die Sie über Microsoft Intune verteilen.

**Erforderliche Apps:** Apps, die vom Administrator benötigt werden und auf dem Gerät (abhängig von der Plattform) mit minimalen Benutzereingriffen installiert werden.

**Verfügbare Apps:** Apps, die in der App-Liste im Unternehmensportal enthalten sind und die ein Benutzer optional installieren kann.

**Verwaltete Apps:** Apps, die mittels Richtlinien verwaltet werden können und die von Intune „umschlossen“ werden oder mit dem Software Development Kit (SDK) für die Verwaltung mobiler Anwendungen (MAM) in Intune erstellt wurden. Diese Apps können von Intune verwaltet werden, und ihnen lassen sich Anwendungsrichtlinien zuweisen.

**Nicht verwaltete Apps**: Apps, die mittels Richtlinien verwaltet werden können und die nicht von Intune umschlossen wurden oder nicht in das Intune MAM SDK integriert sind. Diesen Apps lassen sich keine Anwendungsrichtlinien zuweisen.

Einschränkungen seitens Apple verbieten die Auflistung von branchenspezifischen und verwalteten Apps aus dem App Store in der Unternehmensportal-App. Um dieses Problem zu umgehen, verweisen die Kacheln in der Unternehmensportal-App für iOS die Benutzer für alle ihre Apps auf verschiedene Ansichten an einem einzigen Speicherort (der Unternehmensportal-Website).

Registrierte Benutzer erhalten ihre Apps durch Berühren der folgenden Kacheln auf dem Bildschirm „Apps“ der Unternehmensportal-App:

- **Alle Apps** verweist auf eine Liste aller Apps auf der Registerkarte „ALLE“ der [Unternehmensportal-Website](https://portal.manage.microsoft.com).

- **Ausgewählte Apps** leitet Benutzer zur Registerkarte „EMPFOHLEN“ der Unternehmensportal-Website.

- **Kategorien** verweist auf die Registerkarte „KATEGORIEN“ der Unternehmensportal-Website.


![Apps-Bildschirm des iOS-Unternehmensportals](./media/ios-cp-app-main-apps-screen.png)

Informationen zum Hinzufügen von Apps und ihrer Platzierung auf diesen Kacheln finden Sie unter [Hinzufügen von Apps für registrierte Geräte zu Intune](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune.md).

### <a name="see-also"></a>Weitere Informationen:
[Wie Ihre Android-Benutzer Apps erhalten](how-your-android-users-get-their-apps.md)

[Wie Ihre Windows-Benutzer Apps erhalten](how-your-windows-users-get-their-apps.md)

