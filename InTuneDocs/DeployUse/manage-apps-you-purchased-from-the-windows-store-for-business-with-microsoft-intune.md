---
title: "Verwalten von Apps, die im Windows Store für Unternehmen erworben wurden | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e38d47d-0c5e-40ce-b379-29d3657f5c28
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 42e21b802fb605c98f688485c3b77703b3950e94
ms.openlocfilehash: b6e2f0ec13caa9616b72a2fa225e77fe43a4755c


---

# Verwalten von Apps, die im Windows Store für Unternehmen erworben wurden, mit Microsoft Intune
Im [Windows Store für Unternehmen](https://www.microsoft.com/business-store) können Sie Apps für Ihre Organisation suchen und einzeln oder im Rahmen eines Volumenprogramms erwerben. Indem Sie den Store mit Windows Intune verbinden, können Sie im Rahmen von Volumenprogrammen erworbene Apps über die Intune-Verwaltungskonsole verwalten, z. B.:
* Sie können die Liste der Apps, die Sie im Speicher erworben haben, mit Intune synchronisieren.
* Synchronisierte Apps werden in der Intune-Verwaltungskonsole angezeigt und können wie alle anderen Apps bereitgestellt werden.
* Sie können in der Intune-Verwaltungskonsole die Anzahl der verfügbaren und der verwendeten Lizenzen verfolgen.
* Intune blockiert die Bereitstellung und Installation von Apps, wenn nicht genügend Lizenzen vorhanden sind.

## Vorbereitung
Überprüfen Sie die folgenden Informationen, bevor Sie beginnen, Apps aus dem Windows Store für Unternehmen zu synchronisieren und bereitzustellen:
* Sie müssen Intune als Autorität zur Verwaltung mobiler Geräte für Ihre Organisation konfigurieren. Weitere Informationen finden Sie unter [Vorbereiten der Registrierung von Geräten in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md).
* Sie müssen ein Konto im Windows Store für Unternehmen registriert haben.
* Sobald ein Konto für den Windows Store für Unternehmen Intune zugeordnet wurde, können Sie dieses zugeordnete Konto nicht mehr ändern.
* Apps, die im Windows Store für Unternehmen erworben wurden, können nicht manuell zu Intune hinzugefügt oder aus Intune gelöscht werden. Sie können nur mit dem Windows Store für Unternehmen synchronisiert werden.
* Intune synchronisiert nur online lizenzierte Apps, die Sie aus dem Windows Store für Unternehmen erworben haben.
* Geräte müssen mit der Active Directory-Domäne oder dem Arbeitsbereich verknüpft sein, damit diese Funktion verwendet werden kann.
* Registrierte Geräte müssen die Version 1511 von Windows 10 verwenden.

## Verknüpfen Ihres Kontos für den Windows Store für Unternehmen mit Intune
Bevor Sie die Synchronisierung in der Intune-Konsole aktivieren, müssen Sie Ihr Konto für den Windows Store für Unternehmen so konfigurieren, dass Intune als Verwaltungstool verwendet wird:
1. Stellen Sie sicher, dass Sie sich beim Windows Store für Unternehmen und bei Intune mit demselben Mandantenkonto anmelden.
2. Wählen Sie im Windows Store für Unternehmen **Einstellungen** > **Verwaltungstools** aus.
3. Wählen Sie auf der Seite „Verwaltungstools“ die Option **Verwaltungstools hinzufügen** und dann „Microsoft Intune“ aus.

Sie können nun fortfahren und die Synchronisierung in der Intune-Konsole einrichten.

## Konfigurieren der Synchronisierung

1. Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) auf **Verwaltung**.
2. Erweitern Sie im Arbeitsbereich **Verwaltung** den Knoten **Verwaltung mobiler Geräte**, und klicken Sie dann **Store für Geschäfte**.
3. Gehen Sie auf der Seite **Windows Store für Unternehmen** folgendermaßen vor:
* Klicken Sie auf den Link zur Registrierung für den Windows Store für Unternehmen, falls Sie dies noch nicht getan haben.
* Nachdem Sie sich registriert haben, klicken Sie auf **Synchronisierung konfigurieren**.
4. Wählen Sie im Dialogfeld **App-Synchronisierung mit dem Windows Store für Geschäfte konfigurieren** die Option **Synchronisierung mit dem Windows Store für Geschäfte aktivieren** aus.
5. Wählen Sie aus der Dropdownliste **Sprache** die Sprache aus, in der Apps aus dem Windows Store für Unternehmen in der Intune-Konsole angezeigt werden. Die Installation der Apps erfolgt unabhängig von der Anzeigesprache in der Sprache des Endbenutzers, sofern verfügbar.
6. Klicken Sie auf **OK**.

## Synchronisieren von Apps

1. Klicken Sie auf der Seite **Windows Store für Unternehmen** auf **Jetzt synchronisieren**, um die im Store erworbenen Apps mit Intune zu synchronisieren.
2. Klicken Sie im Arbeitsbereich **Apps** auf **Verwaltete Software** > **Lizenzierte Software**, um die verfügbaren Apps anzuzeigen und zu überprüfen, ob Ihre erworbenen Apps fehlerfrei importiert wurden.
Die Apps werden in diesem Knoten mit der Gesamtzahl der Lizenzen, die Sie besitzen, und der Anzahl der Lizenzen, die Ihnen zur Verfügung stehen, angezeigt.

## Bereitstellen von Apps

Sie stellen Apps aus dem Store auf die gleiche Weise wie andere Intune-Apps bereit. Weitere Informationen finden Sie unter [Bereitstellen von Apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md).
Wenn Sie eine App aus dem Windows Store für Unternehmen bereitstellen, wird von jedem Benutzer, der die App installiert, eine Lizenz verwendet. Wenn alle verfügbaren Lizenzen für eine bereitgestellte App verwendet werden, können keine Kopien der App mehr bereitgestellt werden, und Sie müssen eine der folgenden Aktionen ausführen:
* Deinstallieren der App auf einigen Geräten
* Beschränken der aktuellen Bereitstellung auf die Anzahl von Benutzern, für die Sie über Lizenzen verfügen
* Kaufen weiterer Kopien der App aus dem Windows Store für Unternehmen


### Weitere Informationen:
[Hinzufügen von Apps für mobile Geräte in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md)





<!--HONumber=Jun16_HO4-->


