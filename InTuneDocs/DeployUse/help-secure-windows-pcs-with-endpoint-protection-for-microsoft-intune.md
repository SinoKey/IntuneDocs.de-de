---
Titel: Schützen der Windows-PCs mit Endpoint Protection für Microsoft Intune
MS.Custom: Na
MS.Reviewer: Na
MS.Service: Microsoft Intune
MS.Suite: Na
MS.tgt_pltfrm: Na
MS.topic: Artikel
MS.AssetId: 682a83ec-bcf4-46ed-9a74-61b87b6a86a3
Autor: NathBarn
---
# Schützen von Windows-PCs mit Endpoint Protection für Microsoft Intune
[!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)] können Sie zum Sichern des verwalteten Computers auf vielfältige Weise einschließlich Endpoint Protection Echtzeitschutz gegen malwarebedrohungen geboten, Malwaredefinitionen auf dem aktuellen gehalten und Computer werden automatisch überprüft. [!INCLUDE[epshort](./includes/epshort_md.md)] bietet außerdem Tools, mit denen Sie zum Verwalten und Überwachen von Malware-Angriffe

Wenn Sie noch nicht installiert haben die [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] Client auf Ihren Computern finden Sie unter [Installieren des Windows-PC-Clients mit Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

Verwenden Sie die Informationen in den folgenden Abschnitten können Sie konfigurieren, bereitstellen und Überwachen [!INCLUDE[epshort](./includes/epshort_md.md)].

## Verwenden von Endpoint Protection in Microsoft Intune

### Vorbereitung
Eine ihrer wichtigsten Aufgaben als IT-Administrator besteht darin, die von Ihnen verwalteten Computer frei von Malware und Viren zu halten. Bevor Sie [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)] auf Clientcomputern in Ihrer Organisation bereitstellen, sollten Sie entscheiden, wie Sie Ihre Computer schützen. Hierzu wählen Sie eine der folgenden Optionen aus und konfigurieren die zugehörigen Richtlinieneinstellungen:

|Ziel:|Richtlinieneinstellungen für Endpoint Protection|Weitere Informationen|
|--------------|---------------------------------------|--------------------|
|Verwendung [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)][!INCLUDE[epshort](./includes/epshort_md.md)] nur, wenn keine endpunktschutzanwendung eines Drittanbieters installiert ist<br /><br />Sie können [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)][!INCLUDE[epshort](./includes/epshort_md.md)] auf allen Computern, auf denen keine endpunktschutzanwendung eines Drittanbieters installiert ist.|Endpointprotection installieren = **Ja**<br /><br />Endpointprotection aktivieren = **Ja**<br /><br />Endpoint Protection installieren, auch wenn eine endpunktschutzanwendung von Drittanbietern installiert ist = **Nr.**|Wenn die endpunktschutzanwendung eines Drittanbieters erkannt wird, [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)][!INCLUDE[epshort](./includes/epshort_md.md)] nicht installiert oder deinstalliert werden, wenn es bereits installiert wurde.|
|Mit [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)][!INCLUDE[epshort](./includes/epshort_md.md)], selbst wenn die endpunktschutzanwendung eines Drittanbieters installiert ist<br /><br />Bei dieser Vorgehensweise führen Sie [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)][!INCLUDE[epshort](./includes/epshort_md.md)] und die von Drittanbietern Endpoint Protection-Anwendung (sofern installiert) gleichzeitig. Von einer solchen Konfiguration wird aufgrund möglicher Leistungsprobleme abgeraten.|Endpointprotection installieren = **Ja**<br /><br />Endpointprotection aktivieren = **Ja**<br /><br />Endpoint Protection installieren, auch wenn eine endpunktschutzanwendung von Drittanbietern installiert ist = **Ja**|Zu verwenden in folgenden Fällen:<br /><br />-Sie wechseln möchten [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)][!INCLUDE[epshort](./includes/epshort_md.md)].<br />-Der Bereitstellung eines neuen Clients, das verwendet wird [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)][!INCLUDE[epshort](./includes/epshort_md.md)]<br />-Sie aktualisieren einen Client, wird [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)][!INCLUDE[epshort](./includes/epshort_md.md)].|
|Verwendung [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)] ohne [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)][!INCLUDE[epshort](./includes/epshort_md.md)]<br /><br />In diesem Fall Sie nicht verwenden [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)][!INCLUDE[epshort](./includes/epshort_md.md)] zum Schutz Ihrer Computer vor Malware und Viren. Stattdessen greifen Sie auf die Endpunktschutzanwendung eines Drittanbieters zurück.|Endpointprotection installieren = **Nr.**|Wenn Sie keine Endpunktschutzanwendung eines Drittanbieters verwenden, wird von dieser Konfiguration abgeraten, denn in diesem Fall wären die Computer in Ihrer Organisation anfällig für Malware oder andere Angriffe.<br /><br />[!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)][!INCLUDE[epshort](./includes/epshort_md.md)] nicht installiert ist, und er wird deinstalliert, wenn es zuvor installiert war.|
Wenn Sie von Ihrer aktuellen endpunktschutzanwendung zu wechseln möchten [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)][!INCLUDE[epshort](./includes/epshort_md.md)], verwenden Sie die folgenden Schritte aus, die weiter unten in diesem Thema ausführlicher erläutert werden:

