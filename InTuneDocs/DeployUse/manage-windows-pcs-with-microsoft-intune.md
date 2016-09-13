---
title: Verwalten von PCs mit Clientsoftware | Microsoft Intune
description: Verwalten Sie Windows-PCs durch die Installation der Intune-Clientsoftware.
keywords: 
author: nathbarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: cf471320f122eea7804ff6cd6cad208f8cd5a692
ms.openlocfilehash: f264dc3740ce9b117fcc01c39792904a2dc6e7ab


---

# Verwalten von Windows-PCs mit der Intune-PC-Clientsoftware
Anstatt [Windows-PCs als mobile Geräte zu registrieren](set-up-windows-device-management-with-microsoft-intune.md), können Sie Windows-PCs auch registrieren und verwalten, indem Sie die Intune-Clientsoftware installieren.

Intune verwalten Windows-PCs mithilfe von Richtlinien, ähnlich wie die Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) der Windows Server Active Directory-Domänendienste (Active Directory Domain Services, AD DS). Wenn Sie Computer in einer Active Directory-Domäne mit Intune verwalten, [müssen Sie sicherstellen, dass Intune-Richtlinien nicht zu Konflikten mit GPOs führen](resolve-gpo-and-microsoft-intune-policy-conflicts.md), die für Ihre Organisation eingerichtet sind.

Der Intune-Softwareclient verwaltet Softwareupdates, Windows-Firewall und Endpoint Protection und unterstützt auf diese Weise [Verwaltungsfunktionen zum Schutz von PCs](policies-to-protect-windows-pcs-in-microsoft-intune.md). Allerdings können auf PCs, die mit dem Intune-Client verwaltet werden, keine anderen Intune-Richtlinien angewendet werden. Dies gilt auch für **Windows**-Richtlinieneinstellungen speziell für die Verwaltung mobiler Geräte.

> [!NOTE]
> Geräte, auf denen Windows 8.1 oder höher ausgeführt wird, können unter Verwendung des Intune-Clients verwaltet oder als mobile Geräte registriert werden. Die folgenden Informationen gelten für Computer, auf denen der Intune-Client ausgeführt wird. Die Installation des Intune-PC-Clients und die gleichzeitige Registrierung des Windows-Geräts für die Verwaltung mobiler Geräte werden nicht unterstützt.

## Anforderungen für die Intune-PC-Clientverwaltung

**Hardware**: Im Folgenden sind die Hardwaremindestanforderungen zum Installieren des Intune-Clients aufgeführt:

|Anforderungen|Weitere Informationen|
|---------------|--------------------|
|Netzwerk|Für den Client ist ein PC mit Internetzugriff erforderlich.|
|Prozessor und Arbeitsspeicher|Weitere Informationen entnehmen Sie den Prozessor- und Arbeitsspeicheranforderungen des PC-Betriebssystems.|
|Speicherplatz|200 MB verfügbarer Speicherplatz vor der Installation der Clientsoftware|

**Software**: Im Folgenden sind die Softwareanforderungen zum Installieren des Clients aufgeführt:

