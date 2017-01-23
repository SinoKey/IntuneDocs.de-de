---
title: "Einschränken des Zugriffs mithilfe des Schutzes vor Gerätebedrohungen | Microsoft-Dokumentation"
description: "Einschränken des Zugriffs auf Unternehmensressourcen auf der Basis von Geräte-, Netzwerk- und Anwendungsrisiko."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6b83d06ecbe6e202bf022444c288e0866b3507c6
ms.openlocfilehash: 1dd2c4a46857aef1ba273904d58d5eacae99c7bc


---

# <a name="restrict-access-to-company-resource-based-on-device-network-and-application-risk"></a>Einschränken des Zugriffs auf Unternehmensressourcen auf der Basis von Geräte-, Netzwerk- und Anwendungsrisiko
Sie können den Zugriff mobiler Geräte auf Unternehmensressourcen basierend auf Risikobewertungen steuern, die von Lookout vorgenommen werden, einer Lösung für den Schutz vor Gerätebedrohungen, die in Microsoft Intune integriert ist. Das Risiko wird basierend auf Telemetriedaten bewertet, die vom Lookout-Dienst auf Geräten erfasst werden, wie z.B.:
- Sicherheitsrisiken des Betriebssystems
- Installierte Apps, die Schadsoftware enthalten
- Netzwerkprofile mit böswilligen Absichten

Sie können Richtlinien für bedingten Zugriff basierend auf Risikobewertungen von Lookout konfigurieren, die mithilfe von Intune-Kompatibilitätsrichtlinien aktiviert werden. Mithilfe von Einstellungen können Sie basierend auf den erkannten Bedrohungen nicht kompatible Geräte zulassen oder blockieren.  

## <a name="what-problem-does-this-solve"></a>Welches Problem wird dadurch gelöst?
Unternehmen müssen vertrauliche Daten vor auftretenden Bedrohungen schützen. Dazu gehören physische, App-und netzwerkbasierte Bedrohungen sowie Sicherheitsrisiken beim Betriebssystem.

In der Vergangenheit haben Firmen PCs vor Angriffen proaktiv geschützt, während mobile Geräte nicht überwacht wurden und ungeschützt blieben. Mobile Plattformen bieten integrierten Schutz in Form von App-Isolierung und sicherheitsgeprüfter App Stores für Verbraucher, doch diese Plattformen bleiben weiterhin für komplexe Angriffe anfällig. Immer mehr Mitarbeiter nutzen ihre Geräte für die Arbeit und benötigen Zugriff auf vertrauliche Informationen. Geräte müssen gegen zunehmend raffinierter werdende Angriffe geschützt werden.

Intune gibt Ihnen die Möglichkeit, den Zugriff auf Unternehmensressourcen auf Grundlage von Risikobewertungen zu steuern, die von Lösungen für den Schutz vor Gerätebedrohungen wie Lookout bereitgestellt werden.

## <a name="how-do-intune-and-lookout-device-threat-protection-help-protect-company-resources"></a>Wie werden Unternehmensressourcen von Intune und durch den Lookout-Schutz vor Gerätebedrohungen geschützt?
Die mobile Lookout-App **Lookout for Work** wird auf Mobilgeräten installiert und ausgeführt. Diese App erfasst Telemetriedaten des Dateisystems, Netzwerkstapels sowie von Geräten und Anwendungen, sofern verfügbar, und sendet diese dann an den Lookout-Clouddienst, mit dessen Hilfe die Anfälligkeit des Geräts für mobile Bedrohungen bewertet wird. Sie können die Klassifizierung der Risikostufe für Bedrohungen in der Lookout-Konsole gemäß Ihren Anforderungen ändern.  

Die Konformitätsrichtlinie in Intune enthält eine Regel für Lookout Mobile Threat Protection, die auf der Risikobewertung durch Lookout basiert. Wenn diese Regel aktiviert ist, bewertet Intune die Gerätekompatibilität mit der von Ihnen aktivierten Richtlinie.

Wird das Gerät als nicht kompatibel eingestuft, kann der Zugriff auf Ressourcen wie Exchange Online und SharePoint Online blockiert werden. Benutzer auf blockierten Geräten erhalten Anweisungen zum Beheben des Problems und erneuten Erlangen des Zugriffs. Die Anleitung wird in der Lookout for Work-App gestartet.

