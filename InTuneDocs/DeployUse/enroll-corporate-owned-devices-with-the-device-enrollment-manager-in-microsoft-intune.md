---
# required metadata

title: Registrieren von firmeneigenen Geräten mit dem Geräteregistrierungs-Manager in Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Registrieren von firmeneigenen Geräten mit dem Geräteregistrierungs-Manager in Microsoft Intune
Mit Intune können Organisationen eine Vielzahl mobiler Geräte mit einem einzelnen Benutzerkonto verwalten. Das Konto *Geräteregistrierungs-Manager* ist ein spezielles Intune-Konto mit Berechtigung zum Registrieren von mehr als fünf Geräten. Sie können beispielsweise einem Speicher-Manager oder Supervisor ein Benutzerkonto für einen Geräteregistrierungs-Manager zuweisen, um ihm folgende Möglichkeiten zu geben:

-   Registrieren von Geräten in Intune

-   Anmelden beim Unternehmensportal, um Unternehmens-Apps abzurufen

-   Installieren und Deinstallieren von Software

-   Konfigurieren des Zugriffs auf Unternehmensdaten

Verwenden Sie das Geräte-Manager-Konto nur für Geräte, die keine E-Mails empfangen, oder melden Sie sich als ein bestimmter Benutzer an. Geräte, die mit einem Geräte-Manager-Konto verwaltet werden, können nicht für bedingten Zugriff konfiguriert werden, da es sich dabei auch um benutzerspezifische Szenarien handelt. Der Speicher-Manager kann das Gerät nicht über das Unternehmensportal zurücksetzen.

**Beispiele für ein Geräteregistrierungs-Manager-Szenario:**
Ein Restaurant wünscht Point-of-Sale-Tablets für sein Bedienpersonal und die Bestellmonitore für seine Küchenmitarbeiter. Die Mitarbeiter müssen niemals auf Unternehmensdaten zugreifen und sich nie als Benutzer anmelden. Der Intune-Administrator erstellt ein Konto für den Geräteregistrierungs-Manager und registriert die firmeneigenen Geräte mit diesem Konto. Alternativ kann der Administrator die Anmeldeinformationen des Geräteregistrierungs-Managers einem Restaurant-Manager geben, sodass dieser die Geräte registrieren und verwalten kann.

Der Administrator oder Manager kann rollenspezifische Apps auf den Restaurantgeräten bereitstellen. Ein Administrator kann das Gerät auch in der Intune-Konsole auswählen und es über die Verwaltungskonsole aus der Verwaltung mobiler Geräte entfernen.

> [!NOTE]
> Benutzerkonten für Geräteregistrierungs-Manager mit mehr als 20 registrierten Geräten haben möglicherweise Probleme bei der Verwendung der Unternehmensportal-App. Um Geräten, die mit dem Geräteregistrierungs-Manager verwaltet werden, Unternehmensportal-Apps bereitzustellen, stellen Sie die Unternehmensportal-App als **erforderliche Installation** für das Benutzerkonto des Geräteregistrierungs-Managers bereit.

## Erstellen von Konten für Geräteregistrierungs-Manager
Konten für Geräteregistrierungs-Manager sind Benutzerkonten mit der Berechtigung, eine große Anzahl firmeneigener Geräten anzumelden. Nur Benutzer in der Intune-Konsole können Geräteregistrierungs-Manager sein.

#### Hinzufügen eines Geräteregistrierungs-Managers zu Intune

1.  Navigieren Sie zum [Microsoft Intune-Kontenportal](http://go.microsoft.com/fwlink/?LinkId=698854), und melden Sie sich bei Ihrem Administratorkonto an.

2.  Klicken Sie auf **Benutzer hinzufügen**..

3.  Vergewissern Sie sich, dass das Benutzerkonto aufgeführt wird, das ein Geräteregistrierungs-Manager werden soll. Ist dies nicht der Fall, fügen Sie den Benutzer hinzu, indem Sie auf **Neu** klicken und den Prozess zum Hinzufügen eines Benutzers ausführen. Eine Abonnementlizenz ist für jeden Benutzer erforderlich, der auf den Dienst zugreift und der *Geräteregistrierungs-Manager* kann kein Intune-Administrator sein. Stellen Sie fest, ob Sie weitere Lizenzen benötigen, bevor Sie diese Funktion verwenden.

4.  Melden Sie sich bei der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) mit Ihren Administratoranmeldedaten an.

5.  Klicken Sie im Navigationsbereich auf **Admin**, gehen Sie zu **Administratorverwaltung** , und wählen Sie **Geräteregistrierungs-Manager**. Die Seite "Geräteregistrierungs-Manager" wird geöffnet.

6.  Klicken Sie auf **Hinzufügen…**. Das Dialogfeld **Geräteregistrierungs-Manager hinzufügen** wird geöffnet.

7.  Geben Sie die **Benutzer-ID** des Intune-Kontos ein, und klicken Sie auf **OK**. Der Geräteregistrierungs-Manager kann kein Intune-Administrator sein.

8.  Der Geräteregistrierungs-Manager kann nun Mobilgeräte über das Verfahren registrieren, das ein Endbenutzer für ein BYOD-Szenario im Unternehmensportal verwendet.

## Löschen eines Geräteregistrierungs-Managers aus Intune

1.  Melden Sie sich beim [Microsoft Intune-Verwaltungsportal](http://manage.microsoft.com) mit Ihren Administratoranmeldedaten an.

2.  Klicken Sie im Navigationsbereich auf **Admin** , gehen Sie zu **Administratorverwaltung** , und wählen Sie **Geräteregistrierungs-Manager**. Die Seite "Geräteregistrierungs-Manager" wird geöffnet.

3.  Wählen Sie den Registrierungs-Manager- **Benutzer** aus, den Sie löschen möchten, und klicken Sie dann auf **Löschen**. Dieser Benutzer wird nicht aus Intune gelöscht, und die Geräte, die diese Benutzer verwaltet, bleiben in Intune angemeldet. Durch das Löschen eines Geräteregistrierungs-Manager wird verhindert, dass der Benutzer mehr Geräte in Intune registrieren kann.

4.  Klicken Sie auf **Ja** , um das Löschen des Geräteregistrierungs-Managers zu bestätigen.

Wenn Sie einen Geräteregistrierungs-Manager löschen, wirkt sich dies nicht auf registrierte Geräte aus. Wenn ein Geräteregistrierungs-Manager gelöscht wird:

-   sind keine registrierten Geräte betroffen

-   werden registrierte Geräte weiterhin vollständig verwaltet

-   bleiben die gelöschten Kontoanmeldedaten für den Geräteregistrierungs-Manager für die Anmeldung beim Unternehmensportal zum Zugriff auf Apps gültig

-   können über die Kontoanmeldedaten für den Geräteregistrierungs-Manager weiterhin keine Geräte zurückgesetzt oder deaktiviert werden

-   bleibt die Beziehung des gelöschten Geräteregistrierungs-Manager-Kontos zu registrierten Geräten bestehen, es können jedoch keine zusätzlichen Geräte registriert werden.


<!--HONumber=May16_HO1-->


