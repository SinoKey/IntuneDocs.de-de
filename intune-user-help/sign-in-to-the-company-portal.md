---
title: Anmelden bei der Unternehmensportal-App | Microsoft-Dokumentation
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cfd214bc-f072-4808-af2e-a3cbf7af9bca
searchScope: User help
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 93a08f4c653fe320284821c1532cdbd84d090b2f
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2017
---
# <a name="how-do-i-sign-in-to-the-company-portal-app---user-story-1132123--"></a>Wie melde ich mich bei der Unternehmensportal-App an? <!--User Story 1132123-->

Mit der Unternehmensportal-App erhalten Sie Zugriff auf die Ressourcen Ihres Unternehmens, z.B. E-Mails und geschäftliche Apps. Sie haben zwei Möglichkeiten, sich beim Unternehmensportal anzumelden:

* Mit Ihrer geschäftlichen E-Mail-Adresse und Ihrem Kennwort
* Anmelden über ein anderes Gerät

Die folgenden Screenshots wurden unter iOS gemacht. Die Vorgehensweise auf Android- und Windows-Geräten ist aber nahezu identisch.

## <a name="signing-in-with-your-email-address-and-password"></a>Anmelden mit Ihrer E-Mail-Adresse und Ihrem Passwort

1. Öffnen Sie die Unternehmensportal-App auf dem Gerät, und tippen Sie auf **Anmelden**.

  ![Die Seite für die Anmeldung beim Unternehmensportal mit einem Symbol für eine Person vor der grafischen Darstellung einer Website. Darunter befindet sich die Schaltfläche zum Anmelden. Ein Link am unteren Seitenrand führt zu Informationen von Microsoft zu Datenschutz und Cookies.](/intune/media/cp_ios_aad_signin_after_1704_001.png)

  Sie haben die Unternehmensportal-App noch nicht installiert? Hier finden Sie die Anleitungen für den Download und die Installation unter [iOS](install-and-sign-in-to-the-intune-company-portal-app-ios.md) und [Android](install-the-company-portal-app-android.md).

2. Geben Sie den Namen Ihres **Geschäfts- oder Schulkontos** ein.

  ![Der Benutzer wird nur zur Eingabe der E-Mail-Adresse aufgefordert, nicht zur Eingabe von E-Mail-Adresse und Kennwort im gleichen Bildschirm.](/intune/media/cp_ios_aad_signin_after_1704_002.png)

3. Warten Sie, bis Ihre E-Mail-Adresse akzeptiert wurde, und geben Sie dann Ihr Kennwort ein.

  ![Der Benutzer wird erst zur Eingabe des Kennworts aufgefordert, wenn die E-Mail-Adresse akzeptiert wurde.](/intune/media/cp_ios_aad_signin_after_1704_003.png)

4. Nachdem Ihre Anmeldedaten in der Unternehmensportal-App akzeptiert wurden, werden Sie angemeldet und können auf Ihre Unternehmensressourcen zugreifen.   

  ![Nach Abschluss des Authentifizierungsprozesses meldet sich die Unternehmensportal-App an und zeigt einen entsprechenden Ladebalken an.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

## <a name="signing-in-from-another-device"></a>Anmelden über ein anderes Gerät

Für den Zugriff auf Ihre Unternehmensressourcen können Sie statt einem Kennwort auch ein anderes Gerät verwenden, um zu bestätigen, dass Sie die richtige Person mit den richtigen Zugriffsrechten sind. Wenn in Ihrem Unternehmen der Computerzugriff per Smartcards geregelt wird, müssen Sie sich sehr wahrscheinlich über ein anderes Gerät anmelden.

1. Statt Ihre E-Mail-Adresse einzugeben, klicken Sie unter dem Textfeld für die E-Mail-Adresse auf den Link **Von anderem Gerät aus anmelden**.

  ![Die Seite für die Anmeldung beim Unternehmensportal mit einem Symbol für eine Person vor der grafischen Darstellung einer Website. Darunter befindet sich die Schaltfläche zum Anmelden. Ein Link am unteren Seitenrand führt zu Informationen von Microsoft zu Datenschutz und Cookies.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

2. Sie erhalten einen eindeutigen, einmal gültigen Code für die Anmeldung im Unternehmensportal.

  ![Der Benutzer erhält die Anweisung, mit einem über den Arbeitscomputer bezogenen eindeutigen Passcode zur Seite „aka.ms/devicelogin“ zu wechseln und sich dort mit dem Code anzumelden.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

3. Öffnen Sie auf Ihrem anderen Gerät einen Browser und gehen Sie zu [https://aka.ms/devicelogin](https://aka.ms/devicelogin), um den Code einzugeben.

  ![Ein Bild des Browsers des Benutzers auf dem Arbeitscomputer statt in der Unternehmensportal-App. Die angezeigte Seite „Geräteanmeldung“ fordert den Benutzer auf, den über die Unternehmensportal-App empfangenen Code einzugeben.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

4. Sobald der auf der Seite **Geräteanmeldung** eingegebene Code überprüft wurde, klicken Sie auf __Weiter__, um dem Unternehmensportal die Anmeldung über Ihr anderes Gerät zu erlauben.

  ![Der Benutzer hat den eindeutigen Code in das Feld eingegeben und wurde auf der Seite „Geräteanmeldung“ aufgefordert, zu bestätigen, dass das Intune-Unternehmensportal die App ist, die zur Anmeldung autorisiert werden soll.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

5. Sobald der Code überprüft wurde, können Sie das Fenster schließen.

  ![Eine Bestätigungsseite informiert darüber, dass der Benutzer sich jetzt auf dem Gerät bei der Unternehmensportal-App angemeldet hat und dass diese Seite geschlossen werden kann.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

6. Auf Ihrem eigentlichen Gerät wird nur über die Unternehmensportal-App der Anmeldevorgang eingeleitet.

  ![Nach Abschluss des Authentifizierungsprozesses meldet sich die Unternehmensportal-App Sie an und zeigt einen entsprechenden Ladebalken an.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

Benötigen Sie weitere Unterstützung? Wenden Sie sich an Ihren IT-Administrator. Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](http://portal.manage.microsoft.com).
