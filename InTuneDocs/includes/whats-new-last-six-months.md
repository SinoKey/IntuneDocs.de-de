## <a name="december-2016"></a>Dezember 2016

### <a name="public-preview-of-the-new-intune-admin-experience-on-azure--736542--"></a>Öffentliche Vorschau der neuen Intune-Administratoroberfläche auf Azure<!--736542-->
Anfang 2017 erfolgt die Migration der gesamten Administratoroberfläche zu Azure. Dies ermöglicht die leistungsstarke und integrierte Verwaltung von EMS-Kernworkflows in einer modernen, mit Grafik-APIs erweiterbaren Dienstplattform. Im Vorfeld der allgemeinen Verfügbarkeit dieses Portals für alle Intune-Mandanten freuen wir uns, bekannt geben zu können, dass noch in diesem Monat mit dem Rollout einer Vorschau dieser neuen Verwaltungsoberfläche für ausgewählte Mandanten begonnen wird.

Die Administratoroberfläche im Azure-Portal verwendet die bereits angekündigten neuen Gruppierungs- und Zielgruppenadressierungsfunktionen. Bei der Migration eines vorhandenen Mandanten zur neuen Gruppierungsoberfläche erfolgt gleichzeitig die Migration zur Vorschau der neuen Administratoroberfläche auf Ihrem Mandanten. In der Zwischenzeit erfahren Sie im Azure-Portal in der [neuen Dokumentation](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune) mehr über die Neuigkeiten zu Microsoft Intune.

