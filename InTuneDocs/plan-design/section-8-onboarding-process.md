---
title: Intune-Onboardingprozess | Microsoft-Dokumentation
description: "Dieser Artikel hilft Ihnen bei allen Details, die beim Onboarding einer reinen Intune-Cloudlösung in Ihrer Umgebung berücksichtigt werden müssen."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac7bd764-5365-4920-8fd0-ea57d5ebe039
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 23d40a31c43a061e0f3b1fbb05827697ca7380ac
ms.lasthandoff: 04/14/2017


---

# <a name="intune-implementation"></a>Implementierung von Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Während der Onboardingphase implementieren Sie Intune in Ihrer Produktionsumgebung. Der Implementierungsprozess besteht aus dem Einrichten und Konfigurieren von Intune und externen Abhängigkeiten (falls erforderlich), basierend auf den [Anforderungen Ihres Anwendungsfalls](section-3-determine-use-case-requirements.md), die in den vorherigen Abschnitten dieses Handbuchs behandelt wurden.

Der folgende Abschnitt enthält eine Übersicht über den Intune-Implementierungsprozess, der Anforderungen und allgemeine Aufgaben umfasst.

>[!TIP]
> Unter [Weitere Ressourcen](additional-resources.md) finden Sie weitere Informationen über den Prozess der Intune-Implementierung.

## <a name="intune-requirements"></a>Intune-Anforderungen

Die wichtigsten Anforderungen der eigenständigen Intune-Version werden unten angegeben:

-   EMS-/Intune-Abonnement

-   Office 365-Abonnement (für Office-Apps und über die MAM-Richtlinie verwaltete Apps)

-   Apple APNs-Zertifikat (zum Aktivieren der Verwaltung der iOS-Geräteplattform)

-   Azure AD Connect (zur Verzeichnissynchronisierung)

-   Intune-Connector für lokale Exchange-Umgebungen (für die Zertifizierungsstelle für Exchange lokal, falls erforderlich)

-   Intune Certificate Connector (für die SCEP-Zertifikatbereitstellung, falls erforderlich)

