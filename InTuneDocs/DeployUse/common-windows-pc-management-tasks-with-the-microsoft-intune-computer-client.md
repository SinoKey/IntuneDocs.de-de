---
# required metadata

title: Allgemeine Aufgaben zur Verwaltung von Windows-PCs | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: eb912c73-54d2-4d78-ac34-3cbe825804c7

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Allgemeine Aufgaben zur Verwaltung von Windows-PCs mit dem Microsoft Intune-Computerclient
Überprüfen Sie die Aufgaben in diesem Thema, um zu erfahren, wie Sie Computer verwalten, auf denen der Intune-Client ausgeführt wird. Wenn Sie den Client noch nicht auf Ihren Computern installiert haben, finden Sie unter [Installieren des Windows-PC-Clients mit Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md) weitere Informationen..


## Verwenden von Richtlinien zum Vereinfachen der Verwaltung von PCs
### Verwalten der Windows-Firewall
Mit Richtlinien lässt sich die Verwaltung der Einstellungen der Windows-Firewall auf verwalteten Computern vereinfachen. Weitere Informationen finden Sie unter [Unterstützen des Schutzes von Windows-PCs mithilfe von Windows-Firewall-Richtlinien in Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md)..

### Verwalten des Microsoft Intune Center
Das Microsoft Intune Center bietet Benutzern folgende Möglichkeiten:

-   Abrufen von Anwendungen aus dem Unternehmensportal

-   Suchen nach Updates

-   Verwalten von Microsoft Intune Endpoint Protection

-   Anfordern von Remoteunterstützung

Das Microsoft Intune Center ist auf allen verwalteten Computern installiert. Sie können die folgenden Einstellungen in einer Intune Center-Richtlinie konfigurieren, die dann Benutzern im Microsoft Intune Center angezeigt werden:

|Richtlinieneinstellung|Details|
|------------------|--------------------|
|**Name**|Name des Administrators, der den Computer verwaltet<br /><br />Maximale Länge: 40 Zeichen|
|**Telefonnummer**|Telefonnummer des Administrators, der den Computer verwaltet<br /><br />Maximale Länge: 20 Zeichen|
|**E-Mail-Adresse**|E-Mail-Adresse des Administrators, der den Computer verwaltet<br /><br />Maximale Länge: 40 Zeichen|
|**Name der Website**|Name der Supportwebsite für Benutzer<br /><br />Maximale Länge: 40 Zeichen|
|**URL der Website**|URL der Supportwebsite<br /><br />Maximale Länge: 150 Zeichen|
|**Hinweise**|Hinweis, der Benutzern angezeigt wird<br /><br />Maximale Länge: 120 Zeichen|

### Verwalten der Einstellungen für Softwareupdates
Mit Richtlinien können Sie die Einstellungen konfigurieren, mit deren Hilfe von verwalteten Computern nach Softwareupdates von Microsoft und Drittanbietern gesucht und diese heruntergeladen werden. Weitere Informationen finden Sie unter [Aktualisieren Ihrer Windows-PCs mit Softwareupdates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)..

### Verwalten der Endpoint Protection-Einstellungen
Konfigurieren Sie die Einstellungen für Endpoint Protection mithilfe von Richtlinien, und stellen Sie sie dann auf verwalteten Computern bereit. Dies schließt Überprüfungszeitpläne, nach dem Erkennen von Schadsoftware durchzuführende Schritte und mehr ein. Weitere Informationen finden Sie unter [Schützen von Windows-PCs mit Endpoint Protection für Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)..

## Anzeigen des Hardware- und Softwareinventars
Durch Intune werden ausführliche Informationen zur Hardware und Software der verbreiteten Computer erfasst. In den nachfolgend beschriebenen Verfahren lernen Sie, wie Sie

-   Einen Bericht erstellen, in dem Informationen zu den Hardwarefunktionen Ihres Computers aufgeführt sind

