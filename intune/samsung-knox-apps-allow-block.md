---
title: "Intune-Richtlinie zum Zulassen/Blockieren von Apps für Samsung KNOX"
titleSuffix: Intune on Azure
description: "Erstellen Sie ein benutzerdefiniertes Profil zum Zulassen und Blockieren von Apps für Samsung KNOX Standard-Geräte.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c5403c8b81caf84a0c7d4bd126a0903ac3122539
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2017
---
# <a name="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices-in-microsoft-intune"></a>Verwenden von benutzerdefinierten Richtlinien zum Zulassen und Blockieren von Apps für Samsung KNOX Standardgeräte in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Verwenden Sie die Verfahren in diesem Thema, um eine benutzerdefinierte Microsoft Intune-Richtlinie zu erstellen, die eine der folgenden Listen erstellt:

- Eine Liste von Apps, deren Ausführung auf dem Gerät blockiert wird. Die Ausführung der Apps in dieser Liste wird blockiert, auch wenn diese bereits vor der Anwendung der Richtlinie installiert waren.
- Eine Liste von Apps, die Benutzer des Geräts aus dem Google Play Store installieren dürfen. Nur die aufgelisteten Apps können installiert werden. Es können keine anderen Apps aus dem Store installiert werden.

Diese Einstellungen können nur von Geräten verwendet werden, auf denen Samsung KNOX Standard ausgeführt wird.

## <a name="create-an-allowed-or-blocked-app-list"></a>Erstellen einer Liste mit zulässigen oder blockierten Apps

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
2. Wählen Sie auf dem Blatt mit der Profilliste die Option **Profil erstellen** aus.
3. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine optionale **Beschreibung** für dieses Geräteprofil ein.
2. Wählen Sie als **Plattformtyp** die Option **Android** und als Profiltyp **Benutzerdefiniert** aus.
3. Klicken Sie auf **Einstellungen**.
3. Wählen Sie auf dem Blatt **Benutzerdefinierte OMA-URI-Einstellungen** die Option **Hinzufügen** aus.
4. Geben Sie im Dialogfeld **OMA-URI-Einstellung hinzufügen oder bearbeiten** Folgendes an:

### <a name="for-a-list-of-apps-that-are-blocked-from-running-on-the-device"></a>Für eine Liste von Apps, deren Ausführung auf dem Gerät blockiert wird:

- **Name:** Geben Sie **PreventStartPackages** ein.
- **Beschreibung:** Geben Sie optional eine Beschreibung wie z.B. „Liste der Apps, deren Ausführung blockiert wird“ ein.
-   **Datentyp:** Wählen Sie in der Dropdownliste **Zeichenfolge** aus.
-   **OMA-URI:** Geben Sie **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages** ein.
-   **Wert:** Geben Sie eine Liste mit den Namen der App-Pakete ein, die Sie zulassen möchten. Sie können **; : ,** oder **|** als Trennzeichen verwenden. (Beispiel: Paket1; Paket2;)

### <a name="for-a-list-of-apps-that-users-are-allowed-to-install-from-the-google-play-store-while-excluding-all-other-apps"></a>Für eine Liste von Apps, die Benutzer des Geräts aus Google Play Store installieren dürfen, wobei alle anderen Apps ausgeschlossen werden:
- **Name:** Geben Sie **AllowInstallPackages** ein.
- **Beschreibung:** Geben Sie optional eine Beschreibung wie z.B. „Liste der Apps, die Benutzer aus Google Play installieren dürfen“ ein.
- **Datentyp:** Wählen Sie in der Dropdownliste **Zeichenfolge** aus.
- **OMA-URI:** Geben Sie **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages** ein.
- **Wert:** Geben Sie eine Liste mit den Namen der App-Pakete ein, die Sie zulassen möchten. Sie können **; : ,** oder **|** als Trennzeichen verwenden. (Beispiel: Paket1; Paket2;)

4. Klicken Sie auf **OK**, und wählen Sie dann auf dem Blatt **Profil erstellen** die Option **Erstellen** aus.

>[!TIP]
> Sie finden die Paket-ID einer App, indem Sie im Google Play Store zu der App navigieren. Die Paket-ID ist in der URL der Seite der App enthalten. Die Paket-ID der Microsoft Word-App lautet z.B. **com.microsoft.office.word**.

Die App-Einstellungen werden beim nächsten Einchecken jedes Zielgeräts angewendet.


<!---## Assign the custom profile--->
