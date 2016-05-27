---
# required metadata

title: Übersicht über Microsoft Intune App SDK | Microsoft Intune
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

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Übersicht über Microsoft Intune App SDK
Das Intune App Software Development Kit (SDK) ist für iOS- und Android-Plattformen erhältlich und ermöglicht Verwaltungsfunktionen für mobile Anwendungen mit Microsoft Intune. Darüber hinaus bemühen wir uns, die Menge der Codeänderungen für Entwickler zu reduzieren. Sie werden feststellen, dass Sie die meisten SDK-Funktionen aktivieren können, ohne das Verhalten Ihrer App ändern zu müssen. Um die Anwendung für Endbenutzer und IT-Administratoren zu verbessern, können Sie unsere APIs verwenden und so das App-Verhalten für Funktionen anpassen, die Ihre Mitwirkung erfordern. 

Nachdem Sie Ihre App aktiviert haben, können IT-Administratoren Richtlinien für von Intune verwaltete Apps bereitstellen und die Vorteile dieser Features nutzen, um die Unternehmensdaten zu schützen.

# Features
## Steuern der Möglichkeit von Benutzern, Unternehmensdaten zu verschieben
IT-Administratoren können die Verlagerung von Dateien mit Unternehmensdaten in von Intune verwalteten Apps steuern. So kann beispielsweise eine Richtlinie bereitgestellt werden, mit verhindert wird, dass Unternehmensdaten mit Datensicherungs-Apps in der Cloud gespeichert werden.  

## Konfigurieren von Einschränkungen für die Zwischenablage
IT-Administratoren können in von Intune verwalteten Apps das Verhalten der Zwischenablage konfigurieren. So können sie beispielsweise eine Richtlinie implementieren, die dafür sorgt, dass Endbenutzer nicht in der Lage sind, die Zwischenablage zu verwenden, um Daten aus von Intune verwalteten Apps auszuschneiden/zu kopieren und in eine nicht verwaltete App zu kopieren.

## Konfigurieren von Einschränkungen für Bildschirmaufnahmen
IT-Administratoren könne verhindern, dass Benutzer eine Bildschirmaufnahme erstellen, wenn eine von Intune verwaltete App angezeigt wird. Mit dieser Einschränkung werden die Erfassung und Weitergabe von vertraulichen Unternehmensinhalten verhindert. Dieses Feature steht nur für Android-Geräte zur Verfügung. 

## Erzwingen der Verschlüsselung von gespeicherten Daten
IT-Administratoren können mit einer Richtlinie erzwingen, dass auf dem Gerät gespeicherte Daten verschlüsselt werden.

## Remotezurücksetzung von Unternehmensdaten
IT-Administratoren können Unternehmensdaten von einem mit Intune verwalteten Gerät löschen, wenn die Registrierung des Geräts in Microsoft Intune aufgehoben wurde. Dieses Feature basiert auf der Identität, und es werden nur Dateien gelöscht, die mit der Unternehmensidentität des Benutzers verbunden sind. Hierfür ist die Mitwirkung der App erforderlich. Die App kann die Identität, für die die Zurücksetzung erfolgen soll, basierend auf den Benutzereinstellungen festlegen. Fehlen solche spezifischen Benutzereinstellungen in der App, wird gemäß dem Standardverhalten vorgegangen, d. h. das Anwendungsverzeichnis wird gelöscht, und der Benutzer wird informiert, dass der Zugriff auf Unternehmensressourcen entfernt wurde. 

## Erzwingen der Verwendung eines verwalteten Browsers
IT-Administratoren können die Verwendung eines verwalteten Browsers („Managed Browser“) beim Öffnen von Links in von Intune verwalteten Apps erzwingen. Die Verwendung von von Microsoft Intune verwalteten Browsern trägt zur Sicherstellung bei, dass Links in E-Mails (die sich in einem von Intune verwalteten Mailclient befinden) innerhalb der Domäne der von Intune verwalteten Apps verbleiben.

## Erzwingen einer PIN-Richtlinie
IT-Administratoren können eine PIN-Richtlinie beim Starten einer von Intune verwalteten App erzwingen. Diese Richtlinie trägt zur Sicherstellung bei, dass es sich bei den Endbenutzern, die ihre Geräte bei Microsoft Intune registriert haben, um die gleichen Personen handelt, die die Apps starten. Wenn Endbenutzer ihre PIN konfigurieren, verwendet das Intune App SDK Azure Active Directory, um die Anmeldeinformationen der Endbenutzer mit den Anmeldeinformationen bei der Geräteregistrierung abzugleichen. 

## Erzwingen, dass Benutzer vor dem Starten von Apps Anmeldeinformationen eingeben
IT-Administratoren können erzwingen, dass Benutzer ihre Anmeldeinformationen eingeben, bevor sie eine von Intune verwaltete App starten können. Das Intune App SDK verwendet Azure Active Directory für die Bereitstellung von einmaligem Anmelden (SSO), damit die einmal eingegebenen Anmeldeinformationen auch für nachfolgende Anmeldungen gelten. Darüber hinaus wird auch die Authentifizierung von Lösungen für die Identitätsverwaltung [im Verbund mit Azure Active Directory](https://msdn.microsoft.com/en-us/library/azure/jj679342.aspx) unterstützt.. 

## Überprüfen der Geräteintegrität und -compliance
IT-Administratoren können die Integrität des Geräts und dessen Compliance mit den Unternehmensrichtlinien abgleichen, bevor Endbenutzer auf von Intune verwaltete Apps zugreifen. Auf der iOS-Plattform überprüft diese Richtlinie, ob es sich um ein Gerät handelt, auf das ein Jailbreak angewendet wurde. Auf der Android-Plattform überprüft diese Richtlinie, ob es sich um ein Gerät handelt, das gerootet wurde.  




<!--HONumber=May16_HO1-->


