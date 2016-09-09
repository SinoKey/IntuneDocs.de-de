---
title: Anpassen des Unternehmensportals | Microsoft Intune
description: "Erläutert die Anpassung des Unternehmensportals für Ihr Intune-Abonnement."
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb4a9f01-f857-4563-ab6f-5d0d7dfa659d
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0c1e08cc49d75303f6793894e3c8a040f6e7a8b1
ms.openlocfilehash: 1578ebcc6d4d01a6e9bee2f40cfcc07b3ae54cb2


---


# Anpassen des Unternehmensportals
Im [!INCLUDE[wit_iwportal_1](../includes/wit_iwportal_1_md.md)] können Benutzer auf Unternehmensdaten zugreifen, häufige Aufgaben wie das Registrieren von Geräten und das Installieren von Apps ausführen und sich über Unterstützungsmöglichkeiten durch Ihre IT-Abteilung informieren.

> [!TIP]
> Wenn Sie das Unternehmensportal anpassen, gelten die Konfigurationen sowohl für die Unternehmensportalwebsite als auch für die Unternehmensportal-Apps.

Durch Anpassen des Unternehmensportals können Sie Ihren Endbenutzern eine vertraute und sinnvolle Benutzeroberfläche bereitstellen. Melden Sie sich zu diesem Zweck einfach als Mandanten- oder Dienstadministrator bei der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) an, wählen Sie **Verwaltung** &gt; **Unternehmensportal** aus, und konfigurieren Sie die Einstellungen für das Unternehmensportal.

![admin-console-admin-workspace-comp-portal-settings](./media/companyportal.png)

## Kontaktdaten und Datenschutzerklärung des Unternehmens
Der Unternehmensname wird als Titel des Unternehmensportals angezeigt. Die Kontaktinformationen werden Benutzern im Unternehmensportal auf dem Bildschirm für die Kontaktaufnahme mit der IT-Abteilung angezeigt. Die Datenschutzerklärung wird angezeigt, wenn ein Benutzer auf den Datenschutzlink klickt.

|Feldname|Max. Länge|Weitere Informationen|
    |----------|------------------------|----------------|
    |Firmenname|40|Dieser Name wird als Titel des Unternehmensportals angezeigt.|
    |Kontaktname für IT-Abteilung|40|Dieser Name wird auf der Seite **An IT-Abteilung wenden** angezeigt.|
    |Telefonnummer der IT-Abteilung|20|Diese Telefonnummer wird auf der Seite **An IT-Abteilung wenden** angezeigt.|
    |E-Mail-Adresse der IT-Abteilung|40|Diese Kontaktadresse wird auf der Seite **An IT-Abteilung** wenden angezeigt. Sie müssen eine gültige E-Mail-Adresse im Format **Alias@Domänenname.com** eingeben.|
    |Weitere Informationen|120|Dies wird auf der Seite **An IT-Abteilung wenden** angezeigt.|
    |URL der Datenschutzrichtlinie des Unternehmens|79|Sie können eine eigene Datenschutzerklärung für Ihr Unternehmen angeben. Diese wird angezeigt, wenn die Benutzer im Unternehmensportal auf die Datenschutzlinks klicken. Sie müssen eine gültige URL im Format https://www.contoso.com eingeben.|

## Supportkontakte
Die Supportwebsite wird Benutzern im Unternehmensportal angezeigt, um ihnen Zugriff auf Onlinesupport zu ermöglichen.

|Feldname|Max. Länge|Weitere Informationen|
    |----------|------------------------|----------------|
    |URL der Supportwebsite|150|Wenn Sie über eine Supportwebsite verfügen, die Ihre Benutzer verwenden sollen, geben Sie hier die URL an. Die URL muss das Format https://www.contoso.com aufweisen. Wenn Sie keine URL angeben, wird im Unternehmensportal auf der Seite **An IT-Abteilung wenden** keine Supportwebsite angezeigt.|
    |Name der Website|40|Dies ist der Anzeigename der URL für die Supportwebsite. Wenn Sie für die Supportwebsite eine URL, aber keinen Anzeigenamen angeben, wird im Unternehmensportal auf der Seite **An IT-Abteilung wenden** der Text **Zur IT-Website wechseln** angezeigt.|

## Anpassen des Unternehmensbrandings
Sie können Ihr Unternehmensportal mit Ihrem Firmenlogo, Firmennamen, Farbdesign und Hintergrund anpassen.

|Feldname|Weitere Informationen|
    |----------|----------------|
    |Farbdesign|Wählen Sie ein Farbdesign aus, das auf das Unternehmensportal angewendet werden soll.|
    |Firmenlogo einschließen|Wenn Sie diese Option aktivieren, können Sie Ihr Firmenlogo hochladen. Dieses wird dann im Unternehmensportal angezeigt. Sie können zwei Logos hochladen: ein Logo, das angezeigt wird, wenn der Hintergrund des Unternehmensportals weiß ist, und eines, das angezeigt wird, wenn für den Hintergrund des Unternehmensportals das von Ihnen ausgewählte Farbdesign verwendet wird. Die Logodateien müssen PNG- oder JPG-Dateien sein. Ihre Auflösung darf maximal 400 x 100 Pixel betragen, und die Größe darf 750 KB nicht überschreiten.|
    |Hintergrund für die [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)]-Unternehmensportal- App auswählen|Diese Einstellung betrifft nur den Hintergrund der Unternehmensportal-App für [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)].|


Nach dem Speichern Ihrer Änderungen können Sie über die Links, die am unteren Rand der Seite **Unternehmensportal** in der Verwaltungskonsole angegeben sind, die Unternehmensportalwebsite anzeigen. Diese Links können nicht geändert werden. Wenn ein Benutzer sich anmeldet, werden über diese Links Ihre Abonnements im Unternehmensportal angezeigt.

### Nächste Schritte
Gratulation! Sie haben Schritt 7 der Kurzanleitung *Erste Schritte mit Intune* abgeschlossen.
>[!div class="step-by-step"]

>[&larr; **Erstellen von Richtlinien und Apps**](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)       [**Registrieren von Geräten** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)  



<!--HONumber=Aug16_HO5-->


