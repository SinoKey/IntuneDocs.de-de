---
title: "Verwalten unternehmenseigener Geräte | Microsoft Intune"
description: "Registrieren Sie unternehmenseigene Geräte auf verschiedene Weise, je nach Gerätetyp, Art des Kaufs und den Anforderungen der Organisation."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9d44a6494bed0758b9768045bd204ea0eb481636
ms.openlocfilehash: 7577cbab528d88635e8551bf8de1ffd49becaa84


---

# <a name="enroll-corporateowned-devices-by-using-intune"></a>Registrieren unternehmenseigener Geräte über Intune

Sie können organisations- bzw. unternehmenseigene Geräte auf verschiedene Weise für die Verwaltung durch Intune registrieren, je nachdem, um welches Gerät es sich handelt, wie es erworben wurde und welche Anforderungen der Organisation bestehen. Sie können auch die Unternehmensportal-App installieren, um unternehmenseigene Geräte zu registrieren und zu verwalten, ähnlich wie in einem BYOD-Szenario („Bring Your Own Device“).

## <a name="enroll-corporateowned-ios-devices"></a>Registrieren firmeneigener iOS-Geräte

Die Registrierungsmethoden für unternehmenseigene Geräte eignen sich gut für CYOD-Szenarien („Choose Your Own Device“). In einer CYOD-Umgebung bezahlt die Organisation das Gerät, das der Benutzer sich aussucht, und die Organisation verwaltet das Gerät auch.

Wenn Sie iOS-Geräte zur Auswahl anbieten, können Sie die Registrierung vorkonfigurieren, sodass das Gerät direkt ab dem ersten Einschalten durch den Benutzer über Intune verwaltet wird. Intune unterstützt die Registrierung mithilfe des [Apple-Programms zur Geräteregistrierung (Device Enrollment Program, DEP)](ios-device-enrollment-program-in-microsoft-intune.md) oder des Tools Apple Configurator, das auf einem Mac-Computer für die [direkte](ios-direct-enrollment-in-microsoft-intune.md) Registrierung oder die Registrierung mit dem [Setup-Assistenten](ios-setup-assistant-enrollment-in-microsoft-intune.md) ausgeführt wird.

Erfahren Sie, wie Sie [unternehmenseigene iOS-Geräte registrieren](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

## <a name="create-a-device-enrollment-manager-account"></a>Erstellen eines Kontos für Geräteregistrierungs-Manager

Sie können ein DEM-Konto (Device Enrollment Manager) für einen Einzelbenutzer in Intune erstellen, um eine Vielzahl von mobilen Geräten für Ihre Organisation zu verwalten. Nachdem Sie das DEM-Konto erstellt haben, kann ein festgelegter Konto-Manager mehr als die fünfzehn Geräte registrieren, die ein Standardbenutzer registrieren darf.

Sie können ein DEM-Konto verwenden, um nur Geräte zu registrieren, die nicht von einem bestimmten Benutzer verwendet werden. Diese Gerätetypen eignen sich z.B. für POS- oder -Hilfsprogramm-Apps, nicht aber für Benutzer, die Zugriff auf E-Mails oder Unternehmensressourcen benötigen.

Erfahren Sie, wie Sie [unternehmenseigene Geräte mithilfe eines DEM-Kontos registrieren](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

## <a name="enroll-corporateowned-windows-10-enterprise-devices"></a>Registrieren von unternehmenseigenen Windows 10 Enterprise-Geräten

Wenn Sie in Ihrer Organisation Azure Active Directory oder die Microsoft Enterprise Mobility Suite verwenden, können Sie [Windows 10 Enterprise-Geräte registrieren](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview). Wenn ein Benutzer auf einem Gerät ein Geschäfts-, Schul- oder Unikonto hinzufügt, wird das Gerät automatisch als „unternehmenseigen“ markiert.

## <a name="import-imei-numbers"></a>Importieren von IMEI-Nummern

Viele Hersteller von mobilen Geräten verwenden für jedes Gerät eine eindeutige Nummer, eine so genannte IMEI-Nummer (International Mobile Equipment Identity). Sie können IMEI-Nummern für Geräte importieren, die sich im Besitz Ihrer Organisation befinden. Wenn ein Gerät von Intune verwaltet wird, wird es als unternehmenseigenes Gerät markiert.

Erfahren Sie, wie Sie [unternehmenseigene Geräte mithilfe von IMEI-Nummern markieren](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md).

## <a name="identify-a-device-as-corporateowned"></a>Identifizieren von Geräten als unternehmenseigen

In einer Geräteliste lautet der Wert für den **Besitz** für die entsprechenden Geräte **Unternehmen**. Ein unternehmenseigenes Gerät weist eines dieser Merkmale auf:

 - Das Gerät wurde [mithilfe eines DEM-Kontos registriert](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).
 - Das Gerät wurde mithilfe von [Apple DEP](ios-device-enrollment-program-in-microsoft-intune.md) oder [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md) registriert.
 - Der Gerätehersteller [hat das Gerät mithilfe von IMEI-Nummern vorab deklariert](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md).
 - Jedes Gerät ist in [Azure Active Directory oder der Enterprise Mobility Suite als Windows 10 Enterprise-Gerät](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview) registriert.



<!--HONumber=Nov16_HO2-->


