---
title: "Hinzufügen von App-Konfigurationsrichtlinien für verwaltete Apps ohne Geräteregistrierung | Microsoft-Dokumentation"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie App-Konfigurationsrichtlinien für verwaltete Apps ohne Geräteregistrierung verwenden."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 750ce7dbb0dccf08757e076826e2d3650b6e6ab5
ms.sourcegitcommit: 67c037af31c1f167ec9b4f4baa754631c817e7d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2017
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a>Hinzufügen von App-Konfigurationsrichtlinien für verwaltete Apps ohne Geräteregistrierung

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Sie können App-Konfigurationsrichtlinien mit verwalteten Apps verwenden, die das Intune App SDK unterstützen. Dies gilt sogar für nicht registrierte Geräte. 

1. Melden Sie sich im Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** + **Intune** aus.
3. Wählen Sie die Workload **Mobile Apps** aus.
4. Klicken Sie auf **App-Konfigurationsrichtlinien** in der Gruppe **Verwalten** und dann auf **Hinzufügen**.
5. Legen Sie die folgenden Details fest:
    - **Name**  
      Der Name des Profils, das im Azure-Portal angezeigt wird
    - **Beschreibung**  
      Die Beschreibung des Profils, das im Azure-Portal angezeigt wird
    - **Geräteregistrierungstyp**  
      Klicken Sie auf **Apps verwalten**.
6. Klicken Sie auf **Zugeordnete App**, um die App auszuwählen, die Sie konfigurieren möchten. Wählen Sie die App aus der Liste der Apps aus, die Sie genehmigt und mit Intune synchronisiert haben.
7. Geben Sie für jede Konfigurationseinstellung, die von der App unterstützt wird, den **Namen** und **Wert** ein, und klicken Sie dann auf die Auslassungspunkte (**...**).  
    Klicken Sie zum Löschen einer Konfiguration auf die Auslassungspunkte (**...**) und dann auf **Löschen**.  
    Für das Intune App SDK aktivierte Apps unterstützen Konfigurationen in Schlüssel-Wert-Paaren. Weitere Informationen dazu, welche Schlüssel-Wert-Konfigurationen unterstützt werden, finden Sie in der Dokumentation für jede App.  
    Zusätzlich können Sie Tokens verwenden, die dynamisch mit den Daten aufgefüllt werden, die von der App generiert werden.

## <a name="configuration-values-using-tokens"></a>Konfigurationswerte für das Verwenden von Tokens

Bestimmte Tokens können von Intune generiert und an die verwaltete App gesendet werden. Wenn Ihre App-Konfiguration beispielsweise eine E-Mail-Einstellung verwenden kann, können Sie durch die Verwendung eines Tokens eine dynamische E-Mail hinzufügen. Geben Sie den Namen, der von der App erwartet wird, in das Feld **Name** und anschließend `\{\{mail\}\}` in das Feld **Wert** ein.

Intune unterstützt folgende Tokentypen in den Konfigurationseinstellungen:

- \{\{userprincipalname\}\} – (Beispiel: **John@contoso.com**)
- \{\{mail\}\} – (Beispiel: **John@contoso.com**)
- \{\{partialupn\}\} – (Beispiel: **John**)
- \{\{accountid\}\} – (Beispiel: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
- \{\{deviceid\}\} – (Beispiel: **b9841cd9-9843-405f-be28-b2265c59ef97**)
- \{\{userid\}\} – (Beispiel: **3ec2c00f-b125-4519-acf0-302ac3761822**)
- \{\{username\}\} – (Beispiel: **John Doe**)
- \{\{PrimarySMTPAddress\}\} – (Beispiel: testuser@ad.domain.com) 


> [!Note]  
> Die Zeichen \{\{ und \}\} werden nur von Tokentypen verwendet und dürfen nicht für andere Zwecke verwendet werden.

## <a name="next-steps"></a>Nächste Schritte

Fahren Sie wie gewöhnlich mit dem [Zuweisen](apps-deploy.md) und [Überwachen](apps-monitor.md) der App fort.