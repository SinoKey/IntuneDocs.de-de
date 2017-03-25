---
title: "Konfigurieren der Einstellungen von Windows Update for Business – Intune | Intune in Azure (Vorschau) | Microsoft-Dokumentation"
description: "Intune in Azure (Vorschau): Hier erfahren Sie, wie Sie in Intune die Einstellungen von Windows Update for Business konfigurieren, um Updates für Windows 10-Geräte zu steuern."
keywords: 
author: dougeby
ms.author: dougeby
manager: angrobe
ms.date: 03/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 08f659cf-715e-4e10-9ab2-1bac3c6f2366
ms.reviewer: coryfe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 911d2887791cf16d4290c3ac5189aa44086f4603
ms.openlocfilehash: 5e2516611b933bb9c74c2b8dc973f85e1d82237f
ms.lasthandoff: 03/11/2017


---

# <a name="how-to-configure-windows-update-for-business-settings-with-microsoft-intune"></a>Konfigurieren der Einstellungen von Windows Update for Business mit Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="introduction"></a>Einführung
Windows als Dienst ist die neue Methode zur Bereitstellung von Updates für Windows 10. Ab Windows 10 enthalten neue Funktions- und Qualitätsupdates die Inhalte aller früheren Updates. Das bedeutet, dass Ihre Windows 10-Geräte nach der Installation des neuesten Updates vollständig auf dem neuesten Stand sind. Im Gegensatz zu früheren Versionen von Windows müssen Sie nun anstelle eines Teilupdates das gesamte Update installieren.

Mithilfe von Windows Update for Business können Sie die Updateverwaltung vereinfachen, sodass Sie für Gruppen von Geräten keine einzelnen Updates genehmigen müssen. Sie können weiterhin eine Updaterolloutstrategie konfigurieren, um das Risiko in Ihren Umgebungen zu managen und sicherzustellen, dass Updates zur richtigen Zeit installiert werden. Mit Microsoft Intune können Sie Updateeinstellungen auf Geräten konfigurieren und die Updateinstallation zurückstellen. Intune speichert nur die Updaterichtlinienzuweisung, nicht die Updates. Geräte greifen direkt auf Windows Update zu, um die Updates zu beziehen. Intune dient zum Konfigurieren und Verwalten der **Windows 10-Updateringe**. Ein Updatering enthält eine Reihe von Einstellungen, die festlegen, wann und wie Updates für Windows 10 installiert werden. So können Sie beispielsweise Folgendes konfigurieren:

- **Windows 10 Servicing Branch:** Wählen Sie aus, ob Gruppen von Geräten Updates aus „Current Branch“ oder aus „Current Branch for Business“ erhalten sollen.  
- **Zurückstellungseinstellungen:** Konfigurieren Sie Einstellungen für die Zurückstellung von Updates, um Updateinstallationen für Gruppen von Geräten zu verzögern. Dadurch erhalten Sie ein gestaffeltes Updaterollout, dessen Status Sie verfolgen können.
- **Aussetzung:** Verschieben Sie die Installation von Updates, falls im Rahmen des Updaterollouts ein Problem auftreten sollte.
- **Wartungsfenster:** Konfigurieren Sie die Zeiten, in denen Updates installiert werden können.
- **Aktualisierungstyp:** Wählen Sie aus, welche Arten von Updates installiert werden. Beispiele wären etwa Qualitätsupdates, Funktionsupdates oder Treiber.
- **Installationsverhalten:** Konfiguriert, wie das Update installiert wird. Hier können Sie beispielsweise festlegen, ob das Gerät nach der Installation automatisch neu gestartet werden soll.
- **Peerdownloads:** Sie können angeben, ob Sie Peerdownloads konfigurieren möchten. Falls ja, können Geräte das Update von einem anderen Gerät herunterladen, das den Downloadvorgang bereits abgeschlossen hat. Dadurch lässt sich der Downloadprozess beschleunigen.

