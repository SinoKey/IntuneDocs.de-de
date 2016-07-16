---
title: "Verwalten von Einstellungen und Features auf Ihren Geräten mit Richtlinien | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 06/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 09bae0b9-4f79-4658-8ca1-a71ab992c1b2
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f33a86c51320c75ce74d20e0cac2b9581990ecec
ms.openlocfilehash: ab570d551189ec71b54081229b93d7b4ce8d58d5


---

# Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien
Microsoft Intune-**Richtlinien** sind Gruppen von Einstellungen zur Steuerung der Features auf mobilen Geräten und Computern. Sie erstellen Richtlinien mithilfe von Vorlagen, in denen empfohlene oder angepasste Einstellungen enthalten sind, und stellen diese dann für Geräte- oder Benutzergruppen bereit.

## Welche Arten von Richtlinien können Sie verwenden?

Intune-Richtlinien lassen sich in die folgenden Kategorien einteilen: Welche Kategorie Sie verwenden, bestimmt, wie Sie die Richtlinie erstellen und bereitstellen können.


- **Konfigurationsrichtlinien:** Diese werden häufig zum Verwalten von Sicherheitseinstellungen und -features auf Ihren Geräten verwendet. Verwenden Sie die Informationen in diesem Thema, um mehr über das Erstellen und Bereitstellen dieser Richtlinien und die verfügbaren Einstellungen zu erfahren.
- **Gerätekompatibilitätsrichtlinien:** Diese definieren die Regeln und Einstellungen, die ein Gerät erfüllen muss, damit es als kompatibel mit Richtlinien für bedingten Zugriff eingestuft wird. Kompatibilitätsrichtlinien ermöglichen Ihnen auch, die Kompatibilität von Geräten unabhängig von bedingten Zugriffsrechten zu überwachen und zu beheben.
Weitere Informationen finden Sie unter [Gerätekompatibilitätsrichtlinien in Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md).
- **Richtlinien für bedingten Zugriff:** Mit diesen Richtlinien können Sie E-Mail- und andere Dienste basierend auf Bedingungen schützen, die Sie festlegen.
Weitere Informationen finden Sie unter [Beschränken des Zugriffs auf E-Mail- und Office 365-Dienste mit Microsoft Intune](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).
- **Richtlinien zum Registrieren unternehmenseigener Geräte:** Informationen zu Richtlinien zum Registrieren unternehmenseigener Geräte finden Sie unter [Einrichten der iOS- und Mac-Verwaltung mit Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md).
- **Ressourcenzugriffsrichtlinien:** Diese Gruppe von Richtlinien ermöglicht Benutzern den Zugriff auf die Dateien und Ressourcen, die sie für ihre Arbeit benötigen, und zwar unabhängig davon, wo sie gespeichert sind.
Weitere Informationen finden Sie unter [Aktivieren des Zugriffs auf Unternehmensressourcen mit Microsoft Intune](enable-access-to-company-resources-with-microsoft-intune.md).


Eine vollständige Liste der Intune-Richtlinien finden Sie unter [Referenz zu Microsoft Intune-Richtlinien](microsoft-intune-policy-reference.md).




## Erstellen einer Konfigurationsrichtlinie

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Optionen **Richtlinie** &gt; **Konfigurationsrichtlinien** &gt; **Hinzufügen**.

2.  Wählen Sie die gewünschte Richtlinie aus, und wählen Sie, ob Sie die empfohlenen Einstellungen für die Richtlinie verwenden (sofern verfügbar, Sie können diese Einstellungen später ändern) oder eine benutzerdefinierte Richtlinie mit Ihren eigenen Einstellungen erstellen möchten.

    > [!TIP]
    > Hilfe zur Auswahl der richtigen Richtlinie finden Sie in der [Referenz zu Microsoft Intune-Richtlinien](microsoft-intune-policy-reference.md).

3.  Wenn Sie bereit sind, wählen Sie **Richtlinie erstellen**.

