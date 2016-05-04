---
title: Aktualisieren Ihrer Windows-PCs mit Softwareupdates in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 64ba8e58-fab1-4480-a440-164268810138
author: robstackmsft
---
# Aktualisieren Ihrer Windows-PCs mit Softwareupdates in Microsoft Intune
Microsoft Intune kann Ihnen helfen, Ihre verwalteten Computer in verschiedene Arten, einschließlich der Verwaltung von Softwareupdates, die Ihren Computern aktuell zu halten, indem sichergestellt wird, die neuesten Patches und Software schnell Updates installiert werden.

Wenn Sie den Intune-Client noch nicht auf Ihren Computern installiert haben, finden Sie unter [Installieren des Windows-PC-Clients mit Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

Wenn neue Updates von Microsoft Update verfügbar sind oder ein Drittanbieter-Update erstellt haben und sie auf die verwalteten Computer anwendbar sind, wird eine Benachrichtigung angezeigt, auf die **Übersicht über die** auf der Seite der **Updates** Arbeitsbereich. Klicken Sie auf diesen Benachrichtigungslink, dann können Sie verschiedene Vorgänge durchführen. Sie können beispielsweise weitere Informationen zum Update anzeigen, das Update genehmigen oder ablehnen und die Computer anzeigen, auf denen das Update im Falle der Genehmigung installiert wird.

> [!IMPORTANT]
> Der Arbeitsbereich **Updates** wird in der Administratorkonsole erst angezeigt, wenn Sie den Client installiert haben und Sie mindestens einen Computerclient erfolgreich verwalten.

Wenn Updates genehmigt und installiert werden, können Sie überprüfen den Erfolg oder Fehlschlag der Installation in der **Updates** Arbeitsbereich der Intune-Konsole.

Verwenden Sie die Informationen in den folgenden Abschnitten, um die Software auf den von Ihnen verwalteten Computern auf dem aktuellen Stand zu halten.

## Vorbereitung
Bevor Sie mit dem Erstellen und Genehmigen von Softwareupdates beginnen, konfigurieren Sie Richtlinien, mit denen gesteuert wird, wann und wie die Updates installiert werden, und stellen Sie diese auf Ihren Computern bereit.

### So konfigurieren Sie Einstellungen für Updaterichtlinien

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/)auf **Richtlinie** &gt; **Übersicht** &gt; **Richtlinie hinzufügen**.

2.  Konfigurieren Sie eine Richtlinie für **Microsoft Intune-Agent-Einstellungen** für die Update-Einstellungen, und stellen Sie sie bereit. Sie können die empfohlenen Einstellungen verwenden oder die Einstellungen anpassen. Sollten Sie weitere Informationen zum Erstellen und Bereitstellen von Richtlinien finden Sie unter den [Allgemeine Windows-PC-Verwaltungsaufgaben mit der Microsoft Intune-Computerclients](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) Thema.

