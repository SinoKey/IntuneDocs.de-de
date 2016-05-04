---
title: Allgemeine Aufgaben zur Verwaltung von Windows-PCs mit dem Microsoft Intune-Computerclient
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: eb912c73-54d2-4d78-ac34-3cbe825804c7
author: robstackmsft
---
# Allgemeine Aufgaben zur Verwaltung von Windows-PCs mit dem Microsoft Intune-Computerclient
Überprüfen Sie die Aufgaben in diesem Thema erhalten Sie Informationen zum Verwalten von Computern, die den Intune-Client ausgeführt. Wenn den Client noch nicht auf Ihren Computern installiert haben, finden Sie unter [Installieren des Windows-PC-Clients mit Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).



## Verwalten der Windows-Firewall mithilfe von Richtlinien
Mit Richtlinien lässt sich die Verwaltung der Einstellungen der Windows-Firewall auf verwalteten Computern vereinfachen. Weitere Informationen finden Sie unter [Schützen von Windows-PCs mit Windows-Firewall-Richtlinien in Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md).

## Verwalten des Microsoft Intune Center mithilfe von Richtlinien
Microsoft Intune Center können Benutzer:

-   Abrufen von Anwendungen aus dem Unternehmensportal

-   Suchen nach Updates

-   Verwalten von Microsoft Intune Endpoint Protection.

-   Anfordern von Remoteunterstützung

Microsoft Intune Center ist auf allen verwalteten Computern installiert. Sie können die folgenden Einstellungen in einer Intune-Richtlinie konfigurieren, und diese Benutzer in Microsoft Intune Center angezeigt werden:

|Richtlinieneinstellung|Details|
|------------------|--------------------|
|**Name**|Name des Administrators, der den Computer verwaltet<br /><br />Maximale Länge: 40 Zeichen|
|**Telefonnummer**|Telefonnummer des Administrators, der den Computer verwaltet<br /><br />Maximale Länge: 20 Zeichen|
|**E-Mail-Adresse**|E-Mail-Adresse des Administrators, der den Computer verwaltet<br /><br />Maximale Länge: 40 Zeichen|
|**Name der Website**|Name der Supportwebsite für Benutzer<br /><br />Maximale Länge: 40 Zeichen|
|**URL der Website**|URL der Supportwebsite<br /><br />Maximale Länge: 150 Zeichen|
|**Hinweise**|Hinweis, der Benutzern angezeigt wird<br /><br />Maximale Länge: 120 Zeichen|

## Verwalten der Einstellungen für Softwareupdates mithilfe von Richtlinien
Mit Richtlinien können Sie die Einstellungen konfigurieren, mit deren Hilfe von verwalteten Computern nach Softwareupdates von Microsoft und Drittanbietern gesucht und diese heruntergeladen werden. Weitere Informationen finden Sie unter [Windows-PCs zu halten, bis zum Datum mit Softwareupdates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).

## Verwalten von Endpoint Protection-Einstellungen mithilfe von Richtlinien
Verwenden Sie Richtlinien für Endpoint Protection konfigurieren, die Sie dann auf verwalteten Computern bereitstellen. Dies schließt Überprüfungszeitpläne, nach dem Erkennen von Malware durchzuführende Schritte und mehr ein. Weitere Informationen finden Sie unter [Schützen der Windows-PCs mit Endpoint Protection für Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).

## Anzeigen des Hardware- und Softwareinventars
Intune werden ausführliche Informationen über die Hardware und Software der verbreiteten Computer erfasst. In den nachfolgend beschriebenen Verfahren lernen Sie, wie Sie

-   Einen Bericht erstellen, in dem Informationen zu den Hardwarefunktionen Ihres Computers aufgeführt sind

-   Einen Bericht erstellen, in dem die auf den jeweiligen Computern installierte Software aufgeführt ist

-   Das Inventar eines Computers aktualisieren, um sicherzustellen, dass die im Bericht enthaltenen Daten aktuell sind

### So zeigen Sie Informationen zu Ihren Computern an

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/)auf **Berichte** &gt; **Computerinventurberichte**.

2.  Übernehmen Sie auf der Seite **Neuen Bericht erstellen** die Vorgaben, oder passen Sie sie an, um die im Bericht zurückgegebenen Ergebnisse zu filtern. Sie können beispielsweise auswählen, dass nur Computer im Bericht angezeigt werden, auf denen Windows 8.1 ausgeführt wird.

3.  Klicken Sie auf **Bericht anzeigen** , um den **Computerinventurbericht** in einem neuen Fenster anzuzeigen.

    Sie können den Bericht durch Klicken auf die entsprechende Spaltenüberschrift nach jeder Spalte sortieren, z. B. **Name**, **Gehäusetyp** oder **Hersteller** .

### So zeigen Sie die auf Ihren Computern installierte Software an

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/)auf **Berichte** &gt; **Berichte zu ermittelter Software**.

2.  Übernehmen Sie auf der Seite **Neuen Bericht erstellen** die Vorgaben, oder passen Sie sie an, um die im Bericht zurückgegebenen Ergebnisse zu filtern. Sie können beispielsweise auswählen, dass nur von Microsoft herausgegebene Software im Bericht angezeigt wird.

