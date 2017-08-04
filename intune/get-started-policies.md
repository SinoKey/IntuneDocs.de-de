---
title: Erste Schritte mit Richtlinien
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dd3279288fe5ea1fec16224c70b4562fcf53555d
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2017
---
# <a name="getting-started-with-policies"></a>Erste Schritte mit Richtlinien

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Eine der wichtigsten Zielsetzungen bei den ersten Schritten mit Intune ist das Registrieren von Geräten, um sicherzustellen, dass sie mit den Unternehmensrichtlinien kompatibel sind. Mit Kompatibilitätsrichtlinien können Sie nicht nur spezielle Gerätetypen wie z.B. firmeneigene Kioske verwalten, sondern auch persönliche Geräte und Tablets sowie benutzerlose Geräte.

![Kompatibilitätsdashboard mit sehr wenigen Daten](/intune/media/generic-compliance-dashboard.png)

Kompatibilitätsrichtlinien bieten folgende Managementfunktionen für mobile Geräte:

* Regulierung der Anzahl von Geräten, die jeder Benutzer registriert
* Verwalten der Geräteeinstellungen (z.B Verschlüsselung auf Geräteebene, Länge des Kennworts, Kameragebrauch)
* Bereitstellen von Apps, E-Mail-Profilen, VPN-Profilen, etc.
* Auswerten der Kriterien für Sicherheitskompatibilitätsrichtlinien auf Geräteebene

Sie erstellen Kompatibilitätsrichtlinien für jede Plattform einzeln. In dieser Übung verwenden wir nur iOS. Die folgenden Richtlinien sind für iOS-Geräte verfügbar:

* PIN- oder Kennwortkonfiguration
* Geräteverschlüsselung
* Per Jailbreak manipuliertes Gerät
* E-Mail-Profil
* Minimale Version des Betriebssystems
* Maximale Version des Betriebssystems

__Wie erstelle ich eine Richtlinie?__

1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.
2. Suchen Sie über **Ressourcen durchsuchen** nach **Intune**.
3. Wählen Sie **Gerätekompatibilität** aus.
4. Wählen Sie auf dem Blatt **Gerätekompatibilität** die Option **Richtlinien** aus.
5. Wählen Sie **Richtlinie erstellen** aus, und geben Sie dann die Details wie **Name** und **Beschreibung** ein. Wählen Sie **iOS** als **Plattform** aus.
6. Wählen Sie unter **Einstellungen** die Option **Systemsicherheit** aus, und legen Sie dann die Umschaltfläche **Anfordern eines Kennworts zum Entsperren mobiler Geräte** auf **Erforderlich** fest. Sie können auch weitere Regeln festlegen wie z.B. **Mindestlänge von Kennwörtern**, **Erforderlicher Kennworttyp** und **Anzahl nicht alphanumerischer Zeichen im Kennwort**. Wenn Sie Ihre Richtlinie eingerichtet haben, wählen Sie **OK** aus.
7. Kehren Sie zurück zum Blatt **Richtlinie erstellen**, und wählen Sie dann **Erstellen** aus.
8. Wählen Sie nach dem Erstellen der Richtlinie **Zuweisungen** aus, um sie Ihrer Testgruppe zuzuweisen. Wählen Sie Ihre Testgruppe mit Ihren Testbenutzern aus, und weisen Sie dieser Gruppe dann die Richtlinie zu, indem Sie auf **Speichern** klicken.
9. Warten Sie einige Minuten, bis Ihr registriertes Gerät Sie zur Eingabe eines aktualisierten Kennworts auffordert, damit weiterhin Kompatibilität mit der Unternehmensrichtlinie gegeben ist. Sie können dies auch manuell in der **Unternehmensportal-App für iOS** überprüfen, indem Sie auf den Gerätenamen und dann auf die Schaltfläche **Synchronisieren** klicken.
