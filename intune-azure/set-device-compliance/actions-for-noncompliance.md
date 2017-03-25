---
title: "Aktionen bei Inkompatibilität"
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Hier erfahren Sie, wie Sie Aktionen für nicht kompatible Geräte erstellen."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d0e0c4b-a562-44f3-82a4-80eb688d4733
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: deea78dcea9ade031441bf12b388a862235a8e9c
ms.openlocfilehash: 16da087e741e335144266c838c0a91050bd7d520
ms.lasthandoff: 03/15/2017


---

# <a name="create-actions-for-non-compliance"></a>Erstellen von Aktionen für nicht kompatible Geräte

Mithilfe der **Aktionen bei Inkompatibilität** können Sie eine zeitlich strukturierte Aktionsfolge für Geräte konfigurieren, die die Kompatibilitätskriterien nicht mehr erfüllen. So können Sie beispielsweise Benutzer mit nicht kompatiblen Geräten per E-Mail informieren oder mithilfe von bedingtem Zugriff dafür sorgen, dass die betroffenen Geräte keinen Zugriff mehr auf Unternehmensressourcen haben.

## <a name="use-case-scenario"></a>Anwendungsfall

Wenn von einer Intune-Gerätekompatibilitätsrichtlinie ein nicht kompatibles Gerät gemeldet wird, wird das Gerät standardmäßig mittels bedingtem Zugriff blockiert, und der Benutzer erhält eine E-Mail mit Anweisungen zur Erfüllung der Kompatibilitätskriterien. Die **Aktionen bei Inkompatibilität** geben Ihnen mehr Entscheidungsfreiheit beim Umgang mit nicht kompatiblen Geräten. Sie können beispielsweise festlegen, dass das Gerät nicht sofort blockiert werden soll, und dem Benutzer eine Toleranzperiode einräumen, in der er dafür sorgen kann, dass das Gerät kompatibel ist.

Es gibt zwei Arten von Aktionen:

-   Benachrichtigen des Benutzers per E-Mail

-   Blockieren des Zugriffs auf Unternehmensressourcen mittels bedingtem Zugriff

## <a name="notify-the-user-via-email"></a>Benachrichtigen des Benutzers per E-Mail

Verwenden Sie entweder eine der vorgefertigten E-Mail-Standardvorlagen oder eine umfassend angepasste E-Mail-Benachrichtigung. Sie können Betreff, Nachrichtentext (einschließlich Unternehmenslogo), Kontaktinformationen und weitere Empfänger anpassen.

## <a name="block-corporate-resource-access-through-conditional-access"></a>Blockieren des Zugriffs auf Unternehmensressourcen mittels bedingtem Zugriff

Sie können einen Zeitplan konfigurieren, um anzugeben, für welchen Zeitraum (in Tagen) der Zugriff auf Unternehmensressourcen für das Gerät blockiert werden soll. Dieser Zeitraum kann sofort beginnen oder erst nach einer gewissen Toleranzperiode, um dem Benutzer Gelegenheit zu geben, die Gerätekompatibilitätsrichtlinien zu erfüllen.

## <a name="before-you-begin"></a>Vorbereitung

Für die Einrichtung von Aktionen bei Inkompatibilität benötigen Sie mindestens eine Gerätekompatibilitätsrichtlinie.

-   Plattformspezifische Informationen zum Erstellen einer Gerätekompatibilitätsrichtlinie finden Sie hier:

    -   [Android](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android)

    -   [Android for Work](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android-for-work)

    -   [iOS](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-ios)

    -   [Windows](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-windows)

Wenn Sie den Zugriff von Geräten auf Unternehmensressourcen mithilfe von Gerätekompatibilitätsrichtlinien sperren möchten, muss der bedingte Zugriff von EMS fertig eingerichtet sein.

- Wie das geht, erfahren Sie [hier](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access).

Darüber hinaus benötigen Sie eine Benachrichtigungsvorlage. Die Benachrichtigungsvorlage wird später beim Erstellen von Aktionen bei Inkompatibilität verwendet, um eine E-Mail an Ihre Benutzer zu senden.

### <a name="to-add-a-notification-message-template"></a>So fügen Sie eine Benachrichtigungsvorlage hinzu

Gehen Sie auf dem Blatt **Device compliance policies** (Gerätekompatibilitätsrichtlinien) wie folgt vor:

1.  Wählen Sie unter **Verwalten** die Option **Benachrichtigungen** aus, um das Blatt für Benachrichtigungsvorlagen zu öffnen.

    ![Vorgehensweise zum Hinzufügen einer Benachrichtigungsvorlage](../media/afnc-1.png)

