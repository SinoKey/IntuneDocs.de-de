---
title: Allgemeine Aufgaben zur Verwaltung von Windows-PCs | Microsoft Intune
description: "Machen Sie sich mit den Aufgaben in diesem Thema vertraut, um zu erfahren, wie Sie Windows PCs verwalten, auf denen der Intune-Softwareclient ausgeführt wird."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb912c73-54d2-4d78-ac34-3cbe825804c7
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: cf6b4c0fbc8a739f205173f39093ce5550cb8321
ms.openlocfilehash: 075ed3f7d8b5f8283b7936c1c89d20081a9264a6


---

# <a name="common-windows-pc-management-tasks-with-the-intune-software-client"></a>Allgemeine Aufgaben zur Verwaltung von Windows-PCs mit dem Intune-Softwareclient
Machen Sie sich mit den Aufgaben in diesem Thema vertraut, um zu erfahren, wie Sie Computer verwalten, auf denen der Intune-Softwareclient ausgeführt wird. Wenn Sie den Client noch nicht auf Ihren Computern installiert haben, finden Sie weitere Informationen unter [Installieren des Windows-PC-Clients mit Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).


## <a name="use-policies-to-simplify-pc-management"></a>Verwenden von Richtlinien zum Vereinfachen der Verwaltung von PCs

Windows-PCs, auf denen der Intune Softwareclient ausgeführt wird, können mithilfe der **Computerverwaltungsrichtlinien** von Intune verwaltet werden.

![Richtlinienvorlage für Windows-PCs](../media/pc_policy_template.png)

### <a name="manage-the-microsoft-intune-center"></a>Verwalten des Microsoft Intune Center
Benutzern wird der Intune-Softwareclient als das **Microsoft Intune Center** angezeigt. Das Microsoft Intune Center bietet Benutzern folgende Möglichkeiten:

-   Abrufen von Anwendungen aus dem Unternehmensportal

-   Suchen nach Updates

-   Verwalten von Microsoft Intune Endpoint Protection

-  Anfordern von Remoteunterstützung

Das Microsoft Intune Center ist auf allen verwalteten Computern installiert. Sie können die folgenden Einstellungen in einer Intune Center-Richtlinie konfigurieren, die anschließend Benutzern im Microsoft Intune Center angezeigt werden:

|Richtlinieneinstellung|Details|
|------------------|--------------------|
|**Name**|Name des Administrators, der den Computer verwaltet<br />Maximale Länge: 40 Zeichen|
|**Telefonnummer**|Telefonnummer des Administrators, der den Computer verwaltet<br />Maximale Länge: 20 Zeichen|
|**E-Mail-Adresse**|E-Mail-Adresse des Administrators, der den Computer verwaltet<br />Maximale Länge: 40 Zeichen|
|**Name der Website**|Name der Supportwebsite für Benutzer<br />>Maximale Länge: 40 Zeichen|
|**URL der Website**|URL der Supportwebsite<br />Maximale Länge: 150 Zeichen|
|**Anmerkungen**|Hinweis, der Benutzern angezeigt wird<br />Maximale Länge: 120 Zeichen|

Finden Sie Informationen zu Richtlinien und Einstellungen für Windows-PCs in den folgenden Ressourcen:

- [Aktualisieren Ihrer Windows-PCs mit Softwareupdates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md): Aufgrund dieser Richtlinien suchen verwaltete Computer nach Softwareupdates und laden diese von Microsoft und Drittanbietern herunter. Diese Updates enthalten keine Upgrades des Betriebssystems (d.h. keine Upgrades von Windows 7 auf Windows 10 oder von Windows 10 auf eine höhere Version).

- [Schützen von Windows-PCs mit Endpoint Protection für Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md): Zu diesen Einstellungen gehören Überprüfungszeitpläne und zu ergreifende Maßnahmen, wenn Malware erkannt wird.

