---
# required metadata

title: Einstellungen für Nutzungsbedingungsrichtlinien in Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6edf0ac1-4f46-4543-a9e5-f484ac37e9a5

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Einstellungen für Nutzungsbedingungsrichtlinien in Microsoft Intune
Sie können Intune-Nutzungsbedingungen für Benutzergruppen bereitstellen, um zu erläutern, wie sich die Registrierung, der Zugriff auf Arbeitsressourcen und die Verwendung des Unternehmensportals auf Geräte und Benutzer auswirken. Benutzer müssen die Nutzungsbedingungen akzeptieren, bevor sie sich über das Unternehmensportal registrieren und auf ihre Arbeit zugreifen können.

Sie können mehrere Richtlinien erstellen und bereitstellen, die verschiedene Nutzungsbedingungen enthalten. Sie können auch Versionen derselben Nutzungsbedingungen in verschiedenen Sprachen erstellen und diese dann für die entsprechenden Gruppen bereitstellen.

## Erstellen einer Nutzungsbedingungsrichtlinie

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) auf **Richtlinie** &gt; **Nutzungsbedingungen**..

    ![Screenshot für Nutzungsbedingungsrichtlinien](./media/pol-sa-terms-conditions.png)

2.  Klicken Sie auf **Hinzufügen**, um eine neue Nutzungsbedingungsrichtlinie zu erstellen.

    Sie können auch eine vorhandene Richtlinie **bearbeiten** oder **löschen**.

3.  Geben Sie auf der Seite zum **Erstellen der Nutzungsbedingungen** die folgenden Informationen an:

    -   **Name**: Ein eindeutiger Richtlinienname, der in der Intune-Konsole angezeigt wird.

    -   **Beschreibung**: Details, die Ihnen dabei helfen, die Richtlinie in der Intune-Konsole zu identifizieren.

    -   **Titel**: Der Benutzern im Unternehmensportal angezeigte Titel.

    -   **Text zur Erläuterung der Bedeutung, wenn der Benutzer zustimmt**: Die für Benutzer angezeigte Bezeichnung hinsichtlich der Zustimmung. **Beispiel**: „Ich stimme den Nutzungsbedingungen zu.“

4.  Wenn Sie fertig sind, klicken Sie auf **Speichern**. Die neue Richtlinie wird im Knoten für die **Nutzungsbedingungen** des Arbeitsbereichs **Richtlinie** angezeigt.

## Bereitstellen einer Nutzungsbedingungsrichtlinie

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) auf **Richtlinie** &gt; **Nutzungsbedingungen**..

2.  Wählen Sie in der Liste der **Nutzungsbedingungsrichtlinien** die bereitzustellende Richtlinie aus, und klicken Sie dann auf **Bereitstellung verwalten**..

3.  Wählen Sie im Dialogfeld **Bereitstellung verwalten** die Gruppen aus, für die Sie die Richtlinie bereitstellen möchten, und klicken Sie dann auf **OK**..

    Wenn die anvisierten Benutzer auf das Unternehmensportal zugreifen, zeigt Intune die bereitgestellten Nutzungsbedingungen an. Benutzer müssen diese Nutzungsbedingungen akzeptieren, bevor sie Zugriff auf Unternehmensressourcen erhalten.

## Überwachen einer Nutzungsbedingungsrichtlinie

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) auf **Richtlinie** &gt; **Nutzungsbedingungen**..

2.  Klicken Sie im Fenster **Neuen Bericht erstellen** auf **Bericht anzeigen**. Der Bericht wird mit ausführlichen Informationen geöffnet, welche Benutzer die bereitgestellten Nutzungsbedingungen akzeptiert haben.

### Updates und Versionskontrolle für Nutzungsbedingungen
Beim Bearbeiten einer vorhandenen Nutzungsbedingungsrichtlinie können Sie das Verhalten auswählen, wenn Sie die Richtlinie bereitstellen. Verwenden Sie das folgende Verfahren beim Aktualisieren vorhandener Nutzungsbedingungsrichtlinien.

## Arbeiten mit mehreren Versionen der Nutzungsbedingungen

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) auf **Richtlinie** &gt; **Nutzungsbedingungen**..

2.  Wählen Sie die zu bearbeitende Nutzungsbedingungsrichtlinie aus, und klicken Sie dann auf **Bearbeiten**..

3.  Nehmen Sie auf der Seite zum **Bearbeiten der Nutzungsbedingungen** alle erforderlichen Änderungen vor, und geben Sie dann an, ob diese neue Version von allen Benutzern eine Zustimmung zu den Nutzungsbedingungen erfordert oder sie nur für neue Benutzer angezeigt wird.

    Es wird empfohlen, dass Sie die Versionsnummer erhöhen und jedes Mal die Zustimmung zu den Nutzungsbedingungen anfordern, wenn Sie wichtige Änderungen an der Nutzungsbedingungsrichtlinie vornehmen. Behalten Sie die aktuelle Versionsnummer bei, wenn Sie z. B. Tippfehler korrigieren oder die Formatierung ändern.

### Weitere Informationen:
[Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)


<!--HONumber=May16_HO1-->


