---
title: "Schützen von Office 365 Exchange Online ohne erforderliche Geräteverwaltung"
description: "Gewähren Sie Mitarbeitern Zugriff auf ihre geschäftlichen E-Mails. Es ist keine Geräteverwaltung erforderlich."
keywords: Office 365 Exchange-E-Mail-Zugriff
author: arob98
manager: angrobe
ms.date: 08/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 88a0d3b9-2622-403b-8374-1396afd8066e
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3e27f8ae8b42617f73d44fdf128772204f1963ed
ms.sourcegitcommit: 86687a8272ee3269aa7330e85022661b20450059
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2017
---
# <a name="protect-office-365-exchange-online-without-requiring-device-management"></a>Schützen von Office 365 Exchange Online ohne erforderliche Geräteverwaltung

Wenn Sie Mitarbeitern Zugriff auf ihre geschäftlichen E-Mails geben möchten, ohne den Aufwand, ein Geräteverwaltungssystem einzurichten, können Sie das tun. Sie können über Intune Zugriff auf Office 365 Exchange Online gewähren. Um die notwendigen Schritte durchzuführen, bestätigen Sie, dass Sie über Lizenzen für Microsoft 365 oder Azure Active Directory (Premium) und Intune verfügen. Mitarbeiter müssen über ein [unterstütztes iOS- oder Android-Gerät](supported-devices-browsers.md) verfügen. 

Wenn Sie sich dafür entscheiden, ein Geräteverwaltungssystem einzurichten, können Sie das tun. Diese Art von App-Schutz funktioniert unabhängig von der Geräteverwaltung. 

## <a name="action-plan"></a>Maßnahmenplan

1. [Weitere Informationen zum bedingten Zugriff](conditional-access.md). 
2. [Weitere Informationen zum App-basierten bedingten Zugriff](app-based-conditional-access-intune.md).
3. [Einrichten App-basierter Richtlinien für bedingten Zugriff](app-based-conditional-access-intune-create.md).
4. [Blockieren von Apps, die nicht verwaltet werden können](app-modern-authentication-block.md), insbesondere Apps, die nicht die Authentifizierungsbibliothek von Azure Active Directory (ADAL) verwenden.
5. (Optional) [Einrichten App-basierter Richtlinien für bedingten Zugriff](app-based-conditional-access-intune-create.md). Diese Richtlinien blockieren den Zugriff auf Ihre Unternehmensdaten über Apps, die nicht verwaltet und geschützt werden können. Die Richtlinien beschränken auch den Zugriff über die mobile Version von SharePoint. 

## <a name="what-to-tell-employees-and-students"></a>Informationen für Mitarbeiter und Studenten

* Bitten Sie Ihre Mitarbeiter und Studenten, Microsoft Outlook oder Microsoft SharePoint für iOS aus dem Apple App Store oder für Android aus dem Google Play Store herunterzuladen. 
* Wenn Sie den Zugriff auf Apps blockieren, die keine moderne Authentifizierung verwenden, informieren Sie die Mitarbeiter und Studenten darüber. 

## <a name="next-steps"></a>Nächste Schritte

Sie haben den App-basierten bedingten Zugriff verwendet, um die Sicherheit der Unternehmensdaten zu erhöhen. Im Zuge der nächsten Schritte können Sie mehr über die anderen Möglichkeiten erfahren, den Schutz Ihrer Unternehmensdaten zu erhöhen. Dazu zählt Folgendes: 

* Einrichten des [bedingten Zugriffs basierend auf der Gerätekompatibilität, dem Geräterisiko, dem Speicherort und Benutzerattributen in Active Directory und Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)  
* Einrichten von App-Schutzrichtlinien zum Schutz Ihrer Unternehmensdaten vor versehentlichen und vorsätzlichen Datenverlusten 
* Verwenden von Azure Information Protection zum Schutz von Unternehmensdaten außerhalb Ihres Netzwerks 

Benötigen Sie Hilfe bei der Aktivierung dieses oder anderer EMS- oder Office 365-Szenarios? Wenn Sie über mindestens 150 Lizenzen für Microsoft 365, Enterprise Mobility + Security oder Azure Active Directory Premium verfügen, nutzen Sie Ihre [FastTrack-Vorteile](https://docs.microsoft.com/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program). 