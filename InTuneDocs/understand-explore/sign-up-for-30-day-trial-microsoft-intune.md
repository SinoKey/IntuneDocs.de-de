---
title: "Registrieren für eine 30-tägige kostenlose Testversion von Microsoft Intune | Microsoft-Dokumentation"
description: "Registrieren Sie sich für eine kostenlose 30-tägige Evaluierung von Microsoft Intune, und konfigurieren Sie diese."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 619a1d11-3d22-4635-8f70-770eba3e1712
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: a65ead23e62870647245120d1663706fc46810ac


---

# <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Registrieren für eine kostenlose Testversion von Microsoft Intune
Dieser Artikel führt Sie durch die Registrierung für eine Testversion von Intune und zeigt, wie Sie diese vorbereiten, indem Sie einige Benutzer anlegen, damit Sie anschließend den Anleitungen im zugehörigen Evaluierungshandbuch folgen und verstehen können, wie mobile Geräte von Intune verwaltet werden. <!---or app data when devices are not enrolled in Intune.--->

## <a name="assumptions"></a>Annahmen
In diesem Artikel über die Registrierung und im Evaluierungshandbuch wird davon ausgegangen, dass Sie die Testversion nur zu Evaluierungszwecken verwenden und beim Abschluss des Abonnements mit einer sauberen Umgebung starten möchten.

Um Ihnen den Einstieg in die Testversion zu erleichtern, richten wir eine sehr einfache Umgebung ein, in der nur Intune verwendet wird. Außerdem wird davon ausgegangen, dass Intune die einzige Methode zur Verwaltung von Geräten ist (auch als Autorität für die Verwaltung mobiler Geräte oder MDM-Autorität bezeichnet). Allerdings finden Sie im gesamten Handbuch Verweise auf weitergehende technische Inhalte, wenn Sie ein Thema genauer untersuchen möchten.

In der Testversion stehen alle Funktionen zur Verfügung, die Sie auch in einer Abonnementversion ausführen können. Der einzige Unterschied besteht darin, dass die Testversion auf 100 Benutzerkonten beschränkt ist.

## <a name="sign-up-for-your-trial"></a>Für die Testversion anmelden
Besuchen Sie die [Intune-Anmeldeseite](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20), und füllen Sie das Formular zur Anmeldung für ein Testabonnement aus.

Wenn Sie über Geschäfts-, Schul- oder Unikonto verfügen und dieses für Ihre Intune-Testversion verwenden möchten, folgen Sie stattdessen [diesen Anmeldeanweisungen](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-1). In diesem Artikel und den Evaluierungshandbüchern wird jedoch davon ausgegangen, dass Sie kein solches Konto verwenden.

> [!TIP]
> Wenn sich der Großteil Ihres IT-Betriebs und Ihrer Benutzer in einem anderen Gebietsschema als Sie befindet, sollten Sie zum Prüfen der Leistung ggf. dieses Gebietsschema für Ihre Testversion festlegen.

### <a name="post-sign-up-considerations"></a>Überlegungen nach der Registrierung
Wenn Sie sich für eine Testversion registrieren, wird eine E-Mail mit Ihren Kontoinformationen an die von Ihnen bei der Registrierung angegebene E-Mail-Adresse gesendet. Diese E-Mail bestätigt, dass Ihre Testversion aktiv ist.

Nach Abschluss des Registrierungsprozesses werden Sie an eine Seite weitergeleitet, auf der Sie über das Office 365 Admin Center Benutzer hinzufügen und ihnen Lizenzen zuweisen können. Wenn Sie sich das nächste Mal bei Intune anmelden, werden Sie automatisch zur Intune-Administratorkonsole weitergeleitet.

