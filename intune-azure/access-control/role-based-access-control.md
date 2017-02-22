---
title: "Rollenbasierte Zugriffssteuerung für Microsoft Intune | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie mit der rollenbasierten Zugriffssteuerung steuern können, wer Aktionen ausführen und Änderungen vornehmen kann."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1024d2a33d843c628ffbb68f7b01a5d511191e7e
ms.openlocfilehash: db0f88db8eee33781ccf3ef54e34089a25118726


---

# <a name="role-based-access-control-rbac-for-microsoft-intune"></a>Rollenbasierte Zugriffssteuerung für Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Einfach ausgedrückt helfen Ihnen Intune-**Rollen** (also die rollenbasierte Zugriffssteuerung) dabei zu steuern, welche Benutzer welche Intune-Aktionen ausführen dürfen, und für wen diese Aktionen gelten. Sie können entweder die integrierten Rollen verwenden, die einige allgemeine Intune-Szenarien abdecken, oder Sie können eigene Rollen erstellen.

Eine Rolle wird durch Folgendes definiert:

- **Definition:** der Name der Rolle und die damit konfigurierten Berechtigungen
- **Mitglieder:** der Benutzer (oder die Benutzergruppe), dem diese Berechtigungen gewährt werden
- **Bereich:** die Benutzer oder Geräte, die eine angegebene Person (das Mitglied) verwalten kann
- **Zuweisung:** Wenn die Definition, die Mitglieder und der Bereich konfiguriert wurden, wird die Rolle zugewiesen.

## <a name="built-in-roles"></a>Integrierte Rollen:

Die folgenden Rollen sind in Intune integriert. Sie können diese Rollen anpassen oder sie ohne weitere Konfiguration Gruppen zuweisen.

- **Intune Administrator:** besitzt vollständige Berechtigungen für alle Intune Vorgänge
- **Application Manager:** verwaltet Anwendungen und Profile und stellt sie bereit
- **Configuration Policy Manager:** verwaltet Konfigurationseinstellungen und Profile und stellt sie bereit
- **Helpdesk Operator:** führt Remoteaufgaben durch und zeigt Benutzer- und Geräteinformationen an
- **Read Only Operator:** zeigt Informationen im Intune-Portal an, ohne Änderungen vornehmen zu können


## <a name="custom-roles"></a>Benutzerdefinierte Rollen

Wenn keine der integrierten Rollen Ihren Anforderungen entspricht, können Sie eigene Rollen erstellen. Wählen Sie dazu die Einstellungen aus, die viele der Funktionen von Intune umfassen. Eine Liste der verfügbaren Einstellungen finden Sie weiter unten in diesem Thema.

### <a name="example"></a>Beispiel

Sie stellen einen neuen IT-Administrator ein, der für das Bereitstellen und Verwalten von Apps für Benutzer in Ihrem Büro in London verantwortlich ist. Die Benutzer sind Mitglieder der Azure AD-Gruppe **London**. Sie möchten sicherstellen, dass der IT-Administrator keine Apps für Benutzer in anderen Büros bereitstellen kann. Sie führen die folgenden Maßnahmen durch:

- Weisen Sie die integrierte Rolle **Application Manager** mit den folgenden Eigenschaften zu:
    - **Mitglieder:** Wählen Sie eine Gruppe aus, die den IT-Administrator enthält, der Apps bereitstellen soll.
    - **Bereich:** Wählen Sie die Azure AD-Gruppe **London** aus.

    >[!IMPORTANT]
    >Für das Erstellen, Bearbeiten oder Zuweisen von Rollen muss das Konto in Azure AD über eine der folgenden Berechtigungen verfügen:
    >- **Global AAD Admin**
    >- **Intune Service Admin**

### <a name="how-to-create-a-custom-role"></a>Erstellen einer benutzerdefinierten Rolle

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Zugriffssteuerung** aus.
![Workload „Zugriffssteuerung“](./media/axxess-control.png)
1. Wählen Sie auf dem Blatt **Rollen** in der Workload **Zugriffssteuerung** die Option **Benutzerdefiniertes Element hinzufügen** aus.
2. Geben Sie auf dem Blatt **Benutzerdefinierte Rolle hinzufügen** einen Namen und eine Beschreibung für die neue Rolle ein, und klicken Sie dann auf **Berechtigungen**.
3. Wählen Sie auf dem Blatt **Berechtigungen** die Berechtigungen aus, die Sie mit dieser Rolle verwenden möchten. Verwenden Sie als Hilfestellung die Liste der Einstellungen für benutzerdefinierte Rollen weiter unten in diesem Thema.
4. Klicken Sie abschließend auf **OK**.
5. Klicken Sie auf dem Blatt **Benutzerdefinierte Rolle hinzufügen** auf **Erstellen**.

Die neue Rolle wird in der Liste auf dem Blatt **Rollen** angezeigt.

## <a name="how-to-assign-a-role"></a>Zuweisen einer Rolle

1. Wählen Sie auf dem Blatt **Rollen** in der Workload **Zugriffssteuerung** die gewünschte integrierte oder benutzerdefinierte Rolle aus, die Sie zuweisen möchten.
2. Wählen Sie auf dem Blatt <*Rollenname*> – **Eigenschaften** die Option **Verwalten** > **Zuweisungen** aus.
    >[!TIP]
    >Sie können auf diesem Blatt auch vorhandene Rollen bearbeiten oder löschen.
