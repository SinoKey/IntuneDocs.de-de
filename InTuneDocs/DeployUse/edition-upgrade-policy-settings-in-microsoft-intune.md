---
title: "Einstellungen der Upgraderichtlinie für die Windows-Edition | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8e911193075d2a621ef94f2917b2126501ea2100
ms.openlocfilehash: e468ff102b45bf0c23fd76d8d15c44978861ae8a


---

# Einstellungen der Upgraderichtlinie für die Windows-Edition in Microsoft Intune
Mithilfe der Microsoft Intune-**Upgraderichtlinie für die Edition** können Sie für Geräte, die eine der folgenden Windows 10-Versionen ausführen, automatisch Upgrades vornehmen:
* Windows 10 Desktop
* Windows 10 Holographic

## Vorbereitung
Bevor Sie beginnen, Geräte auf die neueste Version zu aktualisieren, benötigen Sie eines der folgenden Dinge:
* Einen gültigen Product Key für die Installation der neuen Version von Windows auf allen Geräten, die das Ziel dieser Richtlinie sind (für Windows 10-Desktopeditionen)
* Eine Lizenzdatei von Microsoft, die die Lizenzierungsinformationen zum Installieren der neuen Version von Windows auf allen Geräten enthält, die das Ziel dieser Richtlinie sind (für Windows 10 Mobile- und Windows 10 Holographic-Editionen).
* Die Windows 10-Geräte, die als Ziel vorgesehen sind, müssen bei Microsoft Intune registriert sein.

## Einstellungen der Upgraderichtlinie für die Edition

|Name der Einstellung|Details|
|-|-|
|**Name**|Geben Sie einen Namen für die Upgraderichtlinie für die Edition ein.|
|**Beschreibung**|Geben Sie optional eine Beschreibung für die Richtlinie ein, damit Sie sie in der Intune-Konsole besser identifizieren können.
|**Edition, auf die das Upgrade erfolgen soll**|Wählen Sie aus der Dropdownliste die Version von Windows 10 Desktop, Windows 10 Holographic oder Windows 10 Mobile aus, auf die ein Upgrade für die als Ziel angegebenen Geräte erfolgen soll.
|**Product Key**|Geben Sie den Product Key an, den Sie von Microsoft erhalten haben, und der für das Upgrade aller als Ziel festgelegten Windows 10 Desktop-Geräte verwendet werden kann.<br>Nach der Erstellung einer Richtlinie mit einem Product Key können Sie den Product Key später nicht mehr bearbeiten. Grund hierfür ist, dass der Schlüssel aus Sicherheitsgründen verborgen wird. Um den Product Key zu ändern, müssen Sie den gesamten Schlüssel erneut eingeben.
|**Lizenzdatei**|Klicken Sie auf **Durchsuchen**, um die von Microsoft erhaltene Lizenzdatei auszuwählen, die Lizenzinformationen für die Windows Holographic-Edition oder für die Windows 10 Mobile-Edition enthält, auf die das Upgrade bei den als Ziel festgelegten Geräten erfolgen soll.

### Weitere Informationen:
[Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)


<!--HONumber=Jun16_HO4-->


