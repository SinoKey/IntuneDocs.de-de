---
# required metadata

title: Planen von Benutzer- und Gerätegruppen | Microsoft Intune
description:
keywords:
author: SanchuSa
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f11bb256-1094-4f7e-b826-1314c57f3356

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Planen von Benutzer- und Gerätegruppen
Die Gruppen in Intune bieten eine hervorragende Flexibilität beim Verwalten Ihrer Geräte und Benutzer. Sie können Gruppen anhand der folgenden Kriterien einrichten, um den Anforderungen Ihrer Organisation zu entsprechen:

- Geografischer Standort
- Abteilung
- Hardwareeigenschaften
- Betriebssystem
- Unternehmenseigenes Gerät oder im Besitz des Benutzers


## Funktionsweise von Intune-Gruppen


Die Standardansicht des Knotens „Gruppen“ in der Intune-Verwaltungskonsole:

![Screenshot der Standardansicht des Knotens „Gruppen“ in der Intune-Konsole](/intune/media/Group-planning/Intune_Planning_Groups_Default_small.png)

Richtlinien werden für Gruppen bereitgestellt, daher ist die Gruppenhierarchie eine der wichtigsten Überlegungen zum Entwurf. Es ist auch wichtig zu wissen, dass die übergeordnete Gruppe einer Gruppe nicht geändert werden kann, nachdem die Gruppe erstellt wurde, daher ist der Entwurf Ihrer Gruppen ab dem Zeitpunkt entscheidend, ab dem Sie beginnen, den Intune-Dienst zu verwenden. Einige der empfohlenen Methoden für den Entwurf einer Gruppenhierarchie auf Basis der Anforderungen Ihres Unternehmens werden hier beschrieben.

## Regeln für Gruppenmitgliedschaft

1. Eine Gruppe kann entweder Benutzer oder Geräte enthalten, aber nicht beides.

    * **Gerätegruppen:** Hierbei sind sowohl Computer als auch mobile Geräte enthalten. Bevor Sie einer Gruppe einen Computer hinzufügen können, muss dieser registriert werden. Bevor Sie einer Gruppe ein mobiles Gerät hinzufügen können, muss Ihre Umgebung für die Unterstützung mobiler Geräte konfiguriert werden, und die Geräte müssen entweder registriert oder über Exchange ActiveSync ermittelt werden.

    * **Benutzergruppen:** Eine Gruppe kann Benutzer aus Sicherheitsgruppen enthalten, die mithilfe von Active Directory synchronisiert werden. Wenn Sie keine Active Directory-Synchronisierung verwenden, können sie diese Gruppen manuell erstellen.

2. Ein Gerät oder ein Benutzer kann zu mehr als einer Gruppe gehören.

3. Mitglieder können in einer Gruppe auf Basis folgender Mitgliedschaftsregeln ein- und ausgeschlossen werden:

    * **Mitgliedschaft nach Kriterien:** Hierbei handelt es sich um dynamische Regeln, die von Intune zum Ein- bzw. Ausschließen von Mitgliedern ausgeführt werden. Von diesen Kriterien werden **Sicherheitsgruppen** und andere Informationen verwendet, die von Ihrem lokalen Active Directory (AD) synchronisiert werden. Wenn die Gruppen oder Daten geändert werden, ändert sich bei der Synchronisierung mit AD auch die Gruppenmitgliedschaft.

    * **Direkte Mitgliedschaft:** Hierbei handelt es sich um statische Regeln, durch die Mitglieder explizit hinzugefügt oder ausgeschlossen werden. Die Mitgliederliste ist statisch.

4. Zur Erstellung von Benutzer- oder Gerätegruppen, die Benutzer oder Computer enthalten, sind keine Active Directory-Domänendienste (AD DS) erforderlich. Bei Gerätegruppen, die auch mobile Geräte enthalten sollen, muss Ihre Umgebung jedoch für die Unterstützung mobiler Geräte konfiguriert werden.

    Zusätzlich müssen die Geräte ermittelt und in Intune hinzugefügt werden.

## Regeln für Gruppenbeziehungen

1. Für jede Gruppe, die Sie erstellen, muss eine übergeordnete Gruppe vorhanden sein. Nach Erstellen der Gruppe kann deren übergeordnete Gruppe nicht geändert werden.

2. Beim Hinzufügen von Benutzern oder Geräten zu einer untergeordneten Gruppe gilt Folgendes:

    * Untergeordnete Gruppen sind immer eine Teilmenge der übergeordneten Gruppe.

    * Wenn Sie einer untergeordneten Gruppe Mitglieder hinzufügen, werden diese automatisch auch der entsprechenden übergeordneten Gruppe hinzugefügt.

    * Mitglieder, die von der übergeordneten Gruppe ausgeschlossen wurden, können der untergeordneten Gruppe nicht hinzugefügt werden.

