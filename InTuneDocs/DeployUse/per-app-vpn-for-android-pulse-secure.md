---
title: "App-bezogenes VPN für Android mithilfe von Pulse Secure | Microsoft Intune"
description: 
keywords: 
author: nbigman
manager: jeffgilb
ms.date: 05/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac65e906-3922-429f-8d9c-d313d3126645
ms.sourcegitcommit: 40e5602a4675bd92a85001827fb43426c41ed1e3
ms.openlocfilehash: fc58e71a9b2279200dee2630aab7dbab727ea128


---

# Verwenden einer benutzerdefinierten Richtlinie zum Erstellen eines Profils für ein App-bezogenes VPN für Android-Geräte

Sie können ein App-bezogenes VPN-Profil für Android-Geräte erstellen, die von Intune verwaltet werden. Zunächst erstellen Sie ein VPN-Profil, das den Verbindungstyp „Pulse Secure“ verwendet, und anschließend eine benutzerdefinierte Konfigurationsrichtlinie, die dieses Profil bestimmten Apps zuordnet. Nachdem Sie diese Richtlinien auf Ihrem Android-Gerät oder für Ihre Benutzergruppen bereitgestellt haben, wird beim Öffnen einer der angegebenen Apps auf diesen Geräten eine VPN-Verbindung für die jeweilige App geöffnet. 

### Schritt 1: Erstellen eines VPN-Profils

1. Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) auf **Richtlinie** > **Richtlinie hinzufügen**.
2. Wählen Sie eine Vorlage für die neue Richtlinie aus, indem Sie **Android** erweitern und dann **VPN-Profil (Android 4 und höher)** auswählen.

3. Wählen Sie in der Vorlage für **Verbindungstyp** die Option **Pulse Secure** aus.
4. Vervollständigen und speichern Sie das VPN-Profil. Weitere Informationen zu VPN-Profilen finden Sie unter [VPN-Verbindungen](vpn-connections-in-microsoft-intune.md).

> [!NOTE]
Notieren Sie den Namen des VPN-Profils für den nächsten Schritt. Beispiel: **MeineApp-VPN-Profil**.
   
### Schritt 2: Erstellen einer benutzerdefinierten Konfiguration
    
   1. Wählen Sie in der Intune-Verwaltungskonsole **Richtlinie** -> **Richtlinie hinzufügen** -> **Android** -> **Benutzerdefinierte Konfiguration** -> **Richtlinie erstellen** aus.
   2. Geben Sie einen Namen für die Richtlinie an.
   3. Klicken Sie unter **OMA-URI-Einstellungen** auf **Hinzufügen**.
   4. Geben Sie einen Einstellungsnamen an.
   5. Geben Sie für **Datentyp** **Zeichenfolge** an.
   6. Geben Sie für **OMA-URI** diese Zeichenfolge an: **./Vendor/MSFT/VPN/Profile/*Name*/PackageList**. *Name* ist der Name des VPN-Profils, den Sie in Schritt 1 notiert haben. Bei unserem Beispiel lautet die Zeichenfolge **./Vendor/MSFT/VPN/Profile/MeineApp-VPN-Profil/PackageList**.
   7.   Geben Sie in **Wert** eine durch Semikolons getrennte Liste der Pakete an, die dem Profil zugeordnet werden sollen.  Wenn z.B. Excel und der Google-Browser Chrome die VPN-Verbindung verwenden sollen, geben Sie Folgendes ein: **com.microsoft.office.excel;com.android.chrome**.
  

   ![Beispiel einer benutzerdefinierten Richtlinie für ein App-bezogenes VPN für Android](..\media\android_per_app_vpn_oma_uri.png) 
#### Festlegen Ihrer App-Liste als Positiv- oder Negativliste (optional)
Sie können angeben, dass Ihre Liste mit Apps die VPN-Verbindung *nicht* verwenden darf, indem Sie den Wert **BLACKLIST** verwenden.  Alle anderen Apps stellen per VPN eine Verbindung her.

Alternativ können Sie angeben, dass *nur* die angegebenen Apps die VPN-Verbindung verwenden dürfen, indem Sie den Wert **WHITELIST** verwenden.
 

1.  Klicken Sie unter „OMA-URI-Einstellungen“ auf **Hinzufügen**.
2.  Geben Sie einen Einstellungsnamen an.
3.  Geben Sie für **Datentyp** **Zeichenfolge** an.
4.  Geben Sie für **OMA-URI** diese Zeichenfolge an: **./Vendor/MSFT/VPN/Profile/*Name*/Mode**. *Name* ist der Name des VPN-Profils, den Sie in Schritt 1 notiert haben. Bei unserem Beispiel lautet die Zeichenfolge **./Vendor/MSFT/VPN/Profile/MeineApp-VPN-Profil/Mode**.
5.  Geben Sie für **Wert** entweder **BLACKLIST** oder **WHITELIST** ein. 


   
### Schritt 3: Bereitstellen beider Richtlinien

Sie müssen *beide* Richtlinien für die *gleichen* Intune-Gruppen bereitstellen.

   1.  Wählen Sie im Arbeitsbereich **Richtlinie** die Richtlinie aus, die Sie bereitstellen möchten, und klicken Sie dann auf **Bereitstellung verwalten**.

2.  Führen Sie im Dialogfeld **Bereitstellung verwalten** folgende Schritte aus:

    -   **Zum Bereitstellen der Richtlinie**: Wählen Sie mindestens eine Gruppe aus, für die Sie die Richtlinie bereitstellen möchten, und klicken Sie auf **Hinzufügen** &gt; **OK**.

    -   **Wenn Sie das Dialogfeld schließen möchten, ohne die Richtlinie bereitzustellen:** Klicken Sie auf **Abbrechen**.

Eine Statuszusammenfassung und Warnungen auf der Seite **Übersicht** des Arbeitsbereichs **Richtlinie** identifiziert Probleme mit der Richtlinie, die Ihre Aufmerksamkeit erfordern. Darüber hinaus wird eine Statusübersicht im Arbeitsbereich „Dashboard“ angezeigt.




<!--HONumber=Jun16_HO4-->


