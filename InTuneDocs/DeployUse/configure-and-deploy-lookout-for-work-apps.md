---
title: Bereitstellen der Lookout for Work-App | Microsoft Intune
description: "Konfigurieren und Bereitstellen von Lookout for Work-Apps für Android."
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c4d05b9ba7249e4068d21480b1c9db342277757e
ms.openlocfilehash: 687a102ccb34cb7acfaab1e8a1d4b67cb54b9e92


---

# Konfigurieren und Bereitstellen von Lookout for Work-Apps
Dieser Artikel beschreibt das Konfigurieren und Bereitstellen der Lookout for Work-App für Geräte, die registriert wurden und auf denen Android 4.1 oder höher ausgeführt wird.

* **Schritt 1**: Wechseln Sie in der [Microsoft Intune-Administratorkonsole](https://manage.microsoft.com) zu **Apps**, und wählen Sie **Apps hinzufügen** aus.   
* **Schritt 2**: Wählen Sie auf der Seite **Softwaresetup** des Herausgebers **Externer Link** aus, und geben Sie die folgende URL an: https://play.google.com/store/apps/details?id=com.lookout.enterprise
>[!NOTE]
>Klicken Sie nicht auf das Feld, das einen verwalteten Browser vorschreibt.

* **Schritt 3**: Geben Sie auf der Seite **Softwarebeschreibung** die folgenden Informationen ein:
  * **Herausgeber:** Lookout Mobile Security
  * **Name:**   Lookout for Work
  * **Beschreibung:** Lookout bietet optimalen Schutz vor mobilen Bedrohungen, um die Sicherheit Ihres Geräts zu gewährleisten. Wenn die Lookout-App auf einem Gerät installiert ist, schützt die App das Gerät vor Bedrohungen und warnt Sie und Ihren Unternehmensadministrator, sobald Bedrohungen erkannt werden.
  * **Kategorie:** Computerverwaltung
* **Schritt 4**: Nach erfolgreichem Abschluss wird die Meldung **Daten wurden erfolgreich in Microsoft Intune hochgeladen** angezeigt.

Wenn Sie in der Intune-Konsole auf **Apps** klicken, wird nun die Lookout for Work-App in der Liste angezeigt. ![Screenshot der Seite „Apps“ in der Intune-Administratorkonsole mit der Lookout for Work-App in der Liste](../media/mtp/lookout-app-listed-intune-console.png)

**Um die App Benutzern bereitzustellen**, wählen Sie die auf dem Bildschirm oben dargestellte Lookout for Work-App und dann **Bereitstellung verwalten** aus.

Sie müssen die gleichen Benutzer auswählen, die unter der Option „Registrierungsverwaltung“ in der Lookout MTP-Konsole hinzugefügt wurden.  Informationen zum Hinzufügen von Benutzergruppen zu Lookout MTP finden Sie unter Schritt 3 im Abschnitt [Konfigurieren Ihres Abonnements mit Lookout MTP](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp).
>[!IMPORTANT]
> Dem Intune-Assistenten für die App-Bereitstellung sind die Azure AD-Benutzergruppen nicht bekannt, weshalb er die Intune-Benutzergruppen verwendet. Sie müssen daher auf Grundlage der Azure AD-Benutzergruppe, die bei der Lookout MTP-Konsole registriert ist, eine Intune-Benutzergruppe erstellen, was in [diesem](plan-your-user-and-device-groups.md) Thema erläutert wird.

Aktivieren Sie die Option **Erforderliche Installation**, um vorzuschreiben, dass die Lookout-App auf dem Gerät des Benutzers installiert wird.


Wenn die Option **Erforderliche Installation** für die Bereitstellung aktiviert ist, überträgt Intune die Lookout for Work-Anwendung per Push an das Gerät.   

Wenn der Benutzer Lookout for Work auf dem mobilen Gerät öffnet, wird er aufgefordert, die App zu aktivieren und die Option „Bei Azure Active Directory anmelden“ auszuwählen. Eine ausführliche exemplarische Vorgehensweise mit dem Arbeitsablauf für den Endbenutzer finden sich in folgenden Themen:

* [Sie werden aufgefordert, Lookout for Work auf Ihrem Android-Gerät zu installieren](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [Sie müssen eine Bedrohung beseitigen, die Lookout for Work auf Ihrem Android-Gerät erkannt hat](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## Nächste Schritte
* [Aktivieren der Regel zum Schutz vor Bedrohungen auf dem Gerät in der Kompatibilitätsrichtlinie](enable-device-threat-protection-rule-in-compliance-policy.md)



<!--HONumber=Sep16_HO3-->


