---
# required metadata

title: Verwalten der Datenübertragung zwischen iOS-Apps | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3a4515c1-b325-4ac1-9f0a-45ac27e00681

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Verwalten der Datenübertragung zwischen iOS-Apps mit Microsoft Intune
## Verwalten von iOS-Apps
Der Schutz der Unternehmensdaten umfasst die Sicherstellung, dass die Übertragung von Dateien auf Apps beschränkt ist, die von Ihnen verwaltet werden.  Sie können iOS-Apps auf folgende Weise verwalten:

-   Verhindern Sie den Verlust von Unternehmensdaten, indem Sie eine MAM-Richtlinie für die Apps konfigurieren, die als **richtlinienverwaltete** Apps bezeichnet werden.

-   Sie können Apps auch über den **MDM-Kanal** bereitstellen und verwalten.  Dies erfordert, dass die Geräte in der MDM-Lösung registriert sind. Dabei kann es sich um **richtlinienverwaltete** Apps oder andere verwaltete Apps handeln.

Mit dem Feature **Open in Management** für iOS-Geräte kann die Übertragung von Dateien zwischen Apps, die über den **MDM-Kanal** bereitgestellt werden, eingeschränkt werden. Die Einschränkungen für „Open in Management“ werden in den Konfigurationseinstellungen festgelegt und mithilfe der MDM-Lösung bereitgestellt.  Wenn der Benutzer die bereitgestellte App installiert, werden die festgelegten Einschränkungen angewendet.
##  Verwenden von MAM mit iOS-Apps
Verwaltungsrichtlinien für mobile Apps (MAM) können mit dem Feature **Open in Management** verwendet werden, um Unternehmensdaten auf folgende Weite zu schützen:

-   **Im Besitz der Mitarbeiter befindliche Geräte, die von keiner MDM-Lösung verwaltet werden:** Sie können die MAM-Richtlinieneinstellungen so festlegen, dass die **App nur Daten an verwaltete Apps übertragen kann**. Wenn der Endbenutzer eine geschützte Datei in einer Anwendung öffnet, die nicht richtlinienverwaltet ist, kann die Datei nicht gelesen werden.

-   **Von Intune verwaltete Geräte:** Für Geräte, die bei Intune registriert sind, wird die Datenübertragung zwischen Apps mit MAM-Richtlinien und anderen verwalteten iOS-Apps, die über Intune bereitgestellt wurden, automatisch zugelassen. Um die Datenübertragung zwischen Apps mit MAM-Richtlinien zu erlauben, aktivieren Sie die Einstellung **Übermittlung von Daten nur an verwaltete Apps zulassen**. Sie können das Feature **Open in Management** verwenden, um die Datenübertragung zwischen Apps zu steuern, die über Intune bereitgestellt werden.   

-   **Von einem MDM-Lösung eines Drittanbieters verwaltete Geräte:** Sie können die Datenübertragung mithilfe des iOS-Features **Open in Management** auf verwaltete Apps einschränken.
Um sicherzustellen, dass Apps, die Sie mithilfe der Drittanbieter-MDM-Lösung bereitstellen, auch den in Intune konfigurierten MAM-Richtlinien zugeordnet sind, müssen Sie die Benutzer-UPN-Einstellung wie in der exemplarischen Vorgehensweise [Konfigurieren der Benutzer-UPN-Einstellung](#configure-user-upn-setting) beschrieben konfigurieren.  Wenn Apps mithilfe der Benutzer-UPN-Einstellung bereitgestellt werden, werden die MAM-Richtlinien auf die App angewendet, wenn sich der Endbenutzer mit seinem Geschäftskonto anmeldet.

> [!IMPORTANT]
> Die Benutzer-UPN-Einstellung ist nur für Apps erforderlich, die auf Geräten bereitgestellt werden, die von einer MDM-Lösung eines Drittanbieters verwaltet werden.  Diese Einstellung ist für Geräte nicht erforderlich, die von Intune verwaltet werden.

## Konfigurieren der Benutzer-UPN-Einstellung
Diese Konfiguration ist für Geräte erforderlich, die von der MDM-Lösung eines Drittanbieters verwaltet werden. Das nachfolgend beschriebene Verfahren ist ein allgemeiner Ablauf zum Implementieren der UPN-Einstellung und der resultierenden Benutzerumgebung:


1.  Konfigurieren Sie eine Verwaltungsrichtlinie für mobile Apps für die iOS-Plattform. Konfigurieren Sie Richtlinieneinstellungen für alle Unternehmensanforderungen, und wählen Sie die Apps aus, für die diese Richtlinie gelten soll.

2.  Stellen Sie die Apps und das E-Mail-Profil, die von der MDM-Lösung eines Drittanbieters verwalten werden sollen, mit der in den Schritten 3 und 4 beschriebenen Einstellung bereit.

3.  Stellen Sie die App mit den folgenden Einstellungen für die App-Konfiguration bereit: „key=IntuneMAMUPN“, „Value=<benutzername@firma.com>“ [Beispiel: „IntuneMAMUPN“, „johanschulz@microsoft.com“]

4.  Stellen Sie die Richtlinie „Open in Management“ auf registrierten Geräten bereit.

### Beispiel für die Benutzerumgebung

1.  Der Endbenutzer installiert die Microsoft Word-App auf dem Gerät.

2.  Der Endbenutzer startet die verwaltete systemeigene E-Mail-App für den Zugriff auf seine E-Mails.

3.  Der Endbenutzer versucht, ein Dokument über die systemeigene E-Mail in Microsoft Word zu öffnen.

4.  Beim Start der Word-App wird der Endbenutzer aufgefordert, sich mit seinem Geschäftskonto anzumelden.  Das Geschäftskonto, das der Benutzer eingibt, wenn er dazu aufgefordert wird, sollte dem in den App-Konfigurationseinstellungen für die Microsoft Word-App festgelegten Konto entsprechen.

    > [!NOTE]
    > Der Endbenutzer kann für private Zwecke weitere persönliche Konten zu Word hinzufügen, die nicht den MAM-Richtlinien unterliegen, wenn er die Word-App in einem privaten Kontext verwendet.

5.  Wenn die Anmeldung erfolgreich durchgeführt wurde, werden die Richtlinieneinstellungen für Apps auf die Word-App angewendet.

6.  Jetzt erfolgt die erfolgreiche Datenübertragung und das Dokument wird in der App als Unternehmensidentität markiert. Darüber hinaus werden die Daten in einem Arbeitskontext behandelt und die Richtlinieneinstellungen werden entsprechend angewendet.

### Weitere Informationen:
[Schützen von App-Daten mithilfe der Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


