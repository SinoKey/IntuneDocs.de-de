---
title: "Registrieren mit dem Geräteregistrierungs-Manager | Microsoft Intune"
description: "Das Geräteregistrierungs-Manager-Konto (Device Enrollment Manager, DEM) kann eine große Anzahl gemeinsam genutzter, firmeneigener mobiler Geräte mit einem einzigen Benutzerkonto verwalten."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 289e6019aa1a17deb91b38ed32f0432af0902a9d
ms.openlocfilehash: 51e5f248c5e8759d5992918a99e1f114e2614142


---


# <a name="enroll-corporateowned-devices-with-the-device-enrollment-manager-in-microsoft-intune"></a>Registrieren von firmeneigenen Geräten mit dem Geräteregistrierungs-Manager in Microsoft Intune
Mit Intune können Organisationen eine Vielzahl mobiler Geräte mit einem einzelnen Benutzerkonto verwalten. Das Konto *Geräteregistrierungs-Manager* ist ein spezielles Intune-Konto mit dem bis zu 1.000 Geräte registriert werden können. Es empfiehlt sich, Geräte zu verwenden, die mithilfe dieses Kontos als freigegebene Geräte registriert wurden, statt persönlicher („BYOD“) Geräte. Die Benutzer werden beispielsweise keine „nativen“ E-Mail-Apps verwenden können.

Sie können beispielsweise einem Speicher-Manager oder Supervisor ein Benutzerkonto für einen Geräteregistrierungs-Manager zuweisen, um ihm folgende Möglichkeiten zu geben:

-   Registrieren von Geräten in Intune

-   Anmelden beim Unternehmensportal, um Unternehmens-Apps abzurufen

-   Installieren und Deinstallieren von Software

-   Konfigurieren des Zugriffs auf Unternehmensdaten


**Geräteregistrierungs-Manager-Szenario:** Ein Restaurant wünscht Point-of-Sale-Tablets für sein Bedienpersonal und Bestellmonitore für seine Küchenmitarbeiter. Die Mitarbeiter müssen niemals auf Unternehmensdaten zugreifen und sich nie als Benutzer anmelden. Der Intune-Administrator erstellt ein Konto für den Geräteregistrierungs-Manager und registriert die firmeneigenen Geräte mit diesem Konto. Alternativ kann der Administrator die Anmeldeinformationen des Geräteregistrierungs-Managers einem Restaurant-Manager geben, sodass dieser die Geräte registrieren und verwalten kann.

Der Administrator oder Manager kann rollenspezifische Apps auf den Restaurantgeräten bereitstellen. Ein Administrator kann das Gerät auch in der Intune-Konsole auswählen und es über die Verwaltungskonsole aus der Verwaltung mobiler Geräte entfernen.

Für Geräte, die mit einem Geräteregistrierungs-Manager-Konto registriert wurden, gelten folgende Einschränkungen:
  - Kein bestimmter Benutzer – alle Geräte sind „benutzerlos“. Das heißt, es ist kein E-Mail-Zugriff und kein Zugriff auf Unternehmensdaten möglich. Allerdings können z. B. die Geräte-Apps über VPN auf Daten zugreifen.
  - Kein bedingter Zugriff, da dies benutzerspezifische Szenarien voraussetzen würde.
  - Ein Zurücksetzen von Geräten über das Unternehmensportal ist nicht möglich.
  - Nur das lokale Gerät erscheint in der Unternehmensportal-App oder -Website.
  - Apps aus dem Apple Volume Purchase Program (VPP) können nicht verwendet werden, weil für die Verwaltung dieser Apps benutzerspezifische Apple IDs erforderlich sind.
  - (iOS) Diese Geräte können auch nicht mit Apple Configurator oder dem Apple-Programm zur Geräteregistrierung (Apple Device Enrollment Program, DEP) registriert werden. Mithilfe von DEP oder Apple Configurator verwaltete Geräte können jedoch ohne Benutzeraffinität registriert werden.

> [!NOTE]
> Um Unternehmens-Apps auf Geräten bereitzustellen, die mit dem Geräteregistrierungs-Manager verwaltet werden, stellen Sie die Unternehmensportal-App als **erforderliche Installation** für das Benutzerkonto des Geräteregistrierungs-Managers bereit.
> Zur Verbesserung der Leistung werden beim Anzeigen der Unternehmensportal-App auf einem mit dem Geräteregistrierungs-Manager verwalteten Gerät nur das lokale Gerät angezeigt. Für die Remoteverwaltung anderer vom Geräteregistrierungs-Manager verwalteter Geräte muss die Intune-Verwaltungskonsole verwendet werden.

