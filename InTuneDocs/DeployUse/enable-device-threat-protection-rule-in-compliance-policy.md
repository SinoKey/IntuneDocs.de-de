---
title: "Aktivieren der Geräteschutzregel in der Kompatibilitätsrichtlinie | Microsoft Intune"
description: "Aktivieren der Regel zum Schutz vor Bedrohungen von mobilen Geräten in der Gerätekompatibilitätsrichtlinie."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9c2ffb5fe497d56d8250fe3dec7db606c2067a1c
ms.openlocfilehash: 761372b2c8b81699bc2584ab1ef8d0f9d523abe9


---

# Aktivieren der Regel zum Schutz vor Bedrohungen von mobilen Geräten in der Kompatibilitätsrichtlinie
Intune mit Lookout Mobile Threat Protection gibt Ihnen die Möglichkeit, Bedrohungen von mobilen Geräten zu erkennen und eine Risikobewertung für das Gerät vorzunehmen.  
Regeln der Kompatibilitätsrichtlinie ermöglichen Ihnen, anhand dieser Risikobewertung zu bestimmen, ob das Gerät mit Ihrer Richtlinie kompatibel ist. Anschließend können Sie die Regel für bedingten Zugriff verwenden, um den Zugriff auf Exchange, SharePoint und andere Dienste auf der Grundlage der Gerätekompatibilität zuzulassen oder zu blockieren.

So geben Sie der Lookout MTP-Bedrohungserkennung Einfluss auf die Kompatibilitätsrichtlinie für das Gerät:

1.  Die Regel **Schutz vor Gerätebedrohungen** muss in der Kompatibilitätsrichtlinie aktiviert sein.

2.  Die Seite **Lookout-Status** in der Intune-Verwaltungskonsole muss **Aktiv** anzeigen. Weitere Details und Anweisungen zum Aktivieren der Lookout-Integration finden Sie im Thema [Aktivieren der Lookout MTP-Verbindung in Intune](enable-lookout-mtp-connection-in-intune.md).


## Konfigurieren der Regel zum Schutz vor Gerätebedrohungen

Bevor Sie die Regel zum Schutz vor Gerätebedrohungen in der Unternehmensrichtlinie erstellen, sollten Sie [Ihr Abonnement für Lookout MTP einrichten](set-up-your-subscription-with-lookout-mtp.md), die [Lookout-Verbindung in Intune konfigurieren](enable-lookout-mtp-connection-in-intune.md) und die [Lookout for Work-App konfigurieren](configure-and-deploy-lookout-for-work-apps.md). Die Kompatibilität wird erst durchgesetzt, wenn das Setup abgeschlossen ist.

Um die Regel zum Schutz vor Gerätebedrohungen zu aktivieren, können Sie entweder eine vorhandene Kompatibilitätsrichtlinie verwenden oder eine neue erstellen.

Im Rahmen des Lookout MTP-Setups haben Sie in der [Lookout MTP-Konsole](https://aad.lookout.com) eine Richtlinie erstellt, die verschiedene Bedrohungen in die Klassen hoch, mittel und schwer einstuft. In der Intune-Kompatibilitätsrichtlinie verwenden Sie die Bedrohungsstufe zum Festlegen der maximal zulässigen Bedrohungsstufe.

Gehen Sie in der Intune-Verwaltungskonsole auf der Seite der Kompatibilitätsrichtlinie zu **Geräteintegrität**, und aktivieren Sie mithilfe der Umschaltoption die Regel **Schutz vor Gerätebedrohungen**. Wählen Sie anschließend die maximal zulässige Bedrohungsstufe aus, nämlich eine der folgenden:
* **Keine (geschützt)**: Dies ist die sicherste Einstellung.  Dies bedeutet, dass das Gerät keinerlei Bedrohungen unterliegen darf.  Wenn auf dem Gerät Bedrohungen gleich welcher Stufe erkannt werden, wird es als nicht kompatibel bewertet.  
* **Niedrig**: Das Gerät wird als kompatibel bewertet, wenn nur Bedrohungen der Stufe „Niedrig“ vorliegen. Durch Bedrohungen höherer Stufen wird das Gerät in einen nicht kompatiblen Status versetzt.
* **Mittel**: Das Gerät wird als kompatibel bewertet, wenn die auf dem Gerät gefundenen Bedrohungen die Stufen „Niedrig“ oder „Mittel“ aufweisen. Wenn auf dem Gerät Bedrohungen der Stufe „Hoch“ erkannt werden, wird es als nicht kompatibel bewertet.
* **Hoch**: Dies ist die am wenigsten sichere Option. Grundsätzlich werden dadurch alle Bedrohungsstufen zugelassen, und diese Option ist wohl nur zu Berichtszwecken sinnvoll einsetzbar.

![Screenshot mit der Einstellung der Regel zum Schutz vor Gerätebedrohungen in ](../media/mtp/mtp-compliance-policy-rule.png)

![Screenshot der Option für die Bedrohungsstufe für die Einstellung der Regel zum Schutz vor Gerätebedrohungen](../media/mtp/mtp-compliance-policy-setting.png)

Wenn Sie für O365 und andere Dienste Richtlinien für den bedingten Zugriff erstellen, wird die oben dargestellte Kompatibilitätsbewertung berücksichtigt, und der Zugriff nicht kompatibler Geräte wird gesperrt, bis die Bedrohung beseitigt ist.

Sie können den Kompatibilitätszustand eines Geräts auf der Seite für Geräte in der Intune-Verwaltungskonsole anzeigen.

![Screenshot der Seite für Geräte in der Intune-Verwaltungskonsole mit Kompatibilitätsstatus eines Geräts](../media/mtp/mtp-device-status-intune-console.png)

## Nächste Schritte
* Erstellen einer Richtlinie für bedingten Zugriff
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Exchange lokal](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Skype for Business Online](restrict-access-to-skype-for-business-online-with-microsoft-intune,md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Sep16_HO2-->


