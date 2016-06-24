---
# required metadata

title: Firewallrichtlinien für Windows-PCs | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9549c072-ac3d-4d14-a931-a2eda8846217

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Unterstützen des Schutzes von Windows-PCs mithilfe von Windows-Firewall-Richtlinien in Microsoft Intune
Microsoft Intune kann Ihnen auf verschiedene Weise helfen, Ihre Computer mit dem Intune-Client zu verwalten. Dies umfasst auch die Verwendung von Richtlinien, die Ihnen das Konfigurieren der Windows-Firewall-Einstellungen auf PCs ermöglichen.

Wenn Sie den Intune-Windows-PC-Client noch nicht auf Ihren Computern installiert haben, finden Sie unter [Installieren des Windows-PC-Clients mit Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md) weitere Informationen..

Verwenden Sie die Informationen in den folgenden Abschnitten, um Windows-Firewall-Richtlinien auf Windows-PCs zu konfigurieren, bereitzustellen und zu überwachen.

## Verwalten der Windows-Firewall mithilfe von Intune-Richtlinien
Mit der Windows-Firewall-Richtlinie können Sie Einstellungen erstellen und bereitstellen, von denen die Windows-Firewall auf verwalteten PCs gesteuert wird. Es ist nicht möglich, benutzerdefinierte Ausnahmen für die Windows-Firewall zu verwalten, und die Einstellungen haben keine Auswirkungen auf Firewalls anderer Hersteller.

> [!NOTE]
> Wenn sowohl die Microsoft Intune-Richtlinie als auch die Gruppenrichtlinie zur Verwaltung der gleichen Einstellung auf einem Computer konfiguriert sind, hat die Einstellung der Gruppenrichtlinie Vorrang vor der Microsoft Intune-Richtlinie. Weitere Informationen zur Vermeidung von Konflikten zwischen Intune-Richtlinien und Gruppenrichtlinien finden Sie unter [Lösen von Konflikten mit Gruppenrichtlinienobjekten und Microsoft Intune-Richtlinien](resolve-gpo-and-microsoft-intune-policy-conflicts.md)..
>
> Wenn Sie die Windows-Firewall-Einstellungen auf Computern mit Windows Vista bereitstellen möchten, müssen Sie auf diesen Computern zuerst [Hotfix KB971800](http://support2.microsoft.com/kb/971800) installieren.

> [!IMPORTANT]
> Zum Verwalten der Windows-Firewall mit Intune müssen Sie sicherstellen, dass die folgenden beiden Dienste auf dem Computer aktiviert sind, die Sie verwalten möchten:
>
> -   Windows-Firewall
> -   IPsec-Richtlinien-Agent

## Konfigurieren einer Windows-Firewall-Richtlinie

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) auf **Richtlinie** &gt; **Richtlinie hinzufügen**..

2.  Konfigurieren Sie eine Richtlinie für **Windows-Firewall-Einstellungen** , und stellen Sie sie bereit. Sie können die empfohlenen Einstellungen verwenden oder die Einstellungen anpassen. Weitere Informationen zum Erstellen und Bereitstellen von Richtlinien finden Sie unter [Allgemeine Aufgaben zur Verwaltung von Windows-PCs mit dem Microsoft Intune-Computerclient](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)..

    Im folgenden Abschnitt sind die Werte, die Sie in der Richtlinie konfigurieren können, sowie die Standardwerte aufgeführt, die verwendet werden, wenn Sie die Richtlinie nicht anpassen.

Nach Bereitstellen einer Windows-Firewall-Richtlinie können Sie ihren Status im Arbeitsbereich **Richtlinie** auf der Seite **Alle Richtlinien** anzeigen.

## Richtlinieneinstellungen für die Windows-Firewall

### Windows-Firewall einschalten

Mit diesen Richtlinien aktivieren Sie die Windows-Firewall auf verwalteten Computern, die mit einer Domäne (z. B. am Arbeitsplatz), einem privaten (vertrauenswürdigen) Netzwerk (z. B. einem Heimnetzwerk) oder einem nicht vertrauenswürdigen öffentlichen Netzwerk (z. B. in einem Internetcafé) verbunden sind. Der Standardwert für jede dieser Einstellungen ist **Ja** (der sicherste Wert). 



### Alle eingehenden Verbindungen blockieren, einschließlich der in der Liste der zugelassenen Programme

Mit diesen Richtlinieneinstellungen konfigurieren Sie die Windows-Firewall zum Blockieren von eingehendem Netzwerkverkehr auf verwalteten Computern, die mit einer Domäne (z. B. am Arbeitsplatz), einem privaten (vertrauenswürdigen) Netzwerk (z. B. einem Heimnetzwerk) oder einem nicht vertrauenswürdigen öffentlichen Netzwerk (z. B. in einem Internetcafé) verbunden sind. Der Standardwert für jede dieser Einstellungen ist **Ja** (der sicherste Wert). 

