---
title: Vorteile des Intune App SDK | Microsoft Docs
description: 
keywords: 
author: mtillman
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 613e293d9bd853d6de7cdc0d753cc8473afc180b
ms.openlocfilehash: e8f96499f006af590b6e7da295503696110dad4e


---

# <a name="intune-app-sdk-overview"></a>Übersicht über das Intune App SDK
Das Intune App Software Development Kit (SDK) ist für iOS- und Android-Plattformen erhältlich und ermöglicht Verwaltungsfunktionen für mobile Anwendungen mit Microsoft Intune. Es zielt darauf ab, die vom App-Entwickler vorzunehmenden Codeänderungen zu minimieren. Sie werden feststellen, dass Sie die meisten SDK-Funktionen aktivieren können, ohne das Verhalten Ihrer App ändern zu müssen. Um die Benutzerfreundlichkeit der App für Endbenutzer und IT-Administratoren zu verbessern, können Sie unsere APIs verwenden und so das App-Verhalten für Funktionen anpassen, die Ihre Mitwirkung erfordern. 

Nachdem Sie Ihre App aktiviert haben, können IT-Administratoren Richtlinien für von Intune verwaltete Apps bereitstellen und die Vorteile dieser Features nutzen, um die Unternehmensdaten zu schützen.

## <a name="regular-features"></a>Reguläre Features

### <a name="control-users-ability-to-move-corporate-documents"></a>Steuern der Möglichkeit von Benutzern, Unternehmensdaten zu verschieben
IT-Administratoren können die Verlagerung von Dateien mit Unternehmensdaten in von Intune verwalteten Apps steuern. So kann beispielsweise eine Richtlinie bereitgestellt werden, mit verhindert wird, dass Unternehmensdaten mit Datensicherungs-Apps in der Cloud gespeichert werden.

### <a name="configure-clipboard-restrictions"></a>Konfigurieren von Einschränkungen für die Zwischenablage
IT-Administratoren können in von Intune verwalteten Apps das Verhalten der Zwischenablage konfigurieren. So kann beispielsweise eine Richtlinie bereitgestellt werden, die dafür sorgt, dass Endbenutzer nicht in der Lage sind, die Zwischenablage zu verwenden, um Daten aus von Intune verwalteten Apps auszuschneiden/zu kopieren und in eine nicht verwaltete, persönliche App zu kopieren.

### <a name="enforce-encryption-on-saved-data"></a>Erzwingen der Verschlüsselung von gespeicherten Daten
IT-Administratoren können mit einer Richtlinie erzwingen, dass auf dem Gerät gespeicherte Daten verschlüsselt werden.

### <a name="remotely-wipe-corporate-data"></a>Remotezurücksetzung von Unternehmensdaten
IT-Administratoren können Unternehmensdaten in einer von Intune verwalteten App remote zurücksetzen. Diese Funktion basiert auf der Identität, und es werden nur Dateien gelöscht, die der Unternehmensidentität des Endbenutzers zugeordnet sind. Hierfür ist die Mitwirkung der App erforderlich. Die App kann die Identität, für die die Zurücksetzung erfolgen soll, basierend auf den Benutzereinstellungen festlegen. Fehlen solche spezifischen Benutzereinstellungen in der App, besteht das Standardverhalten darin, das Anwendungsverzeichnis zu löschen und den Endbenutzer darüber zu informieren, dass der Zugriff entfernt wurde.

### <a name="enforce-the-use-of-a-managed-browser"></a>Erzwingen der Verwendung eines verwalteten Browsers
IT-Administratoren können die Verwendung der Intune Managed Browser-App beim Öffnen von Links in von Intune verwalteten Apps erzwingen. Dadurch wird sichergestellt, dass in einer Unternehmensumgebung angezeigte Links in der Domäne von Apps, die von Intune verwaltet werden, beibehalten werden.

### <a name="enforce-a-pin-policy"></a>Erzwingen einer PIN-Richtlinie
IT-Administratoren können eine PIN-Richtlinie beim Starten einer von Intune verwalteten App erzwingen. Dadurch wird sichergestellt, dass es sich bei dem Benutzer, der die App startet, um denselben Benutzer handelt, der sich ursprünglich mit einem registrierten Geschäfts-, Schul- oder Unikonto angemeldet hat. Wenn Endbenutzer ihre PIN konfigurieren, verwendet das Intune App SDK Azure Active Directory, um die Anmeldeinformationen der Endbenutzer mit den Daten des registrierten Intune-Kontos abzugleichen.

