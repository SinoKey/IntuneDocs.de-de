---
title: Android-Apps mit MAM-Richtlinien | Microsoft Intune
description: "In diesem Thema wird beschrieben, was Sie erwartet, wenn Ihre App von Verwaltungsrichtlinien für mobile Apps verwaltet wird."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 389daf0ed39fa2cd4b2e5d6e52cbd6809a568c9e
ms.openlocfilehash: 546b909737b4ea34bd747880fe8ed2d366c6b18a


---

# Was Sie erwartet, wenn Ihre Android-App von MAM-Richtlinien verwaltet wird
Dieses Thema beschreibt die Benutzererfahrung für Apps mit MAM-Richtlinien. MAM-Richtlinien (mobile application management, Verwaltung mobiler Anwendungen) gelten nur, wenn Apps im geschäftlichen Kontext verwendet werden, z.B. wenn Sie Ihr Geschäftskonto für den Zugriff auf Apps verwenden oder auf Dateien zugreifen, die am OneDrive for Business-Speicherort Ihres Unternehmens gespeichert sind.
##  Zugreifen auf Apps

Die Unternehmensportal-App ist auf Android-Geräten für alle Apps erforderlich, die MAM-Richtlinien zugeordnet sind.

Bei Geräten, die nicht bei Intune registriert sind, muss die Unternehmensportal-App auf dem Gerät installiert sein. Jedoch müssen Benutzer die Unternehmensportal-App nicht starten bzw. sich darin anmelden, bevor sie Apps verwenden können, die von MAM-Richtlinien verwaltet werden.
Die Unternehmensportal-App stellt für Intune eine Methode zum Freigeben von Daten an einen sicheren Speicherort dar. Daher wird diese App angefordert, auch wenn das Gerät nicht bei Intune registriert ist.


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
####  Android
Wenn Sie ein Android-Gerät verwenden, wird möglicherweise eine Sperrnachricht mit Anweisungen angezeigt, wie Sie das vorhandene Konto entfernen und ein neues Konto hinzufügen können.  Um das vorhandene Konto zu entfernen, wechseln Sie zu **Einstellungen &gt; Allgemein &gt; Anwendungs-Manager &gt; Unternehmensportal**, und wählen Sie „Daten löschen“ aus.

![Screenshot der Fehlermeldung und Anweisungen zum Entfernen des Kontos](../media/AppManagement/Android_SwitchUser.png)

##  Anzeigen von Mediendateien mit der Azure Information Protection-App (zuvor bekannt als Rights Management-Freigabeanwendung)
Verwenden Sie zum Anzeigen unternehmenseigener AV-, PDF- und Bilddateien auf Android-Geräten die [Azure Information Protection-App](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer).

Laden Sie diese App aus dem Google Play herunter.  

Die folgenden Dateitypen werden unterstützt:

* **Audio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (erweitertes AAC+), AAC ELD (enhanced low delay ACC, erweitertes AAC mit geringer Verzögerung), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE.
* **Video:** H.263, H.264 AVC, MPEG-4 SP, VP8.
* **Bild:** JPG, PJPG, PNG, PPNG, BMP, PBMP, GIF, PGIF, JPEG, PJPEG.
* **Dokumente:** PDF, PPDF

------------
|**Pfile**|**text**|
|----|----|
|Pfile ist ein generisches „Wrapper“-Format für geschützte Dateien, das den verschlüsselten Inhalt sowie die Azure Information Protection-Lizenzen kapselt und zum Schützen beliebiger Dateitypen verwendet werden kann.|Textdateien, einschließlich XML, CSV, etc. können zum Anzeigen in der App geöffnet werden, selbst wenn sie geschützt sind. Dateitypen: TXT, PTXT, CSV, PCSV, LOG, PLOG, XML, PXML.|
---------------
## Nächste Schritte
[Was Sie erwartet, wenn Ihre iOS-App von MAM-Richtlinien verwaltet wird](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)

### Weitere Informationen:
[Erstellen und Bereitstellen von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


