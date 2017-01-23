---
title: Was ist Microsoft Intune? | Microsoft-Dokumentation
description: "Erfahren Sie mehr zu Intune, der Verwaltungskomponente für mobile Geräte der „Enterprise Mobility + Security“-Lösung, und wie Intune Sie beim Schutz von Unternehmensdaten unterstützt."
keywords: Was ist Intune
author: Lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/15/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b4e778d-ac13-4c23-974f-5122f74626bc
ms.reviewer: pmay
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d0057f1e3d2ead729c2143587571fa4b16a3dd2f
ms.openlocfilehash: 9b4eed086853c0feeb8266a8087a275f2b70e40f


---

# <a name="what-is-intune"></a>Was ist Intune?

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune ist ein cloudbasierter Enterprise Mobility-Verwaltungsdienst (Enterprise Mobility Management; EMM), der die Produktivität Ihrer Mitarbeiter unterstützt und gleichzeitig Ihre Unternehmensdaten schützt. Mit Intune können Sie folgende Aktionen ausführen:
* Die mobilen Geräte verwalten, die Ihre Mitarbeiter verwenden, um auf Unternehmensdaten zuzugreifen
* Die mobilen Apps verwalten, die Ihre Mitarbeiter verwenden
* Ihre Unternehmensinformationen schützen, indem Sie steuern, wie Ihre Mitarbeiter darauf zugreifen und diese freigeben
* Sicherstellen, dass Geräte und Apps kompatibel mit den Sicherheitsanforderungen des Unternehmens sind

Die Lösung lässt sich eng in Azure Active Directory (Azure AD) integrieren und bietet Identitäts- und Zugriffsteuerungsfunktionen sowie Azure Rights Management (Azure RMS) für den Datenschutz. Es ist der *Verwaltungszweig* von Microsoft Enterprise Mobility + Security (EMS), während Office 365 der *Produktivitätszweig* der Mobilitätslösung von Microsoft ist.  

Zusammen ermöglichen Office 365 und EMS Ihren Mitarbeitern auf allen ihren Geräten produktiv zu arbeiten, während die Informationen Ihres Unternehmens geschützt bleiben. Office 365 mit EMS ist eine vollständig integrierte Enterprise Mobility Suite, die Funktionen für Produktivität, Identität, Zugriffsteuerung, Verwaltung und Datenschutz bietet. Sie bietet Ihnen eine effektive Möglichkeit für die Bereitstellung und den Betrieb einer Mobilitätslösung in Ihrer Organisation.

## <a name="how-does-intune-work"></a>Funktionsweise von Intune
Intune stellt die Verwaltung mobiler Geräte (MDM) und mobiler Apps (MAM) bereit. Intune MDM- und MAM-Features tragen zur EMS-Suite von Datenschutz- und Kompatibilitätsszenarios bei.  

