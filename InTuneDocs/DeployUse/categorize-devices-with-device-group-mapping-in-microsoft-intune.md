---
title: "Kategorisieren von Geräten mithilfe der Gerätegruppenzuordnung in Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e
ms.reviewer: sumitp
ms.suite: ems
ms.sourcegitcommit: bb30b8e61a768b15e2f09993f4dceae8f4e1bd8a
ms.openlocfilehash: 55f811153bf37048a4fcdfc6da301a5f181700c3


---

# Kategorisieren von Geräten mithilfe der Gerätegruppenzuordnung in Microsoft Intune
Verwenden Sie die **Gerätegruppenzuordnung** in Microsoft Intune zum Gruppieren von Geräten in Kategorien, die Sie definieren, damit Sie diese Geräte einfacher verwalten können. 

Die Gerätegruppenzuordnung verwendet den folgenden Workflow:
1. Sie erstellen Intune-Gerätegruppen für jede Kategorie, die Sie verwenden möchten.
2. Sie konfigurieren Regeln für die Gerätegruppenzuordnung, die die Kategorie zuordnen, die Sie für die erstellte Gerätegruppe auswählen.
3. Wenn Endbenutzer ihre Geräte registrieren, müssen sie eine Kategorie aus den von Ihnen konfigurierten Kategorien auswählen. Nach der Auswahl wird ihr Gerät automatisch zur entsprechenden Gerätegruppe hinzugefügt, die Sie erstellt haben.
4. Sie können diese Gerätegruppen dann zum Bereitstellen der Richtlinien und Apps verwenden.

Beispiele für Kategorien:
* Persönlich
* POS-Gerät (Point of Sale)
* Demogerät
* Sales
* Kontoführung
* Manager

Sie können jedoch beliebige gewünschte Kategorien konfigurieren.

## Konfigurieren der Gerätegruppenzuordnung
1. Für jede zu verwendende Gerätekategorie erstellen Sie eine Intune-Gerätegruppe. Informationen zum Erstellen von Gruppen finden Sie unter [Verwenden von Gruppen zum Verwalten von Benutzern und Geräten in Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).
2. Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Option **Verwaltung** aus.
3. Erweitern Sie im Arbeitsbereich **Verwaltung** die **Verwaltung mobiler Geräte**, und wählen Sie anschließend **Gerätegruppenzuordnung** aus.
4. Aktivieren Sie auf der Seite **Gerätegruppenzuordnung** die Gerätegruppenzuordnung.
5. Wählen Sie **Hinzufügen** aus, um eine neue Zuordnungsregel zu erstellen.
6. Geben Sie im Dialogfeld **Regel für Gerätegruppenzuordnung hinzufügen** den Namen der zu erstellenden Kategorie ein. Wählen Sie dann aus der Dropdownliste die Gerätesammlung aus, der Sie diese Kategorie zuordnen möchten. Wählen Sie **Hinzufügen** aus, wenn Sie fertig sind.
7. Wenn Sie das Hinzufügen von Kategorien und Gruppen abgeschlossen haben, wählen Sie **Speichern** aus.

Wenn Benutzer ihre Geräte jetzt registrieren, wird ihnen eine Liste der von Ihnen konfigurierten Kategorien angezeigt. Nachdem sie eine Kategorie ausgewählt und die Registrierung abgeschlossen haben, wird ihr Gerät zu der Gerätegruppe hinzugefügt, die der gewählten Kategorie entspricht.

### Weitere Informationen:
[Verwenden von Gruppen zum Verwalten von Benutzern und Geräten in Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)


<!--HONumber=Jun16_HO3-->


