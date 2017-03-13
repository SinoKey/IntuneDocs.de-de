---
title: "Abrufen eines Apple-DEP-Zertifikats für Intune"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Anweisungen zum Konfigurieren und Hochladen eines MDM-Push-Zertifikats, das Voraussetzung für die Verwaltung von Apple-Geräten in Intune ist. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/03/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e5c79c5-2883-4841-9be6-74cba16ee447
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 8edc42bb86e3856ac6568cc3c1acc5d757978e79
ms.lasthandoff: 02/18/2017

---

# <a name="get-an-apple-dep-certificate"></a>Abrufen eines Apple-DEP-Zertifikats

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Bevor Sie unternehmenseigene iOS-Geräte mit dem Apple-Programm zur Geräteregistrierung (Device Enrollment Program, DEP) registrieren können, benötigen Sie ein DEP-Token von Apple. Mit diesem Token kann Intune Informationen zu DEP-Geräten synchronisieren, die Ihrem Unternehmen gehören. Damit kann Intune außerdem Registrierungsprofile an Apple übermitteln und diesen Profilen Geräte zuweisen.

Zum Verwalten unternehmenseigener iOS-Geräte mit DEP müssen Unternehmen am Apple-DEP teilnehmen und Geräte über das Programm beziehen. Ausführliche Informationen zu diesem Prozess finden Sie unter https://deploy.apple.com. Das Programm bietet den Vorteil, dass Geräte eingerichtet werden können, ohne dass ein USB-Kabel für die Verbindung jedes Geräts mit einem Computer verwendet werden muss.

> [!NOTE]
> Dieser Hinweis gilt nur für Intune-Kunden, die von der Intune-Verwaltungskonsole zum Azure-Portal migriert wurden. Wenn Sie während der Migrationsphase ein Apple-DEP-Token über die Intune-Verwaltungskonsole gelöscht haben, wurde das DEP-Token möglicherweise in Ihrem Intune-Konto wiederhergestellt. In diesem Fall müssen Sie das DEP-Token einfach vom Azure-Portal löschen.

## <a name="steps-to-get-the-apple-dep-certificate"></a>So rufen Sie das Apple-DEP-Zertifikat ab
Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** > **Apple-Apple-DEP-Token** aus, und befolgen Sie die nachstehend dargestellten nummerierten Schritte im Azure-Portal.

**Schritt 1: Laden Sie ein Intune-Zertifikat mit öffentlichem Schlüssel herunter, das zum Erstellen eines Apple-DEP-Tokens erforderlich ist.**<br>
Wählen Sie **Laden Sie Ihr Zertifikat mit öffentlichem Schlüssel herunter** aus, um die Verschlüsselungsschlüsseldatei (PEM) herunterzuladen und lokal zu speichern. Die PEM-Datei wird verwendet, um ein Vertrauensstellungszertifikat vom Apple Device Enrollment Program-Portal anzufordern.

**Schritt 2: Laden Sie ein Apple-DEP-Token über die entsprechende Apple-Website herunter.**<br>
Wählen Sie [DEP-Token über Apple-Bereitstellungsprogramme erstellen](https://deploy.apple.com) (https://deploy.apple.com) aus, und melden Sie sich mit der Apple-ID Ihres Unternehmens an. Diese Apple-ID muss später zum Erneuern Ihres DEP-Token verwendet werden.

   a.  Wechseln Sie im [Portal des Programms zur Geräteregistrierung](https://deploy.apple.com) zu **Programm zur Geräteregistrierung** &gt; **Server verwalten**, und wählen Sie anschließend **MDM-Server hinzufügen** aus.

   b.  Geben Sie den **MDM-Servernamen** ein, und wählen Sie anschließend **Weiter** aus. Der Servername dient als Referenz zum Identifizieren des MDM-Servers (mobile device management, Verwaltung mobiler Geräte). Es handelt sich nicht um den Namen oder die URL des Microsoft Intune-Servers.

   c.  Das Dialogfeld **&lt;Servername&gt; hinzufügen** wird geöffnet. Wählen Sie **Datei auswählen** aus, um die PEM-Datei hochzuladen, und wählen Sie anschließend **Weiter** aus.

   d.  Im Dialogfeld **&lt;Servername&gt; hinzufügen** wird der Link **Ihr Servertoken** angezeigt. Laden Sie die Servertokendatei (.p7m) auf Ihren Computer herunter, und wählen Sie anschließend **Fertig** aus.

    This certificate (.p7m) file is used to establish a trust relationship between Intune and Apple’s Device Enrollment Program servers.

**Schritt 3: Geben Sie die zum Erstellen Ihres Apple-DEP-Tokens verwendete Apple-ID ein. Diese ID kann verwendet werden, um das Apple-DEP-Token zu erneuern.**

**Schritt 4: Navigieren Sie zu Ihrem hochzuladenden Apple-DEP-Token. Intune führt automatisch eine Synchronisierung mit Ihrem DEP-Konto durch.**<br>
Wechseln Sie zur Zertifikatsdatei (.pem), wählen Sie **Öffnen** aus, und wählen Sie dann **Hochladen**aus. Mit dem Push-Zertifikat kann Intune iOS-Geräte registrieren und verwalten, indem die Richtlinie auf registrierte mobile Geräte übertragen wird.

