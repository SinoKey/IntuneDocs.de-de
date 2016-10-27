---
title: "Kategorisieren von Geräten mithilfe der Gerätegruppenzuordnung in Microsoft Intune | Microsoft Intune"
description: "Verwenden Sie die Gerätegruppenzuordnung in Microsoft Intune, um Geräte in von Ihnen definierte Kategorien zu gruppieren, damit Sie diese Geräte einfacher verwalten können."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e
ms.reviewer: sumitp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 32bded5047b1a08738418e3e36382eeae1a5f3b4
ms.openlocfilehash: 84850f4e9136e6304e51991d6ab0a0ae2a37e7a7


---

# Kategorisieren von Geräten mithilfe der Gerätegruppenzuordnung in Microsoft Intune
Verwenden Sie die **Gerätegruppenzuordnung** in Microsoft Intune, damit Geräte basierend auf Kategorien, die Sie definieren, automatisch zu Gruppen hinzugefügt werden, sodass Sie diese Geräte einfacher verwalten können. 

Die Gerätegruppenzuordnung verwendet den folgenden Workflow:
1. Erstellen Sie Kategorien, die Benutzer beim Registrieren ihrer Geräte verwenden können.
2. Sie erstellen für jede Kategorie, die Sie verwenden möchten, Gruppen, oder Sie verwenden vorhandene Gruppen. Je nach verwendeter Intune-Version handelt es sich dabei entweder um Intune-Gruppen oder um Azure Active Directory-Sicherheitsgruppen.
2. Sie konfigurieren Regeln, mit denen die Kategorie zugeordnet wird, die Sie für die erstellte Gerätegruppe auswählen.
3. Wenn Endbenutzer ihre Geräte registrieren, müssen sie eine Kategorie aus der Liste mit den von Ihnen konfigurierten Kategorien auswählen. Nach der Auswahl wird ihr Gerät automatisch zur entsprechenden Gruppe hinzugefügt, die Sie erstellt haben. Wenn ein Gerät bereits registriert ist, wird der Benutzer beim nächsten Aufruf der Unternehmensportal-App aufgefordert, eine Kategorie auszuwählen.
4. Dann können Sie Richtlinien und Apps für diese Gruppen bereitstellen.

Sie können beliebige Gerätekategorien erstellen, z.B.:
* POS-Gerät (Point of Sale)
* Demogerät
* Sales
* Kontoführung
* Manager

## Wichtige Informationen zu einer Änderung in der Gruppenverwaltung für Intune

