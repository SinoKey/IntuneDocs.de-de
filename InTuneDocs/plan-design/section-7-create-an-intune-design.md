---
title: Erstellen eines Intune-Entwurfs | Microsoft-Dokumentation
description: "Dieser Artikel unterstützt Sie beim Erstellen eines Entwurfs für einen Microsoft Intune-Cloudentwurf und seine Implementierung."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a8e38e29-f5e3-4a71-a170-d3b1a06e37c6
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 70be873367edccdefd724b6aa6959eb67b377bdd
ms.openlocfilehash: 92dedcd165ffec47f6c5b818533fce08ed04b1a0


---

# <a name="create-an-intune-design"></a>Erstellen eines Intune-Entwurfs

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Der Handbuchabschnitt sollte parallel zu anderen Themen in Abschnitt 2 verwendet werden. Dieser Entwurf basiert auf den Informationen und Entscheidungen, die Sie beim Bearbeiten der vorherigen Abschnitte dieses Handbuchs gesammelt bzw. getroffen haben. In diesem Entwurfsabschnitt konzentrieren wir uns auf die eigenständige Version von Intune, einem cloudbasierten Microsoft-Dienst, der sich in der Cloud befindet.

Auch wenn minimale lokale Infrastrukturanforderungen vorliegen, wird dennoch die Arbeit an einem Entwurfsplan empfohlen. So können Sie sicherzustellen, dass Sie die richtige Verwaltungslösung für Mobilgeräte verwenden, die Ihren Zielen und Anforderungen entspricht.

Darüber hinaus ist es während der Implementierungs- und Testphase üblich, dass Entwurfsänderungen anfallen. Stellen Sie sicher, dass all diese Änderungen sowie deren Gründe sofort dokumentiert werden. Die folgenden Bereiche werden erörtert:

-   Die aktuelle Umgebung

-   Intune-Bereitstellungsoptionen

-   Identitätsanforderungen für externe Abhängigkeiten

-   Aspekte zur Geräteplattform

-   Anforderungen an die Zustellung  

Betrachten wir jeden dieser Bereiche im Detail. 

## <a name="record-your-environment"></a>Erfassen Ihrer Umgebung

Der erste Schritt vor der Erstellung des Entwurfs ist das Erfassen Ihrer aktuellen Umgebung. Die aktuelle Umgebung kann Entwurfsentscheidungen beeinflussen. Sie sollte dokumentiert und bei anderen Intune-Entwurfsentscheidungen als Referenz verwendet werden. Im Folgenden finden Sie einige Beispiele für das Erfassen der aktuellen Umgebung:

-   **Identität in der Cloud**

    -   Verwenden Sie DirSync oder Azure Active Directory (AAD) Connect?

    -   Ist Ihre Umgebung im Verbund zusammengefasst?

    -   Ist die mehrstufige Authentifizierung aktiviert?

-   **E-Mail-Umgebung**

    -   Wird Exchange verwendet? Lokal oder in der Cloud?

    -   Befinden Sie sich mitten in einem Projekt zur Migration von Exchange zur Cloud?

-   **Aktuelle MDM-Lösung**

    -   Verwenden Sie zurzeit andere MDM-Lösungen?

    -   Welche MDM-Lösungen verwenden Sie für Unternehmens- und BYOD-Anwendungsszenarien?

    -   Welche Funktionen verwenden Sie (z.B. App-Geräteeinstellungen, WLAN-Konfigurationen usw.)?

    -   Welche Geräteplattformen werden unterstützt?

    -   Welche Gruppen und wie viele Benutzer verwenden die MDM-Lösung?

-   **Zertifikatlösung**

    -   Haben Sie eine Zertifikatlösung implementiert?

    -   Welche Art von Zertifikaten verwenden Sie?

-   **Systemverwaltung**

    -   Wie verwalten Sie Ihre PC- und Serverumgebung?

    -   Wird System Center Configuration Manager verwendet? Verwenden Sie eine Drittanbieterplattform zur Systemverwaltung?

-   **VPN-Lösung**

    -   Was ist Ihre VPN-Lösung?

    -   Wird sie sowohl für Unternehmens- als auch für BYOD-Anwendungsszenarien eingesetzt?

