---
title: "Auf Ihrem Gerät ist ein erforderliches Zertifikat nicht vorhanden | Microsoft-Dokumentation"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 56564589417d074b151383a95eea04a4ba7a22ad


---


# <a name="your-device-is-missing-a-required-certificate"></a>Auf Ihrem Gerät ist ein erforderliches Zertifikat nicht vorhanden


## <a name="your-device-is-missing-a-certificate-that-usually-comes-installed-on-your-phone"></a>Auf Ihrem Gerät fehlt ein Zertifikat, das in der Regel auf Ihrem Telefon installiert ist
Wenn Ihr Android-Gerät nicht bei Intune registriert ist und ein Zertifikat fehlt, dass normalerweise auf Ihrem Telefon installiert ist, können Sie sich nicht bei der Android-Unternehmensportal-App anmelden. Wenn Sie versuchen, sich anzumelden, sehen Sie die folgende Meldung:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

So wird dieses Problem gelöst und das erforderliche Zertifikat bezogen:

1.  Navigieren Sie in einem Browser zu dieser [Digicert-Zertifikatseite](https://www.digicert.com/digicert-root-certificates.htm).

2.  Suchen Sie das Zertifikat „Baltimore CyberTrust Root“ (https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt), und laden Sie es herunter.

3.  Ziehen Sie vom oberen Rand nach unten, um Ihre Benachrichtigungen zu öffnen, und tippen Sie in der Liste der Benachrichtigungen auf **BaltimoreCyberTrustRoot.crt**.

4.  Übernehmen Sie im Dialogfeld **Name the Certificate** (Zertifikat benennen) den Standardzertifikatnamen.

5. Stellen Sie sicher, dass **Verwendung von Anmeldeinformationen** auf **Für VPN und Apps** festgelegt ist, und tippen Sie dann auf **OK**.

    ![screenshot-certificate-name-dialog-showing-baltimore-certificate-name](./media/andr-cert_install-2-add_cert_name.png)

6. Schließen Sie den Webbrowser und die Unternehmensportal-App.

7. Öffnen Sie die Unternehmensportal-App erneut. Sie sollten sich jetzt bei der Unternehmensportal-App anmelden können. Wenn Sie Hilfe benötigen, wenden Sie sich an Ihren IT-Administrator.

## <a name="your-device-is-missing-a-certificate-required-by-your-it-admin"></a>Auf Ihrem Gerät fehlt ein Zertifikat, das Ihr IT-Administrator benötigt
Wenn Ihr Android-Gerät nicht bei Intune registriert ist und darauf ein Zertifikat fehlt, das Ihr IT-Administrator benötigt, können Sie sich nicht bei der Android-Unternehmensportal-App anmelden. Wenn Sie versuchen, sich anzumelden, sehen Sie die folgende Meldung:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

>[!NOTE]
> Wenn Sie bereits eine „Zertifikat fehlt“-Nachricht gesehen und die Schritte in [Auf Ihrem Gerät fehlt ein Zertifikat, das in der Regel auf Ihrem Telefon installiert ist](#your-device-is-missing-a-certificate-that-usually-comes-installed-on-your-phone) ausgeführt haben, dann ist das in Ordnung. Es handelt sich hierbei um eine andere Meldung und ein anderes Zertifikat, also fahren Sie fort, und führen Sie die Schritte in diesem Abschnitt aus, um das fehlende Zertifikat zu erhalten.

Um dieses Problem zu lösen und das erforderliche Zertifikat zu erhalten, müssen Sie zwei Hauptschritte ausführen:

- Identifizieren Sie das fehlende Zertifikat in einem Unternehmens oder Schul-PC.
- Laden Sie das fehlende Zertifikat mit Ihrem Gerät aus dem Internet herunter.

### <a name="identify-the-missing-certificate-by-looking-on-a-company-or-school-pc"></a>Identifizieren des fehlenden Zertifikats durch Suche auf einem Unternehmens oder Schul-PC

1. Öffnen Sie auf einem PC den Internet Explorer. Wenn Ihnen kein PC für diesen Zweck zur Verfügung steht, wenden Sie sich an Ihren IT-Administrator. Die Kontaktinformationen Ihres IT-Administrators finden Sie auf der [Unternehmensportal-Website](http://portal.manage.microsoft.com).

2. Öffnen Sie die [Unternehmensportal-Website](http://portal.manage.microsoft.com), und melden Sie sich mit Ihren Geschäfts- oder Schulanmeldeinformationen an.

3. Wählen Sie ganz rechts in der Adressleiste des Browsers das Symbol aus, das wie ein Vorhängeschloss aussieht, wie im nachstehenden Screenshot dargestellt.

    ![screenshot-internet-explorer-address-bar-padlock-symbol](./media/andr-missing-cert-ie-padlock-symbol.png)

    Wenn das Vorhängeschlosssymbol nicht angezeigt wird, beenden Sie den Vorgang, und wenden Sie sich an Ihren IT-Administrator. Das Vorhängeschlosssymbol bedeutet, dass Sie sicher angemeldet sind, Sie sollten also nicht fortfahren, solange dieses Symbol nicht angezeigt wird.

4. Wählen Sie **Zertifikate anzeigen** aus.

    ![screenshot-internet-explorer-view-certificates-button-on-website-identification-dialog](./media/andr-missg-cert-ie-view-cert-button.png)

5. Wählen Sie im Dialogfeld **Zertifikat** die Registerkarte **Zertifizierungspfad** aus, und identifizieren Sie das Zertifikat, das Sie aus dem Internet abrufen müssen. Der Name des Zertifikats, das Sie benötigen, befindet sich an der gleichen Position wie der, der im vorherigen Beispielscreenshot hervorgehoben ist.

### <a name="download-and-install-the-missing-certificate-on-your-android-mobile-device"></a>Herunterladen des fehlenden Zertifikats auf das Android-Gerät und Installation

1. Suchen Sie mithilfe einer Suchmaschine wie Bing oder Google nach dem Namen des fehlenden Zertifikats, das Sie im vorherigen Abschnitt angegeben haben. Das Zertifikat kann mit verschiedenen Erweiterungen wie CRT oder PEM usw. enden.

2. Laden Sie das Stammzertifikat von der Website herunter.

3. Ziehen Sie nach dem Herunterladen des Zertifikats vom oberen Rand Ihres Geräts nach unten, um Ihre Benachrichtigungen zu öffnen, und tippen Sie dann in der Liste der Benachrichtigungen auf den Namen des Zertifikats.

4. Übernehmen Sie im Dialogfeld **Name the Certificate** (Zertifikat benennen), das im folgenden Screenshot angezeigt wird, den Standardzertifikatnamen.

5. Stellen Sie sicher, dass **Verwendung von Anmeldeinformationen** auf **Für VPN und Apps** festgelegt ist, und tippen Sie dann auf **OK**.

    ![screenshot-certificate-name-dialog-showing-certificate-name](./media/andr-missing-cert-cert-name.png)

6. Schließen Sie die Unternehmensportal-App.

7. Öffnen Sie die Unternehmensportal-App erneut. Sie sollten sich jetzt bei der Unternehmensportal-App anmelden können. Wenn Sie Hilfe benötigen, wenden Sie sich an Ihren IT-Administrator.

Wenn die gleiche „Zertifikat fehlt“-Nachricht wie oben gezeigt angezeigt wird, und Sie den Vorgang oben bereits ausgeführt haben, benötigt Ihr IT-Administrator wahrscheinlich noch ein anderes Zertifikat, um Ihnen bei der Installation zu helfen. Wenden Sie sich an Ihren IT-Administrator, und geben Sie dieser Person diesen Link zu einem Artikelabschnitt über [Android-Probleme](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), in dem Schritte zum Beheben des Problems zu finden sind.



<!--HONumber=Dec16_HO2-->


