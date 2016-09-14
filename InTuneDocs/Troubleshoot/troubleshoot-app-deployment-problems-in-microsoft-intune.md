---
title: Behandlung von Problemen mit der App-Bereitstellung | Microsoft Intune
description: "Diese Themen helfen Ihnen, Probleme mit der App-Bereitstellung mit Microsoft Intune zu lösen."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 28ac298e-fb73-4c1c-b3fd-8336639e05e6
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: aa96cf3a1909e3ea2187a3beb0aede3228894504
ms.openlocfilehash: 9f4b91bd523c82665bcac54902b2e8cc9c72ef75


---

# Behandlung von Problemen mit der App-Bereitstellung in Microsoft Intune
Wenn beim Bereitstellen und Verwalten von Apps mit Intune Probleme auftreten, beginnen Sie hier. In diesem Thema werden einige allgemeine Probleme, die auftreten können, sowie deren Lösungen behandelt.

## Häufige Probleme bei der App-Bereitstellung

### Im Unternehmensportal fehlen die Kontaktinformationen der IT-Abteilung

1.  Klicken Sie in der Intune-Verwaltungskonsole auf **Verwaltung** &gt; **Unternehmensportal**.

2.  Legen Sie die Details unter **An IT-Abteilung wenden** fest.

### In der Liste werden bestimmte Apps nicht angezeigt

1.  Stellen Sie sicher, dass Sie die App-Liste für einen Benutzer oder ein Gerät prüfen, auf dem die App bereitgestellt wurde.

2.  Stellen Sie sicher, dass das Gerät die Anforderungen für die App erfüllt.

### Beim Herunterladen einer App erhalten Sie eine Fehlermeldung

1.  Stellen Sie sicher, dass nicht mehrere gleichzeitige Downloads pro Benutzer stattfinden. Jeder Benutzer kann gleichzeitig eine einzelne App herunterladen.

2.  Stellen Sie sicher, dass nicht zu viele gleichzeitige Downloads pro Konto stattfinden. Warten Sie einige Minuten, und versuchen Sie es erneut.

3.  Wenn Sie eine Meldung von iOS erhalten, dass die Installation nicht möglich ist oder abgebrochen wurde oder Sie den Vorgang wiederholen müssen, liegt möglicherweise eine starke Auslastung vor. Warten Sie einige Minuten, und versuchen Sie es erneut.

4.  Wenn die Statusanzeige für das Herunterladen von Apps in iOS vollständig ist, aber die App nicht ordnungsgemäß installiert wird, liegt möglicherweise ein Fehler bei den bereitgestellten App-Dateien vor.


### Der Upload Ihrer App bleibt im Zustand "Läuft" stehen

1.  Wenn eine App hochgeladen wird, werden zunächst die Metadaten und dann das App-Paket hinzugefügt. Nach dem Hochladen der Metadaten läuft die App scheinbar. Wenn Sie feststellen, dass der Upload Ihrer App ungewöhnlich lange im Zustand „Läuft“ verbleibt, löschen Sie die App, und laden Sie sie erneut hoch.

2.  Achten Sie darauf, die Bereitstellung der App nicht zu verwalten, solange sie sich im Zustand „Läuft“ befindet.

### Bei der Installation einer iOS-App tritt ein Fehler auf

1.  Stellen Sie sicher, dass der Zugriff auf die Apple-Bereitstellungs- und -Zertifizierungswebsites durch die Firewall Ihrer Organisation zugelassen wird.

2.  Weitere Informationen finden Sie in der Apple-Entwicklerdokumentation.

### Wenn der Installationsstatus von verwalteten Anwendungen nicht gemeldet wird