In den folgenden Tabellen sind die Werte, die Sie in der Richtlinie konfigurieren können, sowie die empfohlenen Werte aufgeführt, die verwendet werden, wenn Sie die Richtlinie nicht anpassen. Sie finden diese Einstellungen im Bereich **Updates** .

  |Richtlinieneinstellung|Details|
    |------------------|--------------------|
    |**Häufigkeit der Suche nach Updates und Anwendungen (Stunden)**|Gibt an, wie häufig (aus 8 bis 22 Stunden) Intune überprüft, ob neue Updates und Anwendungen.<br /><br />Empfohlener Wert: **8** Stunden.|
    |**Automatische Installation von Updates und Anwendungen oder Installation auf Aufforderung**|Hiermit wird festgelegt, ob Updates automatisch installiert werden, oder ob vor der Installation eine Benutzeraufforderung angezeigt wird. Darüber hinaus können Sie mit dieser Einstellung die Installation von Updates und Anwendungen planen.<br /><br />**Updates und Anwendungen automatisch wie geplant installieren**  installiert, Updates und Anwendungen, die mit dem angegebenen Zeitplan.<br /><br /> **Automatische Wartung für Windows-Computer verwenden**  ist eine abhängige Richtlinieneinstellung und gibt an, dass Updates und Anwendungen während des automatischen Wartungsfensters von Windows installiert werden.<br /><br />**Benutzer zur Installation auffordern** fordert den Benutzer auf Updates zu installieren, wenn sie bereit sind.<br /><br />Empfohlene Werte:<br /><br />**Updates und Anwendungen automatisch wie geplant installieren** ausgewählten<br /><br />**Geplant am: Täglich**<br /><br />**Geplante Zeit: 03:00 Uhr**<br /><br />**Automatische Wartung für Windows-Computer verwenden** ausgewählten|
    |**Sofortige Installation von Updates zulassen, die Windows nicht unterbrechen**|**Ermöglichen** installiert Updates sofort nach dem Herunterladen, außer Updates, die Unterbrechung oder einem Neustart von Windows. Diese Updates werden entsprechend der Konfiguration der Einstellung **Automatische Installation oder Updateinstallation nach Aufforderung** installiert.<br /><br />**Erlauben Sie keine** installiert Updates laut Konfiguration der **automatische Updateinstallation oder Updateinstallation auf Aufforderung** Einstellung.<br /><br />Empfohlener Wert: **Allow**|
    |**Verzögerung des Windows-Neustarts nach der Installation geplanter Updates und Anwendungen (in Minuten)**|Hiermit wird angegeben, wie lange nach der Installation geplanter Updates und Anwendungen gewartet werden soll, bevor Windows neu gestartet wird. Der Wertebereich liegt zwischen 1 und 30 Minuten.<br /><br />Empfohlener Wert: **15 Minuten**|
    |**Verzögerung nach einem Windows-Neustart bis zum Beginn der Installation verpasster geplanter Updates und Anwendungen (Minuten)**|Hiermit wird festgelegt, wie viel Zeit nach einem Windows-Neustart verstreichen darf, bis mit der Installation von Updates und Anwendungen begonnen wird, wenn ein geplantes Update verpasst wurde. Der Wertebereich liegt zwischen 1 und 60 Minuten.<br /><br />Empfohlener Wert: **5 Minuten**|
    |**Angemeldetem Benutzer die Steuerung des Windows-Neustarts nach der Installation geplanter Updates und Anwendungen gestatten**|Gibt an, ob der angemeldete Benutzer Windows-Neustart verzögern kann (wenn auf festgelegt **Ja**), oder informiert wird, den automatischen Neustart von Windows (wenn auf festgelegt **keine**). Wenn zum Zeitpunkt der Installation geplanter Updates und Anwendungen kein Benutzer angemeldet ist, wird Windows bei Bedarf automatisch neu gestartet. Bei der Einstellung **Nein**ist die Zeit bis zum Windows-Neustart standardmäßig auf 5 Minuten festgelegt.<br /><br />Empfohlener Wert: **Ja**|
    |**Aufforderung zum Neustart von Windows während obligatorischer Updates des Intune-Client-agent**|Gibt an, ob der angemeldete Benutzer wird aufgefordert, Windows neu zu starten, wenn ein obligatorisches Update des Intune-Client neu starten von Windows erforderlich sind.<br /><br />Empfohlener Wert: **Ja**|
    |**Zeitplan für die Installation von obligatorischen Updates des Client-Agents von Microsoft Intune**|Hiermit wird geplant, wann die Installation von Clientupdates stattfindet.<br /><br />Empfohlener Wert: "nicht konfiguriert"|
    |**Verzögerung zwischen Aufforderungen zum Neustart von Windows nach Installation geplanter Updates und Anwendungen (in Minuten)**|Hiermit wird angegeben, wie häufig der Benutzer aufgefordert wird, Windows neu zu starten, wenn nach der Installation eines Updates oder eine Anwendung ein Windows-Neustart erforderlich ist und der Benutzer diesen Neustart verzögert. Der Wertebereich liegt zwischen 1 und 1440 Minuten.<br /><br />Empfohlener Wert: **30 Minuten**|

## Aktualisieren von Microsoft-Software
Das Aktualisieren von Microsoft-Software ist sehr unkompliziert. Bevor Sie jedoch beginnen, müssen Sie zweierlei konfigurieren:

-   **Produktkategorien und Updateklassifizierungen:** Hiermit werden die Kategorien und Klassifizierungen der Updates definiert, die Sie auf Computern verfügbar machen möchten. Sie können beispielsweise festlegen, dass nur kritische Updates für Microsoft Office installiert werden.

-   **Automatische Genehmigungsregeln:** Mit diesen Regeln werden bestimmte Arten von Updates automatisch genehmigt, wodurch der Verwaltungsaufwand verringert wird. Sie sollten beispielsweise automatisch alle kritischen Softwareupdates genehmigen.