3. Die verfügbare Mitgliedschaft einer untergeordneten Gruppe wird durch die Mitgliedschaft der übergeordneten Gruppe definiert.

4. Beim Löschen einer übergeordneten Gruppe werden alle untergeordneten Gruppen gelöscht.

5. Es ist möglich, Inhalt und Richtlinien für eine übergeordnete Gruppe bereitzustellen und die Bereitstellung für untergeordnete Gruppen auszuschließen.

6. Sie können bestimmte Benutzer oder Geräte einer untergeordneten Gruppe hinzufügen, auch wenn sie kein Mitglied der übergeordneten Gruppe sind. In diesem Fall werden die neuen Gruppenmitglieder der übergeordneten Gruppe hinzugefügt.

    Mitglieder, die von der übergeordneten Gruppe ausgeschlossen wurden, können der untergeordneten Gruppe jedoch nicht hinzugefügt werden.

7. Gruppenmitgliedschaften sind rekursiv. Beispiel:

    * **Pat** ist nur bei einer Gruppe Mitglied: bei der Sicherheitsgruppe **Laptopbenutzer** .

    * Die Gruppe **Laptopbenutzer** ist Mitglied der Sicherheitsgruppe **Genehmigte Benutzer** .

    * Sie erstellen in Intune eine Gruppe, von der eine dynamische Mitgliedschaftsabfrage ausgeführt wird, die die Mitglieder der Gruppe **Genehmigte Benutzer** einschließt. Als Ergebnis enthält die Intune-Benutzergruppe das Mitglied **Pat**..

> [!TIP]
> Überlegen Sie beim Erstellen von Gruppen, wie Richtlinien angewendet werden. Sie können beispielsweise spezielle Richtlinien für Gerätebetriebssysteme, für verschiedene Rollen in Ihrer Organisation oder für bereits in Active Directory definierte Organisationseinheiten verwenden. Einige halten es für sinnvoll, spezielle Gerätegruppen für iOS, Android und Windows sowie Benutzergruppen für jede Rolle im Unternehmen zu verwenden.

<!--- should we just link to a policies topic at this point and remove this? Ask Rob
 You'll probably want to create a default policy that applies to all groups and devices, to establish the basic compliance requirements of your company. Then create more specific policies for the broadest categories of users and devices, for example, email policies for each of the device operating systems.

 Be careful naming your policies so that you can easily identify them later. For example, a good, descriptive policy name is **WP Email Policy for Entire Company**.

 Each time you create a restrictive policy you'll want to communicate it to your users, so after you create the more general groups and policies pay attention to how you create smaller groups so that you can reduce unnecessary communication.--->

## Integrierte Gruppen
In Intune sind neun integrierte Gruppen verfügbar, die Sie weder bearbeiten noch löschen können: <!--maybe a screen shot would be best?-->

-   **Allen Benutzern**
    -   Nicht gruppierte Benutzer
-   **Alle Geräte**
    -   Alle Computer
    -   Alle mobilen Geräte
        -   Alle direkt verwalteten Geräte
        -   Alle mit Exchange ActiveSync verwalteten Geräte
    -   Alle firmeneigenen Geräte
    -   Nicht gruppierte Geräte

> [!NOTE]
> Das Motto lautet: *möglichst einfach*. Wenn Ihr Unternehmen keine speziellen Anforderungen (wie z. B. die unten beschriebenen) stellt, können Sie einen schlichten Ansatz wählen und die Standardgruppenstruktur und -richtlinien übernehmen, um den Dienst langfristig leichter verwalten zu können. Die Wartung gestaltet sich einfacher, wenn Sie Ihre Benutzer mit nur leichten Unterscheidungen nach den jeweiligen Gruppen gleich behandeln können, sodass weniger Richtlinien verwaltet werden müssen.


### Alle Benutzer und Geräte in Ihrem Unternehmen
Definieren Sie eine übergeordnete Gruppe für alle Benutzer und Geräte im Unternehmen, da Sie voraussichtlich Richtlinien verwenden werden, die für alle gelten. Zu diesem Zweck können Sie die Standardgruppen **Alle Benutzer** und **Alle Geräte** in Intune verwenden. Untergruppen, die Geräte nach speziellen Eigenschaften organisieren, z. B. eine Gruppe für Ihre eigenen Geräte (Bring Your Own Device, BYOD) und eine Gruppe für unternehmenseigene Geräten (Corporate-Owned, CO), können den übergeordneten Gruppen **Alle Benutzer** und **Alle Geräte** untergeordnet sein.