### <a name="require-users-to-enter-credentials-before-they-can-start-apps"></a>Erzwingen, dass Benutzer vor dem Starten von Apps Anmeldeinformationen eingeben
IT-Administratoren können erzwingen, dass Benutzer ihre Anmeldeinformationen eingeben, bevor sie eine von Intune verwaltete App starten können. Das Intune App SDK verwendet Azure Active Directory für die Bereitstellung von einmaligem Anmelden (SSO), damit die einmal eingegebenen Anmeldeinformationen auch für nachfolgende Anmeldungen gelten. Darüber hinaus wird auch die Authentifizierung von Lösungen für die Identitätsverwaltung [im Verbund mit Azure Active Directory](https://msdn.microsoft.com/library/azure/jj679342.aspx) unterstützt.

### <a name="check-device-health-and-compliance"></a>Überprüfen der Geräteintegrität und -compliance
IT-Administratoren können die Integrität des Geräts und dessen Compliance mit den Unternehmensrichtlinien abgleichen, bevor Endbenutzer auf von Intune verwaltete Apps zugreifen. Auf der iOS-Plattform überprüft diese Richtlinie, ob es sich um ein Gerät handelt, auf das ein Jailbreak angewendet wurde. Auf der Android-Plattform überprüft diese Richtlinie, ob es sich um ein Gerät handelt, das gerootet wurde.

### <a name="sdk-multi-identity-support"></a>SDK-Unterstützung von mehreren Identitäten
Die Unterstützung von mehreren Identitäten (Multi-Identity Support) ist ein Feature, das die Koexistenz von per Richtlinie verwalteten Geschäftskonten und nicht verwalteten Privatkonten in einer App gestattet.

So konfigurieren beispielsweise viele Benutzer in der Outlook-App für iOS und Android sowohl Unternehmens-E-Mail-Konten als auch private E-Mail-Konten. Wenn ein Benutzer auf Daten im Firmenkonto zugreift, muss der IT-Administrator sicher sein, dass die MAM-Richtlinienverwaltung angewendet wird. Wenn ein Benutzer jedoch auf ein privates E-Mail-Konto zugreift, sollten sich diese Daten außerhalb der Kontrolle des IT-Administrators befinden. In Microsoft Intune wird dies erreicht, indem die Verwaltungsrichtlinie nur auf das Unternehmenskonto in der Anwendung abzielt. Das Feature für mehrere Identitäten hilft Ihnen, das Datenschutzproblem zu lösen, mit dem sich Organisation auseinandersetzen müssen, die Geräte und Apps mit privaten und Geschäftskonten unterstützen.

* **Unterstützen mehrerer Identitäten**: Die APIs des Microsoft Intune App SDK ermöglichen Ihnen die Angabe eines Benutzerprinzipalnamens (User Principal Name, UPN) für bestimmte Datenvorgänge wie Zwischenablage- und Dateivorgänge. Das SDK verwendet den UPN zum Abgleichen des erfolgten Aufrufs des UPN, der beim Registrieren des Geräts bei Microsoft Intune verwendet wurde. Wenn sich die UPNs entsprechen, wird der Aufruf als ein Aufruf von Unternehmensdaten behandelt, und die Daten werden geschützt; wenn sich die UPNs nicht entsprechen, wird der Aufruf als Aufruf von privaten Daten behandelt, und die Daten werden nicht geschützt.

### <a name="app-management-without-device-enrollment"></a>App-Verwaltung ohne Geräteregistrierung

>[!IMPORTANT]
>Die Intune-Verwaltung mobiler Apps ohne Geräteregistrierung ist derzeit nur in Verbindung mit dem Intune App SDK für iOS verfügbar. 


Viele Benutzer von privaten Geräten möchten Unternehmensdaten anzeigen und verwenden können, ohne ihr privates Gerät bei einem MDM-Produkt (Mobile Device Management, Verwaltung von mobilen Geräten) registrieren zu müssen. Da die MDM-Registrierung eine globale Kontrolle des Geräts voraussetzt, sind viele Benutzer unsicher, ob sie diese globale Kontrolle über ihr privates Gerät an das Unternehmen übertragen können.

Dank der App-Verwaltung ohne Geräteregistrierung kann Microsoft Intune MAM-Richtlinien direkt in einer App bereitstellen, ohne den MDM-Kanal für diese Bereitstellung zu nutzen. Da kein MDM-Kanal benötigt wird, ist auch keine MDM-Registrierung erforderlich.



<!--HONumber=Dec16_HO2-->


