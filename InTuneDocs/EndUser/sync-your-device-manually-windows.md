---
title: "Manuelles Synchronisieren des Windows-Geräts | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 443c6de7-5187-4dc4-b844-6085a0c659bd
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9ddbcde20fac83289c4622f69538ff00fa0cb65b
ms.openlocfilehash: 2fad0ea18485290a513d175fecf0a4947786e5eb


---


# <a name="sync-your-windows-device-manually"></a>Manuelles Synchronisieren des Windows-Geräts
Wenn die Installation der App zu lange dauert, können Sie versuchen, Ihr Windows-Gerät manuell zu synchronisieren. Manuelles Synchronisieren kann hilfreich sein, um die Installation zu beschleunigen.

Nur die folgenden Versionen werden unterstützt. Wenn Ihr Gerät nicht aufgeführt ist, wird die Synchronisierung nicht unterstützt. Befolgen Sie dazu die Anweisungen, die dem Typ Ihres Geräts entsprechen.

* [Windows 10 Mobile](#windows-10-mobile)
* [Windows 10 Desktop](#windows-10-desktop)
* [Windows Phone 8.1](#windows-phone-8-1)


## <a name="windows-10-mobile"></a>Windows 10 Mobile
So synchronisieren Sie Ihr Windows 10 Mobile-Gerät manuell, um eine langsame App-Installation zu beschleunigen:

1. Wechseln Sie zu **Alle Apps** > **Einstellungen** > **Konten**.

    ![Auswählen von Konten auf dem Bildschirm „Einstellungen“](./media/win10m-sync-1-settings-accounts.png)

2. Wählen Sie **Arbeitsplatzzugriff** aus.

    ![Auswählen des Arbeitsplatzzugriffs als den Kontotyp](./media/win10m-sync-2-work-access.png)

3. Wählen Sie unter **Für Geräteverwaltung registrieren** den Namen Ihres Unternehmens, wie unten dargestellt, aus.

    ![Auswählen des Firmennamens für die Geräteverwaltung aus](./media/win10m-sync-3-tap-comp-name.png)

4. Wählen Sie das **Sync**-Symbol aus.

    ![Auswählen des „Sync“-Symbols](./media/win10m-sync-4-tap-sync.png)

    Oben auf dem Bildschirm wird die Meldung „Ihr Konto wird synchronisiert“ angezeigt. Die Schaltfläche **Sync** wird ausgegraut, bis die Synchronisierung des Geräts abgeschlossen ist.

## <a name="windows-10-desktop"></a>Windows 10 Desktop
Es existiert mehr als eine Version von Windows 10, daher gibt es zwei Vorgehensweisen. Um herauszufinden, welche Vorgehensweise Sie verwenden sollten, sehen Sie sich den Screenshot an, und wählen Sie dann die Vorgehensweise aus, die mit der Anzeige auf Ihrem Gerät übereinstimmt. 

1. Wählen Sie die Schaltfläche **Start** und dann **Einstellungen** aus.

    ![Die Schaltfläche „Start“](./media/win10pc-sync-1-start-button.png)

2. Wählen Sie auf der Seite **Einstellungen** die Option **Konten** aus.

    ![Auswählen von Konten auf der Seite „Einstellungen“](./media/win10pc-sync-2-settings-accounts.png)

3. Sehen Sie sich die beiden folgenden Bildschirme an, und suchen Sie denjenigen heraus, der der Anzeige auf Ihrem Gerät entspricht. Befolgen Sie die Schritte, die Sie auf dem Bildschirm Ihres Gerätes sehen.

    Wenn dieser Bildschirm („Zugriff auf Geschäfts-, Schul- oder Unikonto“) angezeigt wird, befolgen Sie die Anleitung unter [Zu befolgende Schritte bei Anzeige von „Zugriff auf Geschäfts-, Schul- oder Unikonto“](#steps-to-follow-if-you-see-access-work-or-school).

    ![Zu befolgende Synchronisierungsschritte bei Anzeige von „Zugriff auf Geschäfts-, Schul- oder Unikonto“](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    Wenn dieser Bildschirm angezeigt wird („Arbeitsplatzzugriff“), befolgen Sie die Schritte unter [Zu befolgende Schritte bei Anzeige von „Arbeitsplatzzugriff“](#steps-to-follow-if-you-see-your-account).

    ![Auswählen des Arbeitsplatzzugriffs als den Kontotyp](./media/win10pc-sync-3-work-access.png) 

### <a name="steps-to-follow-if-you-see-access-work-or-school"></a>Zu befolgende Schritte bei Anzeige von „Zugriff auf Geschäfts-, Schul- oder Unikonto“

1. Wählen Sie auf der Seite **Konten** **Zugriff auf Geschäfts-, Schul- oder Unikonto** aus.

    ![Auswählen von „Zugriff auf Geschäfts-, Schul- oder Unikonto“](./media/w10-enroll-rs1-connect-to-work-or-school.png)

2. Wählen Sie Ihr Geschäfts-, Schul- oder Unikonto aus. Abhängig von der Einrichtung Ihres IT-Administrators werden Ihnen möglicherweise zwei Konten angezeigt, die ähnlich wie im nachstehenden Beispiel aussehen. Neben einem Konto wird eine Aktentasche angezeigt und neben dem anderen das Microsoft-Logo. 

    - Wenn Ihnen das Konto mit der Aktentasche angezeigt wird, wählen Sie es aus, und suchen Sie darunter nach der Schaltfläche **Info**. 
    - Wenn Ihnen nur das Konto mit dem Microsoft-Logo angezeigt wird, wählen Sie es aus, und suchen Sie darunter nach der Schaltfläche **Info**.

    ![Auswählen Ihres Kontonamens neben der Aktentasche oder dem Microsoft-Logo](./media/win10pc-rs1-sync-info-button.png)

3. Wählen Sie die Schaltfläche **Info** aus. Ein Dialogfeld wird geöffnet, das ähnlich wie im folgenden Beispiel aussieht.

    ![Auswählen Ihres Kontonamens neben der Aktentasche oder dem Microsoft-Logo](./media/win10pc-rs1-sync-button.png)

4. Wählen Sie die Schaltfläche **Synchronisieren** aus. Ihr Gerät wird mit Intune synchronisiert werden.

### <a name="steps-to-follow-if-you-see-work-access"></a>Zu befolgende Schritte bei Anzeige von „Arbeitsplatzzugriff“
    
1. Auf der Seite **Konten** wählen Sie **Arbeitsplatzzugriff** aus.

    ![Auswählen des Arbeitsplatzzugriffs als den Kontotyp](./media/win10pc-sync-3-work-access.png)

2. Wählen Sie unter **Für Geräteverwaltung registrieren** den Namen Ihres Unternehmens aus.

    ![Auswählen des Firmennamens für die Geräteverwaltung aus](./media/win10pc-sync-4-tap-com-name.png)

3. Wählen Sie die Schaltfläche **Synchronisieren** aus.

    ![Auswählen der Schaltfläche „Synchronisieren“](./media/win10pc-sync-5-tap-sync.png)

   Die Schaltfläche wird solange ausgegraut, bis die Synchronisierung fertig ist.

## <a name="windows-phone-81"></a>Windows Phone 8.1
So synchronisieren Sie Ihr Windows Phone 8.1-Gerät manuell, um eine langsame App-Installation zu beschleunigen:

1. Wechseln Sie zu **Alle Apps** > **Einstellungen** > **Arbeitsplatz**.

    ![Liste der Einstellungen](./media/wp81-1-sync-settings-workplace.png)

2. Wählen Sie den Namen Ihres Unternehmens aus.

    ![Auswählen des Namens des Unternehmens für das Unternehmensbereichskonto](./media/wp81-2-sync-tap-compname.png)

3. Wählen Sie das **Sync**-Symbol aus.

    ![Auswählen des „Sync“-Symbols](./media/wp81-3-sync-tap-sync-button.png)

   Oben auf dem Bildschirm wird die Meldung „Ihr Konto wird synchronisiert“ angezeigt, bis die Synchronisierung des Geräts abgeschlossen ist.

Benötigen Sie weitere Unterstützung? Wenden Sie sich an Ihren IT-Administrator. Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](http://portal.manage.microsoft.com).



<!--HONumber=Nov16_HO1-->