## <a name="supported-platforms"></a>Unterstützte Plattformen:
Bei Registrierung in Intune werden die folgenden Plattformen für Lookout unterstützt:
* **Android 4.1 und höher**
* **iOS 8 und höher** Weitere Informationen zur Unterstützung von Plattformen und Sprachen finden Sie auf der [Lookout-Website](https://personal.support.lookout.com/hc/en-us/articles/114094140253).

## <a name="prerequisites"></a>Voraussetzungen:
* Microsoft Intune-Abonnement
* Azure Active Directory
* Ein Enterprise-Abonnement für Lookout Mobile EndPoint Security.  

Weitere Informationen finden Sie unter [Lookout Mobile EndPoint Security](https://www.lookout.com/products/mobile-endpoint-security).

## <a name="sample-scenarios"></a>Beispielszenarien
Es folgen einige gängige Szenarien:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Steuern des Zugriffs basierend auf Bedrohungen durch Apps, die Schadsoftware enthalten
Wenn Apps, die Schadsoftware enthalten, auf Geräten erkannt werden, können Sie Geräte an folgenden Aktionen hindern, bis die Bedrohung beseitigt ist:
* Herstellen einer Verbindung mit Unternehmens-E-Mail
* Synchronisieren von Unternehmensdateien mithilfe der OneDrive for Work-App
* Zugreifen auf Unternehmens-Apps

**Zugriff blockiert, wenn Apps mit Schadsoftware erkannt werden:**
![Diagramm, das eine Richtlinie für bedingten Zugriff zeigt, die den Zugriff blockiert, wenn ein Gerät aufgrund vorhandener Apps mit Schadsoftware als nicht kompatibel eingestuft wird](../media/mtp/malicious-apps-blocked.png)

**Zugriff erteilt nach der Sanierung:**

![Diagramm, das die Richtlinie für bedingten Zugriff darstellt, die den Zugriff erteilt, nachdem das Gerät nach der Sanierung als kompatibel bewertet wurde](../media/mtp/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Steuern des Zugriffs basierend auf der Bedrohung für das Netzwerk
Erkennen von Bedrohungen Ihres Netzwerks, wie etwa Man-in-the-Middle-Angriffe, und Einschränken des Zugriffs auf WLANs auf der Grundlage des Geräterisikos.

**Zugriff auf das Netzwerk über WLAN blockiert:**
![Diagramm, das die Blockierung des WLAN-Zugriffs durch bedingten Zugriff auf Grundlage von Netzwerkbedrohungen zeigt](../media/mtp/network-wifi-blocked.png)

**Nach Korrektur erteilter Zugriff:**

![Diagramm, das den Zugriff durch bedingten Zugriff nach der Beseitigung der Bedrohung erteilt](../media/mtp/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Steuern des Zugriffs auf SharePoint Online basierend auf der Bedrohung für das Netzwerk

Erkennen von Bedrohungen Ihres Netzwerks, wie etwa Man-in-the-Middle-Angriffen, und Verhindern der Synchronisierung von Unternehmensdateien auf der Grundlage des Geräterisikos.

**Blockieren des Zugriffs auf SharePoint Online bei Erkennen von Bedrohungen für das Netzwerk**

![Diagramm, das die Blockierung des Gerätezugriffs auf SharePoint Online mithilfe von bedingtem Zugriff basierend auf der Erkennung von Bedrohungen darstellt](../media/mtp/network-spo-blocked.png)


**Zugriff erteilt nach der Sanierung:**

![Diagramm, das den bedingten Zugriff nach dem Beheben der Netzwerkbedrohung darstellt](../media/mtp/network-spo-unblocked.png)

## <a name="next-steps"></a>Nächste Schritte
Hier sind die wichtigsten Schritte, die Sie ausführen müssen, um diese Lösung zu implementieren:
1.  [Einrichten Ihres Abonnements für Lookout Mobile Threat Protection](set-up-your-subscription-with-lookout-mtp.md)
2.  [Aktivieren der Lookout MTP-Verbindung in Intune](enable-lookout-mtp-connection-in-intune.md)
3.  [Konfigurieren und Bereitstellen der Lookout for Work-Anwendung](configure-and-deploy-lookout-for-work-apps.md)
4.  [Konfigurieren von Kompatibilitätsrichtlinien](enable-device-threat-protection-rule-in-compliance-policy.md)
5.  [Problembehandlung der Lookout-Integration](http://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration)



<!--HONumber=Dec16_HO4-->


