---
title: "Auf Ihrem Gerät ist ein erforderliches Zertifikat nicht vorhanden | Microsoft-Dokumentation"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
searchScope:
- User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: 207297601634f390051a6345b96bf09e1d031747
ms.openlocfilehash: 6b37cede797f965b82c067b274517277d8597939
ms.lasthandoff: 01/12/2017

---


# <a name="your-device-is-missing-a-required-certificate"></a>Auf Ihrem Gerät ist ein erforderliches Zertifikat nicht vorhanden

## <a name="whats-a-certificate"></a>Was ist ein Zertifikat?

Die [Kryptografie](https://technet.microsoft.com/en-us/library/cc962030.aspx) ist die Wissenschaft der Verschlüsselung von Informationen. Traditionell wird Kryptografie zur Weitergabe codierter Nachrichten verwendet, um [sicherzustellen, dass die Kommunikation geheim bleibt](https://technet.microsoft.com/en-us/library/cc962019.aspx). In ihrer einfachsten Form werden bei der Kryptografie Buchstaben ersetzt oder vertauscht, um eine nicht lesbare, unverständliche oder verborgene Nachricht zu erstellen. Nur jemand mit einem Decodierungsschlüssel bzw. _Zertifikat_ kann die codierte Nachricht wieder in ihre ursprüngliche, lesbare Form umwandeln. Ihr Android-Gerät verwendet Zertifikate für Intune, um sicherzustellen, dass die Kommunikation zwischen Ihrem Gerät und Ihren Organisationsressourcen – z.B. E-Mails oder Dokumenten – während der drahtlosen Übertragung vom einen bis zum anderen Ende sicher und geschützt ist.

## <a name="fixing-certificate-issues"></a>Beheben von Problemen mit Zertifikaten

Wenn Ihr Android-Gerät nicht bei Intune registriert ist und ein bestimmtes Zertifikat fehlt, das vom IT-Administrator als erforderlich festgelegt wurde, können Sie sich nicht bei der Unternehmensportal-App anmelden. Wenn Sie versuchen, sich anzumelden, sehen Sie die folgende Meldung:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

Zunächst sollten Sie ermitteln, ob auf Ihrem Gerät [ein Zertifikat fehlt, das normalerweise auf dem Gerät vorinstalliert ist](your-device-is-missing-a-preinstalled-certificate-android.md).

Wenn dies nicht funktioniert, fordert der IT-Administrator Sie möglicherweise auf[ein zweites Zertifikat zu installieren, um die Sicherheit zu erhöhen](your-device-is-missing-an-IT-required-certificate-android.md).

Benötigen Sie weitere Unterstützung? Wenden Sie sich an Ihren IT-Administrator. Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](http://portal.manage.microsoft.com).