## <a name="create-device-enrollment-manager-accounts"></a>Erstellen von Konten für Geräteregistrierungs-Manager
Konten für Geräteregistrierungs-Manager sind Benutzerkonten mit der Berechtigung, eine große Anzahl firmeneigener Geräten anzumelden. Nur Benutzer in der Intune-Konsole können Geräteregistrierungs-Manager sein.

#### <a name="add-a-device-enrollment-manager-to-intune"></a>Hinzufügen eines Geräteregistrierungs-Managers zu Intune

1.  Navigieren Sie zum [Microsoft Intune-Kontenportal](http://go.microsoft.com/fwlink/?LinkId=698854), und melden Sie sich bei Ihrem Administratorkonto an.

2.  Wählen Sie **Benutzer hinzufügen** aus.

3.  Vergewissern Sie sich, dass das Benutzerkonto aufgeführt wird, das ein Geräteregistrierungs-Manager werden soll. Ist dies nicht der Fall, fügen Sie den Benutzer hinzu, indem Sie **Neu** auswählen und den Prozess zum **Hinzufügen eines Benutzers** ausführen. Für jeden Benutzer, der auf den Dienst zugreift, wird eine Abonnementlizenz benötigt. Der Geräteregistrierungs-Manager kann kein Intune-Administrator sein. Prüfen Sie, ob Sie weitere Lizenzen benötigen, bevor Sie diese Funktion verwenden.

4.  Melden Sie sich bei der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) mit Ihren Administratoranmeldedaten an.

5.  Wählen Sie im Navigationsbereich **Admin** aus, gehen Sie zur **Administratorverwaltung**, und wählen Sie **Geräteregistrierungs-Manager** aus. Die Seite **Geräteregistrierungs-Manager** wird geöffnet.

6.  Wählen Sie **Hinzufügen…** aus. Das Dialogfeld **Geräteregistrierungs-Manager hinzufügen** wird geöffnet.

7.  Geben Sie die **Benutzer-ID** des Intune-Kontos ein, und klicken Sie anschließend auf **OK**. Der Geräteregistrierungs-Manager kann kein Intune-Administrator sein.

8.  Der Geräteregistrierungs-Manager kann nun Mobilgeräte über dasselbe Verfahren registrieren, das ein Endbenutzer für ein BYOD-Szenario im Unternehmensportal verwendet.

## <a name="delete-a-device-enrollment-manager-from-intune"></a>Löschen eines Geräteregistrierungs-Managers aus Intune

1.  Melden Sie sich beim [Microsoft Intune-Verwaltungsportal](http://manage.microsoft.com) mit Ihren Administratoranmeldedaten an.

2.  Wählen Sie im Navigationsbereich **Admin** aus, gehen Sie zur **Administratorverwaltung**, und wählen Sie **Geräteregistrierungs-Manager** aus. Die Seite **Geräteregistrierungs-Manager** wird geöffnet.

3.  Wählen Sie den **Geräteregistrierungs-Managerbenutzer** aus, den Sie löschen möchten, und wählen Sie anschließend **Löschen** aus. Dieser Benutzer wird nicht aus Intune gelöscht, und die Geräte, die diese Benutzer verwaltet, bleiben in Intune angemeldet. Durch das Löschen eines Geräteregistrierungs-Manager wird verhindert, dass der Benutzer mehr Geräte in Intune registrieren kann.

4.  Wählen Sie **Ja** aus, um das Löschen des Geräteregistrierungs-Managers zu bestätigen.

Wenn Sie einen Geräteregistrierungs-Manager löschen, wirkt sich dies nicht auf registrierte Geräte aus. Wenn ein Geräteregistrierungs-Manager gelöscht wird:

-   sind keine registrierten Geräte betroffen

-   werden registrierte Geräte weiterhin vollständig verwaltet

-   bleiben die gelöschten Kontoanmeldedaten für den Geräteregistrierungs-Manager für die Anmeldung beim Unternehmensportal zum Zugriff auf Apps gültig

-   können über die Kontoanmeldedaten für den Geräteregistrierungs-Manager weiterhin keine Geräte zurückgesetzt oder deaktiviert werden

-   bleibt die Beziehung des gelöschten Geräteregistrierungs-Manager-Kontos zu registrierten Geräten bestehen, es können jedoch keine zusätzlichen Geräte registriert werden



<!--HONumber=Nov16_HO1-->