Bei Fragen zur Zeitachse für die Migration Ihres Mandanten wenden Sie sich an unser Migrationsteam unter [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

__Integration von TEM-Diensten (Telecom Expense Management) in der öffentlichen Vorschau des Azure-Portals__ <!--747605--> Wir starten nun mit der Vorschau der Integration mit TEM-Diensten (Telecom Expense Management) von Drittanbietern im Azure-Portal. Mit Intune können Sie Beschränkungen für das Datenroaming im In- und Ausland erzwingen. Diese Integrationen starten mit [Saaswedo](http://www.saaswedo.com). Wenn Sie dieses Feature in Ihrem Testmandanten aktivieren möchten, [wenden Sie sich bitte an den Microsoft-Support](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

### <a name="new-capabilities"></a>Neue Funktionen

__Plattformübergreifende Multi-Factor Authentication__ <!--747590--> Sie können Multi-Factor Authentication (MFA) jetzt für eine ausgewählte Gruppe von Benutzern erzwingen, wenn diese ein iOS- oder Android-Gerät bzw. ein Gerät mit Windows 8.1 und höher oder Windows Phone 8.1 und höher über das Azure-Verwaltungsportal registrieren. Dazu konfigurieren Sie MFA in der Microsoft Intune-Registrierungsanwendung in Azure Active Directory.

__Einschränkungsmöglichkeit für die Registrierung mobiler Geräte__ <!--747596--> Es wurden neue Registrierungseinschränkungen zu Intune hinzugefügt, mit denen sich steuern lässt, welche Mobilgeräteplattformen für die Registrierung zugelassen werden. Intune unterscheidet dabei zwischen den Mobilgeräteplattformen iOS, macOS, Android, Windows und Windows Mobile.
* Durch das Einschränken der Registrierung von Mobilgeräten wird die Registrierung von PC-Clients nicht eingeschränkt.
* Für iOS gibt es eine zusätzliche Option, mit der die Registrierung persönlicher Geräte blockiert werden kann.

Intune kennzeichnet alle neuen Geräte als persönlich, es sei denn, der IT-Administrator kennzeichnet sie als unternehmenseigen – wie in [diesem Artikel](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices) beschrieben.

### <a name="notices"></a>Benachrichtigungen

__Multi-Factor Authentication bei der Registrierung wird in das Azure-Portal verlagert__ <!--VSO 750545--> Bisher mussten sich Administratoren entweder bei der Intune-Konsole oder der Configuration Manager-Konsole (vor der Version von Oktober 2016) anmelden, um MFA für Intune-Registrierungen festzulegen. Mit diesem aktualisierten Feature melden Sie sich jetzt mit Ihren Intune-Anmeldeinformationen beim [Microsoft Azure-Portal](https://manage.windowsazure.com) an und konfigurieren die MFA-Einstellungen über Azure AD. Weitere Informationen dazu finden Sie [hier](https://aka.ms/mfa_ad).

__Unternehmensportal-App für Android jetzt in China verfügbar__  <!--VSO 658093--> Wir veröffentlichen die Unternehmensportal-App für Android zum Download in China. Da der Google Play Store in China nicht verfügbar ist, müssen Android-Geräte Apps von chinesischen App-Marktplätzen beziehen. Die Unternehmensportal-App für Android wird in den folgenden Stores zum Download zur Verfügung stehen:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

Die Unternehmensportal-App für Android verwendet Google Play Services für die Kommunikation mit dem Microsoft Intune-Dienst. Da Google Play Services in China noch nicht verfügbar sind, kann die Ausführung der folgenden Aufgaben bis zu 8 Stunden dauern. 

|Intune-Administratorkonsole| Intune-Unternehmensportal-App für Android |Intune Unternehmensportalwebsite|   
|---|---|---|
|Vollständiges Zurücksetzen| Entfernen eines Remotegeräts| Entfernen eines Geräts (lokal und remote)|
|Selektives Zurücksetzen| Zurücksetzen eines Geräts| Zurücksetzen eines Geräts|
|Bereitstellung neuer oder aktualisierter Apps| Installieren von verfügbaren Branchen-Apps| Zurücksetzen der Gerätekennung|
|Remotesperre|||
|Zurücksetzen der Kennung|||

### <a name="deprecations"></a>Veraltete Funktionen

__Firefox-Unterstützung für Silverlight wird eingestellt__ <!--VSO TBA--> Mozilla stellt ab März 2017 die Unterstützung für Silverlight in Version 52 des [Firefox-Browsers](https://www.mozilla.org/firefox) ein. Bei der vorhandenen Intune-Konsole Daher werden Sie sich mit Firefox-Versionen nach Version 51 nicht mehr anmelden können. Wir empfehlen, für den Zugriff auf die Verwaltungskonsole Internet Explorer 10 oder 11 oder eine [Firefox-Version vor Version 52](https://ftp.mozilla.org/pub/firefox/releases/) zu verwenden. Durch den Übergang von Intune zum Azure-Portal wird die Unterstützung einer Reihe von [modernen Browsern](https://docs.microsoft.com/en-us/azure/azure-preview-portal-supported-browsers-devices) ohne Abhängigkeit von Silverlight möglich.

__Entfernung von Postfachrichtlinien für Exchange Online__ <!--770687--> Seit Dezember können Administratoren Richtlinien für das mobile Exchange Online-Postfach (EAS) nicht mehr in der Intune-Konsole anzeigen oder konfigurieren. Das Rollout dieser Änderung erfolgt für alle Intune-Mandanten im Laufe des Dezembers und Januars. Die Konfiguration aller vorhandenen Richtlinien bleibt unverändert. Verwenden Sie zum Konfigurieren neuer Richtlinien die Exchange-Verwaltungsshell. Weitere Informationen finden Sie [hier](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx).

__Intune AV-Player, Image Viewer und PDF-Viewer-Apps werden nicht mehr von Android unterstützt__ <!--747553--> Ab Mitte Dezember 2016 können Benutzer Intune AV-Player-, Image Viewer und PDF-Viewer-Apps nicht mehr verwenden. Diese Apps wurden durch die Azure Information Protection-App ersetzt. [Hier](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq) erfahren Sie mehr über die Azure Information Protection-App.

## <a name="november-2016"></a>November 2016

### <a name="new-capabilities"></a>Neue Funktionen

<!--### View App States for All Platforms in Real Time
App installation status is now shown in real-time in the console. When you previously deployed an app, you had to wait for a targeted device to report back before the app install status was displayed in the Intune console.

### Streamline iOS App Management for your End Users
Intune can now automatically take over management of the previously installed app and no end user action is required.

Previously, if the end user of an enrolled iOS device installed an app from the App Store before you deployed that same app with a deployment action of __Available__, then the end user had to:

1. Open the __Company Portal__.
2. Select the app.
3. Tap __Install__ to enable Intune to take over management of the app.-->

__Neues Microsoft Intune-Unternehmensportal für Windows 10-Geräte__ Microsoft hat eine neue [Microsoft Intune-Unternehmensportal-App für Windows 10-Geräte](https://www.microsoft.com/store/apps/9wzdncrfj3pz) veröffentlicht. Diese App, die das neue universelle Windows 10-Format nutzt, bietet dem Benutzer eine aktualisierte Benutzeroberfläche innerhalb der App und identische Oberflächen auf allen Windows 10-Geräten – sowohl PCs als auch mobilen Geräten – sowie all die Funktionen, die er heute bereits verwendet.

Mit der neuen App können Benutzer auch zusätzliche Plattformfunktionen wie einmaliges Anmelden (SSO) und die zertifikatbasierte Authentifizierung auf Windows 10-Geräten nutzen. Die App wird als Upgrade der vorhandenen Windows 8.1- und Windows Phone 8.1-Unternehmensportalinstallationen im Windows Store zur Verfügung gestellt. Weitere Informationen finden Sie unter [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).

<!--### Support for Windows Store for Business Apps Being Deployed as Available
You can now deploy apps you synchronized from the Windows Store for Business (WSfB) with a deployment action of __Available__ or __Required__. After syncing WSfB apps into Intune, administrators will be able to target those apps as available installs to groups of users. End users will see the deployed WSfB apps as available for install in the Universal Company Portal, where they can choose whether they would like to acquire the apps.

### Conditional Access for MAM with SharePoint Online

You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint online.  You can get started in Intune mobile app management via the Azure portal. Look for the  Conditional Access section in the “Settings” blade which now includes the option for SharePoint online.-->

> [!IMPORTANT]

> __Update auf Intune und Android for Work__

> Wenn Ihre Intune-Gruppen zur neuen Azure AD-Gruppenoberfläche migriert wurden, können Sie Apps nur als __Verfügbar__ bereitstellen, während Sie Android for Work-Apps mit der Aktion __Erforderlich__ bereitstellen können.

__Das Intune App SDK Cordova-Plug-In unterstützt nun MAM ohne Registrierung__ App-Entwickler können das Intune App SDK Cordova-Plug-In jetzt verwenden, um MAM-Funktionalität ohne Geräteregistrierung in Ihren auf Cordova basierenden Apps für Android und iOS zu aktivieren. Sie finden das Intune App SDK Cordova-Plug-in [hier](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam).

__Die Intune App SDK-Xamarin-Komponente unterstützt nun MAM ohne Registrierung__ App-Entwickler können die Intune App SDK Xamarin-Komponente jetzt verwenden, um MAM-Funktionalität ohne Geräteregistrierung in Ihren auf Xamarin basierenden Apps für Android und iOS zu aktivieren. Sie finden die Intune App SDK Xamarin-Komponente [hier](https://github.com/msintuneappsdk/intune-app-sdk-xamarin).

### <a name="notices"></a>Benachrichtigungen

__Kein signiertes Windows Phone 8-Unternehmensportal zum Hochladen des Symantec-Signaturzertifikats mehr erforderlich__ Zum Hochladen des Symantec-Signaturzertifikats ist keine signierte Windows Phone 8-Unternehmensportal-App mehr erforderlich. Das Zertifikat kann einzeln hochgeladen werden.

###<a name="deprecations"></a>Veraltete Funktionen

__Unterstützung für das Windows Phone 8-Unternehmensportal__ Die Unterstützung für das Windows Phone 8-Unternehmensportal wird jetzt beendet. Die Unterstützung für Windows Phone 8- und WinRT-Plattformen wurde im Oktober 2016 beendet. Die Unterstützung für das Windows Phone 8-Unternehmensportal wurde ebenfalls im Oktober 2016 beendet.

## <a name="october-2016"></a>Oktober 2016

### <a name="conditional-access-for-mobile-application-management"></a>Bedingter Zugriff für die mobile Anwendungsverwaltung
Sie können den Zugriff auf Exchange Online einschränken, sodass der Zugriff nur durch Apps erfolgen kann, die wie Outlook Richtlinien zur Intune-Verwaltung von mobilen Anwendungen unterstützen. [Dieses neue Feature](/intune/deploy-use/allow-policy-managed-apps-access-to-o365) stellt die perfekte Ergänzung von Intune-MAM-Richtlinien (Mobile App Management) dar, da Sie nun den Zugriff auf integrierte E-Mail-Clients oder andere Apps, die nicht mit den Intune-MAM-Richtlinien konfiguriert wurden, blockieren können. Dadurch wird sichergestellt, dass Ihre Benutzer mithilfe von Apps auf die Daten Ihrer Organisation zugreifen, die mithilfe von Intune MAM geschützt werden können. Sie können in die Verwaltung von mobilen Apps mithilfe von Intune im Azure-Portal einsteigen. Suchen Sie auf dem Blatt „Einstellungen“ nach dem neuen Abschnitt „Bedingter Zugriff“.

### <a name="conditional-access-for-windows-pcs"></a>Bedingter Zugriff für Windows-PCs
Sie können jetzt über die Intune-Verwaltungskonsole Richtlinien für bedingten Zugriff erstellen, um den Zugriff von Windows-PCs auf [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) und [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune) zu blockieren. Sie können auch Richtlinien für bedingten Zugriff erstellen, um den Zugriff auf Office-Desktop- und universelle Anwendungen zu blockieren.

### <a name="android-for-work-support"></a>Unterstützung für Android for Work

> [!IMPORTANT]

> Wenn Ihre Intune-Gruppen zur neuen Azure AD-Gruppenoberfläche migriert wurden, können Sie Apps nur als __Verfügbar__ bereitstellen, während Sie Android for Work-Apps mit der Aktion __Erforderlich__ bereitstellen können.

Intune ist jetzt Teil des Android for Work-Programms (AfW). Die Einführung des Supports für AfW-Features wird diesen Monat beginnen und über die nächsten Monate fortgesetzt. Beachten Sie, dass verfügbare App-Bereitstellungen von AfW das neue Feature für Gruppierung und Zielgruppenadressierung nutzen. Neu bereitgestellte Intune-Dienstkonten werden dieses Feature nutzen können, sobald AfW für sie zur Verfügung gestellt wurde.

<!--Existing Intune customers can use this feature in production once their tenant has been migrated. Existing customers are welcome to create a trial Intune account to plan for and test this feature until their tenant has been migrated. Any questions on grouping and targeting timelines, please contact our [migration team](mailto:intunegrps@microsoft.com).-->

[Lesen Sie die Ankündigung von Microsoft zur Intune-Unterstützung für Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

Die folgenden Intune-Themen sind neu oder wurden mit Informationen zu Android for Work aktualisiert:

Für IT-Experten:
- [Einrichten von Android for Work](/intune/deploy-use/set-up-android-for-work)
<!--- [Nathan Bigman's resource access topics]()-->
- [Beschränken des E-Mail-Zugriffs auf Exchange Online- und neue Exchange Online Dedicated-Umgebungen mit Intune](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [Beschränken des E-Mail-Zugriffs auf lokale Exchange- und ältere Exchange Online Dedicated-Umgebungen mit Intune](/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Einstellungen für Kompatibilitätsrichtlinien für Android for Work](/intune/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [Bereitstellen von Android for Work-Apps](/intune/deploy-use/android-for-work-apps)
- [Konfigurieren von Android for Work-Apps mit Konfigurationsrichtlinien für mobile Apps](/intune/deploy-use/afw-app-configuration-policy)
- [Android for Work-Richtlinieneinstellungen](/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

Für Endbenutzer:
- [Was geschieht beim Erstellen eines Arbeitsprofils?](/intune/enduser/what-happens-when-you-create-a-work-profile-android)
- [Erstellen eines Arbeitsprofils und Registrieren Ihres Geräts bei Intune](/intune/enduser/create-a-work-profile-and-enroll-your-device-in-intune-android)

### <a name="lookout-integration-to-protect-ios-devices"></a>Lookout-Integration zum Schutz von iOS-Geräten
Im Oktober integriert Microsoft die Mobile Threat Protection-Lösung von Lookout, um mobile iOS-Geräte durch die Erkennung von Schadsoftware, gefährlichen Apps usw. auf Geräten zu schützen. Mithilfe der Lösung von Lookout können Sie die Bedrohungsstufe bestimmen und konfigurieren. Sie können in Intune eine Regel der Kompatibilitätsrichtlinie erstellen, um die Gerätekonformität auf der Grundlage der Risikobewertung durch Lookout zu bestimmen. Mithilfe von Richtlinien für den bedingten Zugriff können Sie den Zugriff auf Unternehmensressourcen auf der Basis des Kompatibilitätsstatus des Geräts zulassen oder blockieren.

Endbenutzer nicht kompatibler iOS-Geräte werden zur Registrierung aufgefordert und müssen die Lookout for Work-App auf ihren Geräten installieren, die App aktivieren und in der Lookout for Work-Anwendung gemeldete Bedrohungen beheben, um auf Unternehmensdaten zugreifen zu können. Hier erhalten Sie Informationen zum [Konfigurieren und Bereitstellen von Lookout for Work-Apps](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps).
<!--TFS 1319493-->

<!--### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new [Microsoft Intune Company Portal for Windows 10 devices](https://go.microsoft.com/fwlink/?linkid=830663). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store.-->

### <a name="intune-app-wrapping-tool-for-android"></a>Intune App Wrapping Tool für Android
Sie können Ihre Apps mit dem Intune App Wrapping Tool für die Verwendung von Intune-MAM-Richtlinien (Verwaltung mobiler Anwendungen) aktivieren. Die Unterstützung für Intune-MAM-Richtlinien ohne Registrierung des Geräts ist nun verfügbar.

### <a name="manage-printing-from-apps-managed-using-mam-policies"></a>Verwalten von Druckvorgängen von mit MAM-Richtlinien verwalteten Apps
Sie können jetzt verhindern, dass über Apps, die über MAM-Richtlinien verfügen, Unternehmensdaten gedruckt werden. Diese Einstellung ist im [Azure-Portal](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) verfügbar und wird sowohl auf [iOS](/Intune/deploy-use/ios-mam-policy-settings)- als auch [Android](/Intune/deploy-use/android-mam-policy-settings)-Geräten unterstützt.
<!--TFS 1014328-->

### <a name="support-for-fingerprints-on-android-devices"></a>Unterstützung für Fingerabdrücke auf Android-Geräten
Android-MAM-Richtlinien (Mobile App Management, Verwaltung mobiler Apps) ermöglichen jetzt allen Benutzern den Zugriff auf eine App mithilfe ihres Fingerabdrucks anstatt durch Eingabe einer PIN. Informieren Sie sich hierzu und zu weiteren [Richtlinieneinstellungen für die Verwaltung mobiler Apps für Android](/Intune/deploy-use/android-mam-policy-settings).

### <a name="notices"></a>Benachrichtigungen

__Kompatibilität von Android Samsung KNOX mit Intune__ Bestimmte Modelle des Telefons Samsung Galaxy Ace können nicht von Intune als Samsung KNOX-Geräte verwaltet werden. Wenn Sie diese Geräte in Intune registrieren, werden sie stattdessen als Android-Standardgeräte verwaltet.

Folgende Modellnummern sind betroffen:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Weder Sie noch Ihre Endbenutzer müssen weitere Schritte unternehmen. Weitere Informationen finden Sie auf der [Samsung KNOX](https://www.samsungknox.com)-Website.

__Unternehmensportal-App für Windows 8 ist veraltet; Unterstützung für Windows Phone 8- und Windows RT-Plattformen wird beendet__ Ab Oktober 2016 wird Microsoft Intune die Unterstützung für das Windows 8-Unternehmensportal beenden. Microsoft Intune wird auch die Unterstützung für die Windows Phone 8- und Windows RT-Plattformen beenden. Die Registrierung oder Aktualisierung von Windows Phone 8- oder Windows RT-Geräten wird daher nicht mehr möglich sein.

Bereits registrierte Windows Phone 8-, Windows RT- und Windows 8-Geräte können weiterhin verwaltet werden. Aktualisieren Sie Windows Phone 8- und Windows 8-Geräte auf Windows Phone 8.1 und Windows 8.1, und nutzen Sie die entsprechenden Windows Phone 8.1- und Windows 8.1-Unternehmensportal-Apps, um weiterhin Apps an diese Geräte verteilen zu können.

Ab November 2016 wird die Unterstützung für das Windows Phone 8-Unternehmensportal beendet.
<!--TFS 1255391-->

### <a name="whats-coming"></a>Was steht an?

__Neues Microsoft Intune-Unternehmensportal für Windows 10-Geräte__ Microsoft veröffentlicht ein neues Microsoft Intune-Unternehmensportal für Windows 10-Geräte. Diese App, die das neue universelle Windows 10-Format nutzt, bietet dem Benutzer eine aktualisierte Benutzeroberfläche innerhalb der App und identische Oberflächen auf allen Windows 10-Geräten – sowohl PCs als auch mobilen Geräten – sowie all die Funktionen, die er heute bereits verwendet.

Mit der neuen App können Benutzer auch zusätzliche Plattformfunktionen wie einmaliges Anmelden (SSO) und die zertifikatbasierte Authentifizierung auf Windows 10-Geräten nutzen. Die App wird als Upgrade der vorhandenen Windows 8.1- und Windows Phone 8.1-Unternehmensportalinstallationen im Windows Store zur Verfügung gestellt. Weitere Informationen finden Sie unter [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).
<!--TFS 1016502-->

## <a name="september-2016"></a>September 2016
### <a name="new-features-announcements-and-information"></a>Neue Funktionen, Ankündigungen und Informationen
* [Bedingter Zugriff für Windows](#windows-conditional-access)
* [iOS 10-Unterstützung](#ios-10-support)
* [Das App Wrapping-Tool unterstützt MAM ohne Geräteregistrierung für Android und iOS](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [Die Umstellung von Intune-Gruppen auf Azure Active Directory beginnt im September](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Lookout-Integration zum Schutz von Android-Geräten](#lookout-integration-to-protect-android-devices)
* [Unternehmensportal-Updates für Android, iOS und Windows](#company-portal-updates)
* [Intune-Glossar](#intune-glossary)
* [Was steht an?](#whats-coming)

### <a name="windows-conditional-access"></a>Bedingter Zugriff für Windows
Sie können jetzt über die Intune-Verwaltungskonsole Richtlinien für bedingten Zugriff erstellen, um den Zugriff von Windows-PCs auf Exchange Online und SharePoint Online zu blockieren. Sie können auch Richtlinien für bedingten Zugriff erstellen, um den Zugriff auf Office-Desktop- und universelle Anwendungen zu blockieren.

### <a name="ios-10-support"></a>iOS 10-Unterstützung
Vorhandene Intune-MDM- und-MAM-Szenarien sind mit iOS 10 kompatibel. Tipps finden Sie im [Intune-Supportteamblog](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/).

### <a name="app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios"></a>Das App Wrapping-Tool unterstützt MAM ohne Geräteregistrierung für Android und iOS
Das Intune App Wrapping-Tool ist ein Befehlszeilentool, das verwendet wird, um Intune-MAM in Branchen-Apps (LOB, Line-of-Business) für iOS und Android zu aktivieren . Es stellt die einfachste Möglichkeit dar, das Intune MAM-SDK in Ihre App zu integrieren, sodass Ihre App die durch Intune bereitgestellten MAM-Richtlinien durchsetzen kann. MAM-Richtlinien bieten Ihnen diese Möglichkeiten:

1. Verschlüsseln der Daten der App.
2. Vorschreiben der Eingabe einer PIN beim Starten der App durch den Information Worker.
3. Einschränken der Übermittlung von Daten durch die App auf andere verwaltete Apps.
4. Verhindern der Sicherung von Daten nach Android, iTunes und iCloud durch die App.
5. Ausschneiden, Kopieren und Einfügen nur im Zusammenwirken mit anderen verwalteten Apps.

Die öffentliche Vorschau des aktualisierten Intune App Wrapping-Tools unterstützt jetzt MAM ohne Geräteregistrierung für interne Branchen-Apps unter iOS und Android. Das bedeutet, dass Ihre Benutzer ihre Geräte nicht bei Intune registrieren müssen, um MAM-aktivierte Branchen-Apps zu verwenden.

Jeder kann die öffentliche Vorschausoftware testen und die nützliche Dokumentation lesen, die sich auf dem msintuneappsdk-GitHub befindet:

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Damit Sie das Microsoft Intune App Wrapper für Android und iOS Pre-Release installieren und verwenden können, müssen diese Voraussetzungen erfüllt sein:

* Sie müssen die Microsoft-Lizenzbedingungen für das Microsoft Intune App Wrapping-Tool für Android und iOS Pre-Release lesen
* Drucken Sie die Lizenzbedingungen aus, und heben Sie eine Kopie für Ihre Unterlagen auf. Indem Sie das Microsoft Intune App Wrapping-Tool für Android Pre-Release herunterladen und verwenden, stimmen Sie diesen Lizenzbedingungen zu. Wenn Sie sie nicht akzeptieren, dürfen Sie die Software nicht verwenden.
<!---TFS 1235607--->

### <a name="intune-groups-begin-transitioning-to-azure-active-directory-in-september"></a>Die Umstellung von Intune-Gruppen auf Azure Active Directory beginnt im September
Einige neue Intune-Konten verwenden Azure Active Directory-Sicherheitsgruppen anstelle von Intune-Benutzergruppen. Sie werden bemerken, dass Sie mit Sicherheitsgruppen arbeiten, da die Gruppenseite auf dem Intune-Portal dann über einen Link zum Azure-Verwaltungsportal verfügt.

### <a name="lookout-integration-to-protect-android-devices"></a>Lookout-Integration zum Schutz von Android-Geräten
Microsoft integriert die Lookout-Lösung zum Schutz vor Bedrohungen auf mobilen Geräten, um mobile Android-Geräte durch das Erkennen von Schadsoftware, gefährlichen Apps und mehr auf Geräten zu schützen. Mithilfe der Lösung von Lookout können Sie die Bedrohungsstufe bestimmen und konfigurieren. Sie können in Intune eine Regel der Kompatibilitätsrichtlinie erstellen, um die Gerätekonformität auf der Grundlage der Risikobewertung durch Lookout zu bestimmen. Mithilfe von Richtlinien für den bedingten Zugriff können Sie den Zugriff auf Unternehmensressourcen auf der Basis des Kompatibilitätsstatus des Geräts zulassen oder blockieren.

Endbenutzer nicht kompatibler Geräte werden zur Registrierung aufgefordert, und die Installation der Lookout for Work-Anwendung auf Android-Geräten, die Aktivierung der App und die Behebung der in der Lookout for Work-Anwendung erkannten Bedrohungen wird vorgeschrieben, bevor der Zugriff erteilt wird. Weitere Informationen finden Sie unter [Einschränken des Zugriffs auf der Basis von Geräte-, Netzwerk- und Anwendungsrisiko](https://docs.microsoft.com/en-us/intune/deploy-use/restrict-access-based-on-device-network-app-risk).


### <a name="company-portal-updates"></a>Aktualisierungen am Unternehmensportal

__Android__

<p style="margin-left: 40px">**Hinzufügen von „Benachrichtigungen“ zum Unternehmensportal für Android**<br/>
<p style="margin-left: 40px">Dem Unternehmensportal für Android wurde auf der Startseite ein neues Symbol „Benachrichtigungen“ hinzugefügt. Beim Tippen auf dieses Symbol wird auf die Seite „Benachrichtigungen“ zugegriffen, die Ihren Endbenutzern alle Elemente in der Unternehmensportal-App anzeigt, die ihr Eingreifen erfordern, etwa inkompatible Geräte, Aktualisierung der Registrierung und Aktivierung der Registrierung. Das iOS-Unternehmensportal verfügt bereits über diese Benachrichtigungsfunktionalität. Durch die neue Seite „Benachrichtigungen“ wird Benutzern nicht bei jedem Starten oder erneuten Anzeigen des Unternehmensportals die Seite „Einrichten des Unternehmenszugriffs“ angezeigt, sofern das Gerät bereits registriert ist. Wenn Sie eine eigene Hilfestellung für Endbenutzer erstellen, empfiehlt es sich, Ihre Dokumentation entsprechend zu aktualisieren, um dieser Änderung Rechnung zu tragen. Aktualisierte Screenshots finden Sie [hier](https://aka.ms/androidcpupdate).  

__iOS__
<p style="margin-left: 40px">**Änderungen bei der Unterstützung der iOS-Unternehmensportal-App**<br/>
<p style="margin-left: 40px">Alle Benutzer der Microsoft Intune-Unternehmensportal-App für iOS müssen jetzt die aktuelle Version verwenden. Neue Benutzer können ausschließlich die neueste Version herunterladen, und aktuelle Benutzer müssen ein Update auf sie ausführen. Die aktuelle Version erfordert iOS 8.0 oder höher. Daher können Benutzer von Geräten mit älteren iOS-Versionen das Unternehmensportal erst dann nutzen und eine Registrierung durchführen, wenn sie ihr Gerät auf iOS 8.0 oder höher aktualisieren und anschließend die Unternehmensportal-App auf die aktuelle Version aktualisieren. Registrierte Geräte mit Versionen vor iOS 8.0 werden weiterhin verwaltet und in der Intune-Verwaltungskonsole aufgeführt.
<!---TFS 1283165--->

<p style="margin-left: 40px">**Verbesserungen für das Abrufen von Apps durch iOS-Endbenutzer**<br/>
<p style="margin-left: 40px">Die folgenden Änderungen wurden an den App-Kacheln in der Unternehmensportal-App für iOS vorgenommen, damit Benutzer für alle ihre Apps an einer einzigen Stelle an verschiedene Ansichten verwiesen werden: auf der Unternehmensportal-Website. Einschränkungen seitens Apple verhindern das Auflisten branchenspezifischer und verwalteter App Store-Apps in der Unternehmensportal-App, sodass Benutzer verschiedene Ansichten besuchen müssen, um all ihre Apps zu finden.

<p style="margin-left: 40px">Die Kachel **Unternehmens-Apps** verwies zuvor auf eine Liste aller Apps auf der Registerkarte ALLE der Unternehmensportal-Website, und diese Funktion bleibt weiterhin bestehen. Der Name der Kachel wurde in **Alle Apps** geändert.

<p style="margin-left: 40px">Die Kachel **Andere Apps** verwies zuvor auf eine Ansicht innerhalb der Unternehmensportal-App, in der alle Apps aufgeführt werden, deren Anzeige Apple der Unternehmensportal-App gestattet. Der Name der Kachel wurde in **Ausgewählte Apps** geändert, und durch Tippen auf die Kachel gelangen Benutzer auf die Registerkarte AUSGEWÄHLTE der Unternehmensportal-Website.

<p style="margin-left: 40px">Die Kachel **Kategorien** verwies zuvor auf eine Ansicht innerhalb der Unternehmensportal-App, in der Kategorien von Apps aufgeführt werden. Der Name der Kachel hat sich nicht geändert, aber sie verweist jetzt auf die Registerkarte KATEGORIEN der Unternehmensportal-Website. Aktualisierte Screenshots finden Sie [hier](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
  <!---TFS 1317133--->

<p style="margin-left: 40px">**Aufforderung zur Installation der iOS-App „Managed Browser“, wenn IT-Experten diese Anforderung für eine App festlegen**<br/>
<p style="margin-left: 40px">Wenn Sie einen Webclip so konfiguriert haben, dass er nur im verwalteten Browser geöffnet wird, und der verwaltete Browser auf einem Gerät nicht installiert ist, wird der Benutzer von der Unternehmensportal-App auf dem Gerät aufgefordert, den verwalteten Browser zu installieren, damit der Webclip installiert werden kann.
  <!---TFS 1228570--->

__Windows__
<p style="margin-left: 40px">**Der Windows Phone 8.1-Unternehmensportal-App wurde eine Feedbackschaltfläche hinzugefügt**<br/>
<p style="margin-left: 40px">Die Windows Phone 8.1-Unternehmensportal-App ermöglicht Endbenutzern, Feedback zur App mithilfe einer neuen Schaltfläche „Feedback senden“ zu senden. Benutzer finden die Schaltfläche durch Tippen auf das Drei-Punkte-Menü unten rechts auf dem Bildschirm der Unternehmensportal-App und anschließendes Tippen auf **Feedback senden**. Das gesammelte anonymisierte Feedback hilft Microsoft, die Benutzerfreundlichkeit der Unternehmensportal-App zu verbessern.
<!---TFS 1317806--->

### <a name="intune-glossarybr"></a>Intune-Glossar</br>
Wir haben der Bibliothek einen neuen [Glossarabschnitt](https://docs.microsoft.com/intune/understand-explore/intune-glossary) hinzugefügt, in dem einige der im Intune-Produkt verwendeten Begriffe erläutert werden.

## <a name="august-2016"></a>August 2016
### <a name="app-management"></a>App-Verwaltung
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

__Aus- und eingeblendete Apps für iOS 9.3__ Bei Geräten mit iOS 9.3 oder höher können Sie die Liste für aus- und eingeblendete Apps in der allgemeinen iOS-Konfigurationsrichtlinie für folgende Aufgaben verwenden:
- Angeben einer Liste von Apps, die vor Benutzern verborgen werden. Benutzer können diese Apps weder anzeigen noch starten.
- Angeben einer Liste von Apps, die Benutzer anzeigen und starten können. Es können keine anderen Apps angezeigt oder gestartet werden.

Die Apps, die Sie angeben können, umfassen sowohl von Ihnen bereitgestellte Apps als auch integrierte iOS-Apps, wie „Nachrichten“ und „Notizen“. Weitere Informationen finden Sie unter [iOS-Richtlinieneinstellungen in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune).
<!---TFS 1279009 checked--->
__Richtlinie für zugelassene und blockierte Apps für Samsung Knox-Geräte__ Sie können jetzt eine benutzerdefinierte Richtlinie für Samsung Knox-Geräte konfigurieren, die Ihnen das Erstellen einer der folgenden Listen ermöglicht:
- Eine Liste von Apps, deren Ausführung auf dem Gerät blockiert wird. Eine in der Liste blockierter Apps definierte App kann nicht auf dem Gerät aktiviert werden, auch wenn sie auf dem Gerät installiert ist.
- Eine Liste von Apps, die Benutzer des Geräts aus dem Google Play Store installieren dürfen. Es können keine anderen Apps aus dem Store installiert werden.

Diese Einstellungen können nur von Geräten verwendet werden, auf denen Samsung KNOX ausgeführt wird.
Weitere Informationen finden Sie unter [Use custom policies to allow and block apps for Samsung KNOX devices](https://docs.microsoft.com/en-us/intune/deploy-use/custom-policy-to-allow-and-block-samsung-knox-apps) (Verwenden von benutzerdefinierten Richtlinien zum Zulassen und Blockieren von Apps für Samsung KNOX-Geräte).
<!---TFS 1311629 checked --->

__Neue Apps, die mit MAM-Richtlinien (Verwaltung mobiler Anwendungen) kompatibel sind__ Die Yammer-App für [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) und [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) ist nun mit [Intune-Richtlinien für die Verwaltung mobiler Anwendungen (mobile application management, MAM)](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) kompatibel. Dies gilt unabhängig davon, ob das Gerät registriert ist oder nicht.

Eine vollständige Liste MAM-kompatibler Apps finden Sie auf der Website [Microsoft Intune-Anwendungspartner](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners).
<!--- TFS 1252335 & 1252336 checked--->


<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

__Intune Viewer-Apps__ Mit dem Release der neuen RMS-Freigabeanwendung werden wir ab August 2016 die folgenden Intune Viewer-Apps entfernen:
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer für Android aus Google Play

Anstatt die Intune-Viewer-Apps zu verwenden, empfehlen wir die Nutzung der neuen [Rights Management-App (RMS-Freigabe)](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app) für Android, die Ihnen das Bereitstellen einer App anstelle von drei getrennten Apps ermöglicht, um Unternehmensdateien sicher auf Android-Geräten anzuzeigen. Wenn die Intune-Viewer-App nicht mehr unterstützt wird, wird sie aus dem Google Store entfernt und steht nicht mehr zur zukünftigen Verwendung zur Verfügung.

### <a name="device-management"></a>Geräteverwaltung
__Android 7.0-Unterstützung__ Intune bietet „Tag 0“-Unterstützung für das bevorstehende Android 7.0-Betriebssystem für mobile Geräte.
<!---TFS 1262053--->
### <a name="google-removal-of-remote-passcode-reset-capability-on-android-70-devices"></a>Funktion für das Remote-Zurücksetzen von Passcodes auf Android 7.0-Geräten von Google entfernt
Die Funktion, durch die IT-Administratoren und Endbenutzer den Passcode von Android 7.0-Geräten remote zurücksetzen konnten, wurde von Google entfernt. Zuvor konnten IT-Administratoren Benutzerpasscodes remote zurücksetzen, und Endbenutzer konnten ihre Passcodes auf der Unternehmensportal-Website zurücksetzen.



### <a name="company-portal-updates"></a>Aktualisierungen am Unternehmensportal
__Unternehmensportal-Website__
- **Feedbacklink vom Unternehmensportal zu Microsoft** <br/>
Auf der Unternehmensportal-Website können Endbenutzer auf einen neuen „Feedbacklink“ am unteren Seitenrand tippen, um Feedback zu ihren Erfahrungen mit der Website an Microsoft zu senden. Das gesammelte anonymisierte Feedback hilft Microsoft, die Benutzerfreundlichkeit der Unternehmensportal-Website zu verbessern.
<!--- TFS 1313657 checked--->

__iOS__
- **Minimale Version des Managed Browser für iOS auf 8.0 aktualisiert**<br/>
Die Microsoft Intune Managed Browser-App für iOS wurde aktualisiert, um Geräte zu unterstützen, die iOS 8.0 oder höher ausführen. iOS 7.1-Geräte können zwar weiterhin die vorhandene Managed Browser-App verwenden, fordern Sie Ihre Benutzer jedoch auf, auf iOS 8.0 oder höher zu aktualisieren, um die neuen Features von Managed Browser in vollem Umfang zu nutzen.  
<!---TFS 1313253 checked--->

### <a name="whats-coming"></a>Was steht an?
__Übergang von Intune-Gruppen zu Azure Active Directory-Gruppen ab September 2016__ Intune erstellt eine neue Benutzeroberfläche für die Gruppenverwaltung, die Azure Active Directory-Sicherheitsgruppen (AAD) als Benutzer- und Gerätegruppen in Intune verwendet. Diese Gruppen werden für sämtliche Gruppenverwaltung, Richtlinien- und Profilbereitstellung verwendet, **wenn das neue Intune-Verwaltungsportal auf Azure-Basis eingeführt wird**.

Diese neue Benutzeroberfläche verhindert, dass Sie Gruppen zwischen Diensten duplizieren müssen, **ermöglicht Ihnen den Zugriff auf einige neue Gruppenfeatures in Azure Active Directory Premium (AADP)** und bietet Erweiterbarkeit mithilfe von PowerShell und Graph. Dies vereinheitlicht auch die Gruppenverwaltungsoberfläche der Enterprise Mobility-Verwaltung übergreifend.

Um den Wechsel zu Sicherheitsgruppen zu ermöglichen, wird die Benutzeroberfläche in der **aktuellen Administratorkonsole** einige Änderungen erfahren. **Diese Änderungen und die Verwendung von AAD-Sicherheitsgruppen werden in der Intune-Dokumentation aufgezeichnet**.

Neue Intune-Kunden **sehen einige der Sicherheitsgruppenänderungen, bevor aktuelle Mandanten sie sehen**.

Zusätzlich zu Änderungen der Gruppenverwaltung **werden die folgende Funktionen als veraltet markiert**:
- Ausschließen von Mitgliedern oder Gruppen beim Erstellen einer neuen Gruppe
- **Nicht gruppierte Benutzer** und **Nicht gruppierte Geräte**
- **Verwalten von Gruppen** in der Dienstadministratorrolle
- Benutzerdefinierte gruppenbasierte Warnungen für Benachrichtigungsregeln
- Pivotieren mit Gruppen in Berichten
<!--- TFS 1295329--->

__Hinzufügen von „Benachrichtigungen“ zum Unternehmensportal für Android__ Im September veröffentlichen wir ein Update zum Unternehmensportal für Android, mit dem auf der Startseite das neue Symbol **Benachrichtigungen** eingeführt wird. Beim Tippen auf dieses Symbol wird die Seite **Benachrichtigungen** aufgerufen, auf der für Ihre Endbenutzer alle Elemente angezeigt werden, die in der Unternehmensportal-App Aufmerksamkeit erfordern, z. B. Nichtkompatibilität, Registrierungsupdate und Registrierungsaktivierung. Wenn Sie auch die iOS-Unternehmensportal-App verwenden, sehen Sie die Benachrichtigungen bereits. Wenn die Seite **Benachrichtigungen** eingeführt wird, werden Sie die Seite **Unternehmenszugriff einrichten** nicht bei jedem Start bzw. jeder Fortsetzung des Unternehmensportals für Android sehen, solange das Gerät bereits registriert ist. Wir haben erfahren, dass viele von Ihnen Endbenutzeranleitungen erstellt haben, und würden eine vorherige Mitteilung schätzen, wenn Ihre Anleitung/Screenshots vielleicht aktualisiert werden müssen. Bitte aktualisieren Sie Ihre Dokumentation gemäß der anstehenden Änderung der Benutzeroberfläche. Aktualisierte Screenshots finden Sie hier: https://aka.ms/androidcpupdate.  

### <a name="service-deprecation"></a>Veraltete Dienste
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **Änderungen bei der Unterstützung der iOS-Unternehmensportal-App**<br/>
Ab September müssen alle Benutzer der Microsoft Intune-Unternehmensportal-App für iOS die aktuelle Version verwenden. Neue Benutzer können nur die aktuelle Version herunterladen, und derzeitige Benutzer müssen ein Update auf die aktuelle Version durchführen. Die aktuelle Version erfordert iOS 8.0 oder höher. Daher können Benutzer von Geräten mit älteren iOS-Versionen erst dann das Unternehmensportal nutzen und eine Registrierung durchführen, wenn sie ihr Gerät auf iOS 8.0 oder höher aktualisieren und anschließend die Unternehmensportal-App auf die aktuelle Version aktualisieren. Registrierte Geräte mit Versionen vor iOS 8.0 werden weiterhin verwaltet und in der Intune-Verwaltungskonsole aufgeführt.  

- **Minimale Version des Managed Browser für iOS auf 8.0 aktualisiert**<br/>
Im August wird Intune eine aktualisierte Microsoft Intune Managed Browser-App für iOS veröffentlichen, die nur Geräte unter iOS 8.0 oder höher unterstützt. iOS 7.1-Geräte können zwar weiterhin die vorhandene Managed Browser-App verwenden, doch fordern Sie Ihre Benutzer bitte auf, auf iOS 8.0 oder höher zu aktualisieren und die neuen Features von Managed Browser in vollem Umfang zu nutzen.  
<!---TFS 1313253--->

- **Unternehmensportal-Apps für Windows 8 und Windows Phone 8 werden ab September 2016 eingestellt** <br/>
Ab September 2016 stellt Microsoft Intune die Unterstützung für die Microsoft Intune-Unternehmensportal-Apps für die Plattformen Windows Phone 8 und Windows 8 ein. Aktualisieren Sie die Geräte auf Windows 8.1 und Windows Phone 8.1, und nutzen Sie die entsprechenden Windows 8.1- und Windows Phone 8.1-Unternehmensportal-Apps, um weiterhin Apps an diese Geräte zu verteilen.
<!---TFS 1255391--->

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->
## <a name="july-2016"></a>Juli 2016
### <a name="app-management"></a>App-Verwaltung

__Verbessern der Benutzererfahrung beim Update des App-Bereitstellungsprofils__ Die Apple iOS-Reihe mobiler Geschäfts-Apps wird mit einem integrierten Bereitstellungsprofil erstellt und mit Code, der mit einem Zertifikat signiert wurde. Beim Ausführen der App auf einem iOS-Gerät bestätigt iOS die Integrität der iOS-App und erzwingt Richtlinien, die durch das Bereitstellungsprofil definiert werden.

Das Unternehmenssignaturzertifikat, das Sie zum Signieren von Apps verwenden, ist in der Regel 3 Jahre lang gültig. Allerdings läuft das Bereitstellungsprofil nach 1 Jahr ab. Mit diesem Update stellt Intune Ihnen die Tools zum proaktiven Bereitstellen einer neuen Richtlinie für Bereitstellungsprofile auf Geräten zur Verfügung, auf denen Apps installiert sind, die bald ablaufen, während das Zertifikat noch gültig ist. Weitere Informationen finden Sie unter [Use iOS mobile provisioning profile policies to keep your line of business apps up to date](/intune/deploy-use/ios-mobile-app-provisioning-profiles) (Verwenden von Richtlinien für iOS-Mobilbereitstellungsprofile, um Ihre Business-Apps aktuell zu halten).
<!--- TFS 1280247--->

__Xamarin SDK für Intune-Apps ist verfügbar__ Mit der Intune-App SDK-Xamarin-Komponente können Sie die Intune-Verwaltungsfeatures für mobile Apps in Ihren mit Xamarin erstellten mobilen iOS- und Android-Apps aktivieren. Sie finden die Komponente im [Xamarin Store](https://components.xamarin.com/view/Microsoft.Intune.MAM) oder auf der [Microsoft Intune-Github-Seite](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

### <a name="device-management"></a>Geräteverwaltung
__Höhere Limits bei der Geräteregistrierung__ Intune erhöhte das maximal konfigurierbare Limit für die Geräteregistrierung von 5 auf 15 Geräte pro Benutzer.
<!---TFS 1289896 --->

__TeamViewer-Integration für Windows-PCs, auf denen die Intune-Clientsoftware ausgeführt wird__
 Mithilfe der [TeamViewer](https://www.teamviewer.com)-Integration für Windows-PCs, auf denen der Intune-Client ausgeführt wird, können Sie Remoteunterstützungssitzungen mit Windows-PCs herstellen, um Helpdeskabteilungen für Endbenutzer zu entlasten. Dies gilt für Windows 7, 8, 8.1 und Windows 10. Weitere Informationen finden Sie unter [Allgemeine Aufgaben zur Verwaltung von Windows-PCs mit dem Microsoft Intune-Computerclient](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

### <a name="company-portal-updates"></a>Aktualisierungen am Unternehmensportal

__Unternehmensportal-Website__
- **Verbesserte Endbenutzererfahrung bei der Registrierung von Windows-Geräten**<br/>
Wenn Sie den bedingten Zugriff verwenden, werden die Registrierungsschritte für Windows 8.1, Windows 10 Desktop und Windows 10 Mobile in der Unternehmensportal-Website erklärt. Benutzer sehen jetzt die separaten Schritte „Geräteregistrierung“ und „Workplace Join“, mit denen sie leichter den Status ihres Geräts anzeigen und den Prozess abschließen können, wenn ein Fehler beim Workplace Join (WPJ) auftritt. Die separaten Schritte sollten auch die Problembehandlung für IT-Administratoren vereinfachen. Wenn Endbenutzer versuchten, das Gerät zu registrieren, und alle Registrierungsschritte außer dem WPJ erfolgreich verliefen, wurde das registrierte Gerät bisher nicht in der Liste der Geräte angezeigt, die Benutzer identifizieren konnten, und dies verwirrte die Benutzer.

__Android__
- **Android-Unternehmensportal-App**<br/>
Wenn Android-Endbenutzer eine Fehlermeldung erhalten, ihrem Gerät fehle ein erforderliches Zertifikat, können sie auf eine Schaltfläche „Problembehebung“ tippen, um [Schritte](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) für die Installation des fehlenden Zertifikats abzurufen. Wenn Benutzer die Schritte ausführen, jedoch eine zusätzliche „Fehlendes Zertifikat“-Fehlermeldung angezeigt wird, werden sie aufgefordert, sich an ihren IT-Administrator zu wenden und diesen [Link](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues) anzugeben, der Schritte enthält, mit denen IT-Administratoren das Zertifikatsproblem beheben können.

- **Einschränken der Installationen quergeladener Apps auf registrierten Geräten**<br/>
Auf Android-Geräten können nicht mehr Apps über die Unternehmensportal-Website installiert werden, es sei denn, die Geräte wurden mithilfe der Intune-Unternehmensportal-App für Android in Intune registriert.
<!---TFS 1299082--->

__iOS__
- **Änderungen an den Geräteregistrierungs-Manager-Konten in der iOS-Unternehmensportal-App**<br/>
Zum Verbessern der Leistung und Skalierung zeigt Intune nicht mehr alle Geräte des Geräteregistrierungs-Managers (Device Enrollment Manager, DEM) im Bereich **Meine Geräte** der Unternehmensportal-App für iOS an. Nur das lokale Gerät, das die App ausführt, wird angezeigt, und dies nur, wenn es über die Unternehmensportal-App registriert wurde.

Der DEM-Benutzer kann Aktionen auf dem lokalen Gerät ausführen, aber die Remoteverwaltung der anderen registrierten Geräte kann nur über die Intune-Verwaltungskonsole ausgeführt werden. Darüber hinaus wird in Intune die Verwendung von DEM-Konten mit dem Apple-Geräteregistrierungsprogramm oder dem Apple Configurator-Tool eingestellt. Diese beiden Registrierungsmethoden unterstützen bereits die benutzerunabhängige Registrierung für gemeinsam genutzte iOS-Geräte.

Verwenden Sie DEM-Konten nur, wenn die benutzerunabhängige Registrierung für gemeinsam genutzte Geräte nicht verfügbar ist. Weitere Informationen siehe [Registrieren von firmeneigenen Geräten mit dem Geräteregistrierungs-Manager in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### <a name="change-of-names-for-windows-features"></a>Ändern von Namen für Windows-Features
- [Microsoft Passport für Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) heißt jetzt **Windows Hello for Business**.
- [Unternehmensdatenschutz](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) heißt jetzt **Windows Information Protection**.


<!--HONumber=Jan17_HO2-->


