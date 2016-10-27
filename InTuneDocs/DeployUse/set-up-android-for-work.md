---
title: "Einrichten der Verwaltung für Android for Work | Microsoft Intune"
description: "Aktivieren Sie die Verwaltung mobiler Geräte (Mobile Device Management, MDM) für Android for Work-Geräte mit Microsoft Intune."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b2fdcea9-9ad7-4d73-88e2-854b7a774bb2
translationtype: Human Translation
ms.sourcegitcommit: 519b66c94f3d056e060ed11e1a3d7d6d118a94fb
ms.openlocfilehash: 5f48303dd28627f961f8c2cfd38f8977354e2724


---

# Aktivieren der Registrierung von Android for Work-Geräten

Für die Aktivierung der Verwaltung von Android for Work-Geräten müssen Sie eine Android for Work-Bindung zu Intune hinzufügen. Zur Registrierung von Geräten, die Android for Work unterstützen, aber zuvor als reguläre Android-Geräte registriert wurden, muss die Registrierung der Geräte aufgehoben werden. Anschließend muss die Registrierung erneuert werden.

## Hinzufügen der Android for Work-Bindung für Intune

1. **Einrichten von Intune**<br>
Wenn nicht bereits geschehen, bereiten Sie die Verwaltung mobiler Geräte durch [Festlegen der Autorität für die Verwaltung mobiler Geräte](prerequisites-for-enrollment.md#set-mobile-device-management-authority) auf **Microsoft Intune** und Einrichten von MDM vor.

2. **Konfigurieren der Android for Work-Bindung**<br>
    Öffnen Sie als Administrator die [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com), wechseln Sie zu **Verwaltung** &gt; **Verwaltung mobiler Geräte** &gt; **Android for Work**, und klicken Sie auf **Konfigurieren**, um die Website von Android for Work unter Google Play zu öffnen. Diese wird in einer neuen Registerkarte im Browser geöffnet.

3. **Anmelden bei Google**<br>
   Melden Sie sich auf der Anmeldeseite von Google mit dem Google-Konto an, das allen Android for Work-Verwaltungsaufgaben für diesen Mandanten zugeordnet sein wird. Dies kann ein freigegebenes Google-Konto von Administratoren sein, die Intune verwalten. Dies ist das Google-Konto, das Ihre Organisation zum Verwalten und Veröffentlichen von Apps in der Play for Work-Konsole verwendet.

4. **Bereitstellen von Informationen zur Organisation**<br>
   Geben Sie den Namen Ihres Unternehmens für den **Organisationsnamen** ein. Für den **Enterprise Mobility Verwaltungsanbieter (EMM)** sollte *Microsoft Intune* angezeigt werden. Stimmen Sie der Android for Work-Vereinbarung zu, und klicken Sie auf **Bestätigen**. Ihre Anforderung wird verarbeitet.

## Angeben von Registrierungseinstellungen für Android for Work
   Android for Work wird nur auf bestimmten Android-Geräten unterstützt. Sehen Sie sich die [Voraussetzungen für Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window") an.  Jedes Gerät, das Android for Work unterstützt, unterstützt auch die herkömmliche Android-Verwaltung.  Mit Intune können Sie angeben, wie Geräte, die Android for Work unterstützen, verwaltet werden sollen:

   - **Alle Geräte als Android verwalten** – (Deaktiviert) Alle Android-Geräte, einschließlich Geräte, die Android for Work unterstützen, werden als herkömmliche Android-Geräte registriert.
   - **Unterstützte Geräte als Android for Work verwalten** – (Aktiviert) Alle Geräte,die Android for Work unterstützen, werden als Android for Work-Geräte registriert. Android-Geräte, die nicht Android for Work unterstützen, werden als herkömmliche Android-Geräte registriert.
   - **Unterstütze Geräte nur für Benutzer in den folgenden Benutzergruppen als Android for Work verwalten** – (In der Testphase) Sie können die Android for Work- Verwaltung auf eine begrenzte Anzahl von Benutzern ausrichten. Nur Geräte der Mitglieder der ausgewählten Gruppen, die ein Gerät registrieren, das Android for Work unterstützt, werden als Android for Work-Geräte registriert. Alle anderen werden als Android-Geräte registriert.

## Nächste Schritte für Android for Work
Nach der Konfiguration der Bindung und der Einstellung für Android for Work können Sie Folgendes tun:
- [Bereitstellen von Android for Work-Apps](android-for-work-apps.md)
- [Hinzufügen von Android for Work-Konfigurationsrichtlinien](android-for-work-policy-settings-in-microsoft-intune.md)

## Aufheben der Bindung Ihres Android for Work-Administratorkontos

Sie können die Registrierung und die Verwaltung von Android for Work deaktivieren. Wenn Sie auf **Unbind** (Bindung aufheben) klicken, werden alle registrierten Android for Work-Geräte aus der Registrierung entfernt und die Beziehung zwischen dem Android for Work-Konto und Intune wird entfernt.

### So trennen Sie ein Android for Work-Konto

1. **Trennen der Android for Work-Bindung**<br>
    Öffnen Sie als Administrator die [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com), wechseln Sie zu **Verwaltung** &gt; **Verwaltung mobiler Geräte** &gt; **Android for Work**, und klicken Sie auf **Bindung aufheben**.

2. **Dem Löschen der Android for Work-Bindung zustimmen**<br>
  Klicken Sie auf **Ja**, um die Bindung zu löschen und die Registrierung von allen Android for Work-Geräten von Intune aufzuheben.



<!--HONumber=Oct16_HO2-->


