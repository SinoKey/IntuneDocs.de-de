---
title: Anpassen des Unternehmensportals | Microsoft Intune
description: "Erläutert die Anpassung des Unternehmensportals für Ihr Intune-Abonnement."
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb4a9f01-f857-4563-ab6f-5d0d7dfa659d
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2a192c71b1b82f59b34ea614d09d895174f8112b
ms.openlocfilehash: b7288cff2e589faac32b9d2a80655079d9490590


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
    |Websitename|40|Dies ist der Anzeigename der URL für die Supportwebsite. Wenn Sie für die Supportwebsite eine URL, aber keinen Anzeigenamen angeben, wird im Unternehmensportal auf der Seite **An IT-Abteilung wenden** der Text **Zur IT-Website wechseln** angezeigt.|

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



<!--HONumber=Jul16_HO4-->