1.  Beenden Sie Ihre aktuelle Endpunktschutzanwendung nicht, während Sie die [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)]-Clientsoftware auf den betreffenden Computern bereitstellen.

2.  Überprüfen Sie, ob [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)][!INCLUDE[epshort](./includes/epshort_md.md)] installiert ist und Absichern Clientcomputer verwendet.

3.  Entfernen Sie die Endpunktschutzsoftware des Drittanbieters auf folgende Weise:

    -   Stellen Sie über die [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)]-Softwareverteilung ein Tool des Herstellers der Endpunktschutzanwendung bereit, mit dessen Hilfe diese entfernt werden kann. Weitere Informationen finden Sie unter [Bereitstellen und Konfigurieren von apps mit Microsoft Intune](deploy-and-configure-apps-with-microsoft-intune.md).

    -   Entfernen Sie die von einem Drittanbieter stammende Endpunktschutzanwendung manuell.

> [!NOTE]
> Endpunktschutzanwendungen von Drittanbietern werden von [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] nicht deinstalliert.

### <a name="BKMK_HowtoConf"></a>So konfigurieren Sie Microsoft Intune Endpoint Protection
Konfigurieren Sie mithilfe des folgenden Verfahrens [!INCLUDE[epshort](./includes/epshort_md.md)] für [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)]. [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] Verwalten [!INCLUDE[epshort](./includes/epshort_md.md)] für Windows 10 Technical Preview. Bestimmte Richtlinieneinstellungen sind nur für Windows 10 verfügbar.

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/)auf **Richtlinie** &gt; **Richtlinie hinzufügen**.

2.  Konfigurieren und Bereitstellen einer **Microsoft Intune-Agent-Einstellungen** Richtlinie für die [!INCLUDE[epshort](./includes/epshort_md.md)] Einstellungen. Sie können die empfohlenen Einstellungen verwenden oder die Einstellungen anpassen. Sollten Sie weitere Informationen zum Erstellen und Bereitstellen von Richtlinien finden Sie unter den [Allgemeine Windows-PC-Verwaltungsaufgaben mit der Microsoft Intune-Computerclients](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) Thema.

    In den Tabellen unter dieser Vorgehensweise sind die Werte aufgeführt, die Sie in der Richtlinie konfigurieren können, sowie die empfohlenen Werte, die verwendet werden, wenn Sie die Richtlinie nicht anpassen. Sie finden diese Einstellungen im Bereich **Endpoint Protection** .

Sehen Sie die bereitgestellte [!INCLUDE[epshort](./includes/epshort_md.md)] -Richtlinie auf die **alle Richtlinien** auf der Seite der **Richtlinie** Arbeitsbereich.

