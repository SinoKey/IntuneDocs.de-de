---
title: "Verwalten der Datenübertragung zwischen iOS-Apps | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Dieses Thema erläutert die Verwendung des iOS-Features „Öffnen in“ und der Richtlinien für die Verwaltung mobiler Apps zur Verwaltung von Datenübertragungen zwischen Apps."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 424fae862592c1ab5b4221fb5ad40a52c39f6760
ms.openlocfilehash: 8846417efd34db32d5a5c872ef438f5a0bc57e36


---

# <a name="how-to-manage-data-transfer-between-ios-apps"></a>Verwalten der Datenübertragung zwischen iOS-Apps 
## <a name="manage-ios-apps"></a>Verwalten von iOS-Apps
Der Schutz der Unternehmensdaten umfasst die Sicherstellung, dass die Übertragung von Dateien auf Apps beschränkt ist, die von Ihnen verwaltet werden.  Sie können iOS-Apps auf folgende Weise verwalten:

-   Verhindern Sie den Verlust von Unternehmensdaten, indem Sie eine App-Schutzrichtlinie für die Apps konfigurieren, die als **richtlinienverwaltete** Apps bezeichnet werden.

-   Sie können Apps auch über den **MDM-Kanal** bereitstellen und verwalten.  Dies erfordert, dass die Geräte in der MDM-Lösung registriert sind. Dabei kann es sich um **richtlinienverwaltete** Apps oder andere verwaltete Apps handeln.

Mit dem Feature **Open in Management** für iOS-Geräte kann die Übertragung von Dateien zwischen Apps, die über den **MDM-Kanal** bereitgestellt werden, eingeschränkt werden. Die Einschränkungen für „Open in Management“ werden in den Konfigurationseinstellungen festgelegt und mithilfe der MDM-Lösung bereitgestellt.  Wenn der Benutzer die bereitgestellte App installiert, werden die festgelegten Einschränkungen angewendet.
##  <a name="using-app-protection-with-ios-apps"></a>Verwenden von App-Schutz mit iOS-Apps
App-Schutzrichtlinien können mit dem iOS-Feature **Open in Management** verwendet werden, um Unternehmensdaten auf folgende Weise zu schützen:

-   **Im Besitz der Mitarbeiter befindliche Geräte, die von keiner MDM-Lösung verwaltet werden:** Sie können die Einstellungen der App-Schutzrichtlinie so festlegen, dass die **App nur Daten an verwaltete Apps übertragen kann**. Wenn der Endbenutzer eine geschützte Datei in einer Anwendung öffnet, die nicht richtlinienverwaltet ist, kann die Datei nicht gelesen werden.

-   **Von Intune verwaltete Geräte:** Für Geräte, die bei Intune registriert sind, wird die Datenübertragung zwischen Apps mit App-Schutzrichtlinien und anderen verwalteten iOS-Apps, die über Intune bereitgestellt wurden, automatisch zugelassen. Um die Datenübertragung zwischen Apps mit App-Schutzrichtlinien zu erlauben, aktivieren Sie die Einstellung **Übermittlung von Daten nur an verwaltete Apps zulassen**. Sie können das Feature **Open in Management** verwenden, um die Datenübertragung zwischen Apps zu steuern, die über Intune bereitgestellt werden.   

-   **Von einem MDM-Lösung eines Drittanbieters verwaltete Geräte:** Sie können die Datenübertragung mithilfe des iOS-Features **Open in Management** auf verwaltete Apps einschränken.
Um sicherzustellen, dass Apps, die Sie mithilfe der Drittanbieter-MDM-Lösung bereitstellen, auch den in Intune konfigurierten App-Schutzrichtlinien zugeordnet sind, müssen Sie die Benutzer-UPN-Einstellung wie in der exemplarischen Vorgehensweise [Konfigurieren der Benutzer-UPN-Einstellung](#configure-user-upn-setting) beschrieben konfigurieren.  Wenn Apps mithilfe der Benutzer-UPN-Einstellung bereitgestellt werden, werden die App-Schutzrichtlinien auf die App angewendet, wenn sich der Endbenutzer mit seinem Geschäftskonto anmeldet.

> [!IMPORTANT]
> Die Benutzer-UPN-Einstellung ist nur für Apps erforderlich, die auf Geräten bereitgestellt werden, die von einer MDM-Lösung eines Drittanbieters verwaltet werden.  Diese Einstellung ist für Geräte nicht erforderlich, die von Intune verwaltet werden.

## <a name="configure-user-upn-setting"></a>Konfigurieren der Benutzer-UPN-Einstellung
Diese Konfiguration ist für Geräte erforderlich, die von der MDM-Lösung eines Drittanbieters verwaltet werden. Das nachfolgend beschriebene Verfahren ist ein allgemeiner Ablauf zum Implementieren der UPN-Einstellung und der resultierenden Benutzerumgebung:


1.  [Konfigurieren Sie eine Verwaltungsrichtlinie für mobile Apps](app-protection-policies.md) für die iOS-Plattform im Azure-Portal. Konfigurieren Sie Richtlinieneinstellungen für alle Unternehmensanforderungen, und wählen Sie die Apps aus, für die diese Richtlinie gelten soll.

2.  Stellen Sie die Apps und das E-Mail-Profil, die **von der MDM-Lösung eines Drittanbieters** verwaltet werden sollen, mit der in den Schritten 3 und 4 beschriebenen Einstellung bereit.

3.  Stellen Sie die App mit den folgenden Einstellungen für die App-Konfiguration bereit: „key=IntuneMAMUPN“, „Value=<username@company.com>“ [Beispiel: „IntuneMAMUPN“, ‘jondoe@microsoft.com’]

4.  Stellen Sie die Richtlinie „Open in Management“ auf registrierten Geräten bereit.

### <a name="example-end-user-experience"></a>Beispiel für die Benutzerumgebung

1.  Der Endbenutzer installiert die Microsoft Word-App auf dem Gerät.

2.  Der Endbenutzer startet die verwaltete systemeigene E-Mail-App für den Zugriff auf seine E-Mails.

3.  Der Endbenutzer versucht, ein Dokument über die systemeigene E-Mail in Microsoft Word zu öffnen.

4.  Beim Start der Word-App wird der Endbenutzer aufgefordert, sich mit seinem Geschäftskonto anzumelden.  Das Geschäftskonto, das der Benutzer eingibt, wenn er dazu aufgefordert wird, sollte dem in den App-Konfigurationseinstellungen für die Microsoft Word-App festgelegten Konto entsprechen.

    > [!NOTE]
    > Der Endbenutzer kann Word für private Zwecke weitere persönliche Konten hinzufügen, die nicht den App-Schutzrichtlinien unterliegen, wenn er die Word-App in einem privaten Kontext verwendet.

5.  Wenn die Anmeldung erfolgreich durchgeführt wurde, werden die Richtlinieneinstellungen für Apps auf die Word-App angewendet.

6.  Jetzt erfolgt die erfolgreiche Datenübertragung und das Dokument wird in der App als Unternehmensidentität markiert. Darüber hinaus werden die Daten in einem Arbeitskontext behandelt und die Richtlinieneinstellungen werden entsprechend angewendet.

### <a name="see-also"></a>Weitere Informationen:
[Was sind Intune-App-Schutzrichtlinien?](what-is-app-protection-policy.md)



<!--HONumber=Feb17_HO1-->


