---
title: Angeben von IMEI-Nummern | Microsoft Intune
description: "Mithilfe von Microsoft Intune können Administratoren IMEI-Nummern für mobile Geräteplattformen zur Identifizierung von unternehmenseigenen mobilen Geräten importieren."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9d44a6494bed0758b9768045bd204ea0eb481636
ms.openlocfilehash: 040413b59c81c20cf579660a83acebc494c0a1b9


---

# <a name="specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers"></a>Angeben unternehmenseigener Geräte über IMEI-Nummern (International Mobile Equipment Identity)
Mithilfe von Microsoft Intune können Administratoren jetzt für mobile Geräteplattformen die entsprechenden IMEI-Nummern (International Mobile Equipment Identity) importieren, indem sie IMEI-Nummern für die Unterstützung der Identifizierung von unternehmenseigenen mobilen Geräten verwenden. Nachdem Geräte bei Intune registriert wurden, werden Geräte mit importierten IMEI-Nummern unter **Gruppen** > **Übersicht** > **Alle Geräte** angezeigt. **Gerätegruppe** listet Geräte mit importierten IMEI-Nummern in der Spalte **Besitz** als **Unternehmen** auf.

1. Wechseln Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) zu **Gruppen** &gt; **Alle Geräte** &gt; **Vorab registrierte Unternehmensgeräte** &gt; **Nach IMEI (Alle Plattformen)**, und wählen Sie anschließend **Geräte hinzufügen** aus. Sie können Geräte auf zwei Arten hinzufügen:

    -   **Eine CSV-Datei mit Seriennummern hochladen**: Erstellen Sie eine durch Trennzeichen getrennte Liste (.csv) mit zwei Spalten ohne Header, und beschränken Sie die Liste auf 5.000 Geräte oder 5 MB pro CSV-Datei.

        |||
        |-|-|
        |&lt;IMEI 1&gt;|&lt;Details zu Gerät 1&gt;|
        |&lt;IMEI 2&gt;|&lt;Details zu Gerät 2&gt;|
        Diese CSV-Datei wird bei der Anzeige in einem Text-Editor folgendermaßen angezeigt:

        ```
        AABBBBBBCCCCCCD,PO 1234
        AABBBBBBCCCCCCE,PO 1234
        ```

    -   **Gerätedetails manuell hinzufügen**: Geben Sie die IMEI-Nummer und Gerätedetails von bis zu 15 Geräten ein.

   *Details* dienen administrativen Zwecken, damit Sie die IMEI-Nummer ermitteln können, die einem Gerät zugeordnet ist. Diese Informationen werden nicht an das Gerät gesendet, jedoch in der Intune-Konsole angezeigt.

2.   Klicken Sie auf **Weiter**.
3.  Im Bereich **Geräte überprüfen** können Sie die importierten IMEI-Nummern der Geräte bestätigen. Sie können zudem entscheiden, ob die **Details** für IMEI-Nummern, die erneut importiert werden, überschrieben werden sollen. Sie können das Kontrollkästchen **Überschreiben** deaktivieren, um die aktuellen Informationen zu erhalten. Klicken Sie auf **Fertig stellen**, um die IMEI-Nummern zu importieren.
4.  Die importierten IMEI-Nummern und Beschreibungen werden zur Liste **Nach IMEI (Alle Plattformen)** hinzugefügt.

Wenn ein Gerät mit einer IMEI-Nummer bei Intune registriert wird (in der Regel, wenn ein Benutzer die Unternehmensportal-App installiert und den Registrierungsvorgang abschließt), wird das Gerät als „unternehmenseigen“ gekennzeichnet und in der Gruppe **IMEI-Geräte** als registriert angezeigt.



<!--HONumber=Nov16_HO2-->


