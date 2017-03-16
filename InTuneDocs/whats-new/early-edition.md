---
title: Early Edition | Microsoft-Dokumentation
description: 
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 03/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 0936051b5c33a2e98f275ef7a3a32be2e8f5a8b0
ms.openlocfilehash: 0ba6695b595849f72eb44d8e6f095e8b1aae39eb
ms.lasthandoff: 03/10/2017


---


# <a name="the-early-edition-for-microsoft-intune---march-2017"></a>Die Early Edition für Microsoft Intune – März 2017

Die **Early Edition** enthält eine Liste der Funktionen, die in späteren Versionen von Microsoft Intune zur Verfügung stehen werden. Diese Informationen werden unter dem Geheimhaltungsvertrag auf einer sehr begrenzten Basis bereitgestellt und Änderungen sind vorbehalten. Einige der hier aufgeführten Features werden möglicherweise bis zum Stichtag nicht fertig und werden erst in eine spätere Version aufgenommen. Andere Features werden in einer Pilotphase getestet (Test-Flighting), um sicherzustellen, dass sie für Kunden bereit sind. Wenden Sie sich an Ihren Intune-/PM-Kontakt, wenn Sie Fragen oder Bedenken haben.

Diese Seite wird regelmäßig aktualisiert. Überprüfen Sie, ob weitere Updates vorliegen.

> [!Note]
> Die folgenden Änderungen sind in der Entwicklung für Intune. Alle diese Features werden letztlich auch für hybride Kundenbereitstellungen (Configuration Manager mit Intune) unterstützt. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Neue Funktionen

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Neue Benutzeroberfläche für die Unternehmensportal-App für Android <!--621622-->

Die Unternehmensportal-App für Android aktualisiert ihre Benutzeroberfläche für ein moderneres Erscheinungsbild und höhere Benutzerfreundlichkeit. Wichtige Updates sind:

- Farben: Die IT-Abteilung kann die Färbung der Kopfzeilen der Registerkarte „Unternehmensportal“ dem Branding gemäß festlegen.
- Apps: Auf der Registerkarte **Apps** wurden die Schaltflächen **Empfohlene Apps** und **Alle Apps** aktualisiert.
- Suche: Auf der Registerkarte **Apps** ist die Schaltfläche **Suche** nun eine unverankerte interaktive Schaltfläche.
- Navigation in Apps: Die Ansicht **Alle Apps** enthält die Registerkartenansicht **Featured** (Highlights), **Alle** und **Kategorien**, um die Navigation zu vereinfachen.
- Unterstützung: Die Registerkarten **Meine Geräte** und **IT kontaktieren** wurden aktualisiert, um die Lesbarkeit zu verbessern.

Weitere Informationen zu diesen Änderungen finden Sie auf der [Seite zu App-Benutzeroberflächenupdates](whats-new-in-intune-app-ui.md).

## <a name="notices"></a>Benachrichtigungen

### <a name="improved-support-for-android-users-based-in-china---720444--"></a>Verbesserte Unterstützung für Android-Benutzer in China<!--720444-->

Da der Google Play Store in China nicht verfügbar ist, müssen Android-Geräte Apps von chinesischen Marktplätzen beziehen. Das Unternehmensportal unterstützt diesen Workflow durch Umleiten von Android-Benutzern in China, damit sie das Unternehmensportal und Outlook-Apps von lokalen App-Stores herunterladen können. Dies verbessert die Benutzerfreundlichkeit, wenn Richtlinien für bedingten Zugriff aktiviert sind, sowohl für die mobile Geräteverwaltung als auch die mobile Anwendungsverwaltung. Das Unternehmensportal und Outlook-Apps für Android sind in den folgenden chinesischen App-Stores verfügbar: 

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple erfordert Updates für die Transportsicherheit für Anwendungen <!--748318-->

