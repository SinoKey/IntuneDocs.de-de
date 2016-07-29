---
title: "Registrieren mit dem Geräteregistrierungs-Manager | Microsoft Intune"
description: "Das Geräteregistrierungs-Manager-Konto (Device Enrollment Manager, DEM) kann eine große Anzahl gemeinsam genutzter, firmeneigener mobiler Geräte mit einem einzigen Benutzerkonto verwalten."
keywords: 
author: NathBarn
manager: arob98
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1e0d05a4f229e2a8e72d1d60021b159f12dfa0d1
ms.openlocfilehash: 5c7eecf5b7801eca3d23dd0eee954203e9c9cb06


---


# Registrieren von firmeneigenen Geräten mit dem Geräteregistrierungs-Manager in Microsoft Intune
Mit Intune können Organisationen eine Vielzahl mobiler Geräte mit einem einzelnen Benutzerkonto verwalten. Das Konto *Geräteregistrierungs-Manager* ist ein spezielles Intune-Konto mit der Berechtigung, bis zu 1.000 Geräte zu registrieren. Verwenden Sie Geräte, die mithilfe des Geräteregistrierungs-Managerkontos als freigegebene Geräte registriert wurden, statt persönlicher („BYOD“) Geräte. Die Benutzer werden beispielsweise keine „nativen“ E-Mail-Apps verwenden können. Sie können beispielsweise einem Speicher-Manager oder Supervisor ein Benutzerkonto für einen Geräteregistrierungs-Manager zuweisen, um ihm folgende Möglichkeiten zu geben:

-   Registrieren von Geräten in Intune

-   Anmelden beim Unternehmensportal, um Unternehmens-Apps abzurufen

-   Installieren und Deinstallieren von Software

-   Konfigurieren des Zugriffs auf Unternehmensdaten


**Beispiele für ein Geräteregistrierungs-Manager-Szenario:** Ein Restaurant wünscht Point-of-Sale-Tablets für sein Bedienpersonal und Bestellmonitore für seine Küchenmitarbeiter. Die Mitarbeiter müssen niemals auf Unternehmensdaten zugreifen und sich nie als Benutzer anmelden. Der Intune-Administrator erstellt ein Konto für den Geräteregistrierungs-Manager und registriert die firmeneigenen Geräte mit diesem Konto. Alternativ kann der Administrator die Anmeldeinformationen des Geräteregistrierungs-Managers einem Restaurant-Manager geben, sodass dieser die Geräte registrieren und verwalten kann.

Der Administrator oder Manager kann rollenspezifische Apps auf den Restaurantgeräten bereitstellen. Ein Administrator kann das Gerät auch in der Intune-Konsole auswählen und es über die Verwaltungskonsole aus der Verwaltung mobiler Geräte entfernen.

Für Geräte, die mit einem Geräteregistrierungs-Managerkonto registriert wurden, gelten folgende Einschränkungen:
  - Kein bestimmter Benutzer – alle Geräte sind „benutzerlos“. Das heißt, es ist kein E-Mail-Zugriff und kein Zugriff auf Unternehmensdaten möglich. Allerdings können z. B. die Geräte-Apps über VPN auf Daten zugreifen.
  - Kein bedingter Zugriff, da dies benutzerspezifische Szenarien voraussetzen würde.
  - Ein Zurücksetzen von Geräten über das Unternehmensportal ist nicht möglich.
  - Nur das lokale Gerät erscheint in der Unternehmensportal-App oder -Website
  - Apps aus dem Apple Volume Purchase Program (VPP) können nicht verwendet werden, weil für die Verwaltung dieser Apps benutzerspezifische Apple IDs erforderlich sind.
  - Eine gleichzeitige Registrierung mit Apple Configurator oder mit dem Apple-Geräteregistrierungsprogramm ist nicht möglich (iOS-Geräte).

> [!NOTE]
> Um Unternehmens-Apps auf Geräten bereitzustellen, die mit dem Geräteregistrierungs-Manager verwaltet werden, stellen Sie die Unternehmensportal-App als **erforderliche Installation** für das Benutzerkonto des Geräteregistrierungs-Managers bereit.
> Zur Verbesserung der Leistung werden beim Anzeigen der Unternehmensportal-App auf einem mit dem Geräteregistrierungs-Manager verwalteten Gerät nur das lokale Gerät angezeigt. Für die Remoteverwaltung anderer vom Geräteregistrierungs-Manager verwalteter Geräte muss die Intune-Verwaltungskonsole verwendet werden.

