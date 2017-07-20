---
title: "Hinzufügen von Benutzern und Gewähren von Berechtigungen"
description: "Synchronisieren lokaler Benutzer mit Azure AD und Gewähren von Administratorberechtigungen für Ihr Intune-Abonnement"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4289fdbdadbef34f06514b62722f84354534ae65
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2017
---
# <a name="add-users-and-give-administrative-permission-to-intune"></a>Hinzufügen von Benutzern und Gewähren von Administratorrechten für Intune

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

In diesem Thema erfahren Administratoren, wie sie Benutzer zu Intune hinzufügen können und welche Administratorberechtigungen im Intune-Dienst verfügbar sind.

Als Administrator können Sie Benutzer direkt oder durch Synchronisieren mit Ihrem lokalen Active Directory hinzufügen. Nachdem ein Benutzer hinzugefügt wurde, kann er Geräte registrieren und auf Unternehmensressourcen zugreifen. Sie können Benutzern auch zusätzliche Berechtigungen erteilen, beispielsweise *globale Administrator*- und *Dienstadministrator*-Berechtigungen.

## <a name="add-users-to-intune"></a>Hinzufügen von Benutzern zu Intune
Sie können Benutzer manuell über das [Office 365-Portal](https://www.office.com/signin) oder das [Azure Intune-Portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview) zu Ihrem Intune-Abonnement hinzufügen. Ein Administrator kann Benutzerkonten bearbeiten, um Intune-Lizenzen zuzuweisen. Sie können Lizenzen entweder im Office 365-Portal oder im Intune Azure-Portal zuweisen. Weitere Informationen zum Gebrauch des Office 365-Portals finden Sie unter [Hinzufügen von einzelnen Benutzern oder Massenhinzufügen von Benutzern zu Office 365 – Administratorhilfe](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="add-intune-users-in-the-office-365-admin-center"></a>Hinzufügen von Benutzern im Office 365 Admin Center
1. Melden Sie sich im [Office 365-Portal](https://www.office.com/signin) an.
2. Wählen Sie im Office 365-Menü **Administrator** aus.
3. Wählen Sie im Admin Center **Benutzer hinzufügen** aus.

  ![Screenshot des Office 365 Admin Center](media/office-add-user.png)

4. Geben Sie die folgenden Benutzerdetails an:
  - **Vorname**
  - **Nachname**
  - **Anzeigename**: wird im Intune-Portal angezeigt
  - **Benutzername**: UPN-Name im Intune-Portal
  - **Speicherort**
  - **Kontaktinformationen** (optional)
  - **Kennwort**: automatisch generiert oder angegeben

     ![Screenshot des Office 365 Admin Center](media/office-add-user-details.png)

5. Weisen Sie eine Intune-Lizenz hinzu. Wählen Sie **Produktlizenzen** aus, und wählen Sie die Produktlizenz.
6. Wählen Sie **Hinzufügen** aus, um den neuen Benutzer zu erstellen.

### <a name="add-intune-users-in-the-azure-intune-portal"></a>Hinzufügen von Intune-Benutzern im Azure Intune-Portal
1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an. Navigieren Sie zu **Überwachung + Verwaltung** > **Intune**. Sie können auch *Ressourcen* für **Intune** suchen.
2. Wählen Sie **Benutzer** aus.
3. Wählen Sie im Admin Center **Benutzer hinzufügen** aus.
  ![Screenshot des Office 365 Admin Center](media/intune-add-user.png)
4. Geben Sie die folgenden Benutzerdetails an:
  - **Name**
  - **Benutzername**: Der neue Name im Azure Active Directory-Portal ![Screenshot des Office 365 Admin Center](media/intune-add-user-info.png) Klicken Sie auf **OK**, um fortzufahren.
5. Optional können Sie die folgenden Benutzereigenschaften angeben:
  - **Profil**: Informationen zum Beruf, einschließlich **Position** und **Abteilung**
  -  **Gruppen**: Gruppen auswählen, die zum Benutzer hinzugefügt werden
  - **Verzeichnisrolle**: dem Benutzer Administratorrechte für Intune geben

  Wählen Sie **Erstellen** aus, um in Intune einen neuen Benutzer hinzuzufügen.
6. Wählen Sie **Profil** aus und dann einen **Verwendungsstandort:** für den neuen Benutzer. Der Verwendungsstandort wird benötigt, bevor Sie dem neuen Benutzer eine Intune-Lizenz zuweisen können. Klicken Sie auf **Speichern**, um fortzufahren.
    ![Screenshot des Office 365 Admin Center](media/intune-add-user-loc.png)
7. Wählen Sie **Lizenzen** aus und dann **Zuweisen**, um diesem Benutzer eine Intune-Lizenz zuzuweisen. Eine Intune-Lizenz ist erforderlich, um Geräte zu registrieren oder auf Unternehmensressourcen zuzugreifen. Wählen Sie **Produkte** aus, dann den Lizenztyp, klicken Sie auf **Auswählen** und dann **Zuweisen**.

## <a name="grant-admin-permissions"></a>Gewähren von Administratorberechtigungen

Nachdem Sie Ihrem Intune-Abonnement Benutzer hinzugefügt haben, sollten Sie einigen Benutzern Administratorrechte gewähren:
-   [Globaler Administrator](#tenant-administrator): Verwenden Sie das Office 365-Portal, um diesen Administratortyp zuzuweisen. Der globale Administrator verwaltet Ihr Abonnement, einschließlich Rechnungen, Cloudspeicher und Benutzer, die Intune verwenden dürfen.
-   [Benutzerdefinierter oder eingeschränkter Administrator](#service-administrator): Verwenden Sie die Office 365- oder Azure Intune-Administratorkonsole, um diesen Administratortyp für tägliche Aufgaben zuzuweisen. Dies schließt die Geräte- und Computerverwaltung, das Bereitstellen von Richtlinien und Apps sowie das Ausführen von Berichten ein.

![Abbildung des Office 365-Portals, das Rollen zuweist](./media/office-assign-roles.png)

### <a name="types-of-administrators"></a>Typen von Administratoren

Weisen Sie Benutzern mindestens eine Administratorberechtigung zu. Diese Berechtigungen definieren den administrativen Bereich für Benutzer sowie die Aufgaben, die sie verwalten können. Administratorberechtigungen sind den verschiedenen Microsoft-Clouddiensten gemeinsam, auch wenn einige Berechtigungen möglicherweise nicht von allen Diensten unterstützt werden. Intune verwendet die folgenden Administratorberechtigungen:

- **Globaler Administrator**: (Office 365 und Intune) Besitzt Zugriff auf alle Verwaltungsfunktionen in Intune. Standardmäßig wird die Person, die sich für Intune angemeldet hat, zum globalen Administrator. Globale Administratoren sind die einzigen Administratoren, die andere Administratorrollen zuweisen können. Sie können in Ihrer Organisation über mehrere globale Administratoren verfügen. Als bewährte Methode wird empfohlen, nur wenigen Personen in Ihrem Unternehmen diese Funktion zuzuweisen, um Risiken für Ihr Unternehmen so gering wie möglich zu halten.
- **Rechnungsadministrator**: (Office 365 und Intune) Tätigt Erwerbe, verwaltet Abonnements, verwaltet Supporttickets und überwacht den Dienststatus.
- **Kennwortadministrator**: (Office 365 und Intune) Setzt Kennwörter zurück, verwaltet Serviceanfragen und überwacht den Dienststatus. Die Rechte von Kennwortadministratoren beschränken sich auf das Zurücksetzen von Kennwörtern für Benutzer.
- **Dienstadministrator**: (Office 365) Öffnet Supportanfragen an Microsoft und überwacht das Servicedashboard und das Nachrichtencenter. Sie verfügen über „Nur-Anzeige“-Berechtigungen, können allerdings Supporttickets öffnen und lesen.
- **Benutzerverwaltungsadministrator**: (Office 365 und Intune) Setzt Kennwörter zurück, überwacht die Dienstintegrität, kann Benutzerkonten hinzufügen oder löschen und verwaltet Serviceanfragen. Der Benutzerverwaltungsadministrator kann keine globalen Administratoren löschen, keine andere Administratorrollen erstellen und keine Kennwörter für andere Administratoren zurücksetzen.

Standardmäßig ist das Konto, mit dem Sie Ihr Microsoft Intune-Abonnement erstellen, ein globaler Administrator. Als Best Practice empfiehlt es sich, für die täglichen Verwaltungsaufgaben keinen globalen Administrator zu verwenden. Ein Administrator benötigt keine Intune-Lizenz für den Zugriff auf die Intune-Administratorkonsole. Weitere Informationen finden Sie im Abschnitt zum Azure AD-Mandanten in [Was ist ein Azure AD-Verzeichnis?](http://technet.microsoft.com/library/jj573650.aspx)

Für den Zugriff auf das Office 365-Portal muss für Ihr Konto **Anmeldung zulässig** festgelegt sein. Legen Sie im Intune-Portal unter **Profil** **Anmeldung blockieren** auf **Nein** fest, um den Zugriff zu gewähren. Dieser Status unterscheidet sich vom Besitz einer Abonnementlizenz. Standardmäßig haben alle Benutzerkonten den Status **Zugelassen**. Benutzer ohne Administratorrechte können Intune-Kennwörter über das Office 365-Portal zurücksetzen.

## <a name="sync-active-directory-and-add-users-to-intune"></a>Synchronisieren von Active Directory und Hinzufügen von Benutzern zu Intune
Sie können die Verzeichnissynchronisierung so konfigurieren, dass Benutzerkonten aus Ihrem lokalen Active Directory in Microsoft Azure Active Directory (Azure AD) importiert werden. Dies schließt Intune Benutzer ein. Wenn Ihr lokaler Active Directory-Dienst mit all Ihren Azure Active Directory-basierten Diensten verbunden ist, gestaltet sich die Verwaltung der Benutzeridentität viel einfacher. Sie können auch Features für die einmalige Anmeldung konfigurieren, damit die Benutzer mit der Art der Authentifizierung vertraut sind und diese problemlos verläuft. Durch das Verknüpfen eines [Azure AD-Mandanten](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) mit mehreren Diensten sind die zuvor synchronisierten Benutzerkonten für alle cloudbasierten Dienste verfügbar.

### <a name="how-to-sync-on-premises-users-with-azure-ad"></a>Synchronisieren lokaler Benutzer mit Azure AD
Das einzige Tool, das Sie zur Synchronisierung der Benutzerkonten mit Azure AD benötigen, ist der [Azure AD Connect-Assistent](https://www.microsoft.com/download/details.aspx?id=47594). Der Azure AD Connect-Assistent stellt eine Anleitung zum Herstellen der Verbindung zwischen Ihrer lokalen Identitätsinfrastruktur und der Cloud bereit.  Wählen Sie Ihre Topologie und Bedürfnisse (einzelnen oder mehrere Verzeichnisse, Kennwortsynchronisierung oder -verbund). Der Assistent konfiguriert alle Komponenten, die für die erfolgreiche Verbindung nötig sind, und stellt sie bereit. Hierzu gehören: Synchronisierungsdienste, Active Directory-Verbunddienste (AD FS) und das Azure AD PowerShell-Modul.

> [!TIP]
> Azure AD Connect umfasst Funktionen, die zuvor als Dirsync und Azure AD Sync veröffentlicht wurden. Erfahren Sie mehr über die [Verzeichnisintegration](http://technet.microsoft.com/library/jj573653.aspx). Informationen zur Synchronisierung von Benutzerkonten aus einem lokalen Verzeichnis mit Azure AD finden Sie unter [Ähnlichkeiten zwischen Active Directory und Azure AD](http://technet.microsoft.com/library/dn518177.aspx).
