---
title: "Aktionen bei Inkompatibilität mit Intune"
titleSuffix: Intune on Azure
description: "Erfahren Sie, wie Sie Aktionen für Inkompatibilität mit Intune erstellen."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 01/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 573a8b000e63576f3dd3bae1b6e8e8c47733f6bf
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2018
---
# <a name="automate-actions-for-noncompliance"></a>Automatisieren von Aktionen bei Inkompatibilität

Mithilfe der **Aktionen bei Inkompatibilität** können Sie eine zeitlich strukturierte Aktionsfolge für Geräte konfigurieren, die die Kriterien der Kompatibilitätsrichtlinie nicht erfüllen. Intune markiert ein Gerät standardmäßig als „nicht kompatibel“, wenn erkannt wird, dass dieses die Kriterien der Konformitätsrichtlinie nicht erfüllt. Das Gerät wird dann durch den bedingten Zugriff mit Azure AD blockiert. Die **Aktionen bei Inkompatibilität** geben Ihnen mehr Entscheidungsfreiheit beim Umgang mit nicht kompatiblen Geräten. Sie können beispielsweise festlegen, dass das Gerät nicht sofort blockiert werden soll, und dem Benutzer eine Toleranzperiode einräumen, in der er dafür sorgen kann, dass das Gerät kompatibel ist.

Es gibt zwei Arten von Aktionen:

-   **Benachrichtigen der Benutzer per E-Mail**: Sie können Ihre E-Mail-Benachrichtigung anpassen, bevor Sie diese an Benutzer senden. Mithilfe von Intune können Sie Empfänger, Betreff, Nachrichtentext (einschließlich Unternehmenslogo) und Kontaktinformationen anpassen.

    Darüber hinaus bezieht Intune Einzelheiten zu dem nicht kompatiblen Gerät in die E-Mail-Benachrichtigung ein.

-   **Markieren des Geräts als nicht konform**: Sie können einen Zeitplan mit der Anzahl von Tagen festlegen, nach der ein Gerät als „nicht konform“ markiert wird. Sie können die Aktion so konfigurieren, dass sie sofort wirksam wird oder erst nach einer gewissen Toleranzperiode, um dem Benutzer Gelegenheit zu geben, Ihre Gerätekonformitätsrichtlinien zu erfüllen.

## <a name="before-you-begin"></a>Vorbereitung

Für die Einrichtung von Aktionen bei Inkompatibilität benötigen Sie mindestens eine Gerätekompatibilitätsrichtlinie. 

- Lesen Sie die plattformspezifischen Informationen zum Erstellen einer Gerätekonformitätsrichtlinie:

    -   [Android](compliance-policy-create-android.md)
    -   [Android for Work](compliance-policy-create-android-for-work.md)
    -   [iOS](compliance-policy-create-ios.md)
    -   [macOS](compliance-policy-create-mac-os.md)
    -   [Windows](compliance-policy-create-windows.md)

Wenn Sie den Zugriff von Geräten auf Unternehmensressourcen mithilfe von Gerätekompatibilitätsrichtlinien sperren möchten, muss der bedingte Zugriff von Azure AD fertig eingerichtet sein. 

- Erfahren Sie, [wie Sie bedingten EMS-Zugriff einrichten](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access).

Darüber hinaus benötigen Sie eine Benachrichtigungsvorlage. Die Benachrichtigungsvorlage wird später beim Erstellen von Aktionen bei Inkompatibilität verwendet, um eine E-Mail an Ihre Benutzer zu senden.

### <a name="to-create-a-notification-message-template"></a>Erstellen einer Benachrichtigungsvorlage

