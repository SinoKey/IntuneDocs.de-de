---
title: "Verwenden von Intune-App-Konfigurationsrichtlinien für Android for Work"
titleSuffix: Intune on Azure
description: "Erfahren Sie, wie Sie App-Konfigurationsrichtlinien zum Bereitstellen von Konfigurationsdaten für eine Android for Work-App beim Ausführen verwenden.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f9ea697cafa0f277c176e55443250d32ca378dbb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-android-for-work"></a>Verwenden von Microsoft Intune-App-Konfigurationsrichtlinien für Android for Work

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Verwenden Sie App-Konfigurationsrichtlinien in Microsoft Intune, um Einstellungen anzugeben, die beim Ausführen einer Android for Work-App durch Benutzer verfügbar sind. Nicht alle Apps unterstützen die App-Konfiguration. Fragen Sie den App-Entwickler, um herauszufinden, ob er die App zur Unterstützung von App-Konfigurationsrichtlinien erstellt hat.

App-Konfigurationsrichtlinien können Ihnen dabei helfen, die verfügbare App-Einstellungen vorab für Ihre Benutzer zu konfigurieren, bevor sie die App verwenden. Einige Android-Apps unterstützen Optionen für verwaltete Konfigurationen, die Sie in der Intune-Konsole mit dem [Konfigurations-Designer](#use-configuration-designer) konfigurieren können. Einige Konfigurationseinstellungen für Apps (z.B. die mit Bündeltypen) können nicht mit dem Konfigurations-Designer konfiguriert werden.  Sie müssen den [JSON-Editor](#use-json-editor) für diese Werte verwenden.   Einstellungen werden Apps automatisch bereitgestellt, wenn die App installiert wird.

Sie weisen diese Richtlinien nicht direkt Benutzern und Geräten zu. Stattdessen verknüpfen Sie eine Richtlinie mit einer App und weisen dann die App zu. Die Richtlinieneinstellungen werden verwendet, wenn die App danach sucht (in der Regel beim ersten Ausführen).

## <a name="use-configuration-designer"></a>Verwenden des Konfigurations-Designers

1. Wählen Sie im Intune-Portal die Option **Mobile Apps** aus. Wählen Sie unter **Verwalten** die Option **App-Konfigurationsrichtlinien** aus, und klicken Sie dann auf **Hinzufügen**.
2. Legen Sie die folgenden Details fest:
    - **Name**: Der Name des Profils, das in der Intune-Konsole angezeigt wird
    - **Beschreibung**: Die Beschreibung des Profils, das in der Intune-Konsole angezeigt wird
    - **Plattform**: Wählen Sie **Android** aus
    - **Geräteregistrierungstyp** - **Bei Intune registriert** ist für Sie vorausgewählt.
3. Wählen Sie **Zugeordnete App** aus, um die App auszuwählen, für die Sie eine Konfigurationsrichtlinie definieren möchten.  Wählen Sie aus der Liste von Android for Work-Apps aus, die Sie genehmigt und mit Intune synchronisiert haben.
4. Wählen Sie **Konfigurationseinstellungen** aus.
5. Wählen Sie für **Format der Konfigurationseinstellungen** die Option **Konfigurations-Designer verwenden** aus.
6. Wählen Sie **Hinzufügen** aus. Eine Liste der verfügbaren Konfigurationseinstellungen wird angezeigt. Die Liste enthält:
    - **Konfigurationsschlüssel**: Name der Einstellung.
    - **Werttyp**: Die Einstellung kann konfiguriert werden, z.B. **Boolesch** oder **Zeichenfolge**.
    - **Beschreibung**: Eine Beschreibung der Konfigurationseinstellung.
7. Aktivieren Sie die Kontrollkästchen der Einstellungen, die Sie für dieses Profil konfigurieren möchten, und klicken Sie dann auf **OK**.
8. Eine Liste Ihrer ausgewählten Einstellungen wird mit dem verfügbaren **Konfigurationswert** angezeigt. Geben Sie einen Wert für jede Einstellung an, und klicken Sie dann auf **OK**.

## <a name="use-json-editor"></a>Verwenden des JSON-Editors

1. Wählen Sie im Intune-Portal die Option **Mobile Apps** aus. Wählen Sie unter **Verwalten** die Option **App-Konfigurationsrichtlinien** aus, und klicken Sie dann auf **Hinzufügen**.
2. Legen Sie die folgenden Details fest:
    - **Name**: Der Name des Profils, das in der Intune-Konsole angezeigt wird
    - **Beschreibung**: Die Beschreibung des Profils, das in der Intune-Konsole angezeigt wird
    - **Plattform**: Wählen Sie **Android** aus
    - **Geräteregistrierungstyp** - **Bei Intune registriert** ist für Sie vorausgewählt.
3. Wählen Sie **Zugeordnete App** aus, um die App auszuwählen, für die Sie eine Konfigurationsrichtlinie definieren möchten.  Wählen Sie aus der Liste von Android for Work-Apps aus, die Sie genehmigt und mit Intune synchronisiert haben.
5. Wählen Sie **Konfigurationseinstellungen** aus.
6. Wählen Sie für **Format der Konfigurationseinstellungen** die Option **JSON-Editor aufrufen** aus.
7. Im Editor können Sie JSON-Werte für Konfigurationseinstellungen definieren. Sie können **JSON-Vorlage herunterladen** auswählen, um eine Beispieldatei herunterzuladen, die Sie dann konfigurieren können.
8. Wenn Sie fertig sind, wählen Sie **OK** aus, und klicken Sie dann auf **Hinzufügen**.

Die Richtlinie wird erstellt und auf dem Blatt mit der Richtlinienliste angezeigt.

Fahren Sie fort, die App wie gewöhnlich [zuzuweisen](apps-deploy.md) und zu [überwachen](apps-monitor.md).

Wenn die zugewiesene App auf einem Gerät gestartet wird, wird sie mit den Einstellungen ausgeführt, die Sie in der App-Konfigurationsrichtlinie konfiguriert haben.

## <a name="preconfigure-permissions-grant-state-for-apps"></a>Vorkonfigurieren der Erteilung von Berechtigungen für Apps

Sie können auch die Berechtigung vorkonfigurieren, dass Apps auf Android-Gerätefeatures zugreifen können. Standardmäßig fordern Android-Apps, die Geräteberechtigungen erfordern (z.B. Zugriff auf den Standort oder die Gerätekamera), die Benutzer zum Annehmen oder Ablehnen der Berechtigungen auf. Wenn eine App z.B. das Gerätemikrofon verwendet, wird der Endbenutzer aufgefordert, der App die Berechtigung zur Verwendung des Mikrofons zu erteilen.

1. Wählen Sie im Intune-Portal die Option **Mobile Apps** aus. Wählen Sie unter **Verwalten** die Option **App-Konfigurationsrichtlinien** aus, und klicken Sie dann auf **Hinzufügen**.
2. Legen Sie die folgenden Details fest:
    - **Name**: Der Name des Profils, das in der Intune-Konsole angezeigt wird
    - **Beschreibung**: Die Beschreibung des Profils, das in der Intune-Konsole angezeigt wird
    - **Plattform**: Wählen Sie **Android** aus
    - **Geräteregistrierungstyp** - **Bei Intune registriert** ist für Sie vorausgewählt.
3. Wählen Sie **Zugeordnete App** aus, um die App auszuwählen, für die Sie eine Konfigurationsrichtlinie definieren möchten.  Wählen Sie aus der Liste von Android for Work-Apps aus, die Sie genehmigt und mit Intune synchronisiert haben.
5. Wählen Sie **Berechtigungen** und dann **Hinzufügen** aus.
6. Wählen Sie aus der Liste der verfügbaren App-Berechtigungen und dann **OK** aus.
7. Wählen Sie eine Option für jede Berechtigung aus, die mit dieser Richtlinie erteilt werden soll:
    - **Auffordern**: Den Benutzer zur Annahme oder Ablehnung auffordern.
    - **Automatisch zulassen**: Automatisch genehmigen, ohne dass der Benutzer benachrichtigt wird.
    - **Automatisch ablehnen**: Automatisch ablehnen, ohne dass der Benutzer benachrichtigt wird.
8. Um die App-Konfigurationsrichtlinie zuzuweisen, wählen Sie die App-Konfigurationsrichtlinie, dann **Zuweisung** und anschließend **Gruppen auswählen** aus.
9. Wählen Sie die zuzuweisenden Benutzergruppen und dann **Auswählen** aus.
10. Wählen Sie **Speichern** aus, um die Richtlinie zuzuweisen.
