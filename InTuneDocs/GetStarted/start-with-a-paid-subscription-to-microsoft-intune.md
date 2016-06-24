---
# required metadata

title: Erste Schritte mit Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Erste Schritte mit Intune
Diese Kurzanleitung führt Sie durch die notwendigen Schritte zum Einrichten eines bezahlten Abonnements für Microsoft Intune, damit Sie mobile Geräte und Windows-PCs, die in Ihrem Unternehmen verwendet werden, schnell und einfach verwalten können. Sie können jeden Schritt in der entsprechenden Reihenfolge ausführen oder einzelne Schritte überspringen, die für Ihre spezifische Umgebung oder Ihre Geschäftsanforderungen nicht zutreffen.

>[!NOTE]
>In diesem Artikel geht es um die Einrichtung von Intune als eigenständiger Dienst. Wenn Sie zurzeit Microsoft System Center Configuration Manager zur Verwaltung von Computern und Servern verwenden, können Sie alternativ dazu auch [Configuration Manager auf die Verwaltung von mobilen Geräten erweitern](https://technet.microsoft.com/library/jj884158.aspx), indem Sie Intune in einer hybriden MDM-Bereitstellung mit Configuration Manager verbinden, um auch mobile Geräte verwalten zu können.

Die Schritte in dieser Kurzanleitung sind in großen Teilen mit den Schritten im [Intune-Evaluierungsleitfaden](/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune) identisch. Wenn Sie nach der Evaluierungsphase bereit sind, Ihre mobilen Geräte zu verwalten, müssen Sie einige weitere Aktionen durchführen. Welche Aktivitäten erforderlich sind, richtet sich nach Ihrer aktuellen Netzwerkinfrastruktur und Ihren Geschäftsanforderungen, wie beispielsweise:

-   Synchronisieren von lokalen Active Directory-Konten mit Intune und Azure Active Directory

-   Aktualisieren von Einträgen für die öffentliche Domäne und den DNS-Dienst bei Ihrer Domänenregistrierungsstelle.

-   Anpassen von Intune-Features für die Produktion

>[!TIP]
>Wenn Sie in einem berechtigenden Plan mindestens 150 Lizenzen für Microsoft Intune erwerben, können Sie das „FastTrack Center-Leistungsangebot“ nutzen, einen Dienst, bei dem Microsoft-Spezialisten Sie bei der Vorbereitung Ihrer Umgebung für Intune unterstützen. Siehe [Microsoft Intune-Servicevorteil – Beschreibung](https://technet.microsoft.com/library/mt228265.aspx)..


## Vorbereitung
Verwenden Sie diese Kurzanleitung, wenn Sie mit einem kostenpflichtigen Abonnement beginnen und bereit sind, Intune bereitzustellen und Änderungen an Ihrer vorhandenen Netzwerkinfrastruktur vorzunehmen. Änderungen können vom einfachen Hinzufügen oder Aktualisieren Ihrer internen und externen DNS-Einträge bis hin zur Synchronisierung Ihrer vorhandenen Active Directory-Benutzerkonten mit Azure Active Directory reichen. Unabhängig von der Kombination von Intune-Features zur Verwaltung mobiler Geräte, für die Sie sich entscheiden, müssen Sie sorgfältig planen, wie Intune mit Ihren vorhandenen Netzwerkkomponenten und Diensten interagiert. Insbesondere sollten Sie Folgendes überprüfen:

-   **Verwalten von Benutzeridentitäten**: Für die meisten mittelgroßen und großen Unternehmen stellt die Verbindung ihrer vorhandenen Verzeichnisdienste mit Intune über Azure Active Directory die beste und einfachste Methode zum Verwalten der Benutzeridentität mit Intune dar. Dies gilt insbesondere dann, wenn Sie bereits andere Microsoft Cloud Services wie Office 365 und Exchange Online verwenden. Das Synchronisieren Ihrer vorhandenen Benutzerkonten mit [Microsoft Azure Active Directory Connect](https://www.microsoft.com/download/details.aspx?id=47594) ist eine schnelle und einfache Möglichkeit, Ihr lokales Active Directory mit Azure Active Directory zu verbinden und eine Authentifizierung für das einmalige Anmelden für Ihre Benutzer zu konfigurieren.

-   **Auswirkungen auf DNS**: Wenn Sie Ihren eigenen Domänennamen anstelle der Standarddomäne onmicrosoft.com verwenden möchten, die Sie bei der ersten Registrierung bei Intune erhalten, müssen einige öffentliche DNS-Einträge aktualisiert werden. DNS-Einträge müssen aktualisiert werden, damit mobile Geräte den Intune-Dienst finden können, und um sicherzustellen, dass der Verwaltungsdienst für Ihr Abonnement ordnungsgemäß funktioniert und alle Geräte verwaltet, die in Ihrem Unternehmen verwendet werden.

## Benötigte Elemente
Bereit für die ersten Schritte? Folgende Elemente sind bei der Nutzung eines kostenpflichtigen Abonnements von Intune erforderlich:

### Ein Gerät mit einem Webbrowser, in dem Silverlight aktiviert ist
Diesen benötigen Sie für den Zugriff auf die Intune-Verwaltungskonsole, in der Sie Geräte, Apps und Richtlinien verwalten. Sie benötigen einen Webbrowser ebenfalls für den Zugriff auf das webbasierte Unternehmensportal, wenn Sie nicht über ein mobiles Gerät auf die Unternehmensportal-App zugreifen. Zur Vereinfachung können Sie in dem Browser, den Sie zur Intune-Verwaltung verwenden, auch den Datenschutzmodus aktivieren (in Internet Explorer beispielsweise klicken Sie hierzu auf **Extras** &gt; **InPrivate-Browsen**).).

>[!TIP]
>Aufgrund dieser Anforderung wird der Zugriff auf die Intune-Verwaltungskonsole über den Microsoft Edge-Browser nicht unterstützt.


### Zertifikate für mobile Geräte
Wenn Sie iOS- oder Windows Phone-Geräte mit Intune verwalten möchten, benötigen Sie Zertifikate und Konten, um diese Zertifikate abzurufen. Für die Verwaltung von Android-Geräten sind keine zusätzlichen Zertifikate erforderlich:

- Für Benutzer von **Windows Phone 8.1**, die die Unternehmensportal-App über den Store installieren, ist kein Zertifikat erforderlich. Für **Windows Phone 8.0** oder zur Verwendung von Intune zum Bereitstellen der Unternehmensportal-App auf Windows Phone 8.1-Geräten ist ein [Symantec-Codesignaturzertifikat](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do) erforderlich.

>[!NOTE]
>In dieser Anleitung wird davon ausgegangen, dass Ihre Benutzer die Unternehmensportal-App aus dem Store auf ein Gerät mit Windows Phone 8.1 oder höher abrufen. Informationen zur Unterstützung von Windows Phone 8.0 finden Sie unter [Einrichten der Windows Phone 8.0-Verwaltung mit Microsoft Intune](/Intune/deploy-use/set-up-windows-phone-8.0-management-with-microsoft-intune)..

- Für **Windows-PCs** oder **Windows RT-Geräte** bestehen keine Zertifikatanforderungen beim Registrieren von Windows-PCs als Geräte oder beim [Installieren des Windows-PC-Clients für Microsoft Intune](/intune/deploy-use/install-the-windows-pc-client-with-microsoft-intune)..

- Für **iOS**- oder **Mac OS X**-Geräte müssen Sie ein Apple Push Notification Service-Zertifikat bei Apple anfordern, wie unter [Einrichten der iOS- und Mac-Verwaltung mit Microsoft Intune](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune), Schritt 3, beschrieben..

### Nächste Schritte
Legen Sie los mit der Intune-Kurzanleitung!

>[!div class="step-by-step"]
[**Anmelden bei Intune** &rarr;](start-with-a-paid-subscription-to-microsoft-intune-step-1.md)


<!--HONumber=May16_HO1-->


