---
title: Problembehandlung der Lookout-Integration | Microsoft Intune
description: "Dieses Thema beschreibt die Behandlung von Problemen, die im Zusammenhang mit der Lookout-Integration häufig auftreten."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: bbe0b5f4-b8bc-49f3-85a9-51fb2f226fca
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9c2ffb5fe497d56d8250fe3dec7db606c2067a1c
ms.openlocfilehash: 66242455279c20bac2aa2e17dda6c2739e9204c7


---

# Problembehandlung der Lookout-Integration mit Intune
In diesem Thema werden einige häufige Probleme beschrieben, die möglicherweise bei Ihrer Bereitstellung von Lookout Mobile Threat Protection (MTP) auftreten.
## Problembehandlung für Anmeldefehler
### 403-Fehler
Bei der Anmeldung an der [Lookout MTP-Konsole](https://aad.lookout.com) tritt möglicherweise ein 403-Fehler auf: **Sie sind nicht zum Zugriff auf den Dienst berechtigt** Dies kann geschehen, wenn der von Ihnen angegebene Benutzername kein Mitglied der Azure Active Directory-Gruppe (Azure AD) ist, die für den Zugriff auf Lookout MTP konfiguriert ist.

Lookout MTP ist dafür konfiguriert, nur Benutzern aus einer konfigurierten Azure AD-Gruppe den Zugriff zu erteilen. Wenn Sie nicht sicher sind, für welche Gruppe der Zugriff auf Lookout MTP konfiguriert ist, wenden Sie sich an den Lookout-Support.

Sie können sich auf den folgenden Wegen an den Lookout-Support wenden:

* E-Mail: enterprisesupport@lookout.com
* Melden Sie sich bei der [MTP-Konsole](http://aad.lookout.com) an, und navigieren Sie zum Modul **Support**.
* Navigieren Sie zu: „https://enterprise.support.lookout.com/hc/en-us/requests“, und stellen Sie eine Supportanfrage.

### Die Anmeldung ist nicht möglich
Möglicherweise wird der folgende Fehler angezeigt, wenn der globale Administratorbenutzer von Azure AD das erstmalige Lookout-Setup nicht akzeptiert hat.

![Screenshot des Lookout-Anmeldebildschirms, der den Anmeldefehler darstellt](../media/mtp/lookout-mtp-consent-not-accepted-error.png)

Um dieses Problem zu beheben, muss sich der globale Administratorbenutzer bei „https://aad.lookout.com/les?action=consent“ anmelden und die Aufforderung zum Starten von Setup akzeptieren. Ausführlichere Informationen finden Sie im Thema [Einrichten Ihres Abonnements für Lookout MTP](set-up-your-subscription-with-lookout-mtp.md)

## Behandeln von Problemen mit dem Gerätestatus

### Das Gerät wird in der Geräteliste in der Lookout MTP-Konsole nicht angezeigt

Diese Problem kann in allen folgenden Szenarien auftreten:
* Wenn der Benutzer, der das Gerät besitzt, nicht Mitglied der in der **Lookout MTP-Konsole** angegebenen **Registrierungsgruppe** ist.  Gehen Sie im Modul **System** zur Registerkarte **Intune-Connector**, und zeigen Sie die Einstellungen unter **Registrierungsverwaltung** an.  Sie sollten mindestens eine Azure AD-Gruppe sehen, die für die Registrierung konfiguriert ist.  Überprüfen Sie, ob der Benutzer, dem das fehlende Gerät gehört, Teil einer der angegebenen Azure AD-Gruppen ist.  Nachdem der Registrierungsgruppe ein neuer Benutzer hinzugefügt wurde, benötigt es bis zum Ablauf des konfigurierten Abrufintervalls (der Standardwert ist 5 Minuten), bis das Gerät im Modul **Geräte** der Lookout MTP-Konsole angezeigt wird.

* Wenn das Gerät nicht von Lookout MTP unterstützt wird.  Nicht unterstützte Geräte werden in der Lookout MTP-Konsole im Abschnitt **Verwaltete Geräte** der Connectoreinstellungen angezeigt.

### Das Gerät wird weiterhin als **ausstehend** gemeldet

Ein Gerät, das als **Ausstehend** angezeigt wird, bedeutet, dass der Endbenutzer die Lookout for Work-App nicht geöffnet und auf die Schaltfläche **Aktivieren** getippt hat. Weitere Details zur Geräteaktivierung mit der Lookout for Work-App finden Sie im folgenden Thema:

[Sie werden aufgefordert, Lookout for Work auf Ihrem Android-Gerät zu installieren ](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

### In der Lookout MTP-Konsole wird ein Gerät als aktiv angezeigt, es weist aber keine Geräte-ID auf.  
Dies bedeutet, dass der Benutzer, der das Gerät besitzt, sich nicht in der in der Lookout MTP-Konsole angegebenen Registrierungsgruppe befindet.   Ein Gerät kann in diesen Zustand kommen, wenn der Benutzer, der das Gerät besitzt, aus der Registrierungsgruppe entfernt wurde oder die Registrierungsgruppe entfernt wurde, zu der der Benutzer gehört.

Navigieren Sie im Modul **System** der Lookout MTP-Konsole zur Registerkarte **Intune-Connector**, und überprüfen Sie die Einstellungen unter **Registrierung**.  Sie sollten mindestens eine Azure AD-Gruppe sehen, die für die Registrierung konfiguriert ist.  Überprüfen Sie, ob der Benutzer, dem das Gerät gehört, Teil einer der angegebenen Azure AD-Gruppen ist.  

Während ein Gerät sich in diesem Zustand befindet, informiert Lookout den Benutzer weiterhin über alle erkannten Bedrohungen, sendet aber keine Bedrohungsinformationen an Intune.

### Das Gerät zeigt den Status „getrennt“ an

„Getrennt“ bedeutet, dass Lookout MTP über einen vorkonfigurierten Zeitraum hinaus (der Standard sind 30 Tage, der Minimalwert 7 Tage) nicht mehr von dem Gerät gehört hat. Dies hat den Grund, dass entweder die Unternehmensportal-App oder die Lookout for Work-App nicht auf dem Gerät installiert ist oder deinstalliert wurde. Das Problem sollte sich durch erneutes Installieren der Apps beheben lassen. Wenn der Benutzer Lookout for Work öffnet und die App aktiviert, synchronisiert sich das Gerät erneut mit Lookout MTP und Intune.    

### Erzwingen einer erneuten Synchronisierung auf dem Gerät
Der Administrator kann das Gerät im Modul **Geräte** der Lookout MTP-Konsole auswählen und sich entscheiden, es zu löschen.   Wenn der Gerätebesitzer die Lookout for Work-App das nächste Mal öffnet und auf **Aktivieren** klickt, erfolgt eine vollständige Neusynchronisierung des Gerätezustands.

### Der Besitzer verwendet dieses Gerät nicht mehr
Sie müssen das Gerät zurücksetzen und den neuen Besitzer bitten, sich zu registrieren.  Wählen Sie das Gerät in der [Intune-Verwaltungskonsole](https://manage.microsoft.com) aus, klicken Sie mit der rechten Maustaste, und wählen Sie **Abkoppeln/Zurücksetzen** aus, um das Gerät aus der Verwaltung zu entfernen. Nach dem Abkoppeln können Sie das Gerät löschen.

![Screenshot des Gerätemoduls in der Intune-Verwaltungskonsole mit dargestellter Option „Abkoppeln/Zurücksetzen“](../media/mtp/mtp-retire-device-intune-console.png)

Alternativ können Sie in der Lookout MTP-Konsole zum Modul **Geräte** navigieren und **Löschen** auswählen.  

Sofern der neue Benutzer sich in einer der Registrierungsgruppen befindet, die in der Lookout MTP-Konsole angegeben sind, wird das Gerät angezeigt, nachdem Azure AD das Gerät dem neuen Benutzer zugeordnet hat.

## Arbeitsabläufe zur Wiederherstellung der Kompatibilität
[Sie werden aufgefordert, Lookout for Work auf Ihrem Android-Gerät zu installieren]( http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

[Sie müssen eine Bedrohung beseitigen, die Lookout for Work auf Ihrem Android-Gerät erkannt hat ](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)


### Weitere Informationen:
[Einrichten Ihres Abonnements für Lookout MTP](set-up-your-subscription-with-lookout-mtp.md)



<!--HONumber=Sep16_HO2-->