#### Endpoint Protection-Diensteinstellungen

|Richtlinieneinstellung|Weitere Informationen|
|------------------|--------------------|
|**Endpoint Protection installieren**|Legen Sie auf **Ja** Installieren [!INCLUDE[epshort](./includes/epshort_md.md)] auf verwalteten Computern. Wenn während der Installation die endpunktschutzanwendung eines Drittanbieters erkannt wird [!INCLUDE[epshort](./includes/epshort_md.md)] nicht installiert werden, wenn **Endpoint Protection installieren, auch wenn eine endpunktschutzanwendung von Drittanbietern installiert ist** Wert **Ja**. **Hinweis:** Intune [!INCLUDE[epshort](./includes/epshort_md.md)] wird auf verwalteten Computern standardmäßig installiert. Wenn Sie nicht möchten, [!INCLUDE[epshort](./includes/epshort_md.md)] auf verwalteten Computern installiert ist, müssen Sie diese Richtlinie auf explizit festlegen **Nr.**. Wenn [!INCLUDE[epshort](./includes/epshort_md.md)] zuvor installiert war und die Richtlinie aktualisiert, sodass **keine**, und klicken Sie dann die [!INCLUDE[epshort](./includes/epshort_md.md)] Clients deinstalliert werden.<br />Empfohlener Wert: **Ja**|
|**Endpoint Protection auch dann installieren, wenn eine Endpunktschutzanwendung von Drittanbietern installiert ist**|Legen Sie auf **Ja** Installieren [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)][!INCLUDE[epshort](./includes/epshort_md.md)] selbst wenn die endpunktschutzanwendung eines Drittanbieters erkannt wird.<br /><br />Empfohlener Wert: **Ja**|
|**Aktivieren von Endpoint Protection**|Legen Sie auf **Ja** aktivieren [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)][!INCLUDE[epshort](./includes/epshort_md.md)] auf dem Computer, für die die [!INCLUDE[epshort](./includes/epshort_md.md)] Client.<br /><br />Wenn auf festgelegt **Nr.**, und [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)][!INCLUDE[epshort](./includes/epshort_md.md)] installiert ist, die [!INCLUDE[epshort](./includes/epshort_md.md)] Client-Benutzeroberfläche wird Benutzern nicht angezeigt und alle Schutzfunktionen sind inaktiv.<br /><br />Empfohlener Wert: **Ja**|
|**Clientbenutzeroberfläche deaktivieren**|Legen Sie auf **Ja** Ausblenden der [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)][!INCLUDE[epshort](./includes/epshort_md.md)] Client-Benutzeroberfläche von Benutzern (erfordert einen Neustart des Clientcomputers wirksam wird).<br /><br />Empfohlener Wert: **Nein**|
|**Endpoint Protection auch dann installieren, wenn eine Endpunktschutzanwendung von Drittanbietern installiert ist**|Legen Sie auf **Ja** erzwingen die Installation von [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)][!INCLUDE[epshort](./includes/epshort_md.md)], selbst wenn die endpunktschutzanwendung eines Drittanbieters erkannt wird.<br /><br />Empfohlener Wert: **Nein**|
|**Vor der Entfernung von Malware einen Systemwiederherstellungspunkt erstellen**|Legen Sie hier **Ja** fest, um vor dem Entfernen von Malware einen Windows-Systemwiederherstellungspunkt zu erstellen.<br /><br />Empfohlener Wert: **Ja**|
|**Behandelte Malware nachverfolgen (Tage)**|Hiermit ist es [!INCLUDE[epshort](./includes/epshort_md.md)] möglich, erkannte Malware für einen festgelegten Zeitraum nachzuverfolgen, damit Sie vormals infizierte verwaltete Computer manuell überprüfen können.<br /><br />Sie können einen Wert zwischen 0 und 30 Tagen angeben.<br /><br />Empfohlener Wert: **7 Tage**|
Wenn Sie die Richtlinienwerte für festgelegt haben **Endpoint Protection installieren** und **Endpoint Protection aktivieren** zu **Ja**, und den Richtlinienwert für  **Endpoint Protection installieren, auch wenn eine endpunktschutzanwendung von Drittanbietern installiert ist** zu **keine**, [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)][!INCLUDE[epshort](./includes/epshort_md.md)] erkennt, dass eine andere endpunktschutzanwendung installiert ist, und werden nicht installiert oder deinstalliert, wenn es bereits vorhanden ist (jedoch [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)][!INCLUDE[epshort](./includes/epshort_md.md)] meldet die Integrität der anderen endpunktschutzanwendung in der [!INCLUDE[wit_adminconsole](./includes/wit_adminconsole_md.md)]).