Die erstellten Updateringe werden Gerätegruppen zugewiesen. Mithilfe von Updateringen können Sie eine auf Ihre Unternehmensanforderungen ausgerichtete Updatestrategie erstellen. Weitere Informationen finden Sie unter [Verwalten von Updates mit Windows Update for Business](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

## <a name="before-you-start"></a>Vorbereitung

- Wenn Sie PCs unter Windows 10 aktualisieren möchten, muss auf diesen mindestens Windows 10 Pro mit dem Windows Anniversary-Update ausgeführt werden.

- Windows Update unterstützt folgende Windows 10-Versionen:
    - Windows 10
    - Windows 10 Team (für Surface Hub-Geräte)

 Geräte unter Windows 10 Mobile und Windows 10 Holographic werden nicht unterstützt.

- Auf Windows-Geräten muss **Feedback und Diagnose** > **Diagnose- und Nutzungsdaten** mindestens auf **Basic** festgelegt sein.

    ![Windows-Einstellung für Diagnose- und Nutzungsdaten](./media/telemetry-basic.png)

    Sie können diese Einstellung entweder manuell konfigurieren oder ein Intune-Geräteeinschränkungsprofil für Windows 10 und höher verwenden. Legen Sie hierzu die Einstellung **Allgemein** > **Übermittlung von Diagnosedaten** mindestens auf **Basic** fest. Weitere Informationen zu Geräteprofilen finden Sie unter [So konfigurieren Sie Einstellungen für Geräteeinschränkungen in Microsoft Intune](/intune-azure/configure-devices/how-to-configure-device-restrictions).

- In der klassischen Intune-Verwaltungskonsole stehen vier Einstellungen zum Steuern des Verhaltens von Softwareupdates zur Verfügung. Diese Einstellungen sind Teil der allgemeinen Konfigurationsrichtlinie für Desktop- und Mobilgeräte unter Windows 10:
    - **Automatische Updates zulassen**
    - **Vorabfeatures zulassen**
    - **Geplanter Installationstag**
    - **Geplante Installationszeit**

  In der klassischen Konsole steht auch eine begrenzte Anzahl anderer Windows 10-Updateeinstellungen im Gerätekonfigurationsprofil zur Verfügung. Falls Sie diese Einstellungen in der klassischen Intune-Verwaltungskonsole konfiguriert haben und zum Azure-Portal migrieren, sollten Sie unbedingt die folgenden Schritte ausführen:

1. Erstellen Sie im Azure-Portal Windows 10-Updateringe mit den erforderlichen Einstellungen. Die Einstellung **Vorabfeatures zulassen** wird im Azure-Portal nicht unterstützt, da sie für die neuesten Windows 10-Builds nicht mehr relevant ist. Die drei anderen Einstellungen können zusammen mit anderen Windows 10-Updateeinstellungen beim Erstellen von Updateringen konfiguriert werden.

  > [!NOTE]
  > In der klassischen Konsole erstellte Windows 10-Updateeinstellungen werden nach der Migration nicht im Azure-Portal angezeigt. Die Einstellungen werden jedoch weiterhin angewendet. Wenn Sie diese Einstellungen migriert haben und die migrierte Richtlinie über das Azure-Portal bearbeiten, werden die Einstellungen aus der Richtlinie entfernt.

2. Löschen Sie die Updateeinstellungen in der klassischen Konsole. Wenn Sie zum Azure-Portal migriert sind und die gleichen Einstellungen einem Updatering hinzufügen, müssen Sie die Einstellungen im klassischen Portal löschen, um potenzielle Richtlinienkonflikte zu vermeiden. Ein Beispiel: Falls die gleiche Einstellung mit unterschiedlichen Werten konfiguriert ist, entsteht ein Konflikt, der sich nicht ohne Weiteres diagnostizieren lässt, da die Einstellung, die in der klassischen Konsole konfiguriert wurde, im Azure-Portal nicht angezeigt wird.

## <a name="how-to-create-and-assign-update-rings"></a>Erstellen und Zuweisen von Updateringen

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Softwareupdates** aus.
4. Wählen Sie auf dem Blatt **Softwareupdates** die Befehlsfolge **Verwalten** > **Windows 10 Update Rings** (Windows 10-Updateringe) aus.
5. Wählen Sie auf dem Blatt mit der Updateringliste die Option **Erstellen** aus.
6. Geben Sie auf dem Blatt **Create Update Ring** (Updatering erstellen) einen Namen und eine optionale Beschreibung für den Updatering an, und wählen Sie anschließend **Einstellungen** aus.
7. Konfigurieren Sie auf dem Blatt **Einstellungen** folgende Informationen:
    - **Servicing Branch**: Legen Sie die Verzweigung fest, für die das Gerät Windows-Updates erhält („Current Branch“ oder „Current Branch for Business“).
    - **Microsoft-Updates**: Wählen Sie aus, ob nach App-Updates von Microsoft Update gesucht werden soll.
    - **Windows drivers** (Windows-Treiber): Wählen Sie aus, ob Windows Update-Treiber bei Updates ausgeschlossen werden sollen.
    - **Automatic update behavior** (Verhalten bei automatischen Updates): Wählen Sie aus, wie das Verhalten bei automatischen Updates verwaltet werden soll, um Updates zu suchen, herunterzuladen und zu installieren. Ausführliche Informationen finden Sie unter [Update/AllowAutoUpdate](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#update-allowautoupdate).
    - **Quality update deferral period (days)** (Zurückstellung von Qualitätsupdates (in Tagen)): Geben Sie an, für wie viele Tage Qualitätsupdates zurückgestellt werden sollen. Der Bezug dieser Qualitätsupdates kann für bis zu 30 Tage (ab Veröffentlichung) zurückgestellt werden.  

      Bei Qualitätsupdates handelt es sich in der Regel um Korrekturen und Verbesserungen für bereits vorhandene Windows-Funktionen. Sie werden üblicherweise am ersten Dienstag jedes Monats veröffentlicht, können von Microsoft jedoch auch zu einem anderen Zeitpunkt veröffentlicht werden. Sie können definieren, ob und wie lange der Bezug von Qualitätsupdates zurückgestellt werden soll, nachdem sie verfügbar geworden sind.
    - **Feature update deferral period (days)** (Zurückstellung von Funktionsupdates (in Tagen)): Geben Sie an, für wie viele Tage Funktionsupdates zurückgestellt werden sollen. Der Bezug dieser Funktionsupdates kann für bis zu 180 Tage (ab Veröffentlichung) zurückgestellt werden.

    Bei Funktionsupdates handelt es sich in der Regel um neue Features für Windows. Nach dem Konfigurieren der Einstellung **Servicing Branch** (**CB** oder **CBB**) können Sie definieren, ob und wie lange der Bezug von Funktionsupdates zurückgestellt werden soll, nachdem sie von Microsoft über Windows Update verfügbar gemacht wurden.

    Beispiel:  
    **„Servicing Branch“ ist auf „CB“ festgelegt und die Zurückstellung mit 30 Tagen konfiguriert:** Angenommen, das Funktionsupdate X wird erstmals im Januar als CB über Windows Update veröffentlicht. In diesem Fall erhält das Gerät das Update erst im Februar (also 30 Tage später).

    **„Servicing Branch“ ist auf „CBB“ festgelegt und die Zurückstellung mit 30 Tagen konfiguriert:** Angenommen, das Funktionsupdate X wird erstmals im Januar als CB über Windows Update veröffentlicht. Vier Monate später (also im April) wird das Funktionsupdate X als CBB veröffentlicht. In diesem Fall erhält das Gerät das Funktionsupdate 30 Tage nach der CBB-Veröffentlichung (also im Mai).

    - **Übermittlungsoptimierung**: Wählen Sie die Methode dafür aus, welche Geräte Windows-Updates herunterladen. Ausführliche Informationen finden Sie unter [DeliveryOptimization/DEDownloadMode](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#deliveryoptimization-dodownloadmode).
8. Klicken Sie abschließend auf **OK** und dann auf dem Blatt **Create Update Ring** (Updatering erstellen) auf **Erstellen**.

Der neue Updatering wird in der Liste mit den Updateringen angezeigt.

1. Wählen Sie zum Zuweisen des Rings in der Liste mit den Updateringen einen Ring aus, und klicken Sie anschließend auf der Registerkarte mit dem Namen des Rings**auf **Zuweisungen**.
2. Wählen Sie auf der nächsten Registerkarte die Option **Gruppen auswählen** aus, und wählen Sie anschließend die Gruppen aus, denen Sie diesen Ring zuweisen möchten.
3. Wählen Sie abschließend **Auswählen** aus, um die Zuweisung abzuschließen.



## <a name="update-compliance-reporting"></a>Updateüberwachungsberichte
Windows 10-Updaterollouts können in der Operations Management Suite (OMS) mithilfe der kostenlosen Updateüberwachung überwacht werden. Ausführliche Informationen finden Sie unter [Monitor Windows Updates with Update Compliance](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor) (Überwachen von Windows-Updates mithilfe der Updateüberwachung). Bei Verwendung dieser Lösung können Sie eine Organisations-ID für jedes Ihrer mit Intune verwalteten Windows 10-Geräte bereitstellen, für das Sie Updateüberwachungsberichte verwenden möchten.

Die Organisations-ID können Sie in der Intune-Konsole mithilfe der OMA-URI-Einstellungen einer benutzerdefinierten Richtlinie konfigurieren. Ausführliche Informationen finden Sie unter [Intune-Richtlinieneinstellungen für Windows 10-Geräte in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).   

Der OMA-URI-Pfad zum Konfigurieren der Organisations-ID lautet „./Vendor/MSFT/DMClient/Provider/ProviderID/CommercialID“. (Hierbei muss die Groß-/Kleinschreibung beachtet werden.)

Unter **OMA-URI-Einstellung hinzufügen oder bearbeiten** können Sie beispielsweise folgende Werte verwenden:

- **Name**: Organisations-ID für die Windows-Analyse
- **Beschreibung**: Konfigurieren der Organisations-ID für Windows-Analyselösungen
- **Datentyp**: Zeichenfolge
- **OMA-URI** (Groß-/Kleinschreibung beachten): ./Vendor/MSFT/DMClient/Provider/ProviderID/CommercialID
- **Wert**: <*Verwenden Sie die GUID, die in Ihrem OMS-Arbeitsbereich auf der Registerkarte „Windows-Telemetrie“ angezeigt wird.*>

![Windows-Einstellung für Diagnose- und Nutzungsdaten](./media/commID.png)

<!--
1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Software Updates**.
4. On the **Software Updates** blade, choose **Overview**. From here you can see general information about the status of any update rings you assigned.
4. On the **Windows 10 Updates** blade, choose **Monitor** > **Update ring deployment for devices**, **Update ring deployment for users**, or **Per-setting deployment state** to view more detailed information about update ring assignments.
-->





## <a name="how-to-pause-updates"></a>Aussetzen von Updates
Sie können für ein Gerät den Bezug von Funktions- oder Qualitätsupdates für einen Zeitraum von bis zu 35 Tagen aussetzen (ab dem Zeitpunkt, ab dem die Updates ausgesetzt wurden). Nach Verstreichen der maximalen Anzahl von Tagen wird die Aussetzung automatisch aufgehoben, und das Gerät sucht bei Windows Update nach geeigneten Updates. Danach können Sie die Updates erneut aussetzen.
1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Softwareupdates** aus.
4. Wählen Sie auf dem Blatt **Softwareupdates** die Befehlsfolge **Verwalten** > **Windows 10 Update Rings** (Windows 10-Updateringe) aus.
5. Wählen Sie auf dem Blatt mit der Updateringliste den auszusetzenden Ring und anschließend **...** > **Qualitätsupdates aussetzen** oder **Funktionsupdates aussetzen** aus (je nachdem, welche Art von Updates Sie aussetzen möchten).

> [!IMPORTANT]
> Wenn Sie einen Aussetzungsbefehl erteilen, geht dieser bei den Geräten ein, wenn sie das nächste Mal mit dem Dienst kommunizieren. Es kann vorkommen, dass die Geräte vor der Kommunikation ein geplantes Update installieren.
> Außerdem gilt: Wenn ein Zielgerät bei Erteilung des Aussetzungsbefehls ausgeschaltet ist, lädt es nach dem Einschalten unter Umständen geplante Updates herunter und installiert sie, bevor es mit Intune kommuniziert.

