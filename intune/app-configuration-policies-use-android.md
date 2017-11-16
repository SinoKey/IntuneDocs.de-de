---
title: "Hinzufügen von App-Konfigurationsrichtlinien für verwaltete Android-Geräte | Microsoft-Dokumentation"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie App-Konfigurationsrichtlinien zum Bereitstellen von Konfigurationsdaten für eine Android for Work-App beim Ausführen verwenden.\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e56aff30b353a2c98eb7effbec3e02bde066804f
ms.sourcegitcommit: 67c037af31c1f167ec9b4f4baa754631c817e7d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2017
---
# <a name="add-app-configuration-policies-for-managed-android-devices"></a>Hinzufügen von App-Konfigurationsrichtlinien für verwaltete Android-Geräte

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Verwenden Sie App-Konfigurationsrichtlinien in Microsoft Intune, um Einstellungen anzugeben, wenn Benutzer eine Android for Work-App ausführen. Sie weisen diese Richtlinien nicht direkt Benutzern und Geräten zu. Stattdessen verknüpfen Sie eine Richtlinie mit einer App und weisen dann die App zu. Die Richtlinieneinstellungen werden verwendet, wenn die App danach sucht (in der Regel beim ersten Ausführen).

> [!Note]  
> Nicht jede App unterstützt App-Konfigurationen. Fragen Sie den App-Entwickler, um herauszufinden, ob er die App zur Unterstützung von App-Konfigurationsrichtlinien erstellt hat.

1. Melden Sie sich im Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** + **Intune** aus.
3. Wählen Sie die Workload **Mobile Apps** aus.
4. Klicken Sie auf **App-Konfigurationsrichtlinien** in der Gruppe **Verwalten** und dann auf **Hinzufügen**.
5. Legen Sie die folgenden Details fest:
    - **Name**  
      Der Name des Profils, das im Azure-Portal angezeigt wird.
    - **Beschreibung**  
      Die Beschreibung des Profils, das im Azure-Portal angezeigt wird.
    - **Geräteregistrierungstyp**  
      Klicken Sie auf **Verwaltete Geräte**.
6. Wählen Sie **Android** für die **Plattform** aus.
7. Wählen Sie **Zugeordnete App** aus, um die App auszuwählen, für die Sie eine App-Konfigurationsrichtlinie definieren möchten.  Wählen Sie aus der Liste von Android for Work-Apps aus, die Sie genehmigt und mit Intune synchronisiert haben.
8. Wählen Sie **Konfigurationseinstellungen** aus. Sie können Konfigurationen mithilfe von Folgendem festlegen:
    - [Der Konfigurations-Designer](#Use-the-configuration-designer)
    - [Eingabe mit dem JSON-Editor](#Use-the-JSON-editor)
9. Klicken Sie auf **OK** und dann auf **Hinzufügen**.

## <a name="use-the-configuration-designer"></a>Verwenden des Konfigurations-Designers

Sie können den Konfigurations-Designer für Apps auf Geräten verwenden, die in Intune registriert sind oder nicht. Der Designer ermöglicht Ihnen das Konfigurieren bestimmter Konfigurationsschlüssel und -werte. Sie müssen ebenfalls den Datentyp für jeden Wert angeben.

Legen Sie für jeden Schlüssel und jeden Wert in der Konfiguration Folgendes fest:

  - **Konfigurationsschlüssel**  
     Dieser wird verwendet, um die bestimmte Einstellungskonfiguration eindeutig zu identifizieren.
  - **Werttyp**  
    Der Datentyp des Konfigurationswerts. Zu den Typen gehören Integer, Real, String oder Boolean.
  - **Konfigurationswert**  
    Der Wert für die Konfiguration. 

## <a name="enter-the-json-editor"></a>Eingabe mit dem JSON-Editor

Einige Konfigurationseinstellungen für Apps (z.B. die mit Bündeltypen) können nicht mit dem Konfigurations-Designer konfiguriert werden.  Sie müssen den JSON-Editor für diese Werte verwenden. Einstellungen werden Apps automatisch bereitgestellt, wenn die App installiert wird.

1. Wählen Sie für **Format der Konfigurationseinstellungen** die Option **JSON-Editor aufrufen** aus.
2. Im Editor können Sie JSON-Werte für Konfigurationseinstellungen definieren. Sie können **JSON-Vorlage herunterladen** auswählen, um eine Beispieldatei herunterzuladen, die Sie dann konfigurieren können.
3. Wenn Sie fertig sind, wählen Sie **OK** aus, und klicken Sie dann auf **Hinzufügen**.

Die Richtlinie wird erstellt und auf dem Blatt mit der Richtlinienliste angezeigt.

Wenn die zugewiesene App auf einem Gerät gestartet wird, wird sie mit den Einstellungen ausgeführt, die Sie in der App-Konfigurationsrichtlinie konfiguriert haben.

## <a name="preconfigure-permissions-grant-state-for-apps"></a>Vorkonfigurieren der Erteilung von Berechtigungen für Apps

Sie können auch die Berechtigung vorkonfigurieren, dass Apps auf Android-Gerätefeatures zugreifen können. Standardmäßig fordern Android-Apps, die Geräteberechtigungen erfordern (z.B. Zugriff auf den Standort oder die Gerätekamera), die Benutzer zum Annehmen oder Ablehnen der Berechtigungen auf. Wenn eine App z.B. das Gerätemikrofon verwendet, wird der Endbenutzer aufgefordert, der App die Berechtigung zur Verwendung des Mikrofons zu erteilen.

1. Melden Sie sich im Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** + **Intune** aus.
3. Wählen Sie **Mobile Apps** aus. Wählen Sie unter **Verwalten** die Option App-Konfigurationsrichtlinien aus, und klicken Sie dann auf **Hinzufügen**.
4. Legen Sie die folgenden Details fest:
    - **Name**: Der Name des Profils, das im Azure-Portal angezeigt wird
    - **Beschreibung**: Die Beschreibung des Profils, das im Azure-Portal angezeigt wird
    - **Plattform**: Wählen Sie **Android** aus
    - **Geräteregistrierungstyp** - *Verwaltete Geräte** ist vorab für Sie ausgewählt.
5. Wählen Sie **Zugeordnete App** aus, um die App auszuwählen, für die Sie eine Konfigurationsrichtlinie definieren möchten.  Wählen Sie aus der Liste von Android for Work-Apps aus, die Sie genehmigt und mit Intune synchronisiert haben.
6. Wählen Sie **Berechtigungen** und dann **Hinzufügen** aus.
7. Wählen Sie aus der Liste der verfügbaren App-Berechtigungen und dann **OK** aus.
8. Wählen Sie eine Option für jede Berechtigung aus, die mit dieser Richtlinie erteilt werden soll:
    - **Auffordern**: Den Benutzer zur Annahme oder Ablehnung auffordern.
    - **Automatisch zulassen**: Automatisch genehmigen, ohne dass der Benutzer benachrichtigt wird.
    - **Automatisch ablehnen**: Automatisch ablehnen, ohne dass der Benutzer benachrichtigt wird.
9. Um die App-Konfigurationsrichtlinie zuzuweisen, wählen Sie die App-Konfigurationsrichtlinie, dann **Zuweisung** und anschließend **Gruppen auswählen** aus.
10. Wählen Sie die zuzuweisenden Benutzergruppen und dann **Auswählen** aus.
11. Wählen Sie **Speichern** aus, um die Richtlinie zuzuweisen.

## <a name="next-steps"></a>Nächste Schritte

Fahren Sie damit fort, die App [zuzuweisen](apps-deploy.md) und zu [überwachen](apps-monitor.md).

