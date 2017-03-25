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
ms.sourcegitcommit: cddeb6bf854b9ffbbc1744d5d164c8ceea34ff49
ms.openlocfilehash: 7d5a1859ef1a373ce424dd4f351fc137c6052fb7
ms.lasthandoff: 03/10/2017


---

# <a name="what-is-device-compliance-in-intune-azure-preview"></a>Was ist die Gerätekonformität in Intune in Azure (Vorschau)?

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Gerätekompatibilitätsrichtlinien in Intune definieren die Regeln und Einstellungen, denen ein Gerät entsprechen muss, um die Kompatibilitätsanforderungen von Intune-Richtlinien sowie von Richtlinien für den bedingten EMS-Zugriff zu erfüllen. Mithilfe von Kompatibilitätsrichtlinien können Sie auch Kompatibilitätsprobleme mit Geräten überwachen und beheben. 

Diese Regeln umfassen Folgendes:

- Verwendung eines Kennworts für den Gerätezugriff
- Verschlüsselung
- Ermittlung, ob das Gerät mit Jailbreak oder Rooting manipuliert wurde
- Mindestens erforderliche Betriebssystemversion
- Maximal zulässige Betriebssystemversion
- Vorgabe, dass das Gerät maximal die Mobile Threat Defense-Stufe aufweisen darf

<!---##  Concepts
Following are some terms and concepts that are useful to understanding how to use compliance policies.

### Device compliance requirements
Compliance requirements are essentially rules like requiring a device PIN or encryption that you can specify as required or not required for a compliance policy.

### Actions for noncompliance

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

##  <a name="how-should-i-use-a-device-compliance-policy"></a>Wie verwende ich Gerätekonformitätsrichtlinien?

### <a name="using-ems-conditional-access"></a>Verwenden des bedingten EMS-Zugriffs
Sie können die Kompatibilitätsrichtlinie mit dem bedingten EMS-Zugriff verwenden, um den Zugriff auf E-Mails und andere Unternehmensressourcen nur für Geräte zuzulassen, die mindestens eine Regel der Gerätekompatibilitätsrichtlinie erfüllen.

### <a name="not-using-ems-conditional-access"></a>Verzichten auf die Verwendung des bedingten EMS-Zugriffs
Gerätekompatibilitätsrichtlinien können auch unabhängig vom bedingten EMS-Zugriff verwendet werden.
Bei unabhängiger Nutzung von Kompatibilitätsrichtlinien werden die Zielgeräte ausgewertet und mit ihrem Kompatibilitätsstatus gemeldet. So können Sie beispielsweise einen Bericht dazu erstellen, wie viele Geräte nicht verschlüsselt sind oder mit Jailbreak oder Rootzugriff manipuliert wurden. Aber wenn Sie Kompatibilitätsrichtlinien unabhängig nutzen, gelten keine Zugriffsbeschränkungen für Unternehmensressourcen.

Sie stellen Konformitätsrichtlinien für Benutzer bereit. Wenn Sie eine Kompatibilitätsrichtlinie für einen Benutzer bereitstellen, wird die Kompatibilität der Geräte des Benutzers überprüft. Informationen darüber, wie lange es dauert, bis eine Richtlinie für mobile Geräte nach der Bereitstellung der Richtlinie abgerufen wird, finden Sie unter „Verwalten von Einstellungen und Features auf Ihren Geräten“.

##  <a name="intune-classic-admin-console-vs-intune-azure-preview-portal"></a>Gegenüberstellung der klassischen Intune-Verwaltungskonsole und des Intune Azure-Vorschauportals

Falls Sie bereits die klassische Intune-Verwaltungskonsole verwendet haben, beachten Sie beim Umstieg auf den neuen Gerätekompatibilitätsrichtlinien-Workflow des Azure-Portals die folgenden Unterschiede:

-   In Azure-Portal werden die Konformitätsrichtlinien separat für jede unterstützte Plattform erstellt. In der Intune-Verwaltungskonsole wurde eine Konformitätsrichtlinie für alle unterstützten Plattformen verwendet.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="next-steps"></a>Nächste Schritte

[Erste Schritte mit der Gerätekonformität in der Vorschau von Intune in Azure](get-started-with-device-compliance.md)


<!---### See also

Conditional access--->

