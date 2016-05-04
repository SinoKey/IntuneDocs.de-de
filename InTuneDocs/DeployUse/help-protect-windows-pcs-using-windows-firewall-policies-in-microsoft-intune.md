---
title: Unterstützen des Schutzes von Windows-PCs mithilfe von Windows-Firewall-Richtlinien in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 62c44f36-d866-439e-8553-948cc0ea2504
author: robstackmsft
---
# Unterstützen des Schutzes von Windows-PCs mithilfe von Windows-Firewall-Richtlinien in Microsoft Intune
Microsoft Intune kann Ihnen helfen, Windows schützen Sie, mit dem Intune-Client eine Reihe von Möglichkeiten verwalten, einschließlich der Verwendung von Richtlinien, die auf PCs Windows Firewall-Einstellungen konfiguriert werden.

Wenn Sie den Computer mit Windows Intune-Client noch nicht auf Ihren Computern installiert haben, finden Sie unter [Installieren des Windows-PC-Clients mit Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

Verwenden Sie die Informationen in den folgenden Abschnitten können Sie konfigurieren, bereitstellen und Überwachen von Windows-Firewall-Richtlinien auf Windows-PCs.

## Verwenden von Intune-Richtlinien zum Verwalten der Windows-Firewall
Die Windows-Firewall-Richtlinie können Sie die Einstellungen, die steuern, die Windows-Firewall auf verwalteten PCs erstellen und bereitstellen. Es ist nicht möglich, benutzerdefinierte Ausnahmen für die Windows-Firewall zu verwalten, und die Einstellungen haben keine Auswirkungen auf Firewalls anderer Hersteller.

> [!NOTE]
> Wenn Microsoft Intune und der Gruppenrichtlinie zum Verwalten derselben Einstellung auf dem Computer konfiguriert sind, überschreibt die Einstellung der Gruppenrichtlinie die Microsoft Intune-Richtlinie. Weitere Informationen zur Vermeidung von Konflikten zwischen Intune und Gruppenrichtlinien finden Sie unter [Gruppenrichtlinienobjekt zu beheben und Windows Intune-Richtlinienkonflikte](resolve-gpo-and-microsoft-intune-policy-conflicts.md).
> 
> Wenn Sie die Windows-Firewall-Einstellungen auf Computern mit Windows Vista bereitstellen möchten, müssen Sie auf diesen Computern zuerst [Hotfix KB971800](http://support2.microsoft.com/kb/971800) installieren.

> [!IMPORTANT]
> Um die Windows-Firewall mithilfe von Intune verwalten möchten, müssen Sie sicherstellen, dass die folgenden beiden Dienste auf dem Computer aktiviert sind, die Sie verwalten möchten:
> 
> -   Windows-Firewall
> -   IPsec-Richtlinien-Agent

## So konfigurieren Sie eine Windows-Firewall-Richtlinie

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/)auf **Richtlinie** &gt; **Richtlinie hinzufügen**.

2.  Konfigurieren Sie eine Richtlinie für **Windows-Firewall-Einstellungen** , und stellen Sie sie bereit. Sie können die empfohlenen Einstellungen verwenden oder die Einstellungen anpassen. Sollten Sie weitere Informationen zum Erstellen und Bereitstellen von Richtlinien finden Sie unter den [Allgemeine Windows-PC-Verwaltungsaufgaben mit der Microsoft Intune-Computerclients](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) Thema.

    In den Tabellen unter dieser Vorgehensweise sind die Werte aufgeführt, die Sie in der Richtlinie konfigurieren können, sowie die empfohlenen Werte, die verwendet werden, wenn Sie die Richtlinie nicht anpassen.

Sie können die bereitgestellte Windows-Firewall-Richtlinie im Arbeitsbereich **Richtlinie** auf der Seite **Alle Richtlinien** ansehen.

## Richtlinieneinstellungen für die Windows-Firewall

### Windows-Firewall einschalten

|Name der Einstellung|Details|
|------------------|--------------------|
|**Domänenprofil**|Hiermit wird die Windows-Firewall auf verwalteten Computern aktiviert, wenn diese mit Domänennetzwerken verbunden sind, z. B. am Arbeitsplatz.<br /><br />Empfohlener Wert: **Ja**|
|**Privates Profil**|Hiermit wird die Windows-Firewall auf verwalteten Computern aktiviert, wenn diese mit vertrauenswürdigen Netzwerken verbunden sind, z. B. mit einem Heimnetzwerk.<br /><br />Empfohlener Wert: **Ja**|
|**Öffentliches Profil**|Hiermit wird die Windows-Firewall auf verwalteten Computern aktiviert, wenn diese mit nicht vertrauenswürdigen Netzwerken an öffentlichen Orten verbunden sind, z. B. in Internetcafés.<br /><br />Empfohlener Wert: **Ja**<br /><br />Erforderliches Betriebssystem: windowsvista oder höher|

### Alle eingehenden Verbindungen blockieren, einschließlich der in der Liste der zugelassenen Programme
> [!IMPORTANT]
> Wenn in Ihrer Umgebung verwaltete Computer mit Windows Vista ohne installierte Service Packs vorhanden sind, müssen Sie entweder das Update installieren, das mit [Artikel 971800](http://go.microsoft.com/fwlink/?LinkId=188405) in der Microsoft Knowledge Base verknüpft ist, oder die Richtlinieneinstellung **Alle eingehenden Verbindungen blockieren** in den Richtlinien auf den entsprechenden Computern deaktivieren.

|Name der Einstellung|Details|
|------------------|--------------------|
|**Domänenprofil**|Hiermit werden alle eingehenden Verbindungen blockiert, wenn die Computer mit Domänennetzwerken verbunden sind, z. B. am Arbeitsplatz. Dazu gehören auch Verbindungen in der Liste mit Ausnahmen.<br /><br />Empfohlener Wert: **Nein**|
|**Privates Profil**|Hiermit werden alle eingehenden Verbindungen blockiert, wenn die Computer mit vertrauenswürdigen Netzwerken verbunden sind, z. B. mit einem Heimnetzwerk. Dazu gehören auch Verbindungen in der Liste mit Ausnahmen.<br /><br />Empfohlener Wert: **Nein**|
|**Öffentliches Profil**|Hiermit werden alle eingehenden Verbindungen blockiert, wenn die Computer mit nicht vertrauenswürdigen Netzwerken an öffentlichen Orten verbunden sind, z. B. in Internetcafés. Dazu gehören auch Verbindungen in der Liste mit Ausnahmen.<br /><br />Empfohlener Wert: **Nein**<br /><br />Erforderliches Betriebssystem: windowsvista oder höher|

### Benutzer benachrichtigen, wenn ein neues Programm von der Windows-Firewall blockiert wird

|Name der Einstellung|Details|
|------------------|--------------------|
|**Domänenprofil**|Benutzer werden benachrichtigt, wenn von der Windows-Firewall ein neues Programm blockiert wird, während die Computer mit Domänennetzwerken verbunden sind, z. B. am Arbeitsplatz.<br /><br />Empfohlener Wert: **Ja**|
|**Privates Profil**|Benutzer werden benachrichtigt, wenn von der Windows-Firewall ein neues Programm blockiert wird, während die Computer mit vertrauenswürdigen Netzwerken verbunden sind, z. B. mit einem Heimnetzwerk.<br /><br />Empfohlener Wert: **Ja**|
|**Öffentliches Profil**|Benutzer werden benachrichtigt, wenn von der Windows-Firewall ein neues Programm blockiert wird, während die Computer mit nicht vertrauenswürdigen Netzwerken an öffentlichen Orten verbunden sind, z. B. in Internetcafés.<br /><br />Empfohlener Wert: **Ja**<br /><br />Erforderliches Betriebssystem: windowsvista oder höher|

### Vordefinierte Ausnahmen

|Name der Einstellung|Details|
|------------------|--------------------|
|**BranchCache –Inhaltsabruf**|Ist diese Einstellung aktiviert, werden von BranchCache-Clients mithilfe von HTTP im verteilten Modus Inhalte voneinander und im gehosteten Cachemodus Inhalte aus dem gehosteten Cache abgerufen. Bei dieser Einstellung wird HTTP verwendet.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows 7 oder höher).|
|**BranchCache –Gehosteter Cacheclient**|Ist diese Einstellung aktiviert, wird von BranchCache-Clients ein gehosteter Cache verwendet. Bei dieser Einstellung wird HTTPS verwendet.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows 7 oder höher).|
|**BranchCache –Gehosteter Cacheserver**|Ist diese Einstellung aktiviert, kann von BranchCache-Clients ein gehosteter Cache zur Kommunikation mit anderen Clients verwendet werden. Bei dieser Einstellung wird HTTPS verwendet.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows 7 oder höher).|
|**BranchCache –Peerermittlung**|Ist diese Einstellung aktiviert, kann von BranchCache-Clients das WS-Suchprotokoll verwendet werden, um die Verfügbarkeit von Inhalt im lokalen Subnetz zu ermitteln.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows 7 oder höher).|
|**BITS-Peercaching**|Ist diese Einstellung aktiviert, kann von den Clients BITS (Background Intelligent Transfer Service) verwendet werden, um Dateien zu finden und freizugeben, die im BITS-Cache von Clients im gleichen Subnetz gespeichert sind. Bei dieser Einstellung werden WSDAPI und RPC verwendet.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**Verbindung mit einem Netzwerkprojektor herstellen**|Ist diese Einstellung aktiviert, können Benutzer zum Projizieren von Präsentationen über verkabelte oder Drahtlosnetzwerke eine Verbindung zu Projektoren herstellen. Bei dieser Einstellung wird WSDAPI verwendet.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**Kernnetzwerk**|Ist diese Einstellung aktiviert, kann von Clients IPv4 und IPv6 verwendet werden, um Verbindungen mit Netzwerkressourcen herzustellen.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**Distributed Transaction Coordinator**|Ist diese Einstellung aktiviert, können von verwalteten Computern Transaktionen koordiniert werden, durch die transaktionsgeschützte Ressourcen wie Datenbanken, Nachrichtenwarteschlangen und Dateisysteme aktualisiert werden.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**Datei- und Druckerfreigabe**|Ist diese Einstellung aktiviert, können Benutzer lokale Dateien und Drucker für andere Benutzer im Netzwerk freigeben. Bei dieser Einstellung werden NetBIOS, LLMNR, SMB und RPC verwendet.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows XP oder spätere Versionen).|
|**Heimnetzgruppe**|Ist diese Einstellung aktiviert, wird verwalteten Computern die Teilnahme an einem Heimnetzgruppen-Netzwerk ermöglicht.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows 7 oder höher).|
|**iSCSI-Dienst**|Ist diese Einstellung aktiviert, wird verwalteten Computern das Herstellen von Verbindungen zu iSCSI-Servern und -Geräten ermöglicht.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**Schlüsselverwaltungsdienst**|Ist diese Einstellung aktiviert, wird die Zählung von Computern zur Lizenzüberprüfung in Unternehmensumgebungen ermöglicht.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**Media Center Extenders**|Ist diese Einstellung aktiviert, wird Media Center Extendern die Kommunikation mit Computern ermöglicht, auf denen Windows Media Center ausgeführt wird. Bei dieser Einstellung werden SSDP und qWave verwendet.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**Anmeldedienst**|Ist diese Einstellung aktiviert, wird zwischen Domänenclients und einem Domänencontroller ein Sicherheitskanal zum Authentifizieren von Benutzern und Diensten konfiguriert. Bei dieser Einstellung wird RPC verwendet.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**Netzwerkermittlung**|Ist diese Einstellung aktiviert, können andere Geräte im Netzwerk von Computern erkannt werden, und die Computer können ihrerseits von anderen Geräten im Netzwerk erkannt werden. Bei dieser Einstellung werden Funktionssuchehost und Veröffentlichungsdienste sowie die Netzwerkprotokolle SSDP, NetBIOS, LLMNR und UPnPverwendet.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**Leistungsprotokolle und -warnungen**|Ist diese Einstellung aktiviert, wird die Remoteverwaltung des Diensts für Leistungsprotokolle und -warnungen ermöglicht. Bei dieser Einstellung wird RPC verwendet.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**Remoteverwaltung**|Ist diese Einstellung aktiviert, wird die Remoteverwaltung des Computers ermöglicht.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**Remoteunterstützung**|Ist diese Einstellung aktiviert, können Benutzer verwalteter Computer Remoteunterstützung von anderen Benutzern im Netzwerk anfordern. Bei dieser Einstellung werden die Netzwerkprotokolle SSDP, PNRP, Teredo und UPnP verwendet.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows XP oder spätere Versionen).|
|**Remotedesktop**|Ist diese Einstellung aktiviert, kann vom Computer Remotedesktop verwendet werden, um auf andere Computer zuzugreifen.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows XP oder spätere Versionen).|
|**Remote-Ereignisprotokollverwaltung**|Ist diese Einstellung aktiviert, wird die Remoteanzeige bzw. -verwaltung von Client-Ereignisprotokollen ermöglicht. Bei dieser Einstellung werden Named Pipes und RPC verwendet.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**Remoteverwaltung geplanter Aufgaben**|Ist diese Einstellung aktiviert, wird die Remoteverwaltung des Aufgabenplanungsdiensts ermöglicht. Bei dieser Einstellung wird RPC verwendet.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**Remotedienstverwaltung**|Ist diese Einstellung aktiviert, wird die Remoteverwaltung lokaler Dienste auf Clients ermöglicht. Bei dieser Einstellung werden Named Pipes und RPC verwendet.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**Remotevolumeverwaltung**|Ist diese Einstellung aktiviert, wird die Remoteverwaltung von Software- und Datenträgervolumes ermöglicht. Bei dieser Einstellung wird RPC verwendet.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**Routing und Remotezugriff**|Ist diese Einstellung aktiviert, werden eingehende VPN- und Remotezugriffsverbindungen mit Clients ermöglicht.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**Secure Socket Tunneling-Protokoll**|Ist diese Einstellung aktiviert, werden eingehende VPN-Verbindungen mit verwalteten Computern unter Verwendung des Secure Socket Tunneling-Protokolls (SSTP) ermöglicht. Bei dieser Einstellung wird HTTPS verwendet.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**SNMP-Trap**|Ist diese Einstellung aktiviert, wird verwalteten Computern das Empfangen von SNMP-Ablaufverfolgungsdienst-Verkehr ermöglicht.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**UPnP-Framework**|Ist diese Einstellung aktiviert, wird der UPnP-Frameworkdienst auf Computern konfiguriert, sodass UPnP-zertifizierte Geräte erkannt und verwendet werden können.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows XP oder spätere Versionen).|
|**Computernamen-Registrierungsdienst von Windows-Teamarbeit**|Ist diese Einstellung aktiviert, kann von Computern unter Verwendung des Peer Name Resolution-Protokolls nach anderen Computern gesucht und mit diesen kommuniziert werden. Bei dieser Einstellung werden SSDP und PNRP verwendet.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**Windows Media Player**|Ist diese Einstellung aktiviert, können Benutzer Streaming Media über UDP empfangen.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**Windows Media Player-Netzwerkfreigabedienst**|Ist diese Einstellung aktiviert, können Benutzer Medien über ein Netzwerk freigeben. Bei dieser Einstellung werden die Netzwerkprotokolle SSDP, qWave und UPnP verwendet.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**Windows Media Player-Netzwerkfreigabedienst (Internet)**|Ist diese Einstellung aktiviert, können Benutzer Heimmedien über das Internet freigeben.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows 7 oder höher).|
|**Windows-Teamarbeit**|Ist diese Einstellung aktiviert, können Benutzer über ein Netzwerk zusammenarbeiten, um Dokumente, Programme oder den Desktop freizugeben. Bei dieser Einstellung werden DFSR und P2P verwendet.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**Windows-Peer-zu-Peer-Zusammenarbeits-Foundation**|Ist diese Einstellung aktiviert, wird Peer-zu-Peer-Programmen und -Technologien das Herstellen von Verbindungen ermöglicht. Bei dieser Einstellung werden SSDP und PNRP verwendet.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**Windows-Remoteverwaltung (Kompatibilität)**|Ist diese Einstellung aktiviert, wird die Remoteverwaltung des Clients unter Verwendung von WS-Verwaltung festgelegt, einem auf Webdiensten basierenden Protokoll für die Remoteverwaltung von Betriebssystemen und Geräten.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|
|**Windows-Remoteverwaltung**|Ist diese Einstellung aktiviert, wird die Remoteverwaltung des Clients unter Verwendung von WS-Verwaltung festgelegt, einem auf Webdiensten basierenden Protokoll für die Remoteverwaltung von Betriebssystemen und Geräten.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows 8 oder spätere Versionen)|
|**Windows Virtual PC**|Ist diese Einstellung aktiviert, wird virtuellen Computern die Kommunikation mit anderen Computern ermöglicht.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Nur Windows 7)|
|**Tragbare Drahtlosgeräte**|Ist diese Einstellung aktiviert, wird die Medienübertragung von einer netzwerkfähigen Kamera oder einem Mediengerät auf verwaltete Computer unter Verwendung des Media Transfer-Protokolls (MTP) ermöglicht. Bei dieser Einstellung werden die Netzwerkprotokolle SSDP und UPnP verwendet.<br /><br />Empfohlener Wert: „Nicht konfiguriert“<br /><br />(Windows Vista oder höher).|

### Siehe auch
[Verwalten von Windows-PCs mit Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md)



<!--HONumber=Mar16_HO4-->


