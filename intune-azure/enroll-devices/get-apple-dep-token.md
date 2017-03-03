---
title: "Abrufen eines Apple-DEP-Zertifikats für Intune | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Anweisungen zum Konfigurieren und Hochladen eines MDM-Push-Zertifikats, das Voraussetzung für die Verwaltung von Apple-Geräten in Intune ist. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/03/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e5c79c5-2883-4841-9be6-74cba16ee447
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: b2c79e92f6378825bdaac03d2d9be699bdaca95b
ms.lasthandoff: 02/15/2017

---

# <a name="get-an-apple-dep-certificate"></a>Abrufen eines Apple-DEP-Zertifikats 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Bevor Sie unternehmenseigene iOS-Geräte mit DEP registrieren können, benötigen Sie ein DEP-Token von Apple. Mit diesem Token kann Intune Informationen zu DEP-Geräten synchronisieren, die Ihrem Unternehmen gehören. Damit kann Intune außerdem Registrierungsprofile an Apple übermitteln und diesen Profile Geräte zuweisen.

Zum Verwalten unternehmenseigener iOS-Geräte mit dem Apple-Programm zur Geräteregistrierung (Device Enrollment Program, DEP) müssen Unternehmen am Apple-DEP teilnehmen und Geräte über das Programm beziehen. Ausführliche Informationen zu diesem Prozess finden Sie unter https://deploy.apple.com. Das Programm bietet den Vorteil, dass Geräte eingerichtet werden können, ohne dass ein USB-Kabel für die Verbindung jedes Geräts mit einem Computer verwendet werden muss.

> [!NOTE]
> Lesen Sie diesen Hinweis nur, wenn Sie ein Kunde sind, die von der Intune-Verwaltungskonsole zum Azure-Portal migriert wurde. Wenn Sie während der Migrationsphase ein Apple-DEP-Token über die Intune-Verwaltungskonsole gelöscht haben, wurde das DEP-Token möglicherweise in Ihrem Intune-Konto wiederhergestellt. In diesem Fall müssen Sie das DEP-Token einfach vom Azure-Portal löschen. 

**So rufen Sie das Apple-DEP-Zertifikat ab**</br>
Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** > **Apple-Apple-DEP-Token** aus, und befolgen Sie die nachstehend dargestellten nummerierten Schritte im Azure-Portal.

**Schritt 1: Laden Sie ein Intune-Zertifikat mit öffentlichem Schlüssel herunter, das zum Erstellen eines Apple-DEP-Tokens erforderlich ist.**<br>
Wählen Sie **Laden Sie Ihr Zertifikat mit öffentlichem Schlüssel herunter** aus, um die Verschlüsselungsschlüsseldatei (PEM) herunterzuladen und lokal zu speichern. Die PEM-Datei wird verwendet, um ein Vertrauensstellungszertifikat vom Apple Device Enrollment Program-Portal anzufordern.

**Schritt 2: Laden Sie ein Apple-DEP-Token über die entsprechende Apple-Website herunter.**<br>
Wählen Sie [DEP-Token über Apple-Bereitstellungsprogramme erstellen](https://deploy.apple.com) (https://deploy.apple.com) aus, und melden Sie sich mit der Apple-ID Ihres Unternehmens an. Diese Apple-ID muss später zum Erneuern Ihres DEP-Token verwendet werden.

   1.  Wechseln Sie im [Portal des Programms zur Geräteregistrierung](https://deploy.apple.com) zu **Programm zur Geräteregistrierung** &gt; **Server verwalten**, und wählen Sie anschließend **MDM-Server hinzufügen** aus.

   2.  Geben Sie den **MDM-Servernamen** ein, und wählen Sie anschließend **Weiter** aus. Der Servername dient als Referenz zum Identifizieren des MDM-Servers (mobile device management, Verwaltung mobiler Geräte). Es handelt sich nicht um den Namen oder die URL des Microsoft Intune-Servers.

   3.  Das Dialogfeld **&lt;Servername&gt; hinzufügen** wird geöffnet. Wählen Sie **Datei auswählen** aus, um die PEM-Datei hochzuladen, und wählen Sie anschließend **Weiter** aus.

   4.  Im Dialogfeld **&lt;Servername&gt; hinzufügen** wird der Link **Ihr Servertoken** angezeigt. Laden Sie die Servertokendatei (.p7m) auf Ihren Computer herunter, und wählen Sie anschließend **Fertig** aus.

    Diese Zertifikatdatei (.p7m) wird verwendet, um eine Vertrauensstellung zwischen dem Intune- und Apple Device Enrollment Program-Server herzustellen.

**Schritt 3: Geben Sie die zum Erstellen Ihres Apple-DEP-Tokens verwendete Apple-ID ein. Diese ID kann verwendet werden, um das Apple-DEP-Token zu erneuern.**

**Schritt 4: Navigieren Sie zu Ihrem hochzuladenden Apple-DEP-Token. Intune führt automatisch eine Synchronisierung mit Ihrem DEP-Konto durch.**<br>
Wechseln Sie zur Zertifikatsdatei (.pem), wählen Sie **Öffnen** aus, und wählen Sie dann **Hochladen**aus. Mit dem Push-Zertifikat kann Intune iOS-Geräte registrieren und verwalten, indem die Richtlinie auf registrierte mobile Geräte übertragen wird.

