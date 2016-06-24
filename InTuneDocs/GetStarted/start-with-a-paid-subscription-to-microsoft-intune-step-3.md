---
# required metadata

title: Synchronisieren von Active Directory und Hinzufügen von Benutzern zu Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Synchronisieren von Active Directory und Hinzufügen von Benutzern zu Intune
Sie können die Verzeichnissynchronisierung so konfigurieren, dass Benutzerkonten aus Ihrem lokalen Active Directory in Microsoft Azure Active Directory (Azure AD) importiert werden. Wenn Ihr lokaler Active Directory-Dienst mit all Ihren Azure Active Directory-basierten Diensten verbunden ist, gestaltet sich die Verwaltung der Benutzeridentität viel einfacher. Sie können auch Features für die einmalige Anmeldung konfigurieren, damit die Benutzer mit der Art der Authentifizierung vertraut sind und diese problemlos verläuft.

Eine weitere Vereinfachung: Wenn Sie mehrere Dienste mit dem gleichen [Azure AD-Mandanten](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant) verwenden, stehen die Benutzerkonten, die Sie zuvor synchronisiert haben, allen cloudbasierten Diensten zur Verfügung, die das gleiche Azure AD-Mandantenabonnement nutzen.

## Synchronisieren lokaler Benutzer mit Azure AD
Das einzige Tool, das Sie zur Synchronisierung der Benutzerkonten mit Azure AD benötigen, ist der [Azure AD Connect-Assistent](https://www.microsoft.com/download/details.aspx?id=47594). Der Azure AD Connect-Assistent stellt eine Anleitung zum Herstellen der Verbindung zwischen Ihrer lokalen Identitätsinfrastruktur und der Cloud bereit.  Wählen Sie die Topologie und Anforderungen aus (einzelne oder mehrere Verzeichnisse, Kennwortsynchronisierung oder Verbund). Alle Komponenten, die zum Einrichten und Aktivieren Ihrer Verbindung erforderlich sind, werden vom Assistenten bereitgestellt und konfiguriert. Hierzu gehören: Synchronisierungsdienste, Active Directory-Verbunddienste (AD FS) und das Azure AD PowerShell-Modul.

> [!TIP]
> Azure AD Connect umfasst Funktionen, die zuvor als Dirsync und Azure AD Sync veröffentlicht wurden. Erfahren Sie mehr über die [Verzeichnisintegration](http://technet.microsoft.com/library/jj573653.aspx). Informationen zu den Vorteilen der Synchronisierung von Benutzerkonten aus Ihrem lokalen Verzeichnis mit Azure AD finden Sie unter [Ähnlichkeiten zwischen Active Directory und Azure AD](http://technet.microsoft.com/library/dn518177.aspx)..

## Gewähren von Administratorberechtigungen
Nachdem Sie Ihrem Intune-Abonnement Benutzer hinzugefügt haben, sollten Sie einigen Benutzerkonten [Administratoranmeldeinformationen](administrative-accounts-websites-perms.md) zuweisen. Welche Konsole Sie für das Zuweisen von Administratoranmeldeinformationen verwenden, hängt davon ab, welchen Administratortyp Sie zuweisen möchten:

-   **Mandantenadministrator**: Weisen Sie diesen Administratortyp über das **[!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)]** zum Verwalten Ihres Abonnements zu. Dies schließt Abrechnungen, Cloudspeicher und das Verwalten von Benutzern ein, die Intune verwenden dürfen. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

-   **Dienstadministrator**: Weisen Sie diesen Administratortyp mithilfe der **[!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]** für tägliche Aufgaben zu. Dies schließt das Verwalten mobiler Geräte oder Computer, das Bereitstellen von Richtlinien oder Software und das Ausführen von Berichten ein.


### Nächste Schritte
Gratulation! Sie haben Schritt 3 der Kurzanleitung *Erste Schritte mit Intune* abgeschlossen..

>[!div class="step-by-step"]

>[&larr; **Domäneneinstellungen**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Verwalten von Intune-Lizenzen** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  


<!--HONumber=May16_HO1-->


