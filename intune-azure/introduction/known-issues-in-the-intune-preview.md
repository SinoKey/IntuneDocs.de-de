---
title: Bekannte Probleme in der Microsoft Intune-Vorschau
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie etwas über bekannte Probleme in der Vorschau."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b6c245d60c661c04b4c4d29c9bdcdd752254d978
ms.openlocfilehash: ec3f87994b19591bda4ec201eac3c839798d634c
ms.lasthandoff: 03/15/2017


---

# <a name="known-issues-in-the-microsoft-intune-preview"></a>Bekannte Probleme in der Vorschau von Microsoft Intune


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


In diesem Thema erfahren Sie etwas über bekannte Probleme in der Intune-Vorschau.

Wenn Sie einen Fehler melden möchten, der hier nicht aufgeführt ist, [öffnen Sie eine Supportanfrage](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

Wenn Sie ein neues Feature für Intune anfordern möchten, sollten Sie auf unsere [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console)-Website einen Bericht erstellen.

## <a name="administration-and-accounts"></a>Verwaltung und Konten

- Globale Administratoren (auch als Mandantenadministratoren bezeichnet) können weiterhin alltägliche Verwaltungsaufgaben ausführen, ohne über eine separate Intune- oder EMS-Lizenz (Enterprise Mobility Suite) zu verfügen. Wenn globale Administratoren den Dienst jedoch verwenden möchten, um z. B. ihr eigenes Gerät oder ein unternehmenseigenes Gerät zu registrieren bzw. das Intune-Unternehmensportal zu verwenden, benötigen sie wie alle anderen Benutzer eine Intune- oder EMS-Lizenz.

## <a name="apple-enrollment-profile-migration"></a>Migration des Apple-Registrierungsprofils
- In den kommenden Monaten ermöglicht Intune die Verwaltung Ihrer Registrierungen für das Apple-Geräteregistrierungsprogramm und für Apple Configurator über das neue Azure-Portal. Wenn Sie das Token für das Apple-Geräteregistrierungsprogramm löschen und kein aktualisiertes Token hochladen, wird das ursprüngliche Token im Rahmen der Migration Ihres Intune-Kontos im neuen Azure-Portal wiederhergestellt. Wenn Sie dieses Token entfernen und die DEP-Registrierung verhindern möchten, löschen Sie das Token einfach im Azure-Portal. 

