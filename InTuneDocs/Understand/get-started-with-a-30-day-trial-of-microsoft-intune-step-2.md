---
# required metadata

title: Hinzufügen von Benutzern zu Ihrer 30-tägigen Evaluierung von Microsoft Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9e40999b-46f7-447b-8974-72af82bec7ef

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Hinzufügen von Benutzern zu Ihrer 30-tägigen Evaluierung von Microsoft Intune
Nachdem Sie nun Ihr Konto eingerichtet haben, verwenden Sie entweder den Assistenten **Neue Benutzer**, um einzelne Benutzerkonten hinzuzufügen, oder den Assistenten **Benutzer per Massenvorgang hinzufügen **, um Benutzer in einem Massenvorgang hinzuzufügen (siehe die Schritte in diesem Abschnitt).  Bevor Sie beginnen, ist es wichtig, dass Sie verstehen, wie Intune Administratorkonten behandelt.

Ein Mandantenadministrator verwendet das Office 365 Admin Center zum Hinzufügen von Benutzern zur **Benutzergruppe** von Microsoft Intune. Durch das Hinzufügen von Benutzern zur **-Benutzergruppe** werden den Benutzern Intune-Abonnementlizenzen zugewiesen, und auf diese Weise werden die Benutzer auch in der Microsoft Intune-Verwaltungskonsole angezeigt.

Administratorkonten für Intune werden nicht wie reguläre Benutzerkonten im Office 365 Admin Center erstellt. Stattdessen weisen Sie Benutzern Administratorrechte für schreibgeschützten Zugriff oder Vollzugriff zu, indem Sie die Verwaltungskonsole im Arbeitsbereich **Verwaltung** unter **Administratorverwaltung** verwenden. Dienstadministratoren, denen schreibgeschützter Zugriff zugewiesen wird, können keine Intune-Einstellungen ändern, aber sie können Daten anzeigen und Berichte ausführen. Dienstadministratoren mit Vollzugriff besitzen alle verfügbaren Administrationsrechte.

Sie können Mandantenadministratorinformationen mithilfe der Intune-Verwaltungskonsole anzeigen, Sie können darin aber keine Mandantenadministratoren erstellen. Standardmäßig wird der Besitzer des Abonnements Mandantenadministrator für Ihren Microsoft Intune-Dienst und verfügt über Vollzugriff auf sowohl das Office 365 Admin Center als auch die Intune-Verwaltungskonsole. Wir empfehlen, mindestens ein zusätzliches Mandantenadministratorkonto über das Office 365 Admin Center zu erstellen, damit Sie Aufgaben delegieren können, und um sicherzustellen, dass Sie sich nicht aus Ihrem Intune-Dienstadministratorkonto aussperren, falls Sie Ihr Kennwort vergessen.

## Hinzufügen einzelner Benutzerkonten
Führen Sie die folgenden Schritte aus, um zusätzliche Benutzerkonten in Ihrem Evaluierungsmandanten zu erstellen. Denken Sie daran, dass jedes von Ihnen hinzugefügte Benutzerkonto als eine der 100 Lizenzen gezählt wird, die Sie im Rahmen der kostenlosen Intune-Evaluierung erhalten.

