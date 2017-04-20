---
title: Bekannte Probleme in der Microsoft Intune-Vorschau
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie etwas über bekannte Probleme in der Vorschau."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 24498abc504f05bd22dc7309bc22948292f9b1e6
ms.openlocfilehash: 4c81c17ba1419f0b5bdc4910be7d26a5893b32e0
ms.lasthandoff: 04/13/2017


---

# <a name="known-issues-in-the-microsoft-intune-preview"></a>Bekannte Probleme in der Vorschau von Microsoft Intune


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


In diesem Thema erfahren Sie etwas über bekannte Probleme in der Intune-Vorschau.

Wenn Sie einen Fehler melden möchten, der hier nicht aufgeführt ist, [öffnen Sie eine Supportanfrage](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

Wenn Sie ein neues Feature für Intune anfordern möchten, sollten Sie auf unsere [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console)-Website einen Bericht erstellen.

## <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Während der Migration von Intune erstellte Gruppen könnten die Funktionalität anderer Microsoft-Produkte beeinträchtigen.

Beim Migrieren vom klassischen Intune zum Azure-Portal könnten Sie eine neue Gruppe mit dem Namen **All Users - b0b08746-4dbe-4a37-9adf-9e7652c0b421** sehen. Beachten Sie, dass diese Gruppe alle Benutzer in Ihrem Azure Active Directory enthält, nicht nur von Intune lizenzierte Benutzer. Dies könnte zu Problemen mit anderen Microsoft-Produkten führen, wenn Sie erwarten, dass einige vorhandene oder neue Benutzer nicht Mitglieder von Gruppen sind.

## <a name="altering-groups-created-by-intune-during-migration-will-delay-migration"></a>Ändern von Gruppen, die von Intune während der Migration erstellt werden, verzögert die Migration.

Als Vorbereitung für die Migration werden Ihre Gruppen von Intune in Azure AD kopiert. Alle weiteren Änderungen, die Sie im klassischen Intune-Portal vornehmen, werden in der Azure AD-Gruppe aktualisiert. Allerdings werden in Azure AD vorgenommene Änderungen nicht zurück in die klassische Intune-Konsole synchronisiert. Dies könnte dazu führen, dass bei der Migration zum Azure-Portal ein Fehler auftritt, und die Migration verzögern.

## <a name="compliance-policies-from-intune-will-not-show-up-in-new-console"></a>Konformitätsrichtlinien von Intune werden in der neuen Konsole nicht angezeigt. 

Alle Konformitätsrichtlinien, die Sie im klassischen Intune-Portal erstellt haben, werden migriert, jedoch nicht im Azure-Portal angezeigt. Ursache hierfür ist eine Designänderung im Azure-Portal. Konformitätsrichtlinien, die Sie im klassischen Intune-Portal erstellt haben, werden noch erzwungen, jedoch müssen Sie sie im klassischen Portal anzeigen und bearbeiten.
Darüber hinaus werden neue Konformitätsrichtlinien, die Sie im Azure-Portal erstellen, im klassischen Portal nicht angezeigt.
Weitere Informationen finden Sie unter [Was ist die Gerätekonformität in Intune in Azure (Vorschau)?](https://docs.microsoft.com/intune-azure/set-device-compliance/what-is-device-compliance).




## <a name="administration-and-accounts"></a>Verwaltung und Konten

Globale Administratoren (auch als Mandantenadministratoren bezeichnet) können weiterhin alltägliche Verwaltungsaufgaben ausführen, ohne über eine separate Intune- oder EMS-Lizenz (Enterprise Mobility Suite) zu verfügen. Wenn globale Administratoren den Dienst jedoch verwenden möchten, um z. B. ihr eigenes Gerät oder ein unternehmenseigenes Gerät zu registrieren bzw. das Intune-Unternehmensportal zu verwenden, benötigen sie wie alle anderen Benutzer eine Intune- oder EMS-Lizenz.

## <a name="apple-enrollment-profile-migration"></a>Migration des Apple-Registrierungsprofils
In den kommenden Monaten ermöglicht Intune die Verwaltung Ihrer Registrierungen für das Apple-Geräteregistrierungsprogramm und für Apple Configurator über das neue Azure-Portal. Wenn Sie das Token für das Apple-Geräteregistrierungsprogramm löschen und kein aktualisiertes Token hochladen, wird das ursprüngliche Token im Rahmen der Migration Ihres Intune-Kontos im neuen Azure-Portal wiederhergestellt. Wenn Sie dieses Token entfernen und die DEP-Registrierung verhindern möchten, löschen Sie das Token einfach im Azure-Portal. 

