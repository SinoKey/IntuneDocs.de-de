---
# required metadata

title: Gängige Arten der Verwendung von Intune | Microsoft Intune
description:
keywords:
author: jeffgilb
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1f37d4ff-b5a7-4a89-8884-a6184908b09c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Gängige Arten der Verwendung von Intune

Bevor die Implementierungsaufgaben behandelt werden, ist es wichtig, die Enterprise Mobility-Beteiligten Ihres Unternehmens auf die Geschäftsziele auszurichten.  Dies ist unabhängig davon wichtig, ob Enterprise Mobility für Sie neu ist oder Sie von einem anderen Produkt migrieren.  Die Anforderungen in Bezug auf Enterprise Mobility entwickeln sich dynamisch und die Ansätze von Microsoft zur Behandlung dieser Anforderungen können sich manchmal von anderen Lösungen am Markt unterscheiden.  Die beste Methode zum Ausrichten von Geschäftszielen besteht darin, die Ziele in Bezug auf die Szenarien auszudrücken, die Sie für Mitarbeiter, Partner und die IT-Abteilung ermöglichen möchten.  Nachfolgend finden Sie kurze Einführung zu den sechs häufigsten, auf Intune beruhenden Szenarien sowie Links zu weiteren Informationen, wie diese jeweils geplant und bereitgestellt werden.

