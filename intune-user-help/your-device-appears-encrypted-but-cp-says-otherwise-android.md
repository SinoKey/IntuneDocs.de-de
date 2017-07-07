---
title: "Ihr Android-Gerät ist anscheinend verschlüsselt"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ba593c08-1a78-4013-8525-b45a948772ec
searchScope: User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 269ad7968242f8f5ce7095c9c73347987675e846
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2017
---
# <a name="your-android-device-seems-to-be-encrypted-but-company-portal-says-otherwise"></a>Es sieht so aus, als sei Ihr Gerät verschlüsselt, aber das Unternehmensportal sagt etwas anderes

Beim Verschlüsseln eines Geräts werden die darauf enthaltenen Informationen mit einem geheimen Schlüssel verschlüsselt, der nur Ihnen bekannt ist. So wird verhindert, dass unautorisierte Personen darauf zugreifen. Damit sichergestellt werden kann, dass Ihre Informationen geschützt sind, werden Sie von Ihrer Organisation angewiesen, Ihr Android-Gerät zu schützen, bevor Sie auf Unternehmensdateien, -E-Mails und -daten zugreifen können.

## <a name="common-issues"></a>Häufige Probleme

Neuere Versionen von Android, insbesondere ab Version 7.0, fordern eine Startkennung an, um sicherzustellen, dass Ihr Gerät vollständig verschlüsselt ist. Verschiedene Gerätehersteller weisen unterschiedliche Beschreibungen und Stellen für die Startkennung auf. Zumeist wird sie als „Sicherer Start“ bezeichnet. 

## <a name="solutions"></a>Lösungen

### <a name="add-a-startup-pin"></a>Hinzufügen einer Start-PIN

Bestimmte Android-Geräte fordern das Erstellen einer Start-PIN, um die Sicherheit Ihres Geräts zu gewährleisten. Es gibt viele Versionen von Android von vielen Herstellern. Sie können versuchen, dieses Problem in den Griff zu bekommen, indem Sie in Ihrem Menüpunkt „Einstellungen“ die Stelle zum Aktivieren dieser Option finden. Auf dem Samsung Galaxy S7 aktivieren Sie beispielsweise „Sicherer Start“ über **Einstellungen** > **Sperrbildschirm und Sicherheit** > **Sicherer Start**.  

### <a name="downgrade-your-version-of-android"></a>Herabstufen Ihrer Android-Version
Falls Ihr Gerät Ihnen die Option gibt, auf Android 6.0+ downzugraden, machen Sie dies. Falls Sie versuchen, Ihr Gerät downzugraden, besteht die Gefahr, dass Daten verloren gehen. Wenden Sie sich andernfalls an Ihren IT-Administrator, um dieses Problem zu beheben. Kontaktinformationen zu Ihrem IT-Administrator finden Sie auf der [Unternehmensportal-Website](http://portal.manage.microsoft.com).

## <a name="specific-manufacturer-issues"></a>Spezifische Herstellerprobleme

Einige Android-Geräte mit Version 7.0+ verschlüsseln Daten so, dass sie mit gewissen Android-Plattformstandards nicht kompatibel sind. Diese Geräte sehen standardmäßig so aus, als seien sie verschlüsselt, aber Intune erkennt die verwendeten Methoden als Risiko für die Sicherheit der Daten auf dem Gerät, das von böswilligen Benutzern ausgeht, die physisch Zugang zu dem Gerät haben.

> [!Note]
> Microsoft arbeitet mit Herstellern zusammen, um Probleme zu beheben, die wir beim Testen finden oder die Benutzer uns melden. Wir aktualisieren diesen Artikel, sobald neue Informationen verfügbar sind. 

## <a name="known-devices"></a>Bekannte Geräte

### <a name="known-devices-that-can-be-updated-to-fix-this-issue"></a>Bekannte Geräte, die aktualisiert werden können, um dieses Problem zu beheben

Wenn Sie eines der folgenden Geräte haben, tritt dieses Problem ggf. auf, sofern Sie Ihr Gerät nicht auf die neueste Version von Android aktualisiert haben. Sie können die Updates für diese Geräte installieren, indem Sie zu **Einstellungen** > **Update** navigieren. 

- [Huawei Honor 8](http://consumer.huawei.com/en/support/mobile-phones/honor8_en-sup.htm)
- [Huawei P9](http://consumer.huawei.com/mobile-phones/p9/index.html)

### <a name="known-devices-that-currently-cannot-be-updated-to-fix-this-issue"></a>Bekannte Geräte, die derzeit nicht aktualisiert werden können, um dieses Problem zu beheben

- [Huawei Mate 8](http://consumer.huawei.com/en/mobile-phones/mate8/index.htm)
- [Xiaomi Mi-Smartphones](https://xiaomi-mi.com/mi-smartphones/)
