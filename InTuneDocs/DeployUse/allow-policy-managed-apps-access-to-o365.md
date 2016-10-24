---
title: App-basierter bedingter Zugriff auf O365 | Microsoft Intune
description: "Informationen dazu, wie Sie mit bedingtem Zugriff für die Verwaltung mobiler Anwendungen bestimmen können, welche Apps auf O365-Dienste zugreifen dürfen."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 64eaba6918c4a5c7ccc39fb8ccfeae729a34ff4c
ms.openlocfilehash: a03faa57f9bf1ec6784f0b1ec2d41d3f4cd88a12


---

# Erstellen einer Richtlinie, die nur mobilen Apps den Zugriff auf Office 365-Dienste ermöglicht, die Intune-Richtlinien für die Verwaltung mobiler Anwendungen unterstützen
[Intune-Richtlinien für die Verwaltung mobiler Anwendungen (MAM)](protect-apps-and-data-with-microsoft-intune.md) unterstützen Sie beim Schutz Ihrer Unternehmensdaten auf Geräten, die für die Verwaltung in Intune registriert sind. Richtlinien für die Verwaltung mobiler Anwendungen können Sie auch auf **mitarbeitereigenen Geräten verwenden, die nicht für die Verwaltung in Intune registriert sind**.  Auch wenn Sie das Gerät nicht verwalten, müssen Sie in diesem Fall dennoch sicherstellen, dass Unternehmensdaten und -ressourcen geschützt sind. Mithilfe des bedingten Zugriffs für die Verwaltung mobiler Anwendungen (MAM CA) können Sie eine Richtlinie erstellen, mit der nur mobile Apps auf O365-Dienste wie Exchange Online zugreifen können, die Intune-Richtlinien für die Verwaltung mobiler Anwendungen unterstützen.

Wenn Sie beispielsweise zulassen, dass nur die **Microsoft Outlook-App** auf Exchange Online zugreifen kann, können Sie so **verhindern, dass die in iOS und Android integrierten Mail-Apps**, die nicht über den Datenschutz von Intune-Richtlinien für die Verwaltung mobiler Anwendungen verfügen, E-Mails von **Exchange Online** empfangen.

## Voraussetzungen
**Bevor** Sie MAM CA-Richtlinien konfigurieren können, müssen Sie über ein **Enterprise Mobility + Security- oder ein Azure Active Directory Premium-Abonnement** verfügen, und die Benutzer müssen für EMS oder Azure AD lizenziert sein. Weitere Informationen finden Sie in der [Preisübersicht für Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) oder der [Preisübersicht für Azure Active Directory](https://azure.microsoft.com/en-us/pricing/details/active-directory/).


## Unterstützte Apps
**Exchange Online**
* Microsoft Outlook für Android und iOS

## Überschneidung mit anderen Methoden des bedingten Zugriffs und Authentifizierungsmethoden
### MAM CA mit Authentifizierung, die auf Azure Active Directory-Zertifikaten basiert

MAM CA darf nicht mit der zertifikatbasierten Authentifizierung von Azure Active Directory (Azure AD) verwendet werden. Es darf immer jeweils nur eine Authentifizierungsmethode konfiguriert werden.
### MAM CA mit dem bedingten Zugriff basierend auf Gerätekompatibilität  

Sie können über die [Intune-Administratorkonsole](https://manage.microsoft.com) oder die [Azure AD Premium-Verwaltungskonsole] (https://manage.windowsazure.com) einen [bedingten Zugriff basierend auf Gerätekompatibilität](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (**bedingten Zugriff für Geräte**) konfigurieren. Bei diesem bedingten Zugriff dürfen Benutzer nur über mit Intune verwaltete Geräte, die mit der Intune-Gerätekompatibilitätsrichtlinie kompatibel sind, oder über in die Domäne eingebundene PCs eine Verbindung mit Exchange Online herstellen.  Wenn ein Benutzer mindestens einer Sicherheitsgruppe angehört, die sowohl für MAM CA als auch für Richtlinien für den bedingten Zugriff für Geräte (Device CA) vorgesehen ist, muss der Benutzer eine der beiden folgenden Anforderungen erfüllen:
* Die App, die für den Zugriff auf den Dienst verwendet wird, ist eine mobile App, die von MAM CA unterstützt wird. Auf dem Gerät, auf dem die App ausgeführt wird, ist **iOS Authenticator (für iOS-Geräte)** bzw. die **Unternehmensportal-App (für Android-Geräte)** installiert.
* Das Gerät, das für den Zugriff auf den Dienst verwendet wird, wird von **Intune verwaltet und ist kompatibel** mit der Intune-Gerätekompatibilitätsrichtlinie, oder es handelt sich um einen **in die Domäne eingebundenen PC**.  Im Folgenden finden Sie einige Beispiele zur Veranschaulichung:
  * Wenn ein Benutzer versucht, über die **native iOS-E-Mail-App** eine Verbindung herzustellen, muss er ein **verwaltetes und kompatibles Gerät** verwenden, da die native Mail-App von MAM CA nicht unterstützt wird.
  * Wenn ein Benutzer versucht, über einen **privaten Windows-PC** eine Verbindung herzustellen, wird die **Geräte-Richtlinie für bedingten Zugriff** angewendet, die verlangt, dass ein in die Domäne eingebundener PC verwendet wird.


## Was ist bei der Verwendung einer App mit MAM CA zu erwarten?
MAM CA überprüft die Identität der genehmigten Anwendung mithilfe einer Broker-App, die auf dem Gerät vorhanden sein muss:
*  Unter **iOS** ist die **Azure Authenticator-App** die Broker-App.
* Unter **Android** ist die **Intune-Unternehmensportal-App** die Broker-App. 

Benutzer, die sich zum ersten Mal bei einer von MAM CA unterstützten App wie OneDrive oder Outlook anmelden, werden aufgefordert, die Broker-App zu installieren und das Gerät bei Azure AD zu registrieren. Beim Registrieren des Geräts in Azure AD (früher als Arbeitsplatzeinbindung bekannt) werden ein Gerätedatensatz und -zertifikat erstellt, für die Token ausgegeben werden.  Hierbei handelt es sich **nicht** um eine **MDM-Registrierung**. Hier werden keine Verwaltungsprofile oder -richtlinien angewendet, und es wird keine Bestandsaufnahme für Apps auf dem Gerät durchgeführt.  Der Prozess der Installation der Broker-App und der Registrierung des Geräts wurde nur bei der ersten Verwendung einer verwalteten App durchgeführt.


## Nächste Schritte
[Erstellen einer Exchange Online-Richtlinie für MAM-Apps](mam-ca-for-exchange-online.md)

[Blockieren von Apps, die über keine moderne Authentifizierung verfügen](block-apps-with-no-modern-authentication.md)

### Weitere Informationen:

[Schützen von App-Daten mithilfe von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO2-->