Bereiten Sie die Verwendung von Softwareupdates mithilfe der folgenden beiden Verfahren vor:

### Konfigurieren Sie die Produktkategorien und Updateklassifizierungen, die Sie auf verwalteten Computern verfügbar machen möchten.

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/)auf **Verwaltung** &gt; **Updates**.

2.  Wählen Sie auf der Seite **Diensteinstellungen: Updates** in der Liste **Produktkategorie** die Updatekategorien aus, die Sie auf Computern verfügbar machen möchten. Beachten Sie, dass die am häufigsten verwendeten Updates standardmäßig aktiviert sind.

    > [!IMPORTANT]
    > Um sicherzustellen, dass der Computer die Updates zu erhalten, die vom Administrator genehmigt wurden die Windows Server Update Services (WSUS) Gruppenrichtlinien-Einstellung **angeben Intranet Microsoft-Updatedienst** muss auf Computern, die mit Intune registriert wurden nicht angewendet werden.

3.  Wählen Sie in der Liste **Updateklassifizierung** die Updateklassen aus, die Sie auf verwalteten Computern verfügbar machen möchten. Auch hier sind die am häufigsten verwendeten Optionen standardmäßig aktiviert.

4.  Klicken Sie auf **Speichern** , um Ihre Auswahl zu speichern.

### So konfigurieren Sie automatische Genehmigungsregeln für Softwareupdates

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/)auf **Verwaltung** &gt; **Updates**.

2.  Klicken Sie im Bereich **Automatische Genehmigungsregeln** der Seite **Servereinstellungen: Updates** auf **Neu**.

3.  Geben Sie auf der Seite **Allgemein** des Assistenten zum Erstellen von automatischen Genehmigungsregeln einen Namen und optional eine Beschreibung für die Regeln an.

4.  Wählen Sie auf der Seite **Produktkategorien** alle Produkte aus, für die Updates automatisch genehmigt werden sollen.

5.  Geben Sie auf der Seite **Updateklassifizierungen** die Updateklassifizierungen an, die automatisch genehmigt werden sollen.

6.  Gehen Sie auf der Seite **Bereitstellung** folgendermaßen vor:

    -   Wählen Sie die Computergruppen aus, für die die neue Regel bereitgestellt werden soll, und klicken Sie auf **Hinzufügen**.

    -   Aktivieren Sie zum Angeben eines Installationszeitlimits für die Updates das Kontrollkästchen **Erzwingen Sie ein Installationszeitlimit für diese Updates** , und wählen Sie aus der Liste **Installationszeitlimit** ein Installationszeitlimit aus.

        > [!NOTE]
        > Wenn Sie ein Installationszeitlimit angeben, muss der verwaltete Computer nach Ablauf des entsprechenden Intervalls möglicherweise einmal oder mehrmals neu gestartet werden.

    -   Klicken Sie danach auf **Weiter**.

7.  Überprüfen Sie auf der Seite **Zusammenfassung** die Einstellungen für die neue Regel, und klicken Sie dann auf **Fertig stellen**.

Die neue Regel wird im Bereich **Automatische Genehmigungsregeln** auf der Seite **Diensteinstellungen: Updates** angezeigt.

> [!NOTE]
> Wenn Sie eine Regel zur automatischen Genehmigung erstellen, es nur zukünftige Updates genehmigt und bereits vorhandene Updates bereits in Intune werden nicht automatisch genehmigt. Zum Genehmigen dieser Updates müssen Sie die automatische Genehmigungsregel ausführen.
### So können Sie eine Regel für die automatische Genehmigung von Updates bearbeiten, ausführen oder löschen

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/)auf **Verwaltung** &gt; **Updates**.

2.  Wählen Sie im Bereich **Automatische Genehmigungsregeln** eine Regel aus, und führen Sie dann einen der folgenden Schritte aus:

    -   Klicken Sie zum Bearbeiten der Regel auf **Bearbeiten**, und ändern Sie dann im **Assistenten für automatische Update-Genehmigungsregeln**die Parameter der Regel.

    -   Klicken Sie zum Ausführen der Regel auf **Ausgewählten Satz ausführen**.

    -   Klicken Sie zum Löschen der Regel auf **Löschen**.

        > [!NOTE]
        > Das Löschen einer Regel hat keine Auswirkungen auf vorherige Updates, die durch diese Regel genehmigt wurden.