- [Unterstützen des Schutzes von Windows-PCs mithilfe von Windows-Firewall-Richtlinien in Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md): Diese Richtlinien vereinfachen die Verwaltung von Windows-Firewalleinstellungen auf verwalteten Computern.

## <a name="view-hardware-and-software-inventory"></a>Anzeigen des Hardware- und Softwareinventars
Durch Intune werden ausführliche Informationen zur Hardware und Software der verbreiteten Computer erfasst. In den nachfolgend beschriebenen Verfahren lernen Sie, wie Sie

-   Einen Bericht erstellen, in dem Informationen zu den Hardwarefunktionen Ihres Computers aufgeführt sind

-   Einen Bericht erstellen, in dem die auf den jeweiligen Computern installierte Software aufgeführt ist

-   Das Inventar eines Computers aktualisieren, um sicherzustellen, dass die im Bericht enthaltenen Daten aktuell sind

### <a name="to-display-information-about-your-computers"></a>So zeigen Sie Informationen zu Ihren Computern an

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Berichte** &gt; **Computerinventurberichte** aus.

2.  Übernehmen Sie auf der Seite **Neuen Bericht erstellen** die Vorgaben, oder passen Sie sie an, um die im Bericht zurückgegebenen Ergebnisse zu filtern. Sie können beispielsweise auswählen, dass nur Computer im Bericht angezeigt werden, auf denen Windows 8.1 ausgeführt wird.

3.  Wählen Sie **Bericht anzeigen** aus, um den **Computerinventurbericht** in einem neuen Fenster anzuzeigen.

    Sie können den Bericht durch Auswählen der entsprechenden Spaltenüberschrift nach jeder Spalte sortieren, z. B. **Name**, **Gehäusetyp** oder **Hersteller**.

### <a name="to-display-software-installed-on-your-computers"></a>So zeigen Sie die auf Ihren Computern installierte Software an

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Berichte** &gt; **Berichte zu ermittelter Software** aus.

2.  Übernehmen Sie auf der Seite **Neuen Bericht erstellen** die Vorgaben, oder passen Sie sie an, um die im Bericht zurückgegebenen Ergebnisse zu filtern. Sie können beispielsweise auswählen, dass nur von Microsoft herausgegebene Software im Bericht angezeigt wird.

3.  Wählen Sie **Bericht anzeigen** aus, um den **Bericht zu ermittelter Software** in einem neuen Fenster anzuzeigen.

    Sie können den Bericht durch Auswählen der entsprechenden Spaltenüberschrift nach jeder Spalte sortieren, z. B. **Name**, **Herausgeber** oder **Kategorie**. Durch Auswahl des Richtungspfeils neben dem Listenelement können Sie die Updates in der Liste erweitern, um weitere Details anzuzeigen (zum Beispiel die Computer, auf denen ein Update installiert ist).

### <a name="to-refresh-computer-inventory-to-ensure-it-is-current"></a>So aktualisieren Sie das Computerinventar, um sicherzustellen, dass es aktuell ist

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Gruppen** &gt; **Alle Geräte** aus (oder eine andere Gruppe, in der der Computer enthalten ist, für den Sie das Inventar aktualisieren möchten).

2.  Wählen Sie einen Computer aus, oder wählen Sie mit gedrückter **STRG** -Taste mehrere Computer aus.

3.  Wählen Sie auf der Taskleiste **Remoteaufgaben** &gt; **Inventar aktualisieren** aus.

4.  Zur Anzeige des Aufgabenstatus wählen Sie **Remoteaufgaben** unten rechts auf der Seite aus.

    Im Dialogfeld **Taskstatus** werden aktuelle Remoteaufgaben, ihr Status, der Gerätename und etwaige gemeldete Fehler mit einem Link zu Problembehandlungsinformationen aufgelistet.


## <a name="remotely-restart-a-windows-pc"></a>Remoteneustart eines Windows-PCs

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Gruppen** &gt; **Alle Geräte** aus (oder eine andere Gruppe, in der der Computer enthalten ist, den Sie erneut starten möchten).