> [!IMPORTANT]
> Wenn in Ihrer Umgebung verwaltete Computer mit Windows Vista ohne installierte Service Packs vorhanden sind, müssen Sie entweder das Update installieren, das mit [Artikel 971800](http://go.microsoft.com/fwlink/?LinkId=188405) in der Microsoft Knowledge Base verknüpft ist, oder die Richtlinieneinstellung **Alle eingehenden Verbindungen blockieren** in den Richtlinien auf den entsprechenden Computern deaktivieren.

### Benutzer benachrichtigen, wenn ein neues Programm von der Windows-Firewall blockiert wird

Mit diesen Richtlinieneinstellungen konfigurieren Sie, ob die Windows-Firewall die PCs der Benutzer über das Blockieren von eingehendem Netzwerkverkehr auf verwalteten Computern benachrichtigt, die mit einer Domäne (z. B. am Arbeitsplatz), einem privaten (vertrauenswürdigen) Netzwerk (z. B. einem Heimnetzwerk) oder einem nicht vertrauenswürdigen öffentlichen Netzwerk (z. B. in einem Internetcafé) verbunden sind. Der Standardwert für jede dieser Einstellungen ist **Ja**..


### Vordefinierte Ausnahmen

Nachdem Sie die oben angegebenen grundlegenden Werte konfiguriert haben, können Sie Ausnahmen konfigurieren, die bestimmten durch die Firewall geleiteten Datenverkehr unabhängig von den oben konfigurierten Werten zulassen. Standardmäßig ist keine dieser Einstellungen konfiguriert.

|Name der Einstellung|Details|
|------------------|--------------------|
|**BranchCache - Inhaltsabruf**<br>(Windows 7 oder höher)|Ermöglicht BranchCache-Clients, mithilfe von HTTP im verteilten Modus Inhalte voneinander und im gehosteten Cachemodus Inhalte aus dem gehosteten Cache abzurufen. Bei dieser Einstellung wird HTTP verwendet.|
|**BranchCache - Gehosteter Cacheclient**<br>(Windows 7 oder höher)|Ermöglicht BranchCache-Clients, einen gehosteten Cache zu verwenden. Bei dieser Einstellung wird HTTPS verwendet.|
|**BranchCache - Gehosteter Cacheserver**|Ermöglicht BranchCache-Clients, einen gehosteten Cache zur Kommunikation mit anderen Clients zu verwenden. Bei dieser Einstellung wird HTTPS verwendet.|
|**BranchCache - Peerermittlung**<br>(Windows 7 oder höher)|Ermöglicht BranchCache-Clients, das WS Discovery-Protokoll zu verwenden, um die Verfügbarkeit von Inhalt im lokalen Subnetz zu ermitteln.|
|**BITS-Peercaching**|Ermöglicht Clients, BITS (Background Intelligent Transfer Service) zu verwenden, um Dateien zu finden und freizugeben, die im BITS-Cache von Clients im gleichen Subnetz gespeichert sind. Bei dieser Einstellung werden WSDAPI und RPC verwendet.|
|**Verbindung mit einem Netzwerkprojektor herstellen**|Ermöglicht Benutzer, zum Projizieren von Präsentationen über drahtgebundene oder Drahtlosnetzwerke eine Verbindung mit Projektoren herzustellen. Bei dieser Einstellung wird WSDAPI verwendet.|
|**Kernnetzwerk**|Ermöglicht Clients das Verwenden von IPv4 und IPv6, um Verbindungen mit Netzwerkressourcen herzustellen.|
|**Distributed Transaction Coordinator**|Ermöglicht verwalteten Computern, Transaktionen zu koordinieren, durch die transaktionsgeschützte Ressourcen wie Datenbanken, Nachrichtenwarteschlangen und Dateisysteme aktualisiert werden.|
|**Datei- und Druckerfreigabe**|Ermöglicht Benutzern, lokale Dateien und Drucker für andere Benutzer im Netzwerk freizugeben. Bei dieser Einstellung werden NetBIOS, LLMNR, SMB und RPC verwendet.|
|**Heimnetzgruppe**<br>(Windows 7 oder höher)|Ermöglicht verwalteten Computern die Teilnahme an einem Netzwerk des Typs Heimnetzgruppe.|
|**iSCSI-Dienst**|Ermöglicht verwalteten Computern das Herstellen von Verbindungen mit iSCSI-Servern und -Geräten.|
|**Schlüsselverwaltungsdienst**|Ermöglicht die Zählung von Computern zur Lizenzüberprüfung in Unternehmensumgebungen.|
|**Media Center Extenders**|Ermöglicht Media Center Extendern die Kommunikation mit Computern, auf denen Windows Media Center ausgeführt wird. Bei dieser Einstellung werden SSDP und qWave verwendet.|
|**Anmeldedienst**|Dient zum Konfigurieren eines Sicherheitskanals zwischen Domänenclients und einem Domänencontroller zum Authentifizieren von Benutzern und Diensten. Bei dieser Einstellung wird RPC verwendet.|
|**Netzwerkermittlung**|Ermöglicht, dass andere Geräte im Netzwerk von Computern erkannt werden, und die Computer ihrerseits von anderen Geräten im Netzwerk erkannt werden können. Bei dieser Einstellung werden Funktionssuchehost und Veröffentlichungsdienste sowie die Netzwerkprotokolle SSDP, NetBIOS, LLMNR und UPnPverwendet.|
|**Leistungsprotokolle und -warnungen**|Ermöglicht die Remoteverwaltung des Diensts für Leistungsprotokolle und -warnungen. Bei dieser Einstellung wird RPC verwendet.|
|**Remoteverwaltung**|Ermöglicht die Remoteverwaltung des Computers.|
|**Remoteunterstützung**|Diese Einstellung ermöglicht Benutzer verwalteter Computer Remoteunterstützung von anderen Benutzern im Netzwerk anzufordern. Bei dieser Einstellung werden die Netzwerkprotokolle SSDP, PNRP, Teredo und UPnP verwendet.|
|**Remotedesktop**|Ermöglicht dem Computer, Remotedesktop zu verwenden, um auf andere Computer zuzugreifen.|
|**Remote-Ereignisprotokollverwaltung**|Ermöglicht die Remoteanzeige bzw. -verwaltung von Clientereignisprotokollen. Bei dieser Einstellung werden Named Pipes und RPC verwendet.|
|**Remoteverwaltung geplanter Aufgaben**|Ermöglicht die Remoteverwaltung des Aufgabenplanungsdiensts. Bei dieser Einstellung wird RPC verwendet.|
|**Remotedienstverwaltung**|Ermöglicht die Remoteverwaltung lokaler Dienste auf Clients. Bei dieser Einstellung werden Named Pipes und RPC verwendet.|
|**Remotevolumeverwaltung**|Ermöglicht die Remoteverwaltung von Software- und Datenträgervolumes. Bei dieser Einstellung wird RPC verwendet.|
|**Routing und Remotezugriff**|Ermöglicht eingehende VPN- und Remotezugriffsverbindungen mit Computern.|
|**Secure Socket Tunneling-Protokoll**|Ermöglicht eingehende VPN-Verbindungen mit verwalteten Computern unter Verwendung des Secure Socket Tunneling-Protokolls (SSTP). Bei dieser Einstellung wird HTTPS verwendet.|
|**SNMP-Trap**|Ermöglicht verwalteten Computern das Empfangen von Datenverkehr vom SNMP-Ablaufverfolgungsdienst.|
|**UPnP-Framework**|Dient zum Konfigurieren des UPnP-Frameworkdiensts auf Computern, sodass UPnP-zertifizierte Geräte erkannt und verwendet werden können.|
|**Computernamen-Registrierungsdienst von Windows-Teamarbeit**|Ermöglicht Computern unter Verwendung des Peer Name Resolution-Protokolls nach anderen Computern zu suchen und mit diesen zu kommunizieren. Bei dieser Einstellung werden SSDP und PNRP verwendet.|
|**Windows Media Player**|Ermöglicht Benutzern das Empfangen von Streamingmedien über UDP.|
|**Windows Media Player-Netzwerkfreigabedienst**|Ermöglicht Benutzern das Freigeben von Medien über ein Netzwerk. Bei dieser Einstellung werden die Netzwerkprotokolle SSDP, qWave und UPnP verwendet.|
|**Windows Media Player-Netzwerkfreigabedienst (Internet)**<br>(Windows 7 oder höher)|Ermöglicht Benutzern, Heimmedien über das Internet freizugeben.|
|**Windows-Teamarbeit**|Ermöglicht Benutzern, über ein Netzwerk zusammenzuarbeiten, um Dokumente, Programme oder den Desktop freizugeben. Bei dieser Einstellung werden DFSR und P2P verwendet.|
|**Windows-Peer-zu-Peer-Zusammenarbeits-Foundation**|Dient zum Konfigurieren verschiedener Peer-zu-Peer-Programme und -Technologien, um ihnen das Herstellen von Verbindungen zu ermöglichen. Bei dieser Einstellung werden SSDP und PNRP verwendet.|
|**Windows-Remoteverwaltung (Kompatibilität)**|Ermöglicht die Remoteverwaltung verwalteter Computer unter Verwendung von WS-Management, einem auf Webdiensten basierenden Protokoll für die Remoteverwaltung von Betriebssystemen und Geräten.|
|**Windows-Remoteverwaltung**<br>(Windows 8 oder spätere Versionen)|Ermöglicht die Remoteverwaltung verwalteter Computer unter Verwendung von WS-Management, einem auf Webdiensten basierenden Protokoll für die Remoteverwaltung von Betriebssystemen und Geräten.|
|**Windows Virtual PC**<br>(Windows 7 oder höher)|Ermöglicht virtuellen Computern die Kommunikation mit anderen Computern.|
|**Tragbare Drahtlosgeräte**|Ermöglicht die Medienübertragung von einer netzwerkfähigen Kamera oder einem Mediengerät auf verwaltete Computer unter Verwendung des MTP-Protokolls (Media Transfer Protocol). Bei dieser Einstellung werden die Netzwerkprotokolle SSDP und UPnP verwendet.|

### Weitere Informationen:
[Richtlinien zum Schutz von Windows-PCs](policies-to-protect-windows-pcs-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


