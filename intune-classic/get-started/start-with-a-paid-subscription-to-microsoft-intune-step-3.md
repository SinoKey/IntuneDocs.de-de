---
title: "Hinzufügen von Benutzern und Gewähren von Berechtigungen | Microsoft-Dokumentation"
description: "Synchronisieren lokaler Benutzer mit Azure AD und Gewähren von Administratorberechtigungen für Ihr Intune-Abonnement"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 4a90d0bdebafeb8a9e5c73892b6f1f11b76eb9f6
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---

# <a name="add-users-and-give-administrative-permission-to-intune"></a>Hinzufügen von Benutzern und Gewähren von Administratorrechten für Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

In diesem Thema erfahren Administratoren, wie sie Benutzer zu Intune hinzufügen können und welche Administratorberechtigungen im Intune-Dienst verfügbar sind.

Als Administrator können Sie Benutzer direkt oder durch Synchronisieren mit Ihrem lokalen Active Directory hinzufügen. Nachdem ein Benutzer hinzugefügt wurde, kann er Geräte registrieren und auf Unternehmensressourcen zugreifen. Sie können Benutzern auch zusätzliche Berechtigungen erteilen, beispielsweise *Mandantenadministrator*-, *Dienstadministrator*- und *Geräteregistrierungs-Manager-Berechtigungen*.

Dieses Thema enthält Hilfe zu folgenden Themen:

