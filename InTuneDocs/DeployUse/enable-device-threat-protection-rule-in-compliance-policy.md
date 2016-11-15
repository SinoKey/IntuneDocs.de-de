---
title: "Aktivieren der Geräteschutzregel in der Kompatibilitätsrichtlinie | Microsoft Intune"
description: "Aktivieren der Regel zum Schutz vor Bedrohungen von mobilen Geräten in der Gerätekompatibilitätsrichtlinie."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9bf5764d1e1bd73fd62e5033b2309fc8d5a912e4
ms.openlocfilehash: ec287d49910a72c22122f45a01850bcbd3a7d203


---

# <a name="enable-device-threat-protection-rule-in-the-compliance-policy"></a>Aktivieren der Regel zum Schutz vor Bedrohungen von mobilen Geräten in der Kompatibilitätsrichtlinie
Intune mit Lookout Mobile Threat Protection gibt Ihnen die Möglichkeit, Bedrohungen von mobilen Geräten zu erkennen und eine Risikobewertung für das Gerät vorzunehmen. Sie können eine Regel für die Kompatibilitätsrichtlinie erstellen, in die die Risikoanalyse zum Bestimmen einbezogen wird, ob das Gerät kompatibel ist. Anschließend können Sie die Regel für bedingten Zugriff verwenden, um den Zugriff auf Exchange, SharePoint und andere Dienste auf Grundlage der Gerätekompatibilität zuzulassen oder zu blockieren.

So geben Sie der Lookout-Bedrohungserkennung für Geräte Einfluss auf die Kompatibilitätsrichtlinie für das Gerät:

* Die Regel **Schutz vor Gerätebedrohungen** muss in der Kompatibilitätsrichtlinie aktiviert sein.

* Die Seite **Lookout-Status** in der **Intune-Verwaltungskonsole** muss als **Aktiv** angezeigt werden. Weitere Details und Anweisungen zum Aktivieren der Lookout-Integration finden Sie im Thema [Aktivieren der Lookout MTP-Verbindung in Intune](enable-lookout-mtp-connection-in-intune.md).


Bevor Sie die Regel zum Schutz vor Gerätebedrohungen in der Unternehmensrichtlinie erstellen, sollten Sie [Ihr Abonnement für den Lookout-Schutz vor Gerätebedrohungen einrichten](set-up-your-subscription-with-lookout-mtp.md), die [Lookout-Verbindung in Intune konfigurieren](enable-lookout-mtp-connection-in-intune.md) und die [Lookout for Work-App konfigurieren](configure-and-deploy-lookout-for-work-apps.md). Die Kompatibilitätsregel wird erst erzwungen, nachdem das Setup abgeschlossen wurde.

Um die Regel zum Schutz vor Gerätebedrohungen zu aktivieren, können Sie entweder eine vorhandene Kompatibilitätsrichtlinie verwenden oder eine neue erstellen.

Beim Setup des Lookout-Schutzes vor Gerätebedrohungen haben Sie in der [Lookout-Konsole](https://aad.lookout.com) eine Richtlinie erstellt, die verschiedene Bedrohungen in die Klassen hoch, mittel und schwer einstuft. In der Intune-Kompatibilitätsrichtlinie verwenden Sie die Bedrohungsstufe zum Festlegen der maximal zulässigen Bedrohungsstufe.

Wechseln Sie in der **Intune-Verwaltungskonsole** auf der Seite **Kompatibilitätsrichtlinie** zu **Geräteintegrität**, und aktivieren Sie mithilfe der Umschaltoption die Regel **Schutz vor Gerätebedrohungen**. Wählen Sie anschließend die maximal zulässige Bedrohungsstufe aus, nämlich eine der folgenden:
* **Keine (geschützt)**: Dies ist die sicherste Einstellung.  Dies bedeutet, dass das Gerät keinerlei Bedrohungen unterliegen darf.  Wenn Bedrohungen beliebiger Stufen gefunden werden, wird das Gerät als nicht kompatibel bewertet.  
* **Niedrig**: Das Gerät wird als kompatibel bewertet, wenn nur Bedrohungen niedriger Stufen vorliegen. Durch Bedrohungen höherer Stufen wird das Gerät in einen nicht kompatiblen Status versetzt.
* **Mittel**: Das Gerät wird als kompatibel bewertet, wenn die auf dem Gerät gefundenen Bedrohungen niedriger oder mittlerer Stufe sind. Wenn auf dem Gerät Bedrohungen hoher Stufen erkannt werden, wird es als nicht kompatibel bewertet.
* **Hoch**: Dies ist die am wenigsten sichere Option. Mit dieser Einstellung werden grundsätzlich alle Bedrohungsstufen zugelassen. Sie ist daher wahrscheinlich nur für Berichtszwecke sinnvoll.

![Screenshot mit der Einstellung der Regel zum Schutz vor Gerätebedrohungen in ](../media/mtp/mtp-compliance-policy-rule.png)

![Screenshot der Option für die Bedrohungsstufe für die Einstellung der Regel zum Schutz vor Gerätebedrohungen](../media/mtp/mtp-compliance-policy-setting.png)

Wenn Sie für Office 365 und andere Dienste Richtlinien für den bedingten Zugriff erstellen, wird die oben dargestellte Kompatibilitätsbewertung berücksichtigt, und der Zugriff auf Unternehmensressourcen für nicht kompatible Geräte wird gesperrt, bis die Bedrohung beseitigt ist.

Sie können den Kompatibilitätszustand eines Geräts in der **Intune-Verwaltungskonsole** auf der Seite **Alle Geräte** anzeigen.

![Screenshot der Seite für Geräte in der Intune-Verwaltungskonsole mit Kompatibilitätsstatus eines Geräts](../media/mtp/mtp-device-status-intune-console.png)

## <a name="next-steps"></a>Nächste Schritte
* Erstellen einer Richtlinie für bedingten Zugriff
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Exchange lokal](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Skype for Business Online](restrict-access-to-skype-for-business-online-with-microsoft-intune,md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Nov16_HO2-->


