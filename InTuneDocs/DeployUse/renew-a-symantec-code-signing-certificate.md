---
# required metadata

title: Erneuern eines Symantec-Codesignaturzertifikats für Ihr Unternehmen zur Verwendung mit Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c4813044-a925-4273-b0ec-e992fd55850a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Erneuern eines Symantec-Codesignaturzertifikats für Ihr Unternehmen für Windows-Geräte

Das zur Verwaltung bestimmter mobiler Windows- und Windows Phone-Geräte verwendete Symantec-Zertifikat muss regelmäßig erneuert werden. Für Windows Phone 8.0-Geräte sind für die Geräteregistrierung eine signierte Unternehmensportal-App und das Codesignaturzertifikat erforderlich. Spätere Windows Phone-Geräte können die aus dem Store heruntergeladene Unternehmensportal-App verwenden. Zur Bereitstellung von Branchen-Apps ist auch ein codesigniertes Zertifikat erforderlich.

## So wird das Symantec-Codesignaturzertifikat erneuert

1.  Suchen Sie nach einer Erneuerungs-E-Mail, die ungefähr 14 Tage vor Ablauf des Zertifikats von Symantec gesendet wurde. Diese E-Mail enthält Anweisungen von Symantec zum Erneuern des Zertifikats für Ihr Unternehmen.

    Weitere Informationen zu Symantec-Zertifikaten erhalten Sie unter [www.symantec.com](http://www.symantec.com) oder telefonisch unter 1-877-438-8776 oder + 1-650-426-3400.

2.  Wechseln Sie zu der Website (z. B.: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)), und melden Sie sich mit der Symantec-Herausgeber-ID und der mit dem Zertifikat verbundenen E-Mail-Adresse an. Denken Sie daran, den gleichen Computer für das Starten der Erneuerung zu verwenden, den Sie auch zum Herunterladen des Zertifikats verwenden werden.

3.  Sobald die Erneuerung genehmigt und bezahlt wurde, können Sie das Zertifikat herunterladen.

## Installieren des aktualisierten Zertifikats für Windows Phone 8.0

1.  Sie können das neueste Windows Phone-Unternehmensportal von folgender Stelle herunterladen und signieren: [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060)..

2.  Öffnen Sie Ihre Intune-Verwaltungskonsole ([https://admin.manage.microsoft.com](https://admin.manage.microsoft.com)), und wechseln Sie zu **Admin**, **Verwaltung mobiler Geräte** &gt; **Windows Phone**, und klicken Sie auf **Signierte App hochladen**..

3.  Laden Sie das neu signierte Unternehmensportal hoch. Sie benötigen die neu signierte SSP.XAP-Datei und die neue PFX-Datei, die Sie von Symantec erhalten, oder das Anwendungsregistrierungstoken, das mit dieser neuen PFX-Datei erstellt wurde.

4.  Wenn das Hochladen abgeschlossen ist, entfernen Sie in der Intune-Verwaltungskonsole die alte Version des Unternehmensportals im Arbeitsbereich **Software** .

5.  Signieren Sie alle Branchen-Apps erneut mit demselben Zertifikat, laden Sie sie hoch, und ersetzen Sie vorhandene Anwendungen.

Das Bereitstellen einer signierten SSP.XAP-Datei ist derzeit die einzige Möglichkeit, das aktualisierte Codesignaturzertifikat bereitzustellen. Zur Unterstützung signierter Branchen-Apps müssen Sie eine Unternehmensportal-App signieren und hochladen, auch wenn die Benutzer die Unternehmensportal-App über den Store installieren.

## Installieren des aktualisierten Zertifikats für Geräte mit Windows Phone 8.1 oder höher

1.  Sie können das neueste Windows Phone-Unternehmensportal aus dem Download Center herunterladen und signieren: [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060)..

2.  Öffnen Sie Ihre [Intune-Verwaltungskonsole](https://admin.manage.microsoft.com) (https://admin.manage.microsoft.com), und wechseln Sie zu **Admin** &gt; **Verwaltung mobiler Geräte** &gt; **Windows Phone**, und klicken Sie auf **Signierte App hochladen**..

3.  Laden Sie das neu signierte Unternehmensportal hoch. Sie benötigen die neu signierte SSP.XAP-Datei und die neue PFX-Datei, die Sie von Symantec erhalten, oder das Anwendungsregistrierungstoken, das mit dieser neuen PFX-Datei erstellt wurde.

4.  Wenn das Hochladen abgeschlossen ist, entfernen Sie die alte Version des Unternehmensportals im Arbeitsbereich **Software**.

5.  Signieren Sie alle neuen und aktualisierten Unternehmens-Apps unter Verwendung des neuen Zertifikats. Vorhandene Anwendungen müssen nicht erneut signiert und erneut bereitgestellt werden.


### Weitere Informationen:
[Einrichten der Windows Phone 8.0-Verwaltung](set-up-windows-phone-8.0-management-with-microsoft-intune.md)
[Einrichten der Windows Phone-Verwaltung](set-up-windows-phone-management-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


