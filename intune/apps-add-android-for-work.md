---
title: "Zuweisen von Apps für Android for Work-Geräte | Microsoft-Dokumentation"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Verwenden Sie dieses Thema zum Synchronisieren und anschließenden Zuweisen von Apps zu Android for Work-Geräten über den Google Play for Work Store."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 49e86ab665d9022739c0330092734ba897ea3b02
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-assign-apps-to-android-for-work-devices-with-intune"></a>Zuweisen von Apps für Android for Work-Geräte mit Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Apps werden zu Android for Work-Geräten anders zugewiesen als zu normalen Android-Geräten. Alle Apps, die für Android for Work installiert werden, stammen aus dem Google Play for Work Store. Melden Sie sich beim Store an, suchen Sie nach der gewünschten App, und genehmigen Sie sie.
Anschließend wird die App im Knoten **Lizenzierte Apps** des Intune-Portals angezeigt. Ab dann können Sie die Zuweisung der App auf dieselbe Weise wie bei jeder anderen App durchführen.

Wenn Sie eigene branchenspezifische Apps erstellt haben, können Sie diese ebenfalls zuweisen. Hierzu müssen Sie sich für ein Google Developer-Konto anmelden, über das Sie Apps in einem privaten Bereich im Google Play Store veröffentlichen und anschließend mit Intune synchronisieren können.

## <a name="before-you-start"></a>Vorbereitung

Stellen Sie sicher, dass Sie Intune und Android for Work für die **Geräteregistrierung** des Intune-Portals so konfiguriert haben, dass beide zusammen funktionieren.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Synchronisieren einer App aus dem Google Play for Work Store


