---
# required metadata

title: Einblicke in Vorgänge durch Berichte | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 857309c2-61c9-4c22-becf-4839fedeaece

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: pbala
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Einblicke in Microsoft Intune-Vorgänge durch Berichte
Anhand der Informationen in diesem Thema können Sie Microsoft Intune-Berichte mit Informationen zu Software, Hardware sowie zu Softwarelizenzen in Ihrer Organisation erstellen und verwalten.

## Verwenden von Berichten
In den Intune-Berichten finden Sie Informationen zu Software, Hardware und Softwarelizenzen in Ihrem Unternehmen. Mithilfe von Berichten können Sie sich über den aktuellen Stand und den zukünftigen Bedarf informieren. Im Arbeitsbereich **Berichte** finden Sie Tools zum Erstellen und Verwalten von Berichten. Weitere Informationen zu Berichten finden Sie unter [Einblicke in Microsoft Intune-Vorgänge durch Berichte](understand-microsoft-intune-operations-by-using-reports.md).

### Berichtstypen

|Berichtstyp|Beschreibung|
|---------------|---------------|
|**Updateberichte**|Hierin werden die auf Computern in Ihrer Organisation erfolgreich abgeschlossenen Softwareupdates sowie fehlerhafte, ausstehende und erforderliche Updates angezeigt. Weitere Informationen zu Softwareupdates finden Sie unter [Aktualisieren Ihrer Windows-PCs mit Softwareupdates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).|
|**Berichte zu ermittelter Software**|Hierin wird Software angezeigt, die auf Computern in Ihrer Organisation installiert ist. Auch die Softwareversionen sind enthalten. Sie können die angezeigten Informationen nach Herausgeber und Kategorie der Software filtern. Durch Anklicken des Richtungspfeils neben dem Listenelement können Sie die Updates in der Liste erweitern, um weitere Details (zum Beispiel die Computer, auf denen ein Update installiert ist) anzuzeigen.<br /><br />Wenn Sie Computer zurückziehen oder deren Gruppenmitgliedschaft in Intune ändern, kann es einige Minuten dauern, bis die Änderungen im Bericht zu ermittelter Software berücksichtigt werden. Um möglichst präzise Softwareinventardaten zu erhalten, warten Sie nach dem Abkoppeln von Computern oder Ändern ihrer Gruppenmitgliedschaft einige Minuten, bevor Sie einen Bericht über erkannte Software ausführen, der diese Computer enthält.|
|**Computerinventurberichte**|Hierin werden Informationen zu verwalteten Computern in Ihrer Organisation angezeigt. Mithilfe dieses Berichts können Sie den Erwerb von Hardware planen und den Hardwarebedarf der Benutzer in Ihrer Organisation besser nachvollziehen. Weitere Informationen zum Arbeiten mit verwalteten Computern finden Sie unter [Verwalten von Windows-PCs mit Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md).|
|**Inventurberichte für mobile Geräte**|Hierin werden Informationen zu den mobilen Geräten in Ihrer Organisation angezeigt. Sie können die angezeigten Informationen nach Gruppen, entfernten Nutzungsbeschränkungen und Betriebssystem filtern.|
|**Lizenzkaufberichte**|Hierin werden die Softwaretitel jeder lizenzierten Software in ausgewählten Lizenzgruppen auf Basis ihrer Lizenzverträge angezeigt. Wenn die Softwarelizenzinformationen seit mehr als 24 Stunden nicht aktualisiert wurden, werden sie beim Erstellen eines Lizenzberichts aktualisiert. Ein Lizenzbericht stellt keine genaue Berechnung von verwendeten Softwaretiteln und keinen Nachweis der Erfüllung von Verträgen dar. Der Bericht ist ein Tool, das Ihnen dabei hilft, Lizenzierungsentscheidungen für Ihre Organisation zu treffen. Von Intune werden möglicherweise nicht alle Produkte erkannt, für die Microsoft-Volumenlizenzen verfügbar sind. Folgende Filter sind verfügbar:<br /><br />**Alle Verträge** zeigt alle lizenzierten Softwareprodukte an, die mit Intune verwaltet werden.<br /><br />**Volumenlizenzverträge** zeigt nur VLSC-Softwareprodukte an.<br /><br />**Andere Softwarelizenzverträge** zeigt Softwareprodukte an, die außerhalb des VLSC verwaltet werden.|
|**Lizenzinstallationsberichte**|Hierin wird die auf Computern in Ihrer Organisation installierte Software mit Ihrer aktuellen Lizenzvertragsabdeckung laut Volume Licensing Service Center (VLSC) verglichen. Zu den Filtern gehören:<br /><br />**Alle Verträge** zeigt alle lizenzierten Softwareprodukte an, die mit Intune verwaltet werden.<br /><br />**Volumenlizenzverträge** zeigt nur VLSC-Softwareprodukte an.<br /><br />**Andere Softwarelizenzverträge** zeigt Softwareprodukte an, die außerhalb des VLSC verwaltet werden.|
|**Berichte zu Nutzungsbedingungen**|Hierin wird angezeigt, ob die Benutzer die von Ihnen bereitgestellten Nutzungsbedingungen akzeptiert haben und welche Version sie akzeptiert haben. Sie können bis zu 10 Benutzer angeben, deren Annahmestatus von beliebigen ihnen bereitgestellten Nutzungsbedingungen angezeigt werden, oder den Annahmestatus für eine bestimmte Bedingung anzeigen.|
|**Nicht kompatible Apps-Berichte**|Es werden Informationen zu den Benutzern mit installierten Apps angezeigt, die in Ihren Listen der kompatiblen und nicht kompatiblen Apps enthalten sind. Verwenden Sie diesen Bericht, um Benutzer und Geräte zu ermitteln, die nicht mit Ihren Unternehmens-App-Richtlinien konform sind.|
|**Berichte zur Zertifikatkompatibilität**|Zeigt an, welche Zertifikate für Benutzer und Geräte über SCEP oder PKCS #12 (.PFX)ausgestellt wurden. Verwenden Sie diesen Bericht, um ausgestellte, abgelaufene und gesperrte Zertifikate zu suchen.|
|**Berichte zum Geräteverlauf**|Zeigt ein historisches Protokoll von Abkoppeln-, Zurücksetzen- und Löschen-Aktionen. Verwenden Sie diesen Bericht, um zu ermitteln, welcher Benutzer in der Vergangenheit Aktionen auf Geräten initiiert hat.|
|**Mac OS X-Hardwarebericht**|Hierin werden Hardwaredetails zu allen registrierten Mac OS X-Geräten in den von Ihnen ausgewählten Gruppen angezeigt. Informationen zu dem von diesen Geräten erfassten Hardwareinventar finden Sie unter [Verstehen Sie Ihre Geräte mithilfe des Inventars in Microsoft Intune](understand-your-devices-with-inventory-in-microsoft-intune.md).|
|**Mac OS X-Softwarebericht**|Hierin wird die auf allen Mac OS X-Geräten in den von Ihnen ausgewählten Gruppen installierte Software angezeigt. Im Bericht werden der Softwarename (als Paket-ID), die Kurzversion des Namens (oder der Anzeigename), die Version und die Anzahl von Geräten, auf denen die Software installiert ist, aufgeführt.|

