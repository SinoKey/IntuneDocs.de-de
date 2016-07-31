---
title: Behandlung von Problemen mit Richtlinien | Microsoft Intune
description: Behandeln Sie Richtlinienkonfigurationsprobleme.
keywords: 
author: Nbigman
manager: angrobe
ms.date: 05/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9915b275101e287498217c4f35e1c0e56d2425c2
ms.openlocfilehash: 06468bd7d6cdcf84da269c8132b37240ef1f2197


---

# Behandlung von Problemen mit Richtlinien in Microsoft Intune

Sie finden hier einige Probleme aufgelistet, die aus Ihrer Microsoft Intune-Richtlinienkonfiguration entstehen können, sowie Empfehlungen zur Behandlung dieser Probleme.

Wenn sich das Problem mit diesen Informationen nicht beheben lässt, finden Sie unter [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Anfordern von Support für Microsoft Intune) weitere Möglichkeiten, Hilfe zu erhalten.


## Ist die Richtlinie auf das Gerät angewendet?
**Problem:** Es ist nicht klar, ob eine bestimmte Richtlinie auf ein Gerät angewendet ist, oder ein Gerät verhält sich entgegen einer Richtlinie.

Überprüfen Sie die Richtlinieninformationen, die für jedes Gerät verfügbar sind, um zu verstehen, wie sich eine Richtlinie auf ein bestimmtes Gerät auswirkt.

In der Intune-Verwaltungskonsole verfügt jedes Gerät unter **Geräteeigenschaften**über eine Registerkarte „Richtlinie“. Wenn nicht, befindet sich das Gerät eventuell noch im Registrierungsprozess, oder es sind keine Richtlinien darauf angewendet. Jede Richtlinie verfügt über einen **beabsichtigten Wert** und einen **Status**. Den beabsichtigten Wert möchten Sie durch Zuweisen der Richtlinie erzielen. Der Status gibt an, was tatsächlich erreicht wird, wenn alle für das Gerät geltenden Richtlinien sowie die Einschränkungen und Anforderungen der Hardware und des Betriebssystems zusammen betrachtet werden. Mögliche Status sind:

-   **Konform**: Das Gerät hat die Richtlinie empfangen und meldet dem Dienst, dass es der Einstellung entspricht.

-   **Nicht zutreffend**: Die Richtlinieneinstellung ist nicht zutreffend. Beispielsweise wären E-Mail-Einstellungen für iOS-Geräte nicht auf ein Android-Gerät anwendbar.

-   **Ausstehend**: Die Richtlinie wurde an das Gerät gesendet, hat aber noch keinen Status an den Dienst gemeldet. Beispiel: Verschlüsselung unter Android erfordert, dass der Benutzer die Verschlüsselung aktiviert, und sie könnte aus diesem Grund ausstehen.

Der folgende Screenshot zeigt zwei eindeutige Beispiele:

-   **Einfache Kennwörter zulassen** ist auf **Ja**gesetzt, wie in der Spalte **Beabsichtigter Wert** gezeigt, der **Status** ist jedoch **Nicht zutreffend**. Dies liegt daran, dass einfache Kennwörter für Android-Geräte nicht unterstützt werden.

-   Ebenso gilt das erweiterte Richtlinienelement **E-Mail-Einstellungen für iOS-Geräte** nicht für dieses Gerät, da es ein Android-Gerät ist.

![Intune-Geräterichtlinie](../media/Intune-Device-Policy-v.2.jpg)

> [!NOTE]
> Denken Sie daran: Wenn zwei Richtlinien mit unterschiedlichen Einschränkungsstufen für das gleiche Gerät gelten, wird in der Praxis die restriktivere Richtlinie angewendet.

## Intervalle für Richtlinienaktualisierungen und -updates
Denken Sie daran, dass Richtlinien in regelmäßigen Abständen aktualisiert werden. Richtlinien sollten in der Regel innerhalb von 15 Minuten nach einer Änderung auf den Geräten registriert werden. Hier finden Sie ausführliche Informationen zu den regelmäßigen Intervallen der Aktualisierung von Richtlinien:

