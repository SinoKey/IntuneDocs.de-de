---
title: "Verwalten unternehmenseigener Geräte | Microsoft Intune"
description: "Verschiedene Möglichkeiten zum Aufnehmen von unternehmenseigenen Geräte (Corporate-Owned Devices, COD) in die Verwaltung – je nach Gerät, Art des Kaufs und Anforderungen der Organisation."
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 26ac7d52c0ad3e37e517b60d448a94849c0f4b30
ms.openlocfilehash: 6cf620a96b39540c8b7ca618936af1367971bb8f


---

# Registrieren firmeneigener Geräten bei Microsoft Intune
Organisations- bzw. unternehmenseigene Geräte können je nach Gerät und Art des Kaufs sowie den geschäftlichen Anforderungen auf verschiedene Arten in die Verwaltung aufgenommen werden.

## Firmeneigene iOS-Geräte
Dieser Registrierungsmethoden eignen sich für CYOD-Szenarien („Choose your own Device“), in denen die Organisation die Geräte der Benutzer erwirbt, jedoch die Verwaltung der Geräte beibehalten möchte. Wenn Ihre Organisation iOS-Geräte erworben hat, können Sie die Registrierung vorab konfigurieren, damit jedes Gerät von Moment der Inbetriebnahme durch den Benutzer verwaltet wird. Intune unterstützt die Registrierung mithilfe des [Apple-Programms zur Geräteregistrierung (Device Enrollment Program, DEP)](ios-device-enrollment-program-in-microsoft-intune.md) oder des Tools Apple Configurator, das auf einem Mac-Computer für die [direkte](ios-direct-enrollment-in-microsoft-intune.md) Registrierung oder die Registrierung mit dem [Setup-Assistenten](ios-setup-assistant-enrollment-in-microsoft-intune.md) ausgeführt wird.

[Registrieren firmeneigener iOS-Geräte](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Geräteregistrierungsmanager
Mit Intune können Organisationen eine große Anzahl mobiler Geräte mit einem einzigen Benutzerkonto verwalten, dem so genannten Geräteregistrierungsmanager-Kontos. Nach dem Erstellen eines Geräteregistrierungsmanager-Kontos kann dieses Konto von einem Manager zum Registrieren von mehr als den standardmäßig zulässigen fünf Geräten verwendet werden, die ein normaler Benutzer registrieren darf. Das Registrieren von Geräten mit einem Geräteregistrierungsmanager funktioniert nur für Geräte, die nicht von einem bestimmten Benutzer verwendet. Diese Geräte eignen sich z. B. für POS- oder -Hilfsprogramm-Apps, sind aber ungeeignet für Benutzer, die Zugriff auf E-Mail oder Unternehmensressourcen benötigen.

[Registrieren von firmeneigenen Geräten mit dem Geräteregistrierungs-Manager](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## Registrieren von unternehmenseigenen Windows 10-Desktops

Wenn Ihre Organisation über Azure Active Directory Premium (AADP) oder die Enterprise Management Suite (EMS) verfügt können Sie [Windows 10 für Unternehmen registrieren](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview). Die Geräte werden automatisch als „unternehmenseigen“ gekennzeichnet, wenn Benutzer ihr Geschäfts-, Schul- oder Unikonto hinzufügen.

## Identifizieren von Geräten als unternehmenseigen

Unternehmenseigene Geräte werden in Gerätelisten unter **Besitz** als **Unternehmen** geführt. Geräte können auf folgende Arten als unternehmenseigen identifiziert werden:

 - [Registriert über den Geräteregistrierungs-Manager](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)
 - Registriert über das [Geräteregistrierungsprogramm](ios-device-enrollment-program-in-microsoft-intune.md) von Apple oder den [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md)
 - [Vorabdeklarieren von Geräten mit IMEI-Nummern](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)
 - [Registrieren von Windows 10-Geräten in Azure Active Directory/Enterprise Management Suite](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview)

### International Mobile Equipment Identity (IMEI)

Eindeutige IMEI-Nummern (International Mobile Equipment Identity) sind allgemeine Geräteeigenschaften für viele Hersteller von mobilen Geräten. Intune-Administratoren können IMEI-Nummern für Geräte importieren, die sich im Besitz des Unternehmens befinden. Wenn das Gerät von Intune verwaltet wird, wird es als unternehmenseigenes Gerät gekennzeichnet.

[Angeben unternehmenseigener Geräte über IMEI-Nummern (International Mobile Equipment Identity)](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)



<!--HONumber=Jul16_HO3-->


