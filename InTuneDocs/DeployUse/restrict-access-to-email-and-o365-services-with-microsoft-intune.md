---
title: Einschränken des Zugriffs auf e-Mail und Office 365-Diensten | Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: c564d292-b83b-440d-bf08-3f5b299b7a5e
author: karthikaraman
---
# Einschränken des Zugriffs auf e-Mail und Office 365-Diensten mit Microsoft Intune
Sie können den Zugriff auf Ihre geschäftlichen e-Mails und den Office 365-Diensten wie SharePoint und Skype for Business einschränken. Intune conditional Access-Funktion können Sie sicherstellen, dass nur die Geräte, die den Regeln entsprechen, die Sie festlegen des Zugriffs auf Unternehmens-e-Mail und Ressourcen zulässig sind.
## Wie funktioniert die Bedingter Zugriff?
Richtlinien für Konformität werden verwendet, um den kompatiblen Status des Geräts zu evaluieren, und die Richtlinien für bedingten Zugriff können Sie die Einschränkungen auf e-Mail und Office 365-Dienste wie SharePoint Online und Skype for Business zu angeben. Wenn die Richtlinie für bedingten Zugriff für die Compliance-Richtlinien verwendet wird, nur kompatible Geräte kann auf den Dienst zuzugreifen. Die Geräte müssen eine Konformitätsrichtlinie bereitgestellt wird, in der Reihenfolge für die Kompatibilität bewertet werden.
Wenn keine Konformitätsrichtlinie für ein Gerät bereitgestellt wird, dann alle anwendbaren bedingte Zugriffsrichtlinien behandelt das Gerät als konform und uneingeschränkt Zugriff angewendet werden.

Im Gegensatz zu anderen Intune-Richtlinien denen Sie Richtlinien für bedingten Zugriff nicht bereitgestellt. Stattdessen konfigurieren Sie diese einmalig; anschließend gelten sie für alle Zielbenutzer.


Wenn Geräte die von Ihnen konfigurierten Bedingungen nicht erfüllen, erhält der Benutzer Anweisungen zum Registrieren des Geräts und zum Beheben des Problems, das die Konformität des Geräts verhindert.

Ein typischer Ablauf für bedingten Zugriff:

![](./media/ConditionalAccess4.png)

## Wie sollte ich bedingten Zugriff konfigurieren?
Verwenden Sie bedingten Zugriff zum Verwalten des Zugriffs auf Microsoft **auf lokales Exchange**, **Exchange Online**, **Exchange Online Dedicated**,  **SharePoint Online** und **Skype for Business Online**.

Um bedingten Zugriff für den Zugriff auf e-Mail und Office 365-Diensten einschränken einzurichten, konfigurieren Sie eine Geräte-Compliance-Richtlinie und eine Richtlinie für bedingten Zugriff.

Die Compliance-Richtlinien weist Einstellungen wie Kennung, Verschlüsselung, ob ein Gerät gehackt wird, die ein Gerät erfüllen muss, damit kompatibel sein.  

Richtlinie für bedingten Zugriff können Sie einschränken, den Zugriff auf Dienste wie Exchange und SharePoint Online basierend auf der Gerätekompatibilität, den Typ von apps, die verwendet werden soll, den Zugriff. Richtlinie für bedingten Zugriff können Sie die Richtlinie auf Azure Active Directory-Benutzer Sicherheitsgruppen anwenden, und geben Sie Verwalten von Geräten, die nicht von Microsoft Intune unterstützt werden.  


## Nächste Schritte
1.  [Erstellen einer Konformitätsrichtlinie](create-a-device-compliance-policy-in-microsoft-intune.md)

2.  Erstellen Sie eine Richtlinie für bedingten Zugriff für eines der folgenden:
> [! Div-Klasse "Op_single_selector" =]
- [Erstellen einer Richtlinie für bedingten Zugriff für Exchange Online] (Zugriff beschränken To-exchange-online-with-microsoft-intune.md)
- [Erstellen Sie eine Richtlinie für bedingten Zugriff für Exchange lokal](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
- [Erstellen einer Richtlinie für bedingten Zugriff für neue Exchange Online Dedicated] (Zugriff beschränken To-new-exchange-online-dedicated-with-microsoft-intune.md)
- [Erstellen einer Richtlinie für bedingten Zugriff für ältere Exchange Online Dedicated] (Zugriff beschränken To-legacy-exchange-online-dedicated-with-microsoft-intune.md)
- [Erstellen der Richtlinie für bedingten Zugriff für SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
- [Erstellen Sie Richtlinie für bedingten Zugriff für Skype for Business Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)


<!--HONumber=Mar16_HO4-->