-   Einen Bericht erstellen, in dem die auf den jeweiligen Computern installierte Software aufgeführt ist

-   Das Inventar eines Computers aktualisieren, um sicherzustellen, dass die im Bericht enthaltenen Daten aktuell sind

### So zeigen Sie Informationen zu Ihren Computern an

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Berichte** &gt; **Computerinventurberichte** aus..

2.  Übernehmen Sie auf der Seite **Neuen Bericht erstellen** die Vorgaben, oder passen Sie sie an, um die im Bericht zurückgegebenen Ergebnisse zu filtern. Sie können beispielsweise auswählen, dass nur Computer im Bericht angezeigt werden, auf denen Windows 8.1 ausgeführt wird.

3.  Wählen Sie **Bericht anzeigen** aus, um den **Computerinventurbericht** in einem neuen Fenster anzuzeigen.

    Sie können den Bericht durch Auswählen der entsprechenden Spaltenüberschrift nach jeder Spalte sortieren, z. B. **Name**, **Gehäusetyp** oder **Hersteller**.

### So zeigen Sie die auf Ihren Computern installierte Software an

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Berichte** &gt; **Berichte zu ermittelter Software** aus..

2.  Übernehmen Sie auf der Seite **Neuen Bericht erstellen** die Vorgaben, oder passen Sie sie an, um die im Bericht zurückgegebenen Ergebnisse zu filtern. Sie können beispielsweise auswählen, dass nur von Microsoft herausgegebene Software im Bericht angezeigt wird.

3.  Wählen Sie **Bericht anzeigen** aus, um den **Bericht zu ermittelter Software** in einem neuen Fenster anzuzeigen.

    Sie können den Bericht durch Auswählen der entsprechenden Spaltenüberschrift nach jeder Spalte sortieren, z. B. **Name**, **Herausgeber** oder **Kategorie**. Durch Anklicken des Richtungspfeils neben dem Listenelement können Sie die Updates in der Liste erweitern, um weitere Details (zum Beispiel die Computer, auf denen ein Update installiert ist) anzuzeigen.

### So aktualisieren Sie das Computerinventar, um sicherzustellen, dass es aktuell ist

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Gruppen** &gt; **Alle Geräte** (oder eine andere Gruppe, in der der Computer enthalten ist, für den Sie das Inventar aktualisieren möchten) aus.

2.  Wählen Sie einen Computer aus, oder wählen Sie mit gedrückter **STRG** -Taste mehrere Computer aus.

3.  Wählen Sie auf der Taskleiste **Remoteaufgaben** &gt; **Inventar aktualisieren** aus..

4.  Zur Anzeige des Aufgabenstatus wählen Sie **Remoteaufgaben** unten rechts auf der Seite aus.

    Im Dialogfeld **Taskstatus** werden aktuelle Remoteaufgaben, ihr Status, der Gerätename und etwaige gemeldete Fehler mit einem Link zu Problembehandlungsinformationen aufgelistet.


## Remoteneustart eines Windows-PCs

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Gruppen** &gt; **Alle Geräte** (oder eine andere Gruppe, in der der Computer enthalten ist, den Sie erneut starten möchten) aus.

2.  Wählen Sie mindestens einen Computer aus, und wählen Sie dann **Remoteaufgaben** &gt; **Computer neu starten**..

3.  Zur Anzeige des Aufgabenstatus wählen Sie **Remoteaufgaben** unten rechts auf der Seite aus.

4.  Überprüfen Sie im Dialogfeld **Taskstatus** die aktuellen Remoteaufgaben, den Aufgabenstatus, den Gerätenamen und etwaige gemeldete Fehler.

## Abkoppeln eines Computers

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Gruppen** &gt; **Alle Geräte** (oder eine andere Gruppe, in der der Computer enthalten ist, den Sie abkoppeln möchten) aus.

