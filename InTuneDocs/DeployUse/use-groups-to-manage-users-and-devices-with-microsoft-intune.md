---
title: Verwenden von Gruppen zum Verwalten von Benutzern und Geräten in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: eb9b01ce-9b9b-4c2a-bf99-3879c0bdaba5
author: Nbigman
---
# Erstellen von Gruppen zum Verwalten von Benutzern und Geräten mit Microsoft Intune
<!-- This is the same intro as for the Plan topic. Not sure if it's worth repeating here. Maybe this should be Set up your groups?**Groups** in [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)] give you great flexibility for managing your devices and users. You can set up groups to suit your organizational needs (for example, by geographic location, department, or hardware characteristics).

Additionally, you can filter groups to allow your IT admins permissions to only perform operations on the groups you specify. For more information, see [Use filtered group views to help secure and manage users and devices](use-groups-to-manage-users-and-devices-with-microsoft-intune.md#BKMK_Filter) in this topic.-->
<!--## The Groups workspace-->

Erstellen und Verwalten von Gruppen mithilfe der **Gruppen** Arbeitsbereich in der [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]. Die Seite **Gruppenübersicht** enthält folgende Statusübersichten, mit denen Sie Probleme, die Ihre Aufmerksamkeit erfordern, schnell erkennen und priorisieren können:

-   Warnungen
-   Softwareupdates
-   [!INCLUDE[epshort](../includes/epshort_md.md)]
-   Richtlinie
-   Softwareverwaltung

Darüber hinaus wird die Gruppenhierarchie mit Statusübersichten zu identifizieren und Lösen von Problemen für Mitglieder einer ausgewählten Gruppe angezeigt.

<!-- moved to plan topic.
### Built-in groups
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] provides nine built-in groups that you cannot edit or delete:

-   **All Users**
    -   Ungrouped Users
-   **All Devices**
    -   All Computers
    -   All Mobile Devices
        -   All Direct Managed Devices
        -   All Exchange ActiveSync Managed Devices
    -   All Corporate-owned Devices
    -   Ungrouped Devices -->

<!-- moved to Plan topic  
## Group memberships

-   A group can contain either users or devices, but not both.

    -   **Device groups:** This includes both computers and mobile devices. Before you can add a computer to a group, it must be enrolled. Before you can add a mobile device to a group, your environment must be configured to support mobile devices, and the devices must be enrolled, or discovered from Exchange ActiveSync.

    -   **User groups:** A group can contain users from security groups, which are groups that synchronize from your Active Directory. If you do not use Active Directory synchronization, you can manually create these groups.

-   A device or a user can belong to more than one group.

-   A group can include and exclude members based on the following membership rules:

    -   **Criteria Membership:** These are dynamic rules that [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] runs to include or exclude members.  These criteria use security groups and other information synchronized from your local Active Directory. When the security group or data that is synchronized changes, the group membership can change.

    -   **Direct Membership:** These are static rules that explicitly add or exclude members. The membership list is static.

-   Active Directory Domain Services (AD DS) is not required to create user groups or device groups that include users or computers, but for device groups to include mobile devices, your environment must be configured to support mobile devices.

    Additionally, the devices must be discovered and added to [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)].

## Group relationships

-   Every group you create must have a parent group and you cannot change a group’s parent group once the group is created.

-   When adding users or devices to a child group:

    -   Child groups are always subsets of the parent group.

    -   New members you add to a child group are automatically added to that group’s parent group.

    -   You cannot add a member to a child group when that member is excluded from the parent group.

-   The membership of a parent group defines the available membership for the child group.

-   When you delete a parent group, all child groups are deleted.

-   You can deploy content and policies to a parent group while excluding deployment to child groups.

-   You can add a specific user or device to a child group that is not a member of the parent group. If you do so, the new group member will be added to the parent group.

    However, you cannot add a member to a child group that is excluded from the parent group.

