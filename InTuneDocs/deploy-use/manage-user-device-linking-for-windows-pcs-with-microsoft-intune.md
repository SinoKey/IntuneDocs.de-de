---
title: "Verwalten von Verknüpfungen zwischen Benutzern und Geräten für Windows-PCs | Microsoft Intune"
description: "Verknüpfen eines Benutzers mit einem vom Intune verwalteten Windows-PC."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c99d63-c312-442a-8a71-de1b10fcd39b
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 39fec6a2ea8d8c0f4b6ea1460c76a8a6c652d614


---

# <a name="manage-user-device-linking-for-windows-pcs"></a>Verwalten von Verknüpfungen zwischen Benutzern und Geräten für Windows-PCs
Damit Sie Software für einen Benutzer bereitstellen können, müssen Sie diesen zunächst mit einem Computer verknüpfen. Sie können einen Benutzer mit mehreren Computern verknüpfen, aber einzelne Computer nur mit jeweils einem Benutzer. Benutzer werden automatisch mit den Computern verknüpft, die sie über das Unternehmensportal in Intune registrieren.

So verknüpfen Sie einen Benutzer mit einem Computer:

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Gruppen** &gt; **Alle Geräte** aus (oder eine andere Gruppe, in der der Computer enthalten ist, den Sie mit einem Benutzer verknüpfen möchten).

2.  Wählen Sie den Computer aus, den Sie mit einem Benutzer verknüpfen möchten, und wählen Sie dann **Benutzer verknüpfen** aus.

    Im Dialogfeld **Benutzer verknüpfen** wird eine Liste verfügbarer Benutzer mit ihren Anzeigenamen, Benutzer-IDs und der Anzahl von Computern angezeigt, mit denen die Benutzer jeweils aktuell verknüpft sind. Wenn ein Benutzer bereits mit dem ausgewählten Computer verknüpft ist, werden Name und Benutzer-ID des Benutzers unter **Aktueller Benutzer**angezeigt. Wenn der Computer mit keinem Benutzer verknüpft ist, wird unter **Aktueller Benutzer** der Wert **Kein Benutzer**angezeigt.

3.  Führen Sie eines der folgenden Verfahren aus:

    -   Wählen Sie **Abbrechen** aus, um die Verknüpfung des Computers mit einem ggf. vorhandenen aktuellen Benutzer beizubehalten.

    -   Zum Entfernen der Verknüpfung mit dem aktuellen Benutzer wählen Sie ggf. **Verknüpfung entfernen** &gt; **OK** aus.

    -   Zum Verknüpfen des Computers mit einem neuen Benutzer wählen Sie diesen in der Liste **Alle Benutzer** aus. Überprüfen Sie, ob die Benutzerdaten korrekt sind, und wählen Sie **OK** aus.

> [!TIP]
> Wenn Sie die Fähigkeit der Endbenutzer, sich mit Computern zu verknüpfen, einschränken möchten, aktivieren Sie die Option **Fähigkeit der Benutzer einschränken, sich mit Computern zu verknüpfen** in der Richtlinie **-Microsoft Intune-Agent-Einstellungen**.

### <a name="see-also"></a>Weitere Informationen:

[Allgemeine Aufgaben zur Verwaltung von Windows-PCs mit dem Intune-Softwareclient](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)


<!--HONumber=Nov16_HO4-->


