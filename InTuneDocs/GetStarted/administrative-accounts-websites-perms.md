---
title: Administratorkonten, Websites und Berechtigungen in Microsoft Intune | Microsoft Intune
description: 
keywords: 
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: db3075e7-38fd-4dfe-b266-26aed10ac8ea
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: a8d9cf5d36107c54b97d2b5a5250645dc735a8da


---

# Administratorkonten, Websites und Berechtigungen in Microsoft Intune

Bevor Sie Microsoft Intune einrichten, lesen Sie dieses Thema, und machen Sie sich mit anderen Anforderungen vertraut, die unter [Was Sie wissen sollten, bevor Sie Microsoft Intune starten](what-to-know-before-you-start-microsoft-intune.md) aufgeführt sind.

Verwenden Sie Folgendes zum Verwalten von Intune:
- Zwei Arten von Administratorkonten
- Benutzerkonten mit zusätzlichen Berechtigungen
- Zwei webbasierte Verwaltungskonsolen/Portale, die Ihren Administratoren Zugriff auf die zu verwaltenden Optionen gewähren.

Diese Konten und Portale werden in den folgenden Abschnitten erläutert.

## Administratorkonten und Benutzerkonten mit speziellen Berechtigungen

Im folgenden finden Sie die Konten und Berechtigungen, die Sie für Intune verwenden.

