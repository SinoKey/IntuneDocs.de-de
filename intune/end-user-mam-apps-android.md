---
title: Android-Apps mit App-Schutzrichtlinien
description: In diesem Thema erfahren Sie, was Sie erwartet, wenn Ihre App von App-Schutzrichtlinien verwaltet wird.
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 030e17a9f28a9476c82e89d4dd26151a2d3cb953
ms.sourcegitcommit: f100c943a635f5a08254ba7cf30f1aaebb7e810e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2017
---
# Was Sie erwartet, wenn Ihre Android-App von App-Schutzrichtlinien verwaltet wird
<a id="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies" class="xliff"></a>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Dieses Thema beschreibt die Benutzererfahrung für Apps mit App-Schutzrichtlinien. App-Schutzrichtlinien gelten nur, wenn Apps in einem geschäftlichen Kontext verwendet werden, z.B. wenn der Benutzer ein Geschäftskonto für den Zugriff auf Apps verwendet oder auf Dateien zugreift, die an einem OneDrive for Business-Speicherort im Unternehmen gespeichert sind.
##  Zugriff auf Apps
<a id="access-apps" class="xliff"></a>

Die Unternehmensportal-App ist auf Android-Geräten für alle Apps erforderlich, die App-Schutzrichtlinien zugeordnet sind.

Bei Geräten, die nicht bei Intune registriert sind, muss die Unternehmensportal-App auf dem Gerät installiert sein. Jedoch muss der Benutzer die Unternehmensportal-App nicht starten bzw. sich darin anmelden, bevor er Apps verwenden kann, die von App-Schutzrichtlinien verwaltet werden.

Die Unternehmensportal-App ist in Intune eine Möglichkeit der Freigabe von Daten an einem sicheren Ort. Daher ist die Unternehmensportal-App eine Voraussetzung für alle Apps, denen App-Schutzrichtlinien zugeordnet sind, auch wenn das Gerät nicht in Intune registriert ist.


##  Verwenden von Apps mit Unterstützung von mehreren Identitäten
<a id="use-apps-with-multi-identity-support" class="xliff"></a>

App-Schutzrichtlinien werden nur im geschäftlichen Kontext angewendet. Eine App kann sich daher unterschiedlich verhalten, je nachdem, ob sie im geschäftlichen oder privaten Kontext verwendet wird.

Beispielsweise erhalten Benutzer eine PIN-Eingabeaufforderung, wenn Sie auf Geschäftsdaten zugreifen. Bei der **Outlook-App** wird der Benutzer beim Starten der App zur Eingabe einer PIN aufgefordert. Bei der **OneDrive-App** wird der Benutzer zur Eingabe der PIN aufgefordert, wenn er das Geschäftskonto eingibt. Bei Microsoft **Word**, **PowerPoint** und **Excel** wird der Benutzer zur Eingabe der PIN aufgefordert, wenn er auf Dokumente zugreift, die am OneDrive for Business-Speicherort des Unternehmens gespeichert sind.

##  Verwalten von Benutzerkonten auf dem Gerät
<a id="manage-user-accounts-on-the-device" class="xliff"></a>

Intune unterstützt die Bereitstellung von App-Schutzrichtlinien nur auf je einem Benutzerkonto pro Gerät.

* Abhängig von der verwendeten App, ist der zweite Benutzer auf dem Gerät möglicherweise blockiert. Unter allen Umständen wirken sich die App-Schutzrichtlinien nur auf den ersten Benutzer aus.

  * **Microsoft Word**, **Excel** und **PowerPoint** blockieren ein zweites Benutzerkonto nicht, die App-Schutzrichtlinien wirken sich auf das zweite Benutzerkonto jedoch nicht aus.

  * Für **OneDrive**- und **Outlook-Apps** können Sie nur ein Geschäftskonto verwenden.  Sie können für diese Apps nicht mehrere Geschäftskonten hinzufügen.  Sie können jedoch einen Benutzer entfernen und auf dem Gerät einen weiteren Benutzer hinzufügen.


* Wenn für ein Gerät vor der Bereitstellung der App-Schutzrichtlinien mehrere Benutzerkonten vorhanden sind, wird das Konto, für das die App-Schutzrichtlinien zuerst bereitgestellt werden, durch die Intune-App-Schutzrichtlinien verwaltet.


Lesen Sie das folgende Beispielszenario, um genauer zu verstehen, wie mehrere Benutzerkonten behandelt werden.

Benutzer A arbeitet für zwei Unternehmen – **Unternehmen X** und **Unternehmen Y**. Benutzer A verfügt für jedes Unternehmen über ein geschäftliches Konto, und beide verwenden Intune zum Bereitstellen von App-Schutzrichtlinien. **Unternehmen X** stellt App-Schutzrichtlinien **vor** **Unternehmen Y** bereit. Das dem **Unternehmen X** zugeordnete Konto erhält die App-Schutzrichtlinie, nicht jedoch das dem Unternehmen Y zugeordnete Konto. Wenn das dem Unternehmen Y zugeordnete Konto durch die App-Schutzrichtlinien verwaltet werden soll, müssen Sie das dem Unternehmen X zugeordnete Benutzerkonto entfernen.
### Hinzufügen eines zweiten Kontos
<a id="add-a-second-account" class="xliff"></a>
####  Android
<a id="android" class="xliff"></a>
Wenn Sie ein Android-Gerät verwenden, wird möglicherweise eine Sperrnachricht mit Anweisungen angezeigt, wie Sie das vorhandene Konto entfernen und ein neues Konto hinzufügen können.  Um das vorhandene Konto zu entfernen, wechseln Sie zu **Einstellungen &gt; Allgemein &gt; Anwendungs-Manager &gt; Unternehmensportal**. Wählen Sie dann **Daten löschen** aus.

![Screenshot der Fehlermeldung und Anweisungen zum Entfernen des Kontos](./media/Android_SwitchUser.png)

##  Anzeigen von Mediendateien mit der Azure Information Protection-App
<a id="view-media-files-with-the-azure-information-protection-app" class="xliff"></a>
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

## Nächste Schritte
<a id="next-steps" class="xliff"></a>
[Was Sie erwartet, wenn Ihre iOS-App von App-Schutzrichtlinien verwaltet wird](end-user-mam-apps-ios.md)
