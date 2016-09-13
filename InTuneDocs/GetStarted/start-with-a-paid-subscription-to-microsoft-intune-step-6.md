---
title: "Erstellen von Richtlinien und Veröffentlichen einer App | Microsoft Intune"
description: "Erläutert das Erstellen und Veröffentlichen von Richtlinien anhand einer Beispiel-App für Ihr Intune-Abonnement."
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0c1e08cc49d75303f6793894e3c8a040f6e7a8b1
ms.openlocfilehash: 0bf3eb60b60e8ad1c91d3010230a41ce5d863dfe


---

# Erstellen von Richtlinien und Veröffentlichen einer App
Mit Intune-Richtlinien stehen Einstellungen bereit, mit deren Hilfe Sie die Sicherheitseinstellungen auf mobilen Geräten steuern, die Windows-Firewall- und Endpoint Protection-Einstellungen für Computer warten und Anwendungen bereitstellen können. Weitere Informationen finden Sie unter [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](/Intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) und [Schützen von Windows-PCs mit Endpoint Protection für Microsoft Intune](/Intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).

Sie können zwei Arten von App-Installationen mithilfe von Intune ausführen: Die erste ist eine **erforderliche Installation**, bei der die App automatisch auf verwalteten Computern bereitgestellt wird. Die andere ist eine **verfügbare Installation**, bei der die App oder ein Link auf die App über das Intune-Unternehmensportal bereitgestellt wird, damit Benutzer auswählen können, ob die App auf ihren Computern oder mobilen Geräten installiert werden soll.

Mithilfe der folgenden Schritte können Sie eine Konfigurationsrichtlinie für mobile Geräte und eine Firewallrichtlinie für Windows-PCs einrichten. Darüber hinaus können Sie Skype als verfügbare Installation für mobile Geräte konfigurieren, nachdem diese registriert wurden.

> [!TIP]
> Nachdem Sie eine neue Richtlinie hinzugefügt und bereitgestellt haben, erben alle Benutzer oder Geräte in der Gruppe, für die Sie die Richtlinie bereitgestellt haben, die Einstellungen als Basisrichtlinie. Sie können die Details dieser Richtlinien später jederzeit über den Arbeitsbereich für Richtlinien überprüfen und bearbeiten.


## Erstellen und Bereitstellen einer Konfigurationsrichtlinie für mobile Geräte

