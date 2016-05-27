---
# required metadata

title: Auswählen der Methode zum Verwalten von Geräten mit Microsoft Intune | Microsoft Intune
description:
keywords:
author: jeffgilb
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 770aad50-fd7a-4cf1-a793-f95fe47fc3f8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Auswählen der Methode zum Verwalten von Geräten
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] ermöglicht Ihnen das Verwalten einer Vielzahl von Geräten, indem Sie diese beim Dienst *registrieren*. Benutzer können dann über ein *Unternehmensportal* eine Reihe von Vorgängen ausführen, z. B. ihr Gerät registrieren, Apps suchen und installieren, sicherstellen, dass ihr Gerät die Unternehmensrichtlinien erfüllt und sich an ihren IT-Support wenden.

## Methoden zum Verwalten mobiler Geräte
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kann folgende Geräteplattformen verwalten:

- Apple iOS 7.1 und höher
- Google Android 4.0 und höher (einschließlich Samsung KNOX)
- Windows Phone 8.0 und höher
- Windows RT und Windows 8.1 RT
- PCs mit Windows 8.1 und höher
- Mac OS X 10.9 und höher

<div class="alert alert-tip">
  <h5><span class="icon-tip"></span> Tipp</h5>
  <p>Wenn Sie bereits Geräte registriert haben, auf denen eine frühere Version von iOS als die oben genannte unterstützte Version ausgeführt wird, bleiben diese registriert. Überprüfen Sie jedoch die Dokumentation für die einzelnen [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], um sicherzustellen, dass die iOS-Version von dem Feature unterstützt wird.</p>
</div>

[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kann auch die Geräte der Benutzer verwalten (was als „Bring your own device“ bzw. BYOD bezeichnet wird). Es dient auch zum Verwalten von Geräten im Besitz des Unternehmens, z. B. in Szenarien, in denen das Unternehmen eine Liste mit Geräten anbietet, aus denen die Benutzer wählen können ("Choose your own device" oder CYOD).

### Registrieren von Geräten für die Verwaltung
Für Betriebssysteme mobiler Geräte, einschließlich iOS, Android und Windows Phone, müssen Sie die Geräte immer registrieren. Die Methode zum Registrieren von Geräten hängt jedoch von den Anforderungen Ihres Unternehmens ab:

|Registrierungstyp|BYOD|CYOD|Gemeinsam genutzte Geräte mit Managerkonto|Gemeinsam genutzte Geräte ohne Benutzerkonto|
|-------------------|--------|--------|--------------------------------------|----------------------------------------|
|**Beschreibung**|Persönliches, mit Microsoft Intune registriertes Gerät|Firmeneigenes Gerät für einzelnen Benutzer|Firmeneigenes Gerät, das über ein von vielen Benutzern gemeinsam genutztes Managerkonto verwaltet wird|Firmeneigenes, benutzerunabhängiges Gerät, das von vielen Benutzern verwendet wird|
|**Benutzer des Geräts**|Besitzer|Zugewiesener Benutzer|Kein benutzerspezifisches Konto|Kein bestimmter Benutzer|
|**Registriert von**|Besitzer|Administrator|Geräte-Manager|Beliebig|
|**Aufhebung der Registrierung durch**|Besitzer oder Administrator|Administrator|Administrator|Administrator|
|**Berechtigung zum Zurücksetzen**|Besitzer oder Administrator|Administrator|Administrator|Administrator|

<div class="alert alert-tip">
  <h5><span class="icon-tip"></span> Tipp</h5>
  <p>Eine vollständige Liste der Funktionen, die Ihnen durch die Registrierung Ihrer Geräte zur Verfügung stehen, finden Sie unter [Verwaltungsfunktionen für mobile Geräte](mobile-device-management-capabilities-in-microsoft-intune.md).</p>
</div>



## Methoden zum Verwalten von Windows-PCs
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kann Windows-PCs mit Windows Vista und höher mithilfe des Intune-Computerclients verwalten. Für Windows-PCs können Sie jedoch zwischen deren Registrierung und der Installation der [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-PC-Clientsoftware wählen, die einige Funktionen bietet, die beim Registrieren von Geräten nicht verfügbar sind. In den meisten Szenarien registrieren Sie Ihre Windows-Geräte mit Intune, sodass Sie über eine größere Anzahl von Funktionen verfügen können als mit dem Computerclient.

Erwägen Sie die Verwendung des Intune-Computerclients für folgende Optionen:
<ul>
<li>Verwenden einer der aktivierten Funktionen des Microsoft Intune-Computerclients zum Verwalten von Windows-PCs.</li>
<li>Verwalten eines Windows-PCs mit einem Betriebssystem, das für die Registrierung nicht unterstützt wird.</li>
</ul>

<div class="alert alert-tip">
  <h5><span class="icon-tip"></span> Tipp</h5>
  <p>Eine vollständige Liste der Funktionen, die Ihnen durch Installieren des Intune-Computerclients auf unterstützten Windows-PCs zur Verfügung stehen, finden Sie unter [Funktionen für die Windows-PC-Verwaltung](windows-pc-management-capabilities-in-microsoft-intune.md).</p>
</div>

## Exchange ActiveSync-Verwaltung
Sie können Geräte auch mithilfe von Exchange ActiveSync verwalten. Dies erfordert das Installieren von On-Premises Connector oder die Verwendung des integrierten Service to Service Connector, um eine Verbindung mit Exchange Server herzustellen.

Weitere Informationen zu den Hardware- und Softwareanforderungen zur Installation von On-Premises Connector finden Sie unter [Anforderungen für On-Premises Connector](/Intune/network-infrastructure-requirements-for-microsoft-intune.md)..

Informationen zum Verwenden von On-Premises Connector oder Service to Service Connector mit Exchange finden Sie unter [Verwaltung mobiler Geräte mit Exchange ActiveSync und Microsoft Intune](/Intune/get-started/mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)..



## Nächste Schritte
Nachdem Sie einige der Funktionen entdeckt haben, die Sie zum Registrieren Ihrer Geräte mit [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] verwenden können, müssen Sie sich auf die [Registrierung Ihrer Geräte](/Intune/get-started/get-ready-to-enroll-devices-in-microsoft-intune.md) vorbereiten. Nachdem Sie Ihre Geräte registriert haben, können Sie alle Funktionen nutzen, über die Sie in diesem Thema gelesen haben. <!--lindavr: There's a logical flaw in our "get to know/get started" content. You can take the path in this topic or you can take the path in the What to know before your get started topic. And they don't cover the same ground. -->


<!--HONumber=May16_HO1-->


