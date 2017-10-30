---
title: Early Edition
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a2e6fd2381286aa652a04b5ed34ab21c57ed85f6
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2017
---
# <a name="the-early-edition-for-microsoft-intune---october-2017"></a>Die Early Edition für Microsoft Intune – Oktober 2017

Die **Early Edition** enthält eine Liste der Funktionen, die in späteren Versionen von Microsoft Intune zur Verfügung stehen werden. Diese Informationen werden auf einer begrenzten Basis bereitgestellt, und Änderungen sind vorbehalten. Geben Sie diese Informationen nicht außerhalb Ihres Unternehmens weiter. Einige der hier aufgeführten Features werden möglicherweise bis zum Stichtag nicht fertig und werden erst in eine spätere Version aufgenommen. Andere Features werden in einer Pilotphase getestet (Test-Flighting), um sicherzustellen, dass sie für Kunden bereit sind. Wenden Sie sich mit Fragen oder Bedenken an den Ansprechpartner für Ihre Microsoft-Produktgruppe.

Diese Seite wird regelmäßig aktualisiert. Überprüfen Sie, ob weitere Updates vorliegen.

> [!Note]
>Die folgenden Änderungen sind in der Entwicklung für Intune. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->



## <a name="intune-in-the-azure-portal"></a>Intune im Azure-Portal

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory-Websites können die App „Intune Managed Browser“ erfordern und unterstützen die einmalige Anmeldung für diese (öffentliche Vorschau) <!-- 710595 -->   
Mithilfe von Azure Active Directory (Azure AD) können Sie den Zugriff auf Websites durch mobile Geräte auf die App „Intune Managed Browser“ beschränken. Im verwalteten Browser bleiben die Websitedaten sicher und getrennt von den persönlichen Daten des Benutzers. Zusätzlich unterstützt der Managed Browser die Funktionen für einmaliges Anmelden für Websites, die von Azure AD geschützt werden. Das Anmelden beim Managed Browser oder das Verwenden desselben auf einem Gerät mit einer anderen App, die von Intune verwaltet wird, ermöglicht es dem Managed Browser, auf Unternehmenswebsites zuzugreifen, die von Azure AD geschützt werden, ohne dass der Benutzer seine Anmeldeinformationen eingeben muss. Diese Funktion gilt für Websites wie Outlook Web Access (OWA) und SharePoint Online sowie für andere Unternehmenswebsites wie Intranetressourcen, auf die über den Azure-App-Proxy zugegriffen wird.

### <a name="troubleshoot-enrollment-issues------746324----"></a>Behandlung von Problemen bei der Registrierung <!--- 746324 --->  
Im Arbeitsbereich „Problembehandlung“ werden Probleme bei der Registrierung der Benutzer angezeigt. Die Details zum Problem und die vorgeschlagenen Wiederherstellungsschritte können die Administratoren und Helpdeskbetreiber bei der Behandlung der Probleme unterstützen. Bestimmte Probleme bei der Registrierung werden nicht erfasst, und für einige Fehler liegen möglicherweise keine Wiederherstellungsvorschläge vor.

### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Administratoren können nun die Firewall-Einstellungen auf einem Gerät mithilfe eines Profils für die Gerätekonfiguration konfigurieren <!-- 951708 -->   
Administratoren können die Firewall für Geräte einschalten sowie verschiedene Protokolle für Domänen sowie private und öffentliche Netzwerke konfigurieren.  Diese Firewall-Einstellungen können im Profil „Endpoint Protection“ gefunden werden.

### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Windows Defender Application Guard unterstützt den Schutz von Geräten vor nicht vertrauenswürdigen Websites gemäß den Definitionen Ihrer Organisation <!-- 958257 -->   
Administratoren können Websites mithilfe eines Windows Information Protection-Workflows oder des neuen Profils „Netzwerkgrenze“ in den Gerätekonfigurationen als „trusted“ (vertrauenswürdig) oder „corporate“ (geschäftlich) definieren. Alle Websites, die mit Microsoft Edge angezeigt werden und nicht in der vertrauenswürdigen Netzwerkgrenze eines Windows 10 Geräts (64 Bit) aufgelistet werden, werden stattdessen in einem Browser innerhalb eines virtuellen Hyper-V-Computers geöffnet.

