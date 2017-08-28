---
title: Verwalten von Apps aus einem iOS-Volumenprogramm
titleSuffix: Intune on Azure
description: "Erfahren Sie, wie Sie Apps, die Sie über ein Volumenprogramm im iOS Store erworben haben, in Intune synchronisieren und dann ihre Nutzung verwalten und nachverfolgen.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1433951e8c17ae226d37705223a80e2e79f7483b
ms.sourcegitcommit: 6a089eb45ea3fb18ae0b2dac96683466f52f95bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2017
---
# <a name="how-to-manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Verwalten von iOS-Apps, die über ein Volumenprogramm mit Microsoft Intune erworben wurden


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Der iOS-App-Store bietet die Möglichkeit, mehrere Lizenzen für eine App zu erwerben, die in Ihrem Unternehmen ausgeführt werden soll. Sie können den Verwaltungsaufwand reduzieren, der durch das Nachverfolgen mehrerer erworbener App-Kopien entsteht, indem Sie mehrere Kopien einer App erwerben.

Microsoft Intune hilft Ihnen beim Verwalten von Apps, die Sie über dieses Programm erworben haben:

- Indem Lizenzinformationen aus dem App Store gemeldet werden
- Nachverfolgen, wie viele Lizenzen bereits verwendet wurden
- Indem verhindert wird, dass mehr Kopien der App installiert werden, als Sie besitzen

Es gibt zwei Methoden, die Sie zum Zuweisen von per Volumenlizenz erworbenen Apps verwenden können:

### <a name="device-licensing"></a>Gerätelizenzierung

Wenn Sie eine App einem Gerät zuweisen, wird eine App-Lizenz verwendet, und die Zuordnung dieser App zu diesem Gerät, zu dem Sie sie zugewiesen haben, bleibt erhalten.
Wenn Sie per Volumenlizenz erworbene Apps einem Gerät zuweisen, muss der Endbenutzer des Geräts keine Apple-ID für den Zugriff auf den Store bereitstellen. 



### <a name="user-licensing"></a>Benutzerlizenzierung

Wenn Sie Benutzern eine App zuweisen, wird eine App-Lizenz für den Benutzer verwendet und ihm zugewiesen. Die App kann auf mehren Geräten des Benutzers ausgeführt werden (die Obergrenze wird von Apple festgelegt).
Wenn Sie Benutzern eine per Volumenlizenz erworbene App zuweisen, muss jeder Benutzer über eine gültige und eindeutige Apple-ID verfügen, um auf den App Store zugreifen zu können.


Außerdem können Sie Bücher, die Sie aus dem Apple-VPP-Store mit Intune gekauft haben, synchronisieren und verwalten. Weitere Informationen finden Sie unter [Verwalten von iOS-E-Books, die über ein Volumenprogramm erworben wurden, mit Microsoft Intune](vpp-ebooks-ios.md).


## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Verwalten von Apps für iOS-Geräte, die über ein Volumenprogramm erworben wurden
Erwerben Sie mehrere Lizenzen für iOS-Apps über das [Programm für Volumenlizenzen für Unternehmen](http://www.apple.com/business/vpp/) oder das [Programm für Volumenlizenzen für Bildungseinrichtungen](http://volume.itunes.apple.com/us/store) (Volume Purchase Program, VPP) von Apple. Dieser Vorgang umfasst das Einrichten eines Apple VPP-Kontos auf der Apple-Website und das Hochladen des Apple VPP-Tokens in Intune.  Anschließend können Sie Ihre Informationen zum Volumenerwerb mit Intune synchronisieren und die Verwendung der im Rahmen des Volumenprogramms erworbenen App verfolgen.

## <a name="before-you-start"></a>Vorbereitung
Bevor Sie beginnen, müssen Sie ein VPP-Token von Apple abrufen und es in Ihr Intune-Konto hochladen. Beachten Sie darüber hinaus die folgenden Kriterien:

* Sie können Ihrem Intune-Konto mehrere Token für das Programm für Volumenlizenzen zuordnen.
* Wenn Sie zuvor ein VPP-Token für ein anderes Produkt verwendet haben, müssen Sie für die Verwendung mit Intune ein neues erstellen.
* Jedes Token ist ein Jahr lang gültig.
* Standardmäßig wird Intune zweimal täglich mit dem Apple VPP-Dienst synchronisiert. Eine manuelle Synchronisierung können Sie jederzeit starten.
* Bevor Sie iOS VPP mit Intune verwenden, entfernen Sie alle vorhandenen, mit anderen Anbietern für das Mobile-Geräte-Management (MDM) erstellten VPP-Benutzerkonten. Aus Sicherheitsgründen synchronisiert Intune diese Benutzerkonten nicht. Intune synchronisiert nur Daten aus dem Apple VPP-Dienst, der von Intune erstellt wurde.
* Intune unterstützt bis zu 256 VPP-Token.
* Wenn Sie eine über ein Volumenprogramm erworbene App für ein über ein Anmeldungsprofil für mobile Geräte oder Apple Configurator registriertes Gerät zuweisen möchten, ist dies nur mit auf Geräte ausgerichtete Apps möglich. Sie können keine mit einem Volumenprogramm erworbenen Apps als Ziel für Benutzer eines DEP-Geräts verwenden, das keine Benutzeraffinität aufweist.
Dies liegt daran, dass bei der iOS VPP-Benutzerlizenzierung Tausende Geräte mit dem gleichen Benutzerkonto registriert werden können. Die iOS VPP-Benutzerlizenzierung ermöglicht es einem Benutzer, eine App auf fünf bis zehn Geräten zu installieren.
Das bedeutet, dass die VPP-App auf den ersten DEM-registrierten Geräten mit der Benutzerlizenzierung installiert wird, während andere Geräte die App nicht erhalten.
* Sie können ein VPP-Token nur mit einem Intune-Konto gleichzeitig verwenden. Verwenden Sie nicht das gleiche VPP-Token für mehrere Intune-Mandanten gleichzeitig.
* Wenn Sie Benutzern oder Geräten mit einem Benutzerlizenzierungsmodell VPP-Apps (mit Benutzeraffinität) zuweisen, muss jeder Intune-Benutzer mit einer eindeutigen Apple-ID oder einer E-Mail-Adresse verknüpft sein, wenn er die allgemeinen Geschäftsbedingungen von Apple auf ihrem Gerät akzeptiert.
Achten Sie beim Einrichten eines Geräts für einen Intune-Benutzer darauf, dass Sie es mit der eindeutigen Apple-ID oder der E-Mail-Adresse des Benutzers konfigurieren. Die Apple-ID bzw. E-Mail-Adresse und der Intune-Benutzer sind ein eindeutiges Paar, das auf bis zu 5 Geräten verwendet werden kann.

>[!IMPORTANT]
>Nachdem Sie den VPP-Token in Intune importiert haben, importieren Sie denselben Token in keine andere Geräteverwaltungslösung. Andernfalls kann dies zu einem Verlust von Lizenzzuweisung und Benutzerdatensätzen führen.

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

1.  Wählen Sie in der Workload **Mobile Apps** die Option **Verwalten** > **App-Lizenzen** aus.
2.  Wählen Sie auf dem Blatt mit der Liste der Apps die App, die Sie zuweisen möchten, und dann **...** > **Gruppen zuweisen**.
3.  Wählen Sie auf dem Blatt *<app name>* - **Zuweisungen** die Optionen **Verwalten** > **Zuweisungen** aus.
4.  Wählen Sie **Gruppen auswählen** und dann auf dem Blatt **Gruppen auswählen** den Azure AD-Benutzer oder Gerätegruppen aus, denen Sie die App zuweisen möchten.
5.  Wählen Sie für jede von Ihnen ausgewählte Gruppe die folgenden Einstellungen aus:
    - **Typ**: Wählen Sie aus, ob die App **verfügbar** (Endbenutzer können die App aus dem Unternehmensportal aus installieren) oder **erforderlich** (Die App wird automatisch auf Endbenutzergeräten installiert) sein soll.
    - **Lizenztyp**: Wählen Sie zwischen **Benutzerlizenzierung** oder **Gerätelizenzierung**.
6.  Wählen Sie abschließend **Speichern** aus.


>[!NOTE]
>Dies angezeigte App-Liste ist mit einem Token verknüpft. Wenn Sie eine App haben, die mit mehreren VPP-Token verknüpft ist, wird die App mehrmals angezeigt: für jedes Token einmal.

## <a name="further-information"></a>Weitere Informationen

Zum Freigeben einer Lizenz müssen Sie die Zuweisungsaktion in „Deinstallieren“ ändern. Die Lizenz wird freigegeben, wenn die App deinstalliert wird. Wenn Sie eine App entfernen, die einem Benutzer zugewiesen wurde, versucht Intune, alle App-Lizenzen freizugeben, die diesem Benutzer zugeordnet wurden.

Wenn ein Benutzer mit einem geeigneten Gerät erstmals versucht, eine VPP-App auf einem Gerät zu installieren, wird er aufgefordert, am Volume Purchase Program (VPP) von Apple teilzunehmen. Die Teilnahme muss erfolgen, bevor die App-Installation fortgesetzt wird. Die Einladung, am Apple Volume Purchase Program teilzunehmen, erfordert, dass der Benutzer die iTunes-App auf dem iOS-Gerät verwenden kann. Wenn Sie eine Richtlinie aufgestellt haben, um die iTunes Store-App zu deaktivieren, funktioniert die benutzerbasierte Lizenzierung für VPP-Apps nicht. Die Lösung besteht darin, die iTunes-App durch Entfernen der Richtlinie zuzulassen oder die gerätebasierte Lizenzierung zu verwenden.



## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zum Überwachen von App-Zuweisungen finden Sie unter [Überwachen von Apps](apps-monitor.md).