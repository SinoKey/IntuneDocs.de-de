---
# required metadata

title: Verwalten von Windows-PCs mit Intune | Microsoft Intune
description:
keywords:
author: nathbarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Verwalten von Windows-PCs mit Microsoft Intune
Zusätzlich zur Registrierung von Geräten können Sie Intune auch zur Verwaltung von Windows-PCs mit unterstützten Betriebssystemen verwenden, indem Sie die Intune-Computerclientsoftware einsetzen. Die Hardware- und Softwarevoraussetzungen zur Ausführung des Computerclients sind minimal. Im Grunde wird jedes System unterstützt, auf dem Windows 7 oder eine höhere Version ausgeführt werden kann.  Die Clientsoftware lässt sich auch problemlos auf Computern innerhalb einer (beliebigen) oder außerhalb einer Domäne installieren.

Intune verwalten Windows-PCs mithilfe von Richtlinien, ähnlich wie die Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) der Windows Server Active Directory-Domänendienste (Active Directory Domain Services, AD DS). Wenn Sie Computer in einer Active Directory-Domäne mit Intune verwalten, [müssen Sie sicherstellen, dass Intune-Richtlinien nicht zu Konflikten mit GPOs führen](resolve-gpo-and-microsoft-intune-policy-conflicts.md), die für Ihre Organisation eingerichtet sind.

> [!NOTE]
> Microsoft Intune bietet als eigenständiger Dienst die folgenden Features zum Verwalten von Computern. Geräte, auf denen Windows 8.1 ausgeführt wird, können unter Verwendung des Intune-Clients verwaltet oder als mobile Geräte registriert werden. Die folgenden Informationen gelten für Computer, auf denen der Intune-Client ausgeführt wird.

## Anforderungen für die PC-Verwaltung durch Intune

**Hardware**:
Im Folgenden sind die Hardwaremindestanforderungen zum Installieren des Intune-Clients aufgeführt:

|Anforderungen|Weitere Informationen|
|---------------|--------------------|
|Netzwerk|Für den Client ist ein PC mit Internetzugriff erforderlich.|
|Prozessor und Arbeitsspeicher|Weitere Informationen entnehmen Sie den Prozessor- und Arbeitsspeicheranforderungen des PC-Betriebssystems.|
|Speicherplatz|200 MB verfügbarer Speicherplatz vor der Installation der Clientsoftware|

**Software**:
Im Folgenden sind die Softwareanforderungen zum Installieren des Clients aufgeführt:

