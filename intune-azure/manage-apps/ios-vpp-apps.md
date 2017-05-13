---
title: "Verwalten von über ein Volumenprogramm erworbenen iOS-Apps | Microsoft-Dokumentation"
titleSuffix: Intune Azure preview
description: 'Intune in Azure (Vorschau): Erfahren Sie, wie Sie Apps, die Sie per Volumenlizenz im iOS Store erworben haben, in Intune synchronisieren und dann ihre Nutzung verwalten und nachverfolgen.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: f9e8a5deb17ebb77d480213567e5ccf6550e3493
ms.openlocfilehash: 1909549b321f51069bb6ad83f2f245afbf60b7dd
ms.contentlocale: de-de
ms.lasthandoff: 05/03/2017

---

# <a name="how-to-manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Verwalten von iOS-Apps, die über ein Volumenprogramm mit Microsoft Intune erworben wurden


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Der iOS-App-Store bietet die Möglichkeit, mehrere Lizenzen für eine App zu erwerben, die in Ihrem Unternehmen ausgeführt werden soll. Dadurch können Sie den Verwaltungsaufwand reduzieren, der durch das Nachverfolgen mehrerer erworbener App-Kopien entsteht.

Microsoft Intune unterstützt Sie bei der Verwaltung von Apps, die über ein solches Programm erworben wurden. Dazu importieren Sie die Lizenzinformationen aus dem App-Store, verfolgen nach, wie viele Lizenzen verwendet wurden, und verhindern, dass mehr App-Kopien installiert werden, als Sie erworben haben.

Außerdem können Sie Bücher, die Sie aus dem Apple-VPP-Store mit Intune gekauft haben, synchronisieren, verwalten und Benutzern zuweisen. Verwenden Sie die Arbeitsauslastung **Books** (Bücher) im Intune-Portal, um Bücher zu verwalten. Die Verfahren zum Verwalten der Bücher sind identisch mit denen zum Verwalten von Apps.
Sie müssen ein Apple-VPP-Token hochgeladen haben, um dies zu tun. Derzeit können Sie Bücher nur als **Required**-Installation (erforderlich) zuweisen.
Wenn Sie ein Buch einem Gerät zuweisen, muss auf dem Gerät die integrierte iBooks-App installiert sein. Wenn dies nicht der Fall ist, muss der Endbenutzer die App erneut installieren, um das Buch zu lesen. Sie können Intune derzeit nicht zum Wiederherstellen entfernt integrierter Apps verwenden.


## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Verwalten von Apps für iOS-Geräte, die über ein Volumenprogramm erworben wurden
Sie erwerben mehrere Lizenzen für iOS-Apps über das [Programm für Volumenlizenzen für Unternehmen](http://www.apple.com/business/vpp/) oder das [Programm für Volumenlizenzen für Bildungseinrichtungen](http://volume.itunes.apple.com/us/store) (Volume Purchase Program, VPP) von Apple. Dies umfasst das Einrichten eines Apple VPP-Kontos auf der Apple-Website und das Hochladen des Apple VPP-Tokens in Intune.  Anschließend können Sie Ihre Informationen zum Volumenerwerb mit Intune synchronisieren und die Verwendung der im Rahmen des Volumenprogramms erworbenen App verfolgen.

## <a name="before-you-start"></a>Vorbereitung
Bevor Sie beginnen, müssen Sie ein VPP-Token von Apple abrufen und es in Ihr Intune-Konto hochladen. Beachten Sie darüber hinaus die folgenden Informationen:

* Sie können Ihrem Intune-Konto mehrere Token für das Programm für Volumenlizenzen zuordnen.
* Wenn Sie zuvor ein VPP-Token für ein anderes Produkt verwendet haben, müssen Sie für die Verwendung mit Intune ein neues erstellen.
* Jedes Token ist ein Jahr lang gültig.
* Standardmäßig wird Intune zweimal täglich mit dem Apple VPP-Dienst synchronisiert. Eine manuelle Synchronisierung können Sie jederzeit starten.
* Nachdem Sie den VPP-Token in Intune importiert haben, importieren Sie denselben Token in keine andere Geräteverwaltungslösung. Andernfalls kann dies zu einem Verlust von Lizenzzuweisung und Benutzerdatensätzen führen.
* Bevor Sie iOS VPP mit Intune verwenden, entfernen Sie alle vorhandenen, mit anderen Anbietern für das Mobile-Geräte-Management (MDM) erstellten VPP-Benutzerkonten. Aus Sicherheitsgründen werden diese Benutzerkonten in Intune nicht synchronisiert. Intune synchronisiert nur Daten aus dem Apple VPP-Dienst, der von Intune erstellt wurde.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>So können Sie einen Apple VPP-Token abrufen und hochladen

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Andere** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Mobile Apps** aus.
1.  Wählen Sie in der Workload **Mobile Apps** die Option **Setup** > **iOS-VPP-Token** aus.
2.  Klicken Sie auf dem Blatt mit der Liste der VPP-Token auf **Hinzufügen**.
3.  Geben Sie auf dem Blatt „Neues VPP-Token“ die folgenden Informationen an:
    - **VPP-Tokendatei:** Sofern nicht bereits geschehen, registrieren Sie sich für das Programm für Volumenlizenzen für Unternehmen oder das Programm für Volumenlizenzen für Bildungseinrichtungen. Sobald Sie registriert sind, laden Sie das Apple-VPP-Token für Ihr Konto herunter und wählen es hier aus.
    - **Apple-ID:** Geben Sie die Apple-ID des Kontos ein, das dem Programm für Volumenlizenzen zugeordnet ist.
    - **Typ des VPP-Kontos:** Wählen Sie **Unternehmen** oder **Bildungswesen** aus.
4. Klicken Sie abschließend auf **Hochladen**.

Das Token wird auf dem Blatt mit der Liste der Token angezeigt.


Sie können die von Apple gespeicherten Daten jederzeit mit Intune synchronisieren, indem Sie **Jetzt synchronisieren** wählen.

## <a name="to-assign-a-volume-purchased-app"></a>So weisen Sie per Volumenlizenz erworbene Apps zu

1. Wählen Sie in der Workload **Mobile Apps** die Option **Verwalten** > **Lizenzierte Apps** aus.
2. Wählen Sie auf dem Blatt mit der Liste der Apps die App, die Sie zuweisen möchten, und dann „**...**“ > **Gruppen zuweisen** aus.
3. Wählen Sie auf dem Blatt <*App-Name*> - **Zugewiesene Gruppen** die Option **Verwalten** > **Gruppen zugewiesen** aus.
4. Wählen Sie **Gruppen zuweisen** und dann auf dem Blatt **Gruppen auswählen** den Azure AD-Benutzer oder Gerätegruppen aus, denen Sie die App zuweisen möchten.
Sie müssen eine Zuweisungsaktion vom Typ **Erforderlich** auswählen. Darüber hinaus sind Zuweisungen zu Gerätegruppen für neu erstellte Mandanten nach Januar 2017 verfügbar. Wenn Ihr Mandant davor erstellt wurde, und Sie nicht über die Möglichkeit verfügen, Gerätegruppen VPP-Apps hinzuzufügen, wenden Sie sich an den Intune-Support.
5. Wählen Sie abschließend **Speichern** aus.

Weitere Informationen zum Überwachen von App-Zuweisungen finden Sie unter [Überwachen von Apps](monitor-apps.md).

## <a name="further-information"></a>Weitere Informationen

Wenn Sie die Anwendung als **erforderliche** Installation zuweisen, verwendet jeder Benutzer, der die App installiert, eine Lizenz.

Zum Freigeben einer Lizenz müssen Sie die Zuweisungsaktion in **Deinstallieren** ändern. Die Lizenz wird freigegeben, wenn die App deinstalliert wird.

Wenn ein Benutzer mit einem geeigneten Gerät erstmals versucht, eine VPP-App zu installieren, wird er aufgefordert, am Programm für Volumenlizenzen (Volume Purchase Program, VPP) von Apple teilzunehmen. Die Teilnahme muss erfolgen, bevor die App-Installation fortgesetzt wird.

Wenn Sie eine VPP-App als verfügbar zuweisen, werden Inhalte und Lizenz der App direkt vom App Store aus zugewiesen.