1. Navigieren Sie zu [Intune im Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Intune-Anmeldeinformationen an.
2. Wählen Sie im linken Menü **Weitere Dienste** aus, und geben Sie in das Filtertextfeld die Zeichenfolge **Intune** ein.
3. Wählen Sie **Intune** aus.
4. Wählen Sie **Gerätekompatibilität** und dann **Benachrichtigungen** im Abschnitt **Verwalten** aus.
5. Wählen Sie **Benachrichtigung erstellen** aus, und geben Sie folgende Informationen ein:
    - Name
    - Antragsteller
    - Nachricht
    - E-Mail-Kopfzeile: Unternehmenslogo einschließen
    - E-Mail-Fußzeile: Unternehmensnamen einschließen
    - E-Mail-Fußzeile: Kontaktinformationen einschließen

5. Wählen Sie **Benachrichtigung erstellen** aus, und geben Sie folgende Informationen ein:

    ein. Name

    b. Antragsteller

    c.  Nachricht

    d. E-Mail-Kopfzeile: Unternehmenslogo einschließen

    e. E-Mail-Fußzeile: Unternehmensnamen einschließen

    f. E-Mail-Fußzeile: Kontaktinformationen einschließen

![Beispiel für die Benachrichtigungsvorlage](./media/actionsfornoncompliance-1.PNG)

Klicken Sie auf **Erstellen**, sobald Sie die Informationen hinzugefügt haben. Die Benachrichtigungsvorlage kann nun verwendet werden.

> [!NOTE]
> Sie können auch eine zuvor erstellte Benachrichtigungsvorlage bearbeiten.

## <a name="to-create-actions-for-noncompliance"></a>So erstellen Sie Aktionen bei Nichteinhaltung

> [!TIP]
> Intune stellt standardmäßig eine vordefinierte Aktion in den Aktionen für den Abschnitt „Inkompatibilität“ bereit. Mit der Aktion wird ein Gerät als „nicht konform“ markiert, nachdem erkannt wurde, dass dieses die Kriterien Ihrer Gerätekonformitätsrichtlinie nicht erfüllt. Sie können anpassen, wann das Gerät nach der Erkennung als „nicht konform“ markiert wird. Die Aktion kann nicht entfernt werden.

Eine Aktion kann beim Erstellen einer neuen Gerätekonformitätsrichtlinie oder beim Bearbeiten einer bereits vorhandenen Gerätekonformitätsrichtlinie hinzugefügt werden.

1.  Wählen Sie auf dem Blatt **Richtlinien zur Gerätekompatibilität** in der Intune-Workload **Richtlinien** im Abschnitt **Verwalten** aus.

2.  Wählen Sie eine Richtlinie zur Gerätekompatibilität aus, indem Sie auf diese klicken, und klicken Sie dann auf **Eigenschaften** im Abschnitt **Verwalten**.

3.  Das Blatt mit den **Eigenschaften für die Kompatibilitätsrichtlinie** wird geöffnet. Wählen Sie hier **Aktionen bei Inkompatibilität** aus.

4.  Wählen Sie auf dem Blatt **Aktionen bei Inkompatibilität** die Option **Hinzufügen** aus, um Aktionsparameter anzugeben. Sie können die zuvor erstellte Benachrichtigungsvorlage, zusätzliche Empfänger und die Toleranzperiode des Zeitplans auswählen. Im Zeitplan können Sie die Anzahl von Tagen (0 bis 365) angeben und dann die Richtlinien für den bedingten Zugriff erzwingen. Bei Angabe von **0** Tagen wird der Zugriff auf Unternehmensressourcen mittels bedingtem Zugriff **umgehend** blockiert, wenn die Geräte die Gerätekompatibilitätsrichtlinien nicht erfüllen.

5.  Klicken Sie auf **Hinzufügen** und dann auf **OK**, wenn Sie Ihre Informationen hinzugefügt haben.

## <a name="next-steps"></a>Nächste Schritte
Sie können die Aktivitäten der Gerätekompatibilität überwachen, indem Sie die auf dem Blatt „Gerätekompatibilität“ verfügbaren Berichte ausführen. Erfahren Sie mehr über das [Überwachen der Gerätekonformität in Intune](device-compliance-monitor.md).