Application Guard kann unter den Profilen für die Gerätekonfiguration im Profil „Endpoint Protection“ gefunden werden. Von dort aus können Administratoren die Interaktionen zwischen dem virtualisierten Browser und dem Hostcomputer, vertrauenswürdigen und nicht vertrauenswürdigen Websites sowie das Speichern von Daten konfigurieren, die im virtualisierten Browser generiert werden. Es muss zunächst eine Netzwerkgrenze konfiguriert werden, um Application Guard auf einem Gerät zu verwenden. Es ist wichtig, nur eine Netzwerkgrenze für ein Gerät zu definieren.  

### <a name="windows-defender-application-guard-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Windows Defender Application Guard unter Windows 10 Enterprise bietet einen Modus, um nur autorisierten Apps zu vertrauen <!-- 1031096 -->    
Durch Tausende von neuen, schädlichen Dateien, die jeden Tag erstellt werden, bietet das Verwenden von signaturbasierten Antivirenerkennungen zum Bekämpfen von Schadsoftware keine angemessene Verteidigung mehr gegen neue Angriffe. Indem Sie Windows Defender Application Guard unter Windows 10 Enterprise verwenden, können Sie die Gerätekonfiguration von einem Modus, in dem Apps als vertrauenswürdig gelten, wenn Sie nicht von einem Antivirenprogramm oder einer anderen Sicherheitslösung blockiert werden, zu einem Modus ändern, in dem das Betriebssystem nur Apps vertraut, die von Ihrem Unternehmen autorisiert wurden. Sie weisen den Apps die Vertrauensstellung in Windows Defender Application Guard zu.

Mithilfe von Intune können Sie die Anwendungssteuerungsrichtlinien entweder für den Modus „Nur überwachen“ oder „Erzwingen“ konfigurieren. Apps werden nicht blockiert, wenn diese im Modus „Nur überwachen“ ausgeführt werden. Der Modus „Nur überwachen“ protokolliert alle Ereignisse in lokalen Clientprotokollen. Sie können ebenfalls konfigurieren, ob nur Windows-Komponenten und Windows Store-Apps ausgeführt werden können, oder ob zusätzliche Apps mit gutem Ruf gemäß der Definition von Intelligent Security Graph ausgeführt werden können.

### <a name="new-enrollment-status-page-for-windows-10-enrollments---1063201--"></a>Neue Seite für den Registrierungsstatus für Windows 10-Registrierungen <!--1063201-->    
Sie können nun eine Begrüßung konfigurieren, die angezeigt wird, wenn Ihr Benutzer Windows 10-Geräte registriert. Verwenden Sie den Bildschirm **Registrierungsstatus**, um eine benutzerdefinierte Nachricht und einen Link zu konfigurieren, die Ihren Benutzern angezeigt werden sollen, wenn diese ihre Windows 10-Geräte registrieren.  Der Bildschirm **Registrierungsstatus** gewährt den Benutzern ebenfalls einen Einblick in den Status der Richtlinieneinstellungen, die auf deren Gerät angewendet werden.  

### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Window Defender Exploit Guard stellt eine neue Reihe von Funktionen zur Abwendung von Eingriffen für Windows 10 dar <!-- 1063615 -->   
Window Defender Exploit Guard enthält benutzerdefinierte Regeln, um die Angreifbarkeit von Anwendungen zu reduzieren, verhindert Bedrohungen durch Makros und Skripts, blockiert automatisch Netzwerkverbindungen zu IP-Adressen mit schlechtem Ruf und kann Daten vor Ransomware und unbekannten Bedrohungen schützen. Windows Defender Exploit Guard besteht aus folgenden Komponenten:

- Die **Verringerung der Angriffsfläche (Attack Surface Reduction, ASR)** stellt Regeln bereit, die es Ihnen ermöglichen, Bedrohungen durch Makros, Skripts und E-Mails zu verhindern.
- Der **gesteuerte Ordnerzugriff** blockiert automatisch den Zugriff auf Inhalte in geschützten Ordnern.
- Der **Netzwerkfilter** blockiert ausgehende Verbindungen von jeder App mit IPs/Domänen mit schlechtem Ruf.
- Der **Exploit-Schutz** stellt Einschränkungen für den Arbeitsspeicher, die Ablaufsteuerung und Richtlinien bereit, die für den Schutz einer Anwendung vor Exploits verwendet werden können.