## Anpassen von Gruppen für Ihre Organisation

### BYOD- und firmeneigene Geräte
Wenn Ihre Organisation Mitarbeitern die Nutzung eigener Geräte am Arbeitsplatz gestattet (BYOD), unternehmenseigene Geräte bereitstellt (CO) oder eine Kombination aus beidem zulässt, empfiehlt es sich, Richtlinien basierend auf diesen beiden Gerätekategorien anzuwenden.

Im Fall von BYOD oder eines kombinierten Ansatzes achten Sie darauf, dass Sie Ihre Richtlinien so planen, dass die vor Ort geltenden Datenschutzbestimmungen nicht verletzt werden. Erstellen Sie eine übergeordnete Gruppe für alle Benutzer, die ihre eigenen Geräte einsetzen. Diese Gruppe kann dann dazu verwendet werden, um Richtlinien anzuwenden, die für alle Benutzer in dieser Kategorie gelten.

![Screenshot der Erstellung einer übergeordneten BYOD-Gruppe](/intune/media/Group-planning/Intune_Planning_Groups_BYOD_small.png)

Ebenso können Sie eine Gruppe für die CO-Benutzer in Ihrer Organisation erstellen:

![Screenshot der gleichgeordneten Benutzergruppen für BYOD und CO](/intune/media/Group-planning/Intune_Planning_Groups_BYOD_Hierachy_View_small.png)

<!---START HERE--->

### Gruppen für geografische Regionen
Wenn Ihre Organisation Richtlinien für bestimmte Regionen benötigt, können Sie Gruppen basierend auf der geografischen Region erstellen. Sie können diese auf der Grundlage regionaler Gruppen anlegen, die Sie bereits in Active Directory (AD) erstellt haben, und sie mit Azure AD synchronisieren. Sie können sie auch direkt in Azure AD erstellen.

Diese Screenshots zeigen, wie Sie auf Basis von Gruppen, die mit dem lokalen Active Directory synchronisiert werden, entsprechende Intune-Gruppen erstellen. In diesem Beispiel wird vorausgesetzt, dass Sie über eine Active Directory-Sicherheitsgruppe namens **US Users Group** verfügen..

1. Stellen Sie zunächst die allgemeinen Informationen bereit.

    ![Screenshot des Bereichs „Gruppe bearbeiten“](/intune/media/PlanDesign/Group-planning/Intune_Planning_Groups_AD_General_small.png)

Wählen Sie unter den Mitgliedschaftskriterien die Gruppe **US Users Group**, die mit Active Directory synchronisiert wurde, als Sicherheitsgruppe aus, die unter den Mitgliedschaftsregeln verwendet wird.

![Dialogfeld „Gruppe bearbeiten“](/intune/media/Intune_Planning_Groups_AD_Criteria_small.png)

Überprüfen Sie den Vorgang, und wählen Sie dann **Fertig stellen**, um die Erstellung der Gruppe abzuschließen.

![Dialogfeld „Gruppe bearbeiten“](/intune/media/Intune_Planning_Groups_AD_Summary_small.png)

In unserem Beispiel haben wir auch eine Gruppe erstellt, die den nahen Osten und Asien (MEA) umfasst.

> [!NOTE]
> Wenn die Gruppenmitgliedschaft nicht auf Basis der Mitgliedschaft in Sicherheitsgruppen entschieden wird, stellen Sie sicher, dass Sie diesen Mitgliedern Intune-Lizenzen zugewiesen haben.

### Gruppen für bestimmte Hardware
Wenn Ihre Organisation Richtlinien benötigt, die auf bestimmte Hardwaretypen angewendet werden, können Sie die Gruppen auf Basis dieser Anforderung erstellen. Sie können diese auf der Grundlage spezieller Gruppen anlegen, die Sie bereits im lokalen Active Directory erstellt haben, und sie mit Azure AD synchronisieren. Sie können sie auch direkt in Azure AD erstellen. In diesem Beispiel verwenden wir **US Users Group** als übergeordnetes Objekt für die Gruppe der **Laptopbenutzer**.

![Dialogfeld „Sicherheitsgruppe auswählen“](/intune/media/Intune_Planning_Groups_Laptop_small.png)

An diesem Punkt sollte die Gruppenhierarchie wie folgt dargestellt werden. Wie Sie sehen, sind jetzt in der Intune-Gruppe der **Laptopbenutzer** entsprechende Mitglieder enthalten. Alle auf diese Gruppe angewendeten Richtlinien werden jetzt auf BYOD-Laptopbenutzer aus der Region „USA“ angewendet.

