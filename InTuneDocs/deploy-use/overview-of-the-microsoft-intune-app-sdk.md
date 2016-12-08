---
title: "Übersicht über Microsoft Intune App SDK | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ef1751bb-3a2f-4662-a922-38c076869eb3
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 4cb153c601b83b113a22b2acf3da5200cdb70472


---

# <a name="overview-of-the-microsoft-intune-app-sdk"></a>Übersicht über Microsoft Intune App SDK
Das Intune App Software Development Kit (SDK) ist für iOS- und Android-Plattformen erhältlich und ermöglicht Verwaltungsfunktionen für mobile Anwendungen mit Microsoft Intune. Darüber soll die Menge der Codeänderungen für Entwickler reduziert werden.

Sie werden feststellen, dass Sie die meisten SDK-Funktionen aktivieren können, ohne das Verhalten Ihrer App ändern zu müssen. Um die Benutzerfreundlichkeit der App für Endbenutzer und IT-Administratoren zu verbessern, können Sie unsere APIs verwenden und so das App-Verhalten für Funktionen anpassen, die Ihre Mitwirkung erfordern.

Nachdem Sie Ihre App aktiviert haben, können IT-Administratoren Richtlinien für von Intune verwaltete Apps bereitstellen und die Vorteile dieser Features nutzen, um die Unternehmensdaten zu schützen.

# <a name="features"></a>Features
## <a name="control-users-ability-to-move-corporate-documents"></a>Steuern der Möglichkeit von Benutzern, Unternehmensdaten zu verschieben
IT-Administratoren können die Verlagerung von Dateien mit Unternehmensdaten in von Intune verwalteten Apps steuern. So kann beispielsweise eine Richtlinie bereitgestellt werden, mit verhindert wird, dass Unternehmensdaten mit Datensicherungs-Apps in der Cloud gespeichert werden.  

## <a name="configure-clipboard-restrictions"></a>Konfigurieren von Einschränkungen für die Zwischenablage
IT-Administratoren können in von Intune verwalteten Apps das Verhalten der Zwischenablage konfigurieren. So können sie beispielsweise eine Richtlinie implementieren, die dafür sorgt, dass Endbenutzer die Zwischenablage nicht verwenden können, um Daten aus von Intune verwalteten Apps auszuschneiden oder zu kopieren und in eine nicht verwaltete App zu kopieren.

## <a name="enforce-encryption-on-saved-data"></a>Erzwingen der Verschlüsselung von gespeicherten Daten
IT-Administratoren können mit einer Richtlinie erzwingen, dass auf dem Gerät gespeicherte Daten verschlüsselt werden.

## <a name="remotely-wipe-corporate-data"></a>Remotezurücksetzung von Unternehmensdaten
IT-Administratoren können Unternehmensdaten von einem mit Intune verwalteten Gerät löschen, wenn die Registrierung des Geräts in Microsoft Intune aufgehoben wurde. Dieses Feature basiert auf der Identität, und es werden nur Dateien gelöscht, die mit der Unternehmensidentität des Benutzers verbunden sind. Hierfür ist die Mitwirkung der App erforderlich. Die App kann die Identität, für die die Zurücksetzung erfolgen soll, basierend auf den Benutzereinstellungen festlegen. Fehlen solche spezifischen Benutzereinstellungen in der App, wird gemäß dem Standardverhalten vorgegangen, d. h. das Anwendungsverzeichnis wird gelöscht, und der Benutzer wird informiert, dass der Zugriff auf Unternehmensressourcen entfernt wurde.

## <a name="enforce-the-use-of-a-managed-browser"></a>Erzwingen der Verwendung eines verwalteten Browsers
IT-Administratoren können erzwingen, dass Benutzer zum Öffnen von Links in von Intune verwalteten Apps einen verwalteten Browser („Managed Browser“) verwenden müssen. Indem Endbenutzer den von Microsoft Intune verwalteten Browser verwenden, kann sichergestellt werden, dass Links in E-Mails in einem von Intune verwalteten E-Mail-Client innerhalb der Domäne der von Intune verwalteten Apps verbleiben.

## <a name="enforce-a-pin-policy"></a>Erzwingen einer PIN-Richtlinie
IT-Administratoren können eine PIN-Richtlinie beim Starten einer von Intune verwalteten App erzwingen. Diese Richtlinie trägt zur Sicherstellung bei, dass es sich bei den Endbenutzern, die ihre Geräte bei Microsoft Intune registriert haben, um die gleichen Personen handelt, die die Apps starten. Wenn Endbenutzer ihre PIN konfigurieren, verwendet das Intune App SDK Azure Active Directory, um die Anmeldeinformationen mit den Anmeldeinformationen bei der Geräteregistrierung abzugleichen.

## <a name="require-users-to-enter-credentials-before-they-can-start-apps"></a>Erzwingen, dass Benutzer vor dem Starten von Apps Anmeldeinformationen eingeben
IT-Administratoren können erzwingen, dass Endbenutzer ihre Anmeldeinformationen eingeben, bevor sie eine von Intune verwaltete App starten können. Das Intune App SDK verwendet Azure Active Directory, um eine Umgebung für einmaliges Anmelden bereitzustellen. Dies bedeutet, dass die Anmeldeinformationen, nachdem sie einmal eingegeben wurden, für nachfolgende Anmeldungen wiederverwendet werden. Darüber hinaus unterstützt das SDK auch die Authentifizierung von Lösungen für die Identitätsverwaltung, die [im Verbund mit Azure Active Directory](/active-directory/active-directory-aadconnect-federation-compatibility) verwendet werden.

## <a name="check-device-health-and-compliance"></a>Überprüfen der Geräteintegrität und -compliance
IT-Administratoren können die Integrität des Geräts und dessen Kompatibilität mit den Unternehmensrichtlinien abgleichen, bevor Endbenutzer auf von Intune verwaltete Apps zugreifen können. Auf der iOS-Plattform überprüft diese Richtlinie, ob es sich um ein Gerät handelt, auf das ein Jailbreak angewendet wurde. Auf der Android-Plattform überprüft diese Richtlinie, ob es sich um ein Gerät handelt, das gerootet wurde.  



<!--HONumber=Nov16_HO5-->