### <a name="app-conditional-launch-support----1193313---"></a>App-bedingte Startunterstützung <!-- 1193313 -->
IT-Administratoren können nun eine Anforderung über das Azure-Verwaltungsportal festlegen, um eine Kennung statt einer numerischen PIN über die mobile App-Verwaltung (Mobile App Management, MAM) zu erzwingen, wenn die Anwendung gestartet wird. Wenn dies konfiguriert ist, muss der Benutzer eine Kennung festlegen und verwenden, wenn er dazu aufgefordert wird, bevor der Zugriff auf MAM-aktivierte Apps gewährt wird. Eine Kennung ist als numerische PIN mit mindestens einem Sonderzeichen oder einem Groß-/Kleinbuchstaben definiert. In dieser Version von Intune wird dieses Feature **nur unter iOS** aktiviert. Intune unterstützt Kennungen auf ähnliche Weise wie numerische PINs, nämlich indem eine Mindestlänge festgelegt wird, sodass wiederholte Zeichen und Sequenzen möglich sind. Dieses Feature erfordert die Teilnahme der Anwendungen (z.B. WXP, Outlook, Managed Browser, Yammer), um das Intune App SDK in den Code für dieses Feature anstelle der Kennungseinstellungen zu integrieren und für die Zielanwendungen zu erzwingen.

### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>App-Versionsnummer für branchenspezifische Apps im Statusbericht der Geräteinstallation <!-- 1233999 -->  
Der Statusbericht der Geräteinstallation zeigt die App-Versionsnummern der branchenspezifischen Apps für iOS und Android an. Sie können diese Informationen verwenden, um Probleme mit Ihren Apps zu beheben oder um Geräte zu suchen, auf denen veraltete App-Versionen ausgeführt werden.

### <a name="co-management-for-windows-10-devices-----124445---"></a>Co-Verwaltung für Windows 10-Geräte <!-- 124445 -->
Bei der Co-Verwaltung handelt es sich um eine Lösung, die eine Brücke von der herkömmlichen zur modernen Verwaltung schlägt und Ihnen die Möglichkeit bietet, die Umstellung schrittweise durchzuführen. Bei der Co-Verwaltung handelt es sich im Grunde um eine Lösung, mit der Windows 10-Geräte gleichzeitig mit Configuration Manager und Intune verwaltet werden können. Außerdem können sie in Active Directory (AD) und Azure Active Directory (Azure AD) eingebunden werden.  Diese Konfiguration bietet Ihnen eine Möglichkeit, um nach und nach den Bedürfnissen Ihrer Organisation entsprechend eine Modernisierung durchzuführen, wenn Sie nicht alles auf einmal durchführen können.  

### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Festlegen des Zugriffs für Apps durch einen mindestens erforderlichen Android-Sicherheitspatch auf dem Gerät <!-- 1278463 -->   
Ein Administrator kann den mindestens erforderlichen Android-Sicherheitspatch definieren, der auf dem Gerät installiert sein muss, um Zugriff auf eine verwaltete Anwendung mit einem verwalteten Konto zu erhalten.

> [!Note]  
> Dieses Feature schränkt nur Sicherheitspatches ein, die von Google für Android 6.0+-Geräte veröffentlicht wurden.

### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Neue Einstellungen für Geräteeinschränkungen für Windows 10 <!-- 1308850 -->
-    Messaging (nur mobil): Deaktivieren von Test- oder MMS-Nachrichten
-    Kennwort: Einstellungen zum Aktivieren von FIPS und der Verwendung von sekundären Windows Hello-Geräten für die Authentifizierung 
-    Anzeige: Einstellungen zum Aktivieren oder Deaktivieren der GDI-Skalierung für ältere Apps


### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Geräteeinschränkungen beim Windows 10-Kioskmodus <!-- 1308872 -->   
Sie können die Benutzer von Windows 10-Geräten auf den Kioskmodus beschränken, der diese auf eine Reihe von vordefinierten Apps einschränkt.  Erstellen Sie dazu ein Einschränkungsprofil für Windows 10-Geräte und legen Sie die Kioskeinstellung fest.

Der Kioskmodus unterstützt zwei Modi: **einzelne App** (ermöglicht dem Benutzer nur das Ausführen einer einzigen App) oder **mehrere Apps** (ermöglicht den Zugriff auf verschiedene Apps).  Sie definieren das Benutzerkonto und den Gerätenamen, der die unterstützten Apps definiert.  Wenn der Benutzer angemeldet ist, ist dieser auf die definierten Apps beschränkt.  Weitere Informationen finden Sie unter [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

Der Kioskmodus erfordert Folgendes:

- Intune muss die MDM-Autorität sein.
- Die Apps müssen bereits auf dem Zielgerät installiert sein.
- Das Gerät muss [ordnungsgemäß bereitgestellt](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions) sein.

### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Neues Gerätekonfigurationsprofil für das Erstellen von Netzwerkgrenzen <!-- 1311967 -->   
Es wurde ein Gerätekonfigurationsprofil namens **Netzwerkgrenze** erstellt, das bei Ihren anderen Gerätekonfigurationsprofilen gefunden werden kann. Verwenden Sie dieses Profile, um Onlineressourcen zu definieren, die als „geschäftlich“ oder „vertrauenswürdig“ angesehen werden sollen. Sie müssen eine Netzwerkgrenze für ein Gerät definieren, *bevor* Features wie Windows Defender Application Guard und Windows Information Protection auf dem Gerät verwendet werden können. Es ist wichtig, nur eine Netzwerkgrenze für jedes Gerät zu definieren.

Sie können Unternehmenscloudressourcen, IP-Adressbereiche und interne Proxyserver definieren, die als vertrauenswürdig angesehen werden sollen. Sobald diese definiert sind, kann die Netzwerkgrenze von anderen Features wie Windows Defender Application Guard und Windows Information Protection verwendet werden.

###  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Zwei zusätzliche Einstellungen für Windows Defender Antivirus <!-- 1338409 -->  
**Ebene der Dateiblockierung**

| | |
|---|---|
| Nicht konfiguriert | **Nicht konfiguriert** verwendet die Standardblockierungsebene von Windows Defender Antivirus und bietet eine starke Erkennung ohne das Risiko zu erhöhen, zulässige Dateien zu erkennen. |
| Hoch | **Hoch** wendet eine starke Erkennungsebene an.
| Hoch +  | **Hoch +** bietet die Ebene „Hoch“ mit zusätzlichen Schutzmaßnahmen, die sich auf die Clientleistung auswirken können.
| Keine Toleranz  | **Keine Toleranz** blockiert alle unbekannten ausführbaren Dateien. |

Es ist zwar unwahrscheinlich, aber dennoch können bei der Einstellung auf **Hoch** einige zulässige Dateien erkannt werden.
Es wird empfohlen, die Ebene der Datenblockierung auf den Standardwert, **Nicht konfiguriert**, festzulegen.

**Timeouterweiterung für die Dateiüberprüfung durch die Cloud**  

| | |
|--|--|
| Anzahl von Sekunden (0–50) | Geben Sie den maximalen Zeitraum an, für den Windows Defender Antivirus eine Datei blockieren soll, während auf ein Ergebnis von der Cloud gewartet wird. Der Standardzeitraum beträgt 10 Sekunden. Jede zusätzliche Zeit, die hier angegeben wird (bis zu 50 Sekunden), wird zu diesen 10 Sekunden addiert. In den meisten Fällen nimmt der Scan wesentlich weniger als den Maximalwert in Anspruch. Das Erweitern des Zeitraums ermöglicht es der Cloud, verdächtige Dateien gründlich zu überprüfen. Es wird empfohlen, diese Einstellung zu aktivieren und mindestens 20 zusätzliche Sekunden anzugeben. |


### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Unterstützung für die Symantec-Cloudzertifizierungsstelle (ZS) <!-- 1333638 -->    
Intune unterstützt nun die Symantec-Cloud-ZS, die es dem Intune Certificate Connector ermöglicht, PKCS-Zertifikate von der Symantec-Cloud-ZS für von Intune verwaltete Geräte auszustellen. Wenn Sie den Intune Certificate Connector bereits mit der Microsoft-Zertifizierungsstelle (ZS) verwenden, können Sie das vorhandene Intune Certificate Connector-Setup nutzen, um die Unterstützung für die Symantec-ZS hinzuzufügen.



### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Citrix-VPN wurde für Windows 10-Geräte hinzugefügt <!-- 1512457 -->  
Kunden können Citrix-VPN für ihre Windows 10-Geräte konfigurieren. Sie können Citrix-VPN in der Liste *Verbindungstyp auswählen* im Blatt **Basis-VPN** auswählen, wenn Sie ein VPN für Windows 10 oder höher konfigurieren.

> [!Note]
> Die Citrix-Konfiguration ist bereits für iOS und Android vorhanden.





<!-- the following are present prior to 1710 -->

### <a name="google-play-protect-support-on-android----908720----"></a>Unterstützung für Google Play Protect unter Android <!-- 908720  -->  
Mit der Version Android Oreo führt Google eine Suite von Sicherheitsfunktionen namens „Google Play Protect“ ein, mit denen Benutzer und Organisationen Apps und Android-Images sicher ausführen können. Intune unterstützt Google Play Protect-Funktionen, einschließlich des SafetyNet-Remotenachweises.  Administratoren können Konformitätsrichtlinienanforderungen festlegen, für die Google Play Protect konfiguriert sein und sich in einem fehlerfreien Zustand befinden muss. Für die Verwendung der Einstellung **SafetyNet-Gerätenachweis** muss das Gerät eine Verbindung mit einem Google-Dienst herstellen, damit sichergestellt ist, dass sich das Gerät in einem fehlerfreien Zustand befindet und es nicht beeinträchtigt ist. Administratoren können zudem eine Konfigurationsprofileinstellung für Android for Work festlegen, um zu erfordern, dass installierte Apps von Google Play-Diensten überprüft werden.  Wenn ein Gerät nicht mit Google Play Protect-Anforderungen kompatibel ist, können Benutzer durch den bedingten Zugriff daran gehindert werden, auf Unternehmensressourcen zuzugreifen. 


### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Unterstützung für die Windows 10-Editionsupgraderichtlinie <!-- 903672(archived), 1119689 -->  
Durch das Erstellen einer Windows 10-Editionsupgraderichtlinie können Sie für Windows 10-Geräte ein Upgrade auf folgende Betriebssysteme durchführen: Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education und Windows 10 Professional Education N. Weitere Informationen zu Windows 10-Editionsupgrades finden Sie unter [Konfigurieren von Windows 10-Editionsupgrades](edition-upgrade-configure-windows-10.md).


### <a name="intune-mam-and-outlook-for-android-add-ins-----1450688---"></a>Intune MAM und Outlook für Android-Add-Ins <!-- 1450688 -->
In einigen Wochen wird das Office-Team Add-Ins für Outlook für Android ankündigen. Diese Add-In-Funktionsgruppe ist bereits in Outlook für Windows, iOS und Mac sowie Outlook im Web vorhanden. Da Add-Ins über Exchange verwaltet werden, können die Benutzer Daten und Nachrichten über Outlook und nicht verwaltete Add-In-Anwendungen kopieren und freigeben, sofern der Zugriff auf Add-Ins von Ihrem Exchange-Administrator aktiviert wurde. 

Arbeiten Sie bei der Verwaltung von Berechtigungen für den Zugriff durch Benutzer auf Add-Ins mit Ihrem Exchange-Administrator zusammen, um sicherzustellen, dass Ihre MAM-Datenschutzrichtlinien auf Add-Ins angewendet werden.

#### <a name="how-does-this-affect-me"></a>Inwiefern betrifft das mich?
Wenn Ihre Exchange-Richtlinien bereits so konfiguriert sind, dass das Querladen oder die Installation von Add-Ins verhindert wird, können Sie diesen Abschnitt überspringen. Ihre MAM-Richtlinien werden wie erwartet angewendet. Wenn Sie jedoch Richtlinien in MAM festgelegt haben, um Vorgänge zum Ausschneiden, Kopieren und Einfügen in Outlook für Android einzuschränken, und nicht Ihre Add-In-Richtlinie in Exchange festgelegt haben, sollte Ihnen bewusst sein, dass Benutzer standardmäßig Add-Ins in Outlook installieren können. Diese Add-Ins können auf den Nachrichtentext, den Betreff und andere Nachrichteneigenschaften zugreifen. Sie können die Funktion zum Installieren von Add-Ins für Benutzer deaktivieren, indem Sie Ihren Exchange-Administrator bitten, die Rollen „Meine Marketplace-Apps“ und „Meine benutzerdefinierten Apps“ zu entfernen.

Die Einstellungsänderung in Exchange gilt für Outlook für Windows, iOS und Mac, Outlook Mobile sowie Outlook im Web. 

#### <a name="what-do-i-need-to-do"></a>Was muss ich tun?
Überprüfen Sie noch heute Ihre Exchange-Richtlinien. Informieren Sie Ihre IT- und Helpdeskmitarbeiter. Wenden Sie sich bei Fragen oder Bedenken an unser Supportteam. 




<!-- the following are present prior to 1709 -->

### <a name="actions-for-non-compliance----730266--846515---"></a>Aktionen bei Inkompatibilität <!--730266  846515 -->     
*Aktionen bei Inkompatibilität* ist eine neue Funktion für Kompatibilitätsrichtlinien, mit der Sie auf Geräten, die nicht kompatibel sind, Maßnahmen ergreifen können. Sie können eine oder mehrere Aktionen angeben und den Zeitraum festlegen, in dem diese Aktionen ausgeführt werden müssen. Sie können z.B. Benutzer von Geräten per E-Mail benachrichtigen, sobald ihr Gerät inkompatibel wurde. Sie können auch den Zugriff nicht kompatibler Geräte auf Unternehmensressourcen sperren, nachdem die Geräte während einer dreitägigen Karenzzeit per bedingtem Zugriff zugreifen konnten.

### <a name="android-for-work-support-for-lookout----1087312---"></a>Unterstützung für Lookout in Android for Work <!-- 1087312 -->   
Der Intune-Connector mit Lookout unterstützt die Verwendung der Lookout for Work-App auf Android for Work-Geräten. Sie können die Lookout-App innerhalb oder außerhalb des Containers bereitstellen.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune-App-Schutz und Citrix MDX-Entwicklungstools <!-- 709185 -->
Sie können Geräte und Apps mit einer Kombination aus Citrix XenMobile MDX und Microsoft Intune verwalten. Dadurch können Sie Apps mit der Intune-App-Schutzrichtlinie verwalten, während Sie die mVPN-Technologie von Citrix verwenden.

Sie können ein Coderepository suchen, das das App Wrapping Tool von Intune und des Intune App SDK für iOS und Android enthält, das von der Citrix MDX mVPN-Technologie integriert wird.

#### <a name="how-integration-with-intune-works"></a>Funktionsweise der Integration mit Intune
Das Risiko wird basierend auf Telemetriedaten von Geräten bewertet, auf denen Zimperium ausgeführt wird. Sie können Richtlinien für bedingten EMS-Zugriff basierend auf der Zimperium-Risikobewertung konfigurieren, die über Intune-Gerätekompatibilitätsrichtlinien aktiviert werden, und so anhand der erkannten Bedrohungen nicht kompatible Geräte für den Zugriff auf Unternehmensressourcen zulassen oder blockieren.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Hochverfügbarkeit der Unterstützung von lokalem Exchange-Connector <!-- 676614 -->   
Sie können über mehrere Clientzugriffs-Serverrollen (CAS) für den lokalen Exchange-Connector verfügen. Bei einem Fehler des Haupt-Clientzugriffsservers empfängt der Exchange-Connector z.B. eine Abfrage, um auf andere Clientzugriffsserver zurückzugreifen. Durch diese Funktion wird sichergestellt, dass der Dienst nicht unterbrochen wird.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>System Center Operations Manager Management Pack für Exchange-Connector <!-- 885457 -->   
Mit dem System Center Operations Manager Management Pack für den Exchange-Connector können Sie die Exchange-Connector-Protokolle analysieren. Dieses Management Pack bietet Ihnen bei der Behebung von Problemen verschiedene Möglichkeiten zur Überwachung von Intune.


## <a name="intune-apps"></a>Intune-Apps


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>Umleiten von macOS-Benutzern zur neuen Unternehmensportal-App <!--1380728-->   
Wenn ein Benutzer sich bei der Website des Unternehmensportals anmeldet, um sein macOS-Gerät zu registrieren, wird dieser zum Download der neuen Unternehmensportal-App für macOS umgeleitet, um den Vorgang abzuschließen. Dies tritt bei macOS-Geräten auf, die OS X El Capitan 10.11 oder höher verwenden. 

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Unterstützung der zertifikatbasierten Authentifizierung auf dem Unternehmensportal für iOS <!--1029830-->
Es wurde eine Unterstützung für die zertifikatbasierte Authentifizierung in der Unternehmensportal-App für iOS hinzugefügt. Benutzer mit zertifikatbasierter Authentifizierung geben ihren Benutzernamen ein und tippen dann auf den Link „Sign in with a certificate“ (Mit einem Zertifikat anmelden). Die zertifikatbasierte Authentifizierung wird auf den Unternehmensportal-Apps für Android und Windows bereits unterstützt. Weitere Informationen finden Sie auf der Seite [Anmelden bei der Unternehmensportal-App](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

<!-- the following are present prior to 1710 -->



### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Apps, die mit oder ohne Registrierung verfügbar sind, können nun installiert werden, ohne dass Sie zur Registrierung aufgefordert werden. <!-- 1334712 -->
Unternehmens-Apps, die mit oder ohne Registrierung in der Android-Unternehmensportal-App zur Verfügung gestellt wurden, können installiert werden, ohne dass Sie zur Registrierung aufgefordert werden.


<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Unterstützung für Intune Managed Browser von iOS und Android <!-- 1374196 -->
Ab Oktober 2017 unterstützt die Intune Managed Browser-App für Android nur noch Geräte mit Android 4.4 oder höher. Die Intune Managed Browser-App unter iOS unterstützt nur noch Geräte mit iOS 9.0 oder höher. Frühere Versionen von Android und iOS können Managed Browser weiterhin verwenden, allerdings können keine neuen Versionen der App installiert werden, und einige App-Funktionen sind möglicherweise nicht verfügbar. Es wird empfohlen, dass Sie diese Geräte auf eine unterstützte Betriebssystemversion aktualisieren.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Verbesserte Fehlermeldungen für den Fall, wenn ein Benutzer die Höchstzahl von zur Registrierung erlaubten Geräten erreicht <!-- 1270370 -->
Statt einer generischen Fehlermeldung sehen Benutzer eine freundliche, handlungsrelevante Fehlermeldung: „You have enrolled the maximum number of devices allowed by your IT admin. Please remove an enrolled device or get help from your IT admin.“ (Sie haben die maximale Anzahl an Geräten registriert, die von Ihrem IT-Administrator erlaubt wurden. Bitte entfernen Sie ein registriertes Gerät, oder wenden Sie sich an Ihren IT-Administrator.“)




## <a name="notices"></a>Benachrichtigungen

### <a name="device-and-app-management-integration----677972---"></a>Integration der Verwaltung von Geräten und Apps <!-- 677972 -->   
Da auf die mobile Geräteverwaltung (Mobile Device Management, MDM) und die mobile Anwendungsverwaltung (Mobile Application Management, MAM) nun über das Azure-Portal zugegriffen werden kann, hat Intune damit begonnen, die Vorteile für IT-Administratoren bei der Verwaltung von Anwendungen und Geräten zu integrieren. Diese Änderungen sind darauf ausgerichtet, das Verwalten von Geräten und Apps zu vereinfachen.

Weitere Informationen zu den angekündigten Änderungen an MDM und MAM finden Sie im [Blog des Intune-Supportteams](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).




### <a name="see-also"></a>Weitere Informationen:
Details zu aktuellen Entwicklungen finden Sie unter [Neuheiten in Microsoft Intune](whats-new.md).