#### Einstellungen für den Echtzeitschutz

|Richtlinieneinstellung|Weitere Informationen|
|------------------|--------------------|
|**Echtzeitschutz aktivieren**|Hiermit werden Überwachung und Überprüfung aller Dateien und Anwendungen aktiviert, auf die zugegriffen wird. Zudem werden schädliche Dateien oder Anwendungen blockiert, bevor sie auf Computern ausgeführt werden können.<br /><br />Empfohlener Wert: **Ja**|
|**Alle Downloads werden überprüft**|Hiermit wird die Überprüfung aller Dateien und Anhänge aktiviert, die aus dem Internet auf Clientcomputer heruntergeladen werden.<br /><br />Empfohlener Wert: **Ja**|
|**Datei- und Programmaktivität auf Computern überwachen**|Hiermit wird die Überwachung eingehender und ausgehender Dateien sowie von Programmaktivitäten auf Computern aktiviert. Mit dieser Einstellung wird von [!INCLUDE[epshort](./includes/epshort_md.md)] überwacht, wann die Ausführung von Dateien und Programmen beginnt, und Sie werden über alle Aktionen informiert, die von bzw. an ihnen durchgeführt werden.<br /><br />Empfohlener Wert: **Ja**|
|**Überwachte Dateien**|Wenn **Datei- und Programmaktivität auf Computern überwachen** aktiviert ist, ermöglicht es Ihnen diese Einstellung, auszuwählen, ob nur eingehende, nur ausgehende oder alle Dateien überwacht werden.<br /><br />Empfohlener Wert: **Alle Dateien überwachen**|
|**Aktivieren der Verhaltensüberwachung**|Ermöglicht [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)][!INCLUDE[epshort](./includes/epshort_md.md)] auf bestimmte verdächtige Aktivitäten auf den Clientcomputern geprüft.<br /><br />Empfohlener Wert: **Ja**|
|**Netzwerkinspektionssystem aktivieren**|Hiermit wird das Netzwerkinspektionssystem (NIS) auf Clientcomputern aktiviert. Im NIS werden Signaturen bekannter Sicherheitsrisiken aus dem [Microsoft Malware Protection Center (Microsoft Center zum Schutz vor Malware)](http://go.microsoft.com/fwlink/?LinkId=234249) verwendet, um schädlichen Netzwerkdatenverkehr zu erkennen und zu blockieren.<br /><br />Empfohlener Wert: **Ja**|

#### Einstellungen für den Überprüfungszeitplan

|Richtlinieneinstellung|Weitere Informationen|
|------------------|--------------------|
|**Eine tägliche Schnellüberprüfung planen**|Hiermit wird eine tägliche Schnellüberprüfung von häufig verwendeten Dateien und wichtigen Systemdateien auf verwalteten Computern geplant. Diese Schnellüberprüfung wirkt sich geringfügig auf die Leistung aus.<br /><br />Empfohlener Wert: **Ja**|
|**Eine Schnellüberprüfung ausführen, wenn zwei aufeinander folgende Schnellüberprüfungen verpasst wurden**|Hiermit wird [!INCLUDE[epshort](./includes/epshort_md.md)] so konfiguriert, dass automatisch eine Schnellüberprüfung auf Computern ausgeführt wird, wenn bei diesen zwei aufeinanderfolgende geplante Schnellüberprüfungen verpasst wurden.<br /><br />Empfohlener Wert: **Ja**|
|**Vollständige Überprüfung planen**|Hiermit wird eine vollständige Überprüfung aller Dateien und Ressourcen auf den lokalen Festplatten der Computer konfiguriert. Diese Überprüfung kann einige Zeit in Anspruch nehmen und sich abhängig von der Anzahl der überprüften Dateien und Ressourcen auf die Computerleistung auswirken.<br /><br />Empfohlener Wert: **Nein**|
|**Eine vollständige Überprüfung ausführen, wenn zwei aufeinander folgende vollständige Überprüfungen verpasst wurden**|Hiermit wird [!INCLUDE[epshort](./includes/epshort_md.md)] so konfiguriert, dass automatisch eine vollständige Überprüfung auf Computern ausgeführt wird, wenn bei diesen zwei aufeinanderfolgende geplante vollständige Überprüfungen verpasst wurden.<br /><br />Empfohlener Wert: Nicht konfiguriert|

#### Einstellungen für Überprüfungsoptionen

|Richtlinieneinstellung|Weitere Informationen|
|------------------|--------------------|
|**Nach der Installation von Endpoint Protection eine vollständige Überprüfung ausführen**|Hiermit wird [!INCLUDE[epshort](./includes/epshort_md.md)] so konfiguriert, dass nach der Installation auf Computern automatisch eine vollständige Systemüberprüfung durchgeführt wird. Um Auswirkungen auf die Benutzerproduktivität zu minimieren, wird diese Überprüfung nur ausgeführt, wenn sich die entsprechenden Computer im Leerlauf befinden.<br /><br />Empfohlener Wert: **Ja**|
|**Bei Bedarf automatisch eine vollständige Überprüfung nach der Beseitigung von Malware ausführen**|Legen Sie auf **Ja** können [!INCLUDE[epshort](./includes/epshort_md.md)] automatisch eine vollständige Überprüfung auf Computern ausgeführt, nach der Beseitigung von Malware, um zu bestätigen, dass andere Dateien nicht betroffen waren.<br /><br />Empfohlener Wert: **Ja**|
|**Geplante Überprüfung nur starten, wenn sich der Computer im Leerlauf befindet**|Legen Sie hier **Ja** fest, um zu verhindern, dass geplante Überprüfungen auf Computern gestartet werden, während diese benutzt werden, und so eine Beeinträchtigung der Benutzerproduktivität zu vermeiden.<br /><br />Empfohlener Wert: **Ja**|
|**Vor dem Start der Überprüfung die aktuellsten Malwaredefinitionen abrufen**|Legen Sie auf **Ja** können [!INCLUDE[epshort](./includes/epshort_md.md)] automatisch die aktuellsten Malwaredefinitionen gesucht, vor dem Beginn einer Überprüfung auf Computern.<br /><br />Empfohlener Wert: **Ja**|
|**Archivdateien überprüfen**|Legen Sie auf **Ja** konfigurieren [!INCLUDE[epshort](./includes/epshort_md.md)] zum Scannen nach Malware Archivdateien (z. B. ZIP- oder CAB-Dateien) auf dem Computer.<br /><br />Empfohlener Wert: **Nein**|
|**Scannen von E-Mail-Nachrichten**|Legen Sie auf **Ja** konfigurieren [!INCLUDE[epshort](./includes/epshort_md.md)] auf eingehende e-Mail-Nachrichten beim Eingang auf Computern überprüft werden.<br /><br />Empfohlener Wert: **Ja**|
|**Dateien überprüfen, die in freigegebenen Netzwerkordnern geöffnet wurden**|Legen Sie auf **Ja** konfigurieren [!INCLUDE[epshort](./includes/epshort_md.md)] Dateien überprüfen, die aus freigegebenen Ordnern im Netzwerk geöffnet werden. In der Regel sind dies Dateien, auf die über einen UNC-Pfad zugegriffen wird. Die Aktivierung dieser Funktion kann Benutzern Probleme bereiten, die nur über Lesezugriff verfügen, da sie Malware nicht entfernen können.<br /><br />Empfohlener Wert: **Nein**|
|**Zugeordnete Netzwerklaufwerke überprüfen**|Legen Sie auf **Ja** konfigurieren [!INCLUDE[epshort](./includes/epshort_md.md)] Dateien auf zugeordneten Netzwerklaufwerken überprüft. Die Aktivierung dieser Funktion kann Benutzern Probleme bereiten, die nur über Lesezugriff verfügen, da sie Malware nicht entfernen können.<br /><br />Empfohlener Wert: **Nein**|
|**Wechseldatenträger überprüfen**|Legen Sie auf **Ja** konfigurieren [!INCLUDE[epshort](./includes/epshort_md.md)] zum Scannen von Malware und unerwünschte Software in den Inhalt von Wechseldatenträgern wie USB-Flashlaufwerke, wenn Sie eine vollständige Überprüfung auf Computern ausführen.<br /><br />Empfohlener Wert: **Ja**|
|**Prozessornutzung während der Überprüfung begrenzen auf**|Hiermit wird der maximale Prozentsatz der Prozessornutzung festgelegt, der bei geplanten Überprüfungen auf Clientcomputern beansprucht werden darf. Sie können hierfür einen Wert zwischen 1 und 100 Prozent festlegen.<br /><br />Empfohlener Wert: **50 %**|

#### Standardeinstellungen für Aktionen

|Richtlinieneinstellung|Weitere Informationen|
|------------------|--------------------|
|**Auswählen, wie von Endpoint Protection mit Malware der folgenden Warnstufen verfahren werden soll**|Hiermit wird die Standardaktion angegeben, die von [!INCLUDE[epshort](./includes/epshort_md.md)] durchgeführt wird, wenn Malware verschiedener Warnstufen erkannt wird.<br /><br />Sie können für jede Warnstufe festlegen, dass die Malware entfernt oder in Quarantäne versetzt oder die von Microsoft empfohlene Aktion ausgeführt wird.<br /><br />Empfohlener Wert: **Empfohlene Aktion**|

#### Einstellungen für ausgeschlossene Dateien und Ordner

|Richtlinieneinstellung|Weitere Informationen|
|------------------|--------------------|
|**Von der Überprüfung oder dem Echtzeitschutz auszuschließende Dateien und Ordner**|Hiermit können Sie auf Computern bestimmte Dateien oder Ordner von der Überprüfung oder vom Echtzeitschutz ausschließen.|

#### Einstellungen für ausgeschlossene Prozesse

|Richtlinieneinstellung|Weitere Informationen|
|------------------|--------------------|
|**Prozesse, die beim Ausführen einer Überprüfung oder bei Verwendung des Echtzeitschutzes auszuschließen sind**|Hiermit können Sie bestimmte Prozesse von der Überprüfung oder vom Echtzeitschutz ausschließen. Sie können nur Dateien mit den folgenden Erweiterungen ausschließen: **.exe**, **.com** oder **.scr**.|

#### Einstellungen für ausgeschlossene Dateitypen

|Richtlinieneinstellung|Weitere Informationen|
|------------------|--------------------|
|**Dateierweiterungen, die beim Ausführen einer Überprüfung oder bei Verwendung des Echtzeitschutzes auszuschließen sind**|Hiermit können Sie auf Computern bestimmte Dateinamenserweiterungen von der Überprüfung oder vom Echtzeitschutz ausschließen.|

#### Einstellungen für Microsoft Active Protection Service
Microsoft Active Protection Service ist eine Online-Community, die Ihnen hilft zu entscheiden, wie Sie auf potenzielle Bedrohungen reagieren. Diese Community trägt auch dazu bei, die Weiterverbreitung neuer Infektionen mit Malware zu unterbinden.

|Richtlinieneinstellung|Weitere Informationen|
|------------------|--------------------|
|**Microsoft Active Protection Service beitreten**|Bei**Ja** werden automatisch Informationen zu erkannter Malware an den Microsoft Active Protection Service gesendet. Microsoft verwendet die auf diese Weise erfassten Informationen nicht, um Sie zu identifizieren oder mit Ihnen Kontakt aufzunehmen.<br /><br />Empfohlener Wert: **Ja**|
|**Mitgliedschaftsebene**|Wenn Sie sich dafür entschieden haben, dem Microsoft Active Protection Service beizutreten, können Sie über diese Einstellung eine der folgenden Mitgliedschaftsebenen auswählen:<br /><br />**Grundlegende** – grundlegenden Informationen zu erkannter Malware an Microsoft gesendet. Hierzu gehören Angaben dazu, woher die Software stammt, welche Aktionen Sie anwenden oder von [!INCLUDE[epshort](./includes/epshort_md.md)] automatisch angewendet werden, und ob diese Aktionen erfolgreich waren.<br /><br />**Erweiterte** -Weitere Informationen zu Malware, Spyware und potenziell unerwünschte Software an Microsoft gesendet. Hierzu gehören Angaben zu dem Speicherort der Software, den Dateinamen, der Funktionsweise der Software und der Auswirkung der Software auf Ihren Computer.<br /><br />Empfohlener Wert: **Erweitert**|
|**Dynamische Definitionen auf Basis von Microsoft Active Protection Service-Berichten empfangen**|**Ja** kann von Computern dynamische Malwaredefinitionen basierend auf Informationen empfangen, [!INCLUDE[epshort](./includes/epshort_md.md)] sendet an den Microsoft Active Protection Service (Wenn Sie es hinzugefügt haben) zu erkannter Malware.<br /><br />Empfohlener Wert: **Ja**|

### Verwaltungsaufgaben für Endpoint Protection
Mithilfe der folgenden Aufgaben können Sie verschiedene Verwaltungsaufgaben auf verwalteten Computern ausführen, auf denen [!INCLUDE[epshort](./includes/epshort_md.md)] ausgeführt wird.

|Ziel:|Über die [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)]-Konsole|Auf dem verwalteten Computer|
|-------------|--------------------------------------------------------------------------|-----------------------------|
|Update für Malwaredefinitionen ausführen|Wählen Sie im Arbeitsbereich **Gruppen** die zu aktualisierenden Computer aus.<br /><br />Klicken Sie auf **Remoteaufgaben** &gt; **Update für Malwaredefinitionen ausführen**.|Starten Sie die [!INCLUDE[epshort](./includes/epshort_md.md)]-Clientsoftware über den Windows-Benachrichtigungsbereich.<br /><br />Klicken Sie zunächst auf die Registerkarte **Aktualisieren** und dann auf **Aktualisieren**.|
|Malwareüberprüfung ausführen|Wählen Sie im Arbeitsbereich **Gruppen** die zu überprüfenden Computer aus.<br /><br />Klicken Sie auf **Vollständige Malwareüberprüfung ausführen** oder auf **Malwareschnellüberprüfung ausführen**.|Starten Sie die [!INCLUDE[epshort](./includes/epshort_md.md)]-Clientsoftware über den Windows-Benachrichtigungsbereich.<br /><br />Wählen Sie **Schnell**, **Vollständig**oder **Benutzerdefiniert**aus, und klicken Sie auf **Jetzt überprüfen**.|
Sie können den Status eines Remotetasks anzeigen, indem Sie auf die **Remoteaufgaben** Link in der unteren rechten Ecke der [!INCLUDE[wit_adminconsole](./includes/wit_adminconsole_md.md)].

