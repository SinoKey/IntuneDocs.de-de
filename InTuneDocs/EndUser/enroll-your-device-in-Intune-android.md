---
title: "Registrieren Ihres Android-Geräts bei Intune | Microsoft Intune"
description: 
keywords: 
author: staciebarker
manager: jeffgilb
ms.date: 06/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0bb435b87c937ea118a0794c8332b9a8f268d36e
ms.openlocfilehash: 76cc1a43e09039285be76858155ef22f7b41cf9b


---


# Registrieren Ihres Android-Geräts bei Intune

Wenn Ihr Unternehmen oder Ihre Schule Microsoft Intune verwendet, können Sie Ihr Android-Gerät registrieren, um Zugriff auf Unternehmens-E-Mails, Dateien und weitere Ressourcen zu erhalten. Durch das Registrieren Ihrer Geräte kann Ihre IT-Abteilung diese Geschäfts- oder Schulressourcen verwalten und schützen, Ihnen aber gleichzeitig die Möglichkeit bieten, Ihr bevorzugtes Gerät zu verwenden, um Ihre Arbeit erledigen. Weitere Informationen zur Registrierung finden Sie unter [Was geschieht, wenn ich die Unternehmensportal-App installiere und mein Gerät registriere?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-android.md)

Diese Registrierungsanweisungen sind für Samsung Knox-Geräte mit Android und native Android-Geräte (ohne Samsung Knox) bestimmt. Wenn Sie ein Samsung Knox-Gerät haben, wechseln Sie zu **Einstellungen** &gt; **Info zu Gerät**. Wird „KNOX-Version“ nicht angezeigt, verfügen Sie über ein natives Android-Gerät.

Vor oder nach der Registrierung werden Sie möglicherweise aufgefordert, eine Kategorie auszuwählen, die am besten beschreibt, wie Sie Ihr Gerät nutzen. Der IT-Administrator verwendet diese Kategorie zum Bestimmen der Apps, auf die Sie Zugriff haben.

Sollte beim Versuch der Registrierung Ihres Geräts bei Intune ein Fehler auftreten, können Sie [Registrierungsfehler an Ihren IT-Administrator senden](send-enrollment-errors-to-your-it-administrator-android.md).

**So registrieren Sie Ihr Android-Gerät:**

