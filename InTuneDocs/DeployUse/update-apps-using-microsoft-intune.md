---
title: Aktualisieren von Apps | Microsoft Intune
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
ms.reviewer: mghadial
ms.suite: ems
ms.sourcegitcommit: 0581d1476fba5bedcdd4446df20f8f92b151f41b
ms.openlocfilehash: 9e5b8f4a467e8e58cc2f8fa495b5f008eee7e35b


---

# Aktualisieren von Apps mit 
Microsoft Intune unterstützt Sie bei der Verwaltung von App-Updates. Anhand der Informationen in diesem Thema erfahren Sie, wie Sie Apps aktualisieren, wenn eine neue Version erforderlich ist.

## Aktualisieren von Apps
Wenn eine neue Version einer von Ihnen bereitgestellten App veröffentlicht wird, können Sie mit Intune die neuere Version der App aktualisieren und bereitstellen. Sie können eine Bereitstellung nur durch eine neuere Version der gleichen App (mit derselben ID) ersetzen. App-Updates können nicht zum Aktualisieren einer Bereitstellung mit einem anderen App-Paket verwendet werden.

> [!IMPORTANT]
> Beim Bereitstellen einer App mit der Bereitstellungsaktion **Erforderliche Installation** und einer späteren Änderung der Bereitstellungsaktion in **Verfügbare Installation**werden Updates für die App auf Geräten, auf denen die App vor der Bereitstellungsänderung installiert war, nicht automatisch installiert. Gehen Sie wie folgt vor, um dieses Problem zu beheben:
> 
> -   Bitten Sie den Benutzer des Geräts, das Unternehmensportal zu öffnen, die installierte App auszuwählen und **Installieren** auszuwählen.
> -   Ändern Sie die Bereitstellungsaktion in **Deinstallieren**, und stellen Sie die App nach der Deinstallation der App erneut mit der Bereitstellungsaktion **Verfügbare Installation**bereit.

### So aktualisieren Sie eine App

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) **Apps** &gt; **Apps**.

2.  Wählen Sie in der Liste **Apps** die zu aktualisierende App und anschließend **Bearbeiten** aus.

3.  Geben Sie im Assistenten **Software bearbeiten** neue Details für das App-Paket ein.

4.  Wählen Sie anschließend **Aktualisieren** aus.

Wenn Geräte das nächste Mal prüfen, ob Apps verfügbar sind, wird die App automatisch auf die neueste Version aktualisiert.
Bei Apps, die aus einem App-Paket installiert wurden (branchenspezifische Apps), erfolgt das Upgrade für erforderliche sowie verfügbare Bereitstellungen automatisch, solange die App über denselben Bezeichner verfügt.
Bei Apps, die als Link zu einem Store bereitgestellt wurden, wird das Update von dem Store verwaltet, aus dem die App stammt.






<!--HONumber=Jul16_HO2-->


