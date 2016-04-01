---
title: Aktualisieren von Apps mit Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
author: robstackmsft
---
# Aktualisieren von Apps mit Microsoft Intune
Microsoft Intune können Sie die app-Updates zu verwalten. Anhand der Informationen in diesem Thema erfahren Sie, wie Sie Apps aktualisieren, wenn eine neue Version erforderlich ist.

## Aktualisieren von Apps
Wenn eine neue Version einer Anwendung, die von Ihnen bereitgestellte veröffentlicht wird, Sie können Intune aktualisieren und die neuere Version der Anwendung bereitstellen. Sie können eine Bereitstellung nur durch eine neuere Version der gleichen App (mit derselben ID) ersetzen. App-Updates können nicht zum Aktualisieren einer Bereitstellung mit einem anderen App-Paket verwendet werden.

> [!IMPORTANT]
> Beim Bereitstellen einer App mit der Bereitstellungsaktion **Erforderliche Installation** und einer späteren Änderung der Bereitstellungsaktion in **Verfügbare Installation**werden Updates für die App auf Geräten, auf denen die App vor der Bereitstellungsänderung installiert war, nicht automatisch installiert. Gehen Sie wie folgt vor, um dieses Problem zu beheben:
> 
> -   Bitten Sie den Benutzer des Geräts das Unternehmensportal zu öffnen, die installierte App auszuwählen und auf **Installieren**zu klicken.
> -   Ändern Sie die Bereitstellungsaktion in **Deinstallieren**, und stellen Sie die App nach der Deinstallation der App erneut mit der Bereitstellungsaktion **Verfügbare Installation**bereit.

### So aktualisieren Sie eine App

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://account.manage.microsoft.com/admin/default.aspx)auf **Apps** &gt; **Apps**.

2.  Wählen Sie in der Liste **Apps** die zu aktualisierende App aus, und klicken Sie dann auf **Bearbeiten**.

3.  Geben Sie im Assistenten **Software bearbeiten** neue Details für das App-Paket ein.

4.  Klicken Sie danach auf **Aktualisieren**.

Wenn Geräte das nächste Mal prüfen, ob Apps verfügbar sind, wird die App automatisch auf die neueste Version aktualisiert.





<!--HONumber=Mar16_HO4-->


