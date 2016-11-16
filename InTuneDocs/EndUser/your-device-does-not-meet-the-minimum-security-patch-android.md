---
title: "Ihr Gerät weist nicht den mindestens erforderlichen Sicherheitspatch auf | Microsoft Intune"
description: 
keywords: 
author: barlan
ms.author: barlan
manager: angrobe
ms.date: 09/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b3e5994c-d215-4c72-8915-349bd0b2504d
ROBOTS: NOINDEX,NOFOLLOW
translationtype: Human Translation
ms.sourcegitcommit: 016449720f6e77b8862fcaa232d252eefa8b20b3
ms.openlocfilehash: 8569d99d7f79b0a27f31aec33f364d30499c6520


---

# Ihr Gerät weist nicht den mindestens erforderlichen Sicherheitspatch auf

Wenn Sie die Meldung „Minimum Android security patch level is not configured“ (Niedrigste zulässige Android-Sicherheitspatchebene ist nicht konfiguriert) sehen, müssen Sie den mindestens erforderlichen Sicherheitspatch oder eine höhere Version installieren. Ihr IT-Administrator verlangt diese Installation, um die Unternehmensdaten auf Ihrem Android-Gerät zu schützen.

Der Speicherort der aktuellen Sicherheitspatchebene variiert je nach Android-Gerät. Sie müssen herausfinden, ob es sich bei Ihrem Gerät um ein Samsung Knox-Gerät oder einen anderen Typ von Android-Gerät handelt. Wechseln Sie zu **Einstellungen** > **Geräteinformationen**, um zu überprüfen, ob es sich bei Ihrem Gerät um ein Samsung Knox-Gerät handelt. Wird das Wort „Knox“ dort nicht aufgelistet, verfügen Sie nicht über ein Samsung Knox-Gerät.

**So ermitteln Sie die neueste Softwareversion auf Ihrem Gerät:**

- Nicht-Samsung Knox-Geräte: Versuchen Sie die Softwareermittlung wie folgt. Wechseln Sie zu **Einstellungen** > **Info** > **Softwareinformationen** > **Mehr**, und sehen Sie anschließend unter **Android security patch level** (Android-Sicherheitspatchebene) nach. Die Menünamen und Speicherorte können bei verschiedenen Android-Geräten leicht abweichen.

- Samsung Knox-Geräte: Wechseln Sie zu **Einstellungen** > **About Phone** (Info zu Gerät) > **Security software version** (Sicherheitssoftwareversion).

**So installieren Sie den erforderlichen Sicherheitspatch:**

- Nicht-Samsung Knox-Geräte: Wechseln Sie zu **Einstellungen** > **Info** > **Softwareupdates**.

- Samsung Knox-Geräte: Wechseln Sie zu **Einstellungen** > **Systemupdates** > **Check for new system update** (Auf neues Systemupdate überprüfen).

Benötigen Sie weitere Unterstützung? Wenden Sie sich an Ihren IT-Administrator. Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](http://portal.manage.microsoft.com).



<!--HONumber=Oct16_HO2-->


