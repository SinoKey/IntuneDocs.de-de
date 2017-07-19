---
title: Verwalten von Apps aus einem iOS-Volumenprogramm
titleSuffix: Intune on Azure
description: "Erfahren Sie, wie Sie Apps, die Sie über ein Volumenprogramm im iOS Store erworben haben, in Intune synchronisieren und dann ihre Nutzung verwalten und nachverfolgen.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 16b7ce81eb63a81534af2911b34904d870ac41ad
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2017
---
# <a name="how-to-manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Verwalten von iOS-Apps, die über ein Volumenprogramm mit Microsoft Intune erworben wurden


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Der iOS-App-Store bietet die Möglichkeit, mehrere Lizenzen für eine App zu erwerben, die in Ihrem Unternehmen ausgeführt werden soll. Sie können den Verwaltungsaufwand reduzieren, der durch das Nachverfolgen mehrerer erworbener App-Kopien entsteht, indem Sie mehrere Kopien einer App erwerben.

Microsoft Intune hilft Ihnen beim Verwalten von Apps, die Sie über dieses Programm erworben haben:

- Importieren der Lizenzinformationen aus dem App-Store
- Nachverfolgen, wie viele Lizenzen bereits verwendet wurden
- Verhindern, dass Sie mehr Kopien der App installieren, als Sie besitzen

Außerdem können Sie Bücher, die Sie aus dem Apple-VPP-Store mit Intune gekauft haben, synchronisieren und verwalten. Verwenden Sie die Arbeitsauslastung **Books** (Bücher) im Intune-Portal, um Bücher zu verwalten. Die Verfahren zum Verwalten der Bücher sind identisch mit denen zum Verwalten von Apps.
Sie müssen ein Apple-VPP-Token hochgeladen haben, bevor Sie beginnen. Derzeit können Sie Bücher nur als **Required**-Installation (erforderlich) zuweisen.
Wenn Sie ein Buch einem Gerät zuweisen, muss auf dem Gerät die integrierte iBooks-App installiert sein. Wenn dies nicht der Fall ist, muss der Endbenutzer die App erneut installieren, um das Buch zu lesen. Sie können Intune derzeit nicht zum Wiederherstellen entfernt integrierter Apps verwenden.


## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Verwalten von Apps für iOS-Geräte, die über ein Volumenprogramm erworben wurden
Erwerben Sie mehrere Lizenzen für iOS-Apps über das [Programm für Volumenlizenzen für Unternehmen](http://www.apple.com/business/vpp/) oder das [Programm für Volumenlizenzen für Bildungseinrichtungen](http://volume.itunes.apple.com/us/store) (Volume Purchase Program, VPP) von Apple. Dieser Vorgang umfasst das Einrichten eines Apple VPP-Kontos auf der Apple-Website und das Hochladen des Apple VPP-Tokens in Intune.  Anschließend können Sie Ihre Informationen zum Volumenerwerb mit Intune synchronisieren und die Verwendung der im Rahmen des Volumenprogramms erworbenen App verfolgen.

## <a name="before-you-start"></a>Vorbereitung
Bevor Sie beginnen, müssen Sie ein VPP-Token von Apple abrufen und es in Ihr Intune-Konto hochladen. Beachten Sie darüber hinaus die folgenden Kriterien:

* Sie können Ihrem Intune-Konto mehrere Token für das Programm für Volumenlizenzen zuordnen.
* Wenn Sie zuvor ein VPP-Token für ein anderes Produkt verwendet haben, müssen Sie für die Verwendung mit Intune ein neues erstellen.
* Jedes Token ist ein Jahr lang gültig.
* Standardmäßig wird Intune zweimal täglich mit dem Apple VPP-Dienst synchronisiert. Eine manuelle Synchronisierung können Sie jederzeit starten.
* Nachdem Sie den VPP-Token in Intune importiert haben, importieren Sie denselben Token in keine andere Geräteverwaltungslösung. Andernfalls kann dies zu einem Verlust von Lizenzzuweisung und Benutzerdatensätzen führen.
* Bevor Sie iOS VPP mit Intune verwenden, entfernen Sie alle vorhandenen, mit anderen Anbietern für das Mobile-Geräte-Management (MDM) erstellten VPP-Benutzerkonten. Aus Sicherheitsgründen synchronisiert Intune diese Benutzerkonten nicht. Intune synchronisiert nur Daten aus dem Apple VPP-Dienst, der von Intune erstellt wurde.
* Intune unterstützt bis zu 256 VPP-Token.
* Wenn Sie eine über ein Volumenprogramm erworbene App für ein über ein Anmeldungsprofil für mobile Geräte oder Apple Configurator registriertes Gerät zuweisen möchten, ist dies nur mit auf Geräte ausgerichtete Apps möglich. Sie können keine mit einem Volumenprogramm erworbenen Apps als Ziel für Benutzer eines DEP-Geräts verwenden, das keine Benutzeraffinität aufweist.
* Sie können ein VPP-Token nur mit einem Intune-Konto gleichzeitig verwenden. Verwenden Sie nicht das gleiche VPP-Token für mehrere Intune-Mandanten gleichzeitig.
* Wenn Sie Benutzern oder Geräten mit einem Benutzerlizenzierungsmodell VPP-Apps (mit Benutzeraffinität) zuweisen, muss jeder Intune-Benutzer mit einer eindeutigen Apple-ID oder einer E-Mail-Adresse verknüpft sein, wenn er die allgemeinen Geschäftsbedingungen von Apple auf ihrem Gerät akzeptiert.
Achten Sie beim Einrichten eines Geräts für einen Intune-Benutzer darauf, dass Sie es mit der eindeutigen Apple-ID oder der E-Mail-Adresse des Benutzers konfigurieren. Die Apple-ID bzw. E-Mail-Adresse und der Intune-Benutzer sind ein eindeutiges Paar, das auf bis zu 5 Geräten verwendet werden kann.


## <a name="to-get-and-upload-an-apple-vpp-token"></a>So können Sie einen Apple VPP-Token abrufen und hochladen

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Mobile Apps** aus.
1.  Wählen Sie in der Workload **Mobile Apps** die Option **Setup** > **iOS-VPP-Token** aus.
2.  Klicken Sie auf dem Blatt mit der Liste der VPP-Token auf **Hinzufügen**.
3.  Geben Sie auf dem Blatt **Neues VPP-Token** die folgenden Informationen an:
    - **VPP-Tokendatei**: Wenn Sie dies noch nicht getan haben, registrieren Sie sich für das Volume Purchase Program für Unternehmen oder für Bildungseinrichtungen. Sobald Sie registriert sind, laden Sie das Apple-VPP-Token für Ihr Konto herunter und wählen es hier aus.
    - **Apple-ID:** Geben Sie die Apple-ID des Kontos ein, das dem Programm für Volumenlizenzen zugeordnet ist.
    - **Typ des VPP-Kontos:** Wählen Sie **Unternehmen** oder **Bildungswesen** aus.
4. Klicken Sie abschließend auf **Hochladen**.

Das Token wird auf dem Blatt mit der Liste der Token angezeigt.


Sie können die von Apple gespeicherten Daten jederzeit mit Intune synchronisieren, indem Sie **Jetzt synchronisieren** wählen.

> [!NOTE]
> Microsoft Intune synchronisiert nur Informationen von Apps, die über den iTunes Store öffentlich verfügbar sind. **Benutzerdefinierte B2B-Apps für iOS** werden noch nicht unterstützt. Wenn Ihr Szenario für solche Apps vorgesehen ist, sind die App-Informationen nicht synchronisiert.

## <a name="to-assign-a-volume-purchased-app"></a>So weisen Sie per Volumenlizenz erworbene Apps zu

1. Wählen Sie in der Workload **Mobile Apps** die Option **Verwalten** > **Lizenzierte Apps** aus.
2. Wählen Sie auf dem Blatt mit der Liste der Apps die App, die Sie zuweisen möchten, und dann „**...**“ > **Gruppen zuweisen** aus.
3. Wählen Sie auf dem Blatt <*App-Name*> - **Zugewiesene Gruppen** die Option **Verwalten** > **Gruppen zugewiesen** aus.
4. Wählen Sie **Gruppen zuweisen** und dann auf dem Blatt **Gruppen auswählen** den Azure AD-Benutzer oder Gerätegruppen aus, denen Sie die App zuweisen möchten.
Sie müssen eine Zuweisungsaktion vom Typ **Erforderlich** auswählen. Darüber hinaus sind Zuweisungen zu Gerätegruppen für neu erstellte Mandanten nach Januar 2017 verfügbar. Wenn Ihr Mandant vor diesem Datum erstellt wurde, und Sie nicht über die Möglichkeit verfügen, Gerätegruppen VPP-Apps hinzuzufügen, wenden Sie sich an den Intune-Support.
5. Wählen Sie abschließend **Speichern** aus.

>[!NOTE]
>Dies angezeigte App-Liste ist mit einem Token verknüpft. Wenn Sie eine App haben, die mit mehreren VPP-Token verknüpft ist, wird die App mehrmals angezeigt: für jedes Token einmal.

Weitere Informationen zum Überwachen von App-Zuweisungen finden Sie unter [Überwachen von Apps](apps-monitor.md).

## <a name="further-information"></a>Weitere Informationen

Wenn Sie die Anwendung als **erforderliche** Installation zuweisen, verwendet jeder Benutzer, der die App installiert, eine Lizenz.

Zum Freigeben einer Lizenz müssen Sie die Zuweisungsaktion in **Deinstallieren** ändern. Die Lizenz wird freigegeben, wenn die App deinstalliert wird.

Wenn ein Benutzer mit einem geeigneten Gerät erstmals versucht, eine VPP-App zu installieren, wird er aufgefordert, am Volume Purchase Program (VPP) von Apple teilzunehmen. Die Teilnahme muss erfolgen, bevor die App-Installation fortgesetzt wird. Die Einladung, am Apple Volume Purchase Program teilzunehmen, erfordert, dass der Benutzer die iTunes-App auf dem iOS-Gerät verwenden kann. Wenn Sie eine Richtlinie aufgestellt haben, um die iTunes Store-App zu deaktivieren, funktioniert die benutzerbasierte Lizenzierung für VPP-Apps nicht. Die Lösung besteht darin, die iTunes-App durch Entfernen der Richtlinie zuzulassen oder die gerätebasierte Lizenzierung zu verwenden.

Wenn Sie eine VPP-App als verfügbar zuweisen, werden Inhalte und Lizenz der App direkt vom App Store aus zugewiesen.
