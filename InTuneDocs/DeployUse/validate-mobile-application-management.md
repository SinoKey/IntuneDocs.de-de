---
title:
- "Überprüfen Ihres MAM-Setups | Microsoft Intune"
description: "In diesem Thema wird beschrieben, wie Sie testen und überprüfen können, ob Ihre MAM-Richtlinie ordnungsgemäß eingerichtet wurde und wie erwartet funktioniert."
keywords: 
author: karthikaraman
manager: angerobe
ms.date: 08/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 41d82597-e13e-4c3e-9151-e71392236ca0
ms.reviewer: joglocke
translationtype: Human Translation
ms.sourcegitcommit: 52d9301f6297065f752cea1dd19024efb11f0730
ms.openlocfilehash: a92334871301523c33f7453038df3ae0fc1fd1a4


---

# Überprüfen des Setups für die Verwaltung Ihrer mobilen Anwendungen

Dieses Thema enthält Informationen zum Suchen nach Problemen nach der Einrichtung der mobilen Anwendungsverwaltung (MAM). Diese Anleitung gilt für MAM-Richtlinien im Azure-Portal.

### Suchen nach Symptomen
Benutzer melden so gut wie keine Probleme, da MAM ein Tool zum Schutz von Daten ist. Liegt ein Problem mit der MAM-Konfiguration vor, erhält der Benutzer uneingeschränkten Zugriff, so wie es ohne MAM der Fall wäre, und er würde nicht bemerken, dass es ein Problem gibt. Aus diesem Grund wird empfohlen, dass Sie Ihre MAM-Konfiguration überprüfen, indem Sie Ihre MAM-Richtlinien mit einer kleinen Gruppe von Benutzern steuern, die bewusst die MAM-Einschränkungen testen können. 


### Was soll überprüft werden? 

Wenn der Test zeigt, dass das Verhalten Ihrer MAM-Richtlinie nicht wie erwartet ist, empfiehlt es sich, folgende Punkte zu überprüfen:

- Sind die Benutzer für MAM lizenziert?
- Sind die Benutzer für Office 365 lizenziert?
- Der Status der MAM-Apps eines jeden Benutzers. Die möglichen Statuswerte für die apps sind **Eingecheckt** und **Nicht eingecheckt**.

#### MAM-Status des Benutzers
1. Wählen Sie im Azure-Portal **Mobile Anwendungsverwaltung mit Intune** > **Einstellungen** > **App-Verwaltung** > **Alle Einstellungen** > **App-Berichterstellung nach Benutzer** > **Benutzer**.

2. Wählen Sie einen Benutzer aus der Liste aus, oder suchen Sie einen Benutzer und wählen Sie Ihn aus. Wählen Sie anschließend **Benutzer auswählen** aus. Am oberen Rand der Spalte **App-Berichterstellung** sehen Sie, ob der Benutzer für die MAM lizenziert ist. Nachfolgend sehen Sie, ob der Benutzer für Office 365 und den App-Status aller Geräte des Benutzers lizenziert ist.

![App-Statuts für MAM](..\media\ts-mam-use-apps.png) 

### Aktion
Hier sind die Aktionen, die basierend auf den Benutzerstatus durchgeführt werden müssen:

- Wenn der Benutzer nicht für MAM lizenziert ist, weisen Sie dem Benutzer eine Intune-Lizenz zu, wie unter [Verwalten von Intune-Lizenzen](..\get-started\start-with-a-paid-subscription-to-microsoft-intune) beschrieben.
- Wenn der Benutzer nicht für Office 365 lizenziert ist, rufen Sie eine Lizenz für den Benutzer ab.
- Wenn die App des Benutzer als **Nicht eingecheckt** aufgelistet ist, überprüfen Sie, ob Sie die MAM-Richtlinie für diese App ordnungsgemäß konfiguriert haben.
- Stellen Sie sicher, dass diese Bedingungen auf alle Benutzer angewendet werden, auf die die MAM Richtlinien angewendet werden sollen.

### Weitere Informationen:
[Vorbereiten der Konfiguration von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](..\deploy-use\get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)

[Schützen von App-Daten mithilfe der Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](..\deploy-use\protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)



<!--HONumber=Aug16_HO5-->


