---
title: Wo ist meine Intune-Funktion in Azure jetzt?
titleSuffix: Intune Azure preview
description: 'Intune Azure-Preview: Hilft Ihnen bei der Suche nach Intune-Funktionen in der Azure-Konsole.'
keywords: 
author: dagerrit
ms.author: dagerrit
manager: angrobe
ms.date: 03/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 6a6b64465c95a3edd6fc2e2d4ae3da80ba3367ee
ms.openlocfilehash: 92bd41aa4acc02e67e983c68f818bd656b0b9608
ms.lasthandoff: 04/12/2017


---
# <a name="where-did-my-intune-feature-go-in-azure"></a>Wo ist meine Intune-Funktion in Azure jetzt?
Wir hatten die Chance, einige Aufgaben logischer zu organisieren, als wir Intune in das Azure-Portal umgezogen haben. Jedoch kommt jede Verbesserung mit der neuen Aufgabe, die neue Organisation kennenzulernen. Daher haben wir dieses Referenzhandbuch für diejenigen von Ihnen erstellt, die mit Intune in der klassischen Konsole bestens vertraut sind und sich nun fragen, wie Aufgaben in Intune unter Azure erledigt werden. Wenn dieser Artikel eine Funktion, die Sie suchen, nicht behandelt, hinterlassen Sie einen Kommentar am Ende des Artikels, damit wir ihn aktualisieren können.
## <a name="quick-reference-guide"></a>Handbuch mit Kurzübersicht
|Funktion |Pfad in der klassischen Konsole|Pfad in Intune unter Azure| |------------||---------------|---------------|
|Geräteregistrierungsprogramm (DEP) |Administrator > Verwaltung mobiler Geräte > iOS und Mac OS X > Programm zur Geräteregistrierung|[Geräteregistrierung > Apple-Registrierung > Enrollment Program-Token](#where-did-apple-dep-go) |
|Geräteregistrierungsprogramm (DEP) |Administrator > Verwaltung mobiler Geräte > iOS und Mac OS X > Programm zur Geräteregistrierung |[Geräteregistrierung > Apple-Registrierung > Seriennummern des Registrierungsprogramms](#where-did-apple-dep-go) |
|Registrierungsregeln |Administrator > Verwaltung mobiler Geräte > Registrierungsregeln|[Registrieren von Geräten > Registrierungseinschränkungen](#where-did-enrollment-rules-go) |
|Gruppen nach iOS-Seriennummer |Gruppen > Alle Geräte > Vorabregistrierte Unternehmensgeräte > Nach iOS-Seriennummer|[Registrieren von Geräten > Apple-Registrierung > Seriennummern des Registrierungsprogramms](#where-did-corporate-pre-enrolled-devices-go) |
|Gruppen nach iOS-Seriennummer |Gruppen > Alle Geräte > Vorabregistrierte Unternehmensgeräte > Nach iOS-Seriennummer| [Registrieren von Geräten | Apple-Registrierung > AC-Seriennummern](#where-did-corporate-pre-enrolled-devices-go)|
|Gruppen nach IMEI (Alle Plattformen)| Gruppen > Alle Geräte > Vorabregistrierte Unternehmensgeräte > Nach IMEI (Alle Plattformen) | [Registrieren von Geräten > Bezeichner von Unternehmensgeräten](#by-imei-all-platforms)|
| Profil für die Unternehmensgeräteregistrierung| Richtlinie > Unternehmensgeräteregistrierung | [Registrieren von Geräten > Apple-Registrierung > Enrollment Program Profiles (Profile für das Registrierungsprogramm)](#where-did-corporate-pre-enrolled-devices-go) |
| Profil für die Unternehmensgeräteregistrierung | Richtlinie > Unternehmensgeräteregistrierung | [Registrieren von Geräten > Apple-Registrierung > AC-Profile](#where-did-corporate-pre-enrolled-devices-go) |


## <a name="where-do-i-manage-groups"></a>Wo verwalte ich Gruppen?
Intune unter Azure verwendet [Azure Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal) zum Verwalten von Gruppen.

## <a name="where-did-enrollment-rules-go"></a>Wo sind die Registrierungsregeln hin?
In der klassischen Konsole konnten Sie Regeln festlegen, die die MDM-Registrierung mobiler und moderner Windows- und macOS-Geräte gesteuert haben:

![Abbildung der klassischen Registrierungsregeln für mobile Geräte](./media/ui-changes/01-classic-rules.png)

Diese Regeln galten ausnahmslos für alle Benutzer in Ihrem Intune-Konto. Im Azure-Portal werden diese Regeln nun in zwei unterschiedlichen Typen von Richtlinien dargestellt: Gerätetypbeschränkungen und Einschränkungen zum Gerätelimit:

![Abbildung der Registrierungseinschränkungen für mobile Azure-Geräte](./media/ui-changes/02-azure-enroll-restrictions.png)

Die Standardeinschränkung zum Gerätelimit entspricht dem Grenzwert für die Geräteregistrierung in der klassischen Konsole:

![Abbildung der Einschränkungen zum Gerätelimit für Azure](./media/ui-changes/03-azure-device-limit.png)

Die Standardeinschränkungen des Gerätetyps entspricht den Plattformeinstellungen in der klassischen Konsole:

![Abbildung von Gerätetypeinschränkungen für Azure](./media/ui-changes/04-azure-platform-restrictions.png)

Die Möglichkeit, persönliche Geräte zuzulassen oder zu blockieren, wird nun unter den Plattformkonfigurationen der Gerätetypeinschränkungen verwaltet:

![Abbildung der Blockiereinstellungen von persönlichen Azure-Geräten](./media/ui-changes/05-azure-personal-block.png)

Neue Funktionen zur Einschränkung werden nur zum Azure-Portal hinzugefügt.

## <a name="where-did-apple-dep-go"></a>Wo ist Apple-DEP jetzt?
In der klassischen Konsole konnten Sie Intune so festlegen, dass es im Geräteregistrierungsprogramm von Apple integriert wurde, und Sie konnten die Synchronisierung mit dem Apple-Dienst manuell anfordern:

![Bild des klassischen DEP-Token](./media/ui-changes/06-classic-dep-token.png)

Im Azure-Portal richten das Geräteregistrierungsprogramm von Apple mit den gleichen Schritten wie in der klassischen Intune-Konsole ein:

![Abbildung des Azure-DEP-Token](./media/ui-changes/07-azure-dep-token.png)

Jedoch wurde die Option **Synchronisierung** in der klassischen Konsole zum Workflow der Verwaltung von Seriennummern verschoben, da die Ergebnisse der manuellen Synchronisierung dort erscheinen werden:

![Abbildung der Azure-DEP-Synchronisation](./media/ui-changes/08-azure-dep-sync.png)

## <a name="where-did-corporate-pre-enrolled-devices-go"></a>Wo sind die vorabregistrierten Unternehmensgeräte jetzt?
### <a name="by-ios-serial-number"></a>Nach iOS-Seriennummer
In der klassischen-Konsole können Sie iOS-Geräte über das Apple-Geräteregistrierungsprogramm (DEP) und das Apple Configurator-Tool registrieren. Beide Methoden bieten Gerätevorabregistrierung durch Seriennummern und umfassen die Zuweisung spezieller Geräteregistrierungsprofile. Vor der Registrierung kann die Registrierungsprofilzuweisung über die Gerätegruppe **Corporate Pre-enrolled Device by iOS Serial Number** (Vorabregistriertes Unternehmensgerät nach iOS-Seriennummer) verwaltet werden:

![Abbildung der klassischen Apple-Seriennummern](./media/ui-changes/09-classic-apple-serials.png)

Hier werden Seriennummern für die Apple-DEP- und die Configurator-Registrierung in einer einzigen Liste aufgeführt: Um Profilzuweisungskonflikte zu reduzieren (DEP-Profile zu AC-Seriennummern und andersherum), haben wir die Seriennummern in zwei Listen im Azure-Portal aufgeteilt:

**DEP-Seriennummern**
![Abbildung von Azure DEP-Seriennummern](./media/ui-changes/10-azure-dep-serials.png)

**Apple Configurator-Seriennummern**
![Abbildung der Azure Apple Configurator-Seriennummern](./media/ui-changes/11-azure-ac-serials.png)

### <a name="by-imei-all-platforms"></a>Durch IMEI (Alle Plattformen)

In der klassischen-Konsole können Sie vorab IMEI-Nummern von Geräten auflisten, um sie als unternehmenseigen zu markieren, wenn Sie in Intune registriert werden:

![Abbildung der klassischen Liste von IMEI-Nummern](./media/ui-changes/12-classic-corp-imei.png)

In der Azure-Konsole müssen Sie die gleiche IMEI-Liste der unternehmenseigenen Geräte-IDs mit einer durch eine Datei mit durch Trennzeichen getrennte Werte (.csv) hochladen. Das neue Portal unterstützt keine manuelle Eingabe der IMEI-Nummern:

![Abbildung der Azure-Liste der IMEI-Nummern](./media/ui-changes/13-azure-corp-imei.png)

Intune im Azure-Portal wird zukünftig andere Typen von Bezeichnern neben IMEI unterstützen, lässt derzeit jedoch nur IMEI-Nummern für die Vorabauflistung zu.

## <a name="where-did-corporate-device-enrollment-profiles-go"></a>Wo befinden sich die Profile für die Unternehmensgeräteregistrierung jetzt?
Zum Registrieren von iOS-Geräten über das Apple-Geräteregistrierungsprogramm oder mit dem Apple Configurator-Tool müssen Sie ein Tool zur Unternehmensgeräteregistrierung bereitstellen, dem das Gerät zugewiesen wird. In der klassischen Konsole befand sich die Erstellung und Verwaltung dieser Profile in einer Liste:

![Abbildung der klassischen Geräteregistrierungsprofile](./media/ui-changes/14-classic-corp-profiles.png)

Dieses Liste zeigt die Profile, die für den Gebrauch mit dem Apple-Geräteregistrierungsprogramm (**DEP On** (DEP aktiviert)) und Profile, die nur für den Gebrauch mit dem Apple Configurator Tool zulässig sind (**DEP Off** (DEP deaktiviert)).

Um Verwechslungen zwischen den beiden Profiltypen und potenzielle nicht übereinstimmende Zuweisungen zu minimieren (DEP-Profil zu Configurator-Geräte und andersherum), haben wir die Erstellung und Verwaltung der Profile für das Registrierungsprogramm (die jeweils das Apple-Geräteregistrierungsprogramm und Apple School Manager unterstützen) sowie Apple Configurator-Profile getrennt:

**DEP-Profile**
![Abbildung von Azure DEP-Profilen](./media/ui-changes/15-azure-dep-profiles.png)

**Apple Configurator-Profile**
![Abbildung der Azure Apple Configurator-Profile](./media/ui-changes/16-azure-ac-profiles.png)

