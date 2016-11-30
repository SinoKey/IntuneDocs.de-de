---
title: "Beschränken des Zugriffs auf E-Mail- und Office 365-Dienste | Microsoft Intune"
description: "In diesem Thema wird beschrieben, wie Sie bedingten Zugriff einrichten, damit nur kompatible Geräte auf Unternehmens-E-Mail und -daten in SharePoint Online und anderen Diensten zugreifen können."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c564d292-b83b-440d-bf08-3f5b299b7a5e
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 027e7e56e6f7d3a604336e0465f688af514c69e6
ms.openlocfilehash: 68fc47ba9f63f2ba05abae1f0e5ae5c6b3dca463


---

# <a name="restrict-access-to-email-o365-and-other-services-with-microsoft-intune"></a>Beschränken des Zugriffs auf E-Mail, O365 und andere Dienste mit Microsoft Intune
Sie können den Zugriff auf die E-Mail- und Office 365-Dienste Ihres Unternehmens mithilfe des bedingten Zugriffs in Intune beschränken. Mithilfe der Intune-Funktion für den bedingten Zugriff können Sie sicherstellen, dass der Zugriff auf die E-Mail- und Office 365-Dienste Ihres Unternehmens auf Geräte beschränkt ist, die den von Ihnen festgelegten Regeln entsprechen.
## <a name="how-does-conditional-access-work"></a>Funktionsweise des bedingten Zugriffs
Zur Bewertung der Gerätekompatibilität werden Einstellungen für Kompatibilitätsrichtlinien verwendet. Die Richtlinie für bedingten Zugriff verwendet diese Bewertung, um den Zugriff auf einen bestimmten Dienst zuzulassen oder zu beschränken. Wenn eine Richtlinie für bedingten Zugriff in Kombination mit einer Kompatibilitätsrichtlinie verwendet wird, erhalten nur kompatible Geräte Zugriff auf den Dienst. Die Richtlinien für Konformität und bedingten Zugriff werden dem Benutzer bereitgestellt. Jedes Gerät, das der Benutzer zum Zugriff auf die Dienste verwendet, wird auf die Einhaltung der Richtlinien überprüft.

Bedenken Sie, dass für den Benutzer, der das Gerät verwendet, eine Kompatibilitätsrichtlinie bereitgestellt werden muss, damit das Gerät hinsichtlich der Kompatibilität bewertet werden kann.
Wenn keine Kompatibilitätsrichtlinie für den Benutzer bereitgestellt wird, wird das Gerät als kompatibel behandelt, und es werden keine Zugriffsbeschränkungen angewendet.

Wenn Geräte die in den Richtlinien festgelegten Bedingungen nicht erfüllen, erhält der Benutzer Anweisungen zum Registrieren des Geräts und zum Beheben des Problems, das die Konformität des Geräts verhindert.

Ein typischer Ablauf des bedingten Zugriffs:

![Das Diagramm veranschaulicht die Entscheidungspunkte, mit denen ermittelt wird, ob ein Gerät Zugriff auf einen Dienst erhält oder blockiert wird](../media/ConditionalAccess4.png)

## <a name="how-to-configure-conditional-access"></a>So konfigurieren Sie den bedingten Zugriff
Verwenden Sie den bedingten Zugriff zur Verwaltung des Zugriffs auf Microsoft **Exchange lokal**, **Exchange Online**, **Exchange Online Dedicated**, **SharePoint Online** und **Skype for Business Online**.

Um den bedingten Zugriff einzurichten, konfigurieren Sie eine Richtlinie für die Gerätekompatibilität und eine Richtlinie für bedingten Zugriff.

Die Kompatibilitätsrichtlinie enthält Einstellungen wie z. B. Kennung, Verschlüsselung und Informationen dazu, ob ein Gerät per Jailbreak manipuliert wurde. Das Gerät muss diesen Regeln entsprechen, um als kompatibel anerkannt zu werden.

Sie können eine Richtlinie für bedingten Zugriff festlegen, um den Zugriff anhand folgender Aspekte zu beschränken:
- Der Status der Gerätekompatibilität.
- Die auf dem Gerät ausgeführte Plattform.
- Die Art von Apps, die für den Zugriff auf die Dienste verwendet werden.

Im Gegensatz zu anderen Intune-Richtlinien stellen Sie Richtlinien für bedingten Zugriff nicht bereit. Stattdessen konfigurieren Sie die Richtlinie und wählen die Benutzer aus, für die die Richtlinie gelten soll. Dann wird die Richtlinie auf diese Benutzer angewendet. Bei Benutzern, für die eine Richtlinie gelten soll, muss jedes von ihnen verwendete Gerät die Richtlinie erfüllen, damit sie auf Ressourcen zugreifen können.


## <a name="next-steps"></a>Nächste Schritte
1. [Informationen zur Richtlinie für die Gerätekompatibilität und ihrer Funktionsweise](introduction-to-device-compliance-policies-in-microsoft-intune.md)

2. [Erstellen einer Konformitätsrichtlinie](create-a-device-compliance-policy-in-microsoft-intune.md)

2.  Erstellen Sie eine Richtlinie für bedingten Zugriff für einen der folgenden Dienste:
> [!div class="op_single_selector"]
  - [Bedingte Zugriffsrichtlinie für Exchange Online erstellen](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Bedingte Zugriffsrichtlinie für Exchange Online lokal erstellen](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Bedingte Zugriffsrichtlinie für Exchange Online Dedicated (neu) erstellen](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Bedingte Zugriffsrichtlinie für Exchange Online Dedicated (älter) erstellen](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Bedingte Zugriffsrichtlinie für SharePoint Online erstellen](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  - [Bedingte Zugriffsrichtlinie für Skype for Business erstellen](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  - [Erstellen einer bedingten Zugriffsrichtlinie für Dynamics CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Nov16_HO2-->


