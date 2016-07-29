---
title: "Anpassen von Konsolenansichten für Administratorrollen | Microsoft Intune"
description: "Filtern Sie wie in diesem Thema beschrieben die Intune-Verwaltungskonsolenansicht, damit Administratoren nur die Elemente anzeigen können, die sie für ihre Rolle benötigen."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0783eaa-67dc-410e-9e80-4d3aa72f36d8
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: 132648f4c4d13983b169fa8497deae9787fe6db5


---

# Anpassen von Intune-Konsolenansichten an Administratorrollen
Sie können die Microsoft Intune-Verwaltungskonsolenansicht filtern, damit Administratoren nur die Elemente anzeigen können, die sie für ihre Rolle benötigen. Beispielsweise empfiehlt es sich, nur den Operatoren der Verwaltungskonsole die Erlaubnis zu erteilen, Malwaredefinitionen zu aktualisieren oder die Kennung auf Geräten zurückzusetzen. Dies erfolgt mithilfe der vorab festgelegten **Bezeichnungen**, die Sie bestimmten Benutzern zuweisen. Wenn diese Benutzer auf die Verwaltungskonsole zugreifen, sehen sie nur die für ihre Bezeichnung bestimmten Elemente.

## Erstellen einer benutzerdefinierten Ansicht

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Option **Admin** &gt; **Dienstadministratoren** aus.

2.  Wählen Sie aus der Liste der Dienstadministratoren den Benutzer aus, dessen Bezeichnung Sie ändern möchten, und wählen Sie anschließend **Zugriff verwalten** aus.

3.  Wählen Sie im Dialogfeld **Zugriff verwalten** die Zugriffsebene, die dem ausgewählten Benutzer zugewiesen werden soll. Es gibt folgende Auswahlmöglichkeiten:

    -   **Vollzugriff**
    -   **Schreibgeschützter Zugriff**
    -   **Helpdesk – Gruppenknoten**

    „Vollzugriff“ und „schreibgeschützter Zugriff“ sind selbsterklärend. <!--- **Helpdesk - Groups Node** allows users to choose from one of the following designations that provide custom levels of access to the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] admin console:--->

    **Helpdesk – Gruppenknoten** beschränkt die Möglichkeiten, was der Administrator anzeigen und ausführen kann auf Folgendes:

    -   Anzeigen der Listen von Benutzern und Geräten. Der Administrator kann die Ansicht nicht mithilfe von Filtern ändern. Sie können jedoch mithilfe der Gruppenfilterung definieren, was dem Administrator angezeigt wird. Weitere Informationen finden Sie unter [Verwenden von Gruppen zum Verwalten von Benutzern und Geräten in Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

    -   Drucken der Liste der Benutzer und Geräte

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

Wenn der von Ihnen konfigurierte Administrator das nächste Mal die Intune-Verwaltungskonsole öffnet, wird ihm die von Ihnen festgelegte Zugriffsebene zugewiesen.



<!--HONumber=Jul16_HO3-->


