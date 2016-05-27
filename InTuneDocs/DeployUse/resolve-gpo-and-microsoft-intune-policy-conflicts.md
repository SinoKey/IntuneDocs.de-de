---
# required metadata

title: Lösen von Konflikten mit Gruppenrichtlinienobjekten und Intune-Richtlinien | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e76af5b7-e933-442c-a9d3-3b42c5f5868b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Lösen von Konflikten mit Gruppenrichtlinienobjekten und Microsoft Intune-Richtlinien
In Intune können Sie Richtlinien zum Verwalten von Einstellungen auf den von Ihnen verwalteten Computern verwenden. Beispielsweise könnten Sie eine Richtlinie verwenden, um Einstellungen für die Windows-Firewall auf Computern zu steuern. Viele der Intune-Einstellungen sind mit Einstellungen vergleichbar, die Sie mit Windows-Gruppenrichtlinien konfigurieren können. Es ist allerdings manchmal möglich, dass die beiden Methoden miteinander in Konflikt stehen.

Wenn Konflikt auftreten, hat die Gruppenrichtlinie auf Domänenebene Vorrang vor der Intune-Richtlinie, sofern die Anmeldung des Computers bei der Domäne möglich ist. In diesem Fall wird die Intune-Richtlinie auf den Clientcomputer angewendet.

## Vorgehensweise bei Verwendung von Gruppenrichtlinien
Stellen Sie sicher, dass die Richtlinien, die Sie anwenden, nicht von Gruppenrichtlinien verwaltet werden. Zum Vermeiden von Konflikten können Sie eine oder mehrere der folgenden Methoden verwenden:

-   Verschieben Sie Ihre Computer in eine Active Directory-Organisationseinheit (OU), auf die keine Gruppenrichtlinien angewendet werden, bevor Sie den Intune-Client installieren. Sie können bei OUs mit Computern, die in Intune registriert sind und auf die Sie die Gruppenrichtlinieneinstellungen nicht anwenden möchten, auch die Vererbung der Gruppenrichtlinie deaktivieren.