## Erstellen von Konten für Geräteregistrierungs-Manager
Konten für Geräteregistrierungs-Manager sind Benutzerkonten mit der Berechtigung, eine große Anzahl firmeneigener Geräten anzumelden. Nur Benutzer in der Intune-Konsole können Geräteregistrierungs-Manager sein.

#### Hinzufügen eines Geräteregistrierungs-Managers zu Intune

1.  Navigieren Sie zum [Microsoft Intune-Kontenportal](http://go.microsoft.com/fwlink/?LinkId=698854), und melden Sie sich bei Ihrem Administratorkonto an.

2.  Wählen Sie **Benutzer hinzufügen** aus.

3.  Vergewissern Sie sich, dass das Benutzerkonto aufgeführt wird, das ein Geräteregistrierungs-Manager werden soll. Ist dies nicht der Fall, fügen Sie den Benutzer hinzu, indem Sie **Neu** auswählen und den Prozess zum Hinzufügen eines Benutzers ausführen. Eine Abonnementlizenz ist für jeden Benutzer erforderlich, der auf den Dienst zugreift und der *Geräteregistrierungs-Manager* kann kein Intune-Administrator sein. Stellen Sie fest, ob Sie weitere Lizenzen benötigen, bevor Sie diese Funktion verwenden.

4.  Melden Sie sich bei der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) mit Ihren Administratoranmeldedaten an.

5.  Wählen Sie im Navigationsbereich **Admin** aus, gehen Sie zur **Administratorverwaltung**, und wählen Sie **Geräteregistrierungs-Manager** aus. Die Seite "Geräteregistrierungs-Manager" wird geöffnet.

6.  Wählen Sie **Hinzufügen…** aus. Das Dialogfeld **Geräteregistrierungs-Manager hinzufügen** wird geöffnet.

7.  Geben Sie die **Benutzer-ID** des Intune-Kontos ein, und wählen Sie anschließend **OK** aus. Der Geräteregistrierungs-Manager kann kein Intune-Administrator sein.

8.  Der Geräteregistrierungs-Manager kann nun Mobilgeräte über das Verfahren registrieren, das ein Endbenutzer für ein BYOD-Szenario im Unternehmensportal verwendet.

## Löschen eines Geräteregistrierungs-Managers aus Intune

1.  Melden Sie sich beim [Microsoft Intune-Verwaltungsportal](http://manage.microsoft.com) mit Ihren Administratoranmeldedaten an.

2.  Wählen Sie im Navigationsbereich **Admin** aus, gehen Sie zur **Administratorverwaltung**, und wählen Sie **Geräteregistrierungs-Manager** aus. Die Seite "Geräteregistrierungs-Manager" wird geöffnet.

3.  Wählen Sie den **Geräteregistrierungs-Managerbenutzer** aus, den Sie löschen möchten, und wählen Sie anschließend **Löschen** aus. Dieser Benutzer wird nicht aus Intune gelöscht, und die Geräte, die diese Benutzer verwaltet, bleiben in Intune angemeldet. Durch das Löschen eines Geräteregistrierungs-Manager wird verhindert, dass der Benutzer mehr Geräte in Intune registrieren kann.

4.  Wählen Sie **Ja** aus, um das Löschen des Geräteregistrierungs-Managers zu bestätigen.

Wenn Sie einen Geräteregistrierungs-Manager löschen, wirkt sich dies nicht auf registrierte Geräte aus. Wenn ein Geräteregistrierungs-Manager gelöscht wird:

-   sind keine registrierten Geräte betroffen

-   werden registrierte Geräte weiterhin vollständig verwaltet

-   bleiben die gelöschten Kontoanmeldedaten für den Geräteregistrierungs-Manager für die Anmeldung beim Unternehmensportal zum Zugriff auf Apps gültig

-   können über die Kontoanmeldedaten für den Geräteregistrierungs-Manager weiterhin keine Geräte zurückgesetzt oder deaktiviert werden

-   bleibt die Beziehung des gelöschten Geräteregistrierungs-Manager-Kontos zu registrierten Geräten bestehen, es können jedoch keine zusätzlichen Geräte registriert werden.



<!--HONumber=Jul16_HO3-->