3.  Klicken Sie auf **Bericht anzeigen** , um den **Bericht zu ermittelter Software** in einem neuen Fenster anzuzeigen.

    Sie können den Bericht durch Klicken auf die entsprechende Spaltenüberschrift nach jeder Spalte sortieren, z. B. **Name**, **Herausgeber** oder **Kategorie** . Durch Anklicken des Richtungspfeils neben dem Listenelement können Sie die Updates in der Liste erweitern, um weitere Details (zum Beispiel die Computer, auf denen ein Update installiert ist) anzuzeigen.

### So aktualisieren Sie das Computerinventar, um sicherzustellen, dass es aktuell ist

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/)auf **Gruppen** &gt; **Alle Geräte** (oder eine andere Gruppe, in der der Computer enthalten ist, für den Sie das Inventar aktualisieren möchten).

2.  Wählen Sie einen Computer aus, oder wählen Sie mit gedrückter **STRG** -Taste mehrere Computer aus.

3.  Klicken Sie auf der Taskleiste auf **Remoteaufgaben** &gt; **Inventar aktualisieren**.

4.  Zur Anzeige des Aufgabenstatus klicken Sie auf **Remoteaufgaben** unten rechts auf der Seite.

    Im Dialogfeld **Taskstatus** werden aktuelle Remoteaufgaben, ihr Status, der Gerätename und etwaige gemeldete Fehler mit einem Link zu Problembehandlungsinformationen aufgelistet.

## Zusätzliche Aufgaben
Zusätzlich zu den Richtlinien können Sie auch die folgenden Verwaltungsaufgaben auf Ihren Computern ausführen:

### Um einen Remoteneustart für einen Windows-PC

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/)auf **Gruppen** &gt; **Alle Geräte** (oder eine andere Gruppe, in der der Computer enthalten ist, den Sie erneut starten möchten).

2.  Wählen Sie mindestens einen Computer aus, und klicken Sie dann auf **Remoteaufgaben** &gt; **Computer neu starten**.

3.  Zur Anzeige des Aufgabenstatus klicken Sie auf **Remoteaufgaben** unten rechts auf der Seite.

4.  Überprüfen Sie im Dialogfeld **Taskstatus** die aktuellen Remoteaufgaben, den Aufgabenstatus, den Gerätenamen und etwaige gemeldete Fehler.

### So koppeln Sie einen Computer ab

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/)auf **Gruppen** &gt; **Alle Geräte** (oder eine andere Gruppe, in der der Computer enthalten ist, den Sie abkoppeln möchten).

2.  Wählen Sie die Geräte abkoppeln, und klicken Sie dann auf **abkoppeln/zurücksetzen**.

Um einen Computer erneut bei Intune registrieren, installieren Sie die Clientsoftware auf dem Computer, die anhand der Informationen in den [Installieren des Windows-PC-Clients mit Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md) Thema.

Wenn ein Computer mit Intune zugreifen kann, wird eine Meldung angezeigt, dem **Dashboard** Arbeitsbereich.

Wenn Sie einen Computer abkoppeln, werden folgende Aktionen ausgeführt:

-   Wird aus dem Intune-Inventar entfernt, und die mit dem Computer verknüpfte Lizenz für die erneute Verwendung zur Verfügung gestellt wird.

-   Der Status ist nicht mehr in der Intune-Konsole angezeigt.

-   Intune entfernt die Clientsoftware vom Computer. Wenn der Computer nicht zum Intune-Dienst verbunden ist, wird die Clientsoftware nächsten entfernt werden, die es verbindet.

-   Microsoft Intune Endpoint Protection wird vom Computer entfernt. Verfügt der Computer ist eine andere endpunktschutzanwendung installiert und deaktiviert, Anwendung erneut aktiviert werden kann, nachdem Microsoft Intune Endpoint Protection entfernt wird, um sicherzustellen, dass Ihre Computer geschützt sind.

-   Alle vorhandenen Richtlinien werden vom Computer entfernt, und die durch die Richtlinie festgelegten Werte werden geändert.

-   Der Computer erhält Softwareupdates für oder Malware nicht mehr aus dem Intune-Dienst.

-   Abgekoppelte Computer können je nach Konfiguration weiterhin Updates über Windows Server Update Services, Windows Update oder Microsoft Update empfangen.

    > [!IMPORTANT]
    > Wurde die Clientsoftware mithilfe eines Gruppenrichtlinienobjekts installiert, dann müssen Sie zuerst das Gruppenrichtlinienobjekt entfernen, bevor Sie die Clientsoftware entfernen können. So wird verhindert, dass die Software erneut installiert wird.

    Wenn der Client nicht deinstallieren, lesen Sie [Problembehandlung bei Endpoint Protection in Microsoft Intune](troubleshoot-endpoint-protection-in-microsoft-intune.md) für weitere Hilfe.