![Anzeigen der Gruppe „Laptopbenutzer“](/intune/media/Group-planning/Intune_Planning_Groups_Laptop_Hierarchy_small.png)

### Gruppen für bestimmte Betriebssysteme
Wenn Ihr Unternehmen Richtlinien benötigt, die auf bestimmte Betriebssysteme wie Android, iOS oder Windows angewendet werden, können Sie die Gruppen auf Basis dieser Anforderung erstellen. Wie in den vorherigen Beispielen können Sie diese auf der Grundlage betriebssystemspezifischer Gruppen anlegen, die Sie bereits im lokalen Active Directory erstellt haben, und sie mit Azure AD synchronisieren. Sie können sie auch direkt in Azure AD erstellen.

Nach derselben Methode aus den vorherigen Beispielen können wir Gruppen basierend auf Benutzern <!--devices?--> anhand bestimmter Betriebssystem-Plattformen erstellen.

> [!NOTE]
> Wenn Sie über Benutzer verfügen, die mehrere mobile Plattformen/Betriebssysteme verwenden, und Sie keine automatisierte Möglichkeit zum Kategorisieren von Benutzern als Android-, iOS- oder Windows-Benutzer haben, sollten Sie die Anwendung der Richtlinien auf Geräteebene erwägen, mit der Sie eine größere Flexibilität bei der Anwendung von betriebssystemspezifischen Richtlinien erhalten.
>
> Sie können keine Gruppen bereitstellen, die dynamisch auf dem Betriebssystem basieren. Dazu verwenden Sie AD- oder AAD-Sicherheitsgruppen.

![Anzeigen der Gruppe „Laptopbenutzer“](/intune/media/Intune_Planning_Groups_OS_Hierachy_small.png)

Nachdem alle Benutzergruppen basierend auf diesen Anforderungen des Unternehmens aufgefüllt wurden, sollte die Gruppenhierarchie in etwa wie folgt aussehen:

![Ansicht der Gruppenhierarchie](/intune/media/Intune_Planning_Groups_Midpoint_Hierachy_small.png)

Diese Hierarchie kann dazu verwendet werden, um die Richtlinien des Unternehmens entsprechend anzuwenden.

### Gerätegruppen
Sie können auch ähnliche Gruppen für Geräte erstellen, wie unten gezeigt, wobei Sie mit einer umfassenden Gruppe beginnen, die alle benutzereigenen Geräte für das BYOD-Szenario einbezieht:

![Dialogfeld „Gruppe erstellen“](/intune/media/Intune_Planning_Groups_Device_General_small.png)

Stellen Sie sicher, dass Sie die Option **Alle Geräte (Computer und mobile Geräte)** auswählen, damit die Gruppe alle BYO-Geräte umfasst:

![Seite „Mitgliedschaftskriterien definieren“](/intune/media/Intune_Planning_Groups_Device_Criteria_small.png)

Überprüfen Sie die Optionen, und wählen Sie **Fertig stellen**, um die BYOD-Gruppe zu erstellen.

![Dialogfeld „Gruppe erstellen“](/intune/media/Intune_Planning_Groups_Device_Summary_small.png)

Setzen Sie die Erstellung der Gerätegruppen fort, bis Sie über eine Gerätegruppenhierarchie verfügen, die der Benutzergruppenhierarchie ähnelt. Dann sollte der Gruppenknoten in der Intune-Konsole etwa wie folgt aussehen:

![Intune-Ansicht der Gruppenhierarchie](/intune/media/Intune_Groups_Hierarchy_Final_Small.png)

## Gruppenhierarchien und Benennungskonventionen
Zur Vereinfachung der Richtlinienverwaltung wird empfohlen, dass Sie jede Richtlinie gemäß dem Zweck, der Plattform und dem Bereich ihrer Anwendung benennen. Dieser Benennungsstandard sollte der Gruppenstruktur folgen, die Sie als Vorbereitung zur Anwendung der Richtlinien erstellt haben.

Eine Android-Richtlinie, die auf alle unternehmenseigenen mobilen Android-Geräte in den USA angewendet wird, kann z. B. wie folgt benannt werden:
**CO_US_Mob_Android_General**.

![Erstellen einer Richtlinie für Android](/intune/media/Intune_planning_policy_android_small.png)

Durch diese Art der Benennung der Richtlinien können Sie Richtlinien sowie deren vorgesehenen Zweck und Gültigkeitsbereich schnell im Richtlinienknoten der Konsole erkennen, wie nachfolgend dargestellt:

![Liste der Intune-Richtlinien](/intune/media/Intune_planning_policy_view_small.png)

## Nächste Schritte
[Erstellen von Gruppen](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