Apple hat angekündigt, dass sie ab Frühjahr 2017 bestimmte Anforderungen für die Transportsicherheit für Anwendungen (Application Transport Security, ATS) erzwingen werden. ATS wird verwendet, um eine strengere Sicherheit in allen App-Kommunikationen über HTTPS zu erzwingen. Diese Änderung wirkt sich auf Intune-Kunden aus, die die iOS/macOS-Unternehmensportal-App verwenden. Unter [Intune support blog](https://aka.ms/compportalats) (Intune-Supportblog) finden Sie weitere Informationen.

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Öffentliche Vorschau der neuen Intune-Administratoroberfläche in Azure <!--736542-->

Anfang 2017 erfolgt die Migration der gesamten Administratoroberfläche zu Azure. Dies ermöglicht die leistungsstarke und integrierte Verwaltung von EMS-Kernworkflows in einer modernen, mit Grafik-APIs erweiterbaren Dienstplattform.

Neue Testmandanten sehen die öffentliche Vorschau der neuen Administratoroberfläche im Azure-Portal bereits in diesem Monat. Die Umgebung ist zwar noch in der Previewphase, schrittweise werden aber Funktionen und Parität zur vorhandenen Intune-Konsole bereitgestellt.

Die Administratoroberfläche im Azure-Portal verwendet die bereits angekündigten neuen Gruppierungs- und Zielgruppenadressierungsfunktionen. Bei der Migration eines vorhandenen Mandanten zur neuen Gruppierungsoberfläche erfolgt gleichzeitig die Migration zur Vorschau der neuen Administratoroberfläche auf Ihrem Mandanten. Wenn Sie in der Zwischenzeit bis zur Migration Ihres Mandanten einzelne neue Funktionen testen oder anschauen möchten, melden Sie sich für ein neues Intune-Testkonto an, oder sehen Sie sich die [neue Dokumentation](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune) an.

Bei Fragen zur Zeitachse für die Migration Ihres Mandanten wenden Sie sich an unser Migrationsteam unter [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Nicht verwaltete Geräte können auf zugewiesene Apps zugreifen <!--664691-->

Als Teil der Designänderungen auf der Unternehmensportal-Website können iOS- und Android-Benutzer Apps installieren, die ihnen als „Verfügbar ohne Registrierung“ auf Ihren nicht verwalteten Geräten zugewiesen sind. Benutzer können sich mit ihren Intune-Anmeldeinformationen auf der Unternehmensportal-Website anmelden und die Liste der ihnen zugewiesenen Apps anzeigen. Die App-Pakete der Apps des Typs „Verfügbar ohne Registrierung“ werden zum Download über die Unternehmensportal-Website verfügbar gemacht. Apps, für die die Registrierung für die Installation erforderlich ist, sind durch diese Änderung nicht betroffen, da Benutzer aufgefordert werden, ihr Gerät zu registrieren, wenn sie diese Apps installieren möchten.

### <a name="improvements-to-device-actions-report---677150--"></a>Verbesserungen des Geräteaktionenberichts<!--677150-->

Wir haben die Leistung des Geräteaktionenberichts verbessert. Darüber hinaus können Sie jetzt den Bericht nach Status filtern. Beispielsweise könnten Sie den Bericht so filtern, dass nur Geräteaktionen angezeigt werden, die abgeschlossen wurden.

### <a name="actions-for-non-compliance---730266--"></a>Aktionen bei Inkompatibilität <!--730266-->

**Aktionen bei Inkompatibilität** ist ein neues Feature für Kompatibilitätsrichtlinien, mit der Sie Aktionen für Geräte einrichten können, die nicht kompatibel sind. Sie können eine oder mehrere Aktionen angeben und den Zeitraum festlegen, in dem diese Aktionen ausgeführt werden müssen. Sie können z.B. Benutzer von Geräten per E-Mail benachrichtigen, sobald ihr Gerät inkompatibel wurde. Sie können auch den Zugriff nicht kompatibler Geräte auf Unternehmensressourcen sperren, nachdem die Geräte während einer dreitägigen Karenzzeit per bedingtem Zugriff zugreifen konnten.

### <a name="custom-app-categories---748805--"></a>Benutzerdefinierte App-Kategorien <!--748805-->

Sie können jetzt Kategorien für in Intune hinzugefügte Apps erstellen, bearbeiten und zuweisen. Zurzeit können Kategorien nur auf Englisch angegeben werden.
Weitere Informationen finden Sie unter [How to add an app to Intune (Hinzufügen einer App zu Intune)](/intune-azure/manage-apps/add-apps).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>Zuweisen von Branchen-Apps für Benutzer nicht registrierter Geräte <!--748823-->

Sie können Benutzern jetzt Branchen-Apps aus dem Store zuweisen, unabhängig davon, ob die Benutzergeräte bei Intune registriert sind oder nicht. Wenn ein Benutzergerät nicht bei Intune registriert ist, muss der Benutzer die App über die Unternehmensportal-Website statt über die Unternehmensportal-App installieren.

### <a name="new-compliance-reports---846671--"></a>Neue Kompatibilitätsberichte <!--846671-->

Jetzt informieren Kompatibilitätsberichte Sie über die Kompatibilitätsstellung von Geräten in Ihrem Unternehmen, sodass sie schnell kompatibilitätsbezogene Probleme beheben können, von denen Ihre Benutzer betroffen sind. Sie können Informationen anzeigen zu:

- Gesamter Kompatibilitätsstatus von Geräten
- Kompatibilitätsstatus für eine einzelne Einstellung
- Kompatibilitätsstatus für eine einzelne Richtlinie

Sie können mit diesen Berichten auch Detailinformationen zu einzelnen Geräten erhalten, um bestimmte Einstellungen und Richtlinien anzuzeigen, die sich auf das Gerät auswirken.

### <a name="additional-windows-10-upgrade-paths---903672--"></a>Zusätzliche Windows 10-Upgradepfade <!--903672-->

Sie können jetzt eine Richtlinie für die Editionsaktualisierung zum Aktualisieren von Geräten auf die folgenden zusätzlichen Windows 10-Editionen erstellen:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N


### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Direkter Zugriff auf Apple-Registrierungsszenarien <!--951869-->

Für Intune-Konten, die nach Januar 2017 erstellt wurden, hat Intune direkten Zugriff auf Apple-Registrierungsszenarien mithilfe der Workload „Geräte registrieren“ im Azure-Vorschauportal aktiviert. Bisher konnte nur über Links im klassischen Intune-Portal auf die Apple-Registrierungsvorschau zugegriffen werden. Vor Januar 2017 erstellte Intune-Konten erfordern eine einmalige Migration, bevor diese Features in Azure verfügbar sind. Der Zeitplan für die Migration wurde noch nicht angekündigt, aber Sie erfahren so bald wie möglich Näheres. Wir empfehlen Ihnen dringend, ein Testkonto zu erstellen, um die neue Oberfläche zu testen, wenn Sie mit Ihrem vorhandenen Konto nicht auf die Vorschau zugreifen können.

### <a name="see-also"></a>Weitere Informationen:
Details zu aktuellen Entwicklungen finden Sie unter [Neuheiten in Microsoft Intune](whats-new-in-microsoft-intune.md).