-   Group membership is recursive. For example:

    -   **Pat** is a member of only one group, the **Laptop Users** security group.

    -   The **Laptop Users** group is a member of the **Approved Users** security group.

    -   You create a group in [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] that uses a dynamic membership query that includes the members of the **Approved Users** group. The result is that your [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] user group includes **Pat**.

> [!TIP]
> When you're creating your groups consider how you will apply policy. For example, you may have policies specific to device operating systems, and policies specific to different roles in your organization, or to Organizational Units you've already defined in Active Directory. Some consider it useful to have device groups specific to iOS, Android, and Windows, as well as user groups for each organizational role.
>
> You'll probably want to create a default policy that applies to all groups and devices, to establish the basic compliance requirements of your company. Then create more specific policies for the broadest categories of users and devices, for example, email policies for each of the device operating systems.
>
> Be careful naming your policies so that you can easily identify them later. For example, a good, descriptive policy name is **WP Email Policy for Entire Company**.
>
> Each time you create a restrictive policy you'll want to communicate it to your users, so after you create the more general groups and policies pay attention to how you create smaller groups so that you can reduce unnecessary communication.-->


## Erstellen einer Gerätegruppe

1.  In der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/), wählen Sie **Gruppen** & Gt; **Übersicht über** & Gt; **Erstellen Sie Gruppe**.

2.  Geben Sie einen Namen und optional eine Beschreibung für die Gruppe, und wählen Sie eine Gerätegruppe als übergeordnete Gruppe. Wählen Sie **Weiter**.

3.  Wählen Sie auf der Seite **Mitgliedschaftskriterien definieren** den Gerätetyp aus, den die Gruppe enthalten wird. Zusätzliche Optionen zum Konfigurieren der Gruppe hängen vom ausgewählten Gerätetyp ab:

    -   **Computer:** angeben, ob alle enthalten Elemente des übergeordneten Elements gruppieren, die Sie einschließen oder ausschließen möchten organisatorische Einheiten (OU), und die Domänen ein-oder ausgeschlossen werden sollen. Die Informationen zu OUs und Domänen für einen Computer werden aus dem Inventar abgerufen.

    -   **Mobile:** Geben nur für mobile Geräte enthalten, die von verwalteten [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], die von Exchange ActiveSync oder beides.

    -   **Alle Geräte:** Bei dieser Option sind alle Geräte ohne Ausschlüsse auf Basis von Kriterien enthalten.

4.  Schließen Sie auf der Seite **Direkte Mitgliedschaft definieren** einzelne Geräte ein oder aus, die Sie angeben, indem Sie auf **Durchsuchen**klicken. Wenn Sie die Option zum Auswählen von Geräten verwenden, die nicht in der angegebenen übergeordneten Gruppe enthalten sind, werden diese Geräte der übergeordneten Gruppe automatisch hinzugefügt.


5.  Auf der **Zusammenfassung** Überprüfen Sie die Aktionen, die ausgeführt werden soll. Wählen Sie **Fertig stellen**.

Finden Sie die neu erstellte Gruppe in der **Gruppen** Liste der **Gruppen** -Arbeitsbereich unter der übergeordneten Gruppe. Hier können Sie die Gruppe auch bearbeiten oder löschen.

## Erstellen einer Benutzergruppe

1.  In der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/), wählen Sie **Gruppen** & Gt; **Übersicht über** & Gt; **Erstellen Sie Gruppe**.

2.  Geben Sie einen Namen und optional eine Beschreibung für die Gruppe, und wählen Sie eine Benutzergruppe als übergeordnete Gruppe aus. Wählen Sie **Weiter**.

