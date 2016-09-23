---
title: "Zurücksetzen Ihrer Kennung über die Unternehmensportalwebsite | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: bff97f79c6e88bbf55c2c3a259891bb6206b690b
ms.openlocfilehash: 57e3175af6364e7dacbf8941f10292fc9dc58b15


---


# Zurücksetzen Ihrer Kennung über die Unternehmensportalwebsite

Wenn Sie die PIN oder das Kennwort für ein bei Intune registriertes Gerät verloren haben, können Sie die PIN bzw. das Kennwort über die [Unternehmensportalwebsite](http://portal.manage.microsoft.com) zurücksetzen. Die Unternehmensportalwebsite ist eine Website, auf der Sie Computer und Geräte verwalten können, die Sie bei Intune registriert haben. Hier können Sie die meisten der Aufgaben ausführen, die auch über Ihre Unternehmensportal-App zur Verfügung stehen.

> [!NOTE]
> Die Schaltfläche „Kennung zurücksetzen“ wird möglicherweise auf der Unternehmensportal-Website nicht angezeigt, je nachdem, wie Intune von Ihrem IT-Administrator konfiguriert wurde. Das Zurücksetzen der Kennung wird auf Geräten mit Windows 8.1 und Windows RT nicht unterstützt.

So setzen Sie Ihre Kennung zurück

1.  Öffnen Sie die [Unternehmensportal-Website](http://portal.manage.microsoft.com), und tippen Sie auf das Gerät, dessen Kennung Sie zurücksetzen möchten.

2.  Tippen Sie auf **Kennung zurücksetzen**.

    ![resetp-passcode-option-on-company-portal-website](./media/iwp-screen-with-all-options.png)

3.  Tippen Sie auf **Abmelden**, und melden Sie sich dann mit den Anmeldeinformationen Ihres Geschäfts- oder Schulkontos wieder an. Sie müssen sich innerhalb von fünf Minuten wieder anmelden.

    ![sign-out-sign-back-in](./media/iwp-2-sign-out.png)

4.  Tippen Sie auf **Kennung zurücksetzen**.

    ![tap-reset-passcode](./media/iwp-3-tap-reset-passcode-after-signin.png)

    In der Tabelle finden Sie Informationen zur Funktionsweise von „Kennung zurücksetzen“ auf Ihrem Gerät.

    |Plattform|Unterstützung|
    |------------|-----------|
    |Android|Erstellt eine neue, temporäre, alphanumerische Kennung.|
    |iOS|Entfernt die Kennung vom Gerät und erstellt keine neue temporäre Kennung. Wenn Sie Touch ID verwenden, müssen Sie es auf dem Gerät erneut einrichten, da es beim Zurücksetzen der Kennung entfernt wird.|
    |Windows 10 (nur mobile Geräte)|Erstellt eine neue, temporäre, alphanumerische Kennung. Windows Hello wird unterstützt.|
    |Windows Phone 8.1|Erstellt eine neue, temporäre, numerische Kennung.|
    Nachdem Sie Ihr Gerät entsperrt haben, können Sie auf Ihrem Gerät unter **Einstellungen** eine neue Kennung festlegen.

5.  Entsperren Sie Ihr Gerät, und legen Sie eine neue Kennung fest, oder ändern Sie die temporäre Kennung auf Ihrem Gerät unter **Einstellungen**.

    Um eine Benachrichtigung anzuzeigen, die bestätigt, dass Ihr Kennwort erfolgreich zurückgesetzt wurde, klicken Sie auf das Benachrichtigungskennzeichen oben rechts auf der Unternehmensportal-Website.

Benötigen Sie weitere Unterstützung? Wenden Sie sich an Ihren IT-Administrator. Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](http://portal.manage.microsoft.com).





<!--HONumber=Sep16_HO3-->


