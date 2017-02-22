---
title: Was ist bedingter Zugriff? | Intune in Azure (Vorschau) | Microsoft Docs
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie Bedingungen festlegen, die Benutzer und Geräte erfüllen müssen, um Zugriff auf Unternehmensressourcen in der Vorschau von Microsoft Intune in Azure zu erhalten."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 41931f64db969c82f79e007c4be9e68b7caf4ce9
ms.openlocfilehash: 20696fb2dc0126aa224e779738cedb4f95f666e8


---

# <a name="what-is-conditional-access"></a>Was ist bedingter Zugriff?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


In diesem Thema wird der bedingte Zugriff für Enterprise Mobility + Security beschrieben. Anschließend werden die Funktionen in Intune für den bedingten Zugriff erläutert.

Beim bedingten Zugriff in Enterprise Mobility + Security (EMS) werden die Leistung von Azure Active Directory Premium und Windows Intune genutzt, damit Sie die Sicherheit Ihrer Unternehmensdaten optimal steuern können, während Ihre Mitarbeiter gleichzeitig alle Möglichkeiten erhalten, ihre Arbeit von jedem Gerät aus bestmöglich zu erledigen.

Mithilfe des bedingten Zugriffs können Sie Bedingungen definieren, die den Zugriff auf Ihre Unternehmensdaten basierend auf dem Ort, dem Geräte- und Benutzerstatus und der Vertraulichkeit der Anwendung beschränken.

Aus der Geräteperspektive stellen Intune und Azure Active Directory zusammen sicher, dass nur verwaltete und konforme Geräte Zugriff auf E-Mail- und Office 365-Dienste erhalten. Sie können beispielsweise in Azure Active Directory eine Richtlinie festlegen, die nur Computern, die der Domäne angehören, oder mobilen Geräten, die in einer MDM-Anwendung wie Intune verwaltet werden, den Zugriff auf Office 365-Dienste erlaubt. Mithilfe von Intune können Sie ein Gerätekonformitätsprofil festlegen, das den Konformitätsstatus des Geräts auswertet. Der Konformitätsstatus wird an Azure Active Directory gemeldet, um die Richtlinie in Azure Active Directory zu erzwingen, wenn der Benutzer versucht, auf Ihre Unternehmensressourcen zuzugreifen. Informationen zur Gerätekonformität in Intune finden Sie unter [Was ist die Gerätekonformität?](/intune-azure/set-device-compliance/what-is-device-compliance).

Der bedingte Zugriff für Cloud-Apps, wie Exchange Online, kann über Azure Active Directory konfiguriert werden. Weitere Informationen finden Sie in [diesem Artikel](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-conditional-access-azure-portal).

## <a name="on-premises-conditional-access-in-intune"></a>Lokaler bedingter Zugriff in Intune

Bedingter Zugriff kann in Intune zum Erlauben oder Sperren des Zugriffs auf **Exchange lokal** basierend auf der Geräteverwaltung und -registrierung verwendet werden.

Zur Bewertung der Gerätekonformität werden Einstellungen für Gerätekonformitätsprofile verwendet. Für den bedingten Zugriff wird diese Auswertung genutzt, um den Zugriff auf Exchange lokal zu erlauben oder zu sperren. Wenn der bedingte Zugriff in Kombination mit einem Gerätekonformitätsprofil verwendet wird, erhalten nur konforme Geräte Zugriff auf den Exchange lokal. Sie können für eine präzisere Steuerung erweiterte Einstellungen für den bedingten Zugriff festlegen: Zulassen oder Sperren bestimmter Plattformen oder sofortige Sperrung von Geräten, die nicht von Intune verwaltet werden.

Das Gerätekonformitätsprofil und der bedingte Zugriff werden dem Benutzer zugewiesen. Jedes Gerät, das der Benutzer für den Zugriff auf die Exchange lokal verwendet, wird auf Konformität überprüft. Bedenken Sie, dass für den Benutzer, der das Gerät verwendet, ein Konformitätsprofil bereitgestellt werden muss, damit das Gerät hinsichtlich der Konformität bewertet werden kann. Wenn keine Konformitätsrichtlinie für den Benutzer bereitgestellt wird, wird das Gerät als konform behandelt, und es werden keine Zugriffsbeschränkungen angewendet.

Wenn Geräte die Bedingungen nicht erfüllen, erhält der Benutzer Anweisungen zum Registrieren des Geräts und zum Beheben des Problems, das die Konformität des Geräts verhindert.

## <a name="next-steps"></a>Nächste Schritte

[Erstellen einer Richtlinie für den bedingten Zugriff auf Exchange lokal](create-conditional-access-policy-for-exchange-on-premises.md)

[Konfigurieren des bedingten Zugriffs in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-conditional-access-azure-portal)



<!--HONumber=Feb17_HO1-->