3.  Geben Sie auf der Seite **Mitgliedschaftskriterien definieren** an, ob alle Mitglieder der übergeordneten Gruppe eingeschlossen werden sollen oder ob mit einer leeren Gruppe begonnen werden soll.  Können Sie einschließen oder Ausschließen von Elementen basierend auf den **Sicherheitsgruppen** von Benutzern, die Sie manuell konfigurieren, die [Office 365 Administrationscenter](http://go.microsoft.com/fwlink/?LinkId=698854) oder vom lokalen Active Directory synchronisiert. Wenn sich die Mitgliedschaft bei einer Sicherheitsgruppe ändert, können sich auch Mitgliedschaften bei Benutzergruppen auf Basis dieser Sicherheitsgruppe ändern.

    > [!IMPORTANT]
    > Derzeit werden, wenn Ihre Gruppe Mitglieder aus bestimmten Sicherheits- oder Vorgesetztengruppen einschließt und Sie außerdem Mitglieder aus bestimmten Gruppen ausschließen, die Mitglieder, die Sie ursprünglich aufgenommen hatten, entfernt. Um eine Gruppe zu erstellen, die sowohl eingeschlossene als auch ausgeschlossene Mitglieder enthält, empfehlen wir, zuerst eine übergeordnete Gruppe mit den eingeschlossenen Mitgliedern zu erstellen und dann eine dieser Gruppe untergeordnete Gruppe zu erstellen, in der Sie die ausgeschlossenen Mitglieder auflisten. Sie können dann diese untergeordnete Gruppe nach Bedarf für Intune-Richtlinien, -Profile und -App-Verteilung verwenden.

    > [!NOTE]
    > Im Azure-Verwaltungsportal können Sie eine Gruppe auf Grundlage des Vorgesetzten erstellen, dem die Benutzer unterstellt sind. Die Gruppe ist dynamisch und ändert sich mit dem Hinzufügen oder Entfernen von Mitarbeitern im Team dieses Vorgesetzten in Azure Active Directory. Das Verfahren zum Erstellen einer Azure-Gruppe basierend auf einem-Manager wird in beschrieben [unter Verwendung von Attributen zum Erstellen erweiterter Regeln](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/) im Abschnitt **So konfigurieren Sie eine Gruppe als eine Gruppe "Manager"**.


4.  Schließen Sie auf der Seite **Direkte Mitgliedschaft definieren** einzelne Benutzer ein oder aus, die Sie angeben, indem Sie auf **Durchsuchen**klicken. Wenn Sie die Option zum Auswählen von Benutzern verwenden, die nicht in der angegebenen übergeordneten Gruppe enthalten sind, werden diese Benutzer der übergeordneten Gruppe automatisch hinzugefügt. Am unteren Rand der **auswählen** Dialogfeld finden Sie die Möglichkeit, einen Benutzer manuell hinzufügen. Dies ist hilfreich, wenn Sie möchten einen Benutzer hinzuzufügen, der noch nicht über eine registrierte Gerät verfügt.


5.  Auf der **Zusammenfassung** Überprüfen Sie die Aktionen, die ausgeführt werden soll. Wählen Sie **Fertig stellen**.

Finden Sie die neu erstellte Gruppe in der **Gruppen** Liste der **Gruppen** -Arbeitsbereich unter der übergeordneten Gruppe. Hier können Sie die Gruppe auch bearbeiten oder löschen.

> [!TIP]
> Sicherheitsgruppen sind eine hervorragende Ressource zum Auffüllen von Benutzergruppen. Da Sicherheitsgruppen definieren, wer auf welche Ressourcen zugreifen, übersetzt, die auch in  [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Benutzergruppen. Sicherheitsgruppen, die aus Active Directory auf Azure Active Directory synchronisiert werden, oder, die direkt in Azure Active Directory über das Office 365 Administrationscenter oder das Azure-Verwaltungsportal erstellt werden, sind für Sie zum Erstellen von Benutzergruppen in verfügbar [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

## Anpassen von Ansichten für Administratorrollen
Mit gefilterten Gruppenansichten können Sie zum Anpassen der Ansicht, die Administratoren sehen können basierend auf ihrer Rolle und die Benutzergruppen, die jeder IT-Administrator verwaltet werden kann. Dies kann in folgenden Fällen hilfreich sein:

-   IT-Administratoren sollten nur Elemente für bestimmte Benutzer und Geräte bereitstellen können.

-   Jedem IT-Administrator sollen nur relevante Gruppen angezeigt werden.

Sie können gefilterte Gruppenansichten für Dienstadministratoren in der [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Verwaltungskonsole konfigurieren. Weitere Informationen finden Sie unter [Wissenswertes vor dem Einrichten von Microsoft Intune](what-to-know-before-setting-up-microsoft-intune.md).

Nach dem Konfigurieren der gefilterten Gruppenansichten für einen Dienstadministrator hat der Administrator:

-   Kann nur die Gruppen anzeigen und auswählen, die Sie bei der Bereitstellung von Software oder Richtlinien oder bei der Verwendung von Berichten angegeben haben.

-   Erhält keine Statusinformationen auf den folgenden Seiten der Verwaltungskonsole:

    -   **Systemübersicht**

    -   **Gruppenübersicht**

    -   **Übersicht über Endpoint Protection**

    -   **Warnungsübersicht**

    -   **Softwareübersicht**

    -   **Richtlinienübersicht**

### Konfigurieren der gefilterten Gruppenansichten

1.  In der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com), wählen Sie **Admin** & Gt; **Administratorverwaltung** & Gt; **Dienstadministratoren**.

2.  Wählen Sie den Dienstadministrator aus, für den die Gruppen gefiltert werden sollen, und klicken Sie auf **Gruppen verwalten**.

3.  Fügen Sie im Dialogfeld **Wählen Sie die Gruppen, die diesem Dienstadministrator angezeigt werden** die Gruppen hinzu, auf die der ausgewählte Dienstadministrator zugreifen darf, und klicken Sie dann auf **OK**.

Nach der Konfiguration der gefilterten Gruppenansichten können IT-Administrator nur die Gruppen anzeigen und auswählen, die Sie ausgewählt haben.

## Verwalten Ihrer Gruppen
Nachdem Sie die Gruppen erstellen, werden Sie weiterhin entsprechend den Anforderungen Ihrer Organisation verwalten.

Sie können den Namen, die Beschreibung und die Mitglieder der Gruppe ändern.

Sie können eine Gruppe löschen, die keinen Nutzen mehr für Ihre Organisation hat. Beim Löschen einer Gruppe werden die Benutzer, die zu dieser Gruppe gehören, nicht gelöscht.

## Nächste Schritte

### Überprüfen Sie den Entwurf
Nachdem Sie die Gruppen und Richtlinien eingerichtet haben, überprüfen Sie die praktischen Auswirkungen Ihres Entwurfs durch Überprüfen der **beabsichtigten Wert** und **Status**.

1. Wählen Sie ein Gerät aus einer Gerätegruppe aus, und navigieren Sie durch die Informationskategorien am oberen Bildschirmrand.
2. Wählen Sie **Richtlinie** . Sie sehen in etwa diesen Screenshot mit den Richtlinieneinstellungen eines Android-Geräts.

![](../media/Intune-Device-Policy-v.2.jpg)

Jede Richtlinie verfügt über einen **beabsichtigten Wert** und einen **Status**. Den beabsichtigten Wert möchten Sie durch Zuweisen der Richtlinie erzielen. Der Status ist, was Sie tatsächlich erreicht, wenn alle Richtlinien, die für das Gerät als auch die Einschränkungen und Anforderungen der Hardware und das Betriebssystem gelten zusammen betrachtet werden.  Der Screenshot zeigt zwei klare Beispiele:

-   **Einfache Kennwörter zulassen** ist auf **Ja**gesetzt, wie in der Spalte **Beabsichtigter Wert** gezeigt, der **Status** ist jedoch **Nicht zutreffend**. Dies liegt daran, dass einfache Kennwörter für Android-Geräte nicht unterstützt werden.

-   Auf ähnliche Weise das erweiterte Richtlinienelement **e-Mail-Einstellungen für iOS-Geräte**, wird nicht auf dieses Gerät angewendet, da es ein Android-Gerät ist.

> [!NOTE]
> Denken Sie daran: Wenn zwei Richtlinien mit unterschiedlichen Einschränkungsstufen für das gleiche Gerät gelten, wird in der Praxis die restriktivere Richtlinie angewendet.


<!--HONumber=Mar16_HO4-->


