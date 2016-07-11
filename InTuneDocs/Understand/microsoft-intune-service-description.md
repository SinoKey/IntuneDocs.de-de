---
title: Dienstbeschreibung | Microsoft Intune
description: 
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 40fa5a2e-6c0f-4150-9740-d5ddc0cdbda0
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4794a22b3bdd1f28e6951b81e8379dc208fffc89
ms.openlocfilehash: 6cab0bacd9157323e342662609de8c9f20550d78


---

# Microsoft Intune-Dienstbeschreibung

Microsoft Intune ist ein cloudbasierter Dienst, der Ihnen bei der Verwaltung von Windows-PCs sowie mobilen iOS-, Mac OS X-, Android- und Windows-Geräten hilft. Intune hilft Ihnen außerdem dabei, Unternehmensanwendungen und -daten zu schützen. Sie können Intune eigenständig verwenden oder in System Center 2012 R2 Configuration Manager integrieren, um Ihre Verwaltungsfunktionen zu erweitern.

Microsoft bietet den Vorteil des Intune Onboardings für zulässige Dienste in zulässigen Plänen. Das Onboarding ermöglichen Ihnen die Remotezusammenarbeit mit Microsoft-Spezialisten, um Ihre Intune-Umgebung einzurichten. Weitere Informationen finden Sie in der [Beschreibung der Vorteile des Microsoft Intune-Onboardings](http://go.microsoft.com/fwlink/?LinkId=619281).

Sie können Intune zunächst mit einer 30-tägigen kostenlosen Testversion verwenden, die 100 Benutzerlizenzen enthält. Um Ihre kostenlose Testversion zu starten, [klicken Sie hier, um die Anmeldeseite von Intune aufzurufen](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/). Wenn Ihre Organisation über ein Enterprise Agreement oder einen vergleichbaren Volumenlizenzvertrag verfügt, wenden Sie sich an Ihren Microsoft-Mitarbeiter, um Ihre kostenlose Testversion einzurichten.

> [!NOTE]
> Wenn Ihre Organisation bereits über ein Geschäfts- oder Schulkonto für Microsoft Online Services verfügt und Sie dieses Intune-Abonnement nach Ende der Testphase möglicherweise in die Produktionsumgebung übernehmen möchten, ist es wichtig, dass Sie auf der Seite auf die Option **Anmelden** klicken und sich unter Verwendung des globalen Administratorkontos Ihrer Organisation authentifizieren. Dadurch wird sichergestellt, dass Ihre Intune-Testversion mit Ihrem bestehenden Geschäfts- oder Schulkonto verknüpft wird.

Eine Liste der Einstellungen für mobile Geräte finden Sie unter:

-   [Verwaltungsfunktionen für mobile Geräte in Microsoft Intune](/intune/get-started/mobile-device-management-capabilities-in-microsoft-intune)

-   [Allgemeine Einstellungen für mobile Geräte im Konfigurations-Manager](https://technet.microsoft.com/en-us/library/dn376523.aspx)

Informationen zum System Center 2012 R2 Configuration Manager finden Sie in der [Dokumentationsbibliothek zu System Center 2012 Configuration Manager](https://technet.microsoft.com/library/gg682041.aspx).

## Auswirkungen von Intune-Dienstupdates auf Sie
Da Intune ein Onlinedienst ist, kann Microsoft ihn in regelmäßigen Abständen aktualisieren.

Verwenden Sie die Informationen in diesem Thema, um die Häufigkeit dieser Dienstupdates besser zu verstehen und die Vorabbenachrichtigung, die Sie von uns erhalten, wenn sich ein Update auf Ihre Verwendung des Diensts auswirken kann.

Informationen zu den Änderungen beim Intune-Dienst finden Sie unter [Neuerungen in Microsoft Intune](/intune/deploy-use/Whats-new-in-microsoft-intune.md). Der [Microsoft Intune-Blog](http://blogs.technet.com/b/microsoftintune/) behandelt auch Änderungen am Dienst und bietet nützliche Tipps, damit Sie Intune optimal nutzen können.

Über wichtige Dienstupdates werden Sie auch im [Verwaltungsportal von Office 365](https://portal.office.com/Admin/Default.aspx) im Nachrichtencenter informiert. Bei Installation der begleitenden [mobilen App für die Office 365-Verwaltung](https://support.office.com/en-us/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a) können Sie Benachrichtigungen auf Ihrem mobilen Gerät erhalten.

> [!NOTE] Sie können den Intune-Dienststatus im [Verwaltungsportal von Office 365](https://portal.office.com/Admin/Default.aspx) überwachen. Wählen Sie im linken Bereich **Dienststatus** aus.  

Folgende Typen von Benachrichtigungen werden von Microsoft über den Intune-Dienst angeboten:
-   Abhängig von den Auswirkungen der Änderung werden Sie mindestens 30 bis 90 Tage vor dem Dienstupgrade benachrichtigt, damit Sie Dienständerungen planen können. Dies erfolgt mithilfe der produktinternen Kommunikationskanäle wie Warnungen am Schwarzen Brett. Dies können folgende Änderungen sein:
* Updates, die möglicherweise Auswirkungen auf Compliance oder gesetzliche Anforderungen haben
* Änderungen an der Benutzererfahrung, Benutzeroberfläche und Workflows
* Neue oder geänderte APIs – Benachrichtigungen, dass Sie Tests durchführen müssen, um die Abwärtskompatibilität benutzerdefinierter Apps sicherzustellen.
* Änderungen an Systemanforderungen, z. B. die erforderliche Mindestversion des Browsers
* Alle Updates, die eine Aktion Ihrerseits erforderlich machen, um das Feature zu aktivieren oder eine Dienstunterbrechung zu der Funktion zu verhindern.
-   Microsoft stellt Informationen zu neuen Funktionen und Verbesserungen an vorhandenen Funktionen in monatlichen Serviceupdates bereit. Im Allgemeinen stellt Microsoft Dienstupdates in der Mitte eines jeden Monats bereit. Updates werden unter [Neues in Microsoft Intune](/intune/deploy-use/whats-new-in-microsoft-intune) beschrieben.
-   Im Falle einer Deaktivierung des Intune-Diensts würden Sie 12 Monate im Voraus informiert.

## Wählen Sie die Verwaltungslösung, die für Sie geeignet ist
Sie können Intune auf unterschiedlichste Weise konfigurieren, um die mobilen Geräte und Computer in Ihrem Unternehmen (in diesem Dokument als **Geräte** bezeichnet) zu verwalten und zu schützen.

-   **Eigenständige Intune-Konfiguration.** Verwenden Sie die webbasierte Verwaltungskonsole in Intune, um Geräte in Ihrer Organisation zu verwalten. Intune kann ohne lokale IT-Infrastruktur verwendet werden. Wenn Sie jedoch Intune mit Active Directory-Domänendiensten verwenden, können Sie Domänenbenutzerkonten verwenden, die Sie mit Domänendiensten mit Intune verwalten.

-   **Intune mit System Center Configuration Manager.** Verwenden Sie die Configuration Manager-Verwaltungskonsole, um Computer und mobile Geräte in Ihrem Unternehmen zu verwalten. Mit dieser Konfiguration können Sie alle Geräte der Organisation zentral über die Configuration Manager-Verwaltungskonsole verwalten. Configuration Manager unterstützt eine große Anzahl mobiler Geräte, Server und Computer. Weitere Informationen finden Sie unter [Verwalten von mobilen Geräten mit Configuration Manager und Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=271118) in der [Dokumentationsbibliothek zu System Center 2012 Configuration Manager](https://technet.microsoft.com/library/gg682041.aspx).  Weitere Informationen dazu, welcher Ansatz für Sie geeignet ist, finden Sie unter [Choose between Microsoft Intune standalone and hybrid mobile device management with Configuration Manager](https://technet.microsoft.com/en-us/library/mt706478.aspx) (Auswählen zwischen eigenständigem Microsoft Intune und der hybriden Verwaltung mobiler Geräte mit Configuration Manager).


## Weitere Informationen zu Intune
Verwenden Sie die folgenden Ressourcen, um weitere Informationen über Intune zu erhalten:

-   Das [Microsoft Intune Trust Center](http://www.microsoft.com/en-us/server-cloud/products/intune-trust-center/) bietet Informationen zu den Vorgehensweisen für Sicherheit, Datenschutz und Kompatibilität von Intune und beschreibt einige der Zertifizierungen von Intune.

-   [Verwaltungsfunktionen für mobile Geräte in Microsoft Intune](/intune/understand-explore/mobile-device-management-capabilities-in-microsoft-intune)

### Weitere Informationen:
[Microsoft Intune](https://docs.microsoft.com/intune/)
[Dokumentationsbibliothek zu System Center 2012 Configuration Manager](https://technet.microsoft.com/library/gg682041.aspx)

[Neuerungen in Microsoft Intune](/intune/deploy-use/whats-new-in-microsoft-intune)



<!--HONumber=Jun16_HO5-->


