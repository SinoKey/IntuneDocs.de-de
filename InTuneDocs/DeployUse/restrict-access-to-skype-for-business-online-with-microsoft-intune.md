---
title: Verwalten des Zugriffs auf Skype for Business
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1b2d7125-f63f-43cf-ac1e-94fbedf2a7e8
author: karthikaraman
---
# Verwalten des Zugriffs auf Skype for Business
Verwenden Sie die Richtlinie für bedingten Zugriff für  **Skype for Business Online** zum Verwalten des Zugriffs auf Skype für Business Online anhand von Bedingungen, die Sie angeben.

Wenn Sie ein bestimmten Benutzer versucht, Skype for Business Online auf ihrem Gerät zu verwenden, tritt die folgende Bewertung:

![](../Image/ConditionalAccess_SkypeforBusiness.png)

## Voraussetzungen

-   Moderne Authentifizierung für Skype for Business Online zu aktivieren. Füllen Sie diese [Verbinden](https://connect.microsoft.com/office/Survey/NominationSurvey.aspx?SurveyID=17299&ProgramID=8715) für die Anwendung moderner Authentifizierung registriert werden.
-  Alle Ihre Endbenutzer müssen Skype for Business Online verwenden. Wenn Sie eine Bereitstellung mit Skype for Business Online und Skype for Business lokalen verfügen, wird Richtlinie für bedingten Zugriff für Endbenutzer nicht angewendet werden.

    Müssen das Gerät, das Zugriff auf die Skype für Business Online benötigt:

-   Werden Sie ein Android oder iOS-Gerät.

-   Mit registriert werden. [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]

-   Es muss mit allen festgelegten Kompatibilitätsrichtlinien von [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] kompatibel sein.


Der Gerätestatus wird in Azure Active Directory gespeichert, die Anwendung gewährt oder blockiert den Zugriff, basierend auf den von Ihnen angegebenen.

Wenn eine Bedingung nicht erfüllt wird, erhält der Benutzer bei der Anmeldung die folgenden Meldungen:

-   Wenn das Gerät nicht bei [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]oder in Azure Active Directory registriert ist, wird eine Meldung mit Anweisungen zum Installieren der Unternehmensportal-App und zum Registrieren des Geräts angezeigt.

-   Wenn das Gerät nicht kompatibel ist, wird eine Meldung angezeigt, die den Benutzer anweist die [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] Unternehmensportal-Website oder Unternehmensportal-app, wo sie Informationen über das Problem und dessen Lösung finden können.

## Konfigurieren des bedingten Zugriffs für Skype für Business Online

### Schritt 1: Konfigurieren von Active Directory-Sicherheitsgruppen
Bevor Sie beginnen, konfigurieren Sie Azure Active Directory-Sicherheitsgruppen für die bedingte Zugriffsichtlinie. Sie können konfigurieren, dass diese Gruppen in der **Office 365 Administrationscenter**. Die Gruppen beinhalten die Benutzer, für die die Richtlinie gelten soll oder die davon ausgeschlossen sind. Bei Benutzern, für die eine Richtlinie gelten soll, muss jedes von ihnen verwendete Gerät die Richtlinie erfüllen, damit sie auf Ressourcen zugreifen können.

Sie können zwei Arten von Gruppen, die für die Skype for Business-Richtlinie verwendet angeben:

-   **Zielgruppen** : Gruppen von Benutzern, für die die Richtlinie gelten soll.

-   **Ausgenommene Gruppen** : Gruppen von Benutzern, die von der Richtlinie ausgenommen sind (optional).

Benutzer, die in beiden Gruppen enthalten sind, werden von der Richtlinie ausgenommen.

### Schritt 2: Konfigurieren und Bereitstellen einer Kompatibilitätsrichtlinie
Stellen Sie sicher, dass Sie beim Erstellen und Bereitstellen einer Konformitätsrichtlinie für alle Geräte, denen die Skype for Business Online-Richtlinie gelten soll.

> [!NOTE]
> Wenn Kompatibilitätsrichtlinien für [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] -Gruppen bereitgestellt werden, gelten bedingte Zugriffsrichtlinien für Azure Active Directory-Sicherheitsgruppen.

Ausführliche Informationen zum Konfigurieren der Konformitätsrichtlinien finden Sie unter [Verwalten von gerätekonformitätsrichtlinien für Microsoft Intune](../Topic/Manage-device-compliance-policies-for-Microsoft-Intune.md).

> [!IMPORTANT]
> Wenn Sie keine Konformitätsrichtlinie bereitgestellt haben und dann die Skype for Business Online-Richtlinie aktivieren, werden alle Zielgeräte Zugriff gewährt, wenn sie in Intune registriert sind.

Wenn Sie soweit sind, fahren Sie mit **Schritt 3**fort.

### <a name="BKMK_OneDrive"></a>Schritt 3: Konfigurieren der Skype for Business Online-Richtlinie
Konfigurieren Sie anschließend die Richtlinie so, dass nur verwaltete und kompatible Geräte Skype für Business Online zugreifen können. Diese Richtlinie wird in Azure Active Directory gespeichert.

#### <a name="bkmk_spopolicy"></a>

1.  In der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com), klicken Sie auf **Richtlinie** & Gt; **Bedingter Zugriff** & Gt; **Skype for Business Online-Richtlinie**.

![conditional_access_SFBPolicy](/Image/conditional_access_SFBPolicy.png)

2.  Wählen Sie **Richtlinie für bedingten Zugriff aktivieren**.

3.  Unter **Anwendungszugriff**, die Möglichkeit, die Richtlinie für bedingten Zugriff zu übernehmen:

    -   **iOS**

    -   **Android**

4.  Klicken Sie unter **Zielgruppen**auf **Ändern** , um die Active Directory-Sicherheitsgruppen auszuwählen, für die die Richtlinie gelten soll. Sie können dies für alle Benutzer oder nur eine ausgewählte Gruppe von Benutzern als Ziel auswählen.

5.  Klicken Sie unter **Ausgenommene Gruppen**optional auf **Ändern** , um die Active Directory-Sicherheitsgruppen auszuwählen, die von dieser Richtlinie ausgenommen werden.

6.  Klicken Sie abschließend auf **Speichern**.

Sie haben nun Zugangsberechtigung für Skype for Business Online konfiguriert. Die Richtlinie für bedingten Zugriff wird sofort wirksam und muss nicht explizit bereitgestellt werden.


## Überwachen der Richtlinien für Konformität und bedingten Zugriff
Im Arbeitsbereich **Gruppen** können Sie den Status beim bedingten Zugriff Ihrer Geräte anzeigen.

Wählen Sie eine beliebige Gruppe von Mobilgeräten und dann auf der Registerkarte **Geräte** einen der folgenden **Filter**aus:

* **Geräte, die nicht bei AAD registriert sind** – diese Geräte werden von Skype for Business Online blockiert.

* **Nicht kompatible Geräte** – diese Geräte werden von Skype for Business Online blockiert.

* **Geräte, die bei AAD registriert und kompatibel sind** – diese Geräte können Skype for Business Online zugreifen.

### Weitere Informationen:
[Verwalten des Zugriffs auf e-Mail und Office 365-Diensten](Manage-access-to-email-and-SharePoint-with-Microsoft-Intune.md)


<!--HONumber=Mar16_HO4-->


