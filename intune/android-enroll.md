---
title: "Registrieren von Android-Geräten in Intune"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie Android-Geräte in Intune registrieren.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ba809003dbdf63377a0b87b747c9865393786d72
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2017
---
# <a name="enroll-android-devices"></a>Registrieren von Android-Geräten

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Als Intune-Administrator können Sie Android-Geräte verwalten, einschließlich Samsung KNOX Standard-Geräte. Sie können auch das Arbeitsprofil auf Geräten verwalten: [Android for Work-Geräte](#enable-enrollment-of-android-for-work-devices).

Geräte, die mit Samsung KNOX Standard ausgeführt werden, werden für die Mehrbenutzerverwaltung von Intune unterstützt. Dies bedeutet, dass Endbenutzer sich auf dem Gerät mit ihren Azure AD-Anmeldeinformationen an- und wieder abmelden können, und das Gerät wird zentral verwaltet, ob es sich in Gebrauch befindet oder nicht. Wenn sich Endbenutzer anmelden, verfügen Sie über Zugriff auf Apps und erhalten zusätzlich alle Richtlinien, die ihnen zugewiesen sind. Wenn sich Benutzer abmelden, werden alle App-Daten gelöscht.

## <a name="prerequisite"></a>Voraussetzung

Sie müssen die MDM-Autorität auf **Microsoft Intune** festlegen, um die Verwaltung mobiler Geräte vorzubereiten. Anweisungen finden Sie unter [Festlegen der MDM-Autorität](mdm-authority-set.md). Sie legen dieses Element nur einmal fest, wenn Sie die Ersteinrichtung von Intune für die Verwaltung mobiler Geräte durchführen.

## <a name="set-up-android-enrollment"></a>Einrichten der Android-Registrierung

Standardmäßig erlaubt Intune die Registrierung von Android- und Samsung KNOX Standard-Geräten.

Um Android-Geräte oder nur die Registrierung von persönlichen Android-Geräten zu blockieren, gehen Sie unter [Festlegen von Gerätetypbeschränkungen](enrollment-restrictions-set.md).

Um die Geräteverwaltung zu aktivieren, müssen die Benutzer ihre Geräte durch Herunterladen der Intune-Unternehmensportal-App, die bei Google Play verfügbar ist, registrieren und anschließend die App öffnen und den Anweisungen zum Registrieren folgen. Sobald Android-Geräte verwaltet werden, können Sie [Konformitätsrichtlinien zuweisen](compliance-policy-create-android.md), [Apps verwalten](app-management.md) und mehr.

## <a name="enable-enrollment-of-android-for-work-devices"></a>Aktivieren der Registrierung von Android for Work-Geräten

Für die Aktivierung der Verwaltung von Arbeitsprofilen auf Geräten, die [Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) unterstützen, müssen Sie eine Android for Work-Bindung zu Intune hinzufügen. Zur Registrierung von Geräten, die Android for Work unterstützen, aber zuvor als reguläre Android-Geräte registriert wurden, muss die Registrierung der Geräte aufgehoben werden. Anschließend muss die Registrierung erneuert werden.

## <a name="add-android-for-work-binding-for-intune"></a>Hinzufügen der Android for Work-Bindung für Intune

1. **Einrichten von Intune MDM**<br>
Wenn nicht bereits geschehen, bereiten Sie die Verwaltung mobiler Geräte durch [Festlegen der Autorität für die Verwaltung mobiler Geräte](mdm-authority-set.md) auf **Microsoft Intune** vor.
2. **Konfigurieren der Android for Work-Bindung**<br>
    Wählen Sie als Intune-Administrator im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

    1. Wählen Sie auf dem Blatt **Intune** die Option **Geräteregistrierung**, > **Android for Work-Registrierung** aus, und klicken Sie dann auf **Konfigurieren**, um die Android for Work-Website von Google Play zu öffnen. Diese wird in einer neuen Registerkarte im Browser geöffnet.
  ![Screenshot: Link zum Konfigurieren der Android for Work-Bindung](./media/android-work-bind.png)

    2. **Anmelden bei Google**<br>
   Geben Sie auf der Anmeldeseite von Google das Google-Konto an, das allen Android for Work-Verwaltungsaufgaben für diesen Mandanten zugeordnet sein wird. Dies ist das Google-Konto, das von den IT-Administratoren Ihrer Organisation gemeinsam verwendet wird, die Apps in der Play for Work-Konsole verwalten.

    3. **Bereitstellen von Informationen zur Organisation**<br>
   Geben Sie den Namen Ihres Unternehmens für den **Organisationsnamen** ein. Für den **Enterprise Mobility Verwaltungsanbieter (EMM)** sollte *Microsoft Intune* angezeigt werden. Stimmen Sie der Android for Work-Vereinbarung zu, und klicken Sie auf **Bestätigen**. Ihre Anforderung wird verarbeitet.

## <a name="specify-android-for-work-enrollment-settings"></a>Angeben von Registrierungseinstellungen für Android for Work
   Android for Work wird nur auf bestimmten Android-Geräten unterstützt. Sehen Sie sich die [Voraussetzungen für Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window") an. Jedes Gerät, das Android for Work unterstützt, unterstützt auch die herkömmliche Android-Verwaltung.  Mit Intune können Sie angeben, dass Geräte, die Android for Work unterstützen, verwaltet werden sollen:

   - **Alle Geräte als Android verwalten**: Alle Android-Geräte, einschließlich Geräte, die Android for Work unterstützen, werden als herkömmliche Android-Geräte registriert.
   - **Unterstützte Geräte als Android for Work verwalten**: Alle Geräte,die Android for Work unterstützen, werden als Android for Work-Geräte registriert. Android-Geräte, die nicht Android for Work unterstützen, werden als herkömmliche Android-Geräte registriert.
   - **Unterstütze Geräte nur für Benutzer in den folgenden Benutzergruppen als Android for Work verwalten**: Sie können die Android for Work- Verwaltung auf eine begrenzte Anzahl von Benutzern ausrichten. Nur Geräte der Mitglieder der ausgewählten Gruppen, die ein Gerät registrieren, das Android for Work unterstützt, werden als Android for Work-Geräte registriert. Alle anderen werden als Android-Geräte registriert. Dies ist für Android for Work-Pilotprojekte nützlich.

<!--  ## Next steps for Android for Work
After configuring the Android for Work binding and settings, you can do the following:
- [Deploy Android for Work apps](android-for-work-apps.md)
- [Add Android for Work configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)  -->

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Kommunizieren der Geräteregistrierung für den Zugriff auf Unternehmensressourcen an die Benutzer

Ihre Endbenutzer müssen unter Google Play die Intune-Unternehmensportal-App herunterladen, sie dann öffnen und den Aufforderungen folgen, um ihr Gerät zu registrieren. Im Laufe des von der App geführten Registrierungsprozesses werden Benutzer darüber informiert, was sie erwarten können und was IT-Administratoren auf ihren Geräten sehen können und was nicht.

Sie können auch einen Link für Online-Registrierungsschritte senden: [Registrieren Ihres Android-Geräts bei Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).

Informationen zu anderen Endbenutzeraufgaben finden Sie in den folgenden Artikeln:

- [Ressourcen zu Endbenutzerszenarios in Microsoft Intune](end-user-educate.md)
- [Verwenden Ihres Android-Geräts mit Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

## <a name="unbinding-your-android-for-work-administrative-account"></a>Aufheben der Bindung Ihres Android for Work-Administratorkontos

Sie können die Registrierung und die Verwaltung von Android for Work deaktivieren. Wenn Sie in der Intune-Verwaltungskonsole auf **Unbind** (Bindung aufheben) klicken, werden alle registrierten Android for Work-Geräte aus der Registrierung entfernt und die Beziehung zwischen dem Android for Work-Konto und Intune wird entfernt.

### <a name="how-to-unbind-an-android-for-work-account"></a>So heben Sie die Bindung für ein Android for Work-Konto auf

1. **Aufheben der Android for Work-Bindung**<br>
    Wählen Sie als Intune-Administrator im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.  Wählen Sie auf dem Blatt **Intune** die Option **Geräteregistrierung**, > **Android for Work-Registrierung** aus, und klicken Sie dann auf **Bindung aufheben**.

2. **Zustimmen zum Löschen der Android for Work-Bindung**<br>
  Klicken Sie auf **Ja**, um die Bindung zu löschen und die Registrierung von allen Android for Work-Geräten von Intune aufzuheben.
