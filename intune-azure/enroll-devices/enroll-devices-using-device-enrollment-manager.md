---
title: "Registrieren von Geräten – Geräteregistrierungs-Manager | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Verwenden Sie den Geräteregistrierungs-Manager für die Registrierung von Geräten in Intune. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: 78eca605a277c1e0fc750900ece028d8f2c7c5b2
ms.lasthandoff: 02/15/2017

---

# <a name="enroll-devices-using-device-enrollment-manager"></a>Registrieren von Geräten mithilfe des Geräteregistrierungs-Managers

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Mit Intune können Organisationen eine Vielzahl mobiler Geräte mit einem einzelnen Benutzerkonto verwalten. Das Konto *Geräteregistrierungs-Manager* (device enrollment manager, DEM) ist ein spezielles Benutzerkonto mit dem bis zu 1.000 Geräte registriert werden können. Sie fügen vorhandene Benutzer zum Konto des Geräteregistrierungs-Managers (DEM) hinzu, damit diese bestimmte DEM-Fähigkeiten erhalten. Jedes registrierte Gerät verwendet eine Einzellizenz. Es empfiehlt sich, Geräte zu verwenden, die mithilfe dieses Kontos als freigegebene Geräte registriert wurden, statt persönlicher („BYOD“) Geräte.  

Es müssen Benutzer im Azure-Portal vorhanden sein, damit sie als Geräteregistrierungs-Manager hinzugefügt werden können. Für die optimale Sicherheit darf der DEM-Benutzer nicht zusätzlich Intune-Administrator sein.

>[!NOTE]
>Die Registrierungsmethode des Geräteemulator-Managers kann nicht den folgenden anderen Registrierungsmethoden verwendet werden: [Apple Configurator mit Setup-Assistent](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md), [Apple Configurator mit direkter Registrierung](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md) oder [Programm zur Geräteregistrierung](enroll-ios-devices-using-device-enrollment-program.md). 

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Beispiel für ein Geräteregistrierungs-Manager-Szenario:

Ein Restaurant möchte 50 Point-of-Sale-Tablets für sein Bedienpersonal bereitstellen sowie Bestellmonitore für seine Küchenmitarbeiter. Die Mitarbeiter müssen niemals auf Unternehmensdaten zugreifen und sich nie als Benutzer anmelden. Der Intune-Administrator erstellt ein Geräteregistrierungs-Manager-Konto und fügt einen Vorgesetzten des Restaurants zum DEM-Konto hinzu, dieser erhält also DEM-Fähigkeiten. Der Vorgesetzte kann nun die 50 Tablets registrieren, indem er die DEM-Anmeldeinformationen verwendet.

Nur Benutzer in der Intune-Konsole können Geräteregistrierungs-Manager sein. Der Geräteregistrierungs-Manager kann kein Intune-Administrator sein.

Der DEM-Benutzer kann Folgendes tun:

-   Registrieren von bis zu 1000 Geräten in Intune
-   Anmelden beim Unternehmensportal, um Unternehmens-Apps abzurufen
-   Konfigurieren des Zugriffs auf Unternehmensdaten durch Bereitstellen von rollenspezifischen Apps auf den Tablets

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Einschränkungen der Geräte, die mit dem DEM Konto angemeldet sind

Für Geräte, die mit einem Geräteregistrierungs-Manager-Konto registriert wurden, gelten folgende Einschränkungen:

  - Es gibt keinen speziellen „Gerätebenutzer“. Das heißt, es ist kein E-Mail-Zugriff und kein Zugriff auf Unternehmensdaten möglich. Allerdings können z.B. die Geräte-Apps noch immer dazu verwendet werden, um über VPN auf Daten zuzugreifen.

  - Kein bedingter Zugriff, da dies benutzerspezifische Szenarien voraussetzen würde.

  - Der DEM-Benutzer kann die Registrierung von DEM-Geräten auf dem Gerät mit dem Unternehmensportal nicht aufheben. Der Intune-Administrator hat diese Fähigkeit, der DEM-Benutzer jedoch nicht.

  - Nur das lokale Gerät erscheint in der Unternehmensportal-App oder -Website.
 
  - Benutzer können Apps aus dem Apple Volume Purchase Program (VPP) nicht verwenden, weil für die Verwaltung dieser Apps benutzerspezifische Apple-IDs erforderlich sind.
 
  - (Nur iOS) Wenn Sie DEM zur Registrierung von iOS-Geräten verwenden, können Sie Apple Configurator oder das Apple-Programm zur Geräteregistrierung nicht zum Registrieren von Geräten verwenden.


> [!NOTE]
> Um Unternehmens-Apps auf Geräten bereitzustellen, die mit dem Geräteregistrierungs-Manager verwaltet werden, stellen Sie die Unternehmensportal-App als **erforderliche Installation** für das Benutzerkonto des Geräteregistrierungs-Managers bereit.
> Zur Verbesserung der Leistung werden beim Anzeigen der Unternehmensportal-App auf einem mit dem Geräteregistrierungs-Manager verwalteten Gerät nur das lokale Gerät angezeigt. Für die Remoteverwaltung anderer vom Geräteregistrierungs-Manager verwalteter Geräte muss die Intune-Verwaltungskonsole verwendet werden.


## <a name="add-a-device-enrollment-manager"></a>Hinzufügen eines Geräteregistrierungs-Managers

1.  Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

2.  Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Geräteregistrierungs-Manager** aus.

3.  Wählen Sie **Hinzufügen** aus.

4.  Geben Sie auf dem Blatt **Benutzer hinzufügen** einen Benutzerprinzipalnamen für den Geräteregistrierungs-Manager-Benutzer ein, und wählen Sie **Hinzufügen** aus. Der Geräteregistrierungs-Manager-Benutzer wird der Liste der Geräteregistrierungs-Manager-Benutzer hinzugefügt.

## <a name="remove-a-device-enrollment-manager"></a>Entfernen eines Geräteregistrierungs-Managers

Wenn Sie einen Geräteregistrierungs-Manager entfernen, wirkt sich dies nicht auf registrierte Geräte aus. Wenn ein Geräteregistrierungs-Manager entfernt wird:

-   Das Entfernen eines Benutzers aus der Liste der Geräteregistrierungs-Manager-Benutzer hat keine Auswirkungen auf registrierte Geräte, die registrierten Geräte können weiterhin vollständig verwaltet werden.

-   Die Anmeldedaten für das entfernte Geräteregistrierungs-Manager-Konto bleiben gültig.

-   Der entfernte Geräteregistrierungs-Manager kann weiterhin keine Geräte zurücksetzen oder deaktivieren.

-   Der entfernte Geräteregistrierungs-Manager kann so lange zusätzliche Geräte registrieren, bis das durch den Intune-Administrator konfigurierte gerätespezifische Limit erreicht wurde.

**So entfernen Sie einen Geräteregistrierungs-Manager**

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

2. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Geräteregistrierungs-Manager** aus.

3. Klicken Sie auf dem Blatt **Geräteregistrierungs-Manager** mit der rechten Maustaste auf den Geräteregistrierungs-Manager-Benutzer, und wählen Sie **Entfernen** aus.

## <a name="view-the-properties-of-a-device-enrollment-manager"></a>Anzeigen der Eigenschaften des Geräteregistrierungs-Managers

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

2. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Geräteregistrierungs-Manager** aus.

3. Klicken Sie auf dem Blatt **Geräteregistrierungs-Manager** mit der rechten Maustaste auf den Geräteregistrierungs-Manager-Benutzer, und wählen Sie **Eigenschaften** aus.

