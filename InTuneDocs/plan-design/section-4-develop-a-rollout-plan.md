---
title: "Festlegen von Zielgruppen und Zeitrahmen für den Intune-Rollout | Microsoft-Dokumentation"
description: "Dieser Artikel hilft Ihnen beim Festlegen von Zielgruppen und Zeitrahmen für eine reine Microsoft Intune-Cloudimplementierung."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a63f78f-a7e7-4f44-9288-16b28d5d58ca
ms.reviewer: jeffbu, cgerth
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f807d6e4b20b98ecf622d1ebdd9db33b132a2e6a
ms.openlocfilehash: 36530602813467c184b4f262719a56cedbaa2ba9


---

# <a name="develop-an-intune-rollout-plan"></a>Entwickeln eines Rolloutplans für Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Dieser Abschnitt hilft Ihnen beim Festlegen der Organisationsgruppen, die bei Ihrem Intune-Rollout als Zielgruppen verwendet werden sollen, beim Definieren des Rolloutzeitrahmens für die einzelnen Gruppen und beim Bestimmen der zu verwendenden Registrierungsansätze.

## <a name="determine-intune-rollout-targeted-groups-and-timeframes"></a>Festlegen von Zielgruppen und Zeitrahmen für den Intune-Rollout

Zuerst müssen die Gruppen festgelegt werden, die beim Intune-Rollout berücksichtigt werden sollen. Die Zielgruppen wurden in diesem Handbuch bereits im Abschnitt zum Festlegen von Intune-Anwendungsszenarien erläutert.

Als nächstes müssen Sie den Zeitrahmen bestimmen, der für die einzelnen Gruppen beim Intune-Rollout angestrebt werden soll. Hierfür ist normalerweise eine Diskussion innerhalb des Intune-Bereitstellungsteams und mit den Zielgruppen erforderlich, um den am besten geeigneten Rolloutzeitrahmen für die einzelnen Gruppen zu ermitteln.

Beispielsweise kann das Intune-Bereitstellungsteam Faktoren wie die Änderungsbereitschaft der Gruppe, die Anzahl von Benutzern und Geräten, Typen von Geräteplattformen, Anforderungen, den geografischen Standort und das Geschäftsrisiko erörtern, um den Rolloutzeitrahmen zu bestimmen.

Organisationen entscheiden sich häufig dafür, die Einführung von Intune mit einer Pilotphase zu beginnen, die auf eine kleine Gruppe von Benutzern in der IT-Abteilung ausgerichtet ist. Die Pilotphase kann dann auf eine größere Gruppe von IT-Benutzern und durch Teilnehmer aus anderen Gruppen der Organisation erweitert werden. Nach einer erfolgreichen Pilotphase sind Organisationen für einen vollständigen Produktionsrollout bereit, bei dem die restlichen Gruppen der Organisation einbezogen werden. Einige Beispiele für verschiedene Rolloutgruppen und -phasen werden unten angegeben:

-   **Pilotphase:** Die erste Phase beim Rollout sollte Pilotbenutzer umfassen. Die Pilotbenutzer müssen sich darüber im Klaren sein, dass sie die ersten Benutzer in einer neuen Lösung sind und Feedback zur Verbesserung von Konfiguration, Dokumentation und Benachrichtigungen bereitstellen sollen, um den Weg für alle anderen Benutzer in späteren Rolloutphasen zu ebnen. Bei diesen Benutzern darf es sich nicht um Führungskräfte oder VIPs handeln.

-   **Abteilungen:** Jede Abteilung kann an einer Rolloutphase teilnehmen. In diesem Szenario wird eine ganze Abteilung als Zielgruppe verwendet. Bei dieser Art von Rollout wird in jeder Phase wahrscheinlich dasselbe mobile Gerät auf die gleiche Weise verwendet und auf dieselben Anwendungen zugegriffen. Die Benutzer verfügen wahrscheinlich auch über dieselben Richtlinientypen.