>[!NOTE] Möchten Sie wissen, wie Microsoft IT Intune verwendet, um Microsoft-Mitarbeitern den Zugriff auf Unternehmensressourcen auf ihren mobilen Geräten zu ermöglichen, während dabei auch die Unternehmensdaten geschützt bleiben? [Lesen Sie diese technische Fallstudie](https://www.microsoft.com/itshowcase/Article/Content/588), um ausführlich zu erfahren, wie Microsoft IT Intune und andere Dienste dazu verwendet, um Identitäten, Geräte, Apps und Daten zu verwalten.  

## Sichern Ihrer lokalen E-Mails und Daten für den sicheren Zugriff über mobile Geräte
Die meisten Enterprise Mobility-Strategien beginnen mit einem Plan, für Mitarbeiter mit mobilen Geräten den sicheren Zugriff auf E-Mails über das Internet zu ermöglichen. Viele Unternehmen verwenden weiterhin lokale Daten und Anwendungsserver wie Microsoft Exchange, die im Unternehmensnetzwerk gehostet werden. Intune und die Enterprise Mobility Suite (EMS) bieten eine eindeutig integrierte Lösung für Exchange Server für den bedingten Zugriff, die sicherstellt, dass keine mobilen Apps auf Ihre E-Mails zugreifen können, bis das Gerät mit Intune registriert wurde, ohne einen weiteren Gatewaycomputer am Rand des Unternehmensnetzwerks bereitstellen zu müssen.

Neben E-Mails unterstützt Intune auch das Ermöglichen des Zugriffs auf mobile Apps, die den sicheren Zugriff auf lokale Daten erfordern, z. B. ein branchenspezifischer Anwendungsserver.  Dies erfolgt in der Regel mithilfe von Zertifikaten für die Zugriffssteuerung, die von Intune verwaltet werden, in Kombination mit einem VPN-Standardgateway oder -proxy im Umkreis, z. B. Microsoft Azure AD-Anwendungsproxy.  In diesen Fällen besteht die einzige Möglichkeit für den Zugriff auf Unternehmensdaten in der Registrierung des Geräts für die Verwaltung.  Nach der Registrierung stellt das Verwaltungssystem sicher, dass auf Unternehmensdaten zugreifende Geräte Ihren Richtlinien entsprechen.  Darüber hinaus kann das App Wrapping Tool von Intune dazu verwendet werden, die Aufnahme der Daten, auf die zugegriffen wird, in der branchenspezifischen App zu unterstützen, damit sie keine Unternehmensdaten an Apps oder Dienste von Verbrauchern übergeben kann.

<!-- Learn more about how to plan and deploy Intune to help secure on-premises email and data. -->

## Sichern von Office 365-E-Mails und -Daten für den sicheren Zugriff über mobile Geräte
Das Schützen von Unternehmensdaten in Office 365 (E-Mails, Dokumente, Sofortnachrichten, Kontakte) könnte für Sie nicht einfacher oder für Ihre Benutzer nicht problemloser verlaufen. Intune und die Enterprise Mobility Suite bieten eine eindeutig integrierte Lösung für den bedingten Zugriff, die sicherstellt, dass keine Benutzer, Apps oder Geräte auf Office 365-Daten zugreifen können, sofern diese nicht den Compliance-Anforderungen Ihres Unternehmens entsprechen (Multi-Factor Authentification wurde ausgeführt, Registrierung mit Intune ist erfolgt und Folgendes wird verwendet: verwaltete App, unterstützte Betriebssystemversion, Geräte-PIN, Profil mit geringem Benutzerrisiko usw.). Die mobilen Office-Apps in ihren entsprechenden App-Stores sind bereit, den Richtlinien zur Datenaufnahme zu entsprechen, die Sie über Intune konfigurieren können. Dadurch haben Sie die Möglichkeit, die Datenfreigabe für Apps (z. B. eine systemeigene E-Mail-App) und Speicherorte (z. B. Dropbox) zu verhindern, die nicht von der IT-Abteilung verwaltet werden.  Diese Funktionalität ist in Office 365 und EMS vollständig integriert.  Sie müssen keine zusätzlichen Infrastruktur bereitstellen, um dies zu erreichen.

Eine häufige Office 365-Bereitstellungsmethode besteht darin, dass sich Geräte bei der Verwaltung registrieren müssen, wenn sie vollständig mit App-/Zertifikat-/WLAN-/VPN-Konfigurationen im Unternehmen bereitgestellt werden müssen, was bei firmeneigenen Geräten häufig der Fall ist.  Wenn der Benutzer jedoch einfach Zugriff auf die E-Mails und Dokumente im Unternehmen erfordert, was häufig bei Geräten der Fall ist, die sich im privaten Besitz befinden, muss der Benutzer die mobilen Office-Apps nutzen (auf die Sie Richtlinien zur Datenaufnahme angewendet haben) und die Registrierung des Geräts überspringen.  In beiden Fällen werden die Office 365-Daten durch Richtlinien geschützt, die von Ihnen definiert wurden.

<!-- Learn more about how to plan and deploy Intune to help secure Office 365 email and data. -->

## Anbieten eines BYOD-Programms (Bring Your Own Device) für alle Mitarbeiter
Die Beliebtheit von BYOD nimmt in Unternehmen als Mittel zum Reduzieren von Hardwareausgaben oder zum Erhöhen von mobilen Produktivitätsoptionen für Mitarbeiter weiter zu. Fast jeder verfügt heutzutage über ein eigenes Smartphone, warum also sollten die Mitarbeiter mit einem zusätzlichen Smartphone ausgestattet werden? Die wesentliche Herausforderung ist dabei immer gewesen, die Mitarbeiter davon zu überzeugen, ihr privates Gerät bei der Verwaltung zu registrieren, da sie unsicher sind, was die IT-Abteilung mit ihren Geräten anzeigen oder machen kann.  

Wenn die Registrierung des Geräts nicht realisierbar ist, bietet Intune einen alternativen BYOD-Ansatz, bei dem einfach nur die Apps verwaltet werden, die Unternehmensdaten enthalten.  Intune schützt die Unternehmensdaten, auch wenn die betreffende Anwendung sowohl auf Unternehmens- als auch auf private Daten zugreift, wie es bei mobilen Office-Apps der Fall ist.  Als Administrator können Sie festlegen, dass Benutzer über die mobilen Office-Apps auf Office 365 zugreifen müssen. Zudem können Sie die Apps mit Richtlinien konfigurieren, die dafür sorgen, dass die Daten geschützt bleiben (Verschlüsselung, durch PIN geschützt usw.).  Diese Richtlinien verhindern den Datenverlust durch nicht verwaltete Apps und Speicherorte – innerhalb oder außerhalb dieser Apps.  Die Richtlinien hindern z. B. einen Benutzer daran, Text aus einem E-Mail-Profil im Unternehmen in das E-Mail-Profil eines Verbrauchers zu kopieren, auch wenn beide Profile in Outlook Mobile konfiguriert sind.  Ähnliche Konfigurationen können für andere Dienste und Anwendungen bereitgestellt werden, die für Ihre BYOD-Benutzer erforderlich sind.

<!-- Learn more about how to plan and deploy Intune to support BYOD.-->

## Ausgeben firmeneigener Smartphones für Information-Worker
Die meisten Information-Worker sind heutzutage mobil, wodurch Produktivität auf mobilen Geräten unverzichtbar wird, um wettbewerbsfähig zu bleiben.  Diese Mitarbeiter benötigen jederzeit und überall den problemlosen Zugriff auf alle Apps und Daten im Unternehmen.  Sie müssen sicherstellen, dass die Unternehmensdaten sicher und die Verwaltungskosten gering sind.  

Intune bietet die Massenbereitstellung sowie Verwaltungslösungen, die in die wesentlichen Verwaltungsplattformen für Unternehmensgeräte integriert sind, die heute am Markt verfügbar sind, einschließlich dem Apple-Geräteregistrierungsprogramm und der mobilen KNOX-Sicherheitsplattform von Samsung.  Die zentrale Erstellung von Gerätekonfigurationen mit Intune macht die Bereitstellung von firmeneigenen Geräten zu einem Vorgang, der umfassend automatisiert werden kann.  

Stellen Sie sich Folgendes vor: Überreichen Sie einem Mitarbeiter ein ungeöffnetes iPhone-Produktpaket. Der Mitarbeiter schaltet das Gerät ein und wird durch ein Setup mit Firmenbranding geleitet, bei dem er sich selbst authentifizieren muss. Das iPhone wird problemlos mit Sicherheitsrichtlinien (Verschlüsselung der Festplatte, Geräte-PIN usw.), E-Mail-/WLAN-/VPN-/Zertifikatprofilen und einem Basissatz von Apps konfiguriert. Dann startet der Mitarbeiter die Windows Intune-Unternehmensportal-App für den Zugriff auf optionale Unternehmens-Apps, die zur Verfügung stehen.

<!-- Learn more about how to plan and deploy Intune to support corporate owned devices. -->

## Ausgeben gemeinsam genutzter Tablets mit eingeschränkter Verwendung an Ihre Taskworker
Taskworker nutzen zunehmend mobile Technologien.  Gemeinsam genutzte Tablets sind z. B. für Mitarbeiter im Einzelhandel jetzt üblich.  Ob Verkaufsvorgang oder unmittelbare Bestandsprüfung, Tablets helfen bei der Erzeugung hervorragender Kundeninteraktionen.  In diesem Fall ist die Einfachheit der Benutzererfahrung entscheidend.  Aus diesem Grund werden die Tablets in der Regel in einem Modus mit eingeschränkter Nutzung an Mitarbeiter übergeben, damit einzelne branchenspezifische Apps das Einzige ist, womit die Mitarbeiter interagieren können.  Mit Intune können Sie für diese Tablets, die für die Ausführung im Modus mit eingeschränkter Nutzung konfiguriert werden können, eine Massenbereitstellung durchführen, sie sichern und zentral verwalten.

<!-- Learn more about how to plan and deploy Intune to support shared tablets. -->

## Ermöglichen des sicheren Zugriffs für Mitarbeiter auf Office 365 von einem nicht verwalteten, öffentlichen Kiosk aus
Manchmal müssen Ihre Mitarbeiter Geräte, Apps oder Browser verwenden, die von Ihnen nicht verwaltet werden können, z. B. öffentliche Computer auf Messen und in Hotellobbys. Sollten Sie es den Mitarbeitern gestatten, dass sie über diese öffentlichen Computer auf E-Mails im Unternehmen zugreifen? Mit Intune und der Enterprise Mobility Suite <!--you have choices. The--> können Sie diese Frage einfach mit „nein“ beantworten, indem Sie den E-Mail-Zugriff auf Geräte beschränken, die von Ihrem Unternehmen verwaltet werden.  <!-- Alternatively, you can choose to allow limited access to these untrusted computers by requiring multi-factor authentication and only allowing browser access (Outlook Web Access) in a mode where files cannot be downloaded (e.g. email attachments).-->  Dadurch wird sichergestellt, dass der streng authentifizierte Mitarbeiter nicht versehentlich Unternehmensdaten auf nicht vertrauenswürdigen Computern hinterlässt.

<!-- Learn more about how to plan and deploy Intune to support kiosks. -->


<!--HONumber=May16_HO2-->


