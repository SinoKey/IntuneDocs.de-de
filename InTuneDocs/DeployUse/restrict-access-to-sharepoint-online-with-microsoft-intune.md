---
title: Verwalten des Zugriffs auf SharePoint Online mit Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: b088e5a0-fd4a-4fe7-aa49-cb9c8cfb1585
author: karthikaraman
---
# Verwalten des Zugriffs auf SharePoint Online mit Microsoft Intune
Nutzen Sie die [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)]**SharePoint Online** zum Verwalten des Zugriffs auf OneDrive for Business-Dateien in SharePoint Online basierend auf von Ihnen angegebenen Bedingungen.

Wenn ein bestimmten Benutzer versucht, mit einer unterstützten App wie z. B. OneDrive auf seinem Gerät eine Verbindung mit einer Datei herzustellen, erfolgt die folgende Auswertung:

![](../Image/ConditionalAccess8-6.png)

Zur Verbindung mit den erforderlichen Dateien müssen das Gerät:

-   Es muss bei [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] oder einem in die Domäne eingebundenen PC registriert sein.

-   Es muss in Azure Active Directory registriert sein (dies erfolgt automatisch bei der Registrierung des Geräts in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]).

    Für die Domäne eingebundenen PC müssen Sie es so eingerichtet [automatisch registrieren](https://azure.microsoft.com/en-us/documentation/articles/active-directory-conditional-access-automatic-device-registration/) mit Azure Active Directory.
    >[!IMPORTANT]
    >Bedingter Zugriff für PCs ist nicht für alle Kunden, Intune derzeit verfügbar. Wenn Sie bereits bedingten Zugriff für PCs verwenden, brauchen Sie keine Maßnahmen ergreifen. Sie können weiterhin verwenden.
    Wenn Sie keine Richtlinien für bedingten Zugriff für PCs erstellt haben, müssen Sie eine Anforderung für den Zugriff.  Sie finden weitere Informationen zu bekannten Problemen sowie für den Zugriff auf diese Funktion auf der [Website](http://go.microsoft.com/fwlink/?LinkId=761472).

-   Es muss mit allen festgelegten Kompatibilitätsrichtlinien von [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] kompatibel sein.

Der Gerätestatus wird in Azure Active Directory gespeichert. Die Anwendung gewährt oder blockiert den Zugriff auf Dateien entsprechend den von Ihnen angegebenen Bedingungen.

Wenn eine Bedingung nicht erfüllt wird, erhält der Benutzer bei der Anmeldung die folgenden Meldungen:

-   Wenn das Gerät nicht registriert [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)], oder in Azure Active Directory, eine Meldung mit Anweisungen zum Installieren der Unternehmensportal-app und registrieren.

-   Wenn das Gerät nicht kompatibel ist, wird eine Meldung angezeigt, die den Benutzer anweist die [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] Unternehmensportal-Website, wo sie Informationen über das Problem und dessen Lösung finden können.

-   Für PCs:

    -   Wenn die Richtlinie das Beitreten zu einer Domäne erfordert und der PC nicht in die Domäne eingebunden ist, wird die Meldung angezeigt, dass der IT-Administrator kontaktiert werden sollte.

    -   Wenn die Richtlinie zum Beitreten zu einer Domäne erforderlich festgelegt ist, oder kompatibel, und der PC wird nicht der Anforderungen erfüllt, wird eine Meldung angezeigt, mit Informationen zum Installieren der Unternehmensportal-app und registrieren.

Sie können den Zugriff auf SharePoint Online in den folgenden Apps steuern :

-   Microsoft Office Mobile (Android)

-   Microsoft OneDrive (Android und iOS)

-   Microsoft Word (Android und iOS)

-   Microsoft Excel (Android und iOS)

-   Microsoft PowerPoint (Android und iOS)

-   Microsoft OneNote (Android und iOS)

## Schritte zum Konfigurieren des bedingten Zugriffs für SharePoint Online

### Schritt 1: Konfigurieren von Active Directory-Sicherheitsgruppen
Bevor Sie beginnen, konfigurieren Sie Azure Active Directory-Sicherheitsgruppen für die bedingte Zugriffsrichtlinien. Sie können diese Gruppen im **Office 365 Admin Center**oder **Intune-Kontenportal**konfigurieren. Die Gruppen enthalten die Benutzer, für die die Richtlinie gelten soll oder die davon ausgeschlossen sind. Bei Benutzern, für die eine Richtlinie gelten soll, muss jedes von ihnen verwendete Gerät die Richtlinie erfüllen, damit sie auf Ressourcen zugreifen können.

Sie können zwei Arten von Gruppentypen in einer SharePoint Online-Richtlinie angeben:

-   **Zielgruppen** : Gruppen von Benutzern, für die die Richtlinie gelten soll.

-   **Ausgenommene Gruppen** : Gruppen von Benutzern, die von der Richtlinie ausgenommen sind (optional).

Benutzer, die in beiden Gruppen enthalten sind, werden von der Richtlinie ausgenommen.

### Schritt 2: Konfigurieren und Bereitstellen einer Kompatibilitätsrichtlinie
Wichtig ist, dass Sie für alle Geräte, für die die SharePoint Online-Richtlinie gelten soll, eine Kompatibilitätsrichtlinie erstellen und bereitstellen.

> [!NOTE]
> Wenn Kompatibilitätsrichtlinien für [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] -Gruppen bereitgestellt werden, gelten bedingte Zugriffsrichtlinien für Azure Active Directory-Sicherheitsgruppen.

Ausführliche Informationen zum Konfigurieren der Konformitätsrichtlinien finden Sie unter [Verwalten von gerätekonformitätsrichtlinien für Microsoft Intune](../Topic/Manage-device-compliance-policies-for-Microsoft-Intune.md).

> [!IMPORTANT]
> Wenn Sie keine Kompatibilitätsrichtlinie bereitgestellt haben und dann die SharePoint Online-Richtlinie aktivieren, wird allen Zielgeräten der Zugriff erlaubt.

Wenn Sie soweit sind, fahren Sie mit **Schritt 3**fort.

### <a name="BKMK_OneDrive"></a>Schritt 3: Konfigurieren der SharePoint Online-Richtlinie
Anschließend konfigurieren Sie die Richtlinie so, dass nur verwaltete und kompatible Geräte auf SharePoint Online zugreifen dürfen. Diese Richtlinie wird in Azure Active Directory gespeichert.

#### <a name="bkmk_spopolicy"></a>

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com)auf **Richtlinie** &gt; **Bedingter Zugriff** &gt; **SharePoint Online-Richtlinie**.