2.  Wählen Sie die Geräte aus, die Sie abkoppeln möchten, und wählen Sie dann **Abkoppeln/Zurücksetzen** aus..

Zum erneuten Registrieren eines Computers bei Intune müssen Sie die Clientsoftware erneut auf dem Computer installieren. Gehen Sie hierzu vor wie im Thema [Installieren des Windows-PC-Clients mit Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md) beschrieben.

Wenn von einem Computer keine Verbindung mit Intune hergestellt werden kann, wird im Arbeitsbereich **Dashboard** eine Meldung angezeigt.

Wenn Sie einen Computer abkoppeln, werden folgende Aktionen ausgeführt:

-   Der Computer wird aus dem Intune-Inventar entfernt, und die mit dem Computer verknüpfte Lizenz steht zur erneuten Verwendung zur Verfügung.

-   Der Status des Computers wird nicht mehr in der Intune-Konsole angezeigt.

-   Die Clientsoftware wird von Intune vom Computer entfernt. Wenn der Computer nicht mit dem Intune-Dienst verbunden ist, wird die Clientsoftware nach dem nächsten Herstellen der Verbindung entfernt.

-   Microsoft Intune Endpoint Protection wird vom Computer entfernt. Wenn auf dem Computer eine andere Endpunktanwendung installiert ist und diese deaktiviert ist, kann sie unter Umständen nach dem Entfernen von Microsoft Intune Endpoint Protection wieder aktiviert werden, um sicherzustellen, dass Ihre Computer geschützt sind.

-   Alle vorhandenen Richtlinien werden vom Computer entfernt, und die durch die Richtlinie festgelegten Werte werden geändert.

-   Der Computer erhält vom Intune-Dienst keine Softwareupdates oder aktualisierten Schadsoftwaredefinitionen mehr.

-   Abgekoppelte Computer können je nach Konfiguration weiterhin Updates über Windows Server Update Services, Windows Update oder Microsoft Update empfangen.

    > [!IMPORTANT]
    > Wurde die Clientsoftware mithilfe eines Gruppenrichtlinienobjekts installiert, dann müssen Sie zuerst das Gruppenrichtlinienobjekt entfernen, bevor Sie die Clientsoftware entfernen können. So wird verhindert, dass die Software erneut installiert wird.

    Wenn der Client nicht deinstalliert werden kann, finden Sie hilfreiche Informationen unter [Problembehandlung für Endpoint Protection](/intune/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune).

## Verwalten von Verknüpfungen zwischen Benutzern und Geräten
Damit Sie Software für einen Benutzer bereitstellen können, müssen Sie diesen zunächst mit einem Computer verknüpfen. Sie können einen Benutzer mit mehreren Computern verknüpfen, aber einzelne Computer nur mit jeweils einem Benutzer. Benutzer werden automatisch mit den Computern verknüpft, die sie über das Unternehmensportal in Intune registrieren.

### So verknüpfen Sie einen Benutzer mit einem Computer

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Gruppen** &gt; **Alle Geräte** (oder eine andere Gruppe, in der der Computer enthalten ist, den Sie mit einem Benutzer verknüpfen möchten) aus.

2.  Wählen Sie den Computer aus, den Sie mit einem Benutzer verknüpfen möchten, und wählen Sie dann **Benutzer verknüpfen** aus..

    Im Dialogfeld **Benutzer verknüpfen** wird eine Liste verfügbarer Benutzer mit ihren Anzeigenamen, Benutzer-IDs und der Anzahl von Computern angezeigt, mit denen die Benutzer jeweils aktuell verknüpft sind. Wenn ein Benutzer bereits mit dem ausgewählten Computer verknüpft ist, werden Name und Benutzer-ID des Benutzers unter **Aktueller Benutzer**angezeigt. Wenn der Computer mit keinem Benutzer verknüpft ist, wird unter **Aktueller Benutzer** der Wert **Kein Benutzer**angezeigt..

