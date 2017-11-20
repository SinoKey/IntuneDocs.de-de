---
title: "Registrieren von Android-Geräten bei Intune | Microsoft-Dokumentation"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie Android-Geräte in Intune registrieren."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 68d93fe98b89f27c947e07d79eca9a0e02dea582
ms.sourcegitcommit: ce35790090ebe768d5f75c108e8d5934fd19c8c7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2017
---
# <a name="enroll-android-devices"></a>Registrieren von Android-Geräten

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Als Intune-Administrator können Sie Android-Geräte verwalten, einschließlich Geräte nach dem Samsung Knox-Standard. Sie können außerdem das Arbeitsprofil [Android for Work-Geräte](#enable-enrollment-of-android-for-work-devices) verwalten.

Geräte, die mit Samsung Knox-Standard ausgeführt werden, werden für die Mehrbenutzerverwaltung von Intune unterstützt. Dies bedeutet, dass Benutzer sich bei einem Gerät mit ihren Azure AD-Anmeldeinformationen an- und abmelden können. Das Gerät wird zentral verwaltet, ganz gleich, ob es verwendet oder nicht. Wenn sich Benutzer anmelden, verfügen sie über Zugriff auf Apps und erhalten zusätzlich alle Richtlinien, die ihnen zugewiesen sind. Wenn sich Benutzer abmelden, werden alle App-Daten gelöscht.

## <a name="prerequisite"></a>Voraussetzung

Um auf die Verwaltung von mobilen Geräten vorzubereiten, müssen Sie die MDM-Autorität (Mobile Device Management, Verwaltung mobiler Geräte) auf **Microsoft Intune** festlegen. Anweisungen finden Sie unter [Festlegen der MDM-Autorität](mdm-authority-set.md). Sie legen dieses Element nur einmal fest, wenn Sie die Ersteinrichtung von Intune für die Verwaltung mobiler Geräte durchführen.

## <a name="set-up-android-enrollment"></a>Einrichten der Android-Registrierung

Standardmäßig erlaubt Intune die Registrierung von Android- und Samsung KNOX Standard-Geräten.

Um Android-Geräte oder nur die Registrierung von persönlichen Android-Geräten zu blockieren, gehen Sie unter [Festlegen von Gerätetypbeschränkungen](enrollment-restrictions-set.md).

Um die Geräteverwaltung zu aktivieren, müssen die Benutzer ihre Geräte durch Herunterladen der Intune-Unternehmensportal-App (bei Google Play verfügbar) registrieren und anschließend die App öffnen und den Anweisungen folgen. Sobald Android-Geräte verwaltet werden, können Sie [Konformitätsrichtlinien zuweisen](compliance-policy-create-android.md), [Apps verwalten](app-management.md) und mehr.

## <a name="enable-enrollment-of-android-for-work-devices"></a>Aktivieren der Registrierung von Android for Work-Geräten

Für die Aktivierung der Verwaltung von Arbeitsprofilen auf Geräten, die [Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) unterstützen, müssen Sie eine Android for Work-Bindung zu Intune hinzufügen. Zur Registrierung von Geräten, die Android for Work unterstützen, aber zuvor als reguläre Android-Geräte registriert wurden, müssen Sie die Registrierung der Geräte aufheben und die Geräte anschließend erneut registrieren.

Wenn Sie Android for Work-Geräte mithilfe eines [Geräteregistrierungs-Manager](device-enrollment-manager-enroll.md)-Kontos registrieren, besteht pro Konto ein Grenzwert von 10 registrierbaren Geräten.

## <a name="add-android-for-work-binding-for-intune"></a>Hinzufügen der Android for Work-Bindung für Intune

1. **Einrichten von Intune MDM**<br>
Wenn nicht bereits geschehen, bereiten Sie die Verwaltung mobiler Geräte durch [Festlegen der Autorität für die Verwaltung mobiler Geräte](mdm-authority-set.md) auf **Microsoft Intune** vor.
2. **Konfigurieren der Android for Work-Bindung**<br>
    Wählen Sie als Intune-Administrator im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

   a. Wählen Sie auf dem Blatt **Intune** die Option **Geräteregistrierung**  > **Android for Work-Registrierung** und dann **Konfigurieren** aus, um die Android for Work-Website von Google Play zu öffnen. Die Website wird auf einer neuen Registerkarte im Browser geöffnet.
   ![Screenshot: Link zum Konfigurieren der Android for Work-Bindung](./media/android-work-bind.png)

   b. **Anmelden bei Google**<br>
   Geben Sie auf der Anmeldeseite von Google das Google-Konto an, das allen Android for Work-Verwaltungsaufgaben für diesen Mandanten zugeordnet sein wird. Dies ist das Google-Konto, das von den IT-Administratoren Ihres Unternehmens gemeinsam zum Verwalten und Veröffentlichen von Apps in der Play for Work-Konsole verwendet wird.

   c. **Bereitstellen von Informationen zur Organisation**<br>
   Geben Sie den Namen Ihres Unternehmens als **Organisationsnamen** ein. Für den **Enterprise Mobility Verwaltungsanbieter (EMM)** sollte **Microsoft Intune** angezeigt werden. Stimmen Sie der Android for Work-Vereinbarung zu, und wählen Sie dann **Bestätigen** aus. Ihre Anforderung wird verarbeitet.

## <a name="specify-android-for-work-enrollment-settings"></a>Angeben von Registrierungseinstellungen für Android for Work
   Android for Work wird nur auf bestimmten Android-Geräten unterstützt. Sehen Sie sich die [Voraussetzungen für Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window") an. Jedes Gerät, das Android for Work unterstützt, unterstützt auch die herkömmliche Android-Verwaltung. Mit Intune können Sie angeben, dass Geräte, die Android for Work unterstützen, verwaltet werden sollen:

   - **Alle Geräte als Android-Geräte verwalten** Alle Android-Geräte, einschließlich der Geräte, die Android for Work unterstützen, werden als herkömmliche Android-Geräte registriert.
   - **Unterstützte Geräte als Android for Work-Geräte verwalten** Alle Geräte, die Android for Work unterstützen, werden als Android for Work-Geräte registriert. Android-Geräte, die nicht Android for Work unterstützen, werden als herkömmliche Android-Geräte registriert.
   - **Nur unterstützte Geräte für Benutzer in diesen Benutzergruppen als Android for Work-Geräte verwalten** Sie können eine eingeschränkte Zielbenutzergruppe für die Verwaltung mit Android for Work festlegen. Nur Geräte der Mitglieder der ausgewählten Gruppen, die ein Gerät registrieren, das Android for Work unterstützt, werden als Android for Work-Geräte registriert. Alle anderen werden als Android-Geräte registriert. Dies ist für Android for Work-Pilotprojekte nützlich.

<!--  ## Next steps for Android for Work
After configuring the Android for Work binding and settings, you can do the following:
- [Deploy Android for Work apps](android-for-work-apps.md)
- [Add Android for Work configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)  -->

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Kommunizieren der Geräteregistrierung für den Zugriff auf Unternehmensressourcen an die Benutzer

Informieren Sie Ihre Benutzer, dass sie die Intune-Unternehmensportal-App von Google Play herunterladen, sie dann öffnen und den Aufforderungen folgen müssen, um ihr Gerät zu registrieren. Im Laufe des von der App geführten Registrierungsprozesses werden Benutzer darüber informiert, was sie erwarten können und was IT-Administratoren auf ihren Geräten sehen können und was nicht.

Sie können auch einen Link für Online-Registrierungsschritte senden: [Registrieren Ihres Android-Geräts bei Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).

Informationen zu anderen Benutzeraufgaben finden Sie in den folgenden Artikeln:

- [Ressourcen zu Endbenutzerszenarios in Microsoft Intune](end-user-educate.md)
- [Verwenden Ihres Android-Geräts mit Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

## <a name="unbind-your-android-for-work-administrative-account"></a>Aufheben der Bindung Ihres Android for Work-Administratorkontos

Sie können die Registrierung und die Verwaltung von Android for Work deaktivieren. Durch Auswählen von **Bindung aufheben** in der Intune-Verwaltungskonsole wird die Registrierung aller registrierten Android for Work-Geräte aufgehoben. Außerdem wird die Beziehung zwischen dem Android for Work-Konto und Intune entfernt.

### <a name="to-unbind-an-android-for-work-account"></a>Aufheben der Bindung für ein Android for Work-Konto

1. **Aufheben der Android for Work-Bindung**<br>
    Wählen Sie als Intune-Administrator im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.  Wählen Sie auf dem Blatt **Intune** die Option **Geräteregistrierung** > **Android for Work-Registrierung** und dann **Bindung aufheben** aus.

2. **Zustimmen zum Löschen der Android for Work-Bindung**<br>
  Wählen Sie **Ja** aus, um die Bindung zu löschen und die Registrierung von allen Android for Work-Geräten in Intune aufzuheben.
