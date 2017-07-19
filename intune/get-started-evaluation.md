---
title: Erste Schritte mit Intune
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bfab644-c1e2-4154-a254-e95b9a1d75f2
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ef58e46118a0a44609abba5de4986b5a1526a151
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2017
---
# <a name="what-is-microsoft-intune"></a>Was ist Microsoft Intune?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

![Microsoft Intune im Azure-Portal](./media/generic-intune-azure.png)

Microsoft Intune ist einer der neuesten Azure-Dienste. Er bietet Tools zum Verwalten der mobilen Geräte, PCs und Apps Ihrer Organisation, die [regelmäßig aktualisiert](whats-new.md) werden. Neben der modernen Azure-Konsole ermöglicht Intune auch die Verwendung der klassischen Konsole. Die klassische Konsole ist die erste Version von Intune, die Sie noch immer nutzen, um [Windows-PCs mit dem Intune-Softwareclient zu verwalten](/intune-classic/deploy-use/pc-management-comparison.md). Das klassische Portal, das in Silverlight integriert ist, wird für wenige Aufgaben verwendet. Alles andere einschließlich der Verwaltung mobiler Geräte und Apps erfolgt im Azure-Portal. Die ersten Schritte führen Sie durch die grundlegenden Aufgaben, die Sie erfüllen müssen, um Intune erfolgreich im Azure-Portal nutzen zu können.

![Das Blatt zu Hilfe und Support finden Sie in der linken Randleiste von Intune unten auf der Liste der Aktionen.](./media/intune-azure-help-support-closeup.png)

## <a name="what-does-intune-in-the-azure-portal-provide"></a>Was bietet Intune im Azure-Portal?

Intune im Azure-Portal bietet Ihnen:

* Eine integrierte Konsole für alle [Komponenten von Enterprise Mobility + Security (EMS)](https://docs.microsoft.com/enterprise-mobility-security)
* Eine HTML-Konsole basierend auf Webstandards, die [moderne Webbrowser](supported-devices-browsers.md) unterstützt
* [Azure Active Directory-Gruppen](groups-get-started.md) für Kompatibilität zwischen all Ihren Azure-Anwendungen
* Automatisierung über die [Microsoft Graph-API](intune-graph-apis.md)

## <a name="prerequisites"></a>Voraussetzungen

Bevor Sie beginnen, benötigen Sie ein Administratorkonto und ein Mandantenkonto für Intune. Für diese Konten können Sie sich [hier](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) registrieren. Aktuelle Abonnenten können diese Schritte auch in ihrem Live-Mandanten vornehmen. Stellen Sie sicher, dass Sie nur mit Testgeräten arbeiten!

Sie müssen auch sicherstellen, dass Sie der globale Administrator für Ihre Organisation sind, um alle Aufgaben in dieser Anleitung abzuschließen.
