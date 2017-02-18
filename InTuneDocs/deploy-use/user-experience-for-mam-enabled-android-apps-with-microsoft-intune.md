---
title: Android-Apps mit MAM-Richtlinien | Microsoft-Dokumentation
description: "In diesem Thema wird beschrieben, was Sie erwartet, wenn Ihre App von Verwaltungsrichtlinien für mobile Apps verwaltet wird."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: aeacfddb3ed42938dd9443e2734222c977436430


---

# <a name="what-to-expect-when-your-android-app-is-managed-by-mam-policies"></a>Was Sie erwartet, wenn Ihre Android-App von MAM-Richtlinien verwaltet wird

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Dieses Thema beschreibt die Benutzerumgebung für Apps mit MAM-Richtlinien (Mobile Application Management, Verwaltung mobiler Anwendungen). MAM-Richtlinien gelten nur, wenn Apps in einem geschäftlichen Kontext verwendet werden, z. B. wenn der Benutzer ein Geschäftskonto für den Zugriff auf Apps verwendet oder auf Dateien zugreift, die an einem OneDrive for Business-Speicherort im Unternehmen gespeichert sind.
##  <a name="access-apps"></a>Zugriff auf Apps

Die Unternehmensportal-App ist auf Android-Geräten für alle Apps erforderlich, die MAM-Richtlinien zugeordnet sind.

Bei Geräten, die nicht bei Intune registriert sind, muss die Unternehmensportal-App auf dem Gerät installiert sein. Jedoch muss der Benutzer die Unternehmensportal-App nicht starten bzw. sich darin anmelden, bevor er Apps verwenden kann, die von MAM-Richtlinien verwaltet werden.

Die Unternehmensportal-App ist in Intune eine Möglichkeit der Freigabe von Daten an einem sicheren Ort. Daher ist die Unternehmensportal-App eine Voraussetzung für alle Apps, denen MAM-Richtlinien zugeordnet sind, auch wenn das Gerät nicht in Intune registriert ist.


##  <a name="use-apps-with-multi-identity-support"></a>Verwenden von Apps mit Unterstützung von mehreren Identitäten

MAM-Richtlinien werden nur im geschäftlichen Kontext angewendet. Eine App kann sich daher unterschiedlich verhalten, je nachdem, ob sie im geschäftlichen oder privaten Kontext verwendet wird.

Beispielsweise erhalten Benutzer eine PIN-Eingabeaufforderung, wenn Sie auf Geschäftsdaten zugreifen. Bei der **Outlook-App** wird der Benutzer beim Starten der App zur Eingabe einer PIN aufgefordert. Bei der **OneDrive-App** wird der Benutzer zur Eingabe der PIN aufgefordert, wenn er das Geschäftskonto eingibt. Bei Microsoft **Word**, **PowerPoint** und **Excel** wird der Benutzer zur Eingabe der PIN aufgefordert, wenn er auf Dokumente zugreift, die am OneDrive for Business-Speicherort des Unternehmens gespeichert sind.

##  <a name="manage-user-accounts-on-the-device"></a>Verwalten von Benutzerkonten auf dem Gerät

Intune unterstützt die Bereitstellung von MAM-Richtlinien nur auf je einem Benutzerkonto pro Gerät.

* Abhängig von der verwendeten App, ist der zweite Benutzer auf dem Gerät möglicherweise blockiert. Unter allen Umständen wirken sich die MAM-Richtlinien nur auf den ersten Benutzer aus.

  * **Microsoft Word**, **Excel** und **PowerPoint** blockieren ein zweites Benutzerkonto nicht, die MAM-Richtlinien wirken sich auf das zweite Benutzerkonto aber nicht aus.

  * Für **OneDrive**- und **Outlook-Apps** können Sie nur ein Geschäftskonto verwenden.  Sie können für diese Apps nicht mehrere Geschäftskonten hinzufügen.  Sie können jedoch einen Benutzer entfernen und auf dem Gerät einen weiteren Benutzer hinzufügen.


* Wenn für ein Gerät vor der Bereitstellung der MAM-Richtlinien mehrere Benutzerkonten vorhanden sind, wird das Konto, für das die MAM-Richtlinien zuerst bereitgestellt werden, durch die Intune MAM-Richtlinien verwaltet.


Lesen Sie das folgende Beispielszenario, um genauer zu verstehen, wie mehrere Benutzerkonten behandelt werden.

Benutzer A arbeitet für zwei Unternehmen – **Unternehmen X** und **Unternehmen Y**. Der Benutzer A verfügt für jedes Unternehmen über ein geschäftliches Konto, und beide verwenden Intune zum Bereitstellen von MAM-Richtlinien. **Unternehmen X** stellt MAM-Richtlinien **vor** **Unternehmen Y** bereit. Das **Unternehmen X** zugeordnete Konto erhält die MAM-Richtlinie, nicht jedoch das dem Unternehmen Y zugeordnete Konto. Wenn das Unternehmen Y zugeordnete Konto durch die MAM-Richtlinien verwaltet werden soll, müssen Sie das Unternehmen X zugeordnete Benutzerkonto entfernen.
### <a name="add-a-second-account"></a>Hinzufügen eines zweiten Kontos
####  <a name="android"></a>Android
Wenn Sie ein Android-Gerät verwenden, wird möglicherweise eine Sperrnachricht mit Anweisungen angezeigt, wie Sie das vorhandene Konto entfernen und ein neues Konto hinzufügen können.  Um das vorhandene Konto zu entfernen, wechseln Sie zu **Einstellungen &gt; Allgemein &gt; Anwendungs-Manager &gt; Unternehmensportal**. Wählen Sie dann **Daten löschen** aus.

![Screenshot der Fehlermeldung und Anweisungen zum Entfernen des Kontos](../media/AppManagement/Android_SwitchUser.png)

##  <a name="view-media-files-with-the-azure-information-protection-app"></a>Anzeigen von Mediendateien mit der Azure Information Protection-App
Verwenden Sie zum Anzeigen unternehmenseigener AV-, PDF- und Bilddateien auf Android-Geräten die [Azure Information Protection-App](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer) (ehemals Rights Management-Freigabe-App).

Laden Sie diese App aus dem Google Play Store herunter.  

Die folgenden Dateitypen werden unterstützt:

* **Audio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (erweitertes AAC+), AAC ELD (erweitertes AAC mit geringer Verzögerung), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE
* **Video:** H.263, H.264 AVC, MPEG-4 SP, VP8
* **Bild:** JPG, PJPG, PNG, PPNG, BMP, PBMP, GIF, PGIF, JPEG, PJPEG
* **Dokumente:** PDF, PPDF


|**pfile**|**text**|
|----|----|
|Pfile ist ein generisches „Wrapper“-Format für geschützte Dateien, das den verschlüsselten Inhalt sowie die Azure Information Protection-Lizenzen kapselt. Es kann zum Schützen beliebiger Dateitypen verwendet werden.|Textdateien, einschließlich XML, CSV, etc., können zum Anzeigen in der App geöffnet werden, selbst wenn sie geschützt sind. Dateitypen: TXT, PTXT, CSV, PCSV, LOG, PLOG, XML, PXML.|

## <a name="next-steps"></a>Nächste Schritte
[Was Sie erwartet, wenn Ihre iOS-App von MAM-Richtlinien verwaltet wird](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)

### <a name="see-also"></a>Weitere Informationen:
[Erstellen und Bereitstellen von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


