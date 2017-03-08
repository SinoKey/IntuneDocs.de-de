---
title: "Zurücksetzen Ihrer Kennung über die Website des Unternehmensportals | Microsoft-Dokumentation"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
searchScope:
- User help
ROBOTS: 
ms.reviewer: mamoriss
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: f293901d3865f0b10ed876e83b151cf59a046cba
ms.openlocfilehash: 68725bb63ae2750e89a03c16027f8b4fd9111255
ms.lasthandoff: 02/24/2017


---

# <a name="how-to-reset-your-device-passcode-from-the-company-portal-website"></a>So setzen Sie Ihre Kennung über die Unternehmensportalwebsite zurück

Wenn Sie die PIN oder das Kennwort für ein bei Intune registriertes Gerät verloren haben, können Sie die PIN bzw. das Kennwort über die [Unternehmensportalwebsite](http://portal.manage.microsoft.com) zurücksetzen. Sie können die Unternehmensportal-Website verwenden, um Computer und Geräte zu verwalten, die Sie bei Intune registriert haben. Außerdem können Sie auf dieser die meisten der Aufgaben ausführen, die auch über Ihre Unternehmensportal-App zur Verfügung stehen.

> [!NOTE]
> Es ist möglich, dass Sie die Schaltfläche **Kennung zurücksetzen** auf der Unternehmensportal-Website nicht sehen. Wenn das der Fall ist, wenden Sie sich bitte an Ihren IT-Administrator für Hilfe auf der Unternehmensportal-Website.

So setzen Sie Ihre Kennung zurück

1.    Tippen Sie auf der [Unternehmensportalwebsite](http://portal.manage.microsoft.com) auf die Schaltfläche __Menü__ ![Eine kleine Abbildung der Menü-Schaltfläche, drei horizontal übereinandergestapelte Balken.](/Intune/whats-new/media/CP_hamburger_menu.png), und wählen Sie dann __Meine Geräte__ aus.

2. Wählen Sie auf der Seite __Meine Geräte__ den Namen des Geräts aus, dessen Kennung Sie zurücksetzen möchten.

  ![Ein Screenshot der Seite „Meine Geräte“ mit mehreren nicht identifizierten Geräten oberhalb der Banneraufforderung, nicht aufgelistete Geräte zu registrieren oder nicht identifizierte Geräte zu identifizieren.](./media/macOS_enroll_002_tap_here_banner.png)

3.    Das Gerät wird in einem Popupfenster geöffnet. Wählen Sie die Schaltfläche **Kennung zurücksetzen** aus.

    ![Alle Optionen für ein ausgewähltes Gerät auf der Unternehmensportalwebsite, darunter „Umbenennen“, „Entfernen“, „Gerät zurücksetzen“, „Kennung zurücksetzen“ und „Remotesperre“. ](./media/iwp-screen-with-all-options.png)

4.  Daraufhin öffnet sich ein Banner, in dem Sie dazu aufgefordert werden, zu bestätigen, dass Sie Ihre Kennung zurücksetzen möchten, und dass Ihr Gerät Sie nach dem Vorgang abmeldet. Danach müssen Sie 5 Minuten warten, bevor Sie sich wieder anmelden können.

  ![Das Banner „Kennung zurücksetzen“ mit der Warnung bezüglich des Zurücksetzens der Kennung und der Abmeldung des Benutzers. Die Schaltflächen für Benutzereingaben sind „Abmelden“ und „Abbrechen“.](./media/iwp-reset-passcode-popup.png)

4.  Wählen Sie **Abmelden** aus; danach erhalten Sie eine letzte Meldung, die Sie über das Entfernen der Kennung von dem Gerät informiert. Wenn Sie das Gerät nicht bei sich haben, entfernen Sie die Kennung nicht; ansonsten können Personen, die physisch Zugang zu Ihrem Gerät haben, auf die meisten – persönlichen und geschäftlichen – Daten auf Ihrem Gerät zugreifen.

  ![Das zweite Banner „Kennung zurücksetzen“ mit der Warnung bezüglich des Zurücksetzens der Kennung und des Entfernens der Kennung von dem Gerät. Außerdem informiert es Sie darüber, wie Sie eine neue Kennung in den Geräteeinstellungen festlegen können.](./media/iwp-reset-passcode-2nd-popup.png)


Da unterschiedliche Geräte unterschiedliche Kennungen haben, können Sie sich in der untenstehenden Tabelle darüber informieren, welche Auswirkung das Zurücksetzen der Kennung auf Ihr konkretes Gerät haben kann. 

    |Gerätetyp|Was geschieht beim Zurücksetzen?|
    |------------|-----------|
    |Android|Entfernt die vorhandene Kennung und erstellt eine vorübergehende Kennung mit jeweils Buchstaben und Zahlen|
    |iOS|Entfernt die aktuelle Kennung und erstellt keine neue temporäre Kennung. Wenn Sie den Touch ID-Fingerabdruckscanner zum Öffnen Ihres Geräts oder zum Abwickeln von Käufen nutzen, müssen Sie diesen erneut einrichten.|
    |Windows 10 Mobile|Entfernt die vorhandene Kennung und erstellt eine vorübergehende Kennung mit jeweils Buchstaben und Zahlen. Wenn Sie die Windows Hello-Gesichtserkennung zum Anmelden verwenden, wird diese noch immer unterstützt.|
    |Windows Phone 8.1|Entfernt die vorhandene Kennung und erstellt eine vorübergehende Kennung mit Zahlen.|

    5.  Entsperren Sie Ihr Gerät, und legen Sie eine neue Kennung fest, oder ändern Sie die temporäre Kennung auf Ihrem Gerät unter **Einstellungen**.

    Um eine Benachrichtigung anzuzeigen, die bestätigt, dass Ihr Kennwort erfolgreich zurückgesetzt wurde, klicken Sie auf das Benachrichtigungskennzeichen oben rechts auf der Unternehmensportal-Website.

Benötigen Sie weitere Unterstützung? Wenden Sie sich an Ihren IT-Administrator. Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](http://portal.manage.microsoft.com).

