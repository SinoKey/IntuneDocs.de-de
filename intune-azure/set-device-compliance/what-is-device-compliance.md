---
title: "Gerätekompatibilität"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): In diesem Thema erfahren Sie etwas über die Gerätekonformität in Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a916fa0d-890d-4efb-941c-7c3c05f8fe7c
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: b245dac28f88e7eab70dfa9d759b15e155f8a7df


---

# <a name="what-is-device-compliance-in-intune-azure-preview"></a>Was ist die Gerätekonformität in Intune in Azure (Vorschau)?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Um Unternehmensdaten zu schützen, müssen Sie sicherstellen, dass die Geräte, die für den Zugriff auf Unternehmens-Apps und Daten verwendet werden, bestimmten Regeln entsprechen. Diese Regeln könnten die Verwendung einer PIN für den Zugriff auf Geräte und das Verschlüsseln von Daten, die auf Geräten gespeichert sind, einschließen. Eine Gruppe solcher Regeln wird als **Konformitätsrichtlinie** bezeichnet.

##  <a name="how-should-i-use-a-device-compliance-policy"></a>Wie verwende ich Gerätekonformitätsrichtlinien?
Sie können Konformitätsrichtlinien mit dem bedingten Zugriff verwenden, um nur Geräte zuzulassen, die Konformitätsrichtlinienregeln für den Zugriff auf E-Mail und andere Dienste entsprechen.

Sie können Konformitätsrichtlinien auch unabhängig vom bedingten Zugriff nutzen.
Bei unabhängiger Nutzung von Kompatibilitätsrichtlinien werden die Zielgeräte ausgewertet und mit ihrem Kompatibilitätsstatus gemeldet. Sie können beispielsweise einen Bericht dazu erstellen, wie viele Geräte nicht verschlüsselt sind oder per Jailbreak oder Rootzugriff manipuliert wurden. Aber wenn Sie Kompatibilitätsrichtlinien unabhängig nutzen, gelten keine Zugriffsbeschränkungen für Unternehmensressourcen.

Sie stellen Konformitätsrichtlinien für Benutzer bereit. Wenn Sie eine Kompatibilitätsrichtlinie für einen Benutzer bereitstellen, wird die Kompatibilität der Geräte des Benutzers überprüft. Informationen darüber, wie lange es dauert, bis eine Richtlinie für mobile Geräte nach der Bereitstellung der Richtlinie abgerufen wird, finden Sie unter „Verwalten von Einstellungen und Features auf Ihren Geräten“.

##  <a name="concepts"></a>Konzepte
Es folgen einige Begriffe und Konzepte, die für das Verwenden von Konformitätsrichtlinien hilfreich sind.

### <a name="compliance-requirements"></a>Konformitätsanforderungen
Konformitätsanforderungen sind im Wesentlichen Regeln, mit denen Sie z.B. eine Geräte-PIN erzwingen oder angeben können, ob Verschlüsselung für die Konformitätsrichtlinie erforderlich ist.

<!---### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be non-compliant, an email with noncompliant notification is sent to the user.

-   3 days after initial noncompliance state, a follow up reminder is sent to the user.

-   5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

-   7 days after initial noncompliance state, access to company resources is blocked. This requires that you have conditional access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement conditional access policies in addition to compliance policies in order for access to company resources to be blocked.--->

##  <a name="differences-between-the-classic-intune-admin-console-and-intune-in-the-azure-portal"></a>Unterschiede zwischen der klassischen Intune-Verwaltungskonsole und Intune im Azure-Portal


Wenn Sie bereits die klassische Intune-Verwaltungskonsole verwendet haben, werden Ihnen die folgenden Unterschiede beim Umstieg auf den neuen Gerätekonformitäts-Workflow im Azure-Portal auffallen:


-   In Azure-Portal werden die Konformitätsrichtlinien separat für jede unterstützte Plattform erstellt. In der Intune-Verwaltungskonsole wurde eine Konformitätsrichtlinie für alle unterstützten Plattformen verwendet.


<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="next-steps"></a>Nächste Schritte

[Erste Schritte mit Konformitätsrichtlinien](get-started-with-device-compliance.md)


<!---### See also

Conditional access--->



<!--HONumber=Feb17_HO3-->