- [Hinzufügen von Benutzern zu Intune](#add-users-to-intune)
- [Gewähren von zusätzlichen Berechtigungen für Intune](#grant-intune-permissions), z. B.:
  - [Mandantenadministrator](#tenant-administrator)
  - [Dienstadministrator](#service-administrator)
  - [Geräteregistrierungs-Manager](#device-enrollment-managers)

## <a name="add-users-to-intune"></a>Hinzufügen von Benutzern zu Intune
Sie können Benutzer manuell über das [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) zu Ihrem Intune-Abonnement hinzufügen, ihnen werden jedoch nicht automatisch Intune-Lizenzen zugewiesen. Stattdessen muss ein Intune-Mandantenadministrator die Benutzerkonten später bearbeiten, um den betreffenden Benutzern über das Office 365-Portal eine Lizenz zuzuweisen. Eine Anleitung hierzu finden Sie unter [Hinzufügen von einzelnen Benutzern oder Massenhinzufügen von Benutzern zu Office 365](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="sync-active-directory-and-add-users-to-intune"></a>Synchronisieren von Active Directory und Hinzufügen von Benutzern zu Intune
Sie können die Verzeichnissynchronisierung so konfigurieren, dass Benutzerkonten aus Ihrem lokalen Active Directory in Microsoft Azure Active Directory (Azure AD) importiert werden. Dies schließt Intune Benutzer ein. Wenn Ihr lokaler Active Directory-Dienst mit all Ihren Azure Active Directory-basierten Diensten verbunden ist, gestaltet sich die Verwaltung der Benutzeridentität viel einfacher. Sie können auch Features für die einmalige Anmeldung konfigurieren, damit die Benutzer mit der Art der Authentifizierung vertraut sind und diese problemlos verläuft. Durch das Verknüpfen eines [Azure AD-Mandanten](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) mit mehreren Diensten sind die zuvor synchronisierten Benutzerkonten für alle cloudbasierten Dienste verfügbar.

### <a name="how-to-sync-on-premises-users-with-azure-ad"></a>Synchronisieren lokaler Benutzer mit Azure AD
Das einzige Tool, das Sie zur Synchronisierung der Benutzerkonten mit Azure AD benötigen, ist der [Azure AD Connect-Assistent](https://www.microsoft.com/download/details.aspx?id=47594). Der Azure AD Connect-Assistent stellt eine Anleitung zum Herstellen der Verbindung zwischen Ihrer lokalen Identitätsinfrastruktur und der Cloud bereit.  Wählen Sie die Topologie und Anforderungen aus (einzelne oder mehrere Verzeichnisse, Kennwortsynchronisierung oder Verbund). Alle Komponenten, die zum Einrichten und Aktivieren Ihrer Verbindung erforderlich sind, werden vom Assistenten bereitgestellt und konfiguriert. Hierzu gehören: Synchronisierungsdienste, Active Directory-Verbunddienste (AD FS) und das Azure AD PowerShell-Modul.

> [!TIP]
> Azure AD Connect umfasst Funktionen, die zuvor als Dirsync und Azure AD Sync veröffentlicht wurden. Erfahren Sie mehr über die [Verzeichnisintegration](http://technet.microsoft.com/library/jj573653.aspx). Informationen zu den Vorteilen der Synchronisierung von Benutzerkonten aus Ihrem lokalen Verzeichnis mit Azure AD finden Sie unter [Ähnlichkeiten zwischen Active Directory und Azure AD](http://technet.microsoft.com/library/dn518177.aspx).

## <a name="grant-intune-permissions"></a>Gewähren von Intune-Berechtigungen

Nachdem Sie Ihrem Intune-Abonnement Benutzer hinzugefügt haben, sollten Sie einigen Benutzerkonten Administratorrechte gewähren. Für die Verwaltung von Intune können Sie Benutzern drei Arten von Intune Berechtigungen gewähren.
-   **Mandantenadministrator**: Weisen Sie diesen Administratortyp über das Office 365-Portal zum Verwalten Ihres Abonnements zu. Dies schließt Abrechnungen, Cloudspeicher und das Verwalten von Benutzern ein, die Intune verwenden dürfen.
-   **Dienstadministrator**: Verwenden Sie die Microsoft Intune-Administratorkonsole, um diesen Administratortyp für tägliche Aufgaben zuzuweisen. Dies schließt die Geräte- und Computerverwaltung, das Bereitstellen von Richtlinien und Apps sowie das Ausführen von Berichten ein.
-   **Geräteregistrierungs-Manager**: Verwenden Sie die Microsoft Intune-Administratorkonsole, um diesen Administratortyp für tägliche Aufgaben zuzuweisen. Dies schließt die Geräte- und Computerverwaltung, das Bereitstellen von Richtlinien und Apps sowie das Ausführen von Berichten ein.


### <a name="tenant-administrator"></a>Mandantenadministrator


Mandantenadministratoren ist eine Administratorrolle zugewiesen, mit der der Verwaltungsbereich des betreffenden Benutzers und die Aufgaben definiert werden, die er verwalten darf. Administratorrollen sind den verschiedenen Microsoft-Clouddiensten gemeinsam, auch wenn einige Rollen möglicherweise nicht von allen Diensten unterstützt werden. Intune verwendet die folgenden Rollen:
- **Globaler Administrator**: Besitzt Zugriff auf alle Verwaltungsfunktionen in Intune. Standardmäßig wird die Person, die sich für Intune angemeldet hat, zum globalen Administrator. Globale Administratoren sind die einzigen Administratoren, die andere Administratorrollen zuweisen können. Sie können in Ihrer Organisation über mehrere globale Administratoren verfügen. Als bewährte Methode wird empfohlen, nur wenigen Personen in Ihrem Unternehmen diese Funktion zuzuweisen, um Risiken für Ihr Unternehmen so gering wie möglich zu halten.
- **Rechnungsadministrator**: Tätigt Erwerbe, verwaltet Abonnements, verwaltet Supporttickets und überwacht den Dienststatus.
- **Kennwortadministrator**: Setzt Kennwörter zurück, verwaltet Serviceanfragen und überwacht den Dienststatus. Die Rechte von Kennwortadministratoren beschränken sich auf das Zurücksetzen von Kennwörtern für Benutzer.
- **Dienstunterstützungsadministrator**: Öffnet Supportanfragen an Microsoft und überwacht das Servicedashboard und das Nachrichtencenter. Sie verfügen über „Nur-Anzeige“-Berechtigungen, können allerdings Supporttickets öffnen und lesen.
- **Benutzerverwaltungsadministrator**: Setzt Kennwörter zurück, überwacht die Dienstintegrität, kann Benutzerkonten hinzufügen oder löschen und verwaltet Serviceanfragen. Der Benutzerverwaltungsadministrator kann keine globalen Administratoren löschen, keine andere Administratorrollen erstellen und keine Kennwörter für Rechnungsadministratoren, globale Aministratoren oder Dienstadministratoren zurücksetzen.

Standardmäßig ist das Konto, mit dem Sie Ihr Microsoft Intune-Abonnement erstellen, ein Mandantenadministrator mit der globalen Administratorrolle. Als Mandantenadministrator verwenden Sie die Intune-Administratorkonsole zur Verwaltung Ihres Abonnements für Intune und das [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) zum Zuweisen von Mandantenadministratoren. Verwenden Sie einen Mandantenadministrator mit der globalen Administratorrolle, um auf das Portal zuzugreifen und den ersten Dienstadministrator zuzuweisen. Als Best Practice empfiehlt es sich, für die täglichen Verwaltungsaufgaben keinen Mandantenadministrator zu verwenden. Ein Mandantenadministrator benötigt keine Intune-Lizenz für den Zugriff auf die Intune-Administratorkonsole. Der Mandantenadministrator ist ein Konzept, das allen Microsoft-Clouddiensten gemein ist. Wenn Sie Intune abonnieren, ist Ihr Dienst ein Mandant von Azure AD. Weitere Informationen finden Sie im Abschnitt zum Azure AD-Mandanten in [Was ist ein Azure AD-Verzeichnis?](http://technet.microsoft.com/library/jj573650.aspx)

Als Mandantenadministrator verwenden Sie das [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) zum Verwalten Ihres Abonnements. Dies umfasst die folgenden Aufgaben, sofern sie durch Ihre Administratorrolle zugelassen werden:

- Verwalten von Benutzerkonten und Konfigurieren der Verzeichnissynchronisierung aus Ihrem lokalen Active Directory
- Verwalten von als „Sicherheitsgruppen“ bezeichneten Gruppen von Benutzern
- Zuweisen von Lizenzen für Intune an Benutzer
- Konfigurieren des Domänennamens (z. B. contoso.com) für Ihr Abonnement, der verwendet wird, wenn Benutzer sich anmelden
- Verwalten von Abrechnungs- und Kaufvorgängen, einschließlich Lizenzen und Cloudspeicher
- Suchen von Links zum Anzeigen der Integrität des Intune-Diensts

Für den Zugriff auf das Office 365-Portal ist für Ihr Konto der Anmeldestatus **Zugelassen** erforderlich. Dieser Status unterscheidet sich vom Besitz einer Abonnementlizenz. Standardmäßig haben alle Benutzerkonten den Status **Zugelassen**. Benutzer ohne Administratorrechte können Intune-Kennwörter über das Office 365-Portal zurücksetzen.

### <a name="service-administrator"></a>Dienstadministrator

Standardmäßig wird in Intune kein Dienstadministrator zugewiesen. Stattdessen müssen Sie den ersten Dienstadministrator für Ihr Abonnement mithilfe eines Mandantenadministrators mit globaler Administratorrolle zuweisen. Als Dienstadministrator verwenden Sie zur Verwaltung täglicher Aufgaben für Intune die [Intune-Administratorkonsole](https://manage.microsoft.com/). Dienstadministratoren werden über die Verwaltungskonsole zugewiesen. Damit ein Dienstadministrator auf die Administratorkonsole zugreifen kann, benötigt er eine Lizenz für Intune.

Dienstadministratoren sind die folgenden Berechtigungen zugewiesen:
- **Vollzugriff**: Uneingeschränkter Zugriff auf alle Bereiche der Intune-Administratorkonsole, Hinzufügen und Verwalten anderer Dienstadministratoren
- **Schreibgeschützter Zugriff**: Leseberechtigung für alle Bereiche der Intune-Administratorkonsole, kann keine Daten ändern, aber Berichte ausführen
- **Helpdesk – Gruppenknoten**: Erlaubt dem Dienstadministrator, nur Aufgaben im Zusammenhang mit Helpdeskszenarien auszuführen. Weitere Informationen finden Sie unter [Anpassen von Intune-Konsolenansichten entsprechend den Administratorrollen](/intune-classic/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console)

Als Dienstadministrator verwenden Sie dieses Portal für tägliche Aufgaben wie die folgenden:

- Erstellen und Verwalten von Richtlinien für Computer und mobile Geräte
- Hochladen und Bereitstellen von Softwareupdates und Apps
- Verwalten von Endpoint Protection auf Computern
- Anzeigen des Gerätestatus und Ausführen von Berichten

### <a name="device-enrollment-managers"></a>Geräteregistrierungsmanager

Geräteregistrierungs-Manager sind Standardbenutzerkonten mit der zusätzlichen Berechtigung zum Registrieren großer Mengen von benutzerlosen Geräten. Standardmäßig kann jeder Intune-Benutzer bis zu 15 Geräte registrieren. Als Administrator können Sie einem Benutzerkonto die Geräteregistrierungs-Manager-Berechtigung erteilen. Dieses Konto kann große Mengen unternehmenseigener Geräte registrieren. Dies ist hilfreich, wenn die Geräte den Benutzern möglicherweise nur vorübergehend zugewiesen werden oder sie im Kioskmodus arbeiten, bei dem die Zuordnung des Geräts zu einem Benutzer nicht erforderlich ist. Weitere Informationen finden Sie unter [Geräteregistrierungs-Manager](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

>[!div class="step-by-step"]

>[&larr; **Domäneneinstellungen**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Verwalten von Intune-Lizenzen** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  

