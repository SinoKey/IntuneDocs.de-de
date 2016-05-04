---
title: Angeben firmeneigener Geräte über IMEI-Nummern (International Mobile Equipment Identity)
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
author: NathBarn
---
# Angeben firmeneigener Geräte über IMEI-Nummern (International Mobile Equipment Identity)
Mithilfe von Microsoft Intune können Administratoren jetzt für mobile Geräteplattformen, die über eine IMEI-Nummer verfügen, die entsprechenden IMEI-Nummern (International Mobile Equipment Identity) importieren, um die Identifizierung von firmeneigenen mobilen Geräten zu unterstützen. Nach der Registrierung in Intune werden Geräte mit importierten IMEI-Nummern als firmeneigene Geräte gekennzeichnet, die zum Anwenden von Richtlinien verwendet werden können, die sich von denen unterscheiden, die auf Geräte angewendet werden, die sich im privaten Besitz befinden.
## Hinzufügen von IMEI-Nummern (International Mobile Equipment Identity) zu Intune
1. Wechseln Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) zu **Gruppen** &gt; **Alle Geräte** &gt; **Vorab registrierte Unternehmensgeräte** &gt; **Nach IMEI (Alle Plattformen)**, und klicken Sie dann auf **Geräte hinzufügen**. Sie können Geräte auf zwei Arten hinzufügen:

    -   **Eine CSV-Datei mit Seriennummern hochladen**: Erstellen Sie eine durch Trennzeichen getrennte Liste (.csv) mit zwei Spalten ohne Überschrift, die auf 5000 Geräte oder 5 MB pro CSV-Datei beschränkt ist.

        |||
        |-|-|
        |&lt;IMEI #1&gt;|&lt;Details zu Gerät1&gt;|
        |&lt;IMEI #2&gt;|&lt;Gerät2 – Details&gt;|
        Diese CSV-Datei wird bei der Anzeige in einem Text-Editor folgendermaßen angezeigt:

        ```
        AA-BBBBBB-CCCCCC-D,PO 1234
        AA-BBBBBB-CCCCCC-E,PO 1234
        ```

    -   **Gerätedetails manuell hinzufügen**: Geben Sie die IMEI-Nummer und Gerätedetails von bis zu fünf Geräten ein.

   *Details* sind für administrative Zwecke, damit Sie erkennen können, welche IMEI-Nummer einem Gerät zugeordnet ist. Diese Informationen werden nicht an das Gerät gesendet, sondern in der Intune-Konsole angezeigt. 

2.   Klicken Sie auf **Weiter**.
3.  Im Bereich **Geräte überprüfen** können Sie bestätigen, welche IMEI-Nummern der Geräte importiert werden. Sie können zudem entscheiden, ob die **Details** für IMEI-Nummern überschrieben werden sollen, die erneut importiert werden. Sie können das Kontrollkästchen **Überschreiben** deaktivieren, um die aktuellen Informationen zu erhalten. Klicken Sie auf **Fertig stellen**, um die IMEI-Nummern zu importieren.
4.  Die hinzugefügten IMEI-Nummern und Beschreibungen werden zur Liste **Nach IMEI (Alle Plattformen)** hinzugefügt. 

Wenn das Gerät mit dieser IMEI-Nummer registriert wird (in der Regel, wenn ein Benutzer die Unternehmensportal-App installiert und den Registrierungsvorgang abschließt), wird das Gerät als „firmeneigen“ gekennzeichnet und in der Gruppe **IMEI-Geräte** als registriert angezeigt.



<!--HONumber=Apr16_HO4-->


