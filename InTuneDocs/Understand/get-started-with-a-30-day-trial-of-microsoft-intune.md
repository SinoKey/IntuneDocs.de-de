---
title: Intune-Evaluierungsanleitung | Microsoft Intune
description: "Einführung und Voraussetzungen für die Einrichtung einer kostenlosen 30-tägigen Evaluierungsversion von Intune."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 08/09/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 619a1d11-3d22-4635-8f70-770eba3e1712
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 581e880fa4308ec627f5b2c1242fb5b30b713743
ms.openlocfilehash: 3973ac11d4734b17f905e88259863d7ddb59c1f4


---

# Intune-Evaluierungsanleitung
Eine kostenlose 30-tägige Evaluierung von Intune, um Ihre mobilen Geräte und Computer zu verwalten, lässt sich schnell und einfach einrichten. Mit wenigen einfachen Schritten in der Evaluierungsversion können Sie bis zu 100 Benutzer und Geräte hinzufügen, Gruppen einrichten, Kompatibilitätsrichtlinien konfigurieren und mobile Geräte und Computer registrieren und verwalten.

In diesem Thema erfahren grundlegend, wie Sie eine Intune-Evaluierung einrichten und ausführen, und erhalten einen Überblick über den Dienst, sodass Sie die Features und Funktionen von Intune beurteilen können.

