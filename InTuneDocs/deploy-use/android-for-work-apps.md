---
title: "Bereitstellen von Apps für Android for Work-Geräte | Microsoft-Dokumentation"
description: "Verwenden Sie dieses Thema zum Synchronisieren und anschließenden Bereitstellen von Apps für Android for Work-Geräte über den Google Play for Work Store."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/6/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd0bbd90-d3fe-4efc-83fd-d1f3f86800d4
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: c3a46f9a8e66a1d7de8878105f5752b17a3857b7


---

# <a name="how-to-deploy-apps-to-android-for-work-devices-with-intune"></a>Bereitstellen von Apps für Android for Work-Geräte mit Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

Apps werden für Android for Work-Geräte anders bereitgestellt als für normale Android-Geräte. Alle Apps, die für Android for Work installiert werden, stammen aus dem Google Play for Work Store. Melden Sie sich beim Store an, suchen Sie nach der gewünschten App, und genehmigen Sie sie.
Anschließend wird die App im Knoten **Per Volumenlizenz erworbene Apps** der Intune-Konsole angezeigt. Ab dann können Sie die Bereitstellung der App auf dieselbe Weise wie bei jeder anderen App durchführen.
Wenn Sie eigene branchenspezifische Apps erstellt haben, können Sie diese ebenfalls bereitstellen. Hierzu müssen Sie sich für ein Google Developer-Konto anmelden, über das Sie Apps in einem privaten Bereich im Google Play Store veröffentlichen und anschließend mit Intune synchronisieren können.

## <a name="before-you-start"></a>Vorbereitung

1. Stellen Sie sicher, dass Sie Intune und Android for Work auf der Registerkarte **Admin** (Verwaltung) der Intune-Konsole so konfiguriert haben, dass beide zusammen funktionieren.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Synchronisieren einer App aus dem Google Play for Work Store


1. Wechseln Sie zum [Google Play for Work Store](https://play.google.com/work). Melden Sie sich mit dem Konto an, das Sie zum Konfigurieren der Verbindung zwischen Intune und Android for Work verwendet haben.
2. Suchen Sie im Store nach der App, die Sie mit Intune bereitstellen möchten.
3. Wählen Sie auf der Seite für die App, die Sie auswählen möchten, die Option **Genehmigen** aus. In diesem Beispiel wurde die Microsoft Excel-App ausgewählt.<br>
  ![Beispiel für das Genehmigen einer App](/intune/deploy-use/media/approve.png)
4. Ein Fenster für die App wird geöffnet, und Sie werden gebeten, der App Berechtigungen zum Durchführen verschiedener Vorgänge zu erteilen. Sie müssen **Genehmigen** auswählen, um den Vorgang fortzusetzen.<br>
  ![Beispiel für das Genehmigen von App-Berechtigungen](/intune/deploy-use/media/approve-app-permissions.png)
5. Nach einer Weile wird eine Bestätigungsmeldung angezeigt, dass die App genehmigt wurde und nun in Ihrer IT-Verwaltungskonsole verfügbar ist.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Veröffentlichen und anschließendes Synchronisieren einer branchenspezifischen App über den Google Play for Work Store

1. Wechseln Sie zur Google Play Developer Console unter [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Melden Sie sich mit dem Konto an, das Sie zum Konfigurieren der Verbindung zwischen Intune und Android for Work verwendet haben. Wenn Sie sich zum ersten Mal anmelden, müssen Sie sich registrieren und eine Gebühr bezahlen, um Mitglied im Google Developer-Programm zu werden.
3. Wählen Sie in der Konsole **Neue Anwendung hinzufügen**.
4. Informationen über Ihre App laden Sie auf dieselbe Weise hoch wie Sie Apps im Google Play Store veröffentlichen. Sie müssen jedoch wie im Folgenden dargestellt die Einstellung **Only make this application available to my organization (<*organization name*>)** (Diese Anwendung nur für meine Organisation (<Name der Organisation>) verfügbar machen) auswählen.<br>
  ![Option, um eine Anwendung nur für die eigene Organisation verfügbar zu machen](/intune/deploy-use/media/restrict.png)<br>
Dadurch wird sichergestellt, dass die Anwendung nur für Ihre Organisation und nicht im öffentlichen Google Play Store verfügbar ist.
Weitere Informationen zum Hochladen und Veröffentlichen von Android-Apps finden Sie in der [Google Developer Console-Hilfe](https://support.google.com/googleplay/android-developer/answer/113469).
5. Wechseln Sie nach dem Veröffentlichen Ihrer App zum [Google Play for Work Store](https://play.google.com/work). Melden Sie sich mit dem Konto an, das Sie zum Konfigurieren der Verbindung zwischen Intune und Android for Work verwendet haben.
6. Prüfen Sie im Knoten **Apps** im Store, ob die veröffentlichte App angezeigt wird. Sie wurde automatisch genehmigt, um mit Intune synchronisiert zu werden.

## <a name="deploy-an-android-for-work-app"></a>Bereitstellen einer Android for Work-App

In der Regel wird Intune zweimal täglich mit dem Google Play for Work Store synchronisiert. Wenn Sie eine App aus dem Store genehmigt haben und diese im Knoten **Per Volumenlizenz erworbene Apps** des Arbeitsbereichs **Apps** nicht angezeigt wird, können Sie wie folgt eine sofortige Synchronisierung erzwingen:

1. Klicken Sie in der [Intune-Administratorkonsole](https://manage.microsoft.com) auf **Verwaltung** > **Verwaltung mobiler Geräte** > **Android for Work**.
2. Wählen Sie auf der Seite **Android for Work Mobile Device Management Setup** (Android for Work-MDM-Einrichtung) die Option **Jetzt synchronisieren** aus.
3. Auf der Seite werden außerdem die Uhrzeit und der Status der letzten Synchronisierung angezeigt.

Wenn die App im Knoten **Per Volumenlizenz erworbene Apps** des Arbeitsbereichs **Apps** angezeigt wird, können Sie [sie wie jede andere App bereitstellen](deploy-apps-in-microsoft-intune.md). Die App kann nur für Benutzergruppen bereitgestellt werden. Derzeit können nur die Aktionen **Erforderlich** und **Deinstallieren** gewählt werden. Ab Oktober 2016 fügen wir für neue Mandanten die Bereitstellungsoption **Verfügbar** hinzu.

Nachdem Sie die App bereitgestellt haben, wird sie auf den vorgesehenen Geräten installiert. Der Benutzer wird nicht zur Genehmigung aufgefordert.



<!--HONumber=Dec16_HO2-->