3.  Führen Sie eines der folgenden Verfahren aus:

    -   Wählen Sie **Abbrechen** aus, um die Verknüpfung des Computers mit einem ggf. vorhandenen aktuellen Benutzer beizubehalten..

    -   Zum Entfernen der Verknüpfung mit dem aktuellen Benutzer wählen Sie ggf. **Verknüpfung entfernen**&gt;**OK** aus..

    -   Zum Verknüpfen des Computers mit einem neuen Benutzer wählen Sie diesen in der Liste **Alle Benutzer** aus. Überprüfen Sie, ob die Benutzerdaten korrekt sind, und wählen Sie **OK** aus..

> [!TIP]
> Wenn Sie die Fähigkeit der Endbenutzer, sich mit Computern zu verknüpfen, einschränken möchten, aktivieren Sie die Option **Fähigkeit der Benutzer einschränken, sich mit Computern zu verknüpfen** in der Richtlinie **-Microsoft Intune-Agent-Einstellungen**.

## Reagieren auf eine Remoteunterstützungsanforderung
Benutzer können mithilfe der Remoteunterstützung über Microsoft Easy Assist, die automatisch auf verwalteten Computern installiert wird, Unterstützung anfordern. Wird eine Anforderung gestellt, dann wird eine Warnung in der Intune-Konsole angezeigt.

> [!IMPORTANT]
> Eine Remoteunterstützung wird auf Computern mit Windows 8 oder höher nicht unterstützt.
>
> Wenn Sie eine Remoteunterstützungsanforderung auf einem Computer akzeptieren, auf dem Microsoft Easy Assist nicht installiert ist, werden Sie zur Installation von Easy Assist aufgefordert. Der Computer muss nach der Installation neu gestartet werden. Ziehen Sie in Erwägung, Microsoft Easy Assist bereits vorab auf die Computer Ihres Benutzers zu laden, um diesen Neustart zu umgehen.

### So verwalten Sie eine Remoteunterstützungsanforderung

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Warnungen** &gt; **Remoteunterstützung** aus..

2.  Wählen Sie in der Liste **Warnungen** eine Remoteunterstützungsanforderung aus, um die Eigenschaftsseite der Anforderung zu öffnen.

3.  Wählen Sie **Anforderung genehmigen und Remoteunterstützung starten** aus, um ein Dialogfeld mit Optionen zur Behandlung der Warnung zu öffnen.

4.  Führen Sie eines der folgenden Verfahren aus:

    -   **Anforderung akzeptieren:** Wählen Sie **Remoteunterstützungsanforderung annehmen** aus, um der Remotesitzung beizutreten..

        Dem Benutzer wird die folgende Meldung angezeigt: **Ihre Anforderung wurde akzeptiert. Befolgen Sie die Anweisungen in Easy Assist, um ein Programm oder Ihren Desktop für Ihren Systemadministrator freizugeben**..

        > [!IMPORTANT]
        > Sie können keine Remoteunterstützungsanforderung von einem Mac-Computer annehmen, auf dem die Intune-Verwaltungskonsole ausgeführt wird.

    -   **Anforderung ablehnen:** Schließen Sie das Fenster **Problembehandlungsinformationen anzeigen**, und wählen Sie im Warnungseigenschaftsfenster dann **Diese Warnung schließen** aus.

        Die Anforderung wird geschlossen, und dem Benutzer wird eine Meldung angezeigt, die besagt, dass die Anforderung abgelehnt wurde. Wenn der Benutzer erneut eine Remoteunterstützung anfordern möchte, muss er eine neue Remoteunterstützungsanforderung senden. Wenn Sie versehentlich eine Remoteunterstützungswarnung schließen, wenden Sie sich an den Absender der Remoteunterstützungsanforderung, und bitten Sie diesen Benutzer, eine neue Anforderung zu senden.


<!--HONumber=May16_HO1-->