Im Dialogfeld **Status des Remote-Tasks** werden aktuelle Remoteaufgaben, ihr Status, der Gerätename und etwaige berichtete Fehler ggf. mit einem Link zu Problembehandlungsinformationen aufgelistet.

### <a name="BKMK_SCEPmon"></a>So überwachen Sie Endpoint Protection
Sie können den Malwarestatus Ihrer Computer mithilfe des Arbeitsbereichs **Schutz** der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/)überwachen. Dieser Arbeitsbereich enthält zwei Seiten:

|Name der Seite|Weitere Informationen|
|-------------|--------------------|
|**Übersicht über Endpoint Protection**|Hier werden wichtige Probleme als Links angezeigt, die Sie anklicken können, um weitere Informationen zu erhalten. Die folgenden Arten von Problemen können angezeigt werden:<br /><br />**Malwareinstanzen, die nachverfolgung erfordern** – Klicken Sie auf den Link, um eine Liste mit malwareproblemen sowie den Schritten nach der Aktion, die ausgeführt werden, um das Problem zu beheben. Sie können sich über diese Liste auch anzeigen lassen, welche Computer betroffen sind.<br /><br />**Computer mit Malware, die nachverfolgung erfordern** – Klicken Sie auf den Link, um alle Computer mit ungelösten malwareproblemen sowie Aktion, die ausgeführt werden, um das Problem zu beheben.<br /><br />**Geräte, die nicht geschützt sind,** – Klicken Sie auf den Link, um Computer anzuzeigen, die nicht von keiner endpunktschutzsoftware geschützt sind, weil keine Software installiert ist, oder weil ein Fehler auftritt. Wählen Sie einen Computer aus, um weitere Details anzuzeigen.<br /><br />**Geräte mit einem anderen Endpoint Protection wird ausgeführt** – Klicken Sie auf den Link, um Computer anzuzeigen, die endpunktschutzanwendung eines Drittanbieters ausgeführt werden.|
|**Sämtliche Malware**|Hiermit wird eine Liste der gesamten auf Ihren Computern gefundenen aktiven Malware angezeigt. Sie können sich über diese Liste auch alle Computer anzeigen lassen, die von einer bestimmten Malware betroffen sind, oder eine der folgenden Aufgaben auswählen:<br /><br />**Anzeigen von Eigenschaften** – wird eine Seite mit weiteren Informationen zur ausgewählten Schadsoftware geöffnet.<br /><br />**Informationen zu dieser Malware** – wird ein Thema über das Microsoft Malware Protection Center mit weiteren Informationen zur Schadsoftware geöffnet.|
> [!IMPORTANT]
> Der Arbeitsbereich **Schutz** wird in der Administratorkonsole erst angezeigt, wenn Sie den Client installiert haben und Sie mindestens einen Computerclient erfolgreich verwalten.

### Anzeigen der letzten Erkennungspfade für Malware auf Computern
Intune kann die Pfade der 10 zuletzt erkannten Instanzen von Malware auf einem Gerät anzeigen. Die Option **Letzter Erkennungspfad** ist standardmäßig deaktiviert. So aktivieren Sie diese Anzeige:

##### Aktivieren letzter Erkennungspfade für Malware

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) auf **Gruppen** &gt; **Alle Geräte** . **Malware**.

2.  Klicken Sie mit der rechten Maustaste auf eine Spaltenüberschrift. Eine Liste der verfügbaren Spalten wird angezeigt.

3.  Aktivieren Sie das Kontrollkästchen **Letzte Erkennungspfade** in der Liste. Die Spalte **Letzte Erkennungspfade** wird angezeigt. Sie enthält bis zu 10 der zuletzt auf dem Gerät überwachten Malwareinstanzen.

## Benötigen Sie weitere Hilfe?
Weitere Hilfe und Support finden Sie unter [Problembehandlung bei Endpoint Protection in Microsoft Intune](troubleshoot-endpoint-protection-in-microsoft-intune.md).

## Siehe auch
[Verwalten von Windows-PCs mit Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md)



<!--HONumber=Mar16_HO1-->


