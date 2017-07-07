---
title: "Testen und Überprüfen von Intune"
description: "Dieser Artikel hilft Ihnen bei allen Details, die beim Testen und Überprüfen einer reinen Intune-Cloudlösung in Ihrer Umgebung berücksichtigt werden müssen."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4f82ee0c-4bd6-4623-9b10-9249d316ccf5
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4ea2974c4724564cd8f9972fdb238b06d1b100e6
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2017
---
# <a name="intune-testing-and-validation"></a>Testen und Überprüfen von Intune

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Die Testphase sollte während und nach der Implementierungsphase stattfinden. Sie benötigen Testkonten, -gruppen und -geräte zum Testen aller zuvor ermittelten erforderlichen IT- (Administration) und Endbenutzerszenarien (Anwendungsfall).

Es wird empfohlen, Ihre IT-Support-/Helpdeskmitarbeiter in die Testphase einzubeziehen, damit sie eine Supportdokumentation erstellen und sich mit der Unterstützung des Produkts vertraut machen. Wenn eine Komponente oder ein Szenario auf der Grundlage der Anwendungsfälle nicht funktioniert, stellen Sie sicher, dass die notwendigen Änderungen dokumentiert werden. Geben Sie dabei den Grund für die Änderung an.

## <a name="before-you-begin"></a>Vorbereitung

Es wird empfohlen, Folgendes zu dokumentieren:

-   **Testkriterien:** Identifiziert die Benchmarks, anhand derer die Messung erfolgt.

-   **Entwurfskomponenten:** Müssen in mindestens einem Testkriterium vorhanden sein.

Wenn eine Entwurfskomponente nicht in mindestens einem auf eine Anforderung oder ein Szenario ausgerichteten Testkriterium vorhanden ist, überlegen Sie, ob die Entwurfskomponente erforderlich ist oder nicht. Stellen Sie darüber hinaus sicher, dass die folgenden Elemente vorhanden sind:

-   **Konten:** Die für das Testen verwendeten Konten müssen Testkonten sein, die für EMS und Office 365 lizenziert sind, um alle Anwendungsszenarien testen zu können.

-   **Geräte:** Die zu diesem Zeitpunkt verwendeten Geräte müssen Testgeräte sein, die potenziell bereinigt oder auf die werkseitigen Standardeinstellungen zurückgesetzt werden können.

-   **Integrationskomponenten:** Alle Integrationskomponenten (Certificate Connector, dienstübergreifender Intune-Connector für gehostetes Exchange und Intune-Connector für lokale Exchange-Umgebungen) müssen bei Bedarf installiert und konfiguriert werden.

Entwurfsänderungen könnte erforderlich sein, um unvorhergesehene Probleme zu berücksichtigen. Darüber hinaus müssen alle Entwurfsänderungen vollständig zusammen mit der jeweiligen Begründung dokumentiert werden. Hier sehen Sie ein Beispiel für die Veranschaulichung einer Änderung:

-   Sie stellen vielleicht fest, dass Sie die Anforderungen des Registrierungsdiensts für Netzwerkgeräte (SCEP) nicht erfüllen. Zudem erfahren Sie, dass die VPN- und WLAN-Profile mit einer Stammzertifizierungsstelle konfiguriert werden können, die dieselben Anforderungen ohne eine SCEP-Implementierung erfüllt.

Möglicherweise gibt es Herausforderungen oder Probleme, die technische Hilfe oder eine spezielle Problembehandlung während des Test- und Überprüfungsprozesses erfordern. Es wird empfohlen, sich an die Microsoft-Supportkanäle zu wenden.

-   [Informationen zum Erhalten von Intune-Support](/intune-classic/troubleshoot/how-to-get-support-for-microsoft-intune)

-   [Allgemeine Tipps zur Problembehandlung für Microsoft Intune](/intune-classic/troubleshoot/general-troubleshooting-tips-for-microsoft-intune)

-   [Informationen zum Erhalten von Support für Microsoft Intune](/intune-classic/troubleshoot/how-to-get-support-for-microsoft-intune)

-   [Kontaktieren des telefonischen Supports für Microsoft Intune](/intune-classic/troubleshoot/contact-assisted-phone-support-for-microsoft-intune)

## <a name="functional-validation-testing"></a>Test zur Funktionsüberprüfung

Bei der Funktionsüberprüfung werden die einzelnen Komponenten und die Konfiguration getestet, um deren ordnungsgemäße Funktionsweise zu überprüfen. Ein Beispiel für einen Überprüfungstest ist in der folgenden Tabelle aufgeführt.

![Abschnitt 9 Tabelle 1](./media/section-9-image-1-table.PNG)

## <a name="use-case-validation-testing"></a>Test zur Anwendungsfallüberprüfung

Der Test zur Anwendungsfallüberprüfung sollte durchgeführt werden, um sicherzustellen, dass die Szenarien vollständig und funktionsfähig sind. Es gibt zwei Arten von Anwendungsszenarien: IT-Administrator und Endbenutzer.

### <a name="it-admin"></a>IT-Administrator

Überprüfungstests für IT-Administratoren sollten durchgeführt werden, um sicherzustellen, dass administrative Aktionen für ein Gerät oder einen Benutzer ordnungsgemäß funktionieren. Es folgt ein Beispiel für ein umfassendes Überprüfungsszenario für IT-Administratoren.

![Abschnitt 9 Tabelle 2](./media/section-9-image-2-table.PNG)

### <a name="end-user"></a>Endbenutzer

Überprüfungstests für Endbenutzer sollten ausgeführt werden, um sicherzustellen, dass das Endbenutzererlebnis den Erwartungen entspricht und in der gesamten Benutzerkommunikation korrekt dargestellt wird. Es ist wichtig, die Korrektheit des Endbenutzererlebnisses zu überprüfen, da Überprüfungsfehler zu einer niedrigeren Akzeptanz und einer höheren Anzahl von Helpdeskanrufen führen können.

![Abschnitt 9 Tabelle 3](./media/section-9-image-3-table.PNG)

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie Ihre Intune-Funktionen und -Anwendungsszenarien getestet und überprüft haben, sind Sie für den Intune-Rollout in die Produktion bereit. Weitere Informationen finden Sie unter [Weitere Ressourcen](planning-guide-resources.md).
