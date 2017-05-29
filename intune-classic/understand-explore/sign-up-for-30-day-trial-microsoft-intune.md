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
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 560765fa9d9afa4a1050515e1b2304c998f8c158
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---

# <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Registrieren für eine kostenlose Testversion von Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Dieser Artikel führt Sie durch die Registrierung für eine Testversion von Intune und zeigt, wie Sie diese vorbereiten, indem Sie einige Benutzer anlegen, damit Sie anschließend den Anleitungen im zugehörigen Evaluierungshandbuch folgen und verstehen können, wie mobile Geräte von Intune verwaltet werden. <!---or app data when devices are not enrolled in Intune.--->

>[!Note]
> Ab Dezember 2016 wird Microsoft Intune in das Azure-Portal verlagert. Einige kostenlose Testversion werden mit Intune in das Azure-Portal verschoben, einige verbleiben beim klassischen Intune. Wenn sich Ihre Testversion im Azure-Portal befindet, sehen Sie sich nach Abschluss der Schritte in diesem Artikel die wertvollen [Informationen zu Intune in Azure (Vorschau)](/intune/what-is--intune) an.

## <a name="assumptions"></a>Annahmen
In diesem Artikel über die Registrierung und im Evaluierungshandbuch wird davon ausgegangen, dass Sie die Testversion nur zu Evaluierungszwecken verwenden und beim Abschluss des Abonnements mit einer sauberen Umgebung starten möchten.

Um Ihnen den Einstieg in die Testversion zu erleichtern, richten wir eine sehr einfache Umgebung ein, in der nur Intune verwendet wird. Außerdem wird davon ausgegangen, dass Intune die einzige Methode zur Verwaltung von Geräten ist (auch als Autorität für die Verwaltung mobiler Geräte oder MDM-Autorität bezeichnet). Allerdings finden Sie im gesamten Handbuch Verweise auf weitergehende technische Inhalte, wenn Sie ein Thema genauer untersuchen möchten.

In der Testversion stehen alle Funktionen zur Verfügung, die Sie auch in einer Abonnementversion ausführen können. Der einzige Unterschied besteht darin, dass die Testversion auf 100 Benutzerkonten beschränkt ist.

## <a name="sign-up-for-your-trial"></a>Für die Testversion anmelden
Besuchen Sie die [Intune-Anmeldeseite](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20), und füllen Sie das Formular zur Anmeldung für ein Testabonnement aus.

Wenn Sie über Geschäfts-, Schul- oder Unikonto verfügen und dieses für Ihre Intune-Testversion verwenden möchten, folgen Sie stattdessen [diesen Anmeldeanweisungen](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-1). In diesem Artikel und den Evaluierungshandbüchern wird jedoch davon ausgegangen, dass Sie kein solches Konto verwenden.

> [!TIP]
> Wenn sich der Großteil Ihres IT-Betriebs und Ihrer Benutzer in einem anderen Gebietsschema als Sie befindet, sollten Sie zum Prüfen der Leistung ggf. dieses Gebietsschema für Ihre Testversion festlegen.

### <a name="post-sign-up-considerations"></a>Überlegungen nach der Registrierung
Wenn Sie sich für eine Testversion registrieren, wird eine E-Mail mit Ihren Kontoinformationen an die von Ihnen bei der Registrierung angegebene E-Mail-Adresse gesendet. Diese E-Mail bestätigt, dass Ihre Testversion aktiv ist.

