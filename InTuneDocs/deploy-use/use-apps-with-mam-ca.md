---
title: Verwenden von Apps mit MAM CA | Microsoft Intune
description: "Informationen dazu, wie Sie mit bedingtem Zugriff für die Verwaltung mobiler Anwendungen bestimmen können, welche Apps auf O365-Dienste zugreifen dürfen."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71dcf9bc-bfd1-4e06-b7ad-14b33a2288d0
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: df77e1473532399056c3e0c1b4c4db3c7b6ba995
ms.openlocfilehash: 0fc24f1c93cfcdb86c2a66c9a027b4ed9c516dab


---
# <a name="what-to-expect-when-using-an-app-with-mam-ca"></a>Was ist bei der Verwendung einer App mit MAM CA zu erwarten?
MAM CA überprüft die Identität der genehmigten Anwendung mithilfe einer Broker-App, die auf dem Gerät vorhanden sein muss:
*  Unter **iOS** ist die **Azure Authenticator-App** die Broker-App.
* Unter **Android** ist die **Intune-Unternehmensportal-App** die Broker-App. 

Benutzer, die sich zum ersten Mal bei einer von MAM CA unterstützten App wie OneDrive oder Outlook anmelden, werden aufgefordert, die Broker-App zu installieren und das Gerät bei Azure AD zu registrieren. Beim Registrieren des Geräts in Azure AD (früher als Arbeitsplatzeinbindung bekannt) werden ein Gerätedatensatz und -zertifikat erstellt, für die Token ausgegeben werden.  Hierbei handelt es sich **nicht** um eine **MDM-Registrierung**. Hier werden keine Verwaltungsprofile oder -richtlinien angewendet, und es wird keine Bestandsaufnahme für Apps auf dem Gerät durchgeführt.  Der Prozess der Installation der Broker-App und der Registrierung des Geräts wurde nur bei der ersten Verwendung einer verwalteten App durchgeführt.

Im Folgenden finden Sie eine Liste der Eigenschaften, die direkt vom Gerät abgeleitet sind:

* alternativeSecurityIds (Azure Active Directory-Zertifikatfingerabdruck und -Hash für öffentliche Schlüssel)
* deviceOSType
* deviceOSVersion
* displayName

## <a name="to-remove-a-device-from-azure-ad-registration"></a>So entfernen Sie ein Gerät aus der Azure AD-Registrierung.
Eine Möglichkeit ist, die Geräteregistrierung über die Azure AD-Verwaltungskonsole zu entfernen, was normalerweise vom IT-Administrator durchgeführt wird.  Es kann aber auch vom Endbenutzer auf dem Gerät selbst durchgeführt werden.

* **Azure AD-Verwaltungskonsole**: Löschen Sie in der Azure AD-Verwaltungskonsole** das Gerät, das Sie entfernen möchten.
* **iOS-Gerät**: Öffnen Sie die Azure Authenticator-App, wischen Sie für das Konto nach links, und wählen Sie „Registrierung aufheben“ aus.  
* **Android-Gerät**: Deinstallieren Sie die Unternehmensportal-App, oder entfernen Sie das Konto aus den **Systemeinstellungen**.



## <a name="mam-ca-with-conditional-access-based-on-device-compliance"></a>MAM CA mit dem bedingten Zugriff basierend auf Gerätekompatibilität  

Sie können über die [Intune-Administratorkonsole](https://manage.microsoft.com) oder die [Azure AD Premium-Verwaltungskonsole] (https://manage.windowsazure.com) einen [bedingten Zugriff basierend auf Gerätekompatibilität](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (**bedingten Zugriff für Geräte**) konfigurieren. Bei diesem bedingten Zugriff dürfen Benutzer nur über mit Intune verwaltete Geräte, die mit der Intune-Gerätekompatibilitätsrichtlinie kompatibel sind, oder über in die Domäne eingebundene PCs eine Verbindung mit Exchange Online herstellen.  Wenn ein Benutzer mindestens einer Sicherheitsgruppe angehört, die sowohl für MAM CA als auch für Richtlinien für den bedingten Zugriff für Geräte (Device CA) vorgesehen ist, muss der Benutzer eine der beiden folgenden Anforderungen erfüllen:
* Die App, die für den Zugriff auf den Dienst verwendet wird, ist eine mobile App, die von MAM CA unterstützt wird. Auf dem Gerät, auf dem die App ausgeführt wird, ist **iOS Authenticator (für iOS-Geräte)** bzw. die **Unternehmensportal-App (für Android-Geräte)** installiert.
* Das Gerät, das für den Zugriff auf den Dienst verwendet wird, wird von **Intune verwaltet und ist kompatibel** mit der Intune-Gerätekompatibilitätsrichtlinie, oder es handelt sich um einen **in die Domäne eingebundenen PC**.  Im Folgenden finden Sie einige Beispiele zur Veranschaulichung:
  * Wenn ein Benutzer versucht, über die **native iOS-E-Mail-App** eine Verbindung herzustellen, muss er ein **verwaltetes und kompatibles Gerät** verwenden, da die native Mail-App von MAM CA nicht unterstützt wird.
  * Wenn ein Benutzer versucht, über einen **privaten Windows-PC** eine Verbindung herzustellen, wird die **Geräte-Richtlinie für bedingten Zugriff** angewendet, die verlangt, dass ein in die Domäne eingebundener PC verwendet wird.




## <a name="next-steps"></a>Nächste Schritte
[Erstellen einer Exchange Online-Richtlinie für MAM-Apps](mam-ca-for-exchange-online.md)

[Blockieren von Apps, die über keine moderne Authentifizierung verfügen](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Weitere Informationen:

[Schützen von App-Daten mithilfe von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Nov16_HO2-->


