---
title: "Einschließen und Ausschließen von App-Zuweisungen"
titlesuffix: Microsoft Intune
description: "Erfahren Sie, wie Sie mit Intune App-Zuweisungen ein- und ausschließen können."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/29/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59f6df5-3317-4dff-8f19-fdeec33faedf
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ca1f45c3203645dc474fcb6411a8ad598ff83714
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2018
---
# <a name="include-and-exclude-app-assignments-in-microsoft-intune"></a>Einschließen und Ausschließen von App-Zuweisungen in Microsoft Intune

Mithilfe von Intune können Sie bestimmen, wer Zugriff auf eine App hat, indem Sie sowohl die ein- als auch auszuschließenden Gruppen zuweisen. App-Zuweisungen für eine Gruppe von Benutzern oder Geräten schließen Sie mithilfe einer Kombination von Ein- und Ausschlussgruppenzuweisungen ein und aus. Nach der Auswahl einer App können Sie wählen, wie die App zugewiesen wird. Diese Funktion kann nützlich sein, wenn Sie die App verfügbar machen, indem Sie eine große Gruppe einschließen und dann die ausgewählten Benutzer auch durch Ausschluss einer kleineren Gruppe einschränken. Die kleinere Gruppe könnte eine Testgruppe oder ausführende Gruppe sein. 

Beim Ausschließen von Gruppen aus einer Zuweisung dürfen Sie nur Benutzer- oder nur Gerätegruppen ausschließen und keine Kombination von Gruppen. Intune berücksichtigt beim Ausschließen von Gruppen keine Zuweisung eines Benutzers zu einem Gerät. Es ist unwahrscheinlich, dass das Einschließen von Benutzergruppen und gleichzeitige Ausschließen von Gerätegruppen die von Ihnen gewünschten Ergebnisse liefert, da das Einschließen vor dem Ausschließen Vorrang hat. Wenn Sie z.B. **Alle Benutzer** eine iOS-App zuweisen und **Alle iPads** ausschließen, kommt dabei heraus, dass jeder Benutzer mit einem iPad weiterhin die Anwendung erhält. Wenn Sie jedoch die iOS-App **Alle Geräte** zuweisen und **Alle iPads** ausschließen, ist die Bereitstellung erfolgreich.  

>[!NOTE]
>Beim Festlegen einer Gruppenzuweisung für eine App ist der Typ **Nicht zutreffend** veraltet und wird mit der Ausschlussgruppenfunktionalität ersetzt. 
>
>Intune bietet die vorab erstellten Gruppen **Alle Benutzer** und **Alle Geräte** in der Konsole zur Vereinfachung mit integrierten Optimierungen an. Sie sollten diese Gruppen unbedingt anstelle möglicherweise selbst erstellter „Alle Benutzer“- oder „Alle Geräte“-Gruppen verwenden, um alle Benutzer und alle Geräte zu erreichen.  

## <a name="including-and-excluding-groups-when-assigning-apps"></a>Ein- und Ausschließen von Gruppen beim Zuweisen von Apps 
So weisen Sie eine App Gruppen mithilfe der Ein- und Ausschlusszuweisung zu:
1. Wählen Sie auf dem Blatt Microsoft Intune die Option **Mobile Apps** aus.
2. Wählen Sie auf dem Blatt **Mobile Apps** die Option **Apps** aus. Die Liste der hinzugefügten Apps wird angezeigt.
3. Wählen Sie die App aus, die zugewiesen werden soll. Ein Dashboard wird im Zusammenhang mit der App angezeigt. 
4. Wählen Sie **Zuweisungen** im Abschnitt **Verwalten** aus. 

    ![Intune-App-Zuweisungen](./media/apps-inc-exl-01.png)
5. Wählen Sie **Gruppe hinzufügen** aus, um die Gruppen von Benutzern hinzuzufügen, denen die App zugewiesen wird. 
6. Wählen Sie einen **Zuweisungstyp** aus den im Blatt **Gruppe hinzufügen** verfügbaren Zuweisungstypen aus.
7. Wählen Sie **Verfügbar mit oder ohne Registrierung** als Zuweisungstyp aus.

    ![Intune-App-Zuweisungen – Gruppe hinzufügen](./media/apps-inc-exl-02.png)
8. Wählen Sie **Eingeschlossene Gruppen** aus, um die Gruppe von Benutzern auszuwählen, denen Sie diese App zur Verfügung stellen möchten.

    >[!NOTE]
    >Beachten Sie beim Hinzufügen einer Gruppe: Wenn eine Gruppe bereits für einen bestimmten Zuweisungstyp eingeschlossen wurde, ist diese vorausgewählt und kann nicht mehr für andere Einschlusszuweisungstypen geändert werden. Darum kann die Gruppe, die verwendet wurde, nicht als eingeschlossene Gruppe verwendet werden.

9. Wählen Sie **Ja**, um diese App für alle Benutzer verfügbar zu machen.

    ![Intune-App-Zuweisungen – Gruppen einschließen](./media/apps-inc-exl-03.png)
10. Klicken Sie auf **OK**, um die einzuschließende Gruppe festzulegen.
11. Wählen Sie **Ausgeschlossene Gruppen** aus, um die Gruppen von Benutzern auszuwählen, denen diese App nicht zur Verfügung stehen soll. 
12. Wählen Sie die auszuschließenden Gruppen aus, für die diese App nicht verfügbar ist.

    ![Intune-App-Zuweisungen – Gruppen ausschließen](./media/apps-inc-exl-04.png)
13. Klicken Sie auf **Auswählen**, um Ihre Gruppenauswahl abzuschließen.
14. Klicken Sie auf dem Blatt **Gruppe hinzufügen** auf **OK**. Die Liste der App-**Zuweisungen** wird angezeigt.
15. Klicken Sie auf **Speichern**, um Ihre Gruppenzuweisungen für die App zu aktivieren.

Wenn Sie Gruppenzuweisungen vornehmen, sind Gruppen deaktiviert, die bereits zugewiesen oder ausgewählt wurden. Wenn Sie eine derzeit deaktivierte Gruppe auswählen möchten, entfernen Sie sie aus der „Zugewiesen“-Liste der App. Sie können Zuweisungen in der App-**Zuweisungen**-Liste durch Auswahl der Zeile mit der jeweiligen Zuweisung, die Sie ändern möchten, bearbeiten. Darüber hinaus können Sie eine Zuweisung entfernen, indem Sie auf die Auslassungspunkte (...) am Ende einer Zeile klicken und **Entfernen** auswählen. Außerdem können Sie die Ansicht der Liste **Zuweisungen** ändern, indem Sie die Gruppierung nach **Zuweisungstyp** oder **Eingeschlossen/Ausgeschlossen** auswählen.

![Intune-App-Zuweisungen – Abschluss](./media/apps-inc-exl-05.png)

## <a name="next-steps"></a>Nächste Schritte

* Weitere Informationen zu ein- und ausschließenden Gruppenzuweisungen für Apps finden Sie im [Microsoft Intune-Blog](https://aka.ms/new_app_assignment_process).
