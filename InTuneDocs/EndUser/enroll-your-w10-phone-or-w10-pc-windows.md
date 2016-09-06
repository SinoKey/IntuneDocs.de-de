---
title: "Registrieren Ihres Windows 10-Geräts bei Intune | Microsoft Intune"
description: "Beschreibt das Registrieren Ihres Windows 10-Geräts (mobil oder Desktop) bei Intune."
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 06/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 36250832-c6fd-4e8d-b681-de735023ebc3
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 02287eb01598c28906045fd8def9e8b4660e3da5
ms.openlocfilehash: 8806231f8d02885a192053a35559694a8984d2f5


---


# Registrieren Ihres Windows 10 Mobile- oder Windows 10-Desktopgeräts bei Intune

Wenn Ihr Unternehmen oder Ihre Schule Microsoft Intune verwendet, können Sie Ihre Geräte registrieren, um Zugriff auf Unternehmens-E-Mails, Dateien und weitere Ressourcen zu erhalten. Durch das Registrieren Ihrer Geräte kann Ihre Organisation Unternehmensdaten schützen. Weitere Informationen zur Registrierung finden Sie unter [Was geschieht, wenn Sie die Unternehmensportal-App installieren und Ihr Gerät bei Intune registrieren?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md) und unter [Was Ihr IT-Administrator auf Ihrem Gerät sehen bzw. nicht sehen kann](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md).


So registrieren Sie Ihr Windows 10 Mobile- oder Windows 10-Desktopgerät:

1.  Wechseln Sie zu **Windows-Einstellungen**, und tippen Sie auf **Konten**.

    ![Einstellungen-Konten](./media/w10-enroll-rs1-settings-accounts.png)

2.  Sehen Sie sich die beiden folgenden Bildschirme an, und suchen Sie denjenigen heraus, der der Anzeige auf Ihrem Gerät entspricht. Befolgen Sie die Schritte, die zu diesem Bildschirm gehören.

    Wenn dieser Bildschirm angezeigt wird, befolgen Sie die Schritte unter [Zu befolgende Schritte bei Anzeige von „Zugriff auf Geschäfts-, Schul- oder Unikonto“](#steps-to-follow-if-you-see-access-work-or-school).

    ![connect-to-work-or-school](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    Wenn dieser Bildschirm angezeigt wird, befolgen Sie die Schritte unter [Zu befolgende Schritte bei Anzeige von „Ihr Konto“](#steps-to-follow-if-you-see-your-account).

    ![Ihr Konto](./media/w10-enroll-2-accounts-your-account.png)

## Zu befolgende Schritte bei Anzeige von „Zugriff auf Geschäfts-, Schul- oder Unikonto“

1.  Tippen Sie auf **Zugriff auf Geschäfts-, Schul- oder Unikonto**.

    ![tap-access-work-school-account](./media/w10-enroll-rs1-connect-to-work-or-school.png)

2.  Geben Sie die E-Mail-Adresse Ihres Geschäfts-, Schul- oder Unikontos ein, und tippen Sie auf **Weiter**.

    ![enter-your-work-or-school-account](./media/w10-enroll-rs1-set-up-work-or-school-account.png)

3. Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto bei Intune an.

    ![Geschäfts-Schul-Konto hinzufügen](./media/w10-enroll-rs1-enter-your-credentials.png)

    In einer Meldung wird angezeigt, dass Ihr Unternehmen oder Ihre Bildungseinrichtung das Gerät registriert.

4. Wenn die Seite **Alles bereit!** angezeigt wird, tippen Sie auf **Schließen**. Der Vorgang ist abgeschlossen.

  ![tap-close-on-you-are-all-set-screen](./media/w10-enroll-rs1-youre-all-set.png)

5. Wenn Sie die Verbindung noch einmal überprüfen möchten, kehren Sie zu den **Einstellungen** zurück. Ihr Geschäfts-, Schul- oder Unikonto wird jetzt aufgeführt.

    ![validate-that-connection-was-set-up-correctly](./media/w10-enroll-rs1-validate-successful-enrollment.png)

Wenn Sie die obigen Schritte ausgeführt haben und trotzdem nicht auf E-Mails und Dateien Ihres Geschäfts-, Schul- oder Unikontos zugreifen können, befolgen Sie die Schritte unter [Schritte zur Problembehandlung bei Anzeige von „Zugriff auf Geschäfts-, Schul- oder Unikonto“](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).


## Zu befolgende Schritte bei Anzeige von „Mein Konto“

1.  Wechseln Sie zu **Windows-Einstellungen**, und tippen Sie auf **Konten**.

    ![go-to-settings-accounts](./media/W10-enroll-1-settings-accounts.png)

2.  Tippen Sie auf **Mein Konto**.

    ![tap-your-account](./media/W10-enroll-2-accounts-your-account.png)

3.  Tippen Sie auf **Geschäfts- oder Schulkonto hinzufügen**.

    ![add-work-or-school-account](./media/w10-enroll-3-add-work-school-acct.png)

4.  Melden Sie sich mit den Anmeldeinformationen Ihres Geschäfts- oder Schulkontos an.

    ![Anmelden](./media/W10-enroll-4-sign-in.png)

Wenn Sie die obigen Schritte ausgeführt haben und trotzdem nicht auf E-Mails, Dateien und andere Daten Ihres Geschäfts-, Schul- oder Unikontos zugreifen können, befolgen Sie die Schritte zur Problembehandlung unter [Schritte zur Problembehandlung bei Anzeige von „Ihr Konto“](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-your-account).

Außerdem wird empfohlen, dass Sie die Unternehmensportal-App installieren, mit der Sie die Unternehmens-Apps einfach bestimmen und abrufen können, die für Sie und Ihre Rolle relevant sind. Abhängig von der Intune-Konfiguration Ihres Unternehmens wurde die Unternehmensportal-App möglicherweise bereits als Teil Ihres Registrierungsprozesses installiert. Um zu prüfen, ob Sie die App haben, suchen Sie in der Liste Ihrer Apps nach **Unternehmensportal**. Wenn das Unternehmensportal nicht in der Liste der Apps angezeigt wird, gehen Sie folgendermaßen vor, um es zu installieren.

1.  Tippen Sie auf **Starten** &gt; **Store**.

2.  Tippen Sie auf **Suchen**, und geben Sie **Unternehmensportal** ein.

3.  Tippen Sie in der Liste der Ergebnisse auf **Unternehmensportal** &gt; **Installieren**.

4.  Tippen Sie auf **Installieren** oder **Kostenlos**. Die angezeigte Option hängt davon ab, wie Ihr Unternehmen die App konfiguriert hat.

Benötigen Sie weitere Unterstützung? Wenden Sie sich an Ihren IT-Administrator. Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](http://portal.manage.microsoft.com).

### Weitere Informationen:
[Verwenden Ihres Windows-Geräts mit Intune](using-your-windows-device-with-intune.md)



<!--HONumber=Aug16_HO3-->


