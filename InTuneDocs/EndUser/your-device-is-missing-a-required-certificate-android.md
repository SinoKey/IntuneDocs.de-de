---
title: "Auf Ihrem Gerät ist ein erforderliches Zertifikat nicht vorhanden | Microsoft Intune"
description: 
keywords: 
author: staciebarker
manager: arob98
ms.date: 7/7/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
ROBOTS: noindex,nofollow
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: 61dda32b55e108b340923f4ff2a86163da2971dc


---


# Auf Ihrem Gerät ist ein erforderliches Zertifikat nicht vorhanden


## Auf Ihrem Gerät fehlt ein Zertifikat, das in der Regel auf Ihrem Telefon installiert ist
Wenn Ihr Android-Gerät nicht bei Intune registriert ist und ein Zertifikat fehlt, dass normalerweise auf Ihrem Telefon installiert ist, können Sie sich nicht bei der Android-Unternehmensportal-App anmelden. Wenn Sie versuchen, sich anzumelden, sehen Sie die folgende Meldung:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

So wird dieses Problem behoben und das erforderliche Zertifikat bezogen:

1.  Navigieren Sie in einem Browser zu dieser [Digicert-Zertifikatseite](https://www.digicert.com/digicert-root-certificates.htm).

2.  Suchen Sie das Zertifikat „Baltimore CyberTrust Root“ (https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt), und laden Sie es herunter.

3.  Ziehen Sie vom oberen Rand nach unten, um Ihre Benachrichtigungen zu öffnen, und tippen Sie in der Liste der Benachrichtigungen auf **BaltimoreCyberTrustRoot.crt**.

4.  Übernehmen Sie im Dialogfeld **Zertifikat benennen** den Standardzertifikatnamen.

5. Stellen Sie sicher, dass **Verwendung von Anmeldeinformationen** auf **Für VPN und Apps** festgelegt ist, und tippen Sie dann auf **OK**.

    ![screenshot-certificate-name-dialog-showing-baltimore-certificate-name](./media/andr-cert_install-2-add_cert_name.png)

6. Schließen Sie den Webbrowser und die Unternehmensportal-App.

7. Öffnen Sie die Unternehmensportal-App erneut. Sie sollten sich jetzt bei der Unternehmensportal-App anmelden können. Wenn Sie Hilfe benötigen, wenden Sie sich an Ihren IT-Administrator.

## Auf Ihrem Gerät fehlt ein Zertifikat, das Ihr IT-Administrator benötigt
Wenn Ihr Android-Gerät nicht bei Intune registriert ist und darauf ein Zertifikat fehlt, das Ihr IT-Administrator benötigt, können Sie sich nicht bei der Android-Unternehmensportal-App anmelden. Wenn Sie versuchen, sich anzumelden, sehen Sie die folgende Meldung:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

>[!NOTE]
> Wenn Sie bereits eine „Zertifikat fehlt“-Nachricht gesehen und die Schritte in [Auf Ihrem Gerät fehlt ein Zertifikat, das in der Regel auf Ihrem Telefon installiert ist](#your-device-is-missing-a-certificate-that-usually-comes-installed-on-your-phone) ausgeführt haben, dann ist das OK. Es handelt sich hierbei um eine andere Meldung und ein anderes Zertifikat, also fahren Sie fort, und führen Sie die Schritte in diesem Abschnitt aus, um das fehlende Zertifikat zu erhalten.

Um dieses Problem zu beheben und das erforderliche Zertifikat zu erhalten, müssen Sie zwei Hauptschritte ausführen:

- Identifizieren Sie das fehlende Zertifikat in einem Unternehmens oder Schul-PC.
- Laden Sie das fehlende Zertifikat mit Ihrem Gerät aus dem Internet herunter.

### Identifizieren des fehlenden Zertifikats durch Suche auf einem Unternehmens oder Schul-PC

1. Öffnen Sie auf einem PC den Internet Explorer. Wenn Ihnen kein PC für diesen Zweck zur Verfügung steht, wenden Sie sich an Ihren IT-Administrator. Die Kontaktinformationen Ihres IT-Administrators finden Sie auf der [Unternehmensportal-Website](http://portal.manage.microsoft.com).

2. Öffnen Sie die [Unternehmensportal-Website](http://portal.manage.microsoft.com), und melden Sie sich mit Ihren Geschäfts- oder Schulanmeldeinformationen an.

3. Klicken Sie ganz rechts in der Adressleiste des Browsers, wie unten dargestellt, auf das Symbol, das wie ein Vorhängeschlosssymbol aussieht. Wenn das Vorhängeschlosssymbol nicht angezeigt wird, beenden Sie den Vorgang, und wenden Sie sich an Ihren IT-Administrator. Das Vorhängeschlosssymbol bedeutet, dass Sie sicher angemeldet sind, Sie sollten also nicht fortfahren, solange dieses Symbol nicht angezeigt wird.

    ![screenshot-internet-explorer-address-bar-padlock-symbol](./media/andr-missing-cert-ie-padlock-symbol.png)

4. Klicken Sie auf **Zertifikate anzeigen**.

    ![screenshot-internet-explorer-view-certificates-button-on-website-identification-dialog](./media/andr-missg-cert-ie-view-cert-button.png)

5. Klicken Sie im Dialogfeld **Zertifikat** auf die Registerkarte **Zertifizierungspfad**, und identifizieren Sie das Zertifikat, das Sie aus dem Internet abrufen müssen. Der Name des Zertifikats, das Sie benötigen, befindet sich an der gleichen Position wie der, der im obigen Beispielscreenshot hervorgehoben ist. 

### Herunterladen des fehlenden Zertifikats auf das Android-Gerät und Installation

1. Suchen Sie mithilfe einer Suchmaschine wie Bing oder Google nach dem Namen des fehlenden Zertifikats, das Sie im vorherigen Abschnitt angegeben haben. Das Zertifikat kann mit verschiedenen Erweiterungen wie CRT oder PEM usw. enden.

2. Laden Sie das Stammzertifikat von der Website herunter.

3. Ziehen Sie nach dem Herunterladen des Zertifikats vom oberen Rand Ihres Geräts nach unten, um Ihre Benachrichtigungen zu öffnen, und tippen Sie dann in der Liste der Benachrichtigungen auf den Namen des Zertifikats.

4. Übernehmen Sie im unten angezeigten Dialogfeld **Zertifikat benennen** den Standardzertifikatnamen.

5. Stellen Sie sicher, dass **Verwendung von Anmeldeinformationen** auf **Für VPN und Apps** festgelegt ist, und tippen Sie dann auf **OK**.

    ![screenshot-certificate-name-dialog-showing-certificate-name](./media/andr-missing-cert-cert-name.png)

6. Schließen Sie die Unternehmensportal-App.

7. Öffnen Sie die Unternehmensportal-App erneut. Sie sollten sich jetzt bei der Unternehmensportal-App anmelden können. Wenn Sie Hilfe benötigen, wenden Sie sich an Ihren IT-Administrator.

Wenn die gleiche „Zertifikat fehlt“-Nachricht wie oben gezeigt angezeigt wird, und Sie bereits die Schritte oben ausgeführt haben, bedeutet dies wahrscheinlich, dass Ihr IT-Administrator noch ein anderes Zertifikat benötigt, um Ihnen bei der Installation zu helfen. Wenden Sie sich an Ihren IT-Administrator, und senden Sie dieser Person diesen [Link](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), der die Schritte zum Beheben des Problems enthält. 

### Weitere Informationen:
[Verwenden Ihres Windows-Geräts mit Intune](using-your-windows-device-with-intune.md)


<!--HONumber=Jul16_HO3-->


