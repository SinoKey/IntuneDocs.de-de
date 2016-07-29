---
title: "Verwenden von Gruppen zum Verwalten von Benutzern und Geräten | Microsoft Intune"
description: "Erstellen und Verwalten von Gruppen mithilfe des Arbeitsbereichs „Gruppen“."
keywords: 
author: Nbigman
manager: Arob98
ms.date: 06/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb9b01ce-9b9b-4c2a-bf99-3879c0bdaba5
ms.reviewer: lpatha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 72288296d966b9b9fae4fd721b4460528213f626
ms.openlocfilehash: 42328ee749517fd5abf923db35e7b13747e9f14b


---

# Erstellen von Gruppen zum Verwalten von Benutzern und Geräten in Microsoft Intune

Zum Erstellen und Verwalten von Gruppen verwenden Sie den Arbeitsbereich **Gruppen** der Microsoft Intune-Verwaltungskonsole. Die Seite **Gruppenübersicht** enthält folgende Statusübersichten, mit denen Sie Probleme, die Ihre Aufmerksamkeit erfordern, schnell erkennen und priorisieren können:

-   Warnungen
-   Softwareupdates
-   Endpoint Protection
-   Richtlinie
-   Softwareverwaltung

Darüber hinaus werden in der Gruppenhierarchie Statusübersichten angezeigt, damit Sie Probleme bei Mitgliedern einer ausgewählten Gruppe leichter erkennen und beheben können.


> [!TIP]
> Überlegen Sie beim Erstellen von Gruppen, wie Sie Richtlinie angewendet werden. Sie können beispielsweise spezielle Richtlinien für Gerätebetriebssysteme, für verschiedene Rollen in Ihrer Organisation oder für bereits in Active Directory definierte Organisationseinheiten verwenden. Einige halten es für sinnvoll, spezielle Gerätegruppen für iOS, Android und Windows sowie Benutzergruppen für jede Rolle im Unternehmen zu verwenden.
>
> Vermutlich ist es ratsam, eine Standardrichtlinie zu erstellen, die für alle Gruppen und Geräte gilt, um die grundlegenden Compliance-Anforderungen Ihres Unternehmens zu erfüllen. Erstellen Sie anschließend spezifischere Richtlinien für die allgemeinsten Kategorien von Benutzern und Geräten, z. B. E-Mail-Richtlinien für jedes der Gerätebetriebssysteme.
>
> Benennen Sie die Richtlinien so, dass Sie diese später problemlos erkennen können. Ein guter, beschreibender Richtlinienname ist beispielsweise **WP-E-Mail-Richtlinie für das gesamte Unternehmen**.
>
> Wenn Sie restriktive Richtlinien erstellen, sollten Sie diese Ihren Benutzern mitteilen. Achten Sie daher nach dem Erstellen der allgemeineren Gruppen und Richtlinien darauf, wie Sie kleinere Gruppen erstellen, um eine unnötige Kommunikation zu vermeiden.


## Erstellen einer Gerätegruppe

1.  Wählen Sie in der Intune-Verwaltungskonsole **Gruppen** &gt; **Übersicht** &gt; **Gruppe erstellen** aus.

2.  Geben Sie einen Namen und wahlweise eine Beschreibung für die Gruppe an, und wählen Sie eine Gerätegruppe als übergeordnete Gruppe aus. Klicken Sie auf **Weiter**.

3.  Wählen Sie auf der Seite **Mitgliedschaftskriterien definieren** den Gerätetyp aus, den die Gruppe enthalten wird. Zusätzliche Optionen zum Konfigurieren der Gruppe hängen vom ausgewählten Gerätetyp ab:

    -   **Computer:** Geben Sie an, ob alle Mitglieder der übergeordneten Gruppe eingeschlossen werden sollen und welche Organisationseinheiten (OUs) sowie Domänen ein- bzw. ausgeschlossen werden sollen. Die Informationen zu OUs und Domänen für einen Computer werden aus dem Inventar abgerufen.

    -   **Mobil:** Geben Sie an, ob nur mobile Geräte enthalten sein sollen, die von Intune verwaltet werden, oder nur mobile Geräte, die von Exchange ActiveSync verwaltet werden, oder beide Arten von Geräten.

    -   **Alle Geräte:** Bei dieser Option sind alle Geräte ohne Ausschlüsse auf Basis von Kriterien enthalten.

4.  Schließen Sie auf der Seite **Direkte Mitgliedschaft definieren** einzelne Geräte ein oder aus, die Sie angeben, indem Sie auf **Durchsuchen**klicken. Wenn Sie die Option zum Auswählen von Geräten verwenden, die nicht in der angegebenen übergeordneten Gruppe enthalten sind, werden diese Geräte der übergeordneten Gruppe automatisch hinzugefügt.


