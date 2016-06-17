---
# required metadata

title: Auf Ihrem Gerät ist ein erforderliches Zertifikat nicht vorhanden | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 05/31/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: arnab
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Auf Ihrem Gerät ist ein erforderliches Zertifikat nicht vorhanden
Wenn Ihr Android-Gerät nicht bei Intune registriert ist und ein Zertifikat fehlt, dass normalerweise auf Ihrem Telefon installiert ist, können Sie sich nicht bei der Android-Unternehmensportal-App anmelden. Wenn Sie versuchen, sich anzumelden, sehen Sie die folgende Meldung:

![andr-cert-install-cert-missing](./media/andr-cert_install-1-cert_missing.png)

So wird dieses Problem behoben und das erforderliche Zertifikat bezogen:

1.  Navigieren Sie in einem Browser zu dieser [Digicert-Zertifikatseite](https://www.digicert.com/digicert-root-certificates.htm).

2.  Suchen Sie das Zertifikat „Baltimore CyberTrust Root“ (https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt), und laden Sie es herunter.

3.  Ziehen Sie vom oberen Rand nach unten, um Ihre Benachrichtigungen zu öffnen, und tippen Sie in der Liste der Benachrichtigungen auf **BaltimoreCyberTrustRoot.crt**.

4.  Übernehmen Sie im Dialogfeld **Zertifikat benennen** den Standardzertifikatnamen.

5. Stellen Sie sicher, dass **Verwendung von Anmeldeinformationen** auf **Für VPN und Apps** festgelegt ist, und tippen Sie dann auf **OK**.

    ![andr-cert-install-add-cert-name](./media/andr-cert_install-2-add_cert_name.png)

6. Schließen Sie den Webbrowser und die Unternehmensportal-App.

7. Öffnen Sie die Unternehmensportal-App erneut. Sie sollten sich jetzt bei der Unternehmensportal-App anmelden können. Wenn Sie Hilfe benötigen, wenden Sie sich an Ihren IT-Administrator.

Benötigen Sie weitere Unterstützung? Wenden Sie sich an Ihren IT-Administrator. Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](http://portal.manage.microsoft.com).

<!--HONumber=Jun16_HO2-->