>[!TIP]
> Weitere Informationen zu den Anforderungen der eigenständigen Intune-Version finden Sie [hier](https://docs.microsoft.com/intune/get-started/what-to-know-before-you-start-microsoft-intune).

## <a name="intune-implementation-process"></a>Intune-Implementierungsprozess

### <a name="overview-of-implementation-tasks"></a>Übersicht über Implementierungsaufgaben

Hier sehen Sie eine Übersicht über die einzelnen Aufgaben bei der Implementierung von Intune.

#### <a name="task-1-add-intune-subscription"></a>Aufgabe 1: Hinzufügen eines Intune-Abonnements

Wie im vorherigen Abschnitt zu den Anforderungen dargestellt, ist ein EMS- oder Intune-Abonnement erforderlich. Wenn Ihre Organisation nicht über ein EMS- oder Intune-Abonnement verfügt, wenden Sie sich an Microsoft oder das Microsoft-Konto-Team, und teilen Sie Ihr Interesse am Kauf von Enterprise Mobility + Security (EMS) oder Intune mit.

-   Informationen zum [Kauf von Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-pricing).

#### <a name="task-2-add-office-365-subscription"></a>Aufgabe 2: Hinzufügen eines Office 365-Abonnements

Dieser Schritt ist optional. Wie im vorherigen Abschnitt zu den Anforderungen erwähnt, ist ein Office 365-Abonnement erforderlich, wenn Sie Exchange Online verwenden und Office Mobile-Apps mit der MAM-Richtlinie verwalten möchten. Wenn Ihre Organisation nicht über ein Office 365-Abonnement verfügt, wenden Sie sich an Microsoft oder das Microsoft-Konto-Team, und teilen Sie Ihr Interesse am Kauf von Office 365 mit.

-   Weitere Informationen zu [Office 365-Bezugsquellen](https://products.office.com/business/compare-office-365-for-business-plans).

#### <a name="task-3-add-users-groups-in-azure-ad"></a>Aufgabe 3: Hinzufügen von Benutzergruppen in Azure AD

Möglicherweise müssen Sie je nach den Anwendungsszenarien und Anforderungen Ihrer Intune-Bereitstellung Benutzer oder Sicherheitsgruppen in AD oder AAD hinzufügen. Überprüfen Sie Ihre aktuellen Benutzer- und Sicherheitsgruppen in Active Directory oder Azure Active Directory, und ermitteln Sie, ob diese vollständig Ihren Anforderungen entsprechen. Neue Benutzer- und Sicherheitsgruppen werden am häufigsten in Active Directory hinzugefügt und über Azure AD Connect in Azure Active Directory synchronisiert.

-   Weitere Informationen zum [Hinzufügen von Benutzern/Gruppen in Intune](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3).

#### <a name="task-4-assign-intune-and-office-365-user-licenses"></a>Aufgabe 4: Zuweisen von Intune- und Office 365-Benutzerlizenzen

Allen Benutzern, die für die Einführung von EMS/Intune und Office 365 vorgesehen sind, muss eine Lizenz zugewiesen werden. Die EMS-/Intune- und Office 365-Lizenzzuweisung kann im Office 365 Admin Center-Portal erfolgen.

-   Weitere Informationen zum [Zuweisen von Intune-Lizenzen](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4).

#### <a name="task-5-set-mobile-device-management-authority-to-intune"></a>Aufgabe 5: Festlegen von Intune als Autorität für die Verwaltung mobiler Geräte

Bevor Sie mit dem Einrichten, Konfigurieren, Verwalten und Registrieren von Geräten mit Intune beginnen können, müssen Sie die Autorität für die Geräteverwaltung auf Intune festlegen. Die Aufgabe zum Festlegen der Autorität für die Geräteverwaltung wird im Intune-Verwaltungsportal im Administratorarbeitsbereich durchgeführt.

-   Weitere Informationen zum [Festlegen der Autorität für die Geräteverwaltung](https://docs.microsoft.com/intune/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority).

#### <a name="task-6-enable-device-platforms"></a>Aufgabe 6: Aktivieren von Geräteplattformen

Standardmäßig sind in der Intune-Verwaltungskonsole die meisten Plattformen aktiviert, mit Ausnahme von Apple-Geräten (iOS und Mac). Damit iOS-Geräte registriert und in Intune verwaltet werden können, muss die Geräteplattform aktiviert sein. Das Aktivieren der iOS-Geräteplattform besteht aus drei Schritten: Erstellen und Herunterladen des APNs-Zertifikats sowie Hochladen des APNs-Zertifikats in Intune.

-   Weitere Informationen zur [Einrichtung der iOS- und Mac-Geräteverwaltung.](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)

#### <a name="task-7-add-and-deploy-terms-and-conditions-policies"></a>Aufgabe 7: Hinzufügen und Bereitstellen von Richtlinien für Geschäftsbedingungen

Microsoft Intune unterstützt das Hinzufügen und Bereitstellen von Richtlinien für Geschäftsbedingungen. Richtlinien für Geschäftsbedingungen werden im Intune-Verwaltungsportal im Richtlinienarbeitsbereich hinzugefügt und bereitgestellt. Fügen Sie Richtlinien für Geschäftsbedingungen nach Bedarf hinzu, und stellen Sie sie basierend auf den Anwendungsfällen und Anforderungen Ihrer Intune-Bereitstellung für Zielgruppen bereit.

-   Weitere Informationen zum [Hinzufügen und Bereitstellen von Richtlinien für Geschäftsbedingungen](https://docs.microsoft.com/intune/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune).

#### <a name="task-8-add-and-deploy-configuration-policies"></a>Aufgabe 8: Hinzufügen und Bereitstellen von Konfigurationsrichtlinien

Microsoft Intune unterstützt das Hinzufügen und Bereitstellen zweier Typen von Konfigurationsrichtlinien: allgemein und benutzerdefiniert. Konfigurationsrichtlinien werden im Intune-Verwaltungsportal im Richtlinienarbeitsbereich hinzugefügt und bereitgestellt. Fügen Sie Konfigurationsrichtlinien nach Bedarf hinzu, und stellen Sie sie basierend auf den Anwendungsfällen und Anforderungen Ihrer Intune-Bereitstellung für Zielgruppen bereit.

-   Weitere Informationen zum [Hinzufügen und Bereitstellen von Konfigurationsrichtlinien](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).

#### <a name="task-9-add-and-deploy-resource-profiles"></a>Aufgabe 9: Hinzufügen und Bereitstellen von Ressourcenprofilen

Microsoft Intune unterstützt E-Mail-, WLAN- und VPN-Profile. Profile werden im Intune-Verwaltungsportal im Richtlinienarbeitsbereich hinzugefügt und bereitgestellt. Fügen Sie E-Mail-, WLAN- oder VPN-Profile nach Bedarf hinzu, und stellen Sie sie basierend auf den Anwendungsfällen und Anforderungen Ihrer Intune-Bereitstellung für Zielgruppen bereit.

-   Weitere Informationen finden Sie unter [Aktivieren des Zugriffs auf Unternehmensressourcen mit Intune](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune).

#### <a name="task-10-add-and-deploy-apps"></a>Aufgaben 10: Hinzufügen und Bereitstellen von Apps

Microsoft Intune unterstützt die Bereitstellung von Web-Apps, branchenspezifischen Apps und Apps aus öffentlichen Stores. Darüber hinaus wird das Verwalten von Apps unterstützt, bei denen das Intune-SDK durch die Zuordnung von MAM-Richtlinien integriert wurde. Apps werden im Intune-Verwaltungsportal im App-Arbeitsbereich hinzugefügt und bereitgestellt. MAM-Richtlinien werden im Intune-Verwaltungsportal im Richtlinienarbeitsbereich hinzugefügt und bereitgestellt. Fügen Sie Apps nach Bedarf hinzu, und stellen Sie sie basierend auf den Anwendungsfällen und Anforderungen Ihrer Intune-Bereitstellung für Zielgruppen bereit.

-   Weitere Informationen zum [Hinzufügen und Bereitstellen von Anwendungen](https://docs.microsoft.com/intune/deploy-use/deploy-apps).

#### <a name="task-11-add-and-deploy-compliance-policies"></a>Aufgabe 11: Hinzufügen und Bereitstellen von Konformitätsrichtlinien

Microsoft Intune unterstützt Konformitätsrichtlinien. Konformitätsrichtlinien werden im Intune-Verwaltungsportal im Richtlinienarbeitsbereich hinzugefügt und bereitgestellt. Fügen Sie Konformitätsrichtlinien nach Bedarf hinzu, und stellen Sie sie basierend auf den Anwendungsfällen und Anforderungen Ihrer Intune-Bereitstellung für Zielgruppen bereit.

-   Weitere Informationen zu [Konformitätsrichtlinien](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

#### <a name="task-12-enable-conditional-access-policies"></a>Aufgabe 12: Aktivieren von Richtlinien für bedingten Zugriff

Microsoft Intune unterstützt den bedingten Zugriff für Exchange Online und lokal, SharePoint Online, Skype for Business Online und Dynamics CRM Online. Richtlinien für bedingten Zugriff werden im Intune-Verwaltungsportal im Richtlinienarbeitsbereich aktiviert. Aktivieren und konfigurieren Sie den bedingten Zugriff nach Bedarf basierend auf den [Anwendungsfällen und Anforderungen Ihrer Intune-Bereitstellung](section-3-determine-use-case-requirements.md).

-   Weitere Informationen zum [bedingten Zugriff](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

#### <a name="task-13-enroll-devices"></a>Aufgabe 13: Registrieren von Geräten

Intune unterstützt die Geräteplattformen iOS, Mac OS, Android, Windows Desktop und Windows Mobile. Registrieren Sie mobile Geräteplattformen nach Bedarf basierend auf den Anwendungsfällen und Anforderungen Ihrer Intune-Bereitstellung.

-   Weitere Informationen zum [Registrieren von Geräten](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune).

>[!TIP]
> Weitere Informationen zum Prozess der Intune-Implementierung finden Sie in diesem [Intune-Sitzungsmodul der Microsoft Virtual Academy](https://mva.microsoft.com/training-courses/deploying-microsoft-enterprise-mobility-suite-16408?l=PPWNoZxvD_1404778676).

## <a name="next-section"></a>Nächster Abschnitt

Der nächste Abschnitt enthält Hinweise auf das [Testen und Überprüfen Ihrer Intune-Bereitstellung](section-9-test-and-validation.md).

