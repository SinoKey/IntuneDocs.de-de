---
title: "Verwalten von über ein Volumenprogramm erworbenen iOS-Apps | Microsoft Intune"
description: "Verwenden Sie Intune, um Apps zu verwalten, die Sie über ein Volumenprogramm von Apple erworben haben. Dazu importieren Sie die Lizenzinformationen aus dem App-Store, verfolgen nach, wie viele Lizenzen verwendet wurden, und verhindern, dass mehr App-Kopien installiert werden, als Sie erworben haben."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 10/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 611cfb0176a922234c29642c305dd03699922c5f
ms.openlocfilehash: 5981a2e147c89776d304226250170ec4114e35d8


---

# Verwalten von iOS-Apps, die über ein Volumenprogramm mit Microsoft Intune erworben wurden
Der iOS-App-Store bietet die Möglichkeit, mehrere Lizenzen für eine App zu erwerben, die in Ihrem Unternehmen ausgeführt werden soll. Dadurch können Sie den Verwaltungsaufwand reduzieren, der durch das Nachverfolgen mehrerer erworbener App-Kopien entsteht.

Microsoft Intune unterstützt Sie bei der Verwaltung von Apps, die über ein solches Programm erworben wurden. Dazu importieren Sie die Lizenzinformationen aus dem App-Store, verfolgen nach, wie viele Lizenzen verwendet wurden, und verhindern, dass mehr App-Kopien installiert werden, als Sie erworben haben.

> [!Important]
> Derzeit weist Intune App-Lizenzen des Programms für Volumenlizenzen für Unternehmen (Volume Purchase Program for Business, VPP) Benutzern und nicht Geräten zu. Aus diesem Grund müssen Benutzer zum Installieren der App ihr Apple-ID-Kennwort eingeben.
> Das Apple Volume Purchase Program für Bildungseinrichtungen wird in dieser Version nicht unterstützt.

## Verwalten von Apps für iOS-Geräte, die über ein Volumenprogramm erworben wurden
Sie erwerben mehrere Lizenzen für iOS-Apps über das [Programm für Volumenlizenzen für Unternehmen (Volume Purchase Program, VPP) von Apple](http://www.apple.com/business/vpp/). Dies umfasst das Einrichten eines Apple VPP-Kontos auf der Apple-Website und das Hochladen des Apple VPP-Tokens in Intune.  Anschließend können Sie Ihre Informationen zum Volumenerwerb mit Intune synchronisieren und die Verwendung der im Rahmen des Volumenprogramms erworbenen App verfolgen.

## Vorbereitung
Bevor Sie beginnen, müssen Sie ein VPP-Token von Apple abrufen und es in Ihr Intune-Konto hochladen. Beachten Sie darüber hinaus die folgenden Informationen:

* Jede Organisation kann nur über ein VPP-Konto und -Token verfügen.
* Nachdem Sie Intune ein Apple VPP-Konto zugeordnet haben, können Sie später kein anderes Konto zuordnen. Aus diesem Grund ist es sehr wichtig, dass mehreren Personen die Details des verwendeten Kontos bekannt sind.
* Wenn Sie zuvor ein VPP-Token für ein anderes Produkt verwendet haben, müssen Sie für die Verwendung mit Intune ein neues erstellen.
* Jedes Token ist ein Jahr lang gültig.
* Standardmäßig wird Intune zweimal täglich mit dem Apple VPP-Dienst synchronisiert. Eine manuelle Synchronisierung können Sie jederzeit starten.
* Nachdem Sie den VPP-Token in Intune importiert haben, importieren Sie denselben Token in keine andere Geräteverwaltungslösung. Andernfalls kann dies zu einem Verlust von Lizenzzuweisung und Benutzerdatensätzen führen.
* Bevor Sie iOS VPP mit Intune verwenden, entfernen Sie alle vorhandenen, mit anderen Anbietern für das Mobile-Geräte-Management (MDM) erstellten VPP-Benutzerkonten. Aus Sicherheitsgründen werden diese Benutzerkonten in Intune nicht synchronisiert. Intune synchronisiert nur Daten aus dem Apple VPP-Dienst, der von Intune erstellt wurde.
* Sie können keine iOS-VPP-Apps für Geräte bereitstellen, die mithilfe des Geräteregistrierungsprotokolls (Device Enrollment Protocol, DEP) registriert wurden.

## So können Sie einen Apple VPP-Token abrufen und hochladen

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) **Verwaltung** &gt; **iOS und Mac OS X** &gt; **Volume Purchase Program**.

