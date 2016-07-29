---
title: Archiv der Neuheiten | Microsoft Intune
description: 
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 805dfa1eeb81f4407066e27f203f315451937f8b
ms.openlocfilehash: acf502bdf73176450157535577047c9428aabfd1


---
## Dezember 2015
### Änderungen und Updates für das Unternehmensportal von Microsoft
In dieser Version wurden die folgenden Änderungen am Unternehmensportal vorgenommen:

**Android-Unternehmensportal-App**

Die folgenden Änderungen wurden vorgenommen, um neuen Google-Anforderungen zu entsprechen. Auf Geräten mit Android 6.0 und höher werden den Benutzern zwei neue Meldungen angezeigt:
* Zulassen, dass das Unternehmensportal Telefonanrufe tätigt und verwaltet?
* Unternehmensportal den Zugriff auf Fotos, Medien und Dateien auf Ihrem Gerät erlauben?

Ausführliche Informationen über diese beiden Meldungen finden Sie in der folgenden Tabelle.



Meldungstext  |Zulassen, dass das Unternehmensportal Telefonanrufe tätigt und verwaltet?  
---------|---------
Bedeutung der Meldung     |  Erlaubt, dass Telefonnummer und IMEI des Geräts des Benutzers an den Intune-Dienst gesendet und in der Verwaltungskonsole auf der Seite „Hardware“ angezeigt werden.   </br></br>**HINWEIS: Die Unternehmensportal-App tätigt oder verwaltet keine Telefonanrufe!** Der Meldungstext wird von Google gesteuert und kann nicht geändert werden. </br></br>Zum Anzeigen der Seite **Hardware** wechseln Sie zu **Gruppen** > **Alle mobilen Geräte** > **Geräte**. Wählen Sie das Gerät des Benutzers aus, und wechseln Sie zu **Eigenschaften anzeigen** > **Hardware**.    
Ort und Zeitpunkt für die Anzeige der Meldung  | Die Meldung wird angezeigt, wenn Benutzer sich zum ersten Mal bei der Unternehmensportal-App anmelden, um mit der Registrierung ihres Geräts zu beginnen.|         
Wenn Benutzer den Zugriff zulassen, ...  |  ... werden Telefonnummer und IMEI des Geräts in der Verwaltungskonsole auf der Seite „Hardware“ angezeigt. |         
Wenn Benutzer den Zugriff nicht zulassen, ...     | ... können sie die Unternehmensportal-App weiterhin verwenden und ihr Gerät registrieren, die Felder für Telefonnummer und IMEI des Geräts des Benutzers auf der Seite „Hardware“ in der Verwaltungskonsole sind jedoch leer.       </br></br> Wenn Benutzer den Zugriff verweigern und sich dann das nächste Mal bei der Unternehmensportal-App anmelden, wird in der Meldung ein Kontrollkästchen **Nicht mehr nachfragen** angezeigt, das die Benutzer aktivieren können, damit diese Meldung nicht mehr angezeigt wird.</br></br>Wenn Benutzer den Zugriff zunächst erlauben, später aber verweigern, wird die Meldung wieder angezeigt, wenn sie sich nach der Registrierung das nächste Mal bei der Unternehmensportal-App anmelden.</br></br>Wenn Benutzer den Zugriff später erlauben möchten, müssen sie zu **Einstellungen** > **Apps** > ** Unternehmensportal** > **Berechtigungen** > **Telefon** wechseln, um die Berechtigung zu aktivieren.
Weitere Informationen     |  Für Ihre Benutzer: [Anmelden beim Unternehmensportal](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_signin_cp)  </br></br>Für IT-Experten: Die Informationen in dieser Tabelle finden Sie auch unter [Hilfe für Ihre Benutzer zum Verständnis der Meldungen der Unternehmensportal-App](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   

Meldungstext  |Unternehmensportal den Zugriff auf Fotos, Medien und Dateien auf Ihrem Gerät erlauben?  
---------|---------
Bedeutung der Meldung     |  Erlaubt, dass Datenprotokolle auf die SD-Karte des Geräts geschrieben werden, wodurch Protokolle unter Verwendung eines USB-Kabels verschoben werden können.   </br></br>**HINWEIS: Die Unternehmensportal-App greift nicht auf Fotos, Medien und Dateien der Benutzer zu.** Der Meldungstext wird von Google gesteuert und kann nicht geändert werden.     
Ort und Zeitpunkt für die Anzeige der Meldung  | Die Meldung wird angezeigt, wenn Benutzer auf **Daten senden** tippen, um Datenprotokolle an ihren IT-Administrator zu senden.|         
Wenn Benutzer den Zugriff zulassen, ...  |  ... werden die Protokolle auf die SD-Karte kopiert. |         
Wenn Benutzer den Zugriff nicht zulassen, ...     | Sie können weiterhin Datenprotokolle senden, aber die Protokolle werden nicht auf die SD-Karte des Geräts kopiert.       </br></br> Wenn Benutzer den Zugriff verweigern und sich dann das nächste Mal bei der Unternehmensportal-App anmelden, wird in der Meldung ein Kontrollkästchen **Nicht mehr nachfragen** angezeigt, das die Benutzer aktivieren können, damit diese Meldung nicht mehr angezeigt wird.</br></br>Wenn Benutzer den Zugriff zunächst erlauben, später aber verweigern, wird die Meldung wieder angezeigt, wenn sie das nächste Mal Protokolle senden.</br></br>Wenn Benutzer den Zugriff später erlauben möchten, müssen sie zu **Einstellungen** > **Apps** > ** Unternehmensportal** > **Berechtigungen** > **Speicherung** wechseln, um die Berechtigung zu aktivieren.
Weitere Informationen     |  Für Ihre Benutzer: [Senden von Diagnosedatenprotokollen an Ihren IT-Administrator per E-Mail](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_send_diag_logs)  </br></br>Für IT-Experten: Die Informationen in dieser Tabelle finden Sie auch unter [Hilfe für Ihre Benutzer zum Verständnis der Meldungen der Unternehmensportal-App](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   


**iOS-Unternehmensportal-App**
* Benutzer können Diagnoseprotokolle jetzt mit Microsoft Outlook oder anderen E-Mail-Apps an den IT-Administrator senden. Zuvor konnte nur die systemeigene App verwendet werden.
* Die Unterstützung für das Geräteregistrierungsprogramm (DEP) von Apple und im Unternehmen registrierte Geräte wurde verbessert. Weitere Informationen finden Sie unter [Sie werden aufgefordert, Ihr Gerät zu identifizieren, wenn Sie versuchen, sich zu registrieren](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_id_your_device).
* In der Liste der registrierten Geräte des Benutzers wird neben dem Gerät, das der Benutzer gerade verwendet, jetzt ein grünes Häkchen angezeigt. Bevor dieses Häkchen hinzugefügt wurde, konnten Benutzer nicht erkennen, welches der registrierten Geräte sie gerade verwendeten.

**Windows-Unternehmensportal-App**

Microsoft erfasst automatisch anonyme Daten über die Leistung und die Verwendung des Unternehmensportals, um Microsoft-Produkte und -Dienste zu verbessern. Endbenutzer können die Datenerfassung über die Einstellung "Nutzungsdaten" auf ihrem Gerät deaktivieren, Administratoren haben jedoch keine Kontrolle über die Datenerfassung und können die Auswahl der Endbenutzer für diese Einstellung nicht ändern.



## November 2015
### App-Verwaltung
Intune unterstützt Verwaltungsrichtlinien für mobile Anwendungen, die dabei helfen zu verhindern, dass Verbraucher-Apps und -Dienste auf Unternehmensdaten zugreifen können. In der Vergangenheit wurden diese Richtlinien nur für mobile Apps auf Geräten erzwungen, die auch für die Verwaltung mobiler Geräte in Intune registriert wurden.

Mit dem Update dieses Monats erweitert Intune seine MAM-Funktionen auf neue Geräteklassen. Zusätzlich zu in Intune registrierten Geräten können Sie MAM-Richtlinien jetzt auf Folgendem erzwingen:
* Auf Geräten, die von einer anderen Lösung zur Geräteverwaltung verwaltet werden
* Auf Geräten, die in keinem Geräteverwaltungssystem registriert sind, d. h. in der Regel BYO-Geräte (privater Besitz)

Weitere Informationen zu diesen neuen MAM-Funktionen finden in den folgenden Blogbeiträgen:
* [Erhöhen der verwalteten mobilen Produktivität](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)
* [Ankündigung neuer Microsoft Enterprise Mobility-Funktionen](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)

Darüber hinaus folgen hier einige Highlights und zusätzliche Informationen zu MAM-Funktionen von Intunes:
* Unternehmensdaten werden von den Verbraucherdaten in Apps isoliert, die für Intunes aktiviert sind, einschließlich Office Mobile-Apps, Drittanbieter-Apps, die das Intune-SDK eingeführt haben oder Line-of-Business-Apps, die von Intune umschlossen sind.
* Unternehmensdaten können von Unternehmens-Apps gemeinsam genutzt werden (**Ausschneiden, Kopieren und Einfügen**), während die Freigabe von Unternehmensdaten für private Apps verhindert wird. Weitere Informationen finden Sie unter [Wie App-Daten mit MAM-Richtlinien geschützt werden](https://technet.microsoft.com/library/mt627825.aspx). Dieses Beispielszenario, [Verwenden der Microsoft Word-App für berufliche und private Zwecke](https://technet.microsoft.com/library/mt627827.aspx), veranschaulicht, wie die Freigabe von Unternehmensdaten für private Apps verhindert wird.
* Richtlinien zur Verhinderung des Verlusts von Schlüsseldaten wie anwendungsabhängige PIN, „Speichern unter“-Steuerelemente und die Freigabe verwalteter Daten zwischen Apps. Eine Liste aller Richtlinien finden Sie unter [Erstellen und Bereitstellen von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx).
* Word, Excel, PowerPoint, Outlook, OneNote und OneDrive for Business verfügen jeweils über diese neuen Funktionen und können mit und ohne Geräteregistrierung verwaltet werden. Die Funktionen zum Schutz vor Datenverlust sind nativ in den Office-Apps im Apple Store oder Google Play Store integriert und erfordern kein App-Wrapping oder -Sideloading.
* Informationen zu den ersten Schritten finden Sie unter [Erste Schritte mit Verwaltungsrichtlinien für mobile Apps im Azure-Portal](https://technet.microsoft.com/library/mt627830.aspx). Weitere Informationen zum Konfigurieren und Bereitstellen von Verwaltungsrichtlinien für mobile Apps finden Sie unter [Erstellen und Bereitstellen von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx).
* Wenn sich Endbenutzer bei der App mit ihren Unternehmensanmeldeinformationen authentifizieren, werden die Funktionen zum Schutz vor Datenverlust automatisch eingerichtet. Der Abschnitt [Endbenutzer-Erfahrung mit Apps, die den Microsoft Intune-Verwaltungsrichtlinien für mobile Apps unterliegen](https://technet.microsoft.com/library/mt627827.aspx) enthält einige Beispielszenarien für den Zugriff auf OneDrive auf iOS- und Android-Geräten.
* Sie funktionieren für iOS- und Android-Geräte.

Die Liste der [Microsoft-Apps zur Verwendung mit den Microsoft Intune-Verwaltungsrichtlinien für mobile Anwendungen](https://technet.microsoft.com/library/dn708489.aspx) wurde aktualisiert, um die neuesten Apps anzuzeigen.

### Geräteverwaltung
 **Geräteverwaltung unter Mac OS X** Mit Intune können Sie jetzt Mac OS X-Geräte registrieren und verwalten. Mit den Mac OS X-Geräten haben Sie folgende Möglichkeiten:
* Geräte für die Verwaltung mit Intune registrieren. Weitere Informationen finden Sie unter [Einrichten der iOS- und Mac-Verwaltung mit Microsoft Intune](https://technet.microsoft.com/library/dn408185.aspx).
* Steuern Sie Geräteeinstellungen mit einer allgemeinen Konfigurationsrichtlinie. Weitere Informationen finden Sie unter [Einstellungen für Mac OS X-Konfigurationsrichtlinien in Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx).
* Stellen Sie Mac OS X-Einstellungen bereit, die Sie mit Apple Configurator erstellt haben. Weitere Informationen finden Sie unter [Benutzerdefinierte Mac OS X-Richtlinieneinstellungen in Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx).
* Sammeln Sie Hardware- und Softwareinventurdaten von Mac OS X-Clients. Weitere Informationen finden Sie unter [Verstehen Sie Ihre Geräte mithilfe des Inventars in Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx).
* Führen Sie neue Berichte aus, die Details zu den Mac OS X-Geräten anzeigen, die Sie verwalten. Weitere Informationen finden Sie unter [Einblicke in Microsoft Intune-Vorgänge durch Berichte](https://technet.microsoft.com/library/dn646977.aspx).

**Neue Einstellungen für den Edge-Browser für Windows 10-Geräte** Es wurden neue Einstellungen zur allgemeinen Konfigurationsrichtlinie von Windows 10 hinzugefügt, mit denen Sie die Einstellungen und Features des Microsoft Edge-Browsers verwalten können. Weitere Informationen finden Sie unter [Einstellungen für Windows 10-Konfigurationsrichtlinien in Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx).

**E-Mail-Profile** Eine neue Richtlinie für E-Mail-Profile wurde für Windows 10-Desktopgeräte sowie für mobile Windows 10-Geräte hinzugefügt. Weitere Informationen finden Sie unter [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](https://technet.microsoft.com/library/dn646984.aspx).

**Neue Einstellungen für die Kompatibilitätsrichtlinie** Die folgenden neuen Einstellungen für die Sicherheits- und Systemrichtlinie wurden zur Liste der Kompatibilitätsrichtlinien hinzugefügt:
* Um sicherzustellen, dass auf Geräten mit Windows 8.1 oder höher, die Zugriff auf Ihre Unternehmensressourcen haben, die neuesten Updates installiert sind, verwenden Sie die Einstellung **Automatische Updates erforderlich**. Sie können auch die Art der Updates angeben, die automatisch installiert werden – entweder alle als wichtig gekennzeichneten Updates oder alle als wichtig oder empfohlen gekennzeichneten Updates. Eine vollständige Liste der Einstellungen für die Kompatibilitätsrichtlinie finden Sie unter [Verwalten von Gerätekompatibilitätsrichtlinien für Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx).
* Die Kombination der neuen Einstellung **Kennwort anfordern, wenn das Gerät aus dem Leerlauf zurückkehrt** mit der vorhandenen Einstellung **Minuten Inaktivität vor erneuter Anforderung des Kennworts** ermöglicht es Ihnen, eine Kompatibilitätseinstellung zu erstellen, bei der der Endbenutzer ein Kennwort eingeben muss, um ein Gerät zu verwenden, das für einen bestimmten Zeitraum inaktiv war.

**Neue Richtlinienoptionen für den bedingten Zugriff** Sie können Richtlinien für bedingten Zugriff auf **alle Benutzer** in neuen oder vorhandenen Richtlinien für den bedingten Zugriff anwenden. Alle für Intune und Office 365 lizenzierten Benutzer müssen ihre Geräte registrieren. Wenn Intune die Geräteplattform nicht unterstützt, wird der Zugriff für Clientanwendungen mithilfe der auf der [Active Directory-Authentifizierung basierenden Anmeldung (moderne Authentifizierung)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) blockiert.

Sie können auch angeben, dass die Richtlinie für den bedingten Zugriff für **alle Plattformen** gelten.  Jede Clientanwendung, die die auf der [Active Directory-Authentifizierung basierende Anmeldung (moderne Authentifizierung)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) verwendet, unterliegt der Richtlinie für den bedingten Zugriff, und wenn die Plattform von Intune nicht unterstützt wird, wird sie blockiert.

### Änderungen und Updates für das Unternehmensportal von Microsoft
In dieser Version wurden die folgenden Änderungen an den Unternehmensportal-Apps vorgenommen:

* **Android**: Es wurde eine Begrüßungsseite zur Android-Unternehmensportal-App hinzugefügt, damit die Benutzer den Zweck der Unternehmensportal-App besser verstehen. Dieser Bildschirm soll Downloads der App durch Benutzer verringern, deren Unternehmen keine Intune-Abonnenten sind.

* **iOS**: Intune unterstützt jetzt die Registrierung von Mac OS X-Geräten über die [Unternehmensportal-Website](https://portal.manage.microsoft.com). Anweisungen finden Sie unter [Registrieren Ihres Mac OS X-Geräts in Intune](https://technet.microsoft.com/library/mt598622.aspx).

* **Unternehmensportal-Website**: Benutzer, die ihre Geräte bei Intune registriert haben, können jetzt ihre Kennung auf der Unternehmensportal-Website mithilfe der Option **Kennung zurücksetzen** zurücksetzen. Früher konnten nur IT-Administratoren Benutzerkennungen zurücksetzen. Die Option „Kennung zurücksetzen“ wird auf Geräten mit Windows 8.1 und Windows RT nicht unterstützt, und die Option wird nur angezeigt, wenn Geräte in der Verwaltung mobiler Geräte (MDM) oder MDM mit Exchange ActiveSync angemeldet sind. Anweisungen für Benutzer finden Sie unter [Zurücksetzen der Kennung](https://technet.microsoft.com/library/mt590895.aspx).

### Änderungen an der Lizenzierung globaler Administratoren
Im Oktober haben wir bekannt gegeben, dass globale Administratoren (auch als Mandantenadministratoren bezeichnet) weiterhin alltägliche Verwaltungsaufgaben ausführen können, ohne über eine separate Intune- oder EMS-Lizenz (Enterprise Mobility Suite) zu verfügen. Wenn globale Administratoren den Dienst jedoch verwenden möchten, um z. B. ihr eigenes Gerät oder ein unternehmenseigenes Gerät zu registrieren bzw. das Intune-Unternehmensportal zu verwenden, benötigen sie wie alle anderen Benutzer eine Intune- oder EMS-Lizenz. Nachfolgenden finden Sie einige zusätzliche Details.
* Mit dem Intune-Unternehmensportal haben Endbenutzer folgende Möglichkeiten:
    * Registrieren ihres Geräts
    * Anzeigen des Gerätestatus
    * Herunterladen von Software, die ein globaler Administrator für das Unternehmen bereitgestellt hat
    * Verwenden von Links zur Kontaktaufnahme mit der IT-Abteilung, die vom globalen Administrator veröffentlicht wurden

    [Erfahren Sie mehr über das Unternehmensportal](https://technet.microsoft.com/library/dn646966.aspx#BKMK_CompanyPortal) und über [Methoden zum Anpassen des Unternehmensportals](https://technet.microsoft.com/library/dn646983.aspx#BKMK_ConfigureCompanyPortal).
* Die Person, die im Namen des Unternehmens für den Erwerb von Intune oder EMS unterzeichnet, wird automatisch zum ersten globalen Administrator des Mandanten. Im Herbst hat Intune damit begonnen, dem allerersten globalen Administrator im Rahmen des Wechsels zum [Office 365-Portal](http://portal.office.com/) und der Deaktivierung des [Intune-Kontoportals](http://account.manage.microsoft.com/) automatisch eine Intune- oder EMS-Lizenz zuzuweisen. Alle zusätzlich hinzugefügten globalen Administratoren können die tägliche Verwaltung weiterhin ohne separate Intune- oder EMS-Lizenz durchführen. Wenn sie als Endbenutzer agieren und ihr eigenes (oder unternehmenseigenes) Gerät registrieren oder Software aus dem Unternehmensportal herunterladen, ist wie bei allen anderen Benutzern eine Lizenz erforderlich.
* Die Änderung wird stufenweise ab Januar 2016 eingeführt.
* Diese Änderung sollte sich für Microsoft-Partners nicht auf die Möglichkeit auswirken, den Dienst im Auftrag des Kunden zu verwalten. Für Endbenutzeraufgaben muss ein Benutzer eine Intune- oder EMS-Lizenz besitzen, um ein Gerät zu registrieren und auf Software aus dem Unternehmensportal zuzugreifen bzw. diese herunterzuladen.

Wenn Sie Fragen zu dieser Änderung haben, können Sie sich an das Intune-Supportteam wenden:
* [Microsoft Intune-Supportkanäle](https://technet.microsoft.com/library/jj839713.aspx)
* [Communityunterstützung](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

Allgemeines Feedback zu Microsoft Intune, z. B. zur Archivierung von DCRs (Design Change Requests) oder bei Fehlern, finden Sie unter [Intune User Voice](https://microsoftintune.uservoice.com/).


### Neuerungen in der Intune-Dokumentation – November 2015
**Neuer Inhalt**
* [Einstellungen für die Mac OS X-Konfigurationsrichtlinie in Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx): Steuern von Geräteeinstellungen und Features für Mac OS X-Geräte.
* [Benutzerdefinierte Mac OS X-Richtlinieneinstellungen in Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx): Bereitstellen von Mac OS X-Geräteeinstellungen, die mit dem Apple Configurator-Tool erstellt wurden.
* [Konfigurieren von App-Richtlinien zum Schutz vor Datenverlust mit Microsoft Intune](https://technet.microsoft.com/library/mt627825.aspx): Enthält Informationen zu den Szenarien, die von Richtlinien für die Verwaltung mobiler Apps unterstützt werden, und Informationen zur Funktionsweise der Richtlinie zum Schutz der Daten.
* [Erste Schritte mit Verwaltungsrichtlinien für mobile Apps im Azure-Portal](https://technet.microsoft.com/library/mt627830.aspx): Anforderungen für die ersten Schritte mit dem Azure-Vorschauportal für Verwaltungsrichtlinien für mobile Apps.
* [Erstellen und Bereitstellen von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx): Enthält eine schrittweise Anleitung zum Erstellen von Verwaltungsrichtlinien für mobile Apps im Azure-Vorschauportal.
* [Überwachen der Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](https://technet.microsoft.com/library/mt627824.aspx): Informationen zum Überwachen Ihrer Verwaltungsrichtlinien für mobile Apps mithilfe des Azure-Vorschauportals.
* [ Microsoft Intune-Richtlinien für die Verwaltung von mobilen Apps und iOS-Feature „Öffnen in“](https://technet.microsoft.com/library/mt627821.aspx): Informationen zur Funktionsweise der Verwaltungsrichtlinien für mobile Apps mit dem iOS-Feature „Öffnen in“.
* [Endbenutzer-Erfahrung mit Apps, die den Microsoft Intune-Verwaltungsrichtlinien für mobile Apps unterliegen](https://technet.microsoft.com/library/mt627827.aspx): Informationen zum Endbenutzererlebnis bei der Verwendung von Apps, die der Verwaltungsrichtlinie für mobile Apps zugeordnet sind.
* [Löschen verwalteter Unternehmensdaten aus Apps mit Microsoft Intune](https://technet.microsoft.com/library/mt627826.aspx): Informationen zum Entfernen von Unternehmensdaten aus Apps.

**Aktualisierter Inhalt**
* [Einstellungen für Windows 10-Konfigurationsrichtlinien in Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx): Es wurden neue Einstellungen für den Edge-Browser hinzugefügt.
* [Einrichten der iOS- und Mac-Verwaltung mit Microsoft Intune](http://technet.microsoft.com/library/dn408185.aspx): Es wurden Informationen zum Registrieren von Mac OS X-Geräten hinzugefügt.
* [Verstehen Sie Ihre Geräte mithilfe des Inventars in Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx): Es wurden Informationen zum Inventar hinzugefügt, das von Mac OS X-Geräte gesammelt wurde. Zudem wurde das Thema mit den neuesten Informationen für alle Plattformen aktualisiert.
* [Einblicke in Microsoft Intune-Vorgänge durch Berichte](https://technet.microsoft.com/library/dn646977.aspx): Es wurden Informationen zu den beiden neuen Berichten hinzugefügt, mit denen Informationen zu Ihren verwalteten Mac OS X-Geräten angezeigt werden können.
* [Verwalten von Gerätekonformitätsrichtlinien für Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx): Es wurden Informationen zu den neuen Konformitätsrichtlinien für die Anforderung automatischer Updates und Kennwörter hinzugefügt, wenn ein Gerät aus dem Leerlauf zurückkehrt.
* [Verwalten des E-Mail-Zugriffs mit Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx): Es wurden Informationen zu der Möglichkeit zum Anwenden der Richtlinie für den bedingten Zugriff für alle Plattformen und alle Benutzer hinzugefügt.
* [Verwalten des Zugriffs auf SharePoint Online mit Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx): Es wurden Informationen zu der Möglichkeit zum Anwenden der Richtlinie für den bedingten Zugriff für alle Plattformen und alle Benutzer hinzugefügt.

## Oktober 2015

### Aktualisierungen beim bedingten Zugriff für Exchange lokal
**Sie können jetzt den Zugriff auf Exchange ActiveSync-E-Mail für konforme Geräte zulassen, die bei Intune registriert sind, wenn die globale Exchange-Regel auf „Blockieren“ oder „Isolieren“ festgelegt ist.** Bisher mussten Sie, um den E-Mail-Zugriff auf registrierten und konformen Geräten zuzulassen, die globale Exchange-Standardregel auf **Zulassen** festlegen.

Mit diesem Dienstupdate ist diese Einstellung keine Voraussetzung mehr für den bedingten Zugriff. Wenn Ihre Exchange-Umgebung erfordert, dass Ihre globale Standardregel auf **Blockieren/Isolieren** festgelegt ist, aktivieren Sie einfach das Kontrollkästchen **Standardregel außer Kraft setzen** auf der Seite für den bedingten Zugriff in Exchange lokal. Das Thema [Verwalten des E-Mail-Zugriffs mit Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx) enthält mehr Detailinformationen zu den Regeln und den resultierenden Endbenutzerbenachrichtigungen.

**Neue One-Click-Quarantäneumgebung**. Wir haben die E-Mail-Quarantäneumgebung so vereinfacht, dass die Registrierung mit nur einem Klick möglich ist. Mit diesem Dienstupdate können Endbenutzer auf einen einzelnen Link in der Quarantäne-E-Mail klicken, um den Registrierungsprozess in der Unternehmensportal-App abzuschließen.
### Updates für die Verwaltung von mobilen Geräten und Apps
**Android**: Alle Intune-Verwaltungsfeatures unterstützen jetzt Android 6.0 (Marshmallow), wie in diesem Blogbeitrag beschrieben: [Microsoft Intune bietet Day-0-Unterstützung für Android Marshmallow](http://blogs.technet.com/b/microsoftintune/archive/2015/10/09/microsoft-intune-to-provide-day-0-support-for-android-marshmallow.aspx).

**iOS**: Sie können keine neuen App-Bereitstellungen mehr für iOS-Geräte erstellen, auf denen eine ältere Version als iOS 7.1 ausgeführt wird. Alle vorhandenen App-Bereitstellungen auf Geräten, auf denen eine ältere Version als iOS 7.1 ausgeführt wird, funktionieren weiterhin und werden auch weiterhin von Intune verwaltet.

**Windows 10**: Intune unterstützt jetzt die Bereitstellung von universellen Windows 10-Apps mithilfe des Softwareinstallationsprogramm-Typs **App-Paket für Windows**. Ausführlichere Informationen und die Anforderungen finden Sie unter [Erste Schritte bei der Bereitstellung von Apps in Microsoft Intune](http://technet.microsoft.com/en-US/library/dn646955.aspx).


### Änderungen und Updates für die Unternehmensportal-Apps von Microsoft
In dieser Version wurden die folgenden Änderungen an den Unternehmensportal-Apps vorgenommen: **iOS** Der Unternehmensportal-App wurden neue Schaltflächen hinzugefügt, um Benutzer das Senden von Diagnoseprotokollen an ihre IT-Administratoren zu erleichtern:

|Schaltflächenname|Position in der Oberfläche|
|------------|---------------|
|Bericht|Fehlerwarnmeldungen|
|Diagnosebericht senden|Bildschirm „Info“ in der Unternehmensportal-App|



## September 2015
### Updates für die Verwaltung von mobilen Geräten und Apps
**Alle Intune-Verwaltungsfunktionen für iOS unterstützen jetzt iOS 9** Ausführliche Informationen zu den iOS 9-Verwaltungsfunktionen finden Sie in [diesem Blogbeitrag](http://blogs.technet.com/b/microsoftintune/archive/2015/09/09/day-zero-support-for-ios-9-with-intune.aspx).

**Neue Konfigurationsrichtlinie für mobile Apps für iOS** Verwenden Sie die neue Konfigurationsrichtlinie für mobile Apps, um automatisch die Einstellungen bereitzustellen, die eine iOS-App bei der Ausführung möglicherweise benötigt. So könnten Sie beispielsweise einen Netzwerkport oder einen Benutzernamen bereitstellen. Weitere Informationen finden Sie unter [Konfigurieren von Apps mit Konfigurationsrichtlinien für mobile Apps in Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx).

**Einfachere App-Verwaltung für iOS 9-Benutzer**
 In diesem Release können Sie bereits bereitgestellte Apps für iOS 9-Benutzer in die Intune-Verwaltung integrieren. Wenn Sie bei früheren Versionen von iOS eine App bereitstellen und eine nicht verwaltete Version der App bereits auf einem Gerät installiert ist, müssen Sie den Benutzer nach wie vor bitten, die App manuell zu deinstallieren, bevor Intune die verwaltete App installieren kann.

 Aber beginnend mit dieser Version von Intune können Sie Benutzer von iOS 9-Geräten jetzt auffordern, Intune die Verwaltung der App und die Anwendung aller relevanten Verwaltungsrichtlinien für mobile Anwendungen zu erlauben.

 **Windows 10-Verwaltung** Verwenden Sie die neue [allgemeine Windows 10-Konfigurationsrichtlinie](https://technet.microsoft.com/library/mt404697.aspx), um die Kennwort-, Geräte-, Browser- und sonstigen Einstellungen für registrierte Geräte, auf denen Windows 10 und Windows 10 Mobile ausgeführt wird, zu konfigurieren.

 **Erstellen und Bereitstellen von Apps auf registrierten Windows 10-Geräten** Dank eines neuen Softwareinstallationsprogramm-Typs, Windows Installer über MDM (&#42;.msi), können Sie Windows Installer-Apps für registrierte Geräte, auf denen Windows 10 ausgeführt wird, erstellen und darauf bereitstellen. Weitere Informationen finden Sie unter [Erste Schritte bei der Bereitstellung von Apps in Microsoft Intune](https://technet.microsoft.com/library/dn646955.aspx).

### Änderungen und Updates für die Unternehmensportal-Apps von Microsoft
In dieser Version wurden die folgenden Änderungen an den Unternehmensportal-Apps vorgenommen:

**iOS**
* Microsoft erfasst automatisch anonyme Daten über die Leistung und die Verwendung des Unternehmensportals, um Microsoft-Produkte und -Dienste zu verbessern. Endbenutzer können die Datenerfassung über die Einstellung "Nutzungsdaten" auf ihrem Gerät deaktivieren, Administratoren haben jedoch keine Kontrolle über die Datenerfassung und können die Auswahl der Endbenutzer für diese Einstellung nicht ändern.
* Unterstützung für Vollbildauflösung auf dem iPhone 6 und 6 Plus
* Fehlerbehebungen für verbesserte Sicherheit.

### Neuerungen in der Intune-Dokumentation – September 2015
**Neue Themen**

|Name|Details|
|----|--------|
|[Einstellungen für Windows 10-Konfigurationsrichtlinien in Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx)|Dies ist eine neue Konfigurationsrichtlinie, mit der Sie die Einstellungen und Funktionen auf Geräten verwalten können, auf denen Windows 10 und Windows 10 Mobile ausgeführt wird.
| [Konfigurieren von Apps mit Konfigurationsrichtlinien für mobile Apps in Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx)|Dies ist ein neuer Richtlinientyp, mit dem Sie automatisch Einstellungen bereitstellen können, die beim Ausführen einer iOS-App durch den Benutzer möglicherweise erforderlich sind. |

**Aktualisierte Themen**

|Name|Details|
|----|-------|
|[Verwenden von Richtlinien zum Verwalten von Computern und mobilen Geräten mit Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx)|Aktualisiert mit den neuesten Informationen zum Grundverständnis und Erstellen von Richtlinien.|

## August 2015
### Updates für die Verwaltung von mobilen Geräten und Apps
* **Geschäftsbedingungen** für die Intune-Registrierung und den Unternehmenszugriff werden [jetzt mithilfe von Richtlinien verwaltet](https://technet.microsoft.com/library/mt405893.aspx). Sie können verschiedene Sätze von Geschäftsbedingungen bereitstellen, um die Anforderungen bestimmter Benutzergruppen zu erfüllen. Beispielsweise können Sie Geschäftsbedingungen in verschiedenen Sprachen für geografisch definierte Benutzergruppen bereitstellen. Sie können auch [Ihre Geschäftsbedingungen bearbeiten](https://technet.microsoft.com/library/mt405893.aspx#BKMK_TCVers) und angeben, ob die Versionsnummern erhöht werden sollen, sodass Benutzer den neuen Geschäftsbedingungen zustimmen müssen, bevor sie das Unternehmensportal verwenden können.
* **Eine Reihe von Intune-Richtlinien wurde umbenannt** , um die Konsistenz im gesamten Produkt zu erhöhen und sie leichter auffindbar zu machen. Eine Liste aller verfügbaren Intune-Richtlinien finden Sie unter [Verwenden von Richtlinien zum Verwalten von Computern und mobilen Geräten mit Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx).
* **Zertifikatprofile vom Typ „PKCS #12 (.PFX)“** sind für Android 4.0 oder höher und Windows 10 (Desktop und mobil) und höher erhältlich. Für die Verwendung von PFX ist kein NDES-Server erforderlich. Weitere Informationen zum Verwenden von PFX-Zertifikatprofilen finden Sie unter [Aktivieren des Zugriffs auf Unternehmensressourcen mithilfe von Zertifikatprofilen mit Microsoft Intune](http://technet.microsoft.com/library/dn818904.aspx).
* **Einstellungen für Unternehmensgrenzen für Windows 10 Desktop und Mobile** ermöglichen differenzierte VPN-Einstellungen, wie unter [Unterstützen von Benutzern beim Verbinden mit ihrer Arbeit über VPN-Profile in Microsoft Intune](https://technet.microsoft.com/library/dn818905.aspx) beschrieben.
* **Die OneDrive-App für Android unterstützt jetzt mehrere Identitäten.** Dieses und weitere Aktualisierungen an den Verwaltungsrichtlinien für mobile Apps werden in der [Liste der Microsoft-Anwendungen, die verwaltet werden können](https://technet.microsoft.com/library/dn708489.aspx), beschrieben.
* **Umgehung der iOS-Aktivierungssperre** Wenn firmeneigene iOS-Geräte durch eine Aktivierungssperre geschützt sind, müssen Sie vor dem Löschen oder erneuten Aktivieren des Geräts die Apple-ID und das zugehörige Kennwort des Benutzers eingeben. Dies kann ein Problem darstellen, wenn Benutzer das Unternehmen verlassen und ein firmeneigenes Gerät ohne deaktivierte Aktivierungssperre zurückgeben. Sie können die [Intune-Umgehung der Aktivierungssperre](https://technet.microsoft.com/library/mt414176.aspx) verwenden, um dieses Problem zu beheben.

### Bedingter Zugriff für PCs
Sie können jetzt bedingte Zugriffsrichtlinien für PCs konfigurieren. Dadurch können Office-Desktop-Apps auf Exchange Online- und SharePoint Online-Dienste zugreifen.
Um bedingte Zugriffsrichtlinien für PCs zu aktivieren, muss der PC entweder in eine Domäne eingebunden oder kompatibel sein.
* Der Abschnitt **Erste Schritte** in [Verwalten des Zugriffs auf E-Mail und SharePoint mit Microsoft Intune](http://technet.microsoft.com/library/dn818907) enthält eine vollständige Liste der Anforderungen für das Aktivieren des bedingten Zugriffs für PCs.
* Optionen, die Sie festlegen können, um den bedingten Zugriff für E-Mail-Zugriff zu aktivieren, finden Sie unter [Verwalten des E-Mail-Zugriffs mit Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx).
* Optionen, die Sie festlegen können, um den bedingten Zugriff für SharePoint Online zu aktivieren, finden Sie unter [Verwalten des Zugriffs auf SharePoint Online mit Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx).

### Änderungen und Updates für die Unternehmensportal-Apps von Microsoft
In dieser Version wurden die folgenden Änderungen an den Unternehmensportal-Apps vorgenommen:

**Android**

Den Benutzern werden jetzt nach der Anmeldung Anweisungen zur Geräteregistrierung angezeigt, sofern das Gerät noch nicht für die Verwaltung registriert wurde.

### Neuerungen in der Intune-Dokumentation – August 2015
**Neue Themen**

|Titel|Details|
|-----|-------|
|[Unterstützen des Schutz von iOS-Geräten durch Umgehung der Aktivierungssperre für Microsoft Intune](https://technet.microsoft.com/library/mt414176.aspx)|Erfahren Sie, wie Sie Intune verwenden können, um die iOS-Aktivierungssperre zu umgehen, wenn ein Benutzer das Unternehmen verlässt und ein gesperrtes Gerät zurückgibt.|

**Aktualisierte Themen**

|Titel|Details|
|-----|-------|
|[Microsoft-Apps zur Verwendung mit den Microsoft Intune-Verwaltungsrichtlinien für mobile Anwendungen](https://technet.microsoft.com/library/dn708489.aspx)|Aktualisiert mit den neuesten Informationen zu Apps, die Sie mit Verwaltungsrichtlinien für mobile Geräte verwalten können.
|[Verwenden von Richtlinien zum Verwalten von Computern und mobilen Geräten mit Microsoft Intune](http://technet.microsoft.com/library/dn743712.aspx)|Aktualisiert mit den neuesten Richtlinien, die zu Intune hinzugefügt wurden.|
<!---
## July 2015
July updates for Intune are limited to behind-the-scenes enhancements that allow us to continue providing you with a high-quality service experience. New features are not included in this service update.

### Intune Onboarding benefit
Microsoft offers the Intune Onboarding benefit for eligible plans. The Onboarding benefit lets you work remotely with Microsoft specialists to get your Intune environment ready for use. For more information, see [Microsoft Intune Onboarding benefit description](https://technet.microsoft.com/library/mt228266.aspx)
### Changes and updates to Microsoft Company Portal apps
The following changes have been made to the company portal apps in this release.

**Android**

Microsoft automatically collects anonymous data about the performance and use of the company portal to improve Microsoft products and services. End users can turn off data collection by using the Usage Data setting on their device, but administrators have no control over the data collection and cannot change the end user’s selection for this setting.--->



<!--HONumber=Jul16_HO3-->


