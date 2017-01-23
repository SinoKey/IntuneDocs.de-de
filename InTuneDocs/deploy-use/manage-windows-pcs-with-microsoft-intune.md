---
title: Verwalten von PCs mit Clientsoftware | Microsoft-Dokumentation
description: Verwalten Sie Windows-PCs durch die Installation der Intune-Clientsoftware.
keywords: 
author: staciebarker
ms.author: stabar
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
ms.sourcegitcommit: 3d2f3a7233ea7a5127baf5a08be1ccb41f717244
ms.openlocfilehash: 4344251ede6d8cc338d84782d224d87fd78d5bd8


---

# <a name="manage-windows-pcs-with-intune-pc-client-software"></a>Verwalten von Windows-PCs mit der Intune-PC-Clientsoftware
Anstatt [Windows-PCs als mobile Geräte zu registrieren](set-up-windows-device-management-with-microsoft-intune.md), können Sie Windows-PCs auch registrieren und verwalten, indem Sie die Intune-Clientsoftware installieren.

Intune verwaltet Windows-PCs mithilfe von Richtlinien ähnlich wie die Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) der Windows Server Active Directory Domain Services (AD DS). Wenn Sie Computer in einer Active Directory-Domäne mit Intune verwalten, [stellen Sie sicher, dass Intune-Richtlinien nicht zu Konflikten mit GPOs führen](resolve-gpo-and-microsoft-intune-policy-conflicts.md), die für Ihre Organisation eingerichtet sind.

Der Intune-Softwareclient verwaltet Softwareupdates, Windows-Firewall und Endpoint Protection und unterstützt auf diese Weise [Verwaltungsfunktionen zum Schutz von PCs](policies-to-protect-windows-pcs-in-microsoft-intune.md). Allerdings können auf PCs, die mit dem Intune-Softwareclient verwaltet werden, keine anderen Intune-Richtlinien angewendet werden. Dies gilt auch für **Windows**-Richtlinieneinstellungen speziell für die Verwaltung mobiler Geräte.

> [!NOTE]
> Sie können Geräte mit Windows 8.1 oder höher entweder als PCs mithilfe des Intune-Clients oder als mobile Geräte mithilfe der Funktionalität zur Verwaltung mobiler Geräte (Mobile Device Management, MDM) verwalten. Sie können nicht beide Methoden zusammen verwenden. Dieses Thema gilt nur für das Verwalten von Geräten als PCs mithilfe des Intune-Softwareclients.

## <a name="requirements-for-intune-pc-client-management"></a>Anforderungen für die Intune-PC-Clientverwaltung

**Hardware**: Im Folgenden sind die Hardwaremindestanforderungen zum Installieren des Intune-Clients aufgeführt:

|Anforderungen|Weitere Informationen|
|---------------|--------------------|
|Netzwerk|Für den Client ist ein PC mit Internetzugriff erforderlich.|
|Prozessor und Arbeitsspeicher|Weitere Informationen entnehmen Sie den Prozessor- und Arbeitsspeicheranforderungen des PC-Betriebssystems.|
|Speicherplatz|200 MB verfügbarer Speicherplatz vor der Installation der Clientsoftware|

**Software**: Im Folgenden sind die Softwareanforderungen zum Installieren des Clients aufgeführt:

|Anforderungen|Weitere Informationen|
|---------------|--------------------|
|Betriebssystem | Windows-Gerät, auf dem Windows Vista oder höher ausgeführt wird. Versionen der Home-Edition werden nicht unterstützt.|
|Administratorrechte|Das Konto, mit dem die Clientsoftware installiert wird, muss über lokale Administratorrechte auf diesem Gerät verfügen.|
|Windows Installer 3.1|Auf dem PC wird Windows Installer 3.1 oder höher benötigt.<br /><br />So zeigen Sie die Windows Installer-Version auf einem PC an:<br /><br />  Klicken Sie auf dem PC mit der rechten Maustaste auf **%windir%\System32\msiexec.exe**, und klicken Sie dann auf **Eigenschaften**.<br /><br />Sie können die neueste Version von Windows Installer von der Microsoft Developer Network-Website unter [Windows Installer Redistributables (Weitervertreibbare Komponenten für Windows Installer)](http://go.microsoft.com/fwlink/?LinkID=234258) herunterladen.|
|Entfernen nicht kompatibler Clientsoftware|Bevor Sie die Intune-Clientsoftware installieren, deinstallieren Sie sämtliche Clientsoftware für Configuration Manager, Operations Manager, Operations Management Suite und Service Manager auf diesem PC.|

## <a name="computer-management-with-the-intune-computer-client"></a>Computerverwaltung mit dem Intune-Computerclient
Nach der Installation der Clientsoftware sind u.a. die folgenden Verwaltungsfunktionen möglich: 

- [Anwendungsverwaltung](deploy-apps-in-microsoft-intune.md)

- [Überwachung in Echtzeit und Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)

- [Verwaltung von Windows-Firewall-Einstellungen](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md), Hardware- und Softwareinventur, Remotesteuerung (über Remoteunterstützungsanforderungen)

- [Softwareupdateeinstellungen](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)

- Erstellen von Berichten zu Kompatibilitätseinstellungen

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



<!--HONumber=Dec16_HO3-->