Stellen Sie beim Erfassen der aktuellen MDM-Umgebung sicher, dass Sie alle Projekte oder andere Pläne berücksichtigen, die Änderungen an Ihrer Umgebung vornehmen könnten. Im Folgenden sehen Sie ein Beispiel für eine Möglichkeit zum Erfassen der aktuellen Umgebung, das Sie beim Erstellen Ihres Intune-Entwurfs unterstützen kann:

| **Lösungsbereich** | **Aktuelle Umgebung** | **Kommentare** |
|:---:|:---:|:---:|
| **Identität** | Azure AD, Azure AD Connect, kein Verbund, keine MFA | Vorgesehenes Projekt zum Aktivieren der MFA bis zum Ende des Jahres |                 
| **E-Mail-Umgebung** | Exchange lokal, Exchange Online | Derzeit erfolgt die Migration von Exchange lokal zu Exchange Online. 75% der Postfächer migriert. Die letzten 25% werden vor Beginn des Intune-Pilotprojekts migriert. |                
| **SharePoint** | SharePoint lokal | Keine Pläne zur Onlineverwendung von SharePoint |  
| **Aktuelle MDM** | Exchange ActiveSync |  |
| **Zertifikatlösung** | Microsoft Server 2012 R2, Active Directory-Zertifikatdienste | PKI wird nur für Websiteserver verwendet |
| **Systemverwaltung** | System Center Configuration Manager CB 1606 | Die Intune-Hybridlösung soll näher untersucht werden |
| **VPN-Lösung** | Cisco AnyConnect |  |

## <a name="choose-an-intune-deployment-option"></a>Wählen einer Intune-Bereitstellungsoption

Intune bietet zwei Bereitstellungsoptionen: eigenständig und hybrid. Sie müssen entscheiden, welche Ihren Anforderungen entspricht. Eigenständig bezieht sich darauf, dass der Intune-Dienst in der Cloud ausgeführt wird. Hybrid bezieht sich auf die Integration von Intune in System Center Configuration Manager.

- Weitere Informationen zum [Wählen zwischen eigenständigem Microsoft Intune und der hybriden Verwaltung mobiler Geräte mit System Center Configuration Manager](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management)

## <a name="intune-tenant-location"></a>Standort des Intune-Mandanten

Wenn Ihre Organisation weltweit tätig ist, planen Sie beim Abonnieren des Diensts den Standort Ihres Mandanten. Das Land wird definiert, wenn Sie sich erstmals für ein Intune-Abonnement registrieren. Anschließend erfolgt die Zuordnung zu Regionen rund um die Welt, die unten aufgeführt sind:

-   Nordamerika

-   Europa, Naher Osten und Afrika

-   Asien und pazifischer Raum

>[!IMPORTANT]
> Das Land/der Standort des Mandanten kann später nicht mehr geändert werden.

## <a name="external-dependencies"></a>Externe Abhängigkeiten

Externe Abhängigkeiten sind Dienste und Produkte, die separat von Intune ausgeführt werden, aber entweder für Intune erforderlich sind oder in Intune integriert werden können. Die Anforderungen an externe Abhängigkeiten und deren Konfiguration müssen unbedingt abgeklärt werden. Einige Beispiele für gängige externe Abhängigkeiten sind unten aufgeführt.

-   Identität

-   Benutzer- und Gerätegruppen

-   PKI

Betrachten wir diese gängigen externen Abhängigkeiten unten im Detail.

### <a name="identity"></a>Identität

Mit der Identität identifizieren wir die Benutzer, die Ihrer Organisation angehören und ein Gerät registrieren. Intune erfordert Azure Active Directory (Azure AD) als Benutzeridentitätsanbieter. Wenn Sie diesen Dienst bereits verwenden, können Sie Ihre bereits in der Cloud vorhandene Identität nutzen. Azure AD Connect ist außerdem das empfohlene Tool zum Synchronisieren Ihrer lokalen Benutzeridentitäten mit Microsoft Cloud Services. Wenn in Ihrer Organisation bereits Office 365 verwendet wird, muss Intune unbedingt dieselbe Azure Active Directory-Umgebung verwenden.

Unten finden Sie weitere Informationen zu den Intune-Identitätsanforderungen.

-   Weitere Informationen zu [Identitätsanforderungen](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview).

-   Weitere Informationen zu [Anforderungen an die Verzeichnissynchronisierung](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements).

-   Weitere Informationen zu [Anforderungen an die mehrstufige Authentifizierung](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements).