4.  Konfigurieren Sie im Bildschirm **Richtlinie erstellen** einen Namen und optional eine Beschreibung für die Richtlinie.

5.  Konfigurieren Sie die erforderlichen Richtlinieneinstellungen, und wählen Sie dann **Richtlinie speichern**.

    Wenn Sie Hilfe zu Richtlinieneinstellungen benötigen, wählen Sie Ihren Richtlinientyp aus der folgenden Liste aus:

    - [Einstellungen für iOS-Geräte](ios-policy-settings-in-microsoft-intune.md)
    - [Einstellungen für Android-Geräte](android-policy-settings-in-microsoft-intune.md)
    - [Einstellungen für Geräte mit Windows 8 und Windows 8.1](windows-configuration-policy-settings-in-microsoft-intune.md)
    - [Einstellungen für Geräte mit Windows Phone 8.1](windows-phone-8-1-policy-settings-in-microsoft-intune.md)
    - [Einstellungen für Desktop- und mobile Geräte mit Windows 10](windows-10-policy-settings-in-microsoft-intune.md)
    - [Einstellungen für Windows Team-Geräte](windows-team-configuration-policy-settings-in-microsoft-intune.md)
    - [Upgradeeinstellungen für die Windows-Edition](edition-upgrade-policy-settings-in-microsoft-intune.md)
    - [Einstellungen für Mac OS X-Geräte](mac-os-x-policy-settings-in-microsoft-intune.md)
    - [Einstellungen für Exchange ActiveSync](exchange-activesync-policy-settings-in-microsoft-intune.md)
    - [Einstellungen für Nutzungsbedingungsrichtlinien](terms-and-condition-policy-settings-in-microsoft-intune.md)
    - [Allgemeine Einstellungen für mobile Geräte (Legacy)](mobile-device-security-policy-settings-in-microsoft-intune.md)

4.  Wählen Sie im Bestätigungsdialogfeld **Ja**, um die Richtlinie jetzt bereitzustellen, oder **Nein**, um die Richtlinie zu erstellen, ohne sie bereitzustellen.

Sie können die neue Richtlinie anzeigen und bearbeiten, indem Sie durch die Abschnitte für die einzelnen Richtlinientypen im Arbeitsbereich **Richtlinie** navigieren.

Wenn sie eine Richtlinie erstellen, bei der die empfohlenen Einstellungen verwendet werden, setzt sich der Name der neuen Richtlinie aus dem Vorlagennamen, dem Datum und der Uhrzeit zusammen. Bearbeiten Sie die Richtlinie, dann werden Datum und Uhrzeit im Namen entsprechend dem Zeitpunkt der Bearbeitung angepasst.

Nachdem Sie nun eine Richtlinie erstellt haben, werden Sie sie in der Regel für eine oder mehrere Gruppen von Benutzern oder Geräten bereitstellen.

> [!TIP]
> Sie stellen nicht alle Richtlinientypen bereit. Beispielsweise wird die mobile Anwendungsverwaltungsrichtlinie nicht bereitgestellt. Diese Richtlinie wird stattdessen einer App zugeordnet, die Sie dann bereitstellen.

## Bereitstellen einer Konfigurationsrichtlinie

1.  Wählen Sie im Arbeitsbereich **Richtlinie** die Richtlinie aus, die Sie bereitstellen möchten, und wählen Sie dann **Bereitstellung verwalten** aus.

2.  Führen Sie im Dialogfeld **Bereitstellung verwalten** folgende Schritte aus:

    -   **So stellen Sie die Richtlinie bereit**: Wählen Sie mindestens eine Gruppe aus, für die Sie die Richtlinie bereitstellen möchten, und klicken Sie auf **Hinzufügen** &gt; **OK**.

    -   **So schließen Sie das Dialogfeld, ohne die Richtlinie bereitzustellen**: Klicken Sie auf **Abbrechen**.

Wenn Sie eine bereitgestellte Richtlinie auswählen, können Sie weitere Informationen zur Bereitstellung im unteren Teil der Richtlinienliste anzeigen.

