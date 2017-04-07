---
title: Verwalten von PCs mit Clientsoftware | Microsoft-Dokumentation
description: Verwalten Sie Windows-PCs durch die Installation der Intune-Clientsoftware.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: c66226b7fc31f91669c4f4f0693ccbd7c679189f
ms.openlocfilehash: 74f2848dcd2863022dac44cf302b330a99cf1a55
ms.lasthandoff: 03/29/2017


---

# <a name="manage-windows-pcs-with-intune-pc-client-software"></a>Verwalten von Windows-PCs mit der Intune-PC-Clientsoftware
Die [Registrierung von Windows-PCs als mobile Geräte](set-up-windows-device-management-with-microsoft-intune.md) ist die bevorzugte Methode der Registrierung von Windows-PCs in Intune, aber Sie können als IT-Administrator alternativ auch Windows-PCs durch die Installation der Intune-Clientsoftware registrieren und verwalten, so wie in diesem Thema beschrieben. Der Softwareclient von Intune wird von der Registrierung als mobiles Gerät nicht unterstützt.

Intune verwaltet Windows-PCs mithilfe von Richtlinien ähnlich wie die Gruppenrichtlinienobjekte (Group Policy Objects, GPOs) der Windows Server Active Directory Domain Services (AD DS). Wenn Sie Computer in einer Active Directory-Domäne mit Intune verwalten, [stellen Sie sicher, dass Intune-Richtlinien nicht zu Konflikten mit GPOs führen](resolve-gpo-and-microsoft-intune-policy-conflicts.md), die für Ihre Organisation eingerichtet sind. Weitere Informationen hierzu finden Sie unter [Gruppenrichtlinienobjekte (GPOs)](https://technet.microsoft.com/library/hh147307.aspx).

## <a name="policies-and-app-deployments-for-the-intune-software-client"></a>Richtlinien und App-Bereitstellungen für den Intune-Softwareclient

Die Intune-Clientsoftware verwaltet Softwareupdates, Windows-Firewall und Endpoint Protection und unterstützt auf diese Weise [Verwaltungsfunktionen zum Schutz von PCs](policies-to-protect-windows-pcs-in-microsoft-intune.md). Allerdings können auf PCs, die mit der Intune-Clientsoftware verwaltet werden, keine anderen Intune-Richtlinien angewendet werden. Dies gilt auch für **Windows**-Richtlinieneinstellungen speziell für die Verwaltung mobiler Geräte.

Wenn Sie die Intune-Clientsoftware zum Verwalten von Windows-PCs verwenden, können Sie nur die Richtlinien im Abschnitt **Computerverwaltung** verwenden.

  ![Auswählen der Vorlage für neue Windows-PC-Richtlinien](../media/select-template-for-pc-policy.png)

Eine ausführliche Beschreibung der Richtlinien, die Sie festlegen können, finden Sie unter:

- [Verwenden von Richtlinien zum Schutz von Windows-PCs, auf denen die Intune-Clientsoftware ausgeführt wird](https://docs.microsoft.com/intune/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)
- [Aktualisieren Ihrer Windows-PCs mit Softwareupdates in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)
- [Unterstützen des Schutzes von Windows-PCs mithilfe von Windows-Firewall-Richtlinien in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)
- [Schützen von Windows-PCs mit Endpoint Protection für Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

Wenn Sie Apps bereitstellen, können Sie außerdem nur Windows Installer (EXE, MSI) verwenden.

  ![Auswählen von Plattform und Speicherort für PC-Clientsoftwaredateien](../media/select-platform-of-software-files-for-pc-agent.png)

> [!NOTE]
> Sie können Geräte mit Windows 8.1 oder höher entweder als PCs mithilfe der Intune-Clientsoftware oder als mobile Geräte mithilfe der Funktionalität zur Verwaltung mobiler Geräte (MDM) verwalten. Sie können nicht beide Methoden zusammen verwenden, daher müssen Sie Ihre Entscheidung sorgfältig überdenken, bevor Sie PCs mit der Intune-Clientsoftware verwalten. Dieses Thema gilt nur für das Verwalten von Geräten als PCs mithilfe der Intune-Clientsoftware.

## <a name="requirements-for-intune-pc-client-management"></a>Anforderungen für die Intune-PC-Clientverwaltung

**Hardware**: Im Folgenden sind die Hardwaremindestanforderungen zum Installieren der Intune-Clientsoftware aufgeführt:

|Anforderungen|Weitere Informationen|
|---------------|--------------------|
|Netzwerk|Für den Client ist ein PC mit Internetzugriff erforderlich.|
|Prozessor und Arbeitsspeicher|Weitere Informationen entnehmen Sie den Prozessor- und Arbeitsspeicheranforderungen des PC-Betriebssystems.|
|Speicherplatz|200 MB verfügbarer Speicherplatz vor der Installation der Clientsoftware|

**Software**: Im Folgenden sind die Softwareanforderungen zum Installieren der Clientsoftware aufgeführt:

|Anforderungen|Weitere Informationen|
|---------------|--------------------|
|Betriebssystem | Windows-Gerät, auf dem Windows Vista oder höher ausgeführt wird. </br></br>**Versionen der Home Edition werden nicht unterstützt.**|
|Administratorrechte|Das Konto, mit dem die Clientsoftware installiert wird, muss über lokale Administratorrechte auf diesem Gerät verfügen.|
|Windows Installer 3.1|Auf dem PC wird Windows Installer 3.1 oder höher benötigt.<br /><br />So zeigen Sie die Windows Installer-Version auf einem PC an:<br /><br />  Klicken Sie auf dem PC mit der rechten Maustaste auf **%windir%\System32\msiexec.exe**, und klicken Sie dann auf **Eigenschaften**.<br /><br />Sie können die neueste Version von Windows Installer von der Microsoft Developer Network-Website unter [Windows Installer Redistributables (Weitervertreibbare Komponenten für Windows Installer)](http://go.microsoft.com/fwlink/?LinkID=234258) herunterladen.|
|Entfernen nicht kompatibler Clientsoftware|Bevor Sie die Intune-Clientsoftware installieren, deinstallieren Sie sämtliche Clientsoftware für Configuration Manager, Operations Manager, Operations Management Suite und Service Manager auf diesem PC.|

## <a name="computer-management-capabilities-with-the-intune-client-software"></a>Computerverwaltungsfunktionen mit der Intune-Clientsoftware

Nach der Installation der Clientsoftware sind u.a. die folgenden Verwaltungsfunktionen möglich:

- [Anwendungsverwaltung](deploy-apps-in-microsoft-intune.md)

- [Überwachung in Echtzeit und Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md): Endpoint Protection ist dasselbe wie Windows Defender. Endpoint Protection betrifft Windows 7 und Windows 8. Ab Windows 10 und höher wurde der Name des Produkts in Windows Defender geändert.

- [Verwaltung von Windows-Firewall-Einstellungen](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md), Hardware- und Softwareinventur, Remotesteuerung (über Remoteunterstützungsanforderungen)

- [Softwareupdateeinstellungen](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)

- Erstellen von Berichten zu Kompatibilitätseinstellungen

In der Intune-Administratorkonsole werden bestimmte Abschnitte, z.B. „Updates“, „Schutz“ und „Lizenzen“ nur angezeigt, wenn Sie Geräte mit der Intune-Clientsoftware registriert haben.

  ![Elemente der Verwaltungskonsole, die nur für den PC-Client angezeigt werden](../media/admin-console-settings-only-for-pc-agent.png)

Sie können die Intune-Administratorkonsole auch verwenden, um andere allgemeine Verwaltungsaufgaben auf Windows-PCs auszuführen, auf denen der Client installiert ist:

-   Anzeigen von Informationen zum Hardware- und Softwarebestand auf verwalteten Computern
-   Remoteneustart eines Computers
-   Abkoppeln eines Computers zum Deinstallieren der Clientsoftware und Entfernen aus der Intune-Verwaltung
-   Verknüpfen von Benutzern mit bestimmten verwalteten Computern
-   Reagieren auf Remoteunterstützungsanforderungen

Weitere Informationen zu den oben genannten Aufgaben finden Sie unter [allgemeine Verwaltungsaufgaben](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).

## <a name="management-limitations-of-the-intune-client-software"></a>Verwaltungseinschränkungen der Intune-Clientsoftware

Einige Verwaltungsoptionen, die zum Verwalten von PCs als mobile Geräte verwendet werden können, sind nicht für PCs geeignet, die mit der Intune-Clientsoftware verwaltet werden:

-   Vollständiges Zurücksetzen (selektives Zurücksetzen ist verfügbar)

-   Bedingter Zugriff

## <a name="help-with-troubleshooting"></a>Hilfe bei der Problembehandlung

Die Intune-Clientsoftware wird in der Regel im Hintergrund ausgeführt, ohne dass viele Benutzerinteraktionen oder Maßnahmen zur Fehlerbehebung erforderlich sind. Wenn Sie Probleme mit der Computerverwaltung beheben müssen, können Sie die Protokolle überprüfen. Die Intune-Clientsoftware und zugehörige Protokolle sind im Verzeichnis „%Program Files%\Microsoft\OnlineManagement“ installiert.

Unter [Behandlung von Problemen bei der Clienteinrichtung in Microsoft Intune](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune) finden Sie auch Hinweise zu möglichen Problemen und etwaige Lösungen oder Problemumgehungen.

