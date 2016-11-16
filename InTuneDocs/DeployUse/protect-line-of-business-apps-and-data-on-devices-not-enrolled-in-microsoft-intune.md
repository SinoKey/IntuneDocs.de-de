---
title: "Schützen von Branchen-Apps auf nicht registrierten Geräten | Microsoft Intune"
description: "In diesem Thema wird beschrieben, wie Sie Ihre benutzerdefinierte Reihe von Branchen-Apps vorbereiten können, sodass Sie Verwaltungsrichtlinien für mobile Apps anwenden können, die helfen können, Datenverluste zu verhindern."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00219467-a62e-43b6-954b-3084f54c45ba
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9bf5764d1e1bd73fd62e5033b2309fc8d5a912e4
ms.openlocfilehash: bc5d1b429157e6a6b24f4eb319be50b635466317


---

# <a name="protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune"></a>Schützen von branchenspezifischen Apps und Daten auf nicht in Microsoft Intune registrierten Geräten

Mit Richtlinien zur Verwaltung mobiler Apps (Mobile App Management, MAM) können Sie Unternehmensdaten schützen, indem Aktionen eingeschränkt werden, die zu Datenlecks führen könnten, und Datenzugriffsanforderungen wie die Eingabe einer App-PIN erzwungen werden. Zum Anwenden von MAM-Richtlinien auf branchenspezifische iOS- und Android-Apps müssen Sie die App zunächst mit dem Microsoft Intune App Wrapping-Tool umschließen.  Bei diesem Prozess wird einer mobilen App eine Verwaltungsebene hinzugefügt, ohne dass die zugrunde liegende Anwendung geändert werden muss.  Sobald die App umschlossen ist, können Sie MAM-Richtlinien darauf anwenden und sie an Ihre Endbenutzer verteilen.  

In diesem Thema werden die erforderlichen Schritte zum Anwenden von MAM-Richtlinien auf Apps vorgestellt, auf die auf **nicht verwalteten Geräten im Besitz von Mitarbeitern** und auf Geräten zugegriffen wird, die von einer **Lösung für die Verwaltung von Mobilgeräten (Mobile Device Management, MDM) eines Drittanbieters** verwaltet werden.  Informationen zum Vorbereiten branchenspezifischer Apps, die auf **bei Intune MDM registrierten Geräten** ausgeführt werden, finden Sie unter [Auswählen der Vorbereitung von Apps für die mobile Anwendungsverwaltung mit Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).


##  <a name="step-1-prepare-the-app"></a>Schritt 1: Vorbereiten der App
Ehe Sie MAM-Richtlinien auf eine App anwenden können, müssen Sie die App zunächst mit dem Microsoft Intune App Wrapping-Tool umschließen.  Anweisungen zum Herunterladen und Verwenden des App Wrapping Tools finden Sie auf den folgenden Seiten:

- [Vorbereiten von iOS-Apps für die Verwaltung mobiler Anwendungen mit dem Intune App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)
- [Vorbereiten von Android-Apps für die Verwaltung von mobilen Anwendungen mit dem Intune App Wrapping Tool](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)