## Verwalten von Richtlinien

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Richtlinie**, navigieren Sie zu der Richtlinie, die Sie verwalten möchten, und wählen Sie sie aus.

2.  Wählen Sie eine der folgenden Aktionen aus:

- **Bearbeiten:** Hiermit werden die Eigenschaften für die ausgewählte Richtlinie geöffnet, und Sie können Änderungen daran vornehmen.
- **Löschen:** Hiermit wird die ausgewählte Richtlinie gelöscht.<br>Wenn Sie eine Richtlinie löschen, wird sie aus allen Gruppen entfernt, für die sie bereitgestellt worden war.
- **Bereitstellung verwalten:** Wählen Sie die Gruppe aus, für die Sie die Richtlinie bereitstellen möchten, und wählen Sie dann **Hinzufügen**.


## Häufig gestellte Fragen zu Intune-Richtlinien

### Wie lange dauert es für mobile Geräte, bis Richtlinien oder Apps nach ihrer Bereitstellung abgerufen werden?
Wenn eine Richtlinie oder Anwendung bereitgestellt wird, beginnt Intune sofort mit dem Versuch, das Gerät zu benachrichtigen und zum Einchecken beim Intune-Dienst zu veranlassen. Dies dauert normalerweise weniger als 5 Minuten.

Wenn ein Gerät sich nach der ersten Benachrichtigung nicht zum Abrufen der Richtlinie eincheckt, werden drei weitere Versuche unternommen.  Wenn das Gerät offline ist (z. B. abgeschaltet oder nicht mit einem Netzwerk verbunden), erhält es die Benachrichtigungen möglicherweise nicht.

In diesem Fall erhält das Gerät die Richtlinie beim nächsten geplanten Einchecken beim Intune-Dienst wie folgt:

- iOS und Mac OS X: alle sechs Stunden
- Android: alle 8 Stunden
- Windows Phone: alle 8 Stunden
- Registrierte Windows RT-Geräte: alle 24 Stunden
- Als Geräte registrierte PCs mit Windows 8.1 und 10: alle 8 Stunden

Wenn das Gerät gerade registriert wurde, ist die Eincheckfrequenz höher:

- iOS und Mac OS X: sechs Stunden lang alle 15 Minuten, danach alle sechs Stunden
- Android: 15 Minuten lang alle 3 Minuten, danach 2 Stunden lang alle 15 Minuten, anschließend alle 8 Stunden
- Windows Phone: 15 Minuten lang alle 5 Minuten, danach 2 Stunden lang alle 15 Minuten, anschließend alle 8 Stunden
- Windows-PCs, die als Geräte registriert sind: 30 Minuten lang alle drei Minuten, danach alle acht Stunden

Benutzer können auch jederzeit die Unternehmensportal-App starten und das Gerät synchronisieren, um sofort auf Richtlinien zu prüfen.

### Bei welchen Aktionen sendet Intune sofort eine Benachrichtigung an ein Gerät?
Geräte checken bei Intune entweder beim Erhalt einer Benachrichtigung ein, die sie dazu auffordert, oder während ihres regelmäßigen geplanten Eincheckvorgangs, wie in den obigen Tabellen beschrieben.  Wenn Sie für ein Gerät oder einen Benutzer ausdrücklich eine Aktion durchführen wie Zurücksetzen, Sperren, Zurücksetzen der Kennung, App-Bereitstellung, Profilbereitstellung (WLAN, VPN, E-Mail usw.) oder Bereitstellung der Richtlinie, beginnt Intune sofort mit dem Versuch, das Gerät darauf hinzuweisen, dass es sich zum Erhalten dieser Updates beim Intune-Dienst einchecken soll.

Andere Änderungen, wie z. B. die Überarbeitung der Kontaktinformationen im Unternehmensportal, führen nicht zu einer sofortigen Benachrichtigung von Geräten.