## Aktualisieren von Software, die nicht von Microsoft herausgegeben wird
Sie können Updates für Software bereitstellen, die nicht von Microsoft stammt. Hierzu verwenden Sie den **Assistenten zum Hochladen von Updates** , mit dem Sie das Update in Ihren Cloud Speicher hochladen; danach können Sie das Update ebenso wie bei Microsoft-Software genehmigen oder ablehnen.

### So laden Sie ein Drittanbieterupdate hoch und konfigurieren es

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/)auf **Updates** &gt; **Übersicht** &gt; **Hochladen**.

2.  Klicken Sie auf der Seite **Updatedateien** auf **Durchsuchen** , um die Setupdateien auszuwählen, die zur Installation des Updatepakets benötigt werden. Hierbei kann es sich um eine Windows Installer-Datei (MSI), eine Windows Installer-Patchdatei (MSP) oder eine Programmdatei (EXE) handeln. Außerdem können Sie ggf. zusätzliche Dateien oder Ordner einschließen, die sich im selben Ordner wie die Setupdatei befinden.

    Die Gesamtgröße der ausgewählten hochzuladenden Dateien wird angezeigt. Beachten Sie, dass diese Größe nicht die unkomprimierten Größen der Installationsdateien beinhaltet.

3.  Nachdem Sie die Setupdateien angegeben haben die **Updatebeschreibung** Seite zeigt den Namen, die Beschreibung und die Klassifizierung für Softwareinformationen, die Intune aus den softwaresetupdateien extrahiert. Sie können eine Klassifizierung auswählen, um den Typ des bereitzustellenden Updates zu markieren (Updates, Kritische Updates, Sicherheitsupdates, Updaterollups oder Service Packs). Klicken Sie auf **Weiter** , wenn Sie fertig sind.

4.  Auf der **Anforderungen** Seite des Assistenten wählen Sie die Architektur (32-Bit, 64-Bit- oder beides) und die Betriebssysteme der verwalteten Computer, auf denen dieses Update anwendbar sein soll.

5.  Auf der **Erkennungsregeln** geben wie Intune bestimmt, ob das Update bereits auf verwalteten Computern vorhanden ist. Wenn Sie die Standardoption verwenden **Verwenden Sie die standarderkennungsregeln**, Intune immer installiert das Update-Paket auf jedem Zielcomputer einmal.

    > [!NOTE]
    > Wenn es sich bei der von Ihnen angegebenen Updatesetupdatei um eine Windows Installer- oder MSP-Datei handelt, wird die Seite **Erkennungsregeln** des Assistenten nicht angezeigt. Dies liegt daran, dass Windows Installer- und MSP-Dateien über eigene Anweisungen zum Erkennen vorheriger Updateinstallationen verfügen.

    Wählen Sie mindestens eine der folgenden Regeln aus, um festzustellen, ob das Update bereits auf verwalteten Computern installiert ist:

    -   **Die Datei ist vorhanden.**

    -   **Der MSI-Produktcode ist vorhanden.**

    -   **Der Registrierungsschlüssel ist vorhanden.**

6.  Geben Sie ggf. weitere Informationen an, die zur Konfiguration der Erkennungsregeln erforderlich sind – beispielsweise einen Dateipfad und -namen, den Windows Installer-Produktcode oder einen Registrierungsschlüssel –, und klicken Sie dann auf **Weiter**.

7.  Auf der Seite **Erforderliche Komponenten** des Assistenten geben Sie an, welche Software bereits installiert sein muss, damit dieses Update installiert werden kann. Sie können angeben, **keine**, wählen Sie ein Softwarepaket, das bereits hinzugefügt wurde, und von Intune verwaltet wird oder Sie können einen der folgenden Regeln zur Beschreibung der Software angeben:

    -   **Die Datei ist vorhanden.**

    -   **Der MSI-Produktcode ist vorhanden.**

    -   **Der Registrierungsschlüssel ist vorhanden.**

8.  Geben Sie ggf. weitere Informationen an, die zur Konfiguration der Erkennungsregeln erforderlich sind – beispielsweise einen Dateipfad und -namen, den Windows Installer-Produktcode oder einen Registrierungsschlüssel –, und klicken Sie dann auf **Weiter**.