### <a name="user-and-device-groups"></a>Benutzer- und Gerätegruppen

Benutzer- und Gerätegruppen legen das Ziel einer Bereitstellung fest. Dazu gehört beispielsweise die Festlegung von Bereitstellungszielen für Richtlinien, Anwendungen und Profile. Die Intune-Cloud unterstützt Benutzer- und Gerätegruppen – Sie müssen festlegen, welche Benutzer- und Gerätegruppen benötigt werden. Es wird empfohlen, alle Gruppen im lokalen Active Directory zu erstellen und dann mit Azure Active Directory zu synchronisieren. Unten finden Sie weitere Informationen zur Planung und Erstellung von Benutzer- und Gerätegruppen.

-   Weitere Informationen zu [Planen von Benutzer- und Gerätegruppen](https://docs.microsoft.com/intune/deploy-use/plan-your-user-and-device-groups).

-   Erhalten Sie Informationen zum [Erstellen von Benutzer- und Gerätegruppen](https://docs.microsoft.com/en-us/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

### <a name="public-key-infrastructure-pki"></a>Public Key-Infrastruktur (PKI)

Die Public Key-Infrastruktur stellt Zertifikate für Geräte oder Benutzer bereit, damit diese sich sicher bei einem Dienst authentifizieren können. Intune unterstützt eine Microsoft PKI-Infrastruktur. Geräte- und Benutzerzertifikate können für ein mobiles Gerät ausgestellt werden, um die Anforderungen an die zertifikatbasierte Authentifizierung zu erfüllen. Vor der Implementierung von Zertifikaten müssen Sie ermitteln, ob Zertifikate erforderlich sind, ob die Netzwerkinfrastruktur die zertifikatbasierte Authentifizierung unterstützt und ob Zertifikate in der vorhandenen Umgebung derzeit verwendet werden.

Wenn Sie planen, Zertifikate mit VPN-, WLAN- oder E-Mail-Profilen mit Intune zu verwenden, müssen Sie sicherstellen, dass eine unterstützte [PKI-Infrastruktur vorhanden ist](https://docs.microsoft.com/intune/deploy-use/secure-resource-access-with-certificate-profiles), in der Zertifikatprofile erstellt und bereitgestellt werden können.

Wenn SCEP-Zertifikate ausgegeben werden sollen, müssen Sie darüber hinaus festlegen, auf welchem Server der Registrierungsdienst für Netzwerkgeräte (SCEP) gehostet wird und wie die Kommunikation erfolgen soll.

Weitere Informationen zum Konfigurieren von Zertifikaten in Intune:

-   [Konfigurieren der Zertifikatinfrastruktur für SCEP](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-scep)

-   [Konfigurieren der Zertifikatinfrastruktur für PFX](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-pfx)

-   [Konfigurieren von Intune-Zertifikatprofilen](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles)

-   [Konfigurieren von Richtlinien für den Ressourcenzugriff](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune).

## <a name="device-platform-considerations"></a>Aspekte zur Geräteplattform

Sie müssen sich Ihre Geräte genauer ansehen, um ihre Funktionsweise zu verstehen.

-   Ermitteln unterstützter Geräteplattformen

-   Geräte

-   Gerätebesitz

-   Massenregistrierung

Betrachten wir diese Bereiche im Detail.

### <a name="determine-supported-device-platforms"></a>Ermitteln unterstützter Geräteplattformen

Sie müssen beim Erstellen des Entwurfs wissen, welche Geräte sich in der Umgebung befinden werden, und überprüfen, ob diese von Intune unterstützt werden oder nicht. Intune unterstützt die Plattformen iOS, Android und Windows.

-   Weitere Informationen zu [von Intune unterstützten Geräten](https://docs.microsoft.com/intune/get-started/supported-mobile-devices-and-computers).

### <a name="devices"></a>Geräte

Intune verwaltet mobile Geräte, um Unternehmensdaten zu schützen und Endbenutzern die Arbeit an mehreren Standorten zu ermöglichen. Intune unterstützt mehrere Plattformen. Deshalb wird empfohlen, die Geräte und die Betriebssystemplattformen zu dokumentieren, die im Entwurf Ihrer Organisation unterstützt werden. Dies gilt für die im Abschnitt erstellten Geräte und Plattformen (Anforderungen des Anwendungsfalls).

Zudem empfiehlt es sich, die Versionen zu dokumentieren, um die Liste beim Prüfen auf Gerätefunktionen nach Betriebssystemplattform und Version als Referenz zu verwenden. Beispiel:

| **Geräteplattform** | **Betriebssystemversionen** |
|:---:|:---:|
| iOS – iPhone | 9.0+ |                
| iOS – iPad | 8.0+ |               
| Android – Samsung Knox Standard | 4.0+ |
| Windows 10-Tablet | 10+ |

### <a name="device-ownership"></a>Gerätebesitz

Intune unterstützt sowohl Unternehmensgeräte als auch selbst mitgebrachte Geräte (Bring Your Own Device, BYOD). Ein Gerät wird als unternehmenseigen betrachtet, wenn es über einen Geräteregistrierungs-Manager oder ein Programm zur Geräteregistrierung registriert wurde. Beispielsweise kann ein Gerät über Apple-DEP registriert, als unternehmenseigen markiert und in eine Gerätegruppe aufgenommen werden, die gezielte Unternehmensrichtlinien und Apps empfängt.

Weitere Informationen zu Unternehmens- und BYOD-Anwendungsfällen finden Sie unter [Abschnitt 3: Bestimmen von Anwendungsfallanforderungen](section-3-determine-use-case-requirements.md).

### <a name="bulk-enrollment"></a>Massenregistrierung

Für die Registrierung eines Geräts in Intune gibt es mehrere Registrierungsoptionen, die die Self-Service-Registrierung über das Unternehmensportal ergänzen. Die Massenregistrierung kann je nach Plattform unterschiedlich umgesetzt werden. Wenn die Massenregistrierung benötigt wird, legen Sie zunächst die Methode zur Massenregistrierung fest, und integrieren Sie sie in Ihren Entwurf. Unten finden Sie weitere Informationen zu verschiedenen Methoden der Massenregistrierung.

-   Erfahren Sie mehr über die [Massenregistrierung](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune).

## <a name="feature-requirements"></a>Featureanforderungen

In den folgenden Abschnitten betrachten wir die folgenden Features und Funktionen, die auf die Anforderungen Ihres Anwendungsfalls ausgerichtet werden:

-   Richtlinien für Geschäftsbedingungen

-   Konfigurationsrichtlinien

-   Ressourcenprofile

-   Apps

-   Kompatibilitätsrichtlinie

-   Bedingter Zugriff

Betrachten wir jeden dieser Bereiche im Detail.

### <a name="terms-and-conditions-policies"></a>Richtlinien für Geschäftsbedingungen

Anhand von Geschäftsbedingungen können Richtlinien oder Bedingungen erläutert werden, denen ein Benutzer vor der Registrierung zustimmen muss. Intune unterstützt die Möglichkeit, Benutzergruppen mehrere Richtlinien für Geschäftsbedingungen hinzuzufügen und bereitzustellen. Sie müssen festlegen, ob Richtlinien für Geschäftsbedingungen erforderlich sind. Falls ja, muss festgelegt werden, wer für die Bereitstellung dieser Informationen in der Organisation verantwortlich ist.

-   Erfahren Sie, wie in Intune [Richtlinien für Geschäftsbedingungen erstellt werden](https://docs.microsoft.com/intune/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune). Im Folgenden finden Sie ein Beispiel für das Dokumentieren der Richtlinie für Geschäftsbedingungen.

| **Name der Geschäftsbedingungen** | **Anwendungsfall** | **Zielgruppe** |
|:---:|:---:|:---:|
| Bedingungen für Unternehmensgeräte | Unternehmen | Unternehmensbenutzer |                 
| BYOD-Bedingungen | BYOD | BYOD-Benutzer |                

### <a name="configuration-policies"></a>Konfigurationsrichtlinien

Über Konfigurationsrichtlinien werden Sicherheitseinstellungen und -features auf einem Geräten verwaltet. Beim Entwerfen Ihrer Konfigurationsrichtlinien finden Sie Informationen im Abschnitt mit den Anforderungen des Anwendungsfalls. Anhand dieser Informationen können Sie die für Intune-Geräte erforderlichen Konfigurationen ermitteln. Dokumentieren Sie die Einstellungen und wie diese konfiguriert werden sollen. Dokumentieren Sie außerdem, für welche Benutzer- oder Gerätegruppen sie gelten sollen.

Erstellen Sie mindestens eine Konfigurationsrichtlinie pro Plattform. Sie können bei Bedarf mehrere Konfigurationsrichtlinien pro Plattform erstellen. Im Folgenden finden Sie ein Beispiel für das Entwerfen von vier verschiedenen Konfigurationsrichtlinien für verschiedene Plattformen und Anwendungsszenarien.

| **Name der Richtlinie** | **Geräteplattform** | **Einstellungen** | **Zielgruppe** |   
|:---:|:---:|:---:|:---:|
| Unternehmen – iOS | iOS | PIN ist erforderlich, Länge: 6, Cloudsicherung einschränken | Unternehmensgeräte |                                                           
| Unternehmen – Android | Android | PIN ist erforderlich, Länge: 6, Cloudsicherung einschränken | Unternehmensgeräte |                                                           
| BYOD – iOS  | iOS | PIN ist erforderlich, Länge: 4 | BYOD-Geräte |
| BYOD – Android  | Android | PIN ist erforderlich, Länge: 4 | BYOD-Geräte |

### <a name="profiles"></a>Profile

Anhand von Profilen kann der Endbenutzer eine Verbindung mit Unternehmensdaten herstellen. Intune unterstützt zahlreiche Typen von Profilen. Anhand der Anwendungsfälle und Anforderungen können Sie bestimmen, wann die [Profile](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune) konfiguriert werden. Alle Geräteprofile werden nach Plattformtyp kategorisiert und sollten in der Entwurfsdokumentation berücksichtigt werden.

-   Zertifikatprofile

-   Wi-Fi-Profil

-   VPN-Profil

-   E-Mail-Profil

Betrachten wir die einzelnen Profiltypen im Detail.

##### <a name="certificate-profiles"></a>Zertifikatprofile

Mit Zertifikatprofilen kann Intune ein Zertifikat für einen Benutzer oder ein Gerät ausstellen. Intune unterstützt folgende Optionen:

-   Simple Certificate Enrollment-Protokoll (SCEP)

-   Vertrauenswürdiges Stammzertifikat

-   PFX-Zertifikat

Es wird empfohlen zu dokumentieren, welche Benutzergruppe ein Zertifikat benötigt, wie viele Zertifikatprofile benötigt werden und welchen Benutzergruppen sie bereitgestellt werden.

>[!NOTE]
> Denken Sie daran, dass das vertrauenswürdige Stammzertifikat für das SCEP-Zertifikat erforderlich ist. Stellen Sie daher sicher, dass alle Benutzer, die ein SCEP-Zertifikat erhalten sollen, außerdem ein vertrauenswürdiges Stammzertifikat erhalten. Wenn SCEP-Zertifikate erforderlich sind, entwerfen und dokumentieren Sie, welche SCEP-Zertifikatvorlagen benötigt werden.

Im folgenden Beispiel wird gezeigt, wie Zertifikate während des Entwurfs dokumentiert werden können:

| **Typ** | **Profilname** | **Geräteplattform** | **Anwendungsfälle** |   
|:---:|:---:|:---:|:---:|
| Stamm-CA | Stamm-CA für Unternehmensgeräte | Android, iOS, Windows Mobile | Unternehmen, BYOD  |                                                           
| SCEP | Benutzerzertifikat | Android, iOS, Windows Mobile | Unternehmen, BYOD |                                                           

##### <a name="wi-fi-profile"></a>Wi-Fi-Profil

WLAN-Profile werden verwendet, um automatisch ein mobiles Gerät mit einem drahtlosen Netzwerk zu verbinden. Intune unterstützt die Bereitstellung von WLAN-Profilen auf allen unterstützten Plattformen.

-   Weitere Informationen zur [Unterstützung von WLAN-Profilen in Intune](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune).

Im Folgenden sehen Sie ein Beispiel eines Entwurfs für ein WLAN-Profil:

| **Typ** | **Profilname** | **Geräteplattform** | **Anwendungsfälle** |   
|:---:|:---:|:---:|:---:|
| WLAN | WLAN-Profil Asien | Android | Unternehmen, BYOD Region Asien|                                                           
| WLAN | WLAN-Profil Nordamerika | Android, iOS, Windows 10 Mobile | Unternehmen, BYOD Region Nordamerika |                                                           

##### <a name="vpn-profile"></a>VPN-Profil

Anhand von VPN-Profilen können Benutzer von Remotestandorten aus sicher auf Ihr Netzwerk zugreifen. Intune unterstützt VPN-Profile von nativen mobilen VPN-Verbindungen und Drittanbietern.

-   Weitere Informationen zu [von Intune unterstützten VPN-Profilen und Anbietern](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune).

Es folgt ein Beispiel für das Dokumentieren des Entwurfs eines VPN-Profils.

| **Typ** | **Profilname** | **Geräteplattform** | **Anwendungsfälle** |   
|:---:|:---:|:---:|:---:|
| VPN | VPN Cisco beliebiges Verbindungsprofil | Android, iOS, Windows 10 Mobile | Unternehmen, BYOD Nordamerika und Deutschland|                                                           
| VPN | Pulse Secure | Android | Unternehmen, BYOD Region Asien |                                                           

##### <a name="email-profile"></a>E-Mail-Profil

E-Mail-Profile ermöglichen die automatische Einrichtung eines E-Mail-Clients mit Verbindungsinformationen und der E-Mail-Konfiguration. Intune unterstützt E-Mail-Profile auf einigen Geräten.

-   Weitere Informationen zu [E-Mail-Profilen](https://docs.microsoft.com/en-us/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) und den unterstützten Plattformen.

Unten sehen Sie ein Beispiel für das Dokumentieren des Entwurfs von E-Mail-Profilen:

| **Typ** | **Profilname** | **Geräteplattform** | **Anwendungsfälle** |   
|:---:|:---:|:---:|:---:|
| E-Mail-Profil | iOS-E-Mail-Profil | iOS | Unternehmen – Information Worker BYOD |                                                           
| E-Mail-Profil | Android Knox-E-Mail-Profil | Android Knox | BYOD |

### <a name="apps"></a>Apps

Intune unterstützt auf verschiedene Weise die Bereitstellung von Apps für Benutzer oder Geräte. Typen bereitgestellter Anwendungen können Softwareinstallations-Apps, Apps aus einem öffentlichen App Store, externe Links oder verwaltete iOS-Apps sein. Zusätzlich zu einzelnen App-Bereitstellungen können per Volumenlizenz erworbene Apps über die VPPs (Volume Purchase Program) für iOS und Windows verwaltet und bereitgestellt werden. Im Folgenden finden Sie weitere Informationen dazu, wie Apps und VPPs von Intune unterstützt werden.

-   Weitere Informationen zu [App-Typen](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune)

-   Weitere Informationen zum [Apple Volume Purchase Program für Unternehmen (VPP)](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune).

-   Weitere Informationen zu [Windows Store für Unternehmen](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune).

#### <a name="app-type-requirements"></a>Anforderungen an App-Typen

Da Apps für Benutzer und Geräte bereitgestellt werden können, empfiehlt es sich zu entscheiden, welche Anwendungen von Intune verwaltet werden sollen. Versuchen Sie beim Zusammenstellen der Liste folgende Fragen zu beantworten:

-   Ist für die Apps eine Integration mit Cloud-Diensten erforderlich?

-   Sind alle Apps für BYOD-Benutzer verfügbar?

-   Welche Bereitstellungsoptionen stehen für diese Apps zur Verfügung?

-   Muss Ihr Unternehmen seinen Partnern Zugriff auf Daten von SaaS-Apps (Software-as-a-Service) ermöglichen?

-   Ist für die Apps Internetzugriff von den Benutzergeräten aus erforderlich?

-   Sind die Apps in einem App Store öffentlich verfügbar, oder handelt es sich um benutzerdefinierte branchenspezifische Apps?


>[!TIP]
> Sehen Sie sich die [verschiedenen Anwendungstypen an, die von Intune unterstützt werden](https://docs.microsoft.com/intune/deploy-use/add-apps).

#### <a name="app-protection-policies"></a>App-Schutzrichtlinien

Durch App-Schutzrichtlinien werden Datenverluste auf ein Minimum reduziert, indem sie definieren, wie Unternehmensdaten von der Anwendung verwaltet werden. Intune unterstützt App-Schutzrichtlinien für jede Anwendung, die mit der Verwaltung mobiler Apps funktionieren soll. Beim Entwerfen der App-Schutzrichtlinie müssen Sie festlegen, welche Einschränkungen für Unternehmensdaten in einer bestimmten App gelten sollen. Es wird empfohlen, sich über die Funktionsweise von [App-Schutzrichtlinien](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) zu informieren. Im Folgenden finden Sie ein Beispiel für das Dokumentieren der vorhandenen Anwendungen und der entsprechenden Schutzmaßnahmen.

| **Anwendung** | **Zweck** | **Plattformen** | **Anwendungsfall** | **App-Schutzrichtlinie** |
|:---:|:---:|:---:|:---:|:---:|
| Outlook Mobile  | Verfügbar | iOS | Unternehmen – Führungskräfte | Jailbreak nicht möglich, Verschlüsseln von Dateien |                                                         
| Word | Verfügbar | iOS, Android – Samsung Knox, andere als Knox, Windows 10 Mobile | Unternehmen, BYOD | Jailbreak nicht möglich, Verschlüsseln von Dateien |                                                         

#### <a name="compliance-policies"></a>Konformitätsrichtlinien

Konformitätsrichtlinien bestimmen, ob ein Gerät bestimmten Anforderungen entspricht. Intune ermittelt anhand von Konformitätsrichtlinien, ob ein Gerät als konform oder als nicht konform betrachtet wird. Der Konformitätsstatus kann dann dazu verwendet werden, den Zugriff auf Unternehmensressourcen einzuschränken. Wenn bedingter Zugriff erforderlich ist, wird empfohlen, eine [Gerätekonformitätsrichtlinie](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) zu entwerfen. Bestimmen Sie anhand der Anforderungen und Anwendungsfälle, wie viele Gerätekonformitätsrichtlinien erforderlich sind und welche Benutzergruppen als Zielbenutzergruppen verwendet werden sollen. Darüber hinaus müssen Sie festlegen, wie lange ein Gerät ohne Einchecken offline sein kann, bevor es als nicht konform betrachtet wird.

Es folgt ein Beispiel zum Entwerfen einer Konformitätsrichtlinie:

| **Name der Richtlinie** | **Geräteplattform** | **Einstellungen** | **Zielgruppe** |   
|:---:|:---:|:---:|:---:|
| Kompatibilitätsrichtlinie | iOS, Android – Samsung Knox, andere als Knox, Windows 10 Mobile | PIN – erforderlich, Jailbreak nicht möglich | Unternehmen, BYOD |

#### <a name="conditional-access-policies"></a>Bedingte Zugriffsrichtlinien

Bedingter Zugriff wird verwendet, um nur konformen Geräten den Zugriff auf Unternehmensressourcen zu erlauben. Intune kann mit dem gesamten Funktionsumfang von EMS (Enterprise Mobility + Security) zum Steuern des Zugriffs auf Unternehmensressourcen eingesetzt werden. Sie müssen festlegen, ob der bedingte Zugriff erforderlich ist und was gesichert werden muss.

-   Weitere Informationen zum [bedingten Zugriff](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

Legen Sie für den Onlinezugriff fest, für welche Plattformen und Benutzergruppen die Richtlinien für bedingten Zugriff vorgesehen sind.

Darüber hinaus müssen Sie bestimmen, ob Sie den dienstübergreifenden Intune-Connector für Exchange Online oder Exchange lokal installieren/konfigurieren müssen.

Weitere Informationen zum Installieren und Konfigurieren von dienstübergreifenden Intune-Connectors:

-   [Exchange Online](https://docs.microsoft.com/intune/deploy-use/intune-service-to-service-exchange-connector)

-   [Exchange lokal](https://docs.microsoft.com/intune/deploy-use/intune-on-premises-exchange-connector)

Hier sehen Sie ein Beispiel für das Dokumentieren von Richtlinien für den bedingten Zugriff:

| **Dienst** | **Plattformen für moderne Authentifizierung** | **Standardauthentifizierung** | **Anwendungsfälle** |   
|:---:|:---:|:---:|:---:|
| Exchange Online | iOS, Android | Nicht konforme Geräte auf von Intune unterstützten Plattformen blockieren | Unternehmen, BYOD |
| SharePoint Online | iOS, Android |  | Unternehmen, BYOD |

## <a name="next-section"></a>Nächster Abschnitt

Der nächste Abschnitt enthält Hinweise zum [Intune-Implementierungsprozess](section-8-onboarding-process.md).



<!--HONumber=Jan17_HO3-->