Wie Sie die MDM/MAM-Features von Intune und EMS-Datenschutz nutzen, hängt von dem [Geschäftsproblem ab, das Sie lösen möchten](#common-business-problems-that-intune-helps-solve). Beispiel:
* Sie werden MDM stark nutzen, wenn Sie einen Pool von Einmalgeräten erstellen, die von Schichtarbeitern im Einzelhandel geteilt werden sollen.
* Sie brauchen MAM und Datenschutz, wenn Sie Ihren Mitarbeitern erlauben, ihre persönlichen Geräte für den Zugriff auf Unternehmensdaten zu nutzen (BYOD).  
* Wenn Sie Firmentelefone an Information-Worker ausgeben, werden Sie sich stark auf alle Technologien verlassen.

## <a name="intune-mobile-device-management-mdm-explained"></a>Erläuterung der Verwaltung mobiler Geräte mit Intune
MDM funktioniert mithilfe der Protokolle oder APIs, die in den mobilen Betriebssystemen verfügbar sind. Es umfasst Aufgaben wie:
* Registrieren von Geräten in der Verwaltung, damit die IT eine Bestandsaufnahme der Geräte hat, die auf Unternehmensdienste zugreifen
* Konfigurieren von Geräten, um sicherzustellen, dass diese die Sicherheits- und -Integritätsstandards des Unternehmens erfüllen
* Bereitstellen von Zertifikaten und WLAN/VPN-Profilen für den Zugriff auf Unternehmensdienste
* Messen der Gerätekompatibilität nach Standards des Unternehmens, inklusive Berichterstellung
* Entfernen von Unternehmensdaten von verwalteten Geräten  

In manchen Fällen kann der Eindruck entstehen, die **Steuerung des Zugriffs auf Unternehmensdaten** sei eine MDM-Feature. Dies ist nicht der Fall, da die Funktion nicht vom mobilen Betriebssystem bereitgestellt wird. Vielmehr ist es etwas, das der Identitätsanbieter bereitstellt. In unserem Fall ist der Identitätsanbieter Azure Active Directory (Azure AD), das Identitäts- und Zugriffsverwaltungssystem von Microsoft.  

Intune ist mit Azure AD integriert, um eine breite Palette von Szenarios für die Zugriffssteuerung zu aktivieren. Sie können z.B. fordern, dass ein mobiles Gerät kompatibel mit den in Intune definierten Unternehmensstandards ist, bevor das Gerät auf einen Unternehmensdienst wie Exchange zugreifen kann. Ebenso können Sie den Unternehmensdienst auf einen bestimmten Satz mobiler Apps begrenzen. Sie können den Zugriff auf Exchange Online beispielsweise nur auf Outlook und Outlook Mobile begrenzen.

## <a name="intune-mobile-app-management-mam-explained"></a>Erläuterung der Verwaltung mobiler Anwendungen mit Intune
Mithilfe von MAM können IT-Profis mit unseren Lösungen z.B. folgende Vorgänge für mobile Apps durchführen:
* Veröffentlichen mobiler Apps für Mitarbeiter
* Konfigurieren von Apps
* Steuern, wie Unternehmensdaten in mobilen Apps verwendet und freigegeben werden
* Entfernen von Unternehmensdaten aus mobilen Apps   
* Aktualisieren von mobilen Apps
* Berichte über das mobile App-Inventar
* Nachverfolgen der Nutzung mobiler Apps

Mit MAM können diese Punkte einzeln oder in bestimmten Kombinationen umgesetzt werden. Insbesondere wird das Konzept der App-Konfiguration (mit Technologien wie der [verwalteten App-Konfiguration für iOS](https://developer.apple.com/library/content/samplecode/sc2279/Introduction/Intro.html)) mit dem Konzept zum Schutz von Unternehmensdaten in mobilen Apps verbunden, weil einige mobile Apps Einstellungen verfügbar machen, mit denen ihre Datensicherheitsfeatures konfiguriert werden können.

In Verbindung mit den Features des Betriebssystems für den Schutz von Daten (z.B. MDM-Features wie Windows Information Protection auf Windows 10) bietet dies ein hohes Maß an Schutz auf mobilen Geräten.

Wenn Sie Intune mit den anderen Diensten in EMS verwenden, können Sie für die mobilen Anwendungen Ihres Unternehmens Sicherheit jenseits dessen bereitstellen, was das mobile Betriebssystem und die mobilen Apps über die App-Konfiguration bereitstellen. Eine App, die mit EMS verwaltet wird, hat Zugriff auf eine größere Auswahl von Schutzfunktionen für mobile Apps und Daten, einschließlich:

* [Einmaliges Anmelden](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-appssoaccess-whatis)  
*   [Multi-Factor Authentication](https://docs.microsoft.com/en-us/multi-factor-authentication/multi-factor-authentication)
* [bedingter App-Zugriff (Zugriff zulassen, wenn die mobile App Unternehmensdaten enthält)](https://docs.microsoft.com/en-us/intune/deploy-use/allow-policy-managed-apps-access-to-o365)
* [Trennen von Unternehmensdaten und persönlichen Daten in der gleichen App](https://docs.microsoft.com/en-us/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
* [App-Schutzrichtlinie (PIN, Verschlüsselung, Speichern unter, Zwischenablage usw.)](https://docs.microsoft.com/en-us/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
* [Zurücksetzen von Unternehmensdaten in einer mobilen App](https://docs.microsoft.com/en-us/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
* [Unterstützung der Rechteverwaltung](https://docs.microsoft.com/en-us/information-protection/understand-explore/what-is-azure-rms)

![Stufen der Datensicherheit bei der App-Verwaltung](./media/managing-mobile-apps.png)

### <a name="intune-mobile-app-security"></a>Sicherheit für mobile Apps in Intune
Das Bereitstellen von App-Sicherheit ist ein Bestandteil von MAM. Wenn wir in Intune von der Sicherheit für mobile Apps sprechen, meinen wir:
* Ein Bewusstsein dafür, persönliche Informationen getrennt von Unternehmens-IT zu halten
* Eine Beschränkung der Aktionen, die Benutzer mit Unternehmensinformationen durchführen können, z.B. Kopieren, Ausschneiden und Einfügen, Speichern und Anzeigen
* Entfernen von Unternehmensdaten aus mobilen Apps, auch bekannt als selektives Zurücksetzen oder Zurücksetzen von Unternehmensdaten

Intune stellt Sicherheit für mobile Apps z.B. über das Feature **App-Schutzrichtlinie** bereit. Die App-Schutzrichtlinie verwendet die Azure AD-Identität, um Unternehmensdaten von persönlichen Daten zu trennen. Daten, auf die mithilfe von Unternehmensanmeldeinformationen zugegriffen wird, erhalten zusätzliche Unternehmensschutzmaßnahmen.

Wenn ein Benutzer sich auf seinem Gerät mit seinen Unternehmensanmeldeinformationen anmeldet, ermöglicht seine Unternehmensidentität den Zugriff auf Daten, auf die er mit seiner persönlichen Identität nicht zugreifen kann. Wenn diese Daten verwendet werden, steuert Intune zusammen mit anderen EMS-Technologien, wie sie gespeichert und freigegeben werden. Die gleichen Schutzmaßnahmen werden nicht auf Daten angewendet, auf die der Benutzer mit seinem Gerät nach Anmeldung mit seiner persönlichen Identität zugreift. Auf diese Weise hat die IT-Abteilung die Kontrolle über Unternehmensdaten, während der Endbenutzer Zugriff und Schutz seiner persönlichen Daten verwaltet.

## <a name="emm-with-and-without-device-enrollment"></a>EMM mit und ohne Geräteregistrierung
Die meisten Enterprise Mobility Management-Lösungen unterstützen grundlegende Technologien für mobile Geräte und mobile Apps. Diese sind normalerweise an das Gerät gebunden, das in der MDM-Lösung Ihrer Organisation registriert ist. Intune unterstützt diese Szenarios und darüber hinaus viele Szenarios ohne Registrierung.  

Unternehmen unterscheiden sich, inwieweit sie Szenarios ohne Registrierung übernehmen. Einige Unternehmen machen dieses Szenario zu Ihrem Standard. Einige ermöglichen es bloß für Begleitgeräte wie z.B. ein persönliches Tablet. Andere unterstützen es überhaupt nicht. Auch im letzten Fall, in dem eine Organisation von allen Mitarbeitern fordert, ihre Geräte in MDM zu registrieren, unterstützen diese Organisationen in der Regel Szenarios ohne Registrierung für Auftragnehmer, Lieferanten und für andere Geräte, die über eine bestimmte Freistellung verfügen.

Sie können die Intune-Technologie für die Geräteverwendung ohne Registrierung sogar auf registrierten Geräten verwenden. Beispielsweise kann vom mobilen Betriebssystem für ein Gerät, das in MDM registriert ist, die Schutzfunktion „Öffnen In“ bereitgestellt werden. (Es handelt sich hierbei um ein iOS-Feature, das Sie daran hindert, ein Dokument aus einer App, z.B. Outlook, in einer anderen App, z.B Word, zu öffnen – es sei denn, beide Apps werden vom MDM-Anbieter verwaltet.) Darüber hinaus kann die IT die App-Schutzrichtlinie auf EMS-verwaltete mobile Apps anwenden, um die Option „Speichern als“ zu steuern oder eine mehrstufige Authentifizierung bereitzustellen.

Intune verfügt als Teil von EMS über Tools, mit denen Sie Ihre Produktivität steigern und gleichzeitig Ihre Unternehmensdaten schützen können – unabhängig von der Position Ihrer Organisation zu registrierten und nicht registrierten mobilen Geräten und Apps.

## <a name="common-business-problems-that-intune-helps-solve"></a>Häufig auftretende geschäftliche Probleme, die mithilfe von Intune gelöst werden können
Die folgende Liste geschäftlicher Probleme verweist auf ausführlichere Informationen zu den Lösungen, die wir bereitstellen können. Nur das letzte Element erfordert eine MDM-Registrierung als Teil der Lösung.

* [Sichern Ihrer lokalen E-Mails und Daten für den sicheren Zugriff über mobile Geräte](common-ways-to-use-intune.md#protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Sichern von Office 365-E-Mails und -Daten für den sicheren Zugriff über mobile Geräte](common-ways-to-use-intune.md#protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Ausgeben firmeneigener Smartphones für Information-Worker](common-ways-to-use-intune.md#issue-corporate-owned-phones-to-your-information-workers)
* [Anbieten eines BYOD-Programms (Bring Your Own Device) für alle Mitarbeiter](common-ways-to-use-intune.md#offer-a-bring-your-own-device-program-to-all-employees)
* [Ermöglichen des sicheren Zugriffs für Mitarbeiter auf Office 365 von einem nicht verwalteten, öffentlichen Kiosk aus](common-ways-to-use-intune.md#enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk)
* [Ausgeben gemeinsam genutzter Tablets mit eingeschränkter Verwendung an Ihre Taskworker](common-ways-to-use-intune.md#issue-limited-use-shared-tablets-to-your-task-workers)

### <a name="next-steps"></a>Nächste Schritte
* Erfahren Sie mehr über einige der [gängigsten Arten der Verwendung von Intune](common-ways-to-use-intune.md).
* Machen Sie sich [mit einer 30-Tage-Testversion von Intune](get-started-with-a-30-day-trial-of-microsoft-intune.md) mit dem Produkt vertraut.
* Lernen Sie die [technischen Anforderungen und Funktionen](/intune/get-started/what-to-know-before-you-start-microsoft-intune) von Intune detailliert kennen.



<!--HONumber=Jan17_HO2-->


