---
title: "Konfigurieren des App-Zugriffs für SharePoint Online"
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 531b09bb-ddfd-498f-8ee3-6675d2466208
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 992273f88e4bbe234f11f936d6416dbaf0d394e9
ms.lasthandoff: 04/19/2017


---

# <a name="create-a-sharepoint-online-conditional-access-policy-to-only-allow-apps-supported-by-mam"></a>Erstellen einer Richtlinie für den bedingten Zugriff für SharePoint Online, um nur Apps zuzulassen, die von MAM unterstützt werden
Dieses Thema bietet Ihnen eine Schritt-für-Schritt-Anleitung, wie Sie den bedingten Zugriff für Exchange Online einrichten, um nur mobile Apps zuzulassen, die Intune-Richtlinien zur Verwaltung mobiler Apps (Mobile Application Management, MAM) unterstützen.

## <a name="configure-a-sharepoint-online-policy"></a>Konfigurieren einer SharePoint Online-Richtlinie
**Schritt 1**: Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an, das das App-Zugriffsfeature enthält. Wenn Sie noch nicht mit dem Azure-Portal vertraut sind, lesen Sie das Thema [Azure-Portal für MAM-Richtlinien in Microsoft Intune](azure-portal-for-microsoft-intune-mam-policies.md).

**Schritt 2**: Wählen Sie **Durchsuchen > Intune > Mobile Anwendungsverwaltung mit Intune > Einstellungen** aus, und wählen Sie im Abschnitt **Bedingter Zugriff** **SharePoint Online** aus.

![Screenshot des Einstellungenblatts mit dem Abschnitt für bedingten Zugriff und geöffnetem SharePoint Online-Blatt](../media/mam-ca-settings-spo.png)

**Schritt 3**: Wählen Sie auf dem Blatt **Zulässige Apps** die Option **Allow apps that support Intune app policies** (Apps zulassen, die Intune-App-Richtlinien unterstützen), um nur Apps zuzulassen, die von Intune-MAM-Richtlinien unterstützt werden, damit sie auf SharePoint Online zugreifen können. Bei Auswahl der Option, nur Apps zuzulassen, die von Intune MAM-Richtlinien unterstützt werden, wird die Liste der unterstützten Apps angezeigt.

![Screenshot des Blatts der zulässigen Apps mit der Liste der Apps](../media/mam-ca-spo-allowed-apps.png)

**Schritt 4**: Um diese Richtlinie auf Benutzer anzuwenden, öffnen Sie das Blatt **Eingeschränkte Benutzergruppen**, und wählen Sie **Benutzergruppe hinzufügen** aus. Wählen Sie mindestens eine Benutzergruppe aus, auf die diese Richtlinie angewendet werden soll.

![Screenshot des Blatts „Eingeschränkte Benutzergruppen“ mit hervorgehobener Option „Benutzergruppe hinzufügen“](../media/mam-ca-spo-restricted-groups.png)


**Schritt 5**: Möglicherweise möchten Sie, dass einige Benutzer in der Benutzergruppe, die Sie im vorherigen Schritt ausgewählt haben, nicht von dieser Richtlinie betroffen sind. In solchen Fällen fügen Sie die Gruppe der Benutzer der Liste der ausgenommenen Benutzergruppen hinzu. Wählen Sie auf dem Blatt **SharePoint Online** **Exempted user groups** (Ausgenommene Benutzergruppen) aus. Wählen Sie **Benutzergruppe hinzufügen** aus, um die Liste der Benutzergruppen zu öffnen. Wählen Sie die Gruppen aus, die Sie von dieser Richtlinie ausnehmen möchten.  

## <a name="modifying-an-existing-policy"></a>Bearbeiten einer vorhandenen Richtlinie
### <a name="adding-or-deleting-user-groups"></a>Hinzufügen oder Löschen von Benutzergruppen
Um aus der Liste der **eingeschränkten Benutzergruppen** **eine Benutzergruppe zu löschen**, öffnen Sie das Blatt „Eingeschränkte Benutzergruppen“, markieren die Benutzergruppe, die Sie löschen möchten, und klicken auf die Schaltfläche mit den drei Punkten (...),  um die Löschoption anzuzeigen. Wählen Sie **Löschen** aus, um die Benutzergruppe aus der Liste zu entfernen. Sie können genauso vorgehen, um eine Benutzergruppe aus der Liste **exempted user group** (Ausgenommene Benutzergruppen) zu entfernen.


## <a name="next-steps"></a>Nächste Schritte
[Konfigurieren des App-Zugriffs für Exchange Online](mam-ca-for-exchange-online.md)

[Blockieren von Apps, die über keine moderne Authentifizierung verfügen](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Weitere Informationen:

[Schützen von App-Daten mithilfe von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