Sehen Sie sich das folgende fünfminütige Demovideo an, um zu erfahren, wie einfach es ist, mit einer kostenlosen Evaluierungsversion von Microsoft Intune einzusteigen und Ihre Geräte zu verwalten. Im ersten Teil des Videos wird ein Portal erwähnt, das „abgekoppelt“ wurde. Obwohl Sie also ein anderes Portal verwenden, sind die Schritte grundsätzlich gleich. Mehr über das Portal erfahren Sie [hier](https://docs.microsoft.com/intune/deploy-use/account-portal-merged-with-Office-365).

<iframe width="675" height="480" src="https://www.youtube.com/embed/ltcZvm4VOFU" frameborder="0" allowfullscreen></iframe>

## Vorbereitung
Bevor Sie mit Intune loslegen, benötigen Sie Folgendes:

-   Ein Gerät mit einem Silverlight-fähigen Webbrowser, mit dessen Hilfe Sie auf die Websites zugreifen können, auf denen Sie Intune-Benutzerkonten erstellen (**Office 365 Admin Center**) sowie Geräte, Gruppen und Richtlinien verwalten (**Intune-Verwaltungskonsole**) können.

-   Ein zweites Gerät mit einem Webbrowser, mit dem Sie testen, wie sich Intune-Benutzer mithilfe des Unternehmensportals registrieren und ihre Geräte verwalten. Sie werden außerdem testen, wie Benutzer Apps suchen und installieren sowie Hilfe von Administratoren anfordern. Falls Sie kein zweites Gerät haben, können Sie im Browser, den Sie zur Verwaltung von Intune verwenden, auch den Datenschutzmodus aktivieren. (In Internet Explorer wählen Sie hierfür beispielsweise **Extras** &gt; **InPrivate-Browsen**).

-   Wenn Sie über ein vorhandenes Microsoft Online Services-Konto verfügen, dann benötigen Sie die Anmeldeinformationen des Administrators für dieses Konto. Wenn Sie nicht über ein solches Konto verfügen oder diesen Intune-Mandanten nur zu Evaluierungszwecken verwenden möchten, dann benötigen Sie diese Administratoranmeldeinformationen nicht.

-   Wenn Sie iOS- oder Windows Phone 8.1-Geräte mit der Intune-Evaluierungsversion verwalten möchten, benötigen Sie Zertifikate (oder Schlüssel) und Konten, um diese Zertifikate abzurufen (siehe die folgende Tabelle). Für Android-Geräte sind keine zusätzlichen Zertifikate erforderlich.

    |Plattform|Zertifikatanforderungen|Weitere Informationen|
    |------------|----------------------------|--------------------|
    |Windows Phone 8.1 |Für Benutzer von Windows Phone 8.1, die die Unternehmensportal-App über den Store installieren, ist kein Zertifikat erforderlich. |In dieser Anleitung wird davon ausgegangen, dass Ihre Benutzer die Unternehmensportal-App aus dem Store auf ein Gerät mit Windows Phone 8.1 oder höher abrufen. |
    |Windows 10-, Windows RT 8.1- oder Windows 8.1-Geräte|Es bestehen keine Zertifikatanforderungen beim Registrieren von Geräten mit Windows RT und Windows.|[Installieren des Windows-PC-Clients mit Microsoft Intune](/Intune/Deploy-Use/install-the-windows-pc-client-with-microsoft-intune).|
    |iOS 7.1 oder höher|Beziehen Sie ein Apple Push Notification Service-Zertifikat.|Fordern Sie ein Apple Push Notification Service-Zertifikat bei Apple an, wie unter [Einrichten der iOS- und Mac-Geräteverwaltung mit Microsoft Intune](/Intune/Deploy-Use/set-up-ios-and-mac-management-with-microsoft-intune) beschrieben.|

## Schritte zum Durchführen einer 30-tägigen Evaluierung von Intune
- [Schritt 1: Anmelden oder Registrieren für eine 30-tägige Evaluierung](get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md). Bevor Sie sich bei Intune registrieren oder anmelden, müssen Sie prüfen, ob Sie sich mit einem vorhandenen Konto anmelden oder ein temporäres Konto erstellen sollen, das nur für die 30-tägige Evaluierung von Microsoft Intune verwendet wird.
- [Schritt 2: Hinzufügen von Benutzern](get-started-with-a-30-day-trial-of-microsoft-intune-step-2.md). Nachdem Sie Ihr Konto eingerichtet haben, fügen Sie Intune Benutzerkonten entweder einzeln oder in einem Massenvorgang hinzu (siehe die Anweisungen in diesem Abschnitt). Bevor Sie beginnen, ist es wichtig, dass Sie verstehen, wie Intune Administratorkonten behandelt.
- [Schritt 3: Erstellen von Gruppen zum Organisieren von Benutzern und Geräten](get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md). Mit Gruppen erhalten Sie in Intune maximale Flexibilität beim Verwalten Ihrer Geräte und Benutzer. Sie können Gruppen einrichten, die Ihren organisatorischen Anforderungen (z. B. nach geografischem Standort, nach Abteilung oder nach Hardwareeigenschaften) entsprechen und diese verwenden, um verschiedene anstehende Verwaltungsaufgaben auszuführen, die von der Festlegung von Richtlinien für eine Gruppe von Benutzern bis zur Bereitstellung von Anwendungen auf einer Reihe von Geräten reichen.
- [Schritt 4: Erstellen von Richtlinien und Veröffentlichen einer App](get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md). Mit Intune-Richtlinien stehen Einstellungen bereit, mit deren Hilfe Sie die Sicherheitseinstellungen auf mobilen Geräten steuern, die Windows-Firewall- und Endpoint Protection-Einstellungen für Computer warten und Anwendungen bereitstellen können.
- [Schritt 5: Registrieren mobiler Geräte und Installieren einer App](get-started-with-a-30-day-trial-of-microsoft-intune-step-5.md). Um die Verwaltung mobiler Geräte mit Intune einzurichten, müssen Sie die Autorität für die Verwaltung mobiler Geräte festlegen, die Verwaltung spezifischer Geräteplattformen aktivieren und Ihre Geräte anschließend mit der Unternehmensportal-App registrieren. Sie können dann die von Ihnen veröffentlichte Microsoft Skype-Anwendung bereitstellen.
- [Schritt 6: Andere Optionen und Extras](get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md). Wählen Sie, wie Warnungen, Berichte und andere Intune-Funktionen verwendet werden sollen, um Ihre geschäftlichen Anforderungen zu erfüllen.
- [Schritt 7: Nächste Schritte](get-started-with-a-30-day-trial-of-microsoft-intune-step-7.md). Bereiten Sie den Wechsel zu einem kostenpflichtigen Intune-Abonnement vor, und kommen Sie in den Genuss des FastTrack Center-Angebots für Intune.


### Nächste Schritte
Es ist Zeit, mit Ihrem 30-tägigen Evaluierungsabonnement zu starten!

>[!div class="step-by-step"]
[**Bei Intune registrieren** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md)

### Weitere Informationen:
[Kurzanleitung für Intune](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune)



<!--HONumber=Oct16_HO2-->


