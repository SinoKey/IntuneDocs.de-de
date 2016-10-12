---
title: "Einstellungen der Upgraderichtlinie für die Windows-Edition | Microsoft Intune"
description: "Erfahren Sie, wie Sie Windows 10-Geräte mit Intune automatisch auf die neueste Version aktualisieren."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f2aa531744dbd0774958e0450819e45e60a91086
ms.openlocfilehash: 93a632f0f0b8d31149fa1d5fbe15b31d715d20a8


---

# Einstellungen der Upgraderichtlinie für die Windows-Edition in Microsoft Intune
Mithilfe der Microsoft Intune-**Upgraderichtlinie für die Edition** können Sie für Geräte, die eine der folgenden Windows 10-Versionen ausführen, automatisch Upgrades vornehmen:
* Windows 10 Desktop
* Windows 10 Holographic
* Windows 10 Mobile

Die folgenden Upgradepfade werden unterstützt:
- Von Windows 10 Pro auf Windows 10 Enterprise
- Von Windows 10 Home auf Windows 10 Education
- Von Windows 10 Mobile auf Windows 10 Mobile Enterprise
- Von Windows 10 Holographic Pro auf Windows 10 Holographic Enterprise

## Vorbereitung
Bevor Sie beginnen, Geräte auf die neueste Version zu aktualisieren, benötigen Sie eines der folgenden Dinge:
* Einen gültigen Product Key für die Installation der neuen Version von Windows auf allen Geräten, die das Ziel dieser Richtlinie sind (für Windows 10-Desktopeditionen) Sie können entweder Mehrfachaktivierungsschlüssel (Multiple Activation Keys, MAK) oder KMS-Schlüssel (Key Management Server, Schlüsselverwaltungsserver) verwenden.
**Alternativ** verwenden Sie eine Lizenzdatei von Microsoft, die die Lizenzierungsinformationen zum Installieren der neuen Version von Windows auf allen Geräten enthält, die das Ziel dieser Richtlinie sind (für Windows 10 Mobile- und Windows 10 Holographic-Editionen).
* Die Windows 10-Geräte, die als Ziel vorgesehen sind, müssen bei Microsoft Intune registriert sein. Die Editionsupgraderichtlinie kann nicht für PCs verwendet werden, auf denen die Intune-PC-Clientsoftware ausgeführt wird.

## Einstellungen der Upgraderichtlinie für die Edition

|Name der Einstellung|Details|
|-|-|
|**Name**|Geben Sie einen Namen für die Upgraderichtlinie für die Edition ein.|
|**Beschreibung**|Geben Sie optional eine Beschreibung für die Richtlinie ein, damit Sie sie in der Intune-Konsole besser identifizieren können.
|**Edition, auf die das Upgrade erfolgen soll**|Wählen Sie aus der Dropdownliste die Version von Windows 10 Desktop, Windows 10 Holographic oder Windows 10 Mobile aus, auf die ein Upgrade für die als Ziel angegebenen Geräte erfolgen soll.
|**Product Key**|Geben Sie den Product Key an, den Sie von Microsoft erhalten haben, und der für das Upgrade aller als Ziel festgelegten Windows 10 Desktop-Geräte verwendet werden kann.<br>Nach der Erstellung einer Richtlinie, die einen Product Key enthält, können Sie den Product Key später nicht mehr bearbeiten. Grund hierfür ist, dass der Schlüssel aus Sicherheitsgründen verborgen wird. Um den Product Key zu ändern, müssen Sie den gesamten Schlüssel erneut eingeben.
|**Lizenzdatei**|Klicken Sie auf **Durchsuchen**, um die von Microsoft erhaltene Lizenzdatei auszuwählen, die Lizenzinformationen für die Windows Holographic-Edition oder für die Windows 10 Mobile-Edition enthält, auf die das Upgrade bei den als Ziel festgelegten Geräten erfolgen soll.

### Siehe auch
[Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Sep16_HO5-->