-   **Für MDM registriertes Windows-Gerät**: Die Richtlinie wird für Windows 8.1- und Windows 10-Geräte alle 8 Stunden und für Windows RT-Geräte alle 24 Stunden aktualisiert.

-   **Windows Phone**: Die Richtlinie wird alle 8 Stunden aktualisiert. Dies kann durch eine Aktualisierung im Unternehmensportal unter **Einstellungen** erzwungen werden.

-   **iOS**: Die Richtlinie wird in einem zufälligen Zeitintervall einmal täglich aktualisiert. Dies kann auch erzwungen werden, indem Sie das Unternehmensportal öffnen, das Gerät auswählen und auf **Synchronisieren** klicken.

-   **Android**: Die Richtlinie wird in einem zufälligen Zeitintervall einmal täglich aktualisiert. Dies kann auch erzwungen werden, indem Sie das Unternehmensportal öffnen, das Gerät auswählen und auf **Synchronisieren** klicken.

## Fehler in „policyplatform.log“ im Zusammenhang mit der Microsoft Intune-Richtlinie
Bei Windows-Geräten ohne MDM können Richtlinienfehler in der Datei „policyplatform.log“ das Ergebnis nicht standardmäßiger Einstellungen in der Windows-Benutzerkontensteuerung (UAC) auf dem Gerät sein. Einige nicht standardmäßige UAC-Einstellungen können Microsoft Intune-Clientinstallationen und Richtlinienausführungen beeinträchtigen.

### So beheben Sie UAC-Probleme

1.  Koppeln Sie den Computer ab, wie unter [Retire devices from Microsoft Intune management](/intune/deploy-use/retire-devices-from-microsoft-intune-management) (Abkoppeln von Geräten in der Microsoft Intune-Verwaltung) beschrieben.

2.  Warten Sie 20 Minuten, bis die Clientsoftware entfernt wurde.

    > [!NOTE]
    > Versuchen Sie nicht, den Client über „Programme und Funktionen“ zu entfernen.

3.  Geben Sie im Startmenü **UAC** ein, um die Einstellungen der Benutzerkontensteuerung zu öffnen.

4.  Verschieben Sie den Schieberegler für Benachrichtigungen auf die Standardeinstellung.

## Fehler „0x87D1FDE8“ für KNOX-Gerät
**Problem**: Nach dem Erstellen und Bereitstellen eines Exchange ActiveSync-E-Mail-Profils für Samsung KNOX für verschiedene Android-Geräte melden diese den Fehler **0x87D1FDE8** oder **Fehler bei Wiederherstellung** auf der Registerkarte „Eigenschaften“ &gt; „Richtlinie“ des Geräts.

Überprüfen Sie die Konfiguration Ihres EAS-Profils für Samsung KNOX und die Quellrichtlinie. Die Samsung-Option zum Synchronisieren von Notizen wird nicht mehr unterstützt, und diese Option sollte in Ihrem Profil nicht ausgewählt werden. Achten Sie darauf, dass Geräte genug Zeit hatten, um die Richtlinie zu verarbeiten (bis zu 24 Stunden).

## Warnung: Fehler beim Speichern von Zugriffsregeln in Exchange
**Problem**: Sie erhalten die Warnung **Fehler beim Speichern von Zugriffsregeln in Exchange**  in der Verwaltungskonsole.

Wenn Sie Richtlinien im Exchange-Arbeitsbereich „Lokale Richtlinie“ in der Verwaltungskonsole erstellt haben, aber Office 365 verwenden, werden die konfigurierten Richtlinieneinstellungen von Intune nicht erzwungen. Beachten Sie die Richtlinienquelle in der Warnung.  Löschen Sie im Exchange-Arbeitsbereich „Lokale Richtlinie“ die Legacyregeln, weil diese in Intune globale Exchange-Regeln für lokales Exchange und für Office 365 nicht relevant sind. Erstellen Sie dann eine neue Richtlinie für Office 365.