>[!IMPORTANT]  
>Diese Version des App Wrapping Tools, die nicht bei Intune registrierte Geräte unterstützt, wird für iOS und in der öffentlichen Vorschau für Android unterstützt. Sie können das Tool aus [diesem GitHub-Repository](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios) für iOS und [diesem GitHub-Repository](https://github.com/msintuneappsdk/intune-app-wrapper-android-preview) für Android herunterladen.

## <a name="step-2-add-the-app"></a>Schritt 2: Hinzufügen der App

Um Ihre branchenspezifische App zu MAM-Richtlinien zuzuordnen, müssen Sie Ihrem Intune-Abonnement/-Mandanten die App-Details wie folgt hinzufügen:

1. Wechseln Sie im [Azure-Portal](https://portal.azure.com/) zu **Mobile Anwendungsverwaltung mit Intune > Einstellungen**, und wählen Sie **Branchenspezifische Apps**.

  ![Screenshot des Blatts „Einstellungen“ mit der Option „Branchenspezifische Apps“](../media/mam-azure-portal-lob-on-settings.png)

2. Wählen Sie auf dem Blatt **Branchenspezifische Apps** die Option **Benutzerdefinierte App hinzufügen** aus.

  ![Screenshot des Blatts „Branchenspezifische Apps“ mit der Schaltfläche „Benutzerdefinierte App hinzufügen“ oben](../media/mam-azure-portal-add-lob-app-action.png)
3.  Geben Sie einen Namen für die App, die Paket-ID in das Feld „App-ID“ und die Plattform (iOS oder Android) an.

  ![Screenshot des Blatts „Benutzerdefinierte App hinzufügen“ ](../media/mam-azure-portal-add-app-details.png) Dieser Schritt dient zum Erstellen einer eindeutigen Auflistung Ihrer App.  Die App wird auch in der Liste der Ziel-Apps für eine MAM-Richtlinie für Ihren Mandanten angezeigt (siehe den nächsten Schritt).

## <a name="step-3-apply-mam-policies"></a>Schritt 3: Anwenden von MAM-Richtlinien
Sobald die App-Metadaten in den Dienst hochgeladen wurden, zeigt die App die Liste mit Apps an.  Sie können jetzt [eine neue Richtlinie erstellen oder eine vorhandene Richtlinie verwenden](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) und sie auf die branchenspezifische App anwenden, die Sie in Schritt 2 hinzugefügt haben.

>[!IMPORTANT]
>Die MAM-Richtlinie muss für die Benutzer erstellt werden, die die umschlossene App verwenden werden.  Benutzer, für die diese Richtlinie nicht bereitgestellt wird, können die App nicht verwenden.


  ![Screenshot des Blatts mit der Zielliste der Apps mit der angezeigten neuen branchenspezifischen App](../media/mam-azure-portal-lob-on-targeted-app-list.png)
## <a name="step-4-distribute-the-app"></a>Schritt 4: Verteilen der App
Sie können Apps für Ihre Endbenutzer wie folgt bereitstellen:
* Für Geräte, die bei einer MDM-Lösung eines Drittanbieters registriert sind, können Sie die Apps über Ihre MDM-Lösung verteilen.
* Für Geräte, die von keiner MDM-Lösung verwaltet werden, benötigen Sie eine benutzerdefinierte Lösung. Endbenutzer müssen die App herunterladen und auf ihrem Gerät installieren.

## <a name="changing-the-metadata"></a>Ändern der Metadaten
Falls Sie App-Details wie den Namen der App oder die Paket-ID ändern müssen, müssen Sie [die App entfernen](#remove-apps) und mit den neuen Metadaten [hinzufügen](#step-2-add-the-app).

##  <a name="remove-apps"></a>Entfernen von Apps
Sie können eine branchenspezifische App aus der App-Liste entfernen.  Dadurch wird die App aus der Liste und die Zuordnung zu MAM-Richtlinien entfernt, ohne dass die App jedoch vom Gerät des Endbenutzers entfernt oder deinstalliert wird.  

1.  Wechseln Sie im [Azure-Portal](https://portal.azure.com/) zu ** Intune-Verwaltung von mobilen Anwendungen > Einstellungen**.  Wählen Sie auf dem Blatt **Einstellungen** den Eintrag **Branchenspezifische Apps**, um die Liste vorhandener Apps anzuzeigen.  
2.  Wählen Sie die App aus, die Sie entfernen möchten, und klicken Sie auf **(...)**, um das Kontextmenü zu öffnen.

  ![Screenshot des Blatts „Branchenspezifische Apps“ mit der Schaltfläche mit den Auslassungszeichen](../media/mam-azure-portal-lob-context-menu.png)
3.  Wählen Sie **Anwendung löschen** aus, um die App zu löschen.

  ![Screenshot des Blatts „Branchenspezifische Apps“ mit der Option „Anwendung löschen“](../media/mam-azure-portal-delete-app.png)

  Dies entfernt Apps aus der Liste der branchenspezifischen Apps und der Zielliste von Apps in der MAM-Richtlinie.



<!--HONumber=Nov16_HO2-->


