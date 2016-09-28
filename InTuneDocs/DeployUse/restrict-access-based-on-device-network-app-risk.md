---
title: "Einschränken des Zugriffs mithilfe von Schutz vor Bedrohungen für mobile Geräte | Microsoft Intune"
description: "Einschränken des Zugriffs auf Unternehmensressourcen auf der Basis von Geräte-, Netzwerk- und Anwendungsrisiko."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c3cf5e6b32ad24d4972fd147331dda7d2d43e8c6
ms.openlocfilehash: d4eadb73aac14a375f41c434a4303a885bfbae64


---

# Einschränken des Zugriffs auf Unternehmensressourcen auf der Basis von Geräte-, Netzwerk- und Anwendungsrisiko
Sie können den Zugriff von mobilen Geräten auf Unternehmensressourcen steuern, basierend auf Risikobewertungen, die von Lookout vorgenommen werden, einer Lösung für den Schutz vor Bedrohungen auf mobilen Geräten (MTP, Mobile Threat Protection), die in Microsoft Intune integriert ist. Die Risikobewertung erfolgt auf der Grundlage von Telemetriedaten, die der Lookout MTP-Dienst bei Geräten für Sicherheitsrisiken beim Betriebssystem, installierter Schadsoftware und in Netzwerkprofilen sammelt. Auf der Grundlage der Risikobewertung können Sie anschließend Regeln für den bedingten Zugriff in Intune konfigurieren und Geräte zulassen bzw. blockieren, wenn sie aufgrund der auf ihnen erkannten Bedrohungen als nicht kompatibel bestimmt wurden.  Dies wird aktuell nur für **Android**-Geräte unterstützt, die Version **4.1 oder höher** ausführen und bei Microsoft Intune registriert sind.  
## Welches Problem wird dadurch gelöst?
Unternehmen und Organisationen müssen vertrauliche Daten vor auftretenden Bedrohungen schützen; dazu gehören physische, App-basierte und netzwerkbasierte Bedrohungen sowie Sicherheitsrisiken beim Betriebssystem.

In der Vergangenheit hatten Unternehmen und Organisationen beim Schutz von PCs vor böswilligen Angriffen eine aktive Position inne. Mobile Geräte stellen einen sich entwickelnden Bereich dar, der häufig keinem Schutz unterliegt. Zwar verfügen die mobilen Plattformen über integrierten Schutz durch das Betriebssystem in Form von Techniken wie App-Isolierung und sicherheitsgeprüfter App Stores für Verbraucher, diese Plattformen bleiben aber weiterhin durch komplexe Angriffe verwundbar. Da mobile Geräte zunehmend von Mitarbeitern für die Arbeit verwendet werden und daher Zugriff auf Informationen benötigen, die möglicherweise vertraulich und wertvoll sind, müssen diese Geräte vor einer Vielzahl komplexer Angriffe geschützt werden.

Intune gibt Ihnen die Möglichkeit, den Zugriff auf Unternehmensressourcen und -daten auf der Grundlage von Risikobewertungen zu steuern, die von MTP-Lösungen wie Lookout bereitgestellt werden.

## In welcher Form unterstützen Intune und Lookout Mobile Threat Protection den Schutz von Unternehmensressourcen?
Die mobile App von Lookout (Lookout for Work), die auf mobilen Geräten ausgeführt wird, erfasst das Dateisystem, den Netzwerkstapel sowie Telemetrie zu Gerät und Anwendungen (sofern verfügbar) und sendet diese Daten an den Lookout MTP-Clouddienst, um ein aggregiertes Geräterisiko für mobile Bedrohungen zu berechnen. Ferner können Sie die Klassifizierung der Risikostufe für die Bedrohungen in der MTP-Konsole gemäß Ihren Anforderungen ändern.  
Die Kompatibilitätsrichtlinie in Intune enthält jetzt eine neue Regel für Lookout Mobile Threat Protection, die auf der Risikobewertung durch Lookout MTP basiert. Wenn diese Regel aktiviert ist, bewertet Microsoft Intune anschließend die Gerätekompatibilität mit der von Ihnen aktivierten Richtlinie.