Bei verwalteten App-Installationen wurden vor dem Microsoft Intune-Dienstupdate im November 2014 keine Informationen zum Installationsstatus erfasst. Bei Geräten, auf denen vor diesem Dienstupdate verwaltete Apps installiert wurden, muss jede App-Bereitstellung mit der geeigneten Bereitstellungsaktion aktualisiert werden (z. B. **Verfügbare Installation**). Jedes Gerät wird die App während die automatische Prüfung auf verfügbare Apps aktualisieren. Weitere Informationen finden Sie unter [Update apps using Microsoft Intune](/intune/deploy-use/update-apps-using-microsoft-intune) (Aktualisieren von Apps mit Microsoft Intune).

## <a name="BKMK_SoftDistErrorCodes"></a>Fehlercodes von App-Bereitstellungsfehlern
Die folgende Tabelle enthält eine Übersicht über Fehler, die bei der Intune-App-Bereitstellung häufig auftreten, die wahrscheinlichen Fehlerursachen und mögliche Lösungen.

|Fehlercode|Mögliches Problem|Lösungsvorschlag|
|--------------|--------------------|------------------------|
|0x80073CFF<br /><br />0x80CF201C (Clientfehler)|Zur Installation der Anwendung müssen Sie über ein zum Querladen fähiges System verfügen.|Stellen Sie sicher, dass das App-Paket mit einer vertrauenswürdigen Signatur signiert und auf auf einem zur Domäne gehörenden Gerät mit aktivierter Richtlinie "AllowAllTrustedApps" oder auf einem Gerät mit Windows Sideloading-Lizenz und aktivierter Richtlinie "AllowAllTrustedApps" (wird bei Registrierung eines Windows RT-Geräts angewendet) installiert ist.|
|0x80073CF0|Das Paket konnte nicht geöffnet werden.|Mögliche Ursachen:<br /><br />-   Das Paket ist nicht signiert.<br />-   Der Namen des Herausgebers stimmt nicht mit dem Signaturzertifikat des Antragstellers überein.<br /><br />Prüfen Sie das Ereignisprotokoll „AppxPackagingOM“, um weitere Informationen zu erhalten.|
|0x80073CF3|Fehler bei Updates des Pakets (Abhängigkeits- oder Konfliktüberprüfung)|Mögliche Ursachen:<br /><br />-   Das eingehende Paket ist mit einem installierten Paket nicht vereinbar.<br />-   Eine angegebene Paketabhängigkeit wurde nicht gefunden.<br />-   Das Paket unterstützt nicht die richtige Prozessorarchitektur.<br /><br />Prüfen Sie das Ereignisprotokoll „AppXDeployment-Server“, um weitere Informationen zu erhalten.|
|0x80073CFB|Das bereitgestellte Paket ist bereits installiert, und eine erneute Installation des Pakets wird blockiert.|Dieser Fehler kann auftreten, wenn Sie ein Paket installieren, das nicht bitweise mit dem bereits installierten Paket identisch ist. Überprüfen Sie, ob die digitale Signatur auch Teil des Pakets ist. Wenn ein Paket erneut erstellt oder signiert wird, ist das Paket nicht mehr bitweise identisch mit dem zuvor installierten Paket. Es gibt zwei Möglichkeiten, diesen Fehler zu beheben:<br /><br />-   Erhöhen Sie die Versionsnummer der Anwendung, und erstellen und signieren Sie das Paket dann erneut.<br />-   Entfernen Sie das alte Paket für jeden Benutzer des Systems, bevor Sie das neue Paket installieren.|
|0x87D1041C|Die Anwendung wurde erfolgreich installiert, wird jedoch nicht erkannt.|– Die App wurde erfolgreich von Intune bereitgestellt und später deinstalliert (möglicherweise vom Endbenutzer). Weisen Sie den Benutzer an, die App aus dem Unternehmensportal neu zu installieren. Erforderliche Apps werden automatisch beim nächsten Einchecken des Geräts neu installiert.|

### Nächste Schritte
Wenn diese Informationen zur Problembehandlung für Sie nicht hilfreich waren, wenden Sie sich wie in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Anfordern von Support für Microsoft Intune) beschrieben an den Microsoft Support.



<!--HONumber=Aug16_HO5-->


