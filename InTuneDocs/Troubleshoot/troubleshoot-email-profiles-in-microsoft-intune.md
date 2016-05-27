---
# required metadata

title: Problembehandlung bei E-Mail-Profilen | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Problembehandlung bei E-Mail-Profilen in Microsoft Intune
Hier werden einige Probleme mit E-Mail-Profilen sowie Informationen zu ihrer Problembehandlung und Lösung angeführt.

Wenn sich das Problem mit diesen Informationen nicht beheben lässt, finden Sie unter [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Anfordern von Support für Microsoft Intune) weitere Möglichkeiten, Hilfe zu erhalten.


## Senden von Bildern über E-Mail-Konto nicht möglich
Benutzer, deren E-Mail-Konten automatisch konfiguriert wurden, können keine Bilder von ihren Geräten senden.
Dies ist der Fall, wenn die Option **E-Mail-Versand aus Anwendungen von Drittanbietern zulassen ** nicht aktiviert ist.

### Intune-Lösung

1.  Öffnen Sie die Microsoft Intune-Verwaltungskonsole und wählen Sie **Richtlinie** Workload &gt; **Konfigurationsrichtlinie**..

2.  Wählen Sie das E-Mail-Profil aus, und klicken Sie auf **Bearbeiten**..

3.  Wählen Sie **E-Mail-Versand aus Anwendungen von Drittanbietern zulassen **.

### Configuration Manager integriert mit Windows Intune

1.  Öffnen Sie in der Configuration Manager-Konsole &gt; **Bestand und Kompatibilität**..

2.  Erweitern Sie **Übersicht** -&gt; **Kompatibilitätseinstellungen** -&gt; **Zugriff auf Unternehmensressourcen**, und wählen Sie **E-Mail-Profile**..

3.  Klicken Sie mit der rechten Maustaste auf das E-Mail-Profil, und öffnen Sie **Eigenschaften**..

4.  Wählen Sie auf der Registerkarte **Synchronisierungseinstellungen** die Option **E-Mail-Versand aus Anwendungen von Drittanbietern zulassen** aus..

## Nächste Schritte
Wenn diese Informationen zur Problembehandlung für Sie nicht hilfreich waren, wenden Sie sich wie in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Anfordern von Support für Microsoft Intune) beschrieben an den Microsoft Support..


<!--HONumber=May16_HO1-->


