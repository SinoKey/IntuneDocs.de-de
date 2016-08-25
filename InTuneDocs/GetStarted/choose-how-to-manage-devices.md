---
title: "Auswählen der Methode zum Verwalten von Geräten | Microsoft Intune"
description: "Hier erhalten Sie Informationen zu den verschiedenen Möglichkeiten, mit denen Sie Geräte registrieren und verwalten können."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 770aad50-fd7a-4cf1-a793-f95fe47fc3f8
ms.reviewer: angrobe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c329bd08aaf72ae2acaa03dcb12c911d84b46b4e
ms.openlocfilehash: cfd9df3814d0d306a254a5566155a91ce5d0ca16


---

# Auswählen der Methode zum Verwalten von Geräten
Intune ermöglicht Ihnen das Verwalten einer Vielzahl von Geräten, indem Sie diese beim Dienst *registrieren*. Benutzer können dann über ein *Unternehmensportal* eine Reihe von Vorgängen ausführen, z. B. ihr Gerät registrieren, Apps suchen und installieren, sicherstellen, dass ihr Gerät die Unternehmensrichtlinien erfüllt und sich an ihren IT-Support wenden.

## Methoden zum Verwalten mobiler Geräte
Intune kann folgende Geräteplattformen verwalten:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

> [!NOTE]
> Wenn Sie bereits Geräte registriert haben, auf denen eine frühere Version von iOS als die unterstützte Version ausgeführt wird, bleiben die Geräte registriert. Lesen Sie die Dokumentation, um sicherzustellen, dass die Funktion diese iOS-Version unterstützt.

Intune kann die Geräte der Benutzer verwalten (was als „Bring your own device“ bzw. „BYOD“ bezeichnet wird). Es dient auch zum Verwalten von Geräten im Besitz des Unternehmens, z. B. in Szenarien, in denen das Unternehmen eine Liste mit Geräten anbietet, aus denen die Benutzer wählen können ("Choose your own device" oder CYOD).

### Registrieren von Geräten für die Verwaltung
Für Betriebssysteme mobiler Geräte, einschließlich iOS, Android und Windows Phone, müssen Sie die Geräte immer registrieren. Die Methode zum Registrieren von Geräten hängt von den Anforderungen Ihres Unternehmens ab:

|Registrierungstyp|BYOD|CYOD|Gemeinsam genutzte Geräte mit Managerkonto|Gemeinsam genutzte Geräte ohne Benutzerkonto|
|-------------------|--------|--------|--------------------------------------|----------------------------------------|
|**Beschreibung**|Persönliches, mit Microsoft Intune registriertes Gerät|Firmeneigenes Gerät für einzelnen Benutzer|Firmeneigenes Gerät, das über ein von vielen Benutzern gemeinsam genutztes Managerkonto verwaltet wird|Firmeneigenes, benutzerunabhängiges Gerät, das von vielen Benutzern verwendet wird|
|**Benutzer des Geräts**|Besitzer|Zugewiesener Benutzer|Kein benutzerspezifisches Konto|Kein bestimmter Benutzer|
|**Registriert von**|Besitzer|Administrator|Geräte-Manager|Beliebig|
|**Aufhebung der Registrierung durch**|Besitzer oder Administrator|Plattform |Administrator oder Benutzer|Administrator oder Benutzer|
|**Berechtigung zum Zurücksetzen**|Besitzer oder Administrator|Administrator|Administrator|Administrator|

Weitere Hilfestellungen finden Sie unter [Auswählen der Methode zum Registrieren mobiler Geräte](/intune/get-started/choose-how-to-enroll-devices1).

> [!NOTE]
> Eine vollständige Liste der Funktionen, die Ihnen durch die Registrierung Ihrer Geräte zur Verfügung stehen, finden Sie unter [Verwaltungsfunktionen für mobile Geräte](mobile-device-management-capabilities-in-microsoft-intune.md).

## Methoden zum Verwalten von Windows-PCs
Intune kann Windows-PCs mit Windows Vista und höher mithilfe des Intune-Computerclients verwalten. Für Windows-PCs können Sie jedoch zwischen deren Registrierung und der Installation der Intune-PC-Clientsoftware wählen, die einige Funktionen bietet, die beim Registrieren von Geräten nicht verfügbar sind. In den meisten Szenarien registrieren Sie Ihre Windows-Geräte mit Intune, sodass Sie über eine größere Anzahl von Funktionen verfügen können als mit dem Computerclient.

Erwägen Sie die Verwendung des Intune-Computerclients für folgende Optionen:

- Verwenden einer der aktivierten Funktionen des Microsoft Intune-Computerclients zum Verwalten von Windows-PCs
- Verwalten eines Windows-PCs mit einem Betriebssystem, das für die Registrierung nicht unterstützt wird

> [!NOTE]
> Eine vollständige Liste der Funktionen, die Ihnen durch Installieren des Intune-Computerclients auf unterstützten Windows-PCs zur Verfügung stehen, finden Sie unter [Funktionen für die Windows-PC-Verwaltung](windows-pc-management-capabilities-in-microsoft-intune.md).

## Exchange ActiveSync-Verwaltung
Sie können Geräte auch mithilfe von Exchange ActiveSync verwalten. Dies erfordert das Installieren von On-Premises Connector oder die Verwendung des integrierten Service to Service Connector, um eine Verbindung mit Exchange Server herzustellen.

Weitere Informationen zu den Hardware- und Softwareanforderungen für die Installation des lokalen Connectors finden Sie unter [Anforderungen an den lokalen Connector](/intune/deploy-use/intune-on-premises-exchange-connector#requirements-for-the-on-premises-connector).

Informationen zur Verwendung des lokalen Connectors oder Service to Service Connector mit Exchange finden Sie unter [Verwaltung mobiler Geräte mit Exchange ActiveSync und Microsoft Intune](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune).



## Nächste Schritte
Sie haben nun einige der Funktionen kennengelernt, die Sie zum Registrieren Ihrer Geräte bei [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] verwenden können. Als Nächstes müssen Sie [Ihre Geräte registrieren](/intune/deploy-use/enroll-devices-in-microsoft-intune). Nachdem Sie Ihre Geräte registriert haben, können Sie alle Funktionen nutzen, über die Sie in diesem Thema gelesen haben. <!--lindavr: There's a logical flaw in our "get to know/get started" content. You can take the path in this topic or you can take the path in the What to know before your get started topic. And they don't cover the same ground. -->



<!--HONumber=Aug16_HO3-->


