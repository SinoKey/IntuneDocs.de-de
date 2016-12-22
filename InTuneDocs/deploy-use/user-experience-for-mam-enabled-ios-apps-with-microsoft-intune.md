---
title: iOS-Apps mit MAM-Richtlinien | Microsoft Intune
description: "In diesem Thema wird beschrieben, was Sie erwartet, wenn Ihre iOS-App von Verwaltungsrichtlinien für mobile Apps verwaltet wird."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 3aa6728036ff66ea489176063af2d136bef4c7cc


---

# <a name="what-to-expect-when-your-ios-app-is-managed-by-mam-policies"></a>Was Sie erwartet, wenn Ihre iOS-App von MAM-Richtlinien verwaltet wird
 Dieses Thema beschreibt die Benutzerumgebung für Apps mit MAM-Richtlinien (Mobile Application Management, Verwaltung mobiler Anwendungen). MAM-Richtlinien gelten nur, wenn Apps im geschäftlichen Kontext verwendet werden, z. B. wenn der Benutzer ein Geschäftskonto für den Zugriff auf Apps verwendet oder auf Dateien zugreift, die an einem OneDrive for Business-Speicherort im Unternehmen gespeichert sind.

##  <a name="access-apps"></a>Zugriff auf Apps

Wenn das Gerät **nicht bei Intune registriert** ist, wird der Benutzer beim ersten Verwenden der App aufgefordert, die App neu zu starten.  Ein Neustart ist erforderlich, damit MAM-Richtlinien auf die App angewendet werden können. Der folgende Screenshot aus der Skype-App stellt diese Neustartanforderung dar:


![Screenshot des iOS-Geräts mit der PIN-Eingabeaufforderung](../media/appmanagement/iOS_AppPINPrompt.png)

Bei Geräten, die **für die Verwaltung in Intune registriert** sind, wird dem Benutzer eine Meldung angezeigt, dass seine App nun verwaltet wird:

![Screenshot des iOS-Geräts mit der Meldung, dass seine App nun durch das Unternehmen verwaltet wird, und der PIN-Eingabeaufforderung](../media/appmanagement/ios-managed-devices-pin-prompt.png)

##  <a name="use-apps-with-multi-identity-support"></a>Verwenden von Apps mit Unterstützung von mehreren Identitäten

MAM-Richtlinien werden nur im geschäftlichen Kontext angewendet. Eine App kann sich daher unterschiedlich verhalten, je nachdem, ob sie im geschäftlichen oder privaten Kontext verwendet wird.

 Beispielsweise erhalten Benutzer eine PIN-Eingabeaufforderung, wenn Sie auf Geschäftsdaten zugreifen. Bei der **Outlook-App** wird der Benutzer beim Starten der App zur Eingabe einer PIN aufgefordert. Bei der **OneDrive-App** wird der Benutzer zur Eingabe einer PIN aufgefordert, wenn er das Geschäftskonto eingibt.  Bei Microsoft **Word**, **PowerPoint** und **Excel** wird der Benutzer zur Eingabe einer PIN aufgefordert, wenn er auf Dokumente zugreift, die am OneDrive for Business-Speicherort des Unternehmens gespeichert sind.

##  <a name="manage-user-accounts-on-the-device"></a>Verwalten von Benutzerkonten auf dem Gerät

Intune unterstützt die Bereitstellung von MAM-Richtlinien nur auf je einem Benutzerkonto pro Gerät.

* Abhängig von der verwendeten App, ist der zweite Benutzer auf dem Gerät möglicherweise blockiert. Unter allen Umständen wirken sich die MAM-Richtlinien nur auf den ersten Benutzer aus.
  * **Microsoft Word**, **Excel** und **PowerPoint** blockieren ein zweites Benutzerkonto nicht, die MAM-Richtlinien wirken sich auf das zweite Benutzerkonto aber nicht aus.  

  * Für **OneDrive**- und **Outlook-Apps** können Sie nur ein geschäftliches Konto verwenden. Sie können für diese Apps nicht mehrere Geschäftskonten hinzufügen. Sie können jedoch einen Benutzer entfernen und auf dem Gerät einen weiteren Benutzer hinzufügen.

* Wenn für ein Gerät vor der Bereitstellung der MAM-Richtlinien mehrere Benutzerkonten vorhanden sind, wird das Konto, für das die MAM-Richtlinien zuerst bereitgestellt werden, durch die Intune MAM-Richtlinien verwaltet.


Lesen Sie das folgende Beispielszenario, um genauer zu verstehen, wie mehrere Benutzerkonten behandelt werden.

Benutzer A arbeitet für zwei Unternehmen – **Unternehmen X** und **Unternehmen Y**. Der Benutzer A verfügt für jedes Unternehmen über ein geschäftliches Konto, und beide verwenden Intune zum Bereitstellen von MAM-Richtlinien. **Unternehmen X** stellt MAM-Richtlinien **vor** **Unternehmen Y** bereit. Das **Unternehmen X** zugeordnete Konto erhält die MAM-Richtlinie, nicht jedoch das dem Unternehmen Y zugeordnete Konto. Wenn das Unternehmen Y zugeordnete Konto durch die MAM-Richtlinien verwaltet werden soll, müssen Sie das Unternehmen X zugeordnete Benutzerkonto entfernen.

### <a name="add-a-second-account"></a>Hinzufügen eines zweiten Kontos

Wenn Sie ein iOS-Gerät verwenden und versuchen, auf diesem Gerät ein zweites Geschäftskonto einzurichten, wird möglicherweise eine Sperrnachricht angezeigt. Die Konten werden angezeigt, und Sie können das Konto auswählen, das Sie entfernen möchten.

![Screenshot des Dialogfelds mit der Sperrnachricht und den Optionen „Ja“ und „Nein“](../media/AppManagement/iOS_SwitchUser.PNG)
## <a name="next-steps"></a>Nächste Schritte
[Was Sie erwartet, wenn Ihre Android-App von MAM-Richtlinien verwaltet wird](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
### <a name="see-also"></a>Weitere Informationen:
[Erstellen und Bereitstellen von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


