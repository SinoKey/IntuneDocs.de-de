---
title: "Angeben unternehmenseigener Geräte über IMEI-Nummern (International Mobile Equipment Identity) | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
ms.reviewer: jeffgilb
ms.suite: ems
ms.sourcegitcommit: 398d93d4e2317d00a2f9d5f89966aaec3b942504
ms.openlocfilehash: af4b87eb8082ee5ff11cd2d42b788ad17b334bcb


---

# Angeben unternehmenseigener Geräte über IMEI-Nummern (International Mobile Equipment Identity)
Mithilfe von Microsoft Intune können Administratoren jetzt für mobile Geräteplattformen, die über eine IMEI-Nummer verfügen, die entsprechenden IMEI-Nummern (International Mobile Equipment Identity) importieren, um die Identifizierung von unternehmenseigenen mobilen Geräten zu unterstützen. Nach der Registrierung bei Intune können Geräte mit importierten IMEI-Nummern unter **Gruppen** > **Übersicht** > **Alle Geräte** > **Vorab registrierte Unternehmensgeräte** > **Nach IMEI (alle Plattformen)** angezeigt werden.

1. Wechseln Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) zu **Gruppen** &gt; **Alle Geräte** &gt; **Vorab registrierte Unternehmensgeräte** &gt; **Nach IMEI (Alle Plattformen)**, und klicken Sie dann auf **Geräte hinzufügen**. Sie können Geräte auf zwei Arten hinzufügen:

    -   **Eine CSV-Datei mit Seriennummern hochladen**: Erstellen Sie eine durch Trennzeichen getrennte Liste (.csv) mit zwei Spalten ohne Überschrift, die auf 5000 Geräte oder 5 MB pro CSV-Datei beschränkt ist.

        |||
        |-|-|
        |&lt;IMEI 1&gt;|&lt;Details zu Gerät1&gt;|
        |&lt;IMEI 2&gt;|&lt;Details zu Gerät2&gt;|
        Diese CSV-Datei wird bei der Anzeige in einem Text-Editor folgendermaßen angezeigt:

        ```
        AABBBBBBCCCCCCD,PO 1234
        AABBBBBBCCCCCCE,PO 1234
        ```

    -   **Gerätedetails manuell hinzufügen**: Geben Sie die IMEI-Nummer und Gerätedetails von bis zu fünf Geräten ein.

   *Details* sind für administrative Zwecke, damit Sie erkennen können, welche IMEI-Nummer einem Gerät zugeordnet ist. Diese Informationen werden nicht an das Gerät gesendet, sondern in der Intune-Konsole angezeigt.

2.   Klicken Sie auf **Weiter**.
3.  Im Bereich **Geräte überprüfen** können Sie bestätigen, welche IMEI-Nummern der Geräte importiert werden. Sie können zudem entscheiden, ob die **Details** für IMEI-Nummern überschrieben werden sollen, die erneut importiert werden. Sie können das Kontrollkästchen **Überschreiben** deaktivieren, um die aktuellen Informationen zu erhalten. Klicken Sie auf **Fertig stellen**, um die IMEI-Nummern zu importieren.
4.  Die hinzugefügten IMEI-Nummern und Beschreibungen werden zur Liste **Nach IMEI (Alle Plattformen)** hinzugefügt.

Wenn das Gerät mit dieser IMEI-Nummer registriert wird (in der Regel, wenn ein Benutzer die Unternehmensportal-App installiert und den Registrierungsvorgang abschließt), wird das Gerät als „unternehmenseigen“ gekennzeichnet und in der Gruppe **IMEI-Geräte** als registriert angezeigt.



<!--HONumber=Jun16_HO3-->