1.  Öffnen Sie die [Intune-Verwaltungskonsole](https://manage.microsoft.com/).

2.  Klicken Sie im linken Bereich auf das Symbol **Richtlinie**.

    ![admin-console-policy-workspace](./media/policy.png)

3.  Klicken Sie auf der Seite **Richtlinienübersicht** in der Liste **Aufgaben** auf **Richtlinie hinzufügen**.

4.  Erweitern Sie in der Richtlinienliste die Plattform, für die Sie eine Richtlinie erstellen möchten, und klicken Sie auf **Allgemeine Konfiguration** > **Richtlinie mit den empfohlenen Einstellungen erstellen und bereitstellen** > **Richtlinie erstellen**.

> [!NOTE]
> Es gibt keine empfohlenen Einstellungen für Gerätekonfigurationsrichtlinien, da Sie aus vielen Optionen wählen können. Sie müssen eine benutzerdefinierte Gerätekonfigurationsrichtlinie erstellen.


5.  Wählen Sie bei der Aufforderung **Wählen Sie die Gruppen aus, denen die Richtlinie bereitgestellt werden soll** in der Liste der verfügbaren Gruppen eine Gruppe aus, und wählen Sie **Hinzufügen** > **OK**.

Die Richtlinie wird in der Liste der Konfigurationsrichtlinien angezeigt und wurde für die Gruppe **Intune-Benutzer** bereitgestellt. Doppelklicken Sie auf die Richtlinie, um die Einstellungen anzuzeigen.

## Veröffentlichen der Skype-App für mobile Geräte

1.  Klicken Sie in der [Intune-Verwaltungskonsole](https://manage.microsoft.com/) auf das Symbol **Apps** und dann auf **Apps** > **App hinzufügen**. Geben Sie Ihre [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Anmeldeinformationen ein, wenn Sie dazu aufgefordert werden.

    ![admin-console-apps-workspace](./media/apps.png)

    > [!NOTE]
    > Wenn Sie den **Intune-Softwareherausgeber** erstmals ausführen, kommt es zu einer kurzen Verzögerung, während die Anwendung installiert wird.

2.  Überprüfen Sie die Sicherheitswarnung, und klicken Sie auf **Ausführen**.

3.  Klicken Sie auf der Seite **Vorbereitung** auf **Weiter**.

4.  Wählen Sie auf der Seite **Softwaresetup** unter **Wählen Sie aus, wie diese Software für Geräte bereitgestellt werden soll** die Option **Externer Link** aus.

5.  Geben Sie unter **Geben Sie die URL an** den externen Link für die Software ein, und klicken Sie dann auf **Weiter**. Achten Sie darauf, der URL **http://** voranzustellen. Verwenden Sie für die Skype-App den nachfolgenden Link, der der Plattform für mobile Geräte entspricht, die Sie verwenden:

    -   **iOS:** [https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8](https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8)

    -   **Android:** [https://play.google.com/store/apps/details?id=com.skype.raider](https://play.google.com/store/apps/details?id=com.skype.raider)

    -   **Windows Phone 8 oder Windows Phone 8.1:** [http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51](http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51)

6.  Geben Sie auf der Seite **Softwarebeschreibung** die Informationen ein, die den Benutzern im Unternehmensportal zu der Software angezeigt werden sollen. Klicken Sie dann auf **Weiter**. Die folgenden Einstellungen stehen zur Verfügung (dieses Beispiel bezieht sich auf Skype):

    -   **Herausgeber:** Geben Sie den Namen des Herausgebers ein: „Microsoft“.

    -   **Name:** Geben Sie **Skype**

    -   **Beschreibung:** Geben Sie eine Beschreibung für die Software ein, z. B. **Skype-Kommunikations-App**

    -   **Kategorie:** Wählen Sie die Kategorie aus, die dieser Software am ehesten entspricht, z. B. **Zusammenarbeit**

    -   **Als ausgewählte App anzeigen und im Unternehmensportal hervorheben:** Wählen Sie diese Option aus, um die App im Unternehmensportal auf mobilen Geräten an hervorgehobener Stelle zu präsentieren.

    -   **Symbol**: Wählen Sie aus, ob der Software ein Symbol zugeordnet werden soll. Die maximale Größe für das optionale Symbol beträgt 250 x 250 Pixel, die empfohlene Größe beträgt 32 x 32 Pixel.

7.  Überprüfen Sie auf der Seite **Zusammenfassung** die Softwareinformationen, und klicken Sie dann auf **Hochladen**. Klicken Sie auf **Schließen**, um den Assistenten zu beenden.

8.  Klicken Sie in der [Intune-Verwaltungskonsole](https://manage.microsoft.com/) auf **Apps** > **Apps** > **Skype** > **Bereitstellung verwalten**.

9. Wählen Sie auf der Seite **Gruppen auswählen** die Option **Intune-Benutzer** aus, um die Software für diese Benutzergruppe bereitzustellen, und klicken Sie auf **Hinzufügen** > **Weiter**.

10. Wählen Sie auf der Seite **Bereitstellungsaktion** in der Spalte **Genehmigung** bei jeder Gruppe **Verfügbare Installation** aus.

11. Klicken Sie auf **Fertig stellen**.

Die Skype-App kann jetzt über das Unternehmensportal auf mobilen Geräten installiert werden, zunächst müssen Sie jedoch [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Software auf Computern und mobilen Geräten installieren.


### Nächste Schritte
Gratulation! Sie haben Schritt 6 der Kurzanleitung *Erste Schritte mit Intune* abgeschlossen.

>[!div class="step-by-step"]

>[&larr; **Organisieren von Benutzern und Geräten**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)[**Anpassen des Unternehmensportals** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-7.md)  



<!--HONumber=Aug16_HO5-->