-   **Geografie:** Diese Art der Bereitstellung erfolgt für alle Benutzer an einem bestimmten geografischen Ort, ob auf demselben Kontinent, in demselben Land, derselben Region oder demselben Unternehmensgebäude. Diese Art der gestaffelten Bereitstellung lässt die Möglichkeit zu, sich auf einen bestimmten Benutzerstandort zu konzentrieren. Hierdurch wird ein [White Glove](#user-assisted-enrollment)-Ansatz ermöglicht, weil Intune an einer geringeren Anzahl von Standorten gleichzeitig bereitgestellt wird. Da verschiedene Abteilungen oder Anwendungsfälle sich möglicherweise am selben Ort befinden, könnten verschiedene Anwendungsfälle gleichzeitig bereitgestellt werden.

-   **Plattform:** Bei dieser Art der Bereitstellung werden ähnliche Plattformen gleichzeitig bereitgestellt. Beispielsweise werden im ersten Monat alle iOS-Geräte verwendet, gefolgt von Android und dann von Windows. Diese Art der gestaffelten Bereitstellung vereinfacht den Helpdesksupport. Der Helpdesksupport muss immer nur eine einzige Plattform unterstützen.

Dieses Beispiel zeigt einen Intune-Rolloutplan, der Zielgruppen und Zeitrahmen umfasst:

| **Rolloutphase** | **Juli** | **August** | **September** | **Oktober** |
|:---:|:---:|:---:|:---:|:---:|
| Begrenztes Pilotprojekt | IT (50 Benutzer) |  |  |  |                                                         
| Erweitertes Pilotprojekt | IT (200 Benutzer), IT-Führungskräfte (10 Benutzer) |  |  |  |                                                         
| Produktionsrolloutphase 1 |  | Vertrieb und Marketing (2.000 Benutzer) |  |  |
| Produktionsrolloutphase 2 |  |  | Einzelhandel (1.000 Benutzer) |  |
| Produktionsrolloutphase 3 |  |  |  | Personalabteilung (50 Benutzer), Finanzabteilung (40 Benutzer), Führungskräfte (30 Benutzer) |

## <a name="determine-the-intune-enrollment-approach"></a>Festlegen des Intune-Registrierungsansatzes

Nachdem Sie die Zielgruppen und den Zeitrahmen für Ihren Intune-Rollout festgelegt haben, besteht der nächste Schritt darin, für jede Gruppe den angemessenen Ansatz für die Intune-Registrierung zu wählen. Es gibt verschiedene Registrierungsansätze, die Organisationen für ihren Intune-Rollout verwenden können. Einige gängige Registrierungsansätze umfassen die Self-Service-Registrierung, die Registrierung mit Benutzerunterstützung und die Veranstaltung einer IT-Technologiemesse.

### <a name="user-self-service"></a>Benutzer-Self-Service

Bei diesem Ansatz ist der Benutzer für das Registrieren des eigenen Geräts verantwortlich und befolgt in der Regel die von der IT-Organisation bereitgestellten Registrierungsanweisungen. Dieser Ansatz wird in Organisationen am häufigsten verwenden und ist skalierbarer als die Registrierung mit Benutzerunterstützung.

### <a name="user-assisted-enrollment"></a>Registrierung mit Benutzerunterstützung

Dies bezeichnet man als den „White Glove“-Ansatz, bei dem ein Mitglied des IT-Teams den Benutzer persönlich oder über Skype durch den Registrierungsvorgang leitet. Dieser Ansatz wird häufig bei Führungskräften und anderen Gruppen verwendet, die während des Registrierungsvorgangs mehr Unterstützung benötigen.

### <a name="it-tech-fair"></a>IT-Technologiemesse

Eine weitere Option für die Intune-Benutzerregistrierung besteht in der Veranstaltung einer IT-Technologiemesse. Bei dieser Veranstaltung richtet die IT-Gruppe einen Stand zur Unterstützung bei der Intune-Registrierung ein, an dem Benutzer Informationen zur Intune-Registrierung erhalten, Fragen stellen und Unterstützung beim Registrierungsvorgang anfordern können. Die Nutzung dieser Option kann sowohl für die IT-Gruppe als auch für den Benutzer von Vorteil sein, insbesondere in den frühen Phasen des Intune-Rollouts.

Hier sehen Sie ein Beispiel für einen Intune-Rolloutplan mit Zielgruppen, Zeitrahmen und Registrierungsansätzen:

| **Rolloutphase** | **Juli** | **August** | **September** | **Oktober** |
|:---:|:---:|:---:|:---:|:---:|
| Begrenztes Pilotprojekt |  |  |  |  |                                                         
| Self-Service | IT |  |  |  |
| Erweitertes Pilotprojekt |  |  |  |  |                                                         
| Self-Service | IT |  |  |  |
| White Glove | IT-Führungskräfte |  |  |  |
| Produktionsrolloutphase 1 |  | Vertrieb, Marketing |  |  |
| Self-Service |  | Vertrieb und Marketing |  |  |
| Produktionsrolloutphase 2 |  |  | Einzelhandel |  |
| Self-Service |  |  |  |  |
| Produktionsrolloutphase 3 |  |  | Einzelhandel |  |
| Self-Service |  |  |  | Personalabteilung, Finanzabteilung |
| White Glove |  |  |  | Führungskräfte |

## <a name="next-section"></a>Nächster Abschnitt

Der nächste Abschnitt enthält Hinweise für das [Entwickeln eines Kommunikationsplans für den Intune-Rollout](section-5-develop-a-rollout-communication-plan.md).



<!--HONumber=Dec16_HO5-->