3. Wählen Sie auf dem nächsten Blatt **Zuweisen** aus.
4. Geben Sie auf dem Blatt **Rollenzuweisungen** einen **Namen** und eine optionale **Beschreibung** für die Zuweisung ein, und wählen Sie dann Folgendes aus:
    - **Mitglieder:** Wählen Sie eine Gruppe aus, die den Benutzer enthält, dem Sie die Berechtigungen erteilen möchten.
    - **Bereich:** Wählen Sie eine Gruppe aus, die die Benutzer enthält, die das oben ausgewählte Mitglied verwalten soll.
5. Klicken Sie abschließend auf **OK**.

Die neue Zuweisung wird in der Liste der Zuweisungen angezeigt.

## <a name="custom-role-settings-reference"></a>Referenz für die Einstellungen benutzerdefinierter Rollen

Wenn Sie eine benutzerdefinierte Rolle erstellen, können Sie eine oder mehrere der folgenden Einstellungen konfigurieren:

### <a name="device-configurations"></a>Gerätekonfigurationen

|||
|-|-|
|**Zuweisen**|Zuweisen von Geräteprofilen zu Gruppen|
|**Erstellen**|Erstellen von Geräteprofilen|
|**Löschen**|Löschen von Geräteprofilen|
|**Lesen**|Lesen von Geräteprofilen und deren Eigenschaften|
|**Aktualisieren**|Aktualisieren vorhandener Geräteprofile|

### <a name="managed-apps"></a>Verwaltete Apps

|||
|-|-|
|**Zuweisen**|Zuweisen verwalteter Apps zu Gruppen|
|**Erstellen**|Hinzufügen neuer verwalteter Apps in Intune|
|**Löschen**|Löschen verwalteter Apps|
|**Lesen**|Lesen verwalteter Apps und ihrer Eigenschaften|
|**Aktualisieren**|Aktualisieren vorhandener verwalteter Apps|
|**Zurücksetzen**|Zurücksetzen verwalteter Apps auf Geräten|

### <a name="managed-devices"></a>Verwaltete Geräte

|||
|-|-|
|**Löschen**|Löschen verwalteter Geräte aus Intune|
|**Lesen**|Anzeigen von Informationen zu verwalteten Geräte im Intune-Portal|
|**Aktualisieren**|Aktualisieren von Informationen über verwaltete Geräte|

### <a name="mobile-apps"></a>Mobile Apps

|||
|-|-|
|**Zuweisen**|Zuweisen mobiler Apps zu Gruppen|
|**Erstellen**|Hinzufügen neuer mobiler Apps in Intune|
|**Löschen**|Löschen mobiler Apps|
|**Lesen**|Lesen mobiler Apps und ihrer Eigenschaften|
|**Aktualisieren**|Aktualisieren vorhandener mobiler Apps|

### <a name="organization"></a>Organisation

|||
|-|-|
|**Lesen**|Lesen von Mandanteneinstellungen|
|**Aktualisieren**|Aktualisieren von Mandanteneinstellungen|

### <a name="remote-tasks"></a>Remoteaufgaben

|||
|-|-|
|**Aktivierungssperre umgehen**|Entfernen der Aktivierungssperre auf einem iOS-Gerät ohne Apple-ID und Kennwort des Benutzers |
|**Modus für verlorene Geräte deaktivieren**|Deaktivieren des Modus für verlorene Geräte. Der Modus für verlorene Geräte ermöglicht die Angabe einer Nachricht und einer Telefonnummer, die auf dem Sperrbildschirm des Geräts angezeigt werden.|
|**Modus für verlorene Geräte aktivieren**|Aktivieren des Modus für verlorene Geräte. Der Modus für verlorene Geräte ermöglicht die Angabe einer Nachricht und einer Telefonnummer, die auf dem Sperrbildschirm des Geräts angezeigt werden.|
|**Gerät suchen**|-|
|**Jetzt neu starten**|Durchführen eines Neustart des Geräts|
|**Remotesperre**|Sperren eines Geräts. Der Eigentümer des Geräts muss zum Entsperren seine Kennung verwenden.|
|**Kennung zurücksetzen**|Generiert eine neue Kennung für das Gerät, die auf dem Blatt Übersicht über <device name> angezeigt wird.|
|**Außerkraftsetzen**|Entfernt nur Unternehmensdaten, die von Intune verwaltet werden. Es werden keine persönlichen Daten vom Gerät entfernt.|
|**Zurücksetzen**|Setzt das Gerät auf die Standardeinstellungen zurück.|



### <a name="telecom-expenses"></a>Telekommunikationsausgaben

|||
|-|-|
|**Lesen**|Lesen von TEM-Einstellungen (Telecom Expense Management)|
|**Aktualisieren**|Aktualisieren von TEM-Einstellungen (Telecom Expense Management)|

### <a name="terms-and-conditions"></a>Nutzungsbedingungen

|||
|-|-|
|**Zuweisen**|Zuweisen von Geschäftsbedingungen zu Gruppen|
|**Erstellen**|Erstellen von Einstellungen für Geschäftsbedingungen|
|**Löschen**|Löschen von Einstellungen für Geschäftsbedingungen|
|**Lesen**|Lesen von Einstellungen für Geschäftsbedingungen im Intune-Portal|
|**Aktualisieren**|Aktualisieren von Einstellungen für Geschäftsbedingungen|


<!--HONumber=Feb17_HO1-->


