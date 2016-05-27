---
# required metadata

title: Ihr Computer ist bereits registriert | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8d3a40f5-99e9-48dc-9706-f7a3a23e5704

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Ihr Computer ist bereits registriert
Sie sehen diese Seite, da Sie Setup für die Intune-Clientsoftware ausgeführt haben. Die Software ist jedoch bereits auf Ihrem Computer installiert, und Setup kann nicht fortgesetzt werden.

Mögliche Gründe hierfür sind:

-   Die Clientsoftware wude bereits früher installiert, und Setup wird erneut ausgeführt.

-   Setup wurde auf dem Computer ausgeführt, nachdem ein IT-Administrator Ihr Gerät von Intune abgekoppelt hat. Nachdem Ihr Gerät deaktiviert wurde, kann es mehrere Stunden dauern, bis die Clientsoftware von Ihrem Computer entfernt wird.

-   Setup hat eine kürzlich fehlgeschlagene Installation oder Fehler beim Entfernen der Clientsoftware erkannt.

## Was Setup auf dem Computer installiert
Setup installiert den Intune-Client. Nach Abschluss der Installation wird die Clientsoftware weiterhin im Hintergrund ausgeführt, um Ihren Computer für die Verwendung mit Intune zu konfigurieren. Dieser Vorgang kann einige Zeit in Anspruch nehmen und umfasst Folgendes:

-   Registrieren Ihres Computer bei Intune

-   Senden einer Bestandsaufnahme der Computerhardware und der installierten Software

-   Konfigurieren der Intune-Richtlinie, einschließlich Installation von Endpoint Protection (sofern konfiguriert)

-   Installieren von Intune Center

Nach der Installation von Intune Center können Sie es für den Zugriff auf das Unternehmensportal verwenden, wo Sie Ihren Computer mit Ihrem Geschäftskonto verknüpfen können.

## Microsoft Intune Center
Das Intune Center wird als App auf Ihrem Computer installiert, nachdem der Computer die Clientsoftware installiert und den Computer bei Intune registriert hat. Mit dem Intune Center können folgende Aktionen ausgeführt werden:

-   **Abrufen von Anwendungen aus dem Unternehmensportal** – Suchen und installieren Sie Apps, die von Ihrem IT-Administrator bereitgestellt werden. Wenn Sie sich auf einem neu registrierten Computer erstmalig beim Unternehmensportal anmelden, erhalten Sie die Möglichkeit, Ihr Geschäftskonto mit dem betreffenden Computer zu verknüpfen.

-   **Prüfen auf Softwareupdates** – Suchen Sie Softwareupdates, die vom Intune-Administrator bereitgestellt werden.

-   **Starten einer Endpoint Protection-Überprüfung Ihres Computers** – Sie können Ihren Computer auf Schadsoftware überprüfen.

-   **Anfordern von Remoteunterstützung** – Diese Option steht nur zur Verfügung, wenn das Betriebssystem Ihres Computers die Remoteunterstützung unterstützt.

## Überprüfen, ob die Clientsoftware installiert ist oder entfernt wurde
**Überprüfen, ob der Client installiert ist:**
Die Intune-Clientinstallation ist abgeschlossen, wenn die folgenden Apps auf dem Computer verfügbar sind:

-   **Intune Center**

-   **Intune Endpoint Protection** (wenn Endpoint Protection von Ihrem IT-Administrator aktiviert wurde)

Wenn Sie mit der Verwendung von Task-Manager vertraut sind, können Sie nach dem Intune-Clientdienst suchen, der ausgeführt werden sollte:

-   **OmcSvc**

**Überprüfen, ob der Client entfernt wurde:**
Nachdem der Intune-Client von einem Computer deinstalliert wurde, werden die bei Installation des Clients installierten Apps entfernt, dies gilt auch für das Intune Center.

Der Intune-Clientdienst **OmcSvc** wird entfernt.

## Entfernen der Clientsoftware vom Computer
Standardmäßig wird die Intune-Clientsoftware mehrere Stunden nach der Abkoppelung Ihres Computers von der Intune-Verwaltungskonsole von Ihrem Computer deinstalliert.

Zum manuellen Deinstallieren der Intune-Clientsoftware von einem Computer können Sie die folgenden Schritte verwenden, um die Deinstallation zu erzwingen:

1.  Öffnen Sie auf dem Computer eine Eingabeaufforderung im Administratormodus.

2.  Navigieren Sie zum Ordner **%programfiles%\Microsoft\OnlineManagement\Common**.

3.  Führen Sie den folgenden Befehl aus: **ProvisioningUtil.exe /UninstallAgents /MicrosoftIntune**.

Dadurch wird das Entfernen der Clientsoftware geplant.



<!--HONumber=May16_HO1-->