9. Auf der Seite **Befehlszeilenargumente** des Assistenten können Sie erforderliche Installationseigenschaften zur Installationsbefehlszeile hinzufügen, um das Verhalten der Setupdatei zu ändern. Beispielsweise unterstützen verschiedene Softwareprogramme die **/q** Eigenschaft zur Aktivierung der automatischen Installation. Weitere Informationen zu unterstützten Befehlszeilenargumenten finden Sie in der Dokumentation zu Ihrem Softwarepaket. Geben Sie ggf. erforderliche Befehlszeilenargumente an, und klicken Sie dann auf **Weiter**.

    > [!NOTE]
    > Wenn das Update keine automatische Installation unterstützt, können keine Installation des Updates mit Intune

10. Auf der Seite **Rückgabecodes** des Assistenten können Sie angeben, wie Rückgabecodes der Updateinstallation interpretiert werden. Standardmäßig verwendet Intune branchenüblichen Rückgabecodes, um eine fehlerhafte oder erfolgreiche Installation eines Updatepakets zu melden. Die bereitgestellten Rückgabecodes sind:

|Rückgabecode|Details|
|---------------|------------------|
|**0**|Erfolgreich|
|**3010**|Erfolg mit Neustart|
    
11. Alle nicht aufgeführten Rückgabecodes weisen auf Fehler bei der Installation hin.
Bei einigen Updates gelten die Standardinterpretationen für Rückgabecodes nicht. In diesem Fall können Sie eigene Interpretationen für die Rückgabecodes angeben.

12. Geben Sie die erforderlichen Rückgabecodes an, oder bearbeiten Sie sie, und klicken Sie dann auf **Weiter**.

13. Überprüfen Sie auf der Seite **Zusammenfassung** des Assistenten die Aktionen, die ausgeführt werden, und klicken Sie dann auf **Hochladen** , um den Assistenten abzuschließen.

Das hochgeladene Update wird in Ihrem Intune-cloudspeicher gespeichert. Wenn nicht mehr ausreichend freier Speicherplatz zur Verfügung steht, um das Updatepaket hochzuladen, werden Sie während des Uploadprozesses darauf hingewiesen. Intune kann nicht über genügend freien Speicherplatz erst bestimmen, nach das Hochladen des Updates gestartet wurde, weil für komprimierte Setup- und Installationsdateien mehr Speicherplatz benötigt, wenn sie entpackt werden. F

