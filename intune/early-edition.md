---
title: Early Edition
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 08/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5d5d8e0500a0ee928b1037a978f6d4dadab71495
ms.sourcegitcommit: 2ed8d1c39d4b3e3282111f1d758afb3a50f19f8f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2017
---
# <a name="the-early-edition-for-microsoft-intune---august-2017"></a>Die Early Edition für Microsoft Intune – August 2017

Die **Early Edition** enthält eine Liste der Funktionen, die in späteren Versionen von Microsoft Intune zur Verfügung stehen werden. Diese Informationen werden auf einer begrenzten Basis bereitgestellt, und Änderungen sind vorbehalten. Geben Sie diese Informationen nicht außerhalb Ihres Unternehmens weiter. Einige der hier aufgeführten Features werden möglicherweise bis zum Stichtag nicht fertig und werden erst in eine spätere Version aufgenommen. Andere Features werden in einer Pilotphase getestet (Test-Flighting), um sicherzustellen, dass sie für Kunden bereit sind. Wenden Sie sich mit Fragen oder Bedenken an den Ansprechpartner für Ihre Microsoft-Produktgruppe.

Diese Seite wird regelmäßig aktualisiert. Überprüfen Sie, ob weitere Updates vorliegen.

> [!Note]
>Die folgenden Änderungen sind in der Entwicklung für Intune. Weitere Informationen zu neuen hybriden Features finden Sie auf unserer [Seite mit neuen hybriden Funktionen](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--

## What's coming to Intune on the Azure portal  
## What's coming to Intune apps
## Notices

-->



## <a name="intune-on-the-azure-portal"></a>Intune im Azure-Portal

### <a name="actions-for-non-compliance----730266--"></a>Aktionen bei Inkompatibilität <!--730266-->     
*Aktionen bei Inkompatibilität* ist ein neues Feature für Kompatibilitätsrichtlinien, mit der Sie Aktionen für Geräte einrichten können, die nicht kompatibel sind. Sie können eine oder mehrere Aktionen angeben und den Zeitraum festlegen, in dem diese Aktionen ausgeführt werden müssen. Sie können z.B. Benutzer von Geräten per E-Mail benachrichtigen, sobald ihr Gerät inkompatibel wurde. Sie können auch den Zugriff nicht kompatibler Geräte auf Unternehmensressourcen sperren, nachdem die Geräte während einer dreitägigen Karenzzeit per bedingtem Zugriff zugreifen konnten.

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Neuer Bericht, der iOS-Geräte mit älteren iOS-Versionen auflistet <!-- 1352223 -->
Der Bericht **Out-of-date iOS Devices** (Veraltete iOS-Geräte) wird im Arbeitsbereich **Softwareupdates** verfügbar sein. Im Report sehen Sie eine Liste überwachter iOS-Geräte, die unter eine iOS-Updaterichtlinie fallen und mehrere verfügbare Updates besitzen. Für jedes Gerät können Sie einen Status anzeigen, warum das Gerät nicht automatisch aktualisiert wurde. 

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices-----822899--1305423--"></a>Neue Einstellungen zum Zulassen und Blockieren von Apps auf Samsung KNOX Standard-Geräten <!-- 822899,  1305423-->   
Es werden neue [Einstellungen für Geräteeinschränkungen](device-restrictions-android.md) hinzugefügt, mit denen Sie die folgenden App-Listen angeben können:
  - Apps, die Benutzer installieren dürfen
  - Apps, für deren Ausführung Benutzer blockiert sind
  - Apps, die vor dem Benutzer auf dem Gerät verborgen werden  

Sie können die Apps mithilfe der URL, des Paketnamens oder der Liste der Apps, die Sie verwalten, angeben.

### <a name="new-settings-for-windows-10-device-restriction-profile"></a>Neue Einstellungen für das Windows 10-Geräteeinschränkungsprofil
<!--- 978575, 1308849, 1308850 -->
Wir fügen neue Einstellungen zum Geräteeinschränkungsprofil für Windows 10 in der Kategorie „Windows Defender SmartScreen“ hinzu.

Details zum Geräteeinschränkungsprofil für Windows 10 finden Sie in den [Einstellungen für die Geräteeinschränkung für Windows 10 und höher]( device-restrictions-windows-10.md).

### <a name="new-device-restriction-settings-for-windows-10------1063965---"></a>Neue Einstellungen für Geräteeinschränkungen für Windows 10 <!-- 1063965 -->
Wir haben neue Einstellungen für das [Windows 10-Geräteeinschränkungsprofil](/intune/device-restrictions-windows-10) in folgenden Kategorien hinzugefügt:
- Windows Defender SmartScreen
- App Store


### <a name="android-for-work-support-for-lookout----1087312---"></a>Unterstützung für Lookout in Android for Work <!-- 1087312 -->   
Der Intune-Connector mit Lookout unterstützt die Verwendung der Lookout for Work-App auf Android for Work-Geräten. Sie können die Lookout-App innerhalb oder außerhalb des Containers bereitstellen.


### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune-App-Schutz und Citrix MDX-Entwicklungstools <!-- 709185 -->
Sie können Geräte und Apps mit einer Kombination aus Citrix XenMobile MDX und Microsoft Intune verwalten. Dadurch können Sie Apps mit der Intune-App-Schutzrichtlinie verwalten, während Sie die mVPN-Technologie von Citrix verwenden.

Sie können ein Coderepository suchen, das das App Wrapping Tool von Intune und des Intune App SDK für iOS und Android enthält, das von der Citrix MDX mVPN-Technologie integriert wird.


### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium: neuer Mobile Threat Defense-Partner <!-- 954681 -->
Sie können den Zugriff mobiler Geräte auf Unternehmensressourcen mit bedingtem Zugriff basierend auf Risikobewertungen steuern, die von Zimperium vorgenommen werden, einer Mobile Threat Defense-Lösung, die mit Microsoft Intune zusammenarbeitet.

#### <a name="how-integration-with-intune-works"></a>Funktionsweise der Integration mit Intune
Das Risiko wird basierend auf Telemetriedaten von Geräten bewertet, auf denen Zimperium ausgeführt wird. Sie können Richtlinien für bedingten EMS-Zugriff basierend auf der Zimperium-Risikobewertung konfigurieren, die über Intune-Gerätekompatibilitätsrichtlinien aktiviert werden, und so anhand der erkannten Bedrohungen nicht kompatible Geräte für den Zugriff auf Unternehmensressourcen zulassen oder blockieren.

### <a name="new-azure-ad-conditional-access-policy-ui-link-from-intune-----1016201---"></a>Neue Benutzeroberflächenverknüpfung für Azure AD-Richtlinien für den bedingten Zugriff in Intune <!-- 1016201 -->
IT-Administratoren können App-basierte Richtlinien für den bedingten Zugriff über die neue Benutzeroberfläche für Richtlinien für den bedingten Zugriff in der Azure AD-Workload festlegen. Die App-basierten Richtlinien für bedingten Zugriff, die sich im Bereich Intune-App-Schutz in Azure befinden, bleiben dort vorläufig und werden parallel erzwungen. Es wird auch ein praktischer Link zur neuen Benutzeroberfläche der Richtlinie für den bedingten Zugriff in Azure AD von der Intune-Workload vorhanden sein.


### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Hohe Verfügbarkeit der Unterstützung von lokalem Exchange-Connector <!-- 676614 -->   
Sie können über mehrere Clientzugriffs-Serverrollen (CAS) für den lokalen Exchange-Connector verfügen. Bei einem Fehler des Haupt-Clientzugriffsservers empfängt der Exchange-Connector z.B. eine Abfrage, um auf andere Clientzugriffsserver zurückzugreifen. Durch diese Funktion wird sichergestellt, dass der Dienst nicht unterbrochen wird.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>System Center Operations Manager Management Pack für Exchange-Connector <!-- 885457 -->   
Mit dem System Center Operations Manager Management Pack für den Exchange-Connector können Sie die Exchange-Connector-Protokolle analysieren. Dieses Management Pack bietet Ihnen bei der Behebung von Problemen verschiedene Möglichkeiten zur Überwachung von Intune.

### <a name="end-of-support-for-ios-80----1164477---"></a>Ablauf des Supports für iOS 8.0 <!---1164477--->
Verwaltete Apps und die Unternehmensportal-App für iOS benötigen iOS 9.0 und höher, um auf Unternehmensressourcen zugreifen zu können. Geräte, die nicht bis September aktualisiert werden, können nicht mehr auf das Unternehmensportal oder diese Apps zugreifen. Ab Dezember wird jeglicher Zugriff auf Unternehmensressourcen, einschließlich E-Mails, verhindert. 

### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Ablauf des Supports für Android 4.3 und niedriger <!---1171127, 1326920 --->
Verwaltete Apps und die Unternehmensportal-App für Android benötigen Android 4.4 oder höher, um auf Unternehmensressourcen zugreifen zu können. Geräte, die nicht bis Anfang Oktober aktualisiert werden, können nicht mehr auf das Unternehmensportal oder diese Apps zugreifen. Ab Dezember werden alle registrierten Geräte deaktiviert und können dann nicht mehr auf Unternehmensressourcen zugreifen. Bei Verwendung von App-Schutzrichtlinien ohne mobile Geräteverwaltung erhalten Apps keine Updates mehr, und die Qualität ihrer Benutzung wird mit der Zeit abnehmen.


### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017----1327781---"></a>Erinnerung für Plattformunterstützung: Der grundlegende Support für Windows Phone 8.1 wird am 11. Juli 2017 beendet. <!-- 1327781 -->  
Am 11. Juli 2017 wird der grundlegende Support für Windows Phone 8.1 endgültig beendet. Der Support für den Windows 8.1-PC ist davon nicht betroffen.

Dies hat keinen unmittelbaren Einfluss auf Windows Phone 8.1-Geräte, die vom Intune-Dienst verwaltet werden. Registrierte Geräte funktionieren weiterhin, und alle Richtlinien, Konfigurationen und Apps werden weiterhin wie erwartet funktionieren. Bitte beachten Sie, dass es keine Verbesserungen für die Windows Phone 8.1-Plattform im Intune-Dienst sowie für die Unternehmensportal-App von Windows Phone 8.1 gibt.

Daher wird empfohlen, zum schnellstmöglichen Zeitpunkt ein Upgrade für berechtigte Windows Phone 8.1-Geräte auf Windows 10 Mobile durchzuführen. 

## <a name="intune-apps"></a>Intune-Apps

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Unterstützung für Intune Managed Browser von iOS und Android <!---1374196--->

Ab Oktober 2017 unterstützt die Intune Managed Browser-App für Android nur noch Geräte mit Android 4.4 oder höher. Die Intune Managed Browser.App für iOS unterstützt nur noch Geräte mit iOS 9.0 oder höher. Frühere Versionen von Android und iOS können Managed Browser weiterhin verwenden, allerdings können keine neuen Versionen der App installiert werden, und einige App-Funktionen sind möglicherweise nicht verfügbar. Es wird empfohlen, dass Sie diese Geräte auf eine unterstützte Betriebssystemversion aktualisieren.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Zugriff auf die Unternehmensportal-App für Android durch Endbenutzer ohne Registrierung <!---1169910--->  
Endbenutzer müssen ihr Gerät bald nicht mehr registrieren, um auf die Unternehmensportal-App für Android zugreifen zu können. Endbenutzer innerhalb von Organisationen, die App-Schutzrichtlinien verwenden, werden beim Öffnen der Unternehmensportal-App nicht mehr aufgefordert, ihr Gerät zu registrieren. Zudem können Endbenutzer Apps vom Unternehmensportal installieren, ohne ihr Gerät zu registrieren. 

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Verbesserte Fehlermeldungen für den Fall, wenn ein Benutzer die Höchstzahl von zur Registrierung erlaubten Geräten erreicht <!-- 1270370 -->
Statt einer generischen Fehlermeldung sehen Benutzer eine freundliche, handlungsrelevante Fehlermeldung: „You have enrolled the maximum number of devices allowed by your IT admin. Please remove an enrolled device or get help from your IT admin.“ (Sie haben die maximale Anzahl an Geräten registriert, die von Ihrem IT-Administrator erlaubt wurden. Bitte entfernen Sie ein registriertes Gerät, oder wenden Sie sich an Ihren IT-Administrator.“)

### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Neue Anmeldeerfahrung für Benutzer des Android-Unternehmensportals sowie für Benutzer der App-Schutz-Richtlinien <!-- 621669 -->
Endbenutzer können mithilfe der App des Android-Unternehmensportals Apps durchsuchen, Geräte verwalten und IT-Kontaktinformationen anzeigen, ohne ihre Android-Geräte registrieren zu müssen. Wenn ein Endbenutzer, der bereits eine App verwendet, die durch Intune-App-Schutzrichtlinien geschützt ist, zusätzlich die Android-Unternehmensportal-App startet, dann enthält er zukünftig keine Aufforderung mehr, das Gerät zu registrieren. 

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Informieren von Endbenutzern, welche Geräteinformation für iOS angezeigt werden kann <!--739894-->
Wir fügen dem Bildschirm „Gerätedetails“ den **Besitzertyp** auf der Unternehmensportal-App für iOS hinzu. So können Benutzer direkt auf dieser Seite mehr über Privatsphäre in der Dokumentation für Intune-Endbenutzer herausfinden. Sie finden diese Informationen ebenso auf dem Bildschirm „Info“.

### <a name="apps-details-pages-display-new-information-for-android-devices---1287476--"></a>Detailseiten von Apps zeigen neue Informationen für Android-Geräte <!--1287476-->
Die Detailseite der App der Unternehmensportal-App für Android zeigt die App-Kategorien an, die der IT-Administrator für diese App definiert hat.

### <a name="intune-mobile-application-management-mam-dialog-boxes-now-have-a-modern-interface----1199015---"></a>Die Dialogfelder der mobilen Anwendungsverwaltung mit Intune (Intune Mobile Application Management (MAM)) haben nun eine moderne Schnittstelle <!-- 1199015 -->
Die Dialogfelder der mobilen Anwendungsverwaltung mit Intune (MAM) wurden für ein modernes Aussehen und Verhalten aktualisiert. Die Dialogfelder funktionieren wie zuvor.

Auf modernen Android-Geräten verfügen Dialogfelder für Fehler- oder Benachrichtigungen, die von Intune angezeigt werden, nun über ein modernes Aussehen und Verhalten.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Neue Einstellung in der Android-Unternehmensportal-App für die Akkuoptimierung <!--1405990-->
Auf der Seite **Einstellungen** in der Unternehmensportal-App für Android wird eine neue Einstellung zu finden sein, mit der Benutzer die Akkuoptimierung einfach für Unternehmensportal- und Microsoft Authenticator-Apps ausschalten können. Der in der Einstellung dargestellte Name der App hängt davon ab, welche App das Geschäftskonto verwaltet. Benutzern wird empfohlen, die Akkuoptimierung zugunsten besserer Leistung von Work-Apps auszuschalten, die E-Mails und Daten synchronisieren. 




## <a name="notices"></a>Benachrichtigungen

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple erfordert Updates für die Transportsicherheit für Anwendungen <!--748318-->   
Apple hat angekündigt, dass sie ab Frühjahr 2017 bestimmte Anforderungen für die Transportsicherheit für Anwendungen (Application Transport Security, ATS) erzwingen werden. ATS wird verwendet, um eine strengere Sicherheit in allen App-Kommunikationen über HTTPS zu erzwingen. Diese Änderung wirkt sich auf Intune-Kunden aus, die die iOS-Unternehmensportal-App verwenden. Unter [Intune support blog (Intune-Supportblog)](https://aka.ms/compportalats) finden Sie weitere Informationen.

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Direkter Zugriff auf Apple-Registrierungsszenarien <!--951869-->   
Für Intune-Konten, die nach Januar 2017 erstellt wurden, hat Intune direkten Zugriff auf Apple-Registrierungsszenarien mithilfe der Workload „Geräte registrieren“ im Azure-Vorschauportal aktiviert. Bisher konnte nur über Links im klassischen Intune-Portal auf die Apple-Registrierungsvorschau zugegriffen werden. Vor Januar 2017 erstellte Intune-Konten erfordern eine einmalige Migration, bevor diese Features in Azure verfügbar sind. Der Zeitplan für die Migration wurde noch nicht angekündigt, aber Sie erfahren so bald wie möglich Näheres. Wir empfehlen Ihnen dringend, ein Testkonto zu erstellen, um die neue Oberfläche zu testen, wenn Sie mit Ihrem vorhandenen Konto nicht auf die Vorschau zugreifen können.

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Stellen Sie sich auf eine Änderung ein: Intune ändert die Oberfläche des Intune-Partnerportals <!-- 1050016 -->
Ab dem Dienstupdate Mitte Mai 2017 entfernen wir die Intune-Partnerseite von manage.microsoft.com.  

Wenn Sie ein Partneradministrator sind, können Sie über die Intune-Partnerseite nicht mehr im Namen Ihrer Kunden Elemente anzeigen und Aktionen durchführen. Stattdessen müssen Sie sich bei einer der beiden anderen Partnerportale von Microsoft anmelden.

Sowohl das [Microsoft Partner Center](https://partnercenter.microsoft.com/) als auch das [Microsoft Office 365 Partner Admin Center](https://portal.office.com/) ermöglicht Ihnen das Anmelden bei den von Ihnen verwalteten Kundenkonten. Verwenden Sie als Partner künftig eine dieser Websites für die Verwaltung Ihrer Kunden.



### <a name="see-also"></a>Weitere Informationen:
Details zu aktuellen Entwicklungen finden Sie unter [Neuheiten in Microsoft Intune](whats-new.md).
