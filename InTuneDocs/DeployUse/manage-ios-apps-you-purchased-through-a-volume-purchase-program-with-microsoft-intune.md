---
# required metadata

title: Verwalten von iOS-Apps, die über ein Volumenprogramm erworben wurden | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Verwalten von iOS-Apps, die über ein Volumenprogramm mit Microsoft Intune erworben wurden
Einige App-Stores bieten die Möglichkeit, mehrere Lizenzen für eine App zu erwerben, die in Ihrem Unternehmen ausgeführt werden soll. Dadurch können Sie den Verwaltungsaufwand reduzieren, der durch das Nachverfolgen mehrerer erworbener App-Kopien entsteht.

Microsoft Intune unterstützt Sie bei der Verwaltung von Apps, die über ein solches Programm erworben wurden. Dazu werden die Lizenzinformationen aus dem App-Store importiert, es wird nachverfolgt, wie viele Lizenzen verwendet wurden, und es wird verhindert, dass mehr als die erworbene Anzahl von Kopien der App installiert werden.

> [!Important]
> Derzeit weist Intune iOS VPP-App-Lizenzen Benutzern und nicht Geräten zu. Aus diesem Grund müssen Endbenutzer zum Installieren der App ihr Apple-ID-Kennwort eingeben.

## Verwalten von Apps für iOS-Geräte, die über ein Volumenprogramm erworben wurden
Sie erwerben mehrere Lizenzen für iOS-Apps über das [Programm für Volumenlizenzen für Unternehmen (Volume Purchase Program, VPP) von Apple](http://www.apple.com/business/vpp/). Dies umfasst das Einrichten eines Apple VPP-Kontos auf der Apple-Website und des Apple VPP-Tokens in Intune.  Anschließend können Sie Ihre Informationen zum Volumenerwerb mit Intune synchronisieren und die Verwendung der im Rahmen des Volumenprogramms erworbenen App verfolgen.

## Vorbereitung
Bevor Sie beginnen, müssen Sie ein VPP-Token von Apple abrufen und es in Ihr Intune-Konto hochladen. Beachten Sie darüber hinaus die folgenden Informationen:

* Jede Organisation kann nur über ein VPP-Konto und -Token verfügen.
* Sobald Sie Intune ein Apple VPP-Konto zugeordnet haben, können Sie anschließend kein anderes Konto zuordnen. Aus diesem Grund ist es sehr wichtig, dass mehreren Personen die Details des verwendeten Kontos bekannt sind.
* Wenn Sie zuvor ein VPP-Token für ein anderes Produkt verwendet haben, müssen Sie für die Verwendung mit Intune ein neues erstellen.
* Jedes Token ist ein Jahr lang gültig.
* Standardmäßig wird Intune zweimal täglich mit dem Apple VPP-Dienst synchronisiert. Sie können jedoch jederzeit eine manuelle Synchronisierung einleiten.
* Nachdem Sie den VPP-Token in Intune importiert haben, importieren Sie denselben Token in keine andere Geräteverwaltungslösung. Andernfalls kann dies zu einem Verlust von Lizenzzuweisung und Benutzerdatensätzen führen.
* Bevor Sie iOS VPP mit Intune verwenden, entfernen Sie alle vorhandenen, mit anderen MDM-Anbietern erstellten VPP-Benutzerkonten. Aus Sicherheitsgründen werden diese Benutzerkonten in Intune nicht synchronisiert. Intune synchronisiert nur Daten aus dem Apple VPP-Dienst, der von Intune erstellt wurde. 

## So können Sie einen Apple VPP-Token abrufen und hochladen

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) auf **Verwaltung** &gt; **iOS und Mac OS X** &gt; **Volume Purchase Program**.

2.  Klicken Sie auf den **Apple VPP-Konto**-Link, und melden Sie sich für das Programm für Volumenlizenzen für Unternehmen (Volume Purchase Program, VPP) an, falls noch nicht erfolgt. Sobald Sie registriert sind, laden Sie das Apple VPP-Token für Ihr Konto herunter.

3.  Klicken Sie auf der Seite **Apple Volume Purchase Program (VPP) verwalten** in der Intune-Konsole auf **VPP-Token hochladen**.

4.  Geben oder fügen Sie im Dialogfeld **VPP-Token hochladen** den VPP-Token-Namen und Ihre Apple-ID ein, und klicken Sie dann auf **Hochladen**.

5.  Klicken Sie im Dialogfeld mit der Warnung auf das Kontrollkästchen, um anzugeben, dass Sie wissen, dass Sie später nicht zu einem anderen VPP-Konto wechseln können, und klicken Sie dann auf **Ja**.

Auf der Seite **Volume Purchase Program** werden nun Informationen zum Apple VPP-Token angezeigt, einschließlich der letzten Aktualisierung, des Ablaufdatums und der letzten Synchronisierung mit Intune.

Sie können die von Apple gespeicherten Daten jederzeit mit Intune synchronisieren, indem Sie auf **Jetzt synchronisieren** klicken.

## So stellen Sie per Volumenlizenz erworbene Apps bereit

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) auf **Apps** &gt; **Verwaltete Software** &gt; **Per Volumenlizenz erworbene Apps**. Diese Liste zeigt alle Apps, die mit dem Apple VPP-Dienst synchronisiert wurden.

2.  Wählen Sie die bereitzustellende App aus, und klicken Sie anschließend auf **Bereitstellung verwalten**. Befolgen Sie anschließend die Anweisungen im Thema [Bereitstellen von Apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md) zum Hochladen, Erstellen und Bereitstellen der App.

Wenn Sie die Anwendung als **erforderliche** Installation bereitstellen, wird eine Lizenz von jedem Benutzer verwendet, der die App installiert.

Zum Freigeben einer Lizenz müssen Sie die Bereitstellungsaktion in **Deinstallieren** ändern. Die Lizenz wird freigegeben, sobald die App deinstalliert ist.

Wenn ein Benutzer mit einem geeigneten Gerät erstmals versucht, eine VPP-App zu installieren, wird er aufgefordert, am Programm für Volumenlizenzen (Volume Purchase Program, VPP) von Apple teilzunehmen. Die Teilnahme muss erfolgen, bevor die App-Installation fortgesetzt wird.

> [!TIP] In der Spalte **VPP – Nutzungsbedingungen – Status** wird der Annahmestatus für jeden Benutzer angezeigt, dem die App bereitgestellt wurde.

Wenn keine weiteren Lizenzen verfügbar sind, schlägt die Bereitstellung fehl.

## So überwachen Sie Apple VPP-Apps
Sie können überwachen, welche VPP-Apps bereitgestellt wurden und wie viele Lizenzen vom Arbeitsbereich **Apps** auf dem Knoten **Verwaltete Software** &gt; **Per Volumenlizenz erworbene Apps** verwendet werden.

> [!TIP] Sie können auch **Filter** für Apps verwenden, um den Status der einzelnen App-Installationen zu überprüfen.

### Siehe auch
[Bereitstellen von Apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md)



<!--HONumber=May16_HO4-->