|Anforderungen|Weitere Informationen|
|---------------|--------------------|
|Betriebssystem | Auf dem Windows-Gerät muss Windows 7 oder höher ausgeführt werden. |
|Administratorrechte|Das Konto, mit dem die Clientsoftware installiert wird, muss über lokale Administratorrechte auf diesem Gerät verfügen.|
|Windows Installer 3.1|Auf dem PC wird Windows Installer 3.1 oder höher benötigt.<br /><br />So zeigen Sie die Windows Installer-Version auf einem PC an:<br /><br />– Klicken Sie auf dem PC mit der rechten Maustaste auf **%windir%\System32\msiexec.exe**, und klicken Sie dann auf **Eigenschaften**.<br /><br />Sie können die neueste Version von Windows Installer von der Microsoft Developer Network-Website unter [Windows Installer Redistributables (Weitervertreibbare Komponenten für Windows Installer)](http://go.microsoft.com/fwlink/?LinkID=234258) herunterladen.|
|Entfernen nicht kompatibler Clientsoftware|Bevor Sie die Intune-Clientsoftware installieren, müssen Sie alle auf dem PC vorhandene Configuration Manager- oder Systems Management Server-Clientsoftware deinstallieren.|

## Installieren des Intune-Computerclients
Die Intune-Clientsoftware kann mithilfe einer der folgenden Methoden installiert werden:

-  [Stellen Sie die Microsoft Intune-Clientsoftware manuell bereit](install-the-windows-pc-client-with-microsoft-intune.md#to-manually-deploy-the-client-software). Bei dieser Art der Bereitstellung lädt ein Administrator die Intune-Clientsoftware herunter und installiert sie manuell auf jedem PC.

  Um die Intune-Clientsoftware herunterzuladen, öffnen Sie die [Intune-Verwaltungskonsole](https://manage.microsoft.com), wählen Sie **Verwaltung** > **Download der Clientsoftware** aus, und klicken Sie auf **Clientsoftware herunterladen**.

-  Verwenden Sie die gleichen Dateien, die Sie für die manuelle Installation des Intune-Clients herunterladen, auch zur [Bereitstellung des Clients auf Computern in einer Domäne mithilfe von Active Directory-GPOs](install-the-windows-pc-client-with-microsoft-intune.md#to-automatically-deploy-the-client-software-by-using-group-policy).

-  Stellen Sie die Intune-Clientsoftware im Rahmen der [Bereitstellung des Betriebssystems](install-the-windows-pc-client-with-microsoft-intune.md#install-the-microsoft-intune-client-software-as-part-of-an-image) auf Computern bereit.

-  Senden Sie Benutzeranweisungen über die URL für das Intune-Unternehmensportal, [https://portal.manage.microsoft.com](http://go.microsoft.com/fwlink/?LinkId=825632). Wenn die Benutzer das Unternehmensportal öffnen, werden sie zum Registrieren ihres PCs aufgefordert, indem sie die Intune-Clientsoftware herunterladen und ausführen.

## Computerverwaltung mit dem Intune-Computerclient
Nach der Installation der Intune-Clientsoftware stellt die Clientsoftware verschiedene Funktionen für die Computerverwaltung bereit, einschließlich der folgenden: [Anwendungsverwaltung](deploy-apps-in-microsoft-intune.md), Endpoint Protection, Hardware- und Softwareinventar, Softwareupdates sowie Berichterstellung zu Kompatibilitätseinstellungen.

Verschiedene vom Computerclient bereitgestellte Aufgaben der Computerverwaltung werden mithilfe von Intune-Richtlinien wie z. B. den folgenden verwaltet:

-   Konfigurieren von [Windows Firewall-Einstellungen](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) auf verwalteten Computern.

-   Konfigurieren von [Softwareupdateeinstellungen](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) für verwaltete Computer zum Suchen und Herunterladen von erforderlichen Softwareupdates.

-   Schützen der verwalteten Computer vor potenziellen Bedrohungen und Schadsoftwareprogrammen durch [Echtzeitüberwachung und Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).

![Richtlinienvorlage für Windows-PCs](../media/pc_policy_template.png)

Zusätzlich zu den Aktionen, die der Intune-Client-Agent lokal auf einzelnen Computern ausführt, können Sie die Intune-Verwaltungskonsole auch für andere [allgemeine Computerverwaltungsaufgaben](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) auf Windows-PCs verwenden, auf denen der Client installiert ist:

-   Anzeigen von Informationen zum Hardware- und Softwarebestand auf verwalteten Computern

-   Remoteneustart eines Computers

-   Abkoppeln eines Computers zum Deinstallieren der Clientsoftware und Entfernen aus der Intune-Verwaltung

-   Verknüpfen von Benutzern mit bestimmten verwalteten Computern

-   Reagieren auf Remoteunterstützungsanforderungen

Der Intune-Client-Agent wird in der Regel im Hintergrund ausgeführt – Benutzerinteraktionen oder Maßnahmen zur Fehlerbehebung sind nur selten erforderlich. Sollten Sie jedoch Hilfe beim Lösen von Problemen mit der Computerverwaltung benötigen, stehen verschiedene [Ressourcen zur Lösung zur Verfügung](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune).



<!--HONumber=Aug16_HO4-->


