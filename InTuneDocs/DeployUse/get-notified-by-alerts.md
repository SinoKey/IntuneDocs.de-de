---
title: Benachrichtigungen und Warnungen | Microsoft Intune
description: "Erfahren Sie, wie Sie mit Warnungen über Ereignisse in Microsoft Intune auf dem Laufenden bleiben."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 396ea714-0433-4bd5-a934-8d0b477f28e4
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: 59c5cf28a7be2d1b4b9071dd889803e18f31f83b


---

# Benachrichtigungen durch Microsoft Intune-Warnungen
Warnungen halten Sie über Ereignisse in Microsoft Intune auf dem Laufenden.

Warnungen können Sie z. B. bei den folgenden Ereignissen benachrichtigen:

-   Ein Problem mit dem Exchange-Connector beeinflusst die Verwaltung mobiler Geräte.

-   Auf einem Computer wurde Malware gefunden.

-   Ein Konflikt zwischen zwei Intune-Richtlinien wurde erkannt.


## Funktionsweise von Warnungen
Warnungen werden auf der Grundlage von **Warnungstypen**generiert, einem Satz von vorkonfigurierten, in Intune integrierten Regeln. Der Warnungstyp **Im Cloudspeicher ist nur noch weniger als 10 % freier Speicherplatz vorhanden** warnt Sie beispielsweise, wenn Sie der Speicherplatz zum Speichern von Apps in der Cloud zur Neige geht. Sie können jeden Warnungstyp aktivieren oder deaktivieren und die Eigenschaften konfigurieren. Wenn Sie den oben genannten Warnungstyp verwenden, können Sie z. B. folgende Eigenschaften konfigurieren:

-   **Status:** Legt fest, ob der Warnungstyp aktiviert oder deaktiviert ist.

-   **Schweregrad:** Wie schwerwiegend ist diese Warnung?


|Schweregrad|Details|
|--------|-------|
    |![Kritische Warnung](../media/Critical-Alert.jpg)|Weist auf ein schwerwiegendes Problem hin, das Sie so bald wie möglich untersuchen sollten, z. B., wenn Schadsoftware auf einem Computer erkannt wurde.|
    |![Warnung](../media/Warning-Alert.jpg)|Weist auf ein Problem hin, das aktuell nicht kritisch ist, aber möglicherweise ernsthaft werden kann, wenn Sie sich nicht darum kümmern, z. B., wenn Sicherheitsupdates zum Installieren vorhanden sind.|
    |![Informationsmeldung](../media/Informational-Alert.jpg)|Weist auf Informationen hin, die für den Betrieb unkritisch sind, z. B., wenn eine neue Version von Exchange Connector verfügbar ist.|

Andere Warnungstypen können verschiedene, konfigurierbare Elemente enthalten, z. B. den Prozentsatz der Geräte, die durch ein Problem betroffen sein müssen, bevor eine Warnung generiert wird.

**Wenn die Kriterien eines Warnungstyps erfüllt sind, wird eine Warnung generiert und in der Intune-Verwaltungskonsole angezeigt.**

Darüber hinaus können Sie Intune so konfigurieren, dass Sie per E-Mail benachrichtigt werden, wenn eine Warnung generiert wird.

## Konfigurieren von Warnungen
Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Optionen **Verwaltung** &gt; **Warnungen und Benachrichtigungen** aus, und wählen Sie anschließend eine der folgenden Konfigurationsaufgaben aus:

|Aufgabe|Beschreibung|
|--------|---------------|
|**Warnungstypen**|Wählen Sie den Warnungstyp aus, den Sie konfigurieren möchten, und führen Sie dann eine der folgenden Aktionen aus:<br /><br />Wählen Sie **Konfigurieren** aus. Konfigurieren Sie im Dialogfeld **Warnungstyp konfigurieren** die gewünschten Einstellungen, und wählen Sie dann **OK** aus.<br /><br />**Aktivieren** oder **deaktivieren** Sie die Warnung.<br /><br />Erweitern Sie den Knoten **Warnungstypen**, und wählen Sie eine Kategorie aus, um nur die Warnungstypen dieser Kategorie anzuzeigen.|
|**Empfänger**|Wählen Sie **Hinzufügen** aus, um eine neue E-Mail-Adresse hinzuzufügen, an die die konfigurierten E-Mail-Benachrichtigungen gesendet werden sollen.<br /><br />Sie können auch vorhandene Empfänger **bearbeiten** oder **löschen** .<br /><br />Um Benachrichtigungen zu erhalten, müssen Sie diese E-Mail-Adresse zudem als Empfänger unter **Benachrichtigungsregeln** hinzufügen.|
|**Benachrichtigungsregeln**|Konfiguriert Regeln, die definieren, an wen eine E-Mail-Warnung gesendet wird. Sie können entweder:<br /><br />**Eine vorhandene Regel auswählen** – Wählen Sie eine Regel aus, und wählen Sie dann auf **Empfänger auswählen** aus. Dann können Sie alle Empfänger auswählen, an die eine E-Mail gesendet werden soll, wenn eine Warnung generiert wird, die diese Regel erfüllt.<br /><br />**Eine neue Regel erstellen** – Geben Sie einen Namen für die Regel ein, und wählen Sie dann die für die Regel geltenden Warnungskategorien und den Schweregrad aus. Wählen Sie die Benutzer aus, die eine E-Mail erhalten, wenn eine Warnung generiert wird.<br /><br />Sie können auch eine vorhandene Regel **aktivieren**, **deaktivieren**, **bearbeiten**oder **löschen** .|

## Arbeiten mit Warnungen
Die folgenden Optionen erleichtern die Arbeit mit Warnungen in der die Intune-Verwaltungskonsole.

|Option|Beschreibung|
|----------|---------------|
|**Anzeigen aktiver Warnungen**|Wählen Sie eine der folgenden:<br /><br />**Warnungszusammenfassung anzeigen** – Im Arbeitsbereich **Dashboard** werden die wichtigsten Fehler im Warnungsbereich angezeigt. Wählen Sie den Bereich aus, um ausführlichere Informationen anzuzeigen:<br /><br />Darüber hinaus können Sie eine Warnungszusammenfassung auf der Seite **Übersicht** im Arbeitsbereich **Warnungen** anzeigen.<br /><br />**Alle Warnungen anzeigen** – Wählen Sie im Arbeitsbereich **Warnungen** die Option **Alle Warnungen** aus.|
|**Anzeigen von Benachrichtigungen **|Wählen Sie eine der folgenden:<br /><br />Wählen Sie im Arbeitsbereich **Dashboard** die Option **Benachrichtigungen** aus.<br /><br />Wählen Sie im Arbeitsbereich **Warnungen** die Optionen **Alle Warnungen** &gt; **Benachrichtigungen** aus.|
|**Schließen einer Benachrichtigung**|Wählen Sie in der Liste der Warnungen die Warnung aus, die Sie schließen möchten, und wählen Sie dann **Warnung schließen** aus.<br /><br />Geschlossene Warnungen werden nach 90 Tagen dauerhaft gelöscht.|
|**Erneutes Aktivieren einer geschlossenen Warnung**|Legen Sie in der Liste der Warnungen die Dropdownliste **Filter** auf **Geschlossen** fest.<br /><br />Wählen Sie in der Liste geschlossener Warnungen die Warnung aus, die Sie erneut aktivieren möchten, und wählen Sie dann **Warnung erneut aktivieren** aus.|
Intune-Warnungen bleiben aktiv, bis:

-   Das Problem, das die Warnung verursacht hat, beseitigt wurde.

-   Sie die Warnung manuell schließen.

-   45 Tage seit dem Generieren der Warnung vergangen sind.

> [!TIP]
> Wenn dieselbe Warnung von Geräten mit verschiedenen Betriebssystemen generiert wird, werden möglicherweise mehrere Versionen der gleichen Warnung in der Warnungsliste angezeigt.

### Weitere Informationen:
[Überwachung und Berichte in Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


