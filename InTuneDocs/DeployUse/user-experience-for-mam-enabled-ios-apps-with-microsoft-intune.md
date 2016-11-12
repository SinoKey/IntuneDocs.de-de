---
title: iOS-Apps mit MAM-Richtlinien | Microsoft Intune
description: "In diesem Thema wird beschrieben, was Sie erwartet, wenn Ihre iOS-App von Verwaltungsrichtlinien für mobile Apps verwaltet wird."
keywords: 
author: karthikaraman
ms.author: karaman
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
ms.sourcegitcommit: 389daf0ed39fa2cd4b2e5d6e52cbd6809a568c9e
ms.openlocfilehash: 3f9d9c7cafcdac0db21e5ba35f713fe630c65b99


---

# Was Sie erwartet, wenn Ihre iOS-App von MAM-Richtlinien verwaltet wird
 Dieses Thema beschreibt die Benutzererfahrung für Apps mit MAM-Richtlinien. MAM-Richtlinien (mobile application management, Verwaltung mobiler Anwendungen) gelten nur, wenn Apps im geschäftlichen Kontext verwendet werden, z.B. wenn Sie Ihr Geschäftskonto für den Zugriff auf Apps verwenden oder auf Dateien zugreifen, die am OneDrive for Business-Speicherort Ihres Unternehmens gespeichert sind.
##  Zugreifen auf Apps

Wenn das Gerät **nicht bei Intune registriert** ist, wird der Endbenutzer beim ersten Verwenden der App dazu aufgefordert, die App neu zu starten.  Ein Neustart ist erforderlich, damit MAM-Richtlinien auf die App angewendet werden können. Der folgende Screenshot stellt dies mithilfe der Skype-App dar:


![Screenshot des iOS-Geräts mit der PIN-Eingabeaufforderung](../media/appmanagement/iOS_AppPINPrompt.png)

Bei Geräten, die **für die Verwaltung in Intune registriert** sind, wird dem Endbenutzer eine Meldung angezeigt, dass seine App nun verwaltet wird:

![Screenshot des iOS-Geräts mit der Meldung zur Verwaltung durch das Unternehmen und der Eingabeaufforderung](../media/appmanagement/ios-managed-devices-pin-prompt.png)

##  Verwenden von Apps mit Multi-Identity Support (Unterstützung für mehrere Identitäten)

MAM-Richtlinien gelten nur, wenn die App im geschäftlichen Kontext verwendet wird, weshalb Sie abhängig vom Kontext (geschäftlich oder privat) unterschiedliche App-Verhalten feststellen könnten.  

Bei Apps, die mehrere Identitäten unterstützen, wendet Intune die MAM-Richtlinien nur an, wenn der Endbenutzer die App im geschäftlichen Kontext verwendet.  Beispielsweise erhalten Endbenutzer eine PIN-Eingabeaufforderung, wenn Sie auf Geschäftsdaten zugreifen.  Bei der **Outlook-App** wird der Endbenutzer beim Starten der App zur Eingabe einer PIN aufgefordert. Bei der **OneDrive-App** erfolgt diese Aufforderung, wenn der Endbenutzer das Geschäftskonto eingibt.  Bei Microsoft **Word**, **PowerPoint* und **Excel** erfolgt diese Aufforderung, wenn der Endbenutzer auf Dokumente zugreift, die am OneDrive for Business-Speicherort des Unternehmens gespeichert sind.
##  Verwalten von Benutzerkonten auf dem Gerät

Intune unterstützt nur die Bereitstellung von MAM-Richtlinien auf je einem Benutzerkonto pro Gerät.

* Abhängig von der verwendeten App, ist der zweite Benutzer auf dem Gerät möglicherweise blockiert oder auch nicht. Unter allen Umständen wirken sich die MAM-Richtlinien nur auf den ersten Benutzer aus.
  * **Microsoft Word**, **Excel** und **PowerPoint** blockieren ein zweites Benutzerkonto nicht, die MAM-Richtlinien wirken sich auf das zweite Benutzerkonto aber nicht aus.  

  * Für **OneDrive- und Outlook-Apps** kann nur ein geschäftliches Konto verwendet werden.  Das Hinzufügen weiterer Geschäftskonten wird von diesen Apps blockiert.  Sie können jedoch einen Benutzer entfernen und auf dem Gerät einen weiteren Benutzer hinzufügen.

* Wenn für ein Gerät vor der Bereitstellung der MAM-Richtlinien mehrere Benutzerkonten vorhanden sind, wird das Konto, für das die MAM-Richtlinien zuerst bereitgestellt werden, durch die Intune MAM-Richtlinien verwaltet.


Lesen Sie das Beispielszenario unten, um genauer zu verstehen, wie mehrere Benutzerkonten behandelt werden.

Benutzer A arbeitet für zwei Unternehmen – **Unternehmen X** und **Unternehmen Y**. Der Benutzer A verfügt für jedes Unternehmen über ein geschäftliches Konto, und beide verwenden Intune zum Bereitstellen von MAM-Richtlinien. **Unternehmen X** stellt MAM-Richtlinien **vor** **Unternehmen Y** bereit. Das **Unternehmen X** zugeordnete Konto erhält die MAM-Richtlinie, nicht jedoch das dem Unternehmen Y zugeordnete Konto. Wenn das Unternehmen Y zugeordnete Konto durch die MAM-Richtlinien verwaltet werden soll, müssen Sie das Unternehmen X zugeordnete Benutzerkonto entfernen.
### Hinzufügen eines zweiten Kontos

Wenn Sie ein iOS-Gerät verwenden und versuchen, auf demselben Gerät ein zweites Geschäftskonto einzurichten, wird möglicherweise eine Sperrnachricht angezeigt.  Die Konten werden angezeigt, und Sie können das Konto auswählen, das Sie entfernen möchten.

![Screenshot des Dialogfelds mit der Sperrnachricht und den Optionen „Ja“ und „Nein“](../media/AppManagement/iOS_SwitchUser.PNG)
## Nächste Schritte
[Was Sie erwartet, wenn Ihre Android-App von MAM-Richtlinien verwaltet wird](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
### Weitere Informationen:
[Erstellen und Bereitstellen von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


