---
title: Bereitstellen Sie und überwachen Sie der Konformitätsrichtlinie in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service:
ms.suite: na
ms.tgt_pltfrm: na
ms.topic:
ms.assetid:
author: karthikaraman
---
# Bereitstellen Sie und überwachen Sie der Konformitätsrichtlinie in Microsoft Intune
## Bereitstellen einer Konformitätsrichtlinie
Bereitstellen der Konformitätsrichtlinie Sie [erstellt](create-a-device-compliance-policy-in-microsoft-intune.md) für eine oder mehrere Gruppen von Benutzern oder Geräten in Ihrer Organisation.

1.  In der **Richtlinie** Arbeitsbereich, wählen Sie die Richtlinie, die Sie bereitstellen, und wählen Sie dann möchten **Bereitstellung verwalten**.
![IntuneSA3cDeployCompliancePolicy2](./media/intune-sa-3c-deploy-compliance-policy2.png)

2.  In der **Bereitstellung verwalten** Dialogfeld Wählen Sie eine oder mehrere Gruppen aus, die zum Bereitstellen der Richtlinie, und wählen Sie dann **Hinzufügen > OK**.
![IntuneSA3dDeployCompliancePolicy3_Manage](./media/intune-sa-3d-deploy-compliance-policy3-Manage.png)
Sie können eine Richtlinie auf Benutzer und/oder Geräte bereitstellen. Verwenden Sie Active Directory-Gruppen, die Sie bereits erstellt und mit Intune synchronisiert haben, oder erstellen Sie diese Gruppen manuell, in der Intune-Konsole. Weitere Informationen zum Bereitstellen von Richtlinien finden Sie unter [Verwenden von Richtlinien zum Verwalten von Computern und mobilen Geräten mit Microsoft Intune](./intunedocs/use-policies-to-manage-computers-and-mobile-devices-with-microsoft-intune.md).

Verwenden Sie die statuszusammenfassung und Warnungen auf die **Übersicht über die** auf der Seite der **Richtlinie** Arbeitsbereich zum Erkennen von Problemen mit der Richtlinie, die Ihre Aufmerksamkeit erfordern. Darüber hinaus wird eine Statusübersicht im Arbeitsbereich **Dashboard** angezeigt.

> [!IMPORTANT]Wenn Sie keine Konformitätsrichtlinie bereitgestellt haben und dann eine Exchange-Richtlinie für bedingten Zugriff aktivieren, erhalten alle betreffenden Geräte Zugriff.

## Wie Intune-Richtlinienkonflikte gelöst werden
Wenn aufgrund mehrerer auf ein Gerät angewendeter Intune-Einstellungen Konflikte auftreten, gelten die folgenden Regeln:

-   Wenn die in Konflikt stehenden Einstellungen zu einer Intune-Konfigurationsrichtlinie und einer Kompatibilitätsrichtlinie gehören, haben die Einstellungen in der Kompatibilitätsrichtlinie Vorrang vor den Einstellungen in der Intune-Konfigurationsrichtlinie, selbst wenn die Einstellungen in der Konfigurationsrichtlinie sicherer sind.

-   Wenn Sie mehrere Kompatibilitätsrichtlinien bereitgestellt haben, werden die sichersten dieser Richtlinien verwendet.

## Überwachen der Konformitätsrichtlinie

#### So zeigen Sie Geräte an, die keiner Konformitätsrichtlinie entsprechen

1.  In der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com), wählen Sie **Gruppen > alle Geräte**.

2.  Doppelklicken Sie auf den Namen des Geräts in der Liste der Geräte.

3.  Wählen Sie die **Richtlinie** Registerkarte, um eine Liste der Richtlinien für das Gerät.

4.  Aus der **Filter** Dropdown-Liste **Konformitätsrichtlinien entspricht nicht dem**.
![IntuneSA3eViewDeviceNoncomplaince](./media/intune-sa-3e-view-device-noncompliance.png)

#### Zum Anzeigen der Integrität Attestation-Berichte

1.  In der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com), wählen Sie **Berichte**.

2.  In der **Beglaubigung Integritätsbericht - Erstellen eines neuen Berichts** Seite können Sie einen Bericht anzeigen, alle Windows 10 Integrität Nachweis gesammelten Daten werden von Intune. Sie können auch einen Bericht mit einer Teilmenge der Daten mithilfe von Filtern erstellen. Die Filter können auf dem Gerät, Betriebssystem oder nur eine Teilmenge der Datenpunkte basieren.


## Nächste Schritte
Sie können die Konformitätsrichtlinien jetzt zusammen mit bedingten Zugriffsrichtlinien verwenden, um den Zugriff auf Dienste in Ihrer Organisation zu steuern.

[Erstellen von Richtlinien für bedingten Zugriff für e-Mail](manage-email-access-with-microsoft-intune.md)

[Erstellen von Richtlinien für bedingten Zugriff für SharePoint Online](manage-sharepoint-online-access-with-microsoft-intune.md)

### Weitere Informationen:
[Einführung in die Gerätekompatibilität in Intune-Richtlinien](introduction-to-device-compliance-policies-in-microsoft-intune.md)

[Verwalten des Zugriffs auf e-Mail und Office 365-Diensten](manage-access-to-email-and-O365-services-with-intune.md)


<!--HONumber=Mar16_HO4-->