> [!TIP]
> Wenn eine Richtlinie mit Einstellungen auf einem Android-Gerät bereitgestellt wird, wird der Benutzer aufgefordert, die entsprechende Maßnahme zu ergreifen, um der Richtlinie zu entsprechen. Bis der Benutzer diese Aktion durchgeführt hat oder das Gerät neu gestartet wird, werden die neuen Richtlinieneinstellungen nicht wirksam.

### Wie finde ich heraus, welche Einstellungen angewendet werden, wenn für denselben Benutzer oder dasselbe Gerät mehrere Richtlinien bereitgestellt werden?
Bei Bereitstellung mehrerer Richtlinien für denselben Benutzer oder dasselbe Gerät ist es wichtig zu wissen, dass die Bewertung für die jeweils anwendbare Einstellung auf der Ebene einzelner Einstellungen erfolgt.

-   Kompatibilitätsrichtlinieneinstellungen haben immer Vorrang vor Konfigurationsrichtlinieneinstellungen

-   Die restriktivste Kompatibilitätsrichtlinie wird angewendet, wenn sie gegen dieselbe Einstellung in einer anderen Kompatibilitätsrichtlinie ausgewertet wird

-   Falls eine Konfigurationsrichtlinieneinstellung im Konflikt mit einer Einstellung in einer anderen Konfigurationsrichtlinie steht, wird dieser Konflikt in der Intune-Konsole angezeigt. Konflikte dieser Art müssen Sie manuell auflösen.

### Was geschieht, wenn MAM-Richtlinien (mobile Anwendungsverwaltung) miteinander in Konflikt stehen? Welche wird auf die App angewendet?
Konfliktwerte sind die restriktivsten Einstellungen, die in einer mobilen Anwendungsverwaltungsrichtlinie zur Verfügung stehen, außer für die Zahleneingabefelder (z. B. PIN-Versuche vor dem Zurücksetzen).  Die Zahleneingabefelder werden auf dieselben Werte gesetzt, die auch verwendet werden, wenn Sie eine MAM-Richtlinie in der Konsole mit der Option der empfohlenen Einstellungen erstellen.

Konflikte treten auf, wenn zwei Richtlinieneinstellungen identisch sind.  Beispielsweise haben Sie zwei MAM-Richtlinien konfiguriert, die mit Ausnahme der Einstellung für Kopieren/Einfügen identisch sind.  In diesem Szenario wird die Einstellung für Kopieren und Einfügen auf den restriktivsten Wert festgelegt, die übrigen Einstellungen werden jedoch wie konfiguriert angewendet.

Wenn eine Richtlinie für die Anwendung bereitgestellt wird und in Kraft tritt und anschließend eine weitere bereitgestellt wird, erhält die zuerst bereitgestellte Richtlinie Vorrang und bleibt wirksam, während die zweite als in Konflikt stehend angezeigt wird. Wenn sie jedoch beide gleichzeitig angewendet werden, sodass es keine vorhergehende Richtlinie gibt, befinden sich beide im Konflikt, und alle in Konflikt stehenden Einstellungen werden auf die restriktivsten Werte festgelegt.

### Was geschieht, wenn Sie benutzerdefinierte iOS-Richtlinien in Konflikt stehen?
Intune bewertet nicht die Nutzlast von Apple-Konfigurationsdateien oder der benutzerdefinierten OMA-URI-Richtlinie, es dient lediglich als Übermittlungsmechanismus.

Wenn Sie daher eine benutzerdefinierte Richtlinie bereitstellen, stellen Sie sicher, dass die konfigurierten Einstellungen nicht mit Kompatibilitäts-, Konfigurations- oder anderen benutzerdefinierten Richtlinien in Konflikt stehen. Bei einer benutzerdefinierten Richtlinie mit Einstellungskonflikten werden die Einstellungen in zufälliger Reihenfolge angewendet.

### Was geschieht, wenn eine Richtlinie gelöscht wird oder nicht mehr gilt?
Wenn Sie eine Richtlinie löschen oder ein Gerät aus einer Gruppe entfernen, für die eine Richtlinie bereitgestellt wurde, werden die Richtlinie und die Einstellungen entsprechend den folgenden Tabellen vom Gerät entfernt:

#### Angemeldete Geräte

- WLAN-, VPN-, Zertifikat- und E-Mail-Profile: Diese Profile werden von allen unterstützten registrierten Geräten entfernt.
- Alle anderen Richtlinientypen
    - **Windows- und Android-Geräte**: Einstellungen werden nicht vom Gerät entfernt.
    - **Windows Phone 8.1-Geräte**: Die folgenden Einstellungen werden entfernt:
        - Anfordern eines Kennworts zum Entsperren mobiler Geräte
        - Einfache Kennwörter zulassen
        - Minimale Kennwortlänge
        - Erforderlicher Kennworttyp
        - Kennwortablauf (Tage)
        - Kennwortverlauf speichern
        - Anzahl zulässiger wiederholter Anmeldefehler, bevor das Gerät zurückgesetzt wird
        - Minuten der Inaktivität, bevor ein Kennwort erforderlich ist
        - Erforderlicher Kennworttyp – Mindestanzahl von Zeichensätzen
        - Kamera zulassen
        - Verschlüsselung auf mobilem Gerät anfordern
        - Wechselspeichermedien zulassen
        - Webbrowser zulassen
        - App Store zulassen
        - Bildschirmaufnahme zulassen
        - Geolocation zulassen
        - Microsoft-Konto zulassen
        - Kopieren und Einfügen zulassen
        - WLAN-Tethering zulassen
        - Automatische Verbindung mit unverschlüsselten WLAN-Hotspots zulassen
        - Berichterstellung für WLAN-Hotspots zulassen
        - Zurücksetzen auf Werkseinstellungen zulassen
        - Bluetooth zulassen
        - NFC zulassen
        - WLAN zulassen
    
    - **iOS**: Alle Einstellungen werden entfernt, außer:
        - Sprachroaming zulassen
        - Datenroaming zulassen
        - Automatische Synchronisierung beim Roaming zulassen

#### Windows-PCs, auf denen die Intune-Clientsoftware ausgeführt wird

- **Endpoint Protection-Einstellungen:** Die Einstellungen werden auf die empfohlenen Werte zurückgesetzt. Die einzige Ausnahme ist die Einstellung **Microsoft Active Protection Service beitreten** , deren Standardwert **Nein**lautet. Weitere Informationen finden Sie unter [Schützen von Windows-PCs mit Endpoint Protection für Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).
- **Einstellungen für Softwareupdates:** Die Einstellungen werden auf die Standardwerte des Betriebssystems zurückgesetzt. Weitere Informationen finden Sie unter [Aktualisieren Ihrer Windows-PCs mit Softwareupdates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).
- **Microsoft Intune Center-Einstellungen:** Alle den Supportvertrag betreffenden Informationen, die durch die Richtlinie definiert waren, werden von den Computern gelöscht.
- **Einstellungen für die Windows-Firewall:** Die Einstellungen werden auf die Standardwerte des Computerbetriebssystems zurückgesetzt. Weitere Informationen finden Sie unter [Schützen von Windows-PCs mit Endpoint Protection für Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).


### Wie kann ich die Richtlinien auf einem Gerät aktualisieren und so sicherstellen, dass sie aktuell sind (gilt nur für Windows-PCs, auf denen die Intune-Clientsoftware ausgeführt wird)

1.  Wählen Sie in einer beliebigen Gerätegruppe die Geräte aus, auf denen die Richtlinien aktualisiert werden sollen, und wählen Sie dann **Remoteaufgaben** &gt; **Richtlinien aktualisieren**.
2.  Wählen Sie in der Intune-Verwaltungskonsole unten rechts die Option **Remoteaufgaben**, um den Aufgabenstatus zu überprüfen.

### Wo finde ich Hilfe zur Problembehandlung bei Richtlinien?

Siehe [Behandlung von Problemen mit Richtlinien in Microsoft Intune](/intune/troubleshoot/troubleshoot-policies-in-microsoft-intune).



<!--HONumber=Jun16_HO4-->