Wenn das Gerät als nicht mit der Kompatibilitätsrichtlinie kompatibel bestimmt wird, kann der Zugriff auf Ressourcen wie Exchange Online und SharePoint Online mithilfe von Richtlinien für den bedingten Zugriff blockiert werden. Wenn der Zugriff blockiert wird, wird den Endbenutzern eine exemplarische Vorgehensweise vorgestellt, die sie beim Beheben des Problems und beim Wiedererlangen des Zugriffs auf die Unternehmensressourcen unterstützt. Diese exemplarische Vorgehensweise wird mithilfe der Lookout for Work-App gestartet.

## Beispielszenarien
Es folgen einige häufige Szenarien:
### Bedrohung durch Apps, die Schadsoftware enthalten:
Wenn gefährliche Apps, wie z. B. Schadsoftware, auf einem Gerät entdeckt werden, kann sein Zugriff in diesen Punkten blockiert werden:
* Herstellen von Verbindungen mit der Unternehmens-E-Mail vor dem Aufheben der Bedrohung.
* Synchronisieren von Unternehmensdateien mithilfe der OneDrive for Work-App.
* Zugriff auf unternehmenswichtige Apps.

**Zugriff blockiert, wenn gefährliche Apps erkannt werden:**
![Diagramm, das eine Richtlinie für bedingten Zugriff darstellt, die den Zugriff blockiert, wenn ein Gerät aufgrund von gefährlichen Apps auf dem Gerät für nicht kompatibel bestimmt wird](../media/mtp/malicious-apps-blocked.png)

**Die Blockierung des Geräts wird aufgehoben und es kann auf Unternehmensressourcen zugreifen, wenn die Bedrohung beseitigt wurde:**

![Diagramm, das die Richtlinie für bedingten Zugriff darstellt, die den Zugriff erteilt, nachdem das Gerät nach der Sanierung als kompatibel bewertet wurde](../media/mtp/malicious-apps-unblocked.png)
### Bedrohung für das Netzwerk:
Erkennen von Bedrohungen Ihres Netzwerks, wie etwa Man-in-the-Middle-Angriffe, und Einschränken des Zugriffs auf WLANs auf der Grundlage des Geräterisikos.

**Zugriff auf das Netzwerk über WLAN blockiert:**
![Diagramm, das die Blockierung des WLAN-Zugriffs durch bedingten Zugriff auf der Grundlage von Netzwerkbedrohungen darstellt](../media/mtp/network-wifi-blocked.png)

**Zugriff erteilt nach der Sanierung:**

![Diagramm, das den Zugriff durch bedingten Zugriff nach der Beseitigung der Bedrohung erteilt](../media/mtp/network-wifi-unblocked.png)
### Bedrohung für das Netzwerk (Verhindern des Zugriffs auf SharePoint Online):

Erkennen von Bedrohungen Ihres Netzwerks, wie etwa Man-in-the-Middle-Angriffen, und Verhindern der Synchronisierung von Unternehmensdateien auf der Grundlage des Geräterisikos.

**Zugriff auf SharePoint Online basierend auf der auf dem Gerät erkannten Netzwerkbedrohung gesperrt:**

![Diagramm, das die Blockierung des Gerätezugriffs auf SharePoint Online mithilfe von bedingtem Zugriff basierend auf der Erkennung von Bedrohungen darstellt](../media/mtp/network-spo-blocked.png)


**Zugriff erteilt nach der Sanierung:**

![Diagramm, das den bedingten Zugriff nach dem Beheben der Netzwerkbedrohung darstellt](../media/mtp/network-spo-unblocked.png)

## Nächste Schritte
Hier sind die wichtigsten Schritte, die Sie ausführen müssen, um diese Lösung zu implementieren:
1.  [Einrichten Ihres Abonnements für Lookout Mobile Threat Protection](set-up-your-subscription-with-lookout-mtp.md)
2.  [Aktivieren der Lookout MTP-Verbindung in Intune](enable-lookout-mtp-connection-in-intune.md)
3.  [Konfigurieren und Bereitstellen der Lookout for Work-Anwendung](configure-and-deploy-lookout-for-work-apps.md)
4.  [Konfigurieren von Kompatibilitätsrichtlinien](enable-device-threat-protection-rule-in-compliance-policy.md)
5.  [Problembehandlung der Lookout-Integration](http://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration)



<!--HONumber=Sep16_HO3-->