Nach Abschluss des Registrierungsprozesses werden Sie an eine Seite weitergeleitet, auf der Sie über das Office 365 Admin Center Benutzer hinzufügen und ihnen Lizenzen zuweisen können. Wenn Sie sich das nächste Mal beim **klassischen Intune** (https://manage.microsoft.com) anmelden, werden Sie automatisch zur Intune-Administratorkonsole weitergeleitet.

Wenn sich Ihre Testversion im **Azure-Portal** befindet, wechseln Sie zu „https://portal.azure.com“, und melden Sie sich mit den Anmeldeinformationen für Ihre Intune-Testversion an.

## <a name="add-users"></a>Hinzufügen von Benutzern
Bevor Sie das Office 365 Admin Center verlassen und zu Intune wechseln, müssen Sie einige Benutzer zu Ihrem Testkonto hinzufügen.

Im Office 365 Admin Center können Sie Benutzer einzeln oder durch Hochladen einer CSV-Datei in größeren Mengen hinzufügen. Zum Einrichten Ihrer Testversion verwenden wir beide Optionen. In Ihrer Produktionsumgebung möchten Sie jedoch wahrscheinlich Ihre Azure Active Directory-Benutzerkonten nutzen. Mehr dazu finden Sie in unserem [Handbuch „Erste Schritte“](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) sowie in diesem Artikel im Abschnitt [Nächste Schritte](#Next-steps).

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

> [!NOTE]
> Die Benutzer werden in Intune erst angezeigt, wenn sie ein zu verwaltendes Gerät registriert haben.

Jetzt ist es Zeit, zu Intune zu wechseln, um mit dem Verwalten Ihrer Benutzer, Geräte und Apps zu beginnen.

## <a name="keeping-the-admin-experiences-straight"></a>Besserer Überblick für Administratoren
### <a name="classic-intune"></a>Klassisches Intune
Für das klassische Intune verwenden Sie zwei Portale:
- Das Office 365 Admin Center ([portal.office.com](https://portal.office.com))
- Die Intune-Verwaltungskonsole ([manage.microsoft.com](https://manage.microsoft.com))

Normalerweise führen Sie Ihre Arbeit, wie unten beschrieben, in der Intune-Verwaltungskonsole aus. Dies ist der Ort, an dem Sie Ihre Gruppen, Richtlinien, Geräte und Apps einrichten und verwalten.

![Abbildung der Intune-Verwaltungskonsole](./media/sign-up/intune-admin-console.png)

Zum Hinzufügen und Verwalten der Benutzer und anderer Aspekte Ihres Kontos, z. B. Abrechnung und Support, verwenden Sie jedoch, wie unten beschrieben, das Office 365 Admin Center.

![Abbildung des Office 365 Admin Center](./media/sign-up/office-admin-center.png)

Sie können aus Office dem 365 Admin Center zur Intune-Verwaltungskonsole navigieren. Die Admin Center befinden sich unter dem letzten Element im linken Navigationsbereich. Wählen Sie **Intune** aus, um die Intune-Verwaltungskonsole auf einer neuen Registerkarte zu öffnen.

![Abbildung des Links zur Intune-Verwaltungskonsole](./media/sign-up/link-to-intune.png)

Um von Intune zurück zum Office 365 Admin Center zu gelangen, wählen Sie auf der Seite „Gruppenübersicht“ die Aufgabe **Benutzer hinzufügen** aus.

![Abbildung des Links zum Office 365 Admin Center](./media/sign-up/task-add-users.png)

### <a name="intune-azure-preview"></a>Intune Azure-Vorschau
Für die Intune Azure-Vorschau verwenden Sie drei Portale:
- Das Office 365 Admin Center ([portal.office.com](https://portal.office.com))
- Das Intune-Dashboard in Azure ([portal.azure.com](https://portal.azure.com))
- Die klassische Intune-Verwaltungskonsole ([manage.microsoft.com](https://manage.microsoft.com))

Wenn Sie sich zum ersten Mal bei Intune in Azure anmelden, wird Intune möglicherweise auf dem Azure-Dashboard nicht angezeigt. So fügen Sie den Intune-Dienst zu Ihrem Azure-Dashboard hinzu:
1. Wählen Sie auf der linken Seite des Dashboards aus der Liste der Azure-Dienste die Option **Weitere Dienste >** aus, und geben Sie im Suchfeld den Begriff „Intune“ ein.
2. Wählen Sie **Intune** aus der Liste aus, und wählen Sie dann das Sternchen aus, um den Dienst zur Liste der Dienste hinzuzufügen.<br/> ![Abbildung der Auswahl von Intune aus der Liste der Dienste](./media/sign-up/azure-add-intune1.png)
3. Wählen Sie **Intune** aus der Liste der Dienste aus, um das Intune-Dashboard zu öffnen.

Normalerweise werden Sie auf dem unten gezeigten Intune-Dashboard arbeiten. Dies ist der Ort, an dem Sie Ihre Gruppen, Richtlinien, Geräte und Apps einrichten und verwalten. Sie können vom Dashboard zur klassischen Intune-Verwaltungskonsole wechseln, indem Sie die Kachel **Klassisches Intune-Portal öffnen** auswählen. Um zur Intune Azure-Vorschau zurückzukehren, geben Sie „https://portal.azure.com“ in die Adressleiste Ihres Browsers ein, und wählen Sie aus der Liste der Dienste erneut **Intune** aus.

 ![Abbildung des Intune-Dashboards](./media/sign-up/intune-azure-dashboard.png)


Zum Hinzufügen und Verwalten der Benutzer und anderer Aspekte Ihres Kontos, z. B. Abrechnung und Support, verwenden Sie jedoch, wie unten beschrieben, das Office 365 Admin Center.

![Abbildung des Office 365 Admin Center](./media/sign-up/office-admin-center.png)

Um vom Office 365 Admin Center zum Intune-Dashboard zu wechseln, geben Sie „https://portal.azure.com“ in die Adressleiste Ihres Browsers ein. Wählen Sie **Intune** aus der Liste der Dienste aus.

Um von Intune zurück zum Office 365 Admin Center zu wechseln, geben Sie „https://portal.office.com“ in die Adressleiste Ihres Browsers ein. Wenn Sie bereits bei Intune angemeldet sind, werden Sie direkt zum Office 365 Admin Center weitergeleitet.

## <a name="next-steps"></a>Nächste Schritte
### <a name="classic-intune"></a>Klassisches Intune
Evaluierungsszenario: [Evaluieren der Verwaltung mobiler Geräte (MDM) in Microsoft Intune](mobile-device-management-trial-guide-microsoft-intune.md)

### <a name="intune-azure-preview"></a>Intune Azure-Vorschau
Weitere Informationen zu [Intune in der Vorschau des Azure-Portals](/intune/what-is-intune)

### <a name="integration-with-other-products"></a>Integration mit anderen Produkten
Erfahren Sie mehr über die Verwendung Ihrer Azure Active Directory-Benutzerkonten mit Intune:
- [Identitätsanforderungen](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)
- [Anforderungen für die Verzeichnissynchronisierung](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)
- [Anforderungen für mehrstufige Authentifizierung](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

Erfahren Sie mehr über die Verwendung von [Intune mit System Center Configuration Manager](https://docs.microsoft.com/sccm/mdm/understand/hybrid-mobile-device-management).