1.  Wählen Sie im [Office 365 Admin Center](http://go.microsoft.com/fwlink/p/?LinkId=698854) nacheinander **Benutzer hinzufügen** &gt; **Neu**&gt; **Benutzer** aus, um den Assistenten **Neue Benutzer** zu starten.

2.  Füllen Sie auf der Seite **Details** die erforderlichen Felder aus.

3.  Geben Sie auf der Seite **Einstellungen** den **Standort** des Benutzers an.

4.  Klicken Sie auf der Seite **Gruppe** auf **Weiter**, um die Vorgaben zu übernehmen, und weisen Sie dem Benutzerkonto eine Intune-Lizenz zu.

5.  Geben Sie auf der Seite **E-Mail** bis zu fünf E-Mail-Adressen an, an die eine Benachrichtigung zum Benutzernamen und das temporäre Kennwort des Kontos gesendet werden sollen. Trennen Sie mehrere E-Mail-Adressen durch Semikola (;). Wenn Sie fertig sind, klicken Sie auf **Erstellen**, um den Benutzer Ihrem Abonnement hinzuzufügen.

6.  Auf der Seite **Ergebnisse** können Sie den neuen Kontonamen und das zugehörige temporäre Kennwort anzeigen. Das temporäre Kennwort wird von Intune automatisch erstellt.

7.  Wenn der neue Benutzer im Office 365 Admin Center angezeigt wird, überprüfen Sie, ob der neue Benutzer erfolgreich erstellt wurde:

    1.  Wählen Sie in der [Intune-Verwaltungskonsole](https://manage.microsoft.com/) nacheinander **Verwaltung** &gt; **Unternehmensportal** aus, und scrollen Sie zum unteren Rand des Bildschirms. Kopieren Sie die unter **Intune-Unternehmensportal** gezeigte URL..

    2.  Öffnen Sie ein neues Browserfenster im Datenschutzmodus (klicken Sie in Internet Explorer auf **Extras** &gt; **InPrivate-Browsen**) oder auf einem anderen Gerät, und navigieren Sie dann zu der URL, die Sie im vorigen Schritt kopiert haben. Wenn Benutzer sich nun erstmals anmelden, müssen sie ein neues Kennwort für ihr Konto angeben.

## Massenhaftes Hinzufügen von Benutzern
Um Benutzer Intune massenhaft hinzuzufügen, verwenden Sie den Assistenten **Benutzer per Massenvorgang hinzufügen**, um eine CSV-Datei (durch Trennzeichen getrennt) hochzuladen, die Ihre Benutzerdaten enthält. Links im Assistenten ermöglichen es Ihnen, eine leere Vorlage und eine CSV-Beispieldatei herunterzuladen. Die erste Zeile Ihrer CSV-Datei muss jede der Beschriftungen für die Benutzerdatenspalten in der richtigen Reihenfolge enthalten. Für jeden Benutzer in der CSV-Datei müssen der **Benutzername** (z. B. **bob@contoso.com**) und ein **Anzeigename** (wie **Bob Kelly**) enthalten sein.).

1.  Klicken Sie im [Office 365 Admin Center](http://go.microsoft.com/fwlink/p/?LinkId=698854) auf **Benutzer** &gt; **Neu**..

2.  Klicken Sie auf **Massenhinzufügen**, um den Assistenten „Massenhinzufügung von Benutzern“ zu starten.

3.  Auf der Seite **Datei auswählen** klicken Sie auf **Durchsuchen** und geben dann eine auf Ihrem Computer vorhandene CSV-Datei an, die geladen werden soll. Sie können auch eine CSV-Beispieldatei oder eine leere Vorlagendatei herunterladen, indem Sie die Links im Assistenten verwenden.

4.  Überprüfen Sie auf der Seite **Überprüfung** die Ergebnisse, und klicken Sie dann auf **Anzeigen**, um weitere Details anzuzeigen.

5.  Überprüfen Sie auf der Seite **Einstellungen**, ob der Anmeldestatus **Zugelassen** festgelegt ist, und legen Sie den **Speicherort** fest. Diese Einstellungen gelten für alle mithilfe der CSV-Datei hinzugefügten Benutzerkonten.

6.  Klicken Sie auf der Seite **Gruppe** auf **Weiter**, um die Vorgaben zu übernehmen, und weisen Sie allen Benutzerkonten, die mithilfe der CSV-Datei hinzugefügt werden, eine Intune-Lizenz zu. Standardmäßig ist das Kontrollkästchen zum Zuweisen einer Intune-Lizenz zu den Benutzerkonten aktiviert.

7.  Geben Sie auf der Seite **E-Mail** für jedes Konto bis zu fünf E-Mail-Adressen an, an die Benachrichtigungen mit den von Intune jeweils erstellten Benutzernamen und temporären Kennwörtern gesendet werden sollen. Trennen Sie mehrere E-Mail-Adressen durch Semikolons (;). Klicken Sie auf **Erstellen**, um die Benutzer Ihrem Abonnement hinzuzufügen.

8.  Auf der Seite **Ergebnisse** können Sie die Kontonamen und temporären Kennwörter der einzelnen Benutzerkonten anzeigen.

Jedes Benutzerkonto, das Sie durch Importieren hinzugefügt haben, wird nun im Office 365 Admin Center im Knoten **Benutzer** angezeigt. Wenn die neuen Benutzer sich erstmals anmelden, müssen sie für ihre Konten ein neues Kennwort angeben.

### Nächste Schritte
Gratulation! Sie haben soeben Schritt 2 der exemplarischen Vorgehensweise *Microsoft Intune-Evaluierung* ausgeführt.

>[!div class="step-by-step"]

>[&larr; **Registrieren für eine Evaluierung**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md)     [**Erstellen von Gruppen** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)  


<!--HONumber=May16_HO1-->


