---
title: "Synchronisieren von Active Directory und Hinzufügen von Benutzern zu Intune | Microsoft Intune"
description: "Synchronisieren lokaler Benutzer mit Azure AD und Gewähren von Administratorberechtigungen für Ihr Intune-Abonnement"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 29b6e5a3d319c741482fcc2b600842e2e42b96e2
ms.openlocfilehash: 33534c685ad3a4ddfd4b605e088132f2b8ff2c36


---


# <a name="sync-active-directory-and-add-users-to-intune"></a>Synchronisieren von Active Directory und Hinzufügen von Benutzern zu Intune
Sie können die Verzeichnissynchronisierung so konfigurieren, dass Benutzerkonten aus Ihrem lokalen Active Directory in Microsoft Azure Active Directory (Azure AD) importiert werden. Wenn Ihr lokaler Active Directory-Dienst mit all Ihren Azure Active Directory-basierten Diensten verbunden ist, gestaltet sich die Verwaltung der Benutzeridentität viel einfacher. Sie können auch Features für die einmalige Anmeldung konfigurieren, damit die Benutzer mit der Art der Authentifizierung vertraut sind und diese problemlos verläuft.

Eine weitere Vereinfachung: Wenn Sie mehrere Dienste mit dem gleichen [Azure AD-Mandanten](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) verwenden, stehen die Benutzerkonten, die Sie zuvor synchronisiert haben, allen cloudbasierten Diensten zur Verfügung, die das gleiche Azure AD-Mandantenabonnement nutzen.

## <a name="synchronize-on-premises-users-with-azure-ad"></a>Synchronisieren lokaler Benutzer mit Azure AD
Das einzige Tool, das Sie zur Synchronisierung der Benutzerkonten mit Azure AD benötigen, ist der [Azure AD Connect-Assistent](https://www.microsoft.com/download/details.aspx?id=47594). Der Azure AD Connect-Assistent stellt eine Anleitung zum Herstellen der Verbindung zwischen Ihrer lokalen Identitätsinfrastruktur und der Cloud bereit.  Wählen Sie die Topologie und Anforderungen aus (einzelne oder mehrere Verzeichnisse, Kennwortsynchronisierung oder Verbund). Alle Komponenten, die zum Einrichten und Aktivieren Ihrer Verbindung erforderlich sind, werden vom Assistenten bereitgestellt und konfiguriert. Hierzu gehören: Synchronisierungsdienste, Active Directory-Verbunddienste (AD FS) und das Azure AD PowerShell-Modul.

> [!TIP]
> Azure AD Connect umfasst Funktionen, die zuvor als Dirsync und Azure AD Sync veröffentlicht wurden. Erfahren Sie mehr über die [Verzeichnisintegration](http://technet.microsoft.com/library/jj573653.aspx). Informationen zu den Vorteilen der Synchronisierung von Benutzerkonten aus Ihrem lokalen Verzeichnis mit Azure AD finden Sie unter [Ähnlichkeiten zwischen Active Directory und Azure AD](http://technet.microsoft.com/library/dn518177.aspx).

## <a name="grant-administrator-permissions"></a>Gewähren von Administratorberechtigungen

Verwenden Sie Folgendes zum Verwalten von Intune:
- Zwei Arten von Administratorkonten
- Benutzerkonten mit zusätzlichen Berechtigungen
- Zwei webbasierte Verwaltungskonsolen/Portale, die Ihren Administratoren Zugriff auf die zu verwaltenden Optionen gewähren.

Nachdem Sie Ihrem Intune-Abonnement Benutzer hinzugefügt haben, sollten Sie einigen Benutzerkonten Administratoranmeldeinformationen gewähren. Welche Konsole Sie für das Zuweisen von Administratoranmeldeinformationen verwenden, hängt davon ab, welchen Administratortyp Sie zuweisen möchten:

-   **Mandantenadministrator**: Verwenden Sie das **Microsoft Intune-Kontoportal**, um diesen Administratortyp zum Verwalten Ihres Abonnements zuzuweisen. Dies schließt Abrechnung, Cloudspeicher und das Verwalten der Benutzer ein, die Intune verwenden dürfen.

-   **Dienstadministrator**: Verwenden Sie das **Microsoft Intune-Kontoportal**, um diesen Administratortyp für tägliche Aufgaben zuzuweisen. Dies schließt das Verwalten mobiler Geräte oder Computer, das Bereitstellen von Richtlinien oder Software und das Ausführen von Berichten ein.

Diese Konten und Portale werden in den folgenden Abschnitten erläutert.

## <a name="administrator-accounts-and-user-accounts-with-special-permissions"></a>Administratorkonten und Benutzerkonten mit speziellen Berechtigungen

Im Folgenden finden Sie die Konten und Berechtigungen, die Sie für Intune verwenden.

### <a name="tenant-administrator"></a>Mandantenadministrator
|Berechtigungsstufen|Weitere Informationen|
|--------------------------|-------------------------|
|Mandantenadministratoren ist eine Administratorrolle zugewiesen, mit der der Verwaltungsbereich des betreffenden Benutzers und die Aufgaben definiert werden, die er verwalten darf.<br /><br />Administratorrollen sind den verschiedenen Microsoft-Clouddiensten gemeinsam, auch wenn einige Rollen möglicherweise nicht von allen Diensten unterstützt werden.<br /><br /> Microsoft Intune verwendet die folgenden Rollen:<br /><br />– Globaler Administrator<br />– Rechnungsadministrator<br />– Kennwortadministrator<br />– Dienstunterstützungsadministrator<br />– Benutzerverwaltungsadministrator|Standardmäßig ist das Konto, mit dem Sie Ihr Microsoft Intune-Abonnement erstellen, ein Mandantenadministrator mit der globalen Administratorrolle.<br /></br>  Als Mandantenadministrator verwenden Sie zur Verwaltung Ihres Abonnements für Intune das [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)] und weisen Mandantenadministratoren vom [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)] aus zu.<br /><br />Verwenden Sie für den Zugriff auf die [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] einen Mandantenadministrator mit der globalen Administratorrolle, um Ihren ersten Dienstadministrator zuzuweisen. Als Best Practice empfiehlt es sich, für die täglichen Verwaltungsaufgaben keinen Mandantenadministrator zu verwenden. Ein Mandantenadministrator benötigt keine Intune-Lizenz für den Zugriff auf das [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />Der Mandantenadministrator ist ein Konzept, das allen Microsoft-Clouddiensten gemein ist. Wenn Sie Intune abonnieren, ist Ihr Dienst ein Mandant von Microsoft Azure AD. Weitere Informationen finden Sie im Abschnitt zum Azure AD-Mandanten in [Was ist ein Azure AD-Verzeichnis?](http://technet.microsoft.com/library/jj573650.aspx)|


### <a name="service-administrator"></a>Dienstadministrator
|Berechtigungsstufen|Weitere Informationen|
|--------------------------|-------------------------|
|Dienstadministratoren sind die folgenden Berechtigungen zugewiesen:<br /><br />**Vollzugriff**: Mit dieser Berechtigung wird uneingeschränkter Zugriff auf alle Bereiche der [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] gewährt. Außerdem können damit andere Dienstadministratoren hinzugefügt und verwaltet werden.<br /><br />**Schreibgeschützter Zugriff**: Mit dieser Berechtigung wird eine Leseberechtigung für alle Bereiche der [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] gewährt. Ein Dienstadministrator mit schreibgeschütztem Zugriff kann zwar keine Daten ändern, aber Berichte ausführen.<br /><br />**Helpdesk – Gruppenknoten**: Hiermit werden Berechtigungen erteilt, die es dem Dienstadministrator ermöglichen, nur bestimmte Aufgaben auszuführen, die allgemein mit Helpdeskszenarien im Zusammenhang stehen. Informationen zu diesem Berechtigungssatz finden Sie unter [Anpassen von Intune-Konsolenansichten gemäß der Administratorrollen](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console).|Standardmäßig wird in Intune kein Dienstadministrator zugewiesen. Stattdessen müssen Sie den ersten Dienstadministrator für Ihr Abonnement mithilfe eines Mandantenadministrators mit globaler Administratorrolle zuweisen. </br></br> Als Dienstadministrator verwenden Sie zur Verwaltung täglicher Aufgaben für Intune die [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)].<br /><br />Dienstadministratoren werden über die Verwaltungskonsole zugewiesen. Damit ein Dienstadministrator auf die Administratorkonsole zugreifen kann, benötigt er eine Lizenz für Intune.|



### <a name="device-enrollment-managers"></a>Geräteregistrierungsmanager
|Berechtigungsstufen|Weitere Informationen|
|--------------------------|-------------------------|
|Geräteregistrierungsmanager sind Standardbenutzerkonten, die über die zusätzliche Berechtigung zum Registrieren von mehr als fünf Geräten verfügen.|Standardmäßig kann jeder [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)]-Benutzer bis zu fünf Geräte registrieren. Sie können einem Benutzerkonto jedoch die Berechtigung für Geräteregistrierungsmanager zuweisen und dann größere Gruppen von firmeneigenen Geräten über dieses Konto registrieren. Dies ist hilfreich, wenn die Geräte den Benutzern möglicherweise nur vorübergehend zugewiesen werden oder sie im Kioskmodus arbeiten, bei dem die Zuordnung des Geräts zu einem Benutzer nicht erforderlich ist.|




>[!div class="step-by-step"]

>[&larr; **Domäneneinstellungen**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Verwalten von Intune-Lizenzen** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Nov16_HO4-->


