---
title: Einrichten der Android-Verwaltung | Microsoft-Dokumentation
description: "Aktivieren Sie die Verwaltung mobiler Geräte (Mobile Device Management, MDM) für Android- und KNOX Standard-Geräte mit Microsoft Intune."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbe5cad1-3e0d-41a9-966b-738156089700
ms.reviewer: lacranda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 26ddc03985ab8a4959a1d2c9a47e77f042ab9310
ms.openlocfilehash: 6b74c09c37970429d3eaa571db655854d592a2fe


---

# <a name="set-up-android-device-management"></a>Einrichten der Android-Geräteverwaltung

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Als Intune-Administrator können Sie die Verwaltung von Android-Geräten, einschließlich Samsung KNOX Standard-Geräten, über das Unternehmensportal aktivieren. Benutzer können ihre Geräte anschließend über die Unternehmensportal-App registrieren, die in Google Play zur Verfügung steht.

1.  **Einrichten von Intune**<br>
    Wenn nicht bereits geschehen, bereiten Sie die Verwaltung mobiler Geräte durch [Festlegen der Autorität für die Verwaltung mobiler Geräte](prerequisites-for-enrollment.md#step-2-set-mdm-authority) auf **Microsoft Intune** und Einrichten von MDM vor.

2.  **Android-Registrierung aktiviert**<br>
    Um die Registrierung mobiler Android-Geräte zu ermöglichen, sind keine weiteren Konfigurationen in der Intune-Konsole erforderlich.

3.  **Benutzern erklären, wie sie ihre Geräte registrieren, um auf Unternehmensressourcen zugreifen zu können**

    Registrierungsanleitungen für Endbenutzer finden Sie unter [Registrieren Ihres Android-Geräts bei Intune](../enduser/enroll-your-device-in-intune-android.md). Im Laufe des Registrierungsprozesses werden Benutzer darüber informiert, was sie erwarten können und was IT-Administratoren auf ihren Geräten sehen können und was nicht.

    Informationen zu anderen Endbenutzeraufgaben finden Sie in den folgenden Artikeln:
  - [Ressourcen zu Endbenutzerszenarios in Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
  - [Endbenutzer-Leitfaden für Android-Geräte](../enduser/using-your-android-device-with-intune.md)

Da der Google Play Store in China nicht verfügbar ist, müssen Android-Geräte das Unternehmensportal von chinesischen App-Marktplätzen beziehen. Die Unternehmensportal-App für Android wird in den folgenden Stores zum Download zur Verfügung stehen:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

Die Unternehmensportal-App für Android verwendet Google Play Services für die Kommunikation mit dem Microsoft Intune-Dienst. Da Google Play Services in China noch nicht verfügbar sind, kann die Ausführung der folgenden Aufgaben bis zu 8 Stunden dauern. 

|Intune-Administratorkonsole| Intune-Unternehmensportal-App für Android |Intune Unternehmensportalwebsite|   
|---|---|---|
|Vollständiges Zurücksetzen| Entfernen eines Remotegeräts| Entfernen eines Geräts (lokal und remote)|
|Selektives Zurücksetzen| Zurücksetzen eines Geräts| Zurücksetzen eines Geräts|
|Bereitstellung neuer oder aktualisierter Apps| Installieren von verfügbaren Branchen-Apps| Zurücksetzen der Gerätekennung|
|Remotesperre|||
|Zurücksetzen der Kennung|||

### <a name="see-also"></a>Weitere Informationen:
[Voraussetzungen für die Registrierung von Geräten in Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Jan17_HO1-->