Nachdem es in Intune hochgeladen wurde, wird ein Update von Drittanbietern im der **aktualisiert** Arbeitsbereich in der **alle Updates** Bereich. Sie können das Update dann genehmigen und bereitstellen. Weitere Informationen finden Sie unter der [genehmigen und Ablehnen von Updates](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md#BKMK_Approve1) in diesem Thema.

## Genehmigen und Ablehnen von Updates
Wenn Updates zur Installation bereit sind, wird auf der Seite **Updateübersicht** des Arbeitsbereichs **Updates** unter **Updatestatus**eine Meldung angezeigt. Klicken Sie auf diese Meldung, um die Seite **Alle Updates** zu öffnen und die Updates anzuzeigen, die zur Genehmigung bereit sind.

Mithilfe der Liste **Filter** können Sie das Suchen nach Updates erleichtern. Beispielsweise können Sie nur fehlgeschlagene oder aber nur solche Updates auflisten, die abgelöst werden.

Wenn Sie ein Update aus der Liste auswählen, werden weitere Befehle verfügbar, mit denen Sie Updates verwalten können. Diese sind in der folgenden Tabelle aufgeführt:

|Aufgabe|Details|
|--------|--------------------|
|**Eigenschaften anzeigen**|Hiermit werden ausführliche Informationen zum Update einschließlich der Anzahl der Computer angezeigt, auf die dieses Update angewendet werden kann.|
|**Bearbeiten**|Nur für nicht von Microsoft stammende Updates. Hiermit können Sie die Eigenschaften des Updates bearbeiten.|
|**Genehmigen**|Hiermit wird das ausgewählte Update genehmigt und Ihnen ermöglicht, die Gruppen zu konfigurieren, in denen es bereitgestellt wird. Weitere Informationen finden Sie im Verfahren [So genehmigen Sie Updates](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md#BKMK_Approve) in diesem Thema.|
|**Ablehnen**|Hiermit werden alle früheren Genehmigungen für das Update zurückgezogen, und das Update wird in den Standardansichten ausgeblendet. Darüber hinaus werden alle Berichtsdaten für das Update entfernt.<br /><br />Wenn Sie zu einem späteren Zeitpunkt nach einem abgelehnten Updates suchen möchten, legen Sie für den Filter auf der Seite **Alle Updates** die Einstellung **Abgelehnt**fest. Sie können das Update dann erforderlichenfalls genehmigen.<br /><br />Wenn ein Update abgelehnt wurde, weil das Update in Microsoft Update abgelaufen war, kann nicht das Update in der Intune-Verwaltungskonsole genehmigt werden.<br /><br />Wenn Sie eine Richtlinie für Updates löschen, die auf Computern bereitgestellt wurde, werden die Werte dieser Updateeinstellungen auf den Standardstatus für das installierte Betriebssystem zurückgesetzt.|
|**Löschen**|Nur für nicht von Microsoft stammende Updates. Hiermit wird das ausgewählte Update gelöscht.|
|**Hochladen**|Startet die **Hochladen von Updates** Assistenten, mit dem Sie zum Hochladen von nicht-Microsoft-Updates, die Sie bereitstellen möchten.|

### <a name="BKMK_Approve"></a>So genehmigen Sie Updates

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/)auf **Updates** &gt; **Übersicht** &gt; **Neue zu genehmigende Updates**.

    Klicken Sie im Arbeitsbereich **Updates** auf **Übersicht** &gt; **Neue zu genehmigende Updates**.

    > [!NOTE]
    > Der Link **Neue zu genehmigende Updates** wird nur dann im Bereich **Updatestatus** angezeigt, wenn mindestens ein verwalteter Computer vorhanden ist, für den ein Update genehmigt werden muss.

2.  Wählen Sie ein Update aus, überprüfen Sie unten auf der Seite die Updateeigenschaften, um sich zu vergewissern, dass Sie das Update genehmigen möchten, und klicken Sie dann auf **Genehmigen**. Sie können mehrere Updates auswählen, halten die **STRG** -Taste auswählen.

3.  Wählen Sie auf der Seite **Gruppen auswählen** eine Gruppe aus, für die Sie die Updates bereitstellen möchten, und klicken Sie auf **Hinzufügen**. Wenn Sie alle Gruppen ausgewählt haben, klicken Sie auf **Weiter**.

4.  Führen Sie auf der Seite **Bereitstellungsaktion** folgende Schritte für jede Gruppe in der Liste aus:

    -   Wählen Sie in der Liste **Genehmigung** eine der folgenden Optionen aus:

        -   **Erforderliche Installation** -das Update auf Computern in der angegebenen Gruppe installiert.

        -   **Nicht installieren** - berichtet nur die Anwendbarkeit und das Update zu installieren.

        -   **Verfügbare Installation:** Der Benutzer kann die Anwendung bei Bedarf über das Unternehmensportal installieren.

        -   **Deinstallieren Sie** -entfernt Updates von Computern in der Zielgruppe.

            > [!IMPORTANT]
            > Das Update wird entfernt, selbst wenn er nicht von Intune installiert wurde.

    -   Wählen Sie in der Liste **Stichtag** eine der folgenden Optionen aus:

        -   **Keine** -Gibt an, dass wird kein Stichtag für die Installation des Updates erzwungen, und Benutzer können das Update immer wieder ablehnen.

        -   **So bald wie möglich** -das Update wird bei nächster Gelegenheit auf allen Zielcomputern installiert.

        -   **Benutzerdefinierte** -Gibt das Datum und die Uhrzeit, zu dem genehmigte Updates installiert sind.

        -   **Eine Woche**, **Zwei Wochen**, **Ein Monat** : Hiermit wird das Update innerhalb des angegebenen Zeitraums installiert.

5.  Klicken Sie auf **Fertig stellen** , um die Einstellungen zu speichern, oder klicken Sie auf **Abbrechen** , um die Einstellungen zu verwerfen und zur Updateliste zurückzukehren.

    > [!IMPORTANT]
    > Wenn die Aktion **Nicht installieren**, **Erforderliche Installation**oder **Deinstallieren** nicht explizit für eine untergeordnete Gruppe konfiguriert wurde, wird eine Aktion, die für eine übergeordnete Gruppe konfiguriert wurde, von allen dieser Gruppe untergeordneten Gruppen geerbt.

6.  Sie können unten auf der Seite **Alle Updates** im Detailbereich überprüfen, ob Erinnerungsmeldungen zu dem Update vorhanden sind.


### Siehe auch
[Verwalten von Windows-PCs mit Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md)



<!--HONumber=Mar16_HO4-->


