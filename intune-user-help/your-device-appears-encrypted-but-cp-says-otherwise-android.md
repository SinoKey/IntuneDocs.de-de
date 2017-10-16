---
title: "Ihr Android-Gerät ist anscheinend verschlüsselt"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 09/29/2017
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
ms.openlocfilehash: 208cf6eb2d29ec5458d97d0a4481cec420acc281
ms.sourcegitcommit: 59811bf1183b3ef9c9e81eded634bd0d3124d0bb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2017
---
# <a name="your-android-device-seems-to-be-encrypted-but-company-portal-says-otherwise"></a>Es sieht so aus, als sei Ihr Gerät verschlüsselt, aber das Unternehmensportal sagt etwas anderes

Beim Verschlüsseln eines Geräts werden die darauf enthaltenen Informationen mit einem geheimen Schlüssel verschlüsselt, der nur Ihnen bekannt ist. So wird verhindert, dass unautorisierte Personen darauf zugreifen können. Bei vielen Unternehmen müssen die Benutzer ihre Android-Geräte verschlüsseln, bevor sie auf Unternehmensdateien, E-Mails oder Daten zugreifen können.

## <a name="common-issues"></a>Häufige Probleme

Neuere Versionen von Android, insbesondere ab Version 7.0, fordern eine Startkennung an, um sicherzustellen, dass Ihr Gerät vollständig verschlüsselt ist. Verschiedene Gerätehersteller weisen unterschiedliche Beschreibungen und Stellen für die Startkennung auf. Zumeist wird diese Einstellung als „Sicherer Start“ bezeichnet. 

## <a name="solutions"></a>Lösungen

### <a name="add-a-startup-pin"></a>Hinzufügen einer Start-PIN

Bei bestimmten Android-Geräten müssen Sie eine Start-PIN erstellen, um die Sicherheit Ihres Geräts zu gewährleisten. Es gibt viele Versionen von Android von vielen Herstellern. Sie können versuchen, dieses Problem in den Griff zu bekommen, indem Sie in Ihrem Menüpunkt „Einstellungen“ die Stelle zum Aktivieren dieser Option finden. Auf dem Samsung Galaxy S7 aktivieren Sie beispielsweise „Sicherer Start“ über **Einstellungen** > **Sperrbildschirm und Sicherheit** > **Sicherer Start**.  

### <a name="downgrade-your-version-of-android"></a>Herabstufen Ihrer Android-Version

Falls Ihr Gerät Ihnen die Option gibt, auf Android 6.0+ downzugraden, machen Sie dies. Falls Sie versuchen, Ihr Gerät downzugraden, besteht die Gefahr, dass Daten verloren gehen. Wenden Sie sich andernfalls an die Supportabteilung Ihres Unternehmens, um dieses Problem zu beheben. Entsprechende Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](https://portal.manage.microsoft.com).

## <a name="specific-manufacturer-issues"></a>Spezifische Herstellerprobleme

Einige Android-Geräte mit Version 7.0+ verschlüsseln Daten so, dass sie mit gewissen Android-Plattformstandards nicht kompatibel sind. Diese Geräte werden möglicherweise verschlüsselt angezeigt, selbst wenn sie neu sind. Intune erkennt, dass die Informationen des Geräts durch die Verschlüsselungsmethoden dieser Geräte gefährdet werden. Dieses Risiko entsteht ist in erster Linie durch böswillige Benutzer, die physikalischen Zugriff auf das Gerät haben.

> [!Note]
> Microsoft arbeitet mit Herstellern zusammen, um Probleme zu beheben, die wir beim Testen finden oder die Benutzer uns melden. Dieser Artikel wird aktualisiert, sobald neue Informationen verfügbar sind. 

## <a name="known-devices"></a>Bekannte Geräte

### <a name="known-devices-that-can-be-updated-to-fix-this-issue"></a>Bekannte Geräte, die aktualisiert werden können, um dieses Problem zu beheben

Wenn Sie eines der folgenden Geräte haben, tritt dieses Problem ggf. auf, sofern Sie Ihr Gerät nicht auf die neueste Version von Android aktualisiert haben. Sie können die Updates für diese Geräte installieren, indem Sie zu **Einstellungen** > **Update** navigieren. 

- [Huawei Honor 8](http://consumer.huawei.com/en/support/mobile-phones/honor8_en-sup.htm)
- [Huawei P9](http://consumer.huawei.com/en/phones/p9/)

### <a name="known-devices-that-currently-cannot-be-updated-to-fix-this-issue"></a>Bekannte Geräte, die derzeit nicht aktualisiert werden können, um dieses Problem zu beheben

Bei folgenden Geräten kann dieses Problem nicht behoben werden. Möglicherweise müssen Sie ein anderes Gerät verwenden, um auf Unternehmensressourcen zugreifen zu können. 

- [Huawei Mate 8](http://consumer.huawei.com/en/mobile-phones/mate8/index.htm)
- [Xiaomi Mi-Smartphones](https://xiaomi-mi.com/mi-smartphones/)