|Anforderungen|Weitere Informationen|
|---------------|--------------------|
|Administratorrechte|Das Konto, mit dem die Clientsoftware installiert wird, muss über lokale Administratorrechte auf dem PC verfügen.|
|Windows Installer 3.1|Auf dem PC wird Windows Installer 3.1 oder höher benötigt.<br /><br />So zeigen Sie die Windows Installer-Version auf einem PC an:<br /><br />– Klicken Sie auf dem PC mit der rechten Maustaste auf **%windir%\System32\msiexec.exe**, und klicken Sie dann auf **Eigenschaften**..<br /><br />Sie können die neueste Version von Windows Installer von der Microsoft Developer Network-Website unter [Windows Installer Redistributables (Weitervertreibbare Komponenten für Windows Installer)](http://go.microsoft.com/fwlink/?LinkID=234258) herunterladen.|
|Entfernen nicht kompatibler Clientsoftware|Bevor Sie die Intune-Clientsoftware installieren, müssen Sie alle auf dem PC vorhandene Configuration Manager- oder Systems Management Server-Clientsoftware deinstallieren.|

## Installieren des Intune-Computerclients
Der erste Schritt bei der Verwaltung von Windows-PCs mit Intune besteht darin, den Client zu installieren. Die Clientsoftware kann installiert werden, wenn ein PC durch den Intune-Dienst mit einer der folgenden Methoden für die Verwaltung registriert wurde:

-   Sie können [die Microsoft Intune-Clientsoftware manuell bereitstellen](install-the-windows-pc-client-with-microsoft-intune.md#to-manually-deploy-the-client-software). Bei dieser Art der Bereitstellung lädt ein Administrator die Intune-Clientsoftware herunter und installiert sie manuell auf jedem PC.

    Für den Download der Intune-Clientsoftware öffnen Sie die Intune-Verwaltungskonsole und laden im Bereich "Clientsoftwaredownload" das Clientsoftwarepaket herunter. Nach der Installation der Clientsoftware installiert Intune automatisch zusätzliche Software, die ggf. zur Verwaltung des Computers erforderlich ist.

-   Sie können die gleichen Dateien, die Sie für die manuelle Installation des Intune-Clients herunterladen, auch zur [Bereitstellung des Clients auf Computern in einer Domäne mithilfe von Active Directory-GPOs verwenden](install-the-windows-pc-client-with-microsoft-intune.md#to-automatically-deploy-the-client-software-by-using-group-policy)..

-   [Endbenutzer können all ihre Computer über das Intune-Unternehmensportal selbst registrieren](install-the-windows-pc-client-with-microsoft-intune.md#how-users-can-self-enroll-their-computers). Jeder registrierte Computer wird automatisch mit dem Benutzerkonto verknüpft, das zum Installieren der Intune-Clientsoftware verwendet wurde.

-   Sie können die Intune-Clientsoftware auch im Rahmen einer [Betriebssystembereitstellung](install-the-windows-pc-client-with-microsoft-intune.md#install-the-microsoft-intune-client-software-as-part-of-an-image) auf Computern bereitstellen..

## Computerverwaltung mit dem Intune-Computerclient
Nach der Installation des Intune-Clients stellt die Clientsoftware verschiedene Funktionen für die Computerverwaltung bereit, einschließlich der folgenden: [Anwendungsverwaltung](deploy-apps-in-microsoft-intune.md), Endpoint Protection, Hardware- und Softwareinventar, Softwareupdates sowie Berichterstellung zu Kompatibilitätseinstellungen.

Verschiedene vom Computerclient bereitgestellte Aufgaben der Computerverwaltung werden mithilfe von Intune-Richtlinien wie z. B. den folgenden verwaltet:

-   Konfigurieren von [Windows Firewall-Einstellungen](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) auf verwalteten Computern.

-   Konfigurieren von [Softwareupdateeinstellungen](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) für verwaltete Computer zum Suchen und Herunterladen von erforderlichen Softwareupdates.

-   Schützen der verwalteten Computer vor potenziellen Bedrohungen und Schadsoftwareprogrammen durch [Echtzeitüberwachung und Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).

Zusätzlich zu den Aktionen, die der Intune-Client-Agent lokal auf einzelnen Computern ausführt, können Sie die Intune-Verwaltungskonsole auch für andere [allgemeine Computerverwaltungsaufgaben](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) auf Windows-PCs verwenden, auf denen der Client installiert ist:

-   Anzeigen von Informationen zum Hardware- und Softwarebestand auf verwalteten Computern

-   Remoteneustart eines Computers

-   Abkoppeln eines Computers zum Deinstallieren der Clientsoftware und Entfernen aus der Intune-Verwaltung

-   Verknüpfen von Benutzern mit bestimmten verwalteten Computern

-   Reagieren auf Remoteunterstützungsanforderungen

Der Intune-Client-Agent wird in der Regel im Hintergrund ausgeführt – Benutzerinteraktionen oder Maßnahmen zur Fehlerbehebung sind nur selten erforderlich. Sollten Sie jedoch Hilfe bei der Behebung von Problemen mit der Computerverwaltung benötigen, stehen verschiedene [Ressourcen zur Lösung zur Verfügung](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune)..


<!--HONumber=May16_HO1-->