## <a name="keeping-the-admin-center-and-the-intune-administration-console-straight"></a>Auseinanderhalten von Admin Center und Intune-Verwaltungskonsole
Es gibt zwei Portale, die Sie für Intune verwenden: das Office 365 Admin Center ([portal.office.com](https://portal.office.com)) und die Intune-Verwaltungskonsole ([manage.microsoft.com](https://manage.microsoft.com)).

Normalerweise führen Sie Ihre Arbeit, wie unten beschrieben, in der Intune-Verwaltungskonsole aus. Dies ist der Ort, an dem Sie Ihre Gruppen, Richtlinien, Geräte und Apps einrichten und verwalten.

![Abbildung der Intune-Verwaltungskonsole](./media/sign-up/intune-admin-console.png)

Zum Hinzufügen und Verwalten der Benutzer und anderer Aspekte Ihres Kontos, z. B. Abrechnung und Support, verwenden Sie jedoch, wie unten beschrieben, das Office 365 Admin Center.

![Abbildung des Office 365 Admin Center](./media/sign-up/office-admin-center.png)

Sie können aus Office dem 365 Admin Center zur Intune-Verwaltungskonsole navigieren. Die Admin Center befinden sich unter dem letzten Element im linken Navigationsbereich. Wählen Sie **Intune** aus, um die Intune-Verwaltungskonsole auf einer neuen Registerkarte zu öffnen.

![Abbildung des Links zur Intune-Verwaltungskonsole](./media/sign-up/link-to-intune.png)

Um von Intune zurück zum Office 365 Admin Center zu gelangen, wählen Sie auf der Seite „Gruppenübersicht“ die Aufgabe **Benutzer hinzufügen** aus.

![Abbildung des Links zum Office 365 Admin Center](./media/sign-up/task-add-users.png)

## <a name="add-users"></a>Hinzufügen von Benutzern
Bevor Sie das Office 365 Admin Center verlassen und zu Intune wechseln, müssen Sie einige Benutzer zu Ihrem Testkonto hinzufügen.

Im Office 365 Admin Center können Sie Benutzer einzeln oder durch Hochladen einer CSV-Datei in größeren Mengen hinzufügen. Zum Einrichten Ihrer Testversion verwenden wir beide Optionen. In Ihrer Produktionsumgebung möchten Sie jedoch wahrscheinlich Ihre Azure Active Directory-Benutzerkonten nutzen. Mehr dazu finden Sie in unserem [Handbuch „Erste Schritte“](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) sowie in diesem Artikel im Abschnitt [Nächste Schritte](#Next-steps).

### <a name="add-an-individual-user"></a>Hinzufügen eines einzelnen Benutzers
1. Wählen Sie eine der Optionen zum Hinzufügen eines Benutzers, um ein Formular zu öffnen, in dem Sie den Benutzer erstellen können. Nur die mit einem Sternchen markierten Elemente (\*) sind erforderlich.
![Abbildung der Optionen der Schaltfläche „ Benutzer hinzufügen“](./media/sign-up/add-user.png)


2.  Als letzter Schritt beim Hinzufügen eines Benutzers wird dem Benutzer eine E-Mail mit einem temporären Intune-Kennwort gesendet. Verwenden Sie zum Zwecke dieser Evaluierung Ihre eigene geschäftliche E-Mail-Adresse, damit Sie die Anmeldeinformationen und die E-Mail erhalten, die an Ihre Benutzer gesendet werden. Anschließend können Sie mit diesen Benutzeridentitäten Testgeräte registrieren.<br/>

 ![Abbildung des letzten Schritts zum Hinzufügen eines Benutzers](./media/sign-up/new-user-2.png)

3. Wenn Sie einem Benutzer nach der Erstellung eine Administratorrolle zuweisen möchten, können Sie seine Rolle im Office 365 Admin Center bearbeiten. Wählen Sie dazu den Benutzernamen aus der Liste der Benutzer aus, und wählen Sie dann in der Zeile „Rolle“ die Option **Bearbeiten** aus, um die Liste der verfügbaren Benutzerrollen anzuzeigen, die Sie dem Benutzer zuweisen können.

 ![Abbildung von Benutzerrollenoptionen](./media/sign-up/change-user-role.png)

### <a name="import-multiple-users"></a>Importieren mehrerer Benutzer
1. Den Assistenten zum Importieren mehrerer Benutzer finden Sie in der Liste **Mehr**.

 ![Abbildung der Option zum Hinzufügen mehrerer Benutzer](./media/sign-up/add-multiple-users.png)

2. Als Hilfestellung zum korrekten Einrichten der CSV-Datei können Sie eine Vorlagendatei herunterladen und mit Ihren Benutzerdaten füllen. Laden Sie die CSV-Datei herunter. Diese enthält Header und Beispielbenutzerdaten, um zu verdeutlichen, welche Art von Daten für jedes Feld erforderlich ist.

 ![Abbildung des ersten Schritts im Massenregistrierungs-Assistenten](./media/sign-up/bulk-enroll-step-1.png)


3. Nachdem Sie die CSV-Datei erstellt und gespeichert haben, klicken Sie auf **Durchsuchen**, um die Datei auszuwählen. Überprüfen Sie die Auswahl, und klicken Sie auf **Weiter**. Die Benutzer werden hochgeladen und zu Ihrer Liste der aktiven Benutzer hinzugefügt.

Jetzt ist es Zeit, zur Intune-Verwaltungskonsole zu wechseln, um mit dem Verwalten Ihrer Benutzer, Geräte und Apps zu beginnen.

> [!NOTE]
> Die Benutzer werden in Intune erst angezeigt, wenn sie ein zu verwaltendes Gerät registriert haben.

## <a name="next-steps"></a>Nächste Schritte
Evaluierungsszenario: [Evaluieren der Verwaltung mobiler Geräte (MDM) in Microsoft Intune](mobile-device-management-trial-guide-microsoft-intune.md)

Erfahren Sie mehr über die Verwendung Ihrer Azure Active Directory-Benutzerkonten mit Intune:
- [Identitätsanforderungen](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)
- [Anforderungen für die Verzeichnissynchronisierung](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)
- [Anforderungen für mehrstufige Authentifizierung](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

Erfahren Sie mehr über die Verwendung von [Intune mit System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/mdm/understand/hybrid-mobile-device-management).



<!--HONumber=Dec16_HO2-->