#### So erstellen Sie einen Bericht

1.  Klicken Sie in der Intune-Verwaltungskonsole auf **Berichte** und dann auf den Berichtstyp, der erstellt werden soll, wie in der Tabelle oben beschrieben.

2.  Übernehmen Sie auf der Seite **Neuen Bericht erstellen** die Vorgaben, oder passen Sie sie an, um die im Bericht zurückgegebenen Ergebnisse zu filtern. Sie können beispielsweise auswählen, dass nur von Microsoft herausgegebene Software im Bericht über erkannte Software angezeigt werden soll.

3.  Klicken Sie auf **Bericht anzeigen** , um den Bericht in einem neuen Fenster zu öffnen.

Sie können den Bericht nach jeder Spalte sortieren, indem Sie auf die entsprechende Spaltenüberschrift klicken. Zusätzlich können Sie bei einigen Berichten Listenelemente erweitern, um mehr Details anzeigen zu lassen.

## Weitere Berichtsaktionen
Zusätzlich werden von Berichten die folgenden Aktionen unterstützt:

|Aktion|Weitere Informationen|
|----------|--------------------|
|**Drucken**|Klicken Sie in einem geöffneten Bericht auf das Drucken-Symbol, und folgen Sie den Anweisungen.|
|**Exportieren**|Klicken Sie in einem geöffneten Bericht auf das Exportieren-Symbol, und folgen Sie den Anweisungen. Sie können einen Bericht im CSV- (kommagetrennte Werte) oder HTML-Format exportieren.|
|**Speichern**|Auf der Seite **Neuen Bericht erstellen** können von jedem Benutzer bis zu 100 Berichte gespeichert werden. Konfigurieren Sie die Berichtsparameter wie gewünscht, und klicken Sie dann auf **Speichern**oder auf **Speichern unter** , wenn Sie einen anderen Namen verwenden möchten.|
|**Laden**|Klicken Sie auf der Seite **Neuen Bericht erstellen** auf **Laden** , um zuvor gespeicherte Sätze von Berichtsparametern abzurufen.|
|**Löschen**|Wählen Sie im Arbeitsbereich **Berichte** den gewünschten Berichtstyp aus, klicken Sie auf **Laden**und dann in der Berichtsliste auf das Löschen-Symbol (X) neben dem Bericht.|

### Weitere Informationen:
[Überwachung und Berichte in Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)



<!--HONumber=Jun16_HO1-->


