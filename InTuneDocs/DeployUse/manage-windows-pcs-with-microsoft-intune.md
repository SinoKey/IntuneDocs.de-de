---
title: Verwalten von PCs mit Clientsoftware | Microsoft Intune
description: Verwalten Sie Windows-PCs durch die Installation der Intune-Clientsoftware.
keywords: 
author: nathbarn
manager: angrobe
ms.date: 08/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 16be49504b24269f9463905ab5767acbda136a0a
ms.openlocfilehash: a13c03cde29c46a78577b58f85daad30a076bf89


---

# Verwalten von Windows-PCs mit der Intune-PC-Clientsoftware
Anstatt [Windows-PCs als mobile Geräte zu registrieren](set-up-windows-device-management-with-microsoft-intune.md), können Sie Windows-PCs auch registrieren und verwalten, indem Sie die Intune-Clientsoftware installieren.

Intune verwalten Windows-PCs mithilfe von Richtlinien, ähnlich wie die Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) der Windows Server Active Directory-Domänendienste (Active Directory Domain Services, AD DS). Wenn Sie Computer in einer Active Directory-Domäne mit Intune verwalten, [müssen Sie sicherstellen, dass Intune-Richtlinien nicht zu Konflikten mit GPOs führen](resolve-gpo-and-microsoft-intune-policy-conflicts.md), die für Ihre Organisation eingerichtet sind.

Der Intune-Softwareclient verwaltet Softwareupdates, Windows-Firewall und Endpoint Protection und unterstützt auf diese Weise [Verwaltungsfunktionen zum Schutz von PCs](policies-to-protect-windows-pcs-in-microsoft-intune.md). Allerdings können auf PCs, die mit dem Intune-Softwareclient verwaltet werden, keine anderen Intune-Richtlinien angewendet werden. Dies gilt auch für **Windows**-Richtlinieneinstellungen speziell für die Verwaltung mobiler Geräte.

> [!NOTE]
> Geräte unter Windows 8.1 oder höher können mit dem Intune-Client oder als mobile Geräte verwaltet werden. Dieses Thema bezieht sich auf Computer, auf denen der Intune-Softwareclient ausgeführt wird. Die Installation des Intune-Clients und die Registrierung für die Verwaltung mobiler Geräte werden nicht unterstützt.

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

## Computerverwaltung mit dem Intune-Computerclient
Nach der Installation der Intune-Clientsoftware enthalten die Verwaltungsfunktionen u.a. die folgenden: [Anwendungsverwaltung](deploy-apps-in-microsoft-intune.md), [Echtzeitüberwachung und Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md), [Verwaltung der Windows-Firewalleinstellungen](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md), Hardware- und Softwareinventar, Remotesteuerung (über Anforderungen von Remoteunterstützung), [Softwareupdateeinstellungen](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) sowie Berichterstellung zu Kompatibilitätseinstellungen.

Bestimmte Verwaltungsoptionen für PCs, die als mobile Geräte verwaltet werden, stehen nicht für über den Softwareclient verwaltete PCs zur Verfügung, wie z.B.:

-   Vollständiges Zurücksetzen (selektives Zurücksetzen ist verfügbar)
-   Bedingter Zugriff
-   Windows-Richtlinien außer **Computerverwaltungsrichtlinien**

![Richtlinienvorlage für Windows-PCs](../media/pc_policy_template.png)

Zusätzlich zu den Aktionen, die der Intune-Client-Agent lokal auf einzelnen Computern ausführt, können Sie die Intune-Verwaltungskonsole auch für andere [allgemeine Computerverwaltungsaufgaben](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) auf Windows-PCs verwenden, auf denen der Client installiert ist:

-   Anzeigen von Informationen zum Hardware- und Softwarebestand auf verwalteten Computern

-   Remoteneustart eines Computers

-   Abkoppeln eines Computers zum Deinstallieren der Clientsoftware und Entfernen aus der Intune-Verwaltung

-   Verknüpfen von Benutzern mit bestimmten verwalteten Computern

-   Reagieren auf Remoteunterstützungsanforderungen

Der Intune-Client-Agent wird in der Regel im Hintergrund ausgeführt – Benutzerinteraktionen oder Maßnahmen zur Fehlerbehebung sind nur selten erforderlich. Sollten Sie jedoch Hilfe beim Lösen von Problemen mit der Computerverwaltung benötigen, stehen verschiedene [Ressourcen zur Lösung zur Verfügung](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune).



<!--HONumber=Sep16_HO1-->