## FEHLER: Der Wert kann nicht vom Computer abgerufen werden, 0x80041013
Dieser Fehler kann auftreten, wenn die Zeit auf dem lokalen System um mindestens fünf Minuten abweicht. Wenn die Zeit auf dem lokalen Computer nicht synchron ist, schlagen sichere Transaktionen fehl, da der Zeitstempel ungültig ist.

Um dieses Problem zu beheben, legen Sie die lokale Systemzeit so genau wie möglich auf die Internetzeit oder die auf den Domänencontrollern im Netzwerk eingestellte Zeit fest.

## Sicherheitsrichtlinie für verschiedene MDM-Geräte kann nicht geändert werden
Windows Phone- und Windows RT-Geräte gestatten keine Verringerung der Sicherheitsstufe in Sicherheitsrichtlinien, die mittels MDM oder EAS festgelegt wurden, nachdem diese festgelegt wurden. Angenommen, Sie legen ein **Kennwort mit Mindestanzahl von Zeichen** auf 8 fest und versuchen dann, diesen Wert auf 4 zu verringern. Die restriktivere Richtlinie wurde bereits auf das Gerät angewendet.

Abhängig von der Geräteplattform müssen Sie, wenn Sie die Richtlinie auf einen niedrigeren Sicherheitswert ändern möchten, Sicherheitsrichtlinien möglicherweise zurücksetzen.
In Windows RT wischen Sie beispielsweise auf dem Desktop von rechts nach innen, um die Leiste **Charms** zu öffnen, und wählen Sie **Einstellungen** &gt; **Systemsteuerung**.  Wählen Sie das Applet **Benutzerkonten** aus.
Im linken Navigationsmenü befindet sich unten ein Link **Sicherheitsrichtlinien zurücksetzen** . Klicken Sie darauf, und klicken Sie dann auf die Schaltfläche **Richtlinien zurücksetzen**.
Andere MDM-Geräte, wie Android, Windows Phone 8.1 und höher sowie iOS, müssen möglicherweise außer Kraft gesetzt und bei dem Dienst neu registriert werden, damit Sie eine weniger restriktive Richtlinie anwenden können.

## Android-Geräte erzwingen keine Änderungen von Sicherheitsrichtlinien ohne die Genehmigung durch den Endbenutzer
Android-MDM gestattet dem Dienst nicht das Erzwingen von Änderungen an der anfänglichen Richtlinie auf Geräten, wie es andere Plattformen zulassen. Dies liegt an der Funktionalität von Android und steht in keinem Zusammenhang mit dem Intune-Dienst. Android-Geräte fordern den Endbenutzer über das Benachrichtigungsfenster der zugehörigen Richtlinienänderung auf (z. B. Kennwort, Verschlüsselung usw.).  Der Endbenutzer muss auf die Aufforderung reagieren, und nachdem er bestätigt hat, sollte die Richtlinie angewendet werden.

## Erstellen einer Richtlinie oder Registrieren von Clients ist nicht möglich, wenn der Firmenname Sonderzeichen enthält
**Problem:** Sie können keine Richtlinie erstellen bzw. keine Clients registrieren.

**Lösung**: Entfernen Sie im [Office 365 Admin Center](https://portal.office.com/) die Sonderzeichen aus den Firmennamen, und speichern Sie die Unternehmensinformationen.

### Nächste Schritte
Wenn diese Informationen zur Problembehandlung für Sie nicht hilfreich waren, wenden Sie sich wie in [Anfordern von Support für Microsoft Intune](how-to-get-support-for-microsoft-intune.md) beschrieben an den Microsoft Support.



<!--HONumber=Jul16_HO4-->