### Mandantenadministrator
|Berechtigungsstufen|Weitere Informationen|
|--------------------------|-------------------------|
|Mandantenadministratoren ist eine Administratorrolle zugewiesen, mit der der Verwaltungsbereich des betreffenden Benutzers und die Aufgaben definiert werden, die er verwalten darf.<br /><br />Administratorrollen sind den verschiedenen Microsoft-Clouddiensten gemeinsam, auch wenn einige Rollen möglicherweise nicht von allen Diensten unterstützt werden.<br /><br /> Microsoft Intune verwendet die folgenden Rollen:<br /><br />– Globaler Administrator<br />– Rechnungsadministrator<br />– Kennwortadministrator<br />– Dienstunterstützungsadministrator<br />– Benutzerverwaltungsadministrator|Standardmäßig ist das Konto, mit dem Sie Ihr Microsoft Intune-Abonnement erstellen, ein Mandantenadministrator mit der globalen Administratorrolle.<br /></br>  Als Mandantenadministrator verwenden Sie zur Verwaltung Ihres Abonnements für [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)] das [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], und weisen Mandantenadministratoren vom [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)] aus zu.<br /><br />Verwenden Sie für den Zugriff auf die [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] einen Mandantenadministrator mit der globalen Administratorrolle, um Ihren ersten Dienstadministrator zuzuweisen. Als Best Practice empfiehlt es sich, für die täglichen Verwaltungsaufgaben keinen Mandantenadministrator zu verwenden. Ein Mandantenadministrator benötigt für den Zugriff auf die [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] keine Lizenz für [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />Der Mandantenadministrator ist ein Konzept, das allen Microsoft-Clouddiensten gemein ist. Wenn Sie [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] abonnieren, ist Ihr Dienst ein Mandant von Microsoft Azure AD. Weitere Informationen finden Sie im Abschnitt zum Azure AD-Mandanten in [Was ist ein Azure AD-Verzeichnis?](http://technet.microsoft.com/library/jj573650.aspx)|


### Dienstadministrator
|Berechtigungsstufen|Weitere Informationen|
|--------------------------|-------------------------|
|Dienstadministratoren sind die folgenden Berechtigungen zugewiesen:<br /><br />**Vollzugriff**: Mit dieser Berechtigung wird uneingeschränkter Zugriff auf alle Bereiche der [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] gewährt. Außerdem können damit andere Dienstadministratoren hinzugefügt und verwaltet werden.<br /><br />**Schreibgeschützter Zugriff**: Mit dieser Berechtigung wird eine Leseberechtigung für alle Bereiche der [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] gewährt. Ein Dienstadministrator mit schreibgeschütztem Zugriff kann zwar keine Daten ändern, aber Berichte ausführen.<br /><br />**Helpdesk – Gruppenknoten**: Hiermit werden Berechtigungen erteilt, die es dem Dienstadministrator ermöglichen, nur bestimmte Aufgaben auszuführen, die allgemein mit Helpdeskszenarien im Zusammenhang stehen. Informationen zu diesem Berechtigungssatz finden Sie unter [Anpassen von Intune-Konsolenansichten gemäß der Administratorrollen](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console).|Standardmäßig wird in [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kein Dienstadministrator zugewiesen. Stattdessen müssen Sie den ersten Dienstadministrator für Ihr Abonnement mithilfe eines Mandantenadministrators mit globaler Administratorrolle zuweisen. </br></br> Als Dienstadministrator verwenden Sie zur Verwaltung täglicher Aufgaben für [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] die [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].<br /><br />Dienstadministratoren werden über die Verwaltungskonsole zugewiesen. Damit ein Dienstadministrator auf die Verwaltungskonsole zugreifen kann, benötigt er eine Lizenz für [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].|



### Geräteregistrierungsmanager
|Berechtigungsstufen|Weitere Informationen|
|--------------------------|-------------------------|
|Geräteregistrierungsmanager sind Standardbenutzerkonten, die über die zusätzliche Berechtigung zum Registrieren von mehr als fünf Geräten verfügen.|Standardmäßig kann jeder [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)]-Benutzer bis zu fünf Geräte registrieren. Sie können einem Benutzerkonto jedoch die Berechtigung für Geräteregistrierungsmanager zuweisen und dann größere Gruppen von firmeneigenen Geräten über dieses Konto registrieren. Dies ist hilfreich, wenn die Geräte den Benutzern möglicherweise nur vorübergehend zugewiesen werden oder sie im Kioskmodus arbeiten, bei dem die Zuordnung des Geräts zu einem Benutzer nicht erforderlich ist.|


## Verwaltungswebsites für Intune
 Unterschiedliche Verwaltungsaufgaben erfordern von Ihnen die Verwendung einer der folgenden administrativen Websites, auf die Sie mithilfe eines [unterstützten Webbrowsers](supported-web-browsers.md) zugreifen können.

- [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Microsoft Intune-Verwaltungskonsole](https://admin.manage.microsoft.com/)

### [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)

**Als Mandantenadministrator verwenden Sie dieses Portal zum Verwalten Ihres Abonnements.** Dies umfasst die folgenden Aufgaben, sofern sie durch Ihre Administratorrolle zugelassen werden:

- Verwalten von Benutzerkonten für das Abonnement und Konfigurieren der Verzeichnissynchronisierung aus Ihrem lokalen Active Directory
- Verwalten von als „Sicherheitsgruppen“ bezeichneten Gruppen von Benutzern
- Zuweisen von Lizenzen, die Benutzern die Verwendung von [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] gestatten
- Konfigurieren des Domänennamens, den Sie mit Ihrem Abonnement verwenden. Mit dem Domänennamen wird das Konto definiert, mit dem sich Benutzer anmelden.
- Verwalten von Abrechnungs- und Einkaufsdetails für Ihr Abonnement. Dies schließt die Anzahl der Ihnen zur Verfügung stehenden Lizenzen und die Menge des Cloudspeichers ein, den Sie verwenden können.
- Suchen von Links zum Anzeigen der Integrität des [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Diensts
- Als Mandantenadministrator können Sie sich auch dann zur Verwaltung des Abonnements am Office 365-Portal anmelden, wenn Ihrem Konto keine Lizenz für die Nutzung von [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] zugewiesen ist.
- Jeder Benutzer, der über eine Intune-Lizenz verfügt, aber kein Administrator ist, kann über dieses Portal sein Kontokennwort zurücksetzen und sein Profil bearbeiten.
- Für den Zugriff auf das Office 365-Portal ist für Ihr Konto der Anmeldestatus **Zugelassen** erforderlich. Dieser Status unterscheidet sich vom Besitz einer Abonnementlizenz. Standardmäßig haben alle Benutzerkonten den Status **Zugelassen**.


### [Microsoft Intune-Verwaltungskonsole](https://admin.manage.microsoft.com/)

**Als Dienstadministrator verwenden Sie dieses Portal für tägliche Aufgaben** wie die folgenden:

- Festlegen von Richtlinien für Computer und mobile Geräte
- Hochladen und Bereitstellen von Software, z. B. Softwareupdates und Apps
- Verwalten von [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Endpoint Protection auf Computern
- Anzeigen des Gerätestatus und Ausführen von Berichten
- Melden Sie sich bei diesem Portal an. Sie müssen entweder über Dienstadministratorrechte verfügen oder ein Mandantenadministrator mit globaler Administratorrolle sein, damit Sie sich bei diesem Portal anmelden können.


Lediglich Benutzer mit Dienstadministratorrechten oder Mandantenadministratoren mit globaler Administratorrolle können sich bei diesem Portal anmelden. Für den Zugriff auf die Verwaltungskonsole sind für Ihr Konto eine Lizenz zur Verwendung von [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] und der Anmeldestatus **Zugelassen** erforderlich.

Erfahren Sie mehr über das [Hinzufügen von Benutzern für Ihr Abonnement](start-with-a-paid-subscription-to-microsoft-intune-step-3.md) und das [Zuweisen von Lizenzen für Ihr Abonnement](start-with-a-paid-subscription-to-microsoft-intune-step-4.md).

 ### Weitere Informationen:
 [Was Sie wissen sollten, bevor Sie Microsoft Intune starten](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