Derzeit vereinheitlichen wir auf der Grundlage Ihres Feedbacks den Ablauf bei der Gruppierung und Zielgruppenadressierung in Enterprise Mobility + Security. Aus diesem Grund konvertieren wir in Kürze die Intune-Gruppen in Azure Active Directory-basierte Sicherheitsgruppen. Nach dieser Änderung werden Gruppen nicht mehr mit Intune erstellt. Stattdessen werden sie im Azure-Portal erstellt. Diese Änderung wird schrittweise vorgenommen. Ausführliche Informationen zu dieser Änderung sowie zum zeitlichen Ablauf finden Sie in [diesem Thema](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

### Welches Verfahren in diesem Thema sollten Sie verwenden, um die Gerätegruppenzuordnung zu konfigurieren?

Da die Azure Active Directory-basierten Sicherheitsgruppen schrittweise implementiert werden, müssen Sie den Arbeitsbereich **Gruppen** in der [Intune-Verwaltungskonsole](https://manage.microsoft.com) öffnen, um herauszufinden, welches Verfahren zu verwenden ist:

-  Wenn ein Link zum Azure-Portal angezeigt wird, werden keine Intune-Gruppen mehr verwendet. Befolgen Sie das weiter unten beschriebene Verfahren [Konfigurieren der Gerätegruppenzuordnung (für Azure Active Directory-Gruppen)](##Konfigurieren-der-Gerätegruppenzuordnung-(für-Azure Active Directory-Gruppen).
-  Wenn kein Link zum Azure-Portal angezeigt wird, werden weiterhin Intune-Gruppen verwendet. Befolgen Sie das weiter unten beschriebene Verfahren [Konfigurieren der Gerätegruppenzuordnung (für Intune-Gruppen)](##Konfigurieren-der-Gerätegruppenzuordnung-(für-Intune-Gruppen).

## Konfigurieren der Gerätegruppenzuordnung für Intune-Gruppen
1. Erstellen Sie für jede zu verwendende Gerätekategorie eine Intune-Gerätegruppe, oder geben Sie eine vorhandene Gruppe an. Informationen zum Erstellen von Gruppen finden Sie unter [Verwenden von Gruppen zum Verwalten von Benutzern und Geräten in Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).
2. Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Option **Verwaltung** aus.
3. Erweitern Sie im Arbeitsbereich **Verwaltung** die **Verwaltung mobiler Geräte**, und wählen Sie anschließend **Gerätegruppenzuordnung** aus.
4. Aktivieren Sie auf der Seite **Gerätegruppenzuordnung** die Gerätegruppenzuordnung.
5. Wählen Sie **Hinzufügen** aus, um eine neue Zuordnungsregel zu erstellen.
6. Geben Sie im Dialogfeld **Regel für Gerätegruppenzuordnung hinzufügen** den Namen der zu erstellenden Kategorie ein. Wählen Sie dann aus der Dropdownliste die Gerätesammlung aus, der Sie diese Kategorie zuordnen möchten. Wählen Sie **Hinzufügen** aus, wenn Sie fertig sind.
7. Wenn Sie das Hinzufügen von Kategorien und Gruppen abgeschlossen haben, wählen Sie **Speichern** aus.



## Konfigurieren der Gerätegruppenzuordnung für Azure Active Directory-Gruppen

### Schritt 1: Erstellen von Gerätekategorien in der Intune-Verwaltungskonsole
1. Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Option **Verwaltung** aus.
3. Erweitern Sie im Arbeitsbereich **Verwaltung** die **Verwaltung mobiler Geräte**, und wählen Sie anschließend **Gerätekategorien** aus.
4. Auf der Seite **Gerätekategorien** wird eine Liste angezeigt, in der Sie Gerätekategorien konfigurieren können: 
- Geben Sie einen Namen ein, und klicken Sie auf **Hinzufügen**, um die Kategorie als neue Gerätekategorie hinzuzufügen.
- Darüber hinaus können Sie eine Kategorie zum **Löschen** auswählen.

Verwenden Sie den Kategorienamen des Geräts zum Erstellen von Azure Active Directory-Sicherheitsgruppen in Schritt 2.

### Schritt 2: Erstellen von Active Directory-Sicherheitsgruppen

In diesem Schritt erstellen Sie dynamische Gruppen im Azure-Portal auf Basis der Gerätekategorie und des Gerätekategorienamens.

Lesen Sie das Thema [Verwenden von Attributen zum Erstellen erweiterter Regeln](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) in der Dokumentation zu Azure Active Directory, um den Vorgang fortzusetzen.
Verwenden Sie die Informationen in diesem Thema zum Erstellen einer Gerätegruppe mit einer erweiterten Regel mithilfe des Attributs **deviceCategory**.
Beispiel: (**device.deviceCategory -eq** "<*Gerätekategoriename, den Sie über die Intune-Verwaltungskonsole erhalten haben*>")


## Nach dem Konfigurieren von Gerätegruppen

Wenn Benutzer ihre Geräte registrieren, wird ihnen eine Liste der von Ihnen konfigurierten Kategorien angezeigt. Nachdem sie eine Kategorie ausgewählt und die Registrierung abgeschlossen haben, wird ihr Gerät zu der Intune-Gerätegruppe oder Active Directory-Sicherheitsgruppe hinzugefügt, die der gewählten Kategorie entspricht.

### Weitere Informationen:
[Verwenden von Gruppen zum Verwalten von Benutzern und Geräten in Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)


<!--HONumber=Oct16_HO2-->


