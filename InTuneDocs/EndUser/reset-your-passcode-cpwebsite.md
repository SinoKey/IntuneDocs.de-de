---
title: "Zurücksetzen Ihrer Kennung über die Unternehmensportalwebsite | Microsoft-Dokumentation"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
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
ms.sourcegitcommit: db5714009d4d0bcdd77be23314e4f2ff4db44b6e
ms.openlocfilehash: 975759db98854c8276999592d6ecdba195438681


---


# <a name="reset-your-device-passcode-from-the-company-portal-website"></a>Zurücksetzen Ihrer Kennung über die Unternehmensportalwebsite

Wenn Sie die PIN oder das Kennwort für ein bei Intune registriertes Gerät verloren haben, können Sie die PIN bzw. das Kennwort über die [Unternehmensportalwebsite](http://portal.manage.microsoft.com) zurücksetzen. Sie können die Unternehmensportal-Website verwenden, um Computer und Geräte zu verwalten, die Sie bei Intune registriert haben. Außerdem können Sie auf dieser die meisten der Aufgaben ausführen, die auch über Ihre Unternehmensportal-App zur Verfügung stehen.

> [!NOTE]
> Die Schaltfläche **Kennung zurücksetzen** wird auf der Unternehmensportal-Website möglicherweise nicht angezeigt, je nachdem, wie Intune von Ihrem IT-Administrator konfiguriert wurde. Das Zurücksetzen der Kennung wird auf Geräten mit Windows 8.1 nicht unterstützt.

So setzen Sie Ihre Kennung zurück

1.  Öffnen Sie die [Unternehmensportal-Website](http://portal.manage.microsoft.com), und wählen Sie das Gerät aus, dessen Kennung Sie zurücksetzen möchten.

2.  Wählen Sie **Kennung zurücksetzen** aus.

    ![Details zum Gerät mit der Schaltfläche „Kennung zurücksetzen“](./media/iwp-screen-with-all-options.png)

3.  Wählen Sie **Abmelden** aus, und melden Sie sich dann mit den Anmeldeinformationen Ihres Geschäfts-, Schul- oder Unikontos wieder an. Sie müssen sich innerhalb von fünf Minuten wieder anmelden.

    ![Zurücksetzungsmeldung mit der Schaltfläche „Abmelden“](./media/iwp-2-sign-out.png)

4.  Wählen Sie **Kennung zurücksetzen** aus.

    ![Meldung, die erklärt, was geschieht, wenn Sie die Kennung zurücksetzen](./media/iwp-3-tap-reset-passcode-after-signin.png)

    In der Tabelle finden Sie Informationen zur Funktionsweise von **Kennung zurücksetzen** auf Ihrem Gerät.

    |Plattform|Unterstützung|
    |------------|-----------|
    |Android|Erstellt eine temporäre, alphanumerische Kennung|
    |iOS|Entfernt die Kennung vom Gerät und erstellt keine neue temporäre Kennung. Wenn Sie Touch ID verwenden, müssen Sie es auf dem Gerät erneut einrichten, da es beim Zurücksetzen der Kennung entfernt wird.|
    |Windows 10 (nur mobile Geräte)|Erstellt eine temporäre, alphanumerische Kennung. Windows Hello wird unterstützt.|
    |Windows Phone 8.1|Erstellt eine temporäre, numerische Kennung.|
    Nachdem Sie Ihr Gerät entsperrt haben, können Sie auf Ihrem Gerät unter **Einstellungen** eine neue Kennung festlegen.

5.  Entsperren Sie Ihr Gerät, und legen Sie eine neue Kennung fest, oder ändern Sie die temporäre Kennung auf Ihrem Gerät unter **Einstellungen**.

    Um eine Benachrichtigung anzuzeigen, die bestätigt, dass Ihr Kennwort erfolgreich zurückgesetzt wurde, klicken Sie auf das Benachrichtigungskennzeichen oben rechts auf der Unternehmensportal-Website.

Benötigen Sie weitere Unterstützung? Wenden Sie sich an Ihren IT-Administrator. Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](http://portal.manage.microsoft.com).



<!--HONumber=Dec16_HO3-->