2.  Klicken Sie auf den Link **Apple VPP-Konto**. Melden Sie sich für das Programm für Volumenlizenzen für Unternehmen (Volume Purchase Program, VPP) an, falls noch nicht erfolgt. Sobald Sie registriert sind, laden Sie das Apple VPP-Token für Ihr Konto herunter.

3.  Wählen Sie auf der Seite **Apple Volume Purchase Program (VPP) verwalten** in der Intune-Konsole die Option **VPP-Token hochladen**.

4.  Geben oder fügen Sie im Dialogfeld **VPP-Token hochladen** den VPP-Token-Namen und Ihre Apple-ID ein, und wählen Sie dann **Hochladen** aus.

5.  Aktivieren Sie im Dialogfeld mit der Warnung das Kontrollkästchen, um anzugeben, dass Sie wissen, dass Sie später nicht zu einem anderen VPP-Konto wechseln können, und wählen Sie dann **Ja** aus.

Auf der Seite **Volume Purchase Program** werden nun Informationen zum Apple VPP-Token angezeigt, einschließlich der letzten Aktualisierung, des Ablaufdatums und der letzten Synchronisierung mit Intune.

Sie können die von Apple gespeicherten Daten jederzeit mit Intune synchronisieren, indem Sie **Jetzt synchronisieren** wählen.

## So stellen Sie per Volumenlizenz erworbene Apps bereit

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Optionen **Apps** &gt; **Verwaltete Software** &gt; **Per Volumenlizenz erworbene Apps**. Diese Liste zeigt alle Apps, die mit dem Apple VPP-Dienst synchronisiert wurden.

2.  Wählen Sie die bereitzustellende App und dann **Bereitstellung verwalten** aus. Befolgen Sie anschließend die Anweisungen zum Hochladen, Erstellen und Bereitstellen der App im Thema [Bereitstellen von Apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md).

> [!TIP]
> Sie müssen eine Bereitstellungsaktion vom Typ **Erforderlich** auswählen. „Verfügbare“ Installationen werden derzeit nicht unterstützt.

Wenn Sie die Anwendung als **erforderliche** Installation bereitstellen, verwendet jeder Benutzer, der die App installiert, eine Lizenz.

Zum Freigeben einer Lizenz müssen Sie die Bereitstellungsaktion in **Deinstallieren** ändern. Die Lizenz wird freigegeben, wenn die App deinstalliert wird.

Wenn ein Benutzer mit einem geeigneten Gerät erstmals versucht, eine VPP-App zu installieren, wird er aufgefordert, am Programm für Volumenlizenzen (Volume Purchase Program, VPP) von Apple teilzunehmen. Die Teilnahme muss erfolgen, bevor die App-Installation fortgesetzt wird.

> [!TIP]
> In der Spalte **VPP – Nutzungsbedingungen – Status** wird der Annahmestatus für jeden Benutzer angezeigt, dem die App bereitgestellt wurde.

Wenn keine weiteren Lizenzen verfügbar sind, schlägt die Bereitstellung fehl.

## So überwachen Sie Apple VPP-Apps
Sie können überwachen, welche VPP-Apps bereitgestellt wurden und wie viele Lizenzen vom Arbeitsbereich **Apps** auf dem Knoten **Verwaltete Software** &gt; **Per Volumenlizenz erworbene Apps** verwendet werden.

> [!TIP]
> Sie können auch App-**Filter** verwenden, um den Status der einzelnen App-Installationen zu überprüfen.

### Weitere Informationen:
[Bereitstellen von Apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md)



<!--HONumber=Oct16_HO1-->