2.  Wählen Sie **Bedingte Zugriffsrichtlinie für SharePoint Online aktivieren**aus.

3.  Unter **Geräteplattformen**, die Möglichkeit, die Richtlinie für bedingten Zugriff zu übernehmen:

    -   **Alle Plattformen**

        Dies erfordert, dass auf jedem Gerät verwendet zugreifen **SharePoint Online**,  in Intune registriert und mit den Richtlinien kompatibel sein.  Jede Clientanwendung mit **moderne Authentifizierung** ist unterliegt der Richtlinie für bedingten Zugriff, und wenn die Plattform nicht von Intune unterstützt wird, Zugriff auf **SharePoint Online** blockiert wird.
        Diese Option viele nicht angezeigt, wenn Sie noch nicht mit bedingten Zugriff für PCs.  Verwenden der **bestimmte Plattformen** stattdessen. Bedingter Zugriff für PCs ist nicht für alle Kunden, Intune derzeit verfügbar.   Sie finden weitere Informationen zu bekannten Problemen sowie für den Zugriff auf diese Funktion auf der [Website](http://go.microsoft.com/fwlink/?LinkId=761472).


    -   **Specific platforms**

        If you choose the **Specific platforms** option, you will see a list of platforms that you can individually select.   Conditional access policy will apply to any client app that is using modern authentication, but only on the platforms you select.

    > [!TIP]
    > **Modern authentication** brings Active Directory Authentication Library (ADAL)-based sign in to Office clients.
    >
    > -   The ADAL based authentication enables Office clients to engage in browser-based authentication (also known as passive authentication).  To authenticate, the user is directed to a sign-in web page.
    > -   This new sign-in method enables new scenarios such as, conditional access, based on **device compliance** and whether **multi-factor authentication** was performed.
    >
    > This [article](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) has more detailed information on how modern authentication works.

    For windows PCs, the PC must either be domain joined, or enrolled with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] and compliant. You can set the following requirements:

    -   **Devices must be domain joined or compliant.** This means that the PCs must either be domain joined or compliant with the policies set in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]. If the PC does not meet either of these requirements, the user is prompted to enroll the device with [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)].

    -   **Devices must be domain joined.** This means that the PCs must be domain joined to access Exchange Online. If the PC is not domain joined access to email is blocked and the user is prompted to contact the IT admin.

    -   **Devices must be compliant.** This means that the PCs must be enrolled in [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] and compliant. If the PC is not enrolled, a message with instructions on how to enroll is displayed.

4.  Klicken Sie unter **Zielgruppen**auf **Ändern** , um die Active Directory-Sicherheitsgruppen auszuwählen, für die die Richtlinie gelten soll. Sie können dies für alle Benutzer oder nur für ausgewählte Benutzergruppen festlegen.

5.  Klicken Sie unter **Ausgenommene Gruppen**optional auf **Ändern** , um die Active Directory-Sicherheitsgruppen auszuwählen, die von dieser Richtlinie ausgenommen werden.

6.  Klicken Sie abschließend auf **Speichern**.

Die Richtlinie für bedingten Zugriff wird sofort wirksam und muss nicht explizit bereitgestellt werden.

### Schritt 4: Überwachen der Richtlinien für Kompatibilität und bedingten Zugriff
Im Arbeitsbereich **Gruppen** können Sie den Status beim bedingten Zugriff Ihrer Geräte anzeigen.

Wählen Sie eine beliebige Gruppe von Mobilgeräten und dann auf der Registerkarte **Geräte** einen der folgenden **Filter**aus:

-   **Geräte, die nicht bei AAD registriert sind** : Diese Geräte werden für SharePoint Online blockiert.

-   **Geräte, die nicht kompatibel sind** : Diese Geräte werden für SharePoint Online blockiert.

-   **Geräte, die bei AAD registriert und kompatibel sind** : Diese Geräte können auf SharePoint Online zugreifen.

## Siehe auch
[Verwalten des Zugriffs auf E-Mail und SharePoint mit Microsoft Intune](../Topic/Manage-access-to-email-and-SharePoint-with-Microsoft-Intune.md)


<!--HONumber=Mar16_HO4-->


