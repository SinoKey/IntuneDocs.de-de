---
title: "Informationen zur Remoteverwaltung von Android-Geräten mithilfe von TeamViewer"
titleSuffix: Intune on Azure
description: "In diesem Artikel erfahren Sie, wie Android-Geräte mithilfe von TeamViewer remote verwaltet werden."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 15a005ae2b84c7bd4f913f892089965c10f3b23e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2017
---
# <a name="provide-remote-assistance-for-intune-managed-android-devices"></a>Bereitstellen von Remoteunterstützung für mit Intune verwaltete Android-Geräte

In Intune kann die nicht im Lieferumfang inbegriffene [TeamViewer](https://www.teamviewer.com)-Software verwendet werden, damit Sie Ihren Benutzern, die Android-Geräte ausführen, Remoteunterstützung bieten können. Führen Sie die Einrichtung und die ersten Schritte gemäß den Informationen in diesem Thema durch.

## <a name="before-you-start"></a>Vorbereitung

### <a name="required-permissions"></a>Erforderliche Berechtigungen

Stellen Sie sicher, dass dem Benutzer des Azure-Portals folgende Berechtigungen als [Intune-Rolle](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control) zugewiesen sind:
- Damit der Administrator die TeamViewer Connector-Einstellungen ändern kann, erteilen Sie die Berechtigung **Remoteunterstützung aktualisieren**.
- Damit der Administrator neue Remoteunterstützungseinstellungen initiieren kann, erteilen Sie die Berechtigung **Remoteunterstützung anfordern**. Benutzer mit dieser Berechtigung können die Initiierung einer Sitzung für jeden Benutzer anfordern. Dies wird durch keine Intune-Rollenzuweisungsbereiche beschränkt. Intune-Rollenzuweisungsbereiche beschränken weder Geräte noch Benutzer, für die Remoteunterstützungsanforderungen initiiert werden können.

>[!NOTE]
>Durch die Aktivierung von TeamViewer ermöglichen Sie es dem TeamViewer Connector für Intune TeamViewer-Sitzungen zu erstellen, Active Directory-Daten zu lesen und das Zugriffstoken des TeamViewer-Kontos zu speichern.

### <a name="configure-the-intune-teamviewer-connector"></a>Konfigurieren des TeamViewer Connector für Intune

Bevor Sie die Remoteunterstützung für Android-Geräte bereitstellen können, müssen Sie den TeamViewer Connector für Intune anhand der folgenden Schritte konfigurieren:


1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.
4. Wählen Sie auf dem Blatt **Geräte und Gruppen** die Optionen **Setup** > **TeamViewer Connector** aus.
5. Klicken Sie auf dem Blatt **TeamViewer Connector** auf **Aktivieren**. Zeigen Sie den Lizenzvertrag für den TeamViewer-Dienst an und akzeptieren Sie diesen.
6. Wählen Sie **Bei TeamViewer anmelden und autorisieren**.
7. Auf der TeamViewer-Website wird eine Webseite geöffnet. Geben Sie die Anmeldeinformationen für Ihre TeamViewer-Lizenz ein, und klicken Sie dann auf **Anmelden**.


## <a name="how-to-remotely-administer-an-android-device"></a>Informationen zur Remoteverwaltung eines Android-Geräts

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.
4. Wählen Sie auf dem Blatt **Geräte** die Optionen **Verwalten** > **Alle Geräte** aus.
5. Wählen Sie das Gerät aus, das Sie zur Remoteverwaltung verwenden möchten, und wählen Sie dann auf dem Blatt „Geräteeigenschaften“ **Mehr** > **Neue Remoteunterstützungssitzung**.
6. Nachdem Intune eine Verbindung mit dem TeamViewer-Dienst hergestellt hat, werden einige Informationen über das Android-Gerät angezeigt. Wählen Sie **Verbinden**, um die Remotesitzung zu starten.

![Android TeamViewer-Fenster](./media/android-teamviewer.png)

Im TeamViewer-Fenster können Sie eine Reihe von Remoteaktionen auf dem Android-Gerät durchführen, einschließlich der Remotesteuerung des Geräts. Ausführliche Informationen zu den ausführbaren Aktionen finden Sie in der [TeamViewer-Dokumentation](https://www.teamviewer.com/support/documents/).

Wenn Sie fertig sind, schließen Sie das TeamViewer-Fenster.

## <a name="end-user-notifications"></a>Endbenutzerbenachrichtigungen

Beim Öffnen der App werden einem Endbenutzer auf dessen Gerät ein Benachrichtigungskennzeichen auf dem Symbol der Unternehmensportal-App sowie eine Benachrichtigung angezeigt. Anschließend kann er die Remoteunterstützungsanforderung annehmen.

