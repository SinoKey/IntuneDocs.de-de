---
title: Kategorisieren von Geräten mit Pseudo-Gruppe in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e
author: robstackmsft
---
# Kategorisieren von Geräten mit Pseudo-Gruppe in Microsoft Intune
Verwenden von Microsoft Intune **Gruppe Pseudo** Gruppieren von Geräten in Kategorien, die Sie definieren, um Sie zum Verwalten dieser Geräte vereinfachen,. 

Device-Gruppe-Zuordnung verwendet den folgenden Workflow:
1. Sie erstellen Intune Gerätegruppen für jede Kategorie, die Sie verwenden möchten.
2. Sie konfigurieren die Zuordnungsregeln Gerät-Gruppe an, die die Kategorie aus, die wählen Sie, die Gerätegruppe zuordnen, die Sie erstellt haben.
3. Wenn Benutzer ihre Geräte registrieren, müssen sie eine Kategorie aus den Kategorien auswählen, die Sie konfiguriert. Nachdem sie ausgewählt haben, wird ihr Gerät automatisch der entsprechenden Gerätegruppe hinzugefügt werden, die Sie erstellt haben.
4. Sie können dann diese Gerätegruppen verwenden, beim Bereitstellen von Richtlinien und apps.

Beispiele für Kategorien möglicherweise:
* Privat
* Point-of Sale-Gerät
* Demo-Gerät
* Sales
* Kontoführung
* Manager

Allerdings können Sie alle Kategorien konfigurieren Sie die gewünschten.

## Konfigurieren von Pseudo-Gruppe
1. Erstellen Sie für jede Gerätekategorie, die Sie verwenden möchten eine Gerätegruppe Intune. Weitere Informationen zum Erstellen von Gruppen finden Sie unter [Verwenden von Gruppen zum Verwalten von Benutzern und Geräten mit Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).
2. In der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com), klicken Sie auf **Admin**.
3. In der **Verwaltung** Arbeitsbereich erweitern **Verwaltung mobiler Geräte**, und klicken Sie dann auf **Gerät zuordnen**.
4. Auf der **Gruppe Gerätezuordnung** Seite, Gruppe Pseudo aktivieren.
5. Klicken Sie auf **Hinzufügen** zum Erstellen einer neuen Zuordnungsregel.
6. In der **Hinzufügen Gerät Gruppe Zuordnungsregel** Dialogfeld Geben Sie den Namen der Kategorie, die Sie erstellen möchten und wählen Sie dann aus der Dropdown-Liste der Geräte-Auflistung, die dieser Kategorie zugeordnet werden soll. Klicken Sie auf **Hinzufügen** Wenn Sie fertig sind.
7. Wenn Sie nach dem Hinzufügen von Kategorien und Gruppen, klicken Sie auf **Speichern**.

Nun, wenn Benutzer ihre Geräte anmelden, werden sie mit einer Liste der Kategorien angezeigt werden, die Sie konfiguriert. Nach deren wählen Sie eine Kategorie und die Registrierung abzuschließen, wird ihr Gerät zu dieser Gruppe hinzugefügt werden, die der Kategorie entspricht, die sie ausgewählt haben.

### Weitere Informationen:
[Verwenden von Gruppen zum Verwalten von Benutzern und Geräten in Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)

<!--HONumber=Mar16_HO4-->