## So verwalten Sie Verknüpfungen zwischen Benutzern und Geräten
Damit Sie Software für einen Benutzer bereitstellen können, müssen Sie diesen zunächst mit einem Computer verknüpfen. Sie können einen Benutzer mit mehreren Computern verknüpfen, aber einzelne Computer nur mit jeweils einem Benutzer. Benutzer werden automatisch mit Computern verknüpft, die sie über das Unternehmensportal in Intune zu registrieren.

### So verknüpfen Sie einen Benutzer mit einem Computer

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/)auf **Gruppen** &gt; **Alle Geräte** (oder eine andere Gruppe, in der der Computer enthalten ist, den Sie mit einem Benutzer verknüpfen möchten).

2.  Wählen Sie den Computer aus, den Sie mit einem Benutzer verknüpfen möchten, und klicken Sie dann auf **Benutzer verknüpfen**.

    Im Dialogfeld **Benutzer verknüpfen** wird eine Liste verfügbarer Benutzer mit ihren Anzeigenamen, Benutzer-IDs und der Anzahl von Computern angezeigt, mit denen die Benutzer jeweils aktuell verknüpft sind. Wenn ein Benutzer bereits mit dem ausgewählten Computer verknüpft ist, werden Name und Benutzer-ID des Benutzers unter **Aktueller Benutzer**angezeigt. Wenn der Computer mit keinem Benutzer verknüpft ist, wird unter **Aktueller Benutzer** der Wert **Kein Benutzer**angezeigt.

3.  Führen Sie einen der folgenden Schritte aus:

    -   Klicken Sie auf **Abbrechen**, um die Verknüpfung des Computers mit einem ggf. vorhandenen aktuellen Benutzer beizubehalten.

    -   Zum Entfernen der Verknüpfung mit dem aktuellen Benutzer klicken Sie ggf. auf **Verknüpfung entfernen**&gt;**OK**.

    -   Zum Verknüpfen des Computers mit einem neuen Benutzer wählen Sie diesen in der Liste **Alle Benutzer** aus. Überprüfen Sie, ob die Benutzerdaten korrekt sind, und klicken Sie auf **OK**.

> [!TIP]
> Wenn Sie die Möglichkeit der Endbenutzer, sich mit Computern verknüpfen einschränken möchten, aktivieren Sie die Option **Fähigkeit der Benutzer, sich mit Computern verknüpfen einschränken** in die **Microsoft Intune-Agent-Einstellungen** Richtlinie.

## Reagieren auf eine Remoteunterstützungsanforderung
Benutzer können mithilfe der Remoteunterstützung über Microsoft Easy Assist, die automatisch auf verwalteten Computern installiert wird, Unterstützung anfordern. Wenn eine Anforderung gestellt wird, zeigt eine Warnung in der Intune-Konsole.

> [!IMPORTANT]
> Eine Remoteunterstützung wird auf Computern mit Windows 8 oder höher nicht unterstützt.
> 
> Wenn Sie eine Remoteunterstützungsanforderung auf einem Computer akzeptieren, auf dem Microsoft Easy Assist nicht installiert ist, werden Sie zur Installation von Easy Assist aufgefordert. Der Computer muss nach der Installation neu gestartet werden. Ziehen Sie in Erwägung, Microsoft Easy Assist bereits vorab auf die Computer Ihres Benutzers zu laden, um diesen Neustart zu umgehen.

### So verwalten Sie eine Remoteunterstützungsanforderung

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/)auf **Warnungen** &gt; **Remoteunterstützung**.

2.  Wählen Sie in der Liste **Warnungen** eine Remoteunterstützungsanforderung aus, um die Eigenschaftsseite der Anforderung zu öffnen.

3.  Klicken Sie auf **Anforderung genehmigen und Remoteunterstützung starten** , um ein Dialogfeld mit Optionen zur Behandlung der Warnung zu öffnen.

4.  Führen Sie einen der folgenden Schritte aus:

    -   **Anforderung akzeptieren** – Wenn Sie der Remotesitzung beizutreten, klicken Sie auf **die Remoteunterstützungsanforderung akzeptieren**.

        Der Benutzer sieht die Nachricht: **Ihre Anforderung wurde akzeptiert. Führen Sie die Anweisungen in Easy Assist, um ein Programm oder Ihren Desktop für Ihren Systemadministrator freizugeben**.

        > [!IMPORTANT]
        > Sie können keine Remoteunterstützungsanforderung auf einem Macintosh-Computer annehmen, die die Intune-Administratorkonsole ausgeführt wird.

    -   **Anforderung ablehnen** – Schließen der **Problembehandlungsinformationen anzeigen** aus, und klicken Sie dann auf **Diese Warnung schließen** im Fenster Eigenschaften von Warnung.

        Die Anforderung wird geschlossen, und dem Benutzer wird eine Meldung angezeigt, die besagt, dass die Anforderung abgelehnt wurde. Wenn der Benutzer erneut eine Remoteunterstützung anfordern möchte, muss er eine neue Remoteunterstützungsanforderung senden. Wenn Sie versehentlich eine Remoteunterstützungswarnung schließen, wenden Sie sich an den Absender der Remoteunterstützungsanforderung, und bitten Sie diesen Benutzer, eine neue Anforderung zu senden.






<!--HONumber=Mar16_HO4-->


