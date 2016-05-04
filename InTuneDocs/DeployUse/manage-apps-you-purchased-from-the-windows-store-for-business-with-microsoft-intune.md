---
title: Verwalten von apps, die Sie aus dem Windows Store für Unternehmen mit Microsoft Intune erworben
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1643dec0-51dc-4c3a-9dd3-23da496403d9
author: robstackmsft
---
# Verwalten von apps, die Sie aus dem Windows Store für Unternehmen mit Microsoft Intune erworben
Die [Windows Store für Business](https://www.microsoft.com/business-store) können Sie suchen und apps für Ihre Organisation erwerben, einzeln oder im Volume. Durch Verbinden des Speichers in Windows Intune, können Sie z. B. Volume erworbenen apps aus der Intune-Verwaltungskonsole verwalten:
* Sie können die Liste der apps synchronisieren, die Sie aus dem Speicher mit Intune erworben haben.
* Apps, die synchronisiert werden, die in der Intune-Verwaltungskonsole angezeigt werden, und Sie können diese wie alle anderen apps bereitstellen
* Sie können verfolgen, wie viele Lizenzen verfügbar sind und wie viele verwendet werden in der Intune-Verwaltungskonsole
* Intune blockiert, Bereitstellung und Installation von apps, wenn nicht genügend Lizenzen vorhanden sind

## Vorbereitung
Überprüfen Sie die folgenden Informationen, bevor Sie beginnen, Synchronisierung und Bereitstellung von apps aus dem Windows Store für Unternehmen:
* Sie müssen für Ihre Organisation Intune als Autorität zur Verwaltung mobiler Geräte konfigurieren. Weitere Informationen finden Sie unter [Autorität festlegen und Konfigurieren von Microsoft Intune](set-mobile-device-management-authority-and-configure-microsoft-intune.md)
* Sie müssen ein Konto in Windows Store für Business angemeldet haben
* Sobald Sie Intune Windows Business Store-Konto zugeordnet ist, können Sie nicht in der Zukunft an ein anderes Konto ändern.
* Apps, die aus dem Store erworben können nicht werden manuell hinzugefügt oder aus Intune gelöscht. Sie können nur mit dem Windows Store für Unternehmen synchronisiert werden.

## Ordnen Sie Ihre Windows Store für Business-Konto mit Intune
Bevor Sie die Synchronisierung in der Intune-Konsole aktivieren, müssen Sie die Verwendung von Intune als Verwaltungstool Store-Konto konfigurieren:
1. Stellen Sie sicher, dass Sie sich in den Speicher für Unternehmen mit demselben mandantenkonto, das Sie verwenden, um bei Intune anmelden.
2. Wählen Sie in den Speicher Business **Einstellungen** > **Verwaltungstools**.
3. Wählen Sie auf der Seite Management Tools **Fügen Sie ein Tool zur**, und wählen Sie Microsoft Intune.

Sie können nun fortfahren und Einrichten der Synchronisierung in der Intune-Konsole.

## Konfigurieren der Synchronisierung

1. In der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com), klicken Sie auf **Admin**.
2. In der **Verwaltung** Arbeitsbereich erweitern **Verwaltung mobiler Geräte**, und klicken Sie dann auf **Speicher für Business**.
3. Auf der **Windows Store für Business** Seite, gehen Sie folgendermaßen vor:
* Wenn Sie dies nicht bereits getan haben, klicken Sie auf den Link zur Anmeldung für den Windows Store für Unternehmen
* Nachdem Sie-angemeldet sind, klicken Sie auf **Synchronisierung konfigurieren**
4. In der **Konfigurieren Windows Store für Business-app-Synchronisierung** Wählen Sie im Dialogfeld **Enable Windows Store für Business-Synchronisierung**.
5. Aus der **Language** Dropdown-Liste, wählen Sie die Sprache in der aus dem Windows Store-apps für Unternehmen in der Intune-Konsole angezeigt wird. Unabhängig von der Sprache, in der sie angezeigt werden, werden sie in der Sprache des Endbenutzers, wenn verfügbar installiert werden.
6. Klicken Sie auf **OK**.

## Synchronisieren von apps

1. Auf der **Windows Store für Business** auf **Jetzt synchronisieren** die apps zu synchronisieren, Sie aus dem Speicher mit Intune erworben haben.
2. In der **Apps** Arbeitsbereich, klicken Sie auf **verwaltete Software** > **lizenzierte Software** verfügbaren apps anzeigen und überprüfen, ob Ihre erworbenen apps ordnungsgemäß importiert wurden.
Die apps in diesem Knoten werden angezeigt, mit der Gesamtzahl der Lizenzen, die Sie besitzen, zusammen mit der Anzahl der Lizenzen Ihnen zur Verfügung stehen.

## Bereitstellen von Apps

Durch das Bereitstellen von apps aus dem Speicher auf die gleiche Weise, die Sie anderen Intune-app bereitstellen. Weitere Informationen finden Sie unter [Bereitstellen von apps für mobile Geräte in Microsoft Intune](deploy-apps-to-mobile-devices-in-microsoft-intune.md).
Wenn Sie eine Windows Store-Geschäfts-app bereitstellen, wird eine Lizenz von jedem Benutzer verwendet, die die app installiert wird. Wenn Sie alle verfügbaren Lizenzen für eine bereitgestellte Anwendung verwenden, wird nicht in der Lage, mehrere Kopien bereitstellen, und Sie müssen eine der folgenden Aktionen ausführen:
* Deinstallieren Sie die app aus einige Geräte
* Reduzieren Sie den Umfang der aktuellen Bereitstellung nur die Benutzer als Ziel haben Sie über genügend Lizenzen für
* Kaufen Sie weitere Kopien der Anwendung aus dem Windows Store für Unternehmen


### Weitere Informationen:
[Bereitstellen von Apps für mobile Geräte in Microsoft Intune](deploy-apps-to-mobile-devices-in-microsoft-intune.md)




<!--HONumber=Mar16_HO4-->


