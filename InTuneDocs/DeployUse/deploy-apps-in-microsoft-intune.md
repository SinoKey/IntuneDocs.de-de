---
title: Bereitstellen von Apps | Microsoft Intune
description: Die Informationen in diesem Thema helfen Ihnen beim Bereitstellen von Apps mit Microsoft Intune.
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5ef1d2d69acfeea9670324f580d33b191001ffa9
ms.openlocfilehash: 8ab2517a11ecb6ae5395814472dfbb3e83da132b

---
# Bereitstellen von Anwendungen in Microsoft Intune

Die Informationen in diesem Thema helfen Ihnen beim Bereitstellen von Apps mit Microsoft Intune.


## Bereitstellen einer App
In dieser Vorgehensweise stellen Sie die App für ausgewählte Gruppen von Geräten oder für ausgewählte Benutzer bereit.

### So stellen Sie eine App bereit

1. Klicken Sie in der [Microsoft Intune-Administratorkonsole](https://manage.microsoft.com) auf **Apps** &gt; **Apps**, um die Liste der von Ihnen verwalteten Apps anzuzeigen.

2.  Wählen Sie die bereitzustellende App aus, und klicken Sie anschließend auf **Bereitstellung verwalten**.

3.  Wählen Sie im Dialogfeld *&lt;Name der App&gt;* zuerst auf der Seite **Gruppen auswählen** die Benutzer- oder Gerätegruppen aus, für die die App bereitgestellt werden soll.

4.  Konfigurieren Sie auf der Seite **Bereitstellungsaktion** Folgendes:

    - **Genehmigung** – Legen Sie den Status der Bereitstellung fest:
        - **Erforderlich** (die Installation ist obligatorisch)
        - **Verfügbar** (Benutzer installieren die App über das Unternehmensportal nach Bedarf)
        - **Nicht verfügbar** (die App wird nicht installiert und nicht im Unternehmensportal angezeigt)
        - **Deinstallieren** (die App wird von den Zielgeräten deinstalliert).
    - **Deadline** – Geben Sie für erforderliche Installationen an, wann die App bereitgestellt wird. Sie können hier vordefinierte Werte auswählen oder **Benutzerdefiniert** auswählen, um einen eigenen Stichtag zu konfigurieren.

5. Wenn die bereitzustellende App mithilfe einer Richtlinie für die Verwaltung mobiler Anwendungen konfiguriert werden kann, wird die Seite **Verwaltung mobiler Apps** angezeigt. Wählen Sie auf dieser Seite die Richtlinie für die mobile Anwendungsverwaltung aus, die Sie dieser App zuordnen möchten.

    [Informieren Sie sich, welche Microsoft-Apps mit Richtlinien für die Verwaltung mobiler Anwendungen kompatibel sind.](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx)

6. Wenn die bereitzustellende App mit Intune-VPN-Profilen kompatibel ist, wird die Seite **VPN-Profil** angezeigt. Auf dieser Seite können Sie festlegen, dass iOS-Apps mit einem von Ihnen bereitgestellten VPN-Profil verknüpft werden sollen. Die VPN-Verbindung wird automatisch geöffnet, wenn die App gestartet wird. Um ein VPN-Profil verfügbar zu machen, müssen Sie die Profileinstellung **VPN pro App** aktivieren.
 Informationen zum Konfigurieren von VPN-Profilen, einschließlich Unterstützung für das Zuordnen von Profilen zu Apps, finden Sie unter [Unterstützen von Benutzern beim Verbinden mit ihrer Arbeit über VPN-Profile in Microsoft Intune](vpn-connections-in-microsoft-intune.md).

## Beispiel

In diesem Beispiel haben Sie die App als **Verfügbar** für ein iOS-Gerät bereitgestellt.
Die App wird auf den Geräten der Benutzer im Unternehmensportal angezeigt, und von dort aus können die Benutzer sie installieren. In diesem Screenshot wurde z. B. die App „Bing für iOS“ mit dem Installationstyp **Externer Link** zusammen mit einem benutzerdefinierten Symbol bereitgestellt. Außerdem wurde die Option **Als ausgewählte App anzeigen und im Unternehmensportal hervorheben** ausgewählt.  
![Verfügbare iOS-App](./media/available-install-on-iOS.png)

Wenn Sie die App als **Erforderlich** für ein iOS-Gerät bereitgestellt haben, wird der Benutzer benachrichtigt, dass diese App zur Installation bereitsteht. In diesem Screenshot wurde z. B. die App „Arbeitsordner für iOS“ mit dem Installationstyp **Verwaltete iOS-App aus dem App Store** bereitgestellt.  
![Erforderliche iOS-App](./media/iOS-Required-install.PNG)

## Nächste Schritte

Nachdem Sie eine Anwendung bereitgestellt haben, ist es sinnvoll, deren Status zu überwachen. Weitere Informationen finden Sie unter [Überwachen von Apps in Microsoft Intune](monitor-apps-in-microsoft-intune.md).



<!--HONumber=Jul16_HO3-->