2.  Wählen Sie mindestens einen Computer aus, und wählen Sie dann **Remoteaufgaben** &gt; **Computer neu starten**.

3.  Zur Anzeige des Aufgabenstatus wählen Sie **Remoteaufgaben** unten rechts auf der Seite aus.

4.  Überprüfen Sie im Dialogfeld **Taskstatus** die aktuellen Remoteaufgaben, den Aufgabenstatus, den Gerätenamen und etwaige gemeldete Fehler.

## <a name="retire-a-computer"></a>Abkoppeln eines Computers

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Gruppen** &gt; **Alle Geräte** aus (oder eine andere Gruppe, in der der Computer enthalten ist, den Sie abkoppeln möchten).

2.  Wählen Sie die Geräte aus, die Sie abkoppeln möchten, und wählen Sie dann **Abkoppeln/Zurücksetzen** aus.

Installieren Sie zum erneuten Registrieren eines Computers bei Intune den Softwareclient erneut auf dem Computer. Gehen Sie hierzu vor wie unter [Installieren des Windows-PC-Clients mit Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md) beschrieben.

Wenn von einem Computer keine Verbindung mit Intune hergestellt werden kann, wird im Arbeitsbereich **Dashboard** eine Meldung angezeigt.

Wenn Sie einen Computer abkoppeln, werden folgende Aktionen ausgeführt:

-   Der Computer wird aus dem Intune-Verwaltung und -Inventar entfernt, und die mit dem Computer verknüpfte Lizenz steht zur erneuten Verwendung zur Verfügung. Durch „Abkoppeln/Zurücksetzen“ wird der Intune-Softwareclient vom Computer entfernt, es werden aber keine Apps oder Daten gelöscht. Diese Abkopplung führt keine vollständige Zurücksetzung auf dem Computer aus.

-   Der Status des Computers wird nicht mehr in der Intune-Konsole angezeigt.

-   Intune entfernt den Softwareclient von dem Computer. Wenn der Computer nicht mit Intune verbunden ist, wird der Softwareclient nach der nächsten Verbindungsherstellung entfernt.

-   Microsoft Intune Endpoint Protection wird vom Computer entfernt. Wenn auf dem Computer eine andere Endpunktanwendung installiert ist und diese deaktiviert ist, kann sie unter Umständen nach dem Entfernen von Microsoft Intune Endpoint Protection wieder aktiviert werden, um sicherzustellen, dass Ihre Computer geschützt sind.

-   Alle vorhandenen Richtlinien werden vom Computer entfernt, und die durch die Richtlinie festgelegten Werte werden geändert.

-   Der Computer erhält vom Intune-Dienst keine Softwareupdates oder aktualisierten Schadsoftwaredefinitionen mehr.

-   Abgekoppelte Computer können je nach Konfiguration weiterhin Updates über Windows Server Update Services, Windows Update oder Microsoft Update empfangen.

    > [!IMPORTANT]
    > Wurde die Clientsoftware mithilfe eines Gruppenrichtlinienobjekts installiert, dann müssen Sie zuerst das Gruppenrichtlinienobjekt entfernen, bevor Sie die Clientsoftware entfernen können. So wird verhindert, dass die Software erneut installiert wird.

    Wenn der Client nicht deinstalliert werden kann, finden Sie hilfreiche Informationen unter [Problembehandlung für Endpoint Protection](/intune/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune).

## <a name="manage-user-device-linking"></a>Verwalten von Verknüpfungen zwischen Benutzern und Geräten
Damit Sie Software für einen Benutzer bereitstellen können, müssen Sie diesen zunächst mit einem Computer verknüpfen. Sie können einen Benutzer mit mehreren Computern verknüpfen, aber einzelne Computer nur mit jeweils einem Benutzer. Benutzer werden automatisch mit den Computern verknüpft, die sie über das Unternehmensportal in Intune registrieren.

