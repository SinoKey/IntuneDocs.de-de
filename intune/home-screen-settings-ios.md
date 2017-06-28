---
title: "Einstellungen des Layouts des Intune-Startbildschirms für iOS-Geräte"
titleSuffix: Intune Azure preview
description: "Intune Azure-Vorschau: Lernen Sie die Einstellungen kennen, mit denen Sie den Start- und Dockbildschirm von iOS-Geräten anpassen können."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6aba4491-afb9-43cd-9ccc-14e6a2a5a3b1
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 7743573ab893b7d54c11e183133fa02368c00779
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---

# <a name="intune-home-screen-layout-settings-for-ios-devices"></a>Einstellungen des Layouts des Intune-Startbildschirms für iOS-Geräte

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Verwenden Sie diese Einstellungen, um das Layout von Apps, Ordnern und Webclips auf dem Start- und Dockbildschirm aller iOS-Geräte zu konfigurieren, denen Sie die Richtlinie zuweisen.

iOS-Geräte, denen Sie das Profil zuweisen, müssen sich im überwachten Modus befinden und iOS 9.3 oder höher ausführen.

1. Wählen Sie auf dem Blatt **Gerätefunktionen** die Option **Layout des Startbildschirms (nur überwacht)**.
2. Wählen Sie auf dem Blatt **Layout des Startbildschirms (nur überwacht)**, ob Sie das Layout des **Docks** oder der **Seiten** konfigurieren möchten.

## <a name="add-items-to-the-dock"></a>Hinzufügen von Elementen zum Dock

Auf dem Blatt **Dock** können Sie dem Dock am unteren Rand des iOS-Bildschirms bis zu 6 Elemente oder Ordner hinzufügen. Allerdings unterstützen viele Geräte weniger Elemente – z.B. unterstützen iPhone-Geräte bis zu 4 Elemente. In diesem Fall werden nur die ersten vier Elemente, die Sie konfiguriert haben, auf dem Gerät angezeigt.

1. Wählen Sie **Hinzufügen**, um dem Dock ein Element hinzuzufügen.
2. Wählen Sie auf dem Blatt **Zeile hinzufügen** aus, ob Sie eine **App** oder einen **Ordner** hinzufügen möchten.
3. Konfigurieren Sie anhand der Informationen in den Abschnitten **Hinzufügen einer App zur Liste** und **Hinzufügen eines Ordners zur Liste** dieses Themas die Apps und Ordner, die im Dock angezeigt werden sollen.
4. Fügen Sie nach Bedarf weitere Elemente hinzu. Wenn Sie fertig sind, klicken Sie auf jedem Blatt auf **OK**, bis wieder das Blatt **Profil erstellen** angezeigt wird. Wählen Sie **Erstellen** aus.

>[!TIP]
> In jedem Startbildschirm und auf allen Seiten können Sie Elemente mittels Ziehen und Ablegen sortieren. 

### <a name="example"></a>Beispiel

In diesem Beispiel haben Sie den Dockbildschirm so konfiguriert, dass nur die Apps „Safari“, „Mail“ und „Stocks“ angezeigt werden. In der folgenden Abbildung wird die App „Mail“ ausgewählt, um ihre Eigenschaften zu veranschaulichen:

![Beispiel für iOS-Dockeinstellungen](http://i.imgur.com/FfFiUcP.png)

Wenn Sie einem iPhone die Richtlinie zuweisen, ist das Ergebnis ein Dock, das etwa so aussieht:

![Beispiel für das iOS-Docklayout eines iPhones](http://i.imgur.com/bAgCe8F.png)

## <a name="add-home-screen-pages"></a>Hinzufügen von Startbildschirmseiten

Fügen Sie die Seiten hinzu, die auf dem Startbildschirm angezeigt werden sollen, und die Apps, die auf jeder Seite angezeigt werden. Apps, die Sie einer Seite hinzufügen, sind in der Reihenfolge, in der sie in der Liste angegeben sind, von links nach rechts angeordnet. Wenn Sie mehr Apps hinzufügen, als auf eine Seite passen, werden die Apps auf eine nachfolgende Seite verschoben.


1. Wählen Sie auf dem Blatt **Seiten** **Hinzufügen**.
2. Geben Sie auf dem Blatt **Zeile hinzufügen** einen **Seitennamen** ein. Dieser Wert wird im Intune-Portal zur Referenz verwendet und auf iOS-Geräten *nicht angezeigt*.
3. Wählen Sie **Hinzufügen** aus, und wählen Sie dann, ob Sie der Seite eine **App** oder einen **Ordner** hinzufügen möchten.
4. Konfigurieren Sie anhand der Informationen in den Abschnitten **Hinzufügen einer App zur Liste** und **Hinzufügen eines Ordners zur Liste** dieses Themas die Apps und Ordner, die auf der Seite angezeigt werden sollen.

### <a name="example"></a>Beispiel

In diesem Beispiel haben Sie eine neue Seite mit dem Namen **Contoso** konfiguriert. Diese Seite zeigt nur die Apps „Find Friends“ und „Settings“ an. In der folgenden Abbildung wird die App „Settings“ ausgewählt, um ihre Eigenschaften zu veranschaulichen:

![Beispiel für Einstellungen des iOS-Startbildschirms](http://i.imgur.com/Jc2OxyX.png)

Wenn Sie einem iPhone die Richtlinie zuweisen, ist das Ergebnis eine Seite, die etwa so aussieht:

![iOS-Gerät mit geändertem Startbildschirm](http://i.imgur.com/Bd37PHa.png)

## <a name="how-to-add-an-app-to-the-list"></a>Hinzufügen einer App zur Liste

1. Geben Sie den **App-Namen** ein. Dieser Wert wird im Intune-Portal zur Referenz verwendet und auf iOS-Geräten *nicht angezeigt*.
2. Geben Sie die **App-Bündel-ID** der App ein, die Sie anzeigen möchten. Hilfe finden Sie weiter unten in diesem Thema unter **Bündel-ID-Referenz für integrierte iOS-Apps**.
3. Klicken Sie auf **OK**, und fahren Sie mit dem Hinzufügen von Elementen bis zu einem Maximum von **6** für das Gerätedock und **60** für eine Geräteseite fort.
4. Klicken Sie zum Abschluss auf **OK**.

## <a name="how-to-add-a-folder-to-the-list"></a>Hinzufügen eines Ordners zur Liste

Apps, die Sie einer Seite in einem Ordner hinzufügen, sind in der Reihenfolge, in der sie in der Liste angegeben sind, von links nach rechts angeordnet. Wenn Sie mehr Apps hinzufügen, als auf eine Seite passen, werden die Apps auf eine nachfolgende Seite verschoben.

1. Geben Sie den **Ordnernamen** ein. Dieser wird Benutzern auf ihren Geräten angezeigt.
2. Wählen Sie **Hinzufügen**, um eine Seite im Ordner zu erstellen. Sie können bis zu 20 Seiten hinzufügen.
3. Geben Sie auf dem Blatt **Zeile hinzufügen** einen Namen für die Seite ein. Dieser Wert wird im Intune-Portal zur Referenz verwendet und auf iOS-Geräten *nicht angezeigt*.
3. Geben Sie den **App-Namen** ein. Dieser Wert wird im Intune-Portal zur Referenz verwendet und auf iOS-Geräten *nicht angezeigt*.
2. Geben Sie die **App-Bündel-ID** der App ein, die Sie anzeigen möchten. Hilfe finden Sie unter **Hinzufügen einer App zur Liste**.
3. Wählen Sie **Hinzufügen** aus. Sie können bis zu 60 Elemente hinzufügen.
4. Klicken Sie zum Abschluss auf **OK**.


## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Bündel-ID-Referenz für integrierte iOS-Apps

Diese Liste zeigt die Bündel-ID einiger gängiger integrierter iOS-Apps. Um die Bündel-ID von anderen Apps zu finden, wenden Sie sich an den Softwarehersteller. 

|||
|-|-|
|App-Name|Bündel-ID|
|App Store|com.apple.AppStore|
|Calculator|com.apple.calculator|
|Kalender|com.apple.mobilecal|
|Kamera|com.apple.camera|
|Clock|com.apple.mobiletimer|
|Compass|com.apple.compass|
|Kontakte|com.apple.MobileAddressBook|
|FaceTime|com.apple.facetime|
|Find Friends|com.apple.mobileme.fmf1|
|Find iPhone|com.apple.mobileme.fmip1|
|Gamecenter|com.apple.gamecenter|
|GarageBand|com.apple.mobilegarageband|
|Integrität|com.apple.Health|
|iBooks|com.apple.iBooks|
|iTunes Store|com.apple.MobileStore|
|iTunes U|com.apple.itunesu|
|Keynote|com.apple.Keynote|
|Mail|com.apple.mobilemail|
|Zuordnungen|com.apple.Maps|
|Nachrichten|com.apple.MobileSMS|
|Musik|com.apple.Music|
|News|com.apple.news|
|Hinweise|com.apple.mobilenotes|
|Zahlen|com.apple.Numbers|
|Seiten|com.apple.Pages|
|Photo Booth|com.apple.Photo-Booth|
|Fotos|com.apple.mobileslideshow|
|Podcasts|com.apple.podcasts|
|Reminders|com.apple.reminders|
|Safari|com.apple.mobilesafari|
|Einstellungen|com.apple.Preferences|
|Stocks|com.apple.stocks|
|Tipps|com.apple.tips|
|Videos|com.apple.videos|
|VoiceMemos|com.apple.VoiceMemos|
|Wallet|com.apple.Passbook|
|Überwachen|com.apple.Bridge|
|Weather|com.apple.weather|

