---
title: "Registrieren Sie sich für eine 30-tägige kostenlose Testversion"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie sich für Intune in Azure registrieren."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 01/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 195931c0-8208-43bd-b0af-b1f8e469a32c
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 3be43e12abc1cf90da3584450ddd56ab63bdfac1
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---

# <a name="sign-up-for-a-microsoft-intune-free-trial-for-the-azure-portal-preview"></a>Registrieren für eine kostenlose Testversion von Microsoft Intune für die Vorschau des Azure-Portals

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Dieser Artikel führt Sie durch die Registrierung für eine Testversion von Intune Standalone für die Vorschau des Azure-Portals. <!---and prepares your trial with some users so that you can then follow the associated evaluation guide to see how Intune manages mobile devices. ---> <!---or app data when devices are not enrolled in Intune.--->

<!--- ## Assumptions
This sign-up article and the evaluation guide assume you are using the trial for evaluation purposes only and intend to start with a clean environment when you subscribe.

To make it easy for you to get started with the trial, we are setting up a very simple environment that uses only Intune and assumes it will be your sole method of managing devices (known as the mobile device management authority). However, throughout the guide we will point you to deeper technical content if you want to explore farther.

You can do everything in the trial version that you can do in a subscription version; the only difference is you are limited to 100 user accounts in the trial.--->

<!--- ## Sign up for your trial--->
1. Besuchen Sie die [Intune-Anmeldeseite](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20), und füllen Sie das Formular zur Anmeldung für ein Testabonnement aus.

 <!--- If you have a work or school account and want to use that for your Intune trial, follow [these sign-in instructions](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-1) instead. However, this article assumes that you are not using such an account.---><br/> ![Abbildung der Registrierungsseite](./media/1-clicking-try.png)

 > [!TIP]
> Wenn sich der Großteil Ihres IT-Betriebs und Ihrer Benutzer in einem anderen Gebietsschema als Sie befindet, sollten Sie dieses Gebietsschema unter **Where's your company located?** (Unternehmensstandort) festlegen.

2. Am Ende des Registrierungsvorgangs erhalten Sie eine Nachricht mit Informationen zum neuen Konto. <br/> ![Abbildung der Kontoinformationen](./media/2-end-of-sign-up-process.png) <br/>Wenn Sie hier auf **Jetzt kann es losgehen!** klicken, gelangen Sie zum Office 365 Admin Center, wo Sie Ihrer Testumgebung Benutzer hinzufügen können. <br/><br/>Wenn Sie jedoch direkt zur Vorschau von Intune im Azure-Portal wechseln möchten, öffnen Sie ein neues Browserfenster, und geben Sie in der Adressleiste **https://portal.azure.com** ein. Sie werden zur Azure-Anmeldeseite weitergeleitet, auf der Sie die erhaltenen Anmeldeinformationen verwenden können. Verwenden Sie diese Adresse, wenn Sie sich bei Ihrer Intune-Testversion anmelden möchten. <br/> ![Abbildung der Anmeldeseite des Azure-Portals](./media/azure-portal-signin.png)

Wenn Sie sich zum ersten Mal bei der Vorschau von Intune in Azure anmelden, wird Intune möglicherweise auf dem Azure-Dashboard nicht angezeigt. So fügen Sie den Intune-Dienst zu Ihrem Azure-Dashboard hinzu:
1. Wählen Sie auf der linken Seite des Dashboards in der Liste der Azure-Dienste die Option **Weitere Dienste >** aus, und geben Sie im Suchfeld den Begriff **Intune** ein.
2. Wählen Sie **Intune** aus der Liste aus, und wählen Sie dann das Sternchen aus, um den Dienst zur Liste der Dienste hinzuzufügen.<br/> ![Abbildung der Auswahl von Intune aus der Liste der Dienste](./media/azure-add-intune1.png)
3. Wählen Sie dann **Intune** in der Liste der Dienste aus, um das Intune-Dashboard zu öffnen.

Wenn Sie sich für eine Testversion registrieren, wird eine E-Mail mit Ihren Kontoinformationen an die von Ihnen bei der Registrierung angegebene E-Mail-Adresse gesendet. Diese E-Mail bestätigt, dass Ihre Testversion aktiv ist.


<!--- ## Add users
Before you leave the Office 365 Admin center for Intune, you need to add some users to your trial account.