2.  Wählen Sie **Hinzufügen** aus, und definieren Sie anschließend Folgendes:

    a.  Beschreibung

    b.  Von

    c.  Betreff

    d.  Nachricht

    e.  E-Mail-Kopfzeile: Unternehmenslogo einschließen

    f.  E-Mail-Fußzeile: Unternehmensnamen einschließen

    g.  E-Mail-Fußzeile: Kontaktinformationen einschließen

     ![Die Benachrichtigungsvorlage](../media/afnc-2.png)

Klicken Sie nach dem Hinzufügen der Informationen auf **Erstellen**. Die Benachrichtigungsvorlage kann nun verwendet werden.

> [!NOTE] 
> Sie können auch eine zuvor erstellte Benachrichtigungsvorlage bearbeiten.

## <a name="to-create-actions-for-non-compliance"></a>So erstellen Sie Aktionen bei Inkompatibilität

Eine Aktion kann beim Erstellen einer neuen Gerätekompatibilitätsrichtlinie oder beim Bearbeiten einer bereits vorhandenen Gerätekompatibilitätsrichtlinie hinzugefügt werden.

1.  Wählen Sie auf dem Blatt **Device compliance policies** (Gerätekompatibilitätsrichtlinien) unter **Verwalten** die Option **Richtlinien** aus.

2.  Klicken Sie auf eine Gerätekompatibilitätsrichtlinie, um sie auszuwählen.

    ![Kompatibilitätsrichtlinien](../media/afnc-3.png)

3.  Das Blatt mit den Eigenschaften für die Kompatibilitätsrichtlinie****wird geöffnet. Wählen Sie hier **Aktionen bei Inkompatibilität** aus.

4.  Wählen Sie auf dem Blatt „Aktionen bei Inkompatibilität“ die Option **Hinzufügen** aus, um Aktionsparameter anzugeben.

    ![Blatt „Aktionen bei Inkompatibilität“](../media/afnc-4.png)

Als Aktionen bei Inkompatibilität stehen folgende Optionen zur Verfügung:

-   **Als nicht kompatibel markieren**

-   **Benachrichtigung**

### <a name="enforce-conditional-access-policy"></a>„Als nicht kompatibel markieren“

Gehen Sie wie folgt vor, um diese Aktion bei Inkompatibilität hinzuzufügen:

1.  Wählen Sie auf dem Blatt **Aktionen bei Inkompatibilität** die Option **Hinzufügen** aus.

2.  Wählen Sie auf dem Blatt **Aktionsparameter** in der Dropdownliste mit den Aktionen die Option **Als nicht kompatibel markieren** aus.

3.  Unter **Zeitplan** können Sie die Anzahl von Tagen (0 bis 255) für die Erzwingung der Markierung angeben. Bei Angabe von **0** Tagen wird der Zugriff auf Unternehmensressourcen mittels bedingtem Zugriff **umgehend** blockiert, wenn die Geräte die Gerätekompatibilitätsrichtlinien nicht erfüllen.

    ![Planen von Aktionen bei Inkompatibilität](../media/afnc-5.png)

4.  Wählen Sie **Hinzufügen** und auf dem Blatt **Aktionen** anschließend **OK** aus.

5.  Wählen Sie auf dem Blatt mit den Eigenschaften für die Kompatibilitätsrichtlinie****die Option **Speichern** aus.

### <a name="send-e-mail-to-end-user"></a>„Benachrichtigung“

Sie können eine E-Mail-Vorlage an Benutzer mit nicht kompatiblen Geräten senden. Diese E-Mails fördern die Gerätekompatibilität im gesamten Unternehmen.

Gehen Sie wie folgt vor, um diese Aktion bei Inkompatibilität hinzuzufügen:

1.  Wählen Sie auf dem Blatt **Aktionen bei Inkompatibilität** die Option **Hinzufügen** aus.

2.  Wählen Sie auf dem Blatt **Aktionsparameter** in der Dropdownliste mit den Aktionen die Option **Benachrichtigung** aus.

3.  Klicken Sie auf **Nachrichtenvorlage**, und wählen Sie eine zuvor erstellte Nachrichtenvorlage aus. Sehen Sie sich ggf. den Inhalt der Nachrichtenvorlage an, und wählen Sie anschließend **Auswählen** aus.

    ![Nachrichtenvorlage](../media/afnc-6.png)

> [!NOTE] 
> Die Nachrichtenvorlage kann angezeigt, aber nicht bearbeitet werden. Zum Bearbeiten der Nachrichtenvorlage müssen Sie zum Blatt **Benachrichtigungen** zurückkehren.

1.  Geben Sie unter **Zeitplan** an, wie viele Tage nach Eintritt der Inkompatibilität die E-Mail an die Benutzer gesendet werden soll. Bei Angabe von **0** Tagen wird die E-Mail **umgehend** gesendet.

2.  Wählen Sie **Hinzufügen** und auf dem Blatt **Aktionen** anschließend **OK** aus.

3.  Wählen Sie auf dem Blatt mit den Eigenschaften für die Kompatibilitätsrichtlinie****die Option **Speichern** aus.

