---
title: Grundlegende Einrichtung von Intune
description: "Dieser Artikel gibt einen Überblick über die grundlegenden Schritte für das Einrichten von Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c3129b2a8d93e91493455da5f3e5fd1a59dd77bb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2017
---
# <a name="basic-setup"></a>Grundlegende Einrichtung

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Nachdem Sie Ihre Umgebung analysiert haben, können Sie mit dem Einrichten von Intune beginnen.

## <a name="external-dependencies-for-an-intune-deployment"></a>Externe Abhängigkeiten für eine Bereitstellung mit Intune

### <a name="identity"></a>Identität

Intune erfordert Azure Active Directory (AAD) als Identitäts- und Benutzergruppierungsanbieter.

-   Weitere Informationen zu [Identitätsanforderungen](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview).

-   Weitere Informationen zu [Anforderungen an die Verzeichnissynchronisierung](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements).

-   Weitere Informationen zu [Anforderungen an die mehrstufige Authentifizierung](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements).

-   Weitere Informationen zu [Planen von Benutzer- und Gerätegruppen](/intune/users-permissions-add).

-   Erhalten Sie Informationen zum [Erstellen von Benutzer- und Gerätegruppen](/intune/groups-get-started).

Wenn in Ihrer Organisation bereits Office 365 verwendet wird, muss Intune unbedingt dieselbe Azure Active Directory-Umgebung verwenden.

### <a name="pki-optional"></a>PKI (optional)

Wenn Sie Zertifikat-basierte Authentifizierung für VPN-, WLAN- oder E-Mail-Profile von Intune zu verwenden möchten, müssen Sie sicherstellen, dass eine unterstützte [PKI-Infrastruktur vorhanden ist](/intune/certificates-configure), in der Zertifikatprofile erstellt und bereitgestellt werden können.

Weitere Informationen zum Konfigurieren von Zertifikaten in Intune finden Sie weiter unten.

-   [Konfigurieren der Zertifikatinfrastruktur für SCEP](/intune/certificates-scep-configure)

-   [Konfigurieren der Zertifikatinfrastruktur für PFX](/intune/certficates-pfx-configure)


## <a name="task-list-for-an-intune-setup"></a>Aufgabenliste für die Einrichtung von Intune

### <a name="task-1-intune-subscription"></a>Aufgabe 1: Intune-Abonnement

Bevor Sie zu Intune migrieren können, brauchen Sie ein Intune-Abonnement.

-   Suchen Sie [diese Seite](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) auf, um Informationen zu den folgenden Vorgängen zu erhalten:

    -   Erstellen eines neuen Intune-Abonnements, das mit einem neuen AAD-Mandanten verknüpft ist

    -   Verknüpfen eines Intune-Abonnements, indem Sie sich als bereits vorhandener AAD-Mandant anmelden

### <a name="task-2-assign-intune-user-licenses"></a>Aufgabe 2: Zuweisen von Intune-Benutzerlizenzen

-   Erfahren Sie, wie Sie [Intune-Benutzerlizenzen zuweisen](licenses-assign.md) können.

-   Wenn Sie bereits einen neuen AAD-Mandanten erstellt haben, erfahren Sie, wie Sie [neue Benutzer erstellen oder Benutzer aus Ihrem lokalen Active Directory (AD) synchronisieren](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) können.

### <a name="task-3-set-your-mdm-authority-to-intune"></a>Aufgabe 3: Stellen Sie die MDM-Autorität auf Intune um

Intune kann über das Azure-Portal oder über die Konsole von Configuration Manager Current Branch verwaltet werden. Wenn Sie Intune nicht in eine Bereitstellung mit Configuration Manager Current Branch integrieren müssen, wir empfohlen, Intune über das [Azure-Portal](https://portal.azure.com) zu verwalten.

Legen Sie Ihre MDM-Autorität auf **Intune** fest, um das Azure-Portal für Intune zu aktivieren. Wenn Sie eine andere MDM-Autorität verwenden, ist es Intune möglich, die MDM-Verwaltung auf andere Verwaltungskonsolen von Microsoft zu übertragen. Das geschieht jedoch selten.

> [!IMPORTANT]
> Wenn Sie Ihr MDM zum ersten Mal an Intune übertragen, sollten Sie die MDM-Autorität auf Intune festlegen.

-   Erfahren Sie, wie Sie die [Autorität für die Verwaltung mobiler Geräte einrichten](/intune/mdm-authority-set) können.

## <a name="next-step"></a>Nächster Schritt

[Konfigurieren von Richtlinien für die Verwaltung von Apps und Geräten](migration-guide-configure-policies.md)