In the Office 365 Admin center, you can add users individually or in bulk by uploading a .csv file. We will do both to set up your trial. However, in your production environment, you will probably want to take advantage of your Azure Active Directory user accounts, which you can learn more about in our [Getting Started guide](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) and in the [Next steps](#Next-steps) section of this article.

### Add an individual user
1. Choose either of the options to add a use to open a form that allows you to create a user. Only the items starred with an asterisk (\*) are required.
![Image of add user button options](./media/sign-up/add-user.png)


2.  When you add the user, the final step will be to send the user an email with their temporary Intune password. For the purposes of this evaluation, use your own work email address so you will receive the log-on information and see the email your users will get. You can then use these user identities to enroll test devices.<br/>

 ![Image of add user final step](./media/sign-up/new-user-2.png)

3. If you want to assign a user an admin role after you create it, you can edit the role in the Office 365 Admin center by selecting the user name from your list of users, and then choosing **Edit** in the Role line to see the list of user roles you can select from and assign to that user.

 ![Image of user  role options](./media/sign-up/change-user-role.png)

### Import multiple users
1. You will find the wizard for importing multiple users in the **More** list.

 ![Image of option to add multiple users](./media/sign-up/add-multiple-users.png)

2. To help you set up your .csv file correctly, you can download a template file to populate with your user data. Download the .csv file that contains headers and sample user information to see exactly the kind of data is needed for each field.

 ![Image of first step in bulk enrollment wizard](./media/sign-up/bulk-enroll-step-1.png)


3. After you’ve created and saved your .csv file, choose **Browse** to select the file. Verify, and choose **Next**. Your users will be uploaded and added to your list of active users.

> [!NOTE]
> Your users won't show up in Intune until they've enrolled a device to be managed.

Now it’s time to head over to Intune to start managing your users, their devices, and their apps.--->

## <a name="keeping-the-admin-experiences-straight"></a>Besserer Überblick für Administratoren
<!---### Classic Intune
There are two portals you will use for classic Intune:
- The Office 365 Admin center ([portal.office.com](https://portal.office.com))
- The Intune administration console ([manage.microsoft.com](https://manage.microsoft.com))

Normally, you’ll do your work in the Intune administration console, shown below. This is the site where you set up and manage your groups, policies, devices, and apps.

![Image of Intune administration console](./media/sign-up/intune-admin-console.png)

However, you will use the Office 365 Admin center, shown below, to add and manage your users and other aspects of your account, including billing and support.

![Image of Office 365 Admin center](./media/sign-up/office-admin-center.png)

You can navigate from the Office 365 Admin center to the Intune admin console. The admin centers are under the last item in the left navigation pane. Choose **Intune** to open the Intune admin console in a new tab.

![Image of link to Intune administration console](./media/sign-up/link-to-intune.png)

To get from Intune back to the Office 365 Admin center, choose the **Add Users** task on the Groups Overview page.

![Image of link back to Office 365  Admin center](./media/sign-up/task-add-users.png)--->

<!---### Intune Azure preview--->
Für die Intune Azure-Vorschau verwenden Sie drei Portale:
- Das Intune-Dashboard in Azure ([portal.azure.com](https://portal.azure.com)), auf dem Sie die [Funktionen von Intune im Azure-Portal](what-is-intune.md) erkunden können.
- Das Office 365 Admin Center ([portal.office.com](https://portal.office.com)), in dem Sie Benutzer hinzufügen und verwalten können, wenn Sie dazu nicht Azure Active Directory verwenden. Sie können auch andere Aspekte Ihres Kontos verwalten, einschließlich Abrechnung und Support.
- Die klassische Intune-Verwaltungskonsole ([manage.microsoft.com](https://manage.microsoft.com)), in der Sie Features, die in Azure noch nicht hinzugefügt wurden, erkunden können.

Normalerweise werden Sie auf dem unten gezeigten Intune-Dashboard arbeiten. Dies ist der Ort, an dem Sie Ihre Gruppen, Richtlinien, Geräte und Apps einrichten und verwalten.

Sie können vom Dashboard zur klassischen Intune-Verwaltungskonsole wechseln, indem Sie die Kachel **Klassisches Intune-Portal öffnen** auswählen.

Um zur Intune Azure-Vorschau zurückzukehren, geben Sie „https://portal.azure.com“ in die Adressleiste Ihres Browsers ein, und wählen Sie aus der Liste der Dienste erneut **Intune** aus.

 ![Abbildung des Intune-Dashboards](./media/intune-azure-dashboard.png)


Zum Hinzufügen und Verwalten der Benutzer und anderer Aspekte Ihres Kontos, z. B. Abrechnung und Support, verwenden Sie jedoch, wie unten beschrieben, das Office 365 Admin Center.

![Abbildung des Office 365 Admin Center](./media/office-admin-center.png)

Um vom Office 365 Admin Center zum Intune-Dashboard zu wechseln, geben Sie „https://portal.azure.com“ in die Adressleiste Ihres Browsers ein. Wählen Sie **Intune** aus der Liste der Dienste aus.

Um von Intune zurück zum Office 365 Admin Center zu wechseln, geben Sie „https://portal.office.com“ in die Adressleiste Ihres Browsers ein. Wenn Sie bereits bei Intune angemeldet sind, werden Sie direkt zum Office 365 Admin Center weitergeleitet.

## <a name="next-steps"></a>Nächste Schritte

### <a name="intune-azure-preview"></a>Intune Azure-Vorschau
Weitere Informationen zu [Intune in der Vorschau des Azure-Portals](what-is-intune.md)
### <a name="classic-intune"></a>Klassisches Intune
Evaluierungsszenario: [Evaluieren der Verwaltung mobiler Geräte (MDM) in Microsoft Intune](https://docs.microsoft.com/intune-classic/understand-explore/mobile-device-management-trial-guide-microsoft-intune)

### <a name="integration-with-other-products"></a>Integration mit anderen Produkten
Erfahren Sie mehr über die Verwendung Ihrer Azure Active Directory-Benutzerkonten mit Intune:
- [Identitätsanforderungen](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)
- [Anforderungen für die Verzeichnissynchronisierung](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)
- [Anforderungen für mehrstufige Authentifizierung](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

Erfahren Sie mehr über die Verwendung von [Intune mit System Center Configuration Manager](https://docs.microsoft.com/sccm/mdm/understand/hybrid-mobile-device-management).