### <a name="to-link-a-user-to-a-computer"></a>So verknüpfen Sie einen Benutzer mit einem Computer

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Gruppen** &gt; **Alle Geräte** aus (oder eine andere Gruppe, in der der Computer enthalten ist, den Sie mit einem Benutzer verknüpfen möchten).

2.  Wählen Sie den Computer aus, den Sie mit einem Benutzer verknüpfen möchten, und wählen Sie dann **Benutzer verknüpfen** aus.

    Im Dialogfeld **Benutzer verknüpfen** wird eine Liste verfügbarer Benutzer mit ihren Anzeigenamen, Benutzer-IDs und der Anzahl von Computern angezeigt, mit denen die Benutzer jeweils aktuell verknüpft sind. Wenn ein Benutzer bereits mit dem ausgewählten Computer verknüpft ist, werden Name und Benutzer-ID des Benutzers unter **Aktueller Benutzer**angezeigt. Wenn der Computer mit keinem Benutzer verknüpft ist, wird unter **Aktueller Benutzer** der Wert **Kein Benutzer**angezeigt.

3.  Führen Sie eines der folgenden Verfahren aus:

    -   Wählen Sie **Abbrechen** aus, um die Verknüpfung des Computers mit einem ggf. vorhandenen aktuellen Benutzer beizubehalten.

    -   Zum Entfernen der Verknüpfung mit dem aktuellen Benutzer wählen Sie ggf. **Verknüpfung entfernen** &gt; **OK** aus.

    -   Zum Verknüpfen des Computers mit einem neuen Benutzer wählen Sie diesen in der Liste **Alle Benutzer** aus. Überprüfen Sie, ob die Benutzerdaten korrekt sind, und wählen Sie **OK** aus.

> [!TIP]
> Wenn Sie die Fähigkeit der Endbenutzer, sich mit Computern zu verknüpfen, einschränken möchten, aktivieren Sie die Option **Fähigkeit der Benutzer einschränken, sich mit Computern zu verknüpfen** in der Richtlinie **-Microsoft Intune-Agent-Einstellungen**.

## <a name="request-and-provide-remote-assistance-for-windows-pcs"></a>Anfordern und Bereitstellen von Remoteunterstützung für Windows-PCs