-   Verwenden Sie einen WMI-Filter oder einen Sicherheitsfilter, um Gruppenrichtlinienobjekte auf Computer zu beschränken, die nicht mit Intune verwaltet werden. Weitere Informationen und Beispiele hierzu finden Sie unter [Filtern vorhandener Gruppenrichtlinienobjekte, um Konflikte mit Microsoft Intune-Richtlinien zu vermeiden](resolve-gpo-and-microsoft-intune-policy-conflicts.md#BKMK_Filter).

-   Deaktivieren oder entfernen Sie Gruppenrichtlinienobjekte, die mit den Intune-Richtlinien in Konflikt stehen.

Weitere Informationen zu Active Directory und Windows-Gruppenrichtlinien finden Sie in Ihrer Windows Server-Dokumentation.

## Filtern vorhandener Gruppenrichtlinienobjekte, um Konflikte mit Intune-Richtlinien zu vermeiden
Wenn Sie Gruppenrichtlinienobjekte ermittelt haben, deren Einstellungen in Konflikt mit Intune-Richtlinien stehen, können Sie eine der folgenden Filtermethoden anwenden, um diese Gruppenrichtlinienobjekte auf Computer zu beschränken, die nicht mit Intune verwaltet werden.

### Verwenden von WMI-Filtern
Von WMI-Filtern werden GPOs selektiv auf Computer angewendet, die die Bedingungen einer Abfrage erfüllen. Stellen Sie zum Anwenden eines WMI-Filters für alle Computer im Unternehmen eine WMI-Klasseninstanz bereit, bevor Sie Computer beim Intune-Dienst registrieren.

#### So wenden Sie WMI-Filter auf ein GPO an

1.  Erstellen Sie eine Verwaltungsobjektdatei, indem Sie Folgendes kopieren und in eine Textdatei einfügen und diese dann an einem geeigneten Speicherort unter dem Namen **WIT.mof** speichern. Die Datei enthält die WMI-Klasseninstanz, die Sie für Computer bereitstellen, die Sie beim Intune-Dienst registrieren möchten.

    ```
    //Beginning of MOF file.
    #pragma classflags("forceupdate")
    #pragma namespace ("\\\\.\\Root")
    instance of __Namespace
    {
       Name = "WindowsIntune";
    };

    #pragma namespace ("\\\\.\\Root\\WindowsIntune")
    [
       Description("This class defines Microsoft Intune common properties")
    ]
    class WindowsIntune_ManagedNode
    {
       [ read, Description("This defines whether Microsoft Intune Policy is enabled"): DisableOverride ToSubClass ]
       boolean WindowsIntunePolicyEnabled;
       [ read, key, Description("This property defines the version." "Example: 1.0"): ToSubClass ]
       string Version;
    };

    instance of WindowsIntune_ManagedNode
    {
       Version = "1.0";
       WindowsIntunePolicyEnabled = 1;
    };
    ```

2.  Verwenden Sie zum Bereitstellen der Datei entweder ein Startskript oder eine Gruppenrichtlinie. Das Folgende ist der Bereitstellungsbefehl für das Startskript. Bevor Sie Clientcomputer beim Intune-Dienst registrieren, muss die WMI-Klasseninstanz bereitgestellt werden.

    **C:/Windows/System32/Wbem/MOFCOMP &lt;Pfad zur MOF-Datei&gt;\wit.mof**

3.  Führen Sie einen der folgenden Befehle aus, um die WMI-Filter zu erstellen. Welchen Befehl Sie ausführen, hängt davon ab, ob das zu filternde Gruppenrichtlinienobjekt für über Intune verwaltete Computer gilt oder für Computer, die nicht über Intune verwaltet werden.

    -   Verwenden Sie für Gruppenrichtlinienobjekte, die für nicht über Intune verwaltete Computer gelten, den folgenden Befehl:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=0
        ```

    -   Verwenden Sie für Gruppenrichtlinienobjekte, die für über Intune verwaltete Computer gelten, den folgenden Befehl:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=1
        ```

4.  Bearbeiten Sie das GPO in der Gruppenrichtlinien-Verwaltungskonsole so, dass der im vorangegangenen Schritt erstellte WMI-Filter zur Anwendung kommt.

    -   Für Gruppenrichtlinienobjekte, die nur für über Intune verwaltete Computer gelten sollen, wenden Sie den Filter **WindowsIntunePolicyEnabled=1** an..

    -   Für Gruppenrichtlinienobjekte, die nur für nicht über Intune verwaltete Computer gelten sollen, wenden Sie den Filter **WindowsIntunePolicyEnabled=0** an..

Weitere Informationen zum Anwenden von WMI-Filtern bei Gruppenrichtlinien finden Sie im Blogbeitrag [Security Filtering, WMI Filtering, and Item-level Targeting in Group Policy Preferences](http://go.microsoft.com/fwlink/?LinkId=177883) (Sicherheitsfilterung, WMI-Filterung und Zielgruppenadressierung auf Elementebene in Gruppenrichtlinieneinstellungen)..

### Verwenden von Sicherheitsgruppenfiltern
Mit einer Gruppenrichtlinie können Sie GPOs auf nur die Sicherheitsgruppen anwenden, die im Bereich **Sicherheitsfilterung** der Gruppenrichtlinien-Verwaltungskonsole für ein ausgewähltes GPO festgelegt sind. Standardmäßig gelten Gruppenrichtlinienobjekte für **Authentifizierte Benutzer**..

-   Erstellen Sie im Snap-In **Active Directory-Benutzer und -Computer** eine neue Sicherheitsgruppe, die Computer und Benutzerkonten enthält, die nicht über Intune verwaltet werden sollen. Nennen Sie die Gruppe z. B. **Nicht in Microsoft Intune**..

-   Klicken Sie auf der Registerkarte **Delegierung** in der Gruppenrichtlinien-Verwaltungskonsole mit der rechten Maustaste auf die neue Sicherheitsgruppe, um den Benutzern und Computern in der Sicherheitsgruppe die geeigneten Berechtigungen **Lesen** und **Gruppenrichtlinie übernehmen** zu delegieren. (Die Berechtigungen**Gruppenrichtlinie übernehmen** befinden sich im Dialogfeld **Erweitert** .)

-   Wenden Sie dann den neuen Sicherheits-Gruppenfilter auf ein ausgewähltes Gruppenrichtlinienobjekt an, und entfernen Sie den Standardfilter **Authentifizierte Benutzer** .

Die neue Sicherheitsgruppe muss in den Intune-Dienständerungen als Registrierung verwaltet werden.

### Weitere Informationen:
[Verwalten von Windows-PCs mit Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


