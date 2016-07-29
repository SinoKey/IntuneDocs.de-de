---
title: Wie Ihre Android-Benutzer Apps erhalten | Microsoft Intune
description: "Methoden, um Android-Apps für Endbenutzer verfügbar zu machen."
keywords: 
author: Staciebarker
manager: arob98
ms.date: 7/7/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: 43b7eb3378d9977b9d19196c91a812d9411752b9


---


# Wie Ihre Android-Benutzer Apps erhalten
Verwenden Sie diese Informationen, um zu verstehen, wie und wo Ihre Android-Endbenutzer die Apps erhalten, die Sie über Microsoft Intune verteilen. Diese Informationen können für native Android-Geräte und Samsung KNOX-Geräte unterschiedlich sein.

## Native Android-Geräte (nicht Samsung KNOX)

| App-Typ | Branchenspezifische Apps | Play Store-Apps  |
| ------------- |-------------| -----|
| Verfügbare Apps      | Benutzer tippen im Unternehmensportal auf **Installieren**. Es wird eine Benachrichtigung angezeigt, auf die die Benutzer tippen, um die Installation zu starten. Nachdem die Installation erfolgreich durchgeführt wurde, verschwindet die Benachrichtigung. | Benutzer tippen im Unternehmensportal auf die App und werden zu einer App-Seite im Play Store weitergeleitet, auf der sie die Installation starten können.|
| Required apps      | Benutzern wird eine Benachrichtigung angezeigt, die sie nicht verwerfen können, in der sie darauf hingewiesen werden, dass sie eine App installieren müssen. Benutzer tippen auf die Benachrichtigung, um die Installation zu starten. Nachdem die Installation erfolgreich durchgeführt wurde, verschwindet die Benachrichtigung.    | Benutzern wird eine Benachrichtigung angezeigt, die sie nicht verwerfen können, in der sie darauf hingewiesen werden, dass sie eine App installieren müssen. Benutzer tippen auf die Benachrichtigung und werden zu einer App-Seite im Play Store weitergeleitet, auf der sie die Installation starten können. Nachdem die Installation erfolgreich durchgeführt wurde, verschwindet die Benachrichtigung. |

## Android-Geräte mit Samsung KNOX

| App-Typ | Branchenspezifische Apps | Play Store-Apps  |
| ------------- |-------------| -----|
| Verfügbare Apps      | Benutzer tippen im Unternehmensportal auf **Installieren**. Die App wird ohne weiteres Eingreifen der Benutzer installiert. | Benutzer tippen im Unternehmensportal auf die App und werden zu einer App-Seite im Play Store weitergeleitet, auf der sie die Installation starten können.|
| Required apps      | Die App wird ohne weiteres Eingreifen der Benutzer installiert.    | Benutzern wird eine Benachrichtigung angezeigt, die sie nicht verwerfen können, in der sie darauf hingewiesen werden, dass sie eine App installieren müssen. Benutzer tippen auf die Benachrichtigung und werden zu einer App-Seite im Play Store weitergeleitet, auf der sie die Installation starten können. Nachdem die Installation erfolgreich durchgeführt wurde, verschwindet die Benachrichtigung. |

Apps können verwaltet oder nicht verwaltet sein, wie unten beschrieben. Das Verfahren, mit dem Apps in die Verwaltung eingebunden werden, ist das gleiche für alle Arten von Android-Geräten.

**Verwaltete Apps**: Apps, die mittels Richtlinien verwaltet werden können und die von Intune „umschlossen“ werden oder mit dem Intune Mobile Application Management (MAM) Software Development Kit (SDK) erstellt wurden. Diese Apps können von Intune verwaltet werden, und ihnen lassen sich Anwendungsrichtlinien zuweisen.

**Nicht verwaltete Apps**: Apps, die mittels Richtlinien verwaltet werden können und die nicht von Intune umschlossen werden oder nicht in das Intune MAM SDK integriert sind. Diesen Apps lassen sich keine Anwendungsrichtlinien zuweisen.

### Weitere Informationen:
[Hinzufügen von Apps mit Microsoft Intune](/intune/deploy-use/add-apps)
[Wie Ihre iOS-Benutzer Apps erhalten](how-your-ios-users-get-their-apps.md)
[Wie Ihre Windows-Benutzer Apps erhalten](how-your-windows-users-get-their-apps.md)



<!--HONumber=Jul16_HO3-->