In Microsoft Intune können Sie die nicht im Lieferumfang inbegriffene [TeamViewer](https://www.teamviewer.com)-Software verwenden, um PC-Benutzer remote zu unterstützen, bei denen der Intune-Softwareclient ausgeführt wird. Sobald ein Benutzer Hilfe über das Microsoft Intune Center anfordert, werden Sie durch eine Warnung benachrichtigt, können die Anforderung annehmen und Unterstützung leisten.
Diese Funktion ersetzt die vorhandene Funktion „Windows-Remoteunterstützung“ in Intune.


### <a name="before-you-start"></a>Vorbereitung

Bevor Sie entsprechende Einrichtungsschritte ausführen und auf Anforderungen für Remoteunterstützung reagieren können, müssen Sie sicherstellen, dass folgende Voraussetzungen erfüllt sind:

- Sie müssen sich für ein [TeamViewer-Konto registriert haben](https://login.teamviewer.com/LogOn#register), um sich bei der TeamViewer-Website anzumelden.
- Die Windows-PCs, die auf denen Sie Administrationsaufgaben ausführen möchten, müssen [durch den Windows-PC-Client verwaltet werden](manage-windows-pcs-with-microsoft-intune.md).
- Auf allen von Intune unterstützten Windows-PC-Betriebssystemen können Administrationsaufgaben ausgeführt werden.

### <a name="configure-the-teamviewer-connector"></a>Konfigurieren des TeamViewer Connectors

1. Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Option **Verwaltung** aus.
2. Wählen Sie im Arbeitsbereich **Verwaltung** die Option **TeamViewer** aus.
3. Wählen Sie auf der Seite **TeamViewer** unter **TeamViewer Connector** die Option **Aktivieren**.
4. Lesen Sie im Dialogfeld **TeamViewer aktivieren** die Lizenzbedingungen, und klicken Sie auf **Annehmen**, um sie zu akzeptieren. Wenn Sie noch keine TeamViewer-Lizenz besitzen, wählen Sie **TeamViewer-Lizenz erwerben** aus.
5. Wenn das TeamViewer-Browserfenster angezeigt wird, melden Sie sich mit Ihren TeamViewer-Anmeldeinformationen bei der Website an.
6. Lesen Sie auf der TeamViewer-Website die Optionen, um das Herstellen einer Verbindung zwischen Intune und TeamViewer zuzulassen, und akzeptieren Sie sie.
7. Vergewissern Sie sich in der Intune-Konsole, dass das Element **TeamViewer Connector** als **Aktiviert** angezeigt wird.


### <a name="open-a-remote-assistance-request-end-user"></a>Öffnen einer Remoteunterstützungsanforderung (Endbenutzer)

1. Öffnen Sie auf einem Windows-Client-PC das **Microsoft Intune Center**.
2. Wählen Sie unter **Remoteunterstützung** die Option **Remoteunterstützung anfordern** aus.
3. Nach der Genehmigung der Anforderung (siehe unten) wird TeamViewer auf dem Client geöffnet. Der Benutzer muss alle Meldungen akzeptieren, die darauf hinweisen, dass der Webbrowser die TeamViewer-Anwendung zu öffnen versucht.
4. Der Benutzer wird in einer Meldung gebeten zuzulassen, dass Sie die Kontrolle über seinen PC übernehmen. Er muss diese Meldung akzeptieren, damit weitere Schritte möglich sind.
5. Während der Remoteunterstützungssitzung sieht der Benutzer ein Fenster, das anzeigt, dass Sie mit dem Computer des Benutzers verbunden sind. Wenn der Benutzer das Fenster schließt, wird die Remotesitzung beendet.

### <a name="respond-to-a-remote-assistance-request"></a>Reagieren auf eine Remoteunterstützungsanforderung

1. Wenn ein Benutzer eine Remoteunterstützungsanforderung übermittelt, können Sie sie im Arbeitsbereich **Warnungen** unter **Überwachung** > **Remoteunterstützung** anzeigen. Beispiel:
> ![Screenshot einer Remoteunterstützungsanforderung](./media/team-viewer.png)

<br>Wenn die Anforderung länger als 4 Stunden unbeantwortet bleibt, wird sie entfernt.
2. Um die Anforderung anzunehmen, wählen Sie **Anforderung genehmigen und Remoteunterstützung starten** aus.
3. Wählen Sie im Dialogfeld **Eine neue Remoteunterstützungsanforderung steht aus** die Option **Remoteunterstützungsanforderung annehmen** aus. Falls sie noch nicht vorhanden sind, installiert TeamViewer alle nötigen Apps auf Ihrem Computer.
4. Anschließend benachrichtigt TeamViewer den Endbenutzer, dass Sie die Kontrolle seinen PC übernehmen möchten. Nachdem der Benutzer dies akzeptiert hat, wird das TeamViewer-Fenster geöffnet, und Sie können den PC steuern.

Während einer Remoteunterstützungssitzung können Sie in alle verfügbaren TeamViewer-Befehle nutzen, um den Remote-PC zu steuern. Weitere Informationen und Hilfe zu diesen Befehlen finden Sie auf der TeamViewer-Website im [Handbuch für Fernsteuerung](http://www.teamviewer.com/en/support/documents/).

### <a name="close-the-remote-assistance-session"></a>Beenden der Remoteunterstützungssitzung

Wählen Sie im **TeamViewer**-Fenster im Menü **Aktionen** den Befehl **Sitzung beenden** aus.



<!--HONumber=Nov16_HO3-->


