---
title: Wie Ihre Android-Benutzer Apps erhalten | Microsoft-Dokumentation
description: "Methoden, um Android-Apps für Endbenutzer verfügbar zu machen."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 370dd5d4a96253f0b7d208ef85659beeace18739


---


# <a name="how-your-android-users-get-their-apps"></a>Wie Ihre Android-Benutzer Apps erhalten

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Verwenden Sie diese Informationen, um zu verstehen, wie und wo Ihre Android-Endbenutzer die Apps erhalten, die Sie über Microsoft Intune verteilen. Die Informationen können je nach Gerätetyp variieren (native Android-Geräte oder Samsung Knox Standard-Geräte).

## <a name="native-non-samsung-knox-standard-android-devices"></a>Native Android-Geräte (nicht Samsung Knox Standard)

| App-Typ | Branchenspezifische Apps | Play Store-Apps  |
| ------------- |-------------| -----|
| Verfügbare Apps      | Benutzer tippen im Unternehmensportal auf **Installieren**. Es wird eine Benachrichtigung angezeigt, auf die die Benutzer tippen, um die Installation zu starten. Nachdem die Installation erfolgreich durchgeführt wurde, verschwindet die Benachrichtigung. | Benutzer tippen im Unternehmensportal auf die App und werden zu einer App-Seite im Play Store weitergeleitet, auf der sie die Installation starten können.|
| Required apps      | Benutzern wird eine Benachrichtigung angezeigt, die sie nicht verwerfen können, in der sie darauf hingewiesen werden, dass sie eine App installieren müssen. Benutzer tippen auf die Benachrichtigung, um die Installation zu starten. Nachdem die Installation erfolgreich durchgeführt wurde, verschwindet die Benachrichtigung.    | Benutzern wird eine Benachrichtigung angezeigt, die sie nicht verwerfen können, in der sie darauf hingewiesen werden, dass sie eine App installieren müssen. Benutzer tippen auf die Benachrichtigung und werden zu einer App-Seite im Play Store weitergeleitet, auf der sie die Installation starten können. Nachdem die Installation erfolgreich durchgeführt wurde, verschwindet die Benachrichtigung. |

## <a name="samsung-knox-standard-android-devices"></a>Android-Geräte mit Samsung Knox Standard

| App-Typ | Branchenspezifische Apps | Play Store-Apps  |
| ------------- |-------------| -----|
| Verfügbare Apps      | Benutzer tippen im Unternehmensportal auf **Installieren**. Die App wird ohne weiteres Eingreifen der Benutzer installiert. | Benutzer tippen im Unternehmensportal auf die App und werden zu einer App-Seite im Play Store weitergeleitet, auf der sie die Installation starten können.|
| Required apps      | Die App wird ohne weiteres Eingreifen der Benutzer installiert.    | Benutzern wird eine Benachrichtigung angezeigt, die sie nicht verwerfen können, in der sie darauf hingewiesen werden, dass sie eine App installieren müssen. Benutzer tippen auf die Benachrichtigung und werden zu einer App-Seite im Play Store weitergeleitet, auf der sie die Installation starten können. Nachdem die Installation erfolgreich durchgeführt wurde, verschwindet die Benachrichtigung. |

Apps können verwaltet oder nicht verwaltet sein, wie unten beschrieben. Das Verfahren, mit dem Apps in die Verwaltung eingebunden werden, ist das gleiche für alle Arten von Android-Geräten.

**Verwaltete Apps:** Dabei handelt es sich um Apps, die mittels Richtlinien verwaltet werden können. Sie wurden von Intune „umschlossen“ oder mit dem Software Development Kit (SDK) für die Verwaltung mobiler Anwendungen (MAM) in Intune erstellt. Diese Apps können von Intune verwaltet werden, und ihnen lassen sich Anwendungsrichtlinien zuweisen.

**Nicht verwaltete Apps:** Dabei handelt es sich um Apps, die nicht über Richtlinien verwaltet werden können. Diese Apps wurden nicht von Intune „umschlossen“ oder sind nicht in das Intune MAM SDK integriert. Diesen Apps lassen sich keine Anwendungsrichtlinien zuweisen.

### <a name="see-also"></a>Weitere Informationen:
[Hinzufügen von Apps mit Microsoft Intune](/intune/deploy-use/add-apps)

[Wie Ihre iOS-Benutzer Apps erhalten](how-your-ios-users-get-their-apps.md)

[Wie Ihre Windows-Benutzer Apps erhalten](how-your-windows-users-get-their-apps.md)



<!--HONumber=Dec16_HO2-->


