---
title: "Schützen von Apps und Daten | Microsoft Intune"
description: "Dieses Thema beschreibt die verschiedenen Intune-Features und -Funktionen, die Ihnen zum Schutz Ihrer Unternehmens-Apps und Daten zur Verfügung stehen."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c46e188-87eb-4ce2-b184-24809e8bf783
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: dd7a51b5ba176c8c7b593d2d7a3e5cfabd72a1e6
ms.openlocfilehash: 77ce4cca5f85f1847e599a6151411bfc12afbc8b


---

# Schützen von Apps und Daten mit Microsoft Intune


Intune schützt Unternehmensdaten auf verschiedenen Technologieebenen.  Auf Ebene der Identität wird Schutz über das Konzept des bedingten Zugriffs implementiert: Der Zugriff auf Dienste ist nur über verwaltete und kompatible Geräte gestattet.  Auf Ebene der Clientanwendung schützt die Verwaltung mobiler Apps (Mobile App Management, MAM) vor Datenverlusten: Daten werden nicht an ungeschützte Apps oder Speicherorte verschoben, und bei Verlust oder Diebstahl eines Geräts werden Daten gelöscht.  Diese beiden Schutzebenen sollten zusammen verwendet werden, um die Daten zu sichern und gleichzeitig dafür zu sorgen, dass mobile Mitarbeiter produktiv arbeiten können.

Ein wichtiger erster Schritt zum Schutz von Unternehmensdaten ist die Implementierung des bedingten Zugriffs, indem Sie sicherstellen, dass auf den Geräten, über die auf die Daten zugegriffen wird, Sicherheitsmaßnahmen wie starke Kennwörter und Verschlüsselung verwendet werden und die Geräte nicht per Jailbreak manipuliert wurden. Mithilfe von Microsoft Intune können Sie Bedingungen festlegen, denen die Geräte entsprechen müssen, bevor über sie auf geschäftliche E-Mails und Daten zugegriffen werden kann.

[Bedingter Zugriff](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) wird durch zwei Arten von Richtlinien bestimmt, die Sie in Intune festlegen können:
- [Kompatibilitätsrichtlinien](introduction-to-device-compliance-policies-in-microsoft-intune.md) legen die Kompatibilität eines Geräts fest. Damit werden zum Beispiel folgende Einstellungen und Bedingungen ausgewertet:
  - PIN und Kennwörter: Sie können Regeln erstellen, die Kennwörter zum Entsperren eines Geräts erforderlich machen, und die Komplexitätsanforderungen für Kennwörter sowie weitere Kennworteinstellungen festlegen.
  - Verschlüsselung: Sie können den Zugriff auf Geräte einschränken, die verschlüsselt sind.
  - Gerät wurde nicht per Jailbreak oder Rooting manipuliert: Intune kann erkennen, wenn ein Gerät per Jailbreak manipuliert wurde, und Sie können die Richtlinie so festlegen, dass der Zugriff auf solchen Geräten blockiert wird.
- [Richtlinien für den bedingten Zugriff](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) werden für einen bestimmten Dienst wie Exchange Online oder SharePoint Online konfiguriert. Für jeden Dienst können Sie definieren, auf welche Gruppen von Benutzern diese Richtlinien angewendet werden sollen. Beispielsweise können Sie sicherstellen, dass jeder Mitarbeiter der Finanzabteilung nur über registrierte und kompatible Geräte auf Unternehmens-E-Mail zugreifen kann.

Die Sicherung des Zugriffs auf Unternehmensressourcen ist nur der erste Schritt hin zum Schutz der Unternehmensdaten. Sie benötigen außerdem die Möglichkeit, die Daten zu schützen, nachdem der Zugriff über die Geräte erfolgt ist. Die Daten können jetzt kopiert, verschoben, an einem anderen Speicherort gespeichert oder mit anderen Benutzern gemeinsam verwendet werden. Intune löst dieses Problem, indem Sie durch Erstellen eines Satzes von Regeln Datenverschiebungen beschränken können. Folgende Regeln können Sie festlegen:
- Blockieren von Kopier-/Einfügevorgängen oder Verhindern einer Datenübertragung außerhalb des Arbeitskontexts.
- Verhindern der Sicherung im persönlichen Cloudspeicher, Verhindern von „Speichern unter“.
- Sichern des App-Zugriffs durch Anfordern von PIN/Kennung oder Unternehmensanmeldeinformationen.
- Festlegen, dass alle Weblinks in Intune Managed Browser geöffnet werden.

Dieser Regelsatz wird als [MAM-Richtlinien](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md) bezeichnet (Mobile App Management, Verwaltung mobiler Apps).  MAM-Richtlinien können angewendet werden, unabhängig davon, ob die Geräte, auf denen die Apps ausgeführt werden, von Ihnen verwaltet werden oder nicht.  

Sie können Ihre Unternehmensdaten mithilfe von MAM-Richtlinien auf verschiedenen Geräten schützen. Hierzu zählen Geräte, die **bei Intune registriert** sind, Geräte, die **bei einem Drittanbieter-MDM-Dienst (Mobile Device Management, Verwaltung mobiler Geräte) registriert sind und dort verwaltet werden**, oder Geräte, die **nicht bei einer MDM-Lösung registriert** sind (z. B. Privatgeräte von Mitarbeitern).

Um eine App mit einer MAM-Richtlinie zu verknüpfen, muss die App das Microsoft Intune App SDK oder das App Wrapping Tool verwenden.

In Microsoft Office-Apps beispielsweise ist das App SDK integriert. Eine vollständige Liste der unterstützten Apps finden Sie auf der Seite mit den Microsoft Intune-Anwendungspartnern im [Microsoft Intune-Katalog mit mobilen Anwendungen](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx). Wählen Sie eine App aus, um die unterstützten Szenarien, Plattformen und Informationen dazu anzuzeigen, ob die App mehrere Identitäten unterstützt.

Sie können auch [Ihre eigenen, individuellen branchenspezifischen Apps](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) für die Verwendung mit MAM-Richtlinien aktivieren.

Wenn ein Gerät verloren geht oder gestohlen wird oder der Benutzer nicht mehr für Ihr Unternehmen arbeitet, können Sie [Unternehmensdaten selektiv löschen](wipe-managed-company-app-data-with-microsoft-intune.md) und nur persönliche Daten auf dem Gerät belassen.



<!--HONumber=Oct16_HO3-->