5.  Überprüfen Sie auf der Seite **Zusammenfassung** die Aktionen, die ausgeführt werden sollen. Klicken Sie auf **Fertig stellen**.

Sie finden die neue Gruppe im Arbeitsbereich **Gruppen** unter der übergeordneten Gruppe in der Liste **Gruppen**. Hier können Sie die Gruppe auch bearbeiten oder löschen.

## Erstellen einer Benutzergruppe

1.  Wählen Sie in der Intune-Verwaltungskonsole **Gruppen** &gt; **Übersicht** &gt; **Gruppe erstellen** aus.

2.  Geben Sie einen Namen und wahlweise eine Beschreibung für die Gruppe an, und wählen Sie eine Benutzergruppe als übergeordnete Gruppe aus. Klicken Sie auf **Weiter**.

3.  Geben Sie auf der Seite **Mitgliedschaftskriterien definieren** an, ob alle Mitglieder der übergeordneten Gruppe eingeschlossen werden sollen oder ob mit einer leeren Gruppe begonnen werden soll.  Sie können dann Mitglieder auf Basis der **Sicherheitsgruppen** ein- oder ausschließen, welche manuell im [Office 365 Admin Center](http://go.microsoft.com/fwlink/?LinkId=698854) konfiguriert oder vom lokalen Active Directory synchronisiert werden. Wenn sich die Mitgliedschaft bei einer Sicherheitsgruppe ändert, können sich auch Mitgliedschaften bei Benutzergruppen auf Basis dieser Sicherheitsgruppe ändern.

    > [!IMPORTANT]
    > Derzeit werden, wenn Ihre Gruppe Mitglieder aus bestimmten Sicherheits- oder Vorgesetztengruppen einschließt und Sie außerdem Mitglieder aus bestimmten Gruppen ausschließen, die Mitglieder, die Sie ursprünglich aufgenommen hatten, entfernt. Um eine Gruppe zu erstellen, die sowohl eingeschlossene als auch ausgeschlossene Mitglieder enthält, empfehlen wir, zuerst eine übergeordnete Gruppe mit den eingeschlossenen Mitgliedern zu erstellen und dann eine dieser Gruppe untergeordnete Gruppe zu erstellen, in der Sie die ausgeschlossenen Mitglieder auflisten. Sie können dann diese untergeordnete Gruppe nach Bedarf für Intune-Richtlinien, -Profile und -App-Verteilung verwenden.

    > [!NOTE]
    > Im Azure-Verwaltungsportal können Sie eine Gruppe auf Grundlage des Vorgesetzten erstellen, dem die Benutzer unterstellt sind. Die Gruppe ist dynamisch und ändert sich mit dem Hinzufügen oder Entfernen von Mitarbeitern im Team dieses Vorgesetzten in Azure Active Directory. Das Verfahren zum Erstellen einer Azure-Gruppe auf Grundlage eines Vorgesetzten wird unter [Verwenden von Attributen zum Erstellen erweiterter Regeln](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/) im Abschnitt **So konfigurieren Sie eine Gruppe als „Vorgesetzten“-Gruppe** beschrieben.


4.  Schließen Sie auf der Seite **Direkte Mitgliedschaft definieren** einzelne Benutzer ein oder aus, die Sie angeben, indem Sie auf **Durchsuchen**klicken. Wenn Sie die Option zum Auswählen von Benutzern verwenden, die nicht in der angegebenen übergeordneten Gruppe enthalten sind, werden diese Benutzer der übergeordneten Gruppe automatisch hinzugefügt. Unten im Dialogfeld **Mitglieder auswählen** finden Sie eine Option zum manuellen Hinzufügen eines Benutzers. Dies ist hilfreich, wenn Sie einen Benutzer hinzufügen möchten, der noch nicht über ein registriertes Gerät verfügt.


5.  Überprüfen Sie auf der Seite **Zusammenfassung** die Aktionen, die ausgeführt werden sollen. Klicken Sie auf **Fertig stellen**.

Sie finden die neue Gruppe im Arbeitsbereich **Gruppen** unter der übergeordneten Gruppe in der Liste **Gruppen**. Hier können Sie die Gruppe auch bearbeiten oder löschen.

> [!TIP]
> Sicherheitsgruppen sind eine hervorragende Ressource zum Auffüllen von Benutzergruppen. Da Sicherheitsgruppen definieren, wer auf welche Ressourcen zugreifen kann, eignen sie sich gut als Intune-Benutzergruppen. Alle Sicherheitsgruppen, die von Active Directory in Azure Active Directory synchronisiert oder über das Office 365 Admin Center oder das Azure-Verwaltungsportal direkt in Azure Active Directory erstellt werden, stehen Ihnen zum Erstellen von Benutzergruppen in Intune zur Verfügung.

## Anpassen von Ansichten für Administratorrollen
Mithilfe von gefilterten Gruppenansichten können Sie die Ansichten anpassen, die den Administratoren abhängig von ihrer Rolle angezeigt werden. Mit der gleichen Filtermethode können Sie auch einschränken, welche Gruppen der jeweilige IT-Administrator verwalten kann. Dies kann in folgenden Fällen hilfreich sein:

-   IT-Administratoren sollten nur Elemente für bestimmte Benutzer und Geräte bereitstellen können.

-   Jedem IT-Administrator sollen nur relevante Gruppen angezeigt werden.

Sie können gefilterte Gruppenansichten für Dienstadministratoren in der Intune-Verwaltungskonsole konfigurieren. Weitere Informationen finden Sie unter [Was Sie wissen sollten, bevor Sie Microsoft Intune starten](/intune/get-started/what-to-know-before-you-start-microsoft-intune).

Nach dem Konfigurieren von gefilterten Gruppenansichten für einen Dienstadministrator hat der betreffende Administrator folgende Möglichkeiten:

-   Kann nur die Gruppen anzeigen und auswählen, die Sie bei der Bereitstellung von Software oder Richtlinien oder bei der Verwendung von Berichten angegeben haben.

-   Erhält keine Statusinformationen auf den folgenden Seiten der Verwaltungskonsole:

    -   **Systemübersicht**

    -   **Gruppenübersicht**

    -   **Übersicht über Endpoint Protection**

    -   **Warnungsübersicht**

    -   **Softwareübersicht**

    -   **Richtlinienübersicht**

### Konfigurieren von gefilterten Gruppenansichten

1.  Wählen Sie in der Intune-Verwaltungskonsole **Admin** &gt; **Administratorverwaltung** &gt; **Dienstadministratoren** aus.

2.  Wählen Sie den Dienstadministrator aus, für den die Gruppen gefiltert werden sollen, und klicken Sie auf **Gruppen verwalten**.

3.  Fügen Sie im Dialogfeld **Wählen Sie die Gruppen, die diesem Dienstadministrator angezeigt werden** die Gruppen hinzu, auf die der ausgewählte Dienstadministrator zugreifen darf, und klicken Sie dann auf **OK**.

Nach der Konfiguration der gefilterten Gruppenansichten können IT-Administrator nur die Gruppen anzeigen und auswählen, die Sie ausgewählt haben.

## Verwalten Ihrer Gruppen
Nachdem Sie Gruppen erstellt haben, verwalten Sie diese entsprechend den Anforderungen Ihrer Organisation.

Sie können den Namen, die Beschreibung und die Mitglieder der Gruppe ändern.

Sie können eine Gruppe löschen, die keinen Nutzen mehr für Ihre Organisation hat. Beim Löschen einer Gruppe werden die Benutzer, die zu dieser Gruppe gehören, nicht gelöscht.

## Nächste Schritte

### Überprüfen des Entwurfs
Nachdem Sie Ihre Gruppen und Richtlinien konfiguriert haben, überprüfen Sie die praktischen Auswirkungen dieses Entwurfs. Dazu prüfen Sie die Angaben für **Vorgesehener Wert** und **Status**.

1. Wählen Sie ein Gerät aus einer Gerätegruppe aus, und navigieren Sie durch die Informationskategorien am oberen Bildschirmrand.
2. Wählen Sie **Richtlinie** . Sie sehen in etwa diesen Screenshot mit den Richtlinieneinstellungen eines Android-Geräts.

![Beispiel für eine iOS-Einstellungsrichtlinie](../media/Intune-Device-Policy-v.2.jpg)

Jede Richtlinie verfügt über einen **vorgesehenen Wert** und einen **Status**. Den vorgesehenen Wert möchten Sie durch Zuweisen der Richtlinie erzielen. Der Status gibt an, was tatsächlich erreicht wird, wenn alle für das Gerät geltenden Richtlinien sowie die Einschränkungen und Anforderungen der Hardware und des Betriebssystems zusammen betrachtet werden.  Der Screenshot zeigt zwei klare Beispiele:

-   **Einfache Kennwörter zulassen** ist auf **Ja**gesetzt, wie in der Spalte **Vorgesehener Wert** gezeigt, der **Status** ist jedoch **Nicht zutreffend**. Dies liegt daran, dass einfache Kennwörter für Android-Geräte nicht unterstützt werden.

-   Ebenso gilt das erweiterte Richtlinienelement**E-Mail-Einstellungen für iOS-Geräte** nicht für dieses Gerät, da es ein Android-Gerät ist.

> [!NOTE]
> Denken Sie daran: Wenn zwei Richtlinien mit unterschiedlichen Einschränkungsstufen für das gleiche Gerät gelten, wird in der Praxis die restriktivere Richtlinie angewendet.



<!--HONumber=Jul16_HO3-->


