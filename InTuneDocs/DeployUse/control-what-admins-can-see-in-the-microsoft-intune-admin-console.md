---
title: Anpassen von Ansichten für Administratorrollen | Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: e0783eaa-67dc-410e-9e80-4d3aa72f36d8
author: robstackmsft
---
# Anpassen von Ansichten von Intune-Konsole entsprechend Administratorrollen
Sie können filtern, die Microsoft Intune Admin können die Administratoren nur die Elemente anzuzeigen, die sie benötigen, um ihre Rolle finden Sie unter. Beispielsweise können Sie nur Admin-Konsole Operatoren Malwaredefinitionen aktualisieren oder Zurücksetzen der Kennung auf Geräten zulassen. Sie können dazu mit der Voreinstellung **Bezeichnung** die Sie bestimmten Benutzern zuweisen. Wenn diese Benutzer auf die Verwaltungskonsole zugreifen, sehen sie nur die für ihre Bezeichnung bestimmten Elemente.

Mit dieser Funktion können Sie Mitarbeitern Verwaltungsaufgaben zuweisen, bei gleichzeitiger Gewährleistung der Sicherheit Ihrer Daten Intune.

## Gewusst wie: Erstellen einer benutzerdefinierten Ansicht

1.  In der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com), wählen Sie **Admin** & Gt; **Dienstadministratoren**.

2.  Wählen Sie aus der Liste der Dienstadministratoren den Benutzer, dessen Bezeichnung Sie ändern, und wählen Sie dann möchten **Zugriff verwalten**.

3.  Wählen Sie im Dialogfeld **Zugriff verwalten** die Zugriffsebene, die dem ausgewählten Benutzer zugewiesen werden soll. Es gibt folgende Auswahlmöglichkeiten:

    -   **Vollzugriff**
    -   **Schreibgeschützter Zugriff**
    -   **Helpdesk – Gruppenknoten**

    Voller Zugriff und nur-Lese-Zugriff sind sich selbst. <!--- **Helpdesk - Groups Node** allows users to choose from one of the following designations that provide custom levels of access to the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] admin console:--->

    **Helpdesk – Gruppenknoten** beschränkt, was der Administrator kann finden Sie unter und führen Sie die folgenden:

    -   Listen von Benutzern und Geräten anzeigen. Der Administrator kann nicht Filter verwenden, um die Ansicht zu ändern. Allerdings können Sie Filter ändern, was der Administrator anzeigen kann. Weitere Informationen finden Sie unter [Verwenden von Gruppen zum Verwalten von Benutzern und Geräten mit Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

    -   Drucken Sie die Liste der Benutzer und Geräte

    -   Exportieren der Liste der Benutzer und Geräte

    -   Anzeigen der Eigenschaften eines Benutzers oder Geräts

    -   Führen Sie die folgenden Remoteaufgaben aus:

        -   Vollständige Malwareüberprüfung ausführen

        -   Malwareschnellüberprüfung ausführen

        -   Computer neu starten

        -   Update für Malwaredefinitionen ausführen

        -   Richtlinien aktualisieren

        -   Inventur aktualisieren

        -   Remotesperre für Gerät aktivieren

        -   Zurücksetzen der Kennung

Wenn der Administrator konfigurierten neben die Intune-Verwaltungskonsole geöffnet wird, sie die Zugriffsebene erhält, die Sie angegeben haben.




<!--HONumber=Mar16_HO4-->