1. Wechseln Sie zum [Google Play for Work Store](https://play.google.com/work). Melden Sie sich mit dem Konto an, das Sie zum Konfigurieren der Verbindung zwischen Intune und Android for Work verwendet haben.
2. Suchen Sie im Store nach der App, die Sie mit Intune zuweisen möchten.
3. Wählen Sie auf der Seite für die App, die Sie auswählen möchten, die Option **Genehmigen** aus. In diesem Beispiel wurde die Microsoft Excel-App ausgewählt.<br>
  ![Beispiel für das Genehmigen einer App](media/approve.png)
4. Ein Fenster für die App wird geöffnet, und Sie werden gebeten, der App Berechtigungen zum Durchführen verschiedener Vorgänge zu erteilen. Sie müssen **Genehmigen** auswählen, um den Vorgang fortzusetzen.<br>
  ![Beispiel für das Genehmigen von App-Berechtigungen](media/approve-app-permissions.png)
5. Nach einer Weile wird eine Bestätigungsmeldung angezeigt, dass die App genehmigt wurde und nun in Ihrer IT-Verwaltungskonsole verfügbar ist.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Veröffentlichen und anschließendes Synchronisieren einer branchenspezifischen App über den Google Play for Work Store

1. Wechseln Sie zur Google Play Developer Console unter [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Melden Sie sich mit dem Konto an, das Sie zum Konfigurieren der Verbindung zwischen Intune und Android for Work verwendet haben. Wenn Sie sich zum ersten Mal anmelden, müssen Sie sich registrieren und eine Gebühr bezahlen, um Mitglied im Google Developer-Programm zu werden.
3. Wählen Sie in der Konsole **Neue Anwendung hinzufügen**.
4. Informationen über Ihre App laden Sie auf dieselbe Weise hoch wie Sie Apps im Google Play Store veröffentlichen. Sie müssen jedoch wie im Folgenden dargestellt die Einstellung **Only make this application available to my organization (<*organization name*>)** (Diese Anwendung nur für meine Organisation (<Name der Organisation>) verfügbar machen) auswählen.<br>
  ![Option, um eine Anwendung nur für die eigene Organisation verfügbar zu machen](media/restrict.png)<br>
Dadurch wird sichergestellt, dass die Anwendung nur für Ihre Organisation und nicht im öffentlichen Google Play Store verfügbar ist.
Weitere Informationen zum Hochladen und Veröffentlichen von Android-Apps finden Sie in der [Google Developer Console-Hilfe](https://support.google.com/googleplay/android-developer/answer/113469).
5. Wechseln Sie nach dem Veröffentlichen Ihrer App zum [Google Play for Work Store](https://play.google.com/work). Melden Sie sich mit dem Konto an, das Sie zum Konfigurieren der Verbindung zwischen Intune und Android for Work verwendet haben.
6. Prüfen Sie im Knoten **Apps** im Store, ob die veröffentlichte App angezeigt wird. Sie wurde automatisch genehmigt, um mit Intune synchronisiert zu werden.

## <a name="assign-an-android-for-work-app"></a>Zuweisen einer Android for Work-App

Wenn Sie eine App aus dem Store genehmigt haben und diese im Knoten **Lizenzierte Apps** für **Mobile Apps** nicht angezeigt wird, können Sie wie folgt eine sofortige Synchronisierung erzwingen:

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Mobile Apps** aus.
4. Wählen Sie in der Workload **Mobile Apps** die Option **Setup** > **Android for Work** aus.
5. Wählen Sie auf dem Blatt „Android for Work“ die Option **Jetzt synchronisieren** aus.
6. Auf der Seite werden außerdem die Uhrzeit und der Status der letzten Synchronisierung angezeigt.

Wenn die App auf dem Knoten **Lizenzierte Apps** der Workload **Mobile Apps** angezeigt wird, können Sie sie [wie jede andere App zuweisen](/intune-azure/manage-apps/deploy-apps). Die App kann nur zu Benutzergruppen zugewiesen werden.

Nachdem Sie die App zugewiesen haben, wird sie auf den vorgesehenen Geräten installiert. Der Benutzer des Geräts wird nicht zur Genehmigung der Installation aufgefordert.

## <a name="manage-app-permissions"></a>Verwalten von App-Berechtigungen
Android for Work erfordert, dass Sie Apps in der verwalteten Play-Webkonsole von Google genehmigen, bevor Sie sie mit Intune synchronisieren und Ihren Benutzern zuweisen.  Da Sie diese Apps mit Android for Work im Hintergrund und automatisch auf die Geräte der Benutzer übertragen können, müssen Sie die App-Berechtigungen im Interesse aller Ihrer Benutzer akzeptieren.  Endbenutzern werden bei der Installation keine App-Berechtigungen angezeigt, daher ist es wichtig, dass Sie diese Berechtigungen lesen und verstehen.

Wenn ein App-Entwickler eine neue Version der App mit aktualisierten Berechtigungen veröffentlicht, werden diese Berechtigungen auch dann nicht automatisch akzeptiert, wenn Sie die vorherigen Berechtigungen genehmigt haben. Geräte, die die alte Version der App ausführen, können sie weiterhin verwenden, aber die App wird nicht aktualisiert, solange die neuen Berechtigungen nicht genehmigt sind. Geräte, auf denen die App nicht installiert ist, können die App nicht installieren, solange Sie die neuen Berechtigungen nicht genehmigt haben.

### <a name="how-to-update-app-permissions"></a>Aktualisieren von Berechtigungen für die App

Besuchen Sie regelmäßig die verwaltete Google Play-Konsole, um zu prüfen, ob neue Berechtigungen vorliegen. Wenn Sie eine App zuweisen und feststellen, dass sie nicht auf Geräten installiert ist, überprüfen Sie mit den folgenden Schritten, ob neue Berechtigungen vorliegen:

1. Besuchen Sie „http://play.google.com/work“.
2. Melden Sie sich mit dem Google-Konto an, das Sie zum Veröffentlichen und Genehmigen der Apps verwendet haben.
3. Rufen Sie die Registerkarte **Aktualisierungen** auf, um festzustellen, ob Apps vorhanden sind, die ein Update erfordern.  Alle aufgelisteten Apps erfordern neue Berechtigungen und werden nicht zugewiesen, solange diese Berechtigungen nicht angewendet wurden.  