1.  Installieren Sie die kostenlose Intune-Unternehmensportal-App aus [Google Play](http://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal).

2.  Öffnen Sie die Microsoft Intune-Unternehmensportal-App.

3.  Tippen Sie im Unternehmensportal auf dem **Begrüßungsbildschirm** auf **Anmelden**, und melden Sie sich dann mit Ihrem Geschäfts-, Schul- oder Unikonto an.

    ![android-company-portal-sign-in](./media/and-enroll-0-welcome-screen.png)   

4.  Wenn Ihr IT-Administrator Nutzungsbedingungen des Unternehmens eingerichtet hat, tippen Sie auf **AKZEPTIEREN**, um sie anzunehmen.

    ![android-company-portal-sign-in](./media/and-enroll-3-accept-terms.png)

5.  Wenn Sie Android 6.0 oder höher verwenden, führen Sie diesen Schritt aus. Fahren Sie andernfalls mit dem nächsten Schritt fort. 

    Wenn Ihr IT-Administrator bestimmte Richtlinien eingerichtet hat, werden möglicherweise folgende Meldungen angezeigt:
    -   **Zulassen, dass das Unternehmensportal Telefonanrufe tätigt und verwaltet?**

    ![android-company-portal-sign-in](./media/and-enroll-3a-allow-phone-access.png)

    Wenn diese Meldung angezeigt wird, tippen Sie auf **ZULASSEN**. Sie können ruhig auf „ZULASSEN“ tippen, da **Microsoft niemals Ihre Telefonanrufe tätigt oder verwaltet!** Google steuert den Meldungstext, daher kann er von Microsoft nicht geändert werden. Wenn Sie Zugriff gewähren, erlauben Sie Ihrem Gerät lediglich das Schreiben von Datenprotokollen auf die SD-Karte des Geräts, sodass Sie diese Protokolle mithilfe eines USB-Kabels woanders speichern können.

    Wenn Sie den Zugriff verweigern, wird die Meldung bei Ihrer nächsten Anmeldung beim Unternehmensportal angezeigt. Sie können künftige Meldungen jedoch deaktivieren, indem Sie das Kontrollkästchen **Nicht mehr nachfragen** aktivieren.  Wenn Sie den Zugriff später erlauben möchten, wechseln Sie zu **Einstellungen** &gt; **Apps** &gt; **Unternehmensportal** &gt; **Berechtigungen** &gt; **Telefon**, um die Berechtigung zu aktivieren.

    -   **Zulassen, dass das Unternehmensportal auf Ihre Kontakte zugreift?**

    ![android-company-portal-sign-in](./media/and-enroll-3b-allow-contacts-access.png)

    Wenn diese Meldung angezeigt wird, tippen Sie auf **ZULASSEN**. Sie können ruhig auf „ZULASSEN“ tippen, da **Microsoft niemals auf Ihre Kontakte zugreift!** Google steuert den Meldungstext, daher kann er von Microsoft nicht geändert werden. Wenn Sie Zugriff gewähren, wird der Unternehmensportal-App lediglich das Erstellen, Verwenden und Verwalten Ihres Geschäftskontos erlaubt.

    Wenn Sie den Zugriff verweigern, wird die Meldung beim nächsten Tippen auf **Daten senden** angezeigt. Sie können künftige Meldungen jedoch deaktivieren, indem Sie das Kontrollkästchen **Nicht mehr nachfragen** aktivieren. Wenn Sie den Zugriff später erlauben möchten, wechseln Sie zu **Einstellungen** &gt; **Apps** &gt; **Unternehmensportal** &gt; **Berechtigungen** &gt; **Speicher**, um die Berechtigung zu aktivieren.

6.  Melden Sie sich bei der Unternehmensportal-App mit Ihrem Geschäfts- oder Schulkonto und dem zugehörigen Kennwort an, und tippen Sie auf **Anmelden**.

    ![android-company-portal-sign-in](./media/and-enroll-2-cp-sign-in.png)

7.  Tippen Sie auf dem Bildschirm **Unternehmenszugriff einrichten** auf **BEGINNEN**.

    ![Bildschirm „Unternehmenszugriff einrichten“](./media/and-enroll-4a-comp-access-setup.png)

8.  Lesen Sie auf dem Bildschirm **Gründe für das Registrieren Ihres Geräts**, welche Möglichkeiten Sie haben, wenn Sie Ihr Gerät registrieren, und tippen Sie dann auf **WEITER**.

    ![Gründe für das Registrieren Ihres Geräts](./media/and-enroll-4b-why-enroll.png)

9.  Prüfen Sie in einer Liste, was Ihr IT-Administrator auf Ihrem Gerät anzeigen kann und was nicht, und tippen Sie auf **WEITER**.

    ![Datenschutzeinstellungen](./media/and-enroll-4c-we-care-privacy.png)

10.  Lesen Sie im Bildschirm **Was ist der nächste Schritt?**, was während der Registrierung passiert, und tippen Sie dann auf **REGISTRIEREN**.

    ![Was ist der nächste Schritt?](./media/and-enroll-4d-what-comes-next.png)

11.  Klicken Sie auf dem Bildschirm **Geräteadministrator aktivieren** auf **Aktivieren**.

    ![Bildschirm „Geräteadministrator aktivieren?“](./media/and-enroll-5-activate.png)

12.  Befolgen Sie die Aufforderungen zur Eingabe einer PIN oder eines Kennworts. Wenn Sie bereits eine PIN oder ein Kennwort auf diesem Gerät eingerichtet haben, wird dieser Bildschirm nicht angezeigt, und Sie werden nicht zur Eingabe einer neuen PIN oder eines neuen Kennworts aufgefordert.

    ![Eingeben von PIN oder Kennwort](./media/and-enroll-6-PIN-native.png)

13.  Führen Sie die folgenden Schritte für den verwendeten Gerätetyp aus (natives Android oder Samsung Knox). Wenn Sie ein Samsung Knox-Gerät haben, wechseln Sie zu **Einstellungen** &gt; **Info zu Gerät**. Wird „KNOX-Version“ nicht angezeigt, verfügen Sie über ein natives Android-Gerät.

    -   Natives (nicht Samsung Knox-) Gerät: Tippen Sie im Bildschirm **Zertifikat benennen** auf **OK**, um das Standardzertifikat zu akzeptieren.

    ![Bildschirm „Zertifikat benennen“](./media/and-enroll-7-cert-native.png)

    -   Samsung Knox-Gerät: Akzeptieren Sie die Datenschutzrichtlinie, und tippen Sie auf **BESTÄTIGEN**.

    ![Samsung KNOX-Datenschutzrichtlinie](./media/and-enroll-7-knox-privacy-policy.png)

    Die folgende Meldung wird auf dem Bildschirm angezeigt, während Intune Ihr Gerät registriert.

    ![Bildschirm „Gerät wird registriert“](./media/and-enroll-8-device-enrolling.png)

14. Wenn der Bildschirm **Einrichten des Unternehmenszugriffs** angezeigt wird, tippen Sie auf **WEITER**. Wenn die Meldung angezeigt wird, dass Ihr Gerät nicht kompatibel ist, befolgen Sie die Anweisungen zum Beheben des Problems, und tippen Sie dann auf **WEITER**.

    ![Bildschirm „Unternehmenszugriff einrichten“](./media/and-enroll-9-comp-access-setup.png)  

11. Tippen Sie auf dem Bildschirm **Einrichten des Unternehmenszugriffs abgeschlossen** auf **FERTIG**. Ihr Gerät ist jetzt bei registriert.

    ![Bildschirm „Einrichten des Unternehmenszugriffs abgeschlossen“](./media/and-enroll-10-comp-access-setup-complete.png)

Bevor Sie versuchen, Unternehmens-Apps zu installieren, wechseln Sie zu **Einstellungen** &gt; **Sicherheit**, und aktivieren Sie **Unbekannte Quellen**. Wenn Sie diese Option nicht aktivieren, bevor Sie versuchen, Apps zu installieren, erhalten Sie die Meldung „Installation blockiert. Aus Sicherheitsgründen ist Ihr Gerät so eingestellt, dass die Installation von Apps aus unbekannten Quellen blockiert wird.“ Sie können im Fehlerdialog auf **Einstellungen** tippen, um zur Option **Unbekannte Quellen** zu wechseln.

Benötigen Sie weitere Unterstützung? Wenden Sie sich an Ihren IT-Administrator. Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](http://portal.manage.microsoft.com).

### Weitere Informationen:
[Verwenden Ihres Android-Geräts mit Intune](using-your-android-device-with-intune.md)



<!--HONumber=Jun16_HO4-->


