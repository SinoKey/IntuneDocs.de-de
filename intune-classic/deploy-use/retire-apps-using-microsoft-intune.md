---
title: "Außerbetriebnahme von Apps"
description: "Informationen zur Außerbetriebnahme oder zum Deinstallieren von Apps mithilfe von Intune."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6fbf0805-1144-4e08-bafd-4f181d932bf2
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 98dfbd3b4916a0614da7cb8169a594ab4e4044e8
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2017
---
# <a name="retire-apps-using-microsoft-intune"></a>Außerbetriebnahme von Apps mit Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Um eine App außer Betrieb zu nehmen, deinstallieren Sie sie einfach. Wenn Sie Apps mit Intune bereitstellen und verwalten, ist der Prozess zum Deinstallieren der App für mobile Geräte und Windows-PCs identisch. Damit dieses Verfahren erfolgreich ausgeführt werden kann, muss die App den Deinstallationsprozess unterstützen.

## <a name="uninstall-an-app"></a>Deinstallieren einer App

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) **Apps** &gt; **Apps** aus.

2.  Wählen Sie die zu deinstallierende App aus (eine, die zuvor bereitgestellt wurde), und wählen Sie anschließend **Bereitstellung verwalten** aus.

3.  Wählen Sie auf der Seite **Bereitstellungsaktion** die Option **Deinstallieren** aus der Spalte **Genehmigung** aus.

Wenn das Gerät oder der Computer das nächste Mal die Apps prüft, wird die App deinstalliert.

### <a name="see-also"></a>Weitere Informationen:
[Hinzufügen von Apps in Microsoft Intune](add-apps.md)
