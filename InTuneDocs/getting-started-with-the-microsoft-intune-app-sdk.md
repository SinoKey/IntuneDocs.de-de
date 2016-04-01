---
Titel: Erste Schritte mit dem Microsoft Intune App SDK
MS.Custom: Na
MS.Reviewer: Na
MS.Suite: Na
MS.tgt_pltfrm: Na
MS.topic: Artikel
MS.AssetId: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
Autor: Msmbaldwin
---
# Erste Schritte mit dem Microsoft Intune App SDK
Dieser Leitfaden für die ersten Schritte soll Ihnen dabei helfen, Ihre mobile App schnell für die Verwaltung mobiler Anwendungen (Mobile Application Management, MAM) mit Microsoft Intune zu aktivieren. Kann hilfreich sein, die Vorteile des Intune-App-SDK zunächst verstehen, wie in aufgelisteten die [Übersicht](overview-of-the-microsoft-intune-app-sdk.md).

In diesem Leitfaden werden die wichtigsten Schritte zum Aktivieren der Verwaltung mobiler Anwendungen in Ihrer App mit Microsoft Intune vorgestellt. Das Intune App SDK unterstützt plattformübergreifend vergleichbare Szenarien und soll für den IT-Administrator eine plattformübergreifende konsistente Umgebung darstellen. Bei der Unterstützung bestimmter Funktionen gibt es jedoch geringfügige Unterschiede, die auf Einschränkungen der jeweiligen Plattform zurückzuführen sind.

# Erste Schritte

## Registrieren für Microsoft Connect

Das Intune App SDK ist derzeit über Microsoft Connect verfügbar und setzt eine Anmeldung voraus. Dazu registrieren Sie sich für ein [Microsoft Account](https://connect.microsoft.com/ConfigurationManagervnext/InvitationUse.aspx?ProgramID=8967&InvitationID=8967-YJYJ-8G6X) mit Ihrer Unternehmens-e-Mail.

Ihre Registrierung erhält den Status „Ausstehend“, bis das Intune-Team die Beantragung überprüft hat. Die normale Reaktionszeit beträgt 2 bis 3 Arbeitstage. Im Anschluss an die Genehmigung erhalten Sie eine E-Mail-Benachrichtigung mit einem oder mehreren Links, über die Sie das Intune App SDK für Ihre Plattformen und alle entsprechenden Leitfäden herunterladen können. Sie können diese Leitfäden auch auf der MSDN-Website aufrufen.

## Registrieren Ihrer Store-App bei Microsoft Intune

**Ihre aktivierte App soll nur intern im Unternehmen und nicht im Apple oder Google App Store verfügbar sein**: Sie brauchen Ihre App nicht zu registrieren. Derartige interne Apps lädt der IT-Administrator zur Bereitstellung direkt in die Microsoft Intune-Verwaltungskonsole. Intune erkennt, dass die App mit dem SDK erstellt wurde, und bietet dem IT-Administrator die Möglichkeit, eine MAM-Richtlinie zuzuweisen. Sie können den Abschnitt [Aktivieren von mobilen iOS- oder Android-Apps für die mobile Anwendungsverwaltung (MAM) mit dem SDK](#enableapp).

**Sie sind ein ISV und entwickeln eine App, die für Kunden im Apple oder Google App Store verfügbar sein soll**: Sie müssen die App zuerst bei Microsoft Intune registrieren und den Registrierungsbedingungen zustimmen. Bei dieser Gelegenheit können Sie auch den Deep-Link der App angeben. Anschließend kann ein IT-Administrator der App eine Intune-MAM-Richtlinie zuweisen. Solange die Registrierung nicht abgeschlossen und vom Microsoft Intune-Team bestätigt wurde, gibt es keine Möglichkeit, in der Verwaltungskonsole dem Deep-Link der App eine MAM-Richtlinie zuzuweisen. Microsoft bietet auch eine Microsoft Intune-Partnerwebsite an, auf der die App registriert wird. Dadurch weiß der Kunde, dass sie Microsoft Intune-MAM-Richtlinien unterstützt.

Um den Registrierungsvorgang zu beginnen **Überprüfen und sich** den [Vertrag zwischen Microsoft Intune-Partner](https://connect.microsoft.com/ConfigurationManagervnext/Survey/Survey.aspx?SurveyID=17806). Diese Vereinbarung enthält die Bedingungen, denen Ihr Unternehmen zustimmen muss, bevor es ein Microsoft Intune-App-Partner werden kann. Sie müssen sich anmelden, um dieses Dokument anzeigen zu können. Sie finden die Vereinbarung auf der Microsoft Connect-Website unter Intune App SDK auf der Registerkarte „Surveys“ oder hier. Sie werden auch nach dem Namen der App und Ihres Unternehmens gefragt und müssen den Deep-Link Ihrer Anwendung für den Google oder iTunes Store angeben.

![Microsoft Connect](/Image/Microsoft-Connect.png)

Wir verwenden die bei der Registrierung angegebene E-Mail-Adresse, um den Eingang des Registrierungsvorgangs zu bestätigen und diesen abzuschließen. Über diese Registrierungsadresse nehmen wir bei Fragen oder Problemen auch Kontakt mit Ihnen auf.

**Informationen zum Registrierungsvorgang**: Nachdem Sie das Formular gesendet haben, nimmt Microsoft über die bei der Registrierung angegebene E-Mail-Adresse Kontakt mit Ihnen auf, um den erfolgreichen Eingang zu bestätigen oder zusätzliche Informationen anzufordern, um die Registrierung abschließen zu können. Sie erhalten ebenso Nachricht, wenn Ihre App erfolgreich bei Microsoft Intune registriert wurde und auf der Microsoft Intune-Partnerwebsite empfohlen wird. Nachdem der Eingang der Informationen bestätigt wurde, wird der Deep-Link Ihrer App in das nächste monatliche Intune-Dienstupdate einbezogen. Wenn die Registrierung mit allen Informationen beispielsweise im Juli abgeschlossen ist, wird der Deep-Link der App Mitte August unterstützt. Wenn sich in Zukunft der Deep-Link Ihrer Store-App ändert, müssen Sie die App neu registrieren. Außerdem müssen Sie uns informieren, wenn Sie Ihre App mit einer neuen Intune App SDK-Version aktualisieren.

**Hinweis**: Alle Daten, die in obigem Formular oder über die E-Mail-Korrespondenz mit dem Intune-Team erfasst werden, unterliegen der [Microsoft-Datenschutzrichtlinie](https://www.microsoft.com/en-us/privacystatement/default.aspx).

## <a name="enableapp"></a> Aktivieren von mobilen iOS- oder Android-Apps für die mobile Anwendungsverwaltung (MAM) mit dem SDK

Zum Aktivieren Ihrer mobilen iOS-App benötigen Sie Folgendes:

1. **[App-SDK für iOS-Entwicklerhandbuch Intune](microsoft-intune-app-sdk-for-ios-developer-guide.md)**: Dieses Dokument führt Sie schrittweise durch die Aktivierung der mobilen iOS-app mit dem Intune-App-SDK. Sie finden dieses Dokument im Dokumentationsordner, der im heruntergeladenen Intune App SDK-Paket enthalten ist.
2. **Intune App SDK für iOS**: Das von Microsoft Intune heruntergeladene Intune App SDK-Paket enthält den signierten Ordner "Intune App SDK for iOS". Dieser Ordner enthält alle Inhalte des Intune App SDK für iOS.

Zum Aktivieren Ihrer mobilen Android-App mit Intune App SDK benötigen Sie Folgendes:

1. **[App-SDK für Android-Entwicklerhandbuch Intune](microsoft-intune-app-sdk-for-android-developer-guide.md)**: Dieses Dokument führt Sie schrittweise durch die Aktivierung der mobilen android-app mit Intune App-SDK. Sie finden dieses Dokument im Dokumentationsordner, der im heruntergeladenen Intune App SDK-Paket enthalten ist.
2. **Intune App SDK für Android**: Das von Microsoft Intune heruntergeladene Intune App SDK-Paket enthält den signierten Ordner "Intune App SDK for Android". Dieser Ordner enthält alle Inhalte des Intune App SDK für Android.

## Deaktivieren der Telemetrie für Ihre App

**App-SDK für iOS Intune**: das SDK protokolliert SDK Telemetriedaten auf verwendungsereignisse standardmäßig. Diese Daten werden an Microsoft Intune gesendet.

Wenn von Ihrer Anwendung keine SDK-Telemetriedaten an Microsoft Intune gesendet werden sollen, müssen Sie die SDK-Telemetrieübertragung **deaktivieren** , indem Sie unter `MAMTelemetryDisabled` die Eigenschaft `IntuneMAMSettings`.

**App-SDK für Android Intune**: SDK Telemetriedaten über das SDK nicht protokolliert.

## Testen Ihrer für die Verwaltung mobiler Anwendungen (MAM) aktivierten App mit Microsoft Intune

Nachdem Sie die notwendigen Schritte zur Integration des Intune App SDK in Ihre iOS- oder Android-App abgeschlossen haben, müssen Sie sicherstellen, dass alle App-Verwaltungsrichtlinien für den Endbenutzer und IT-Administrator aktiviert und funktionsfähig sind. Zum Testen Ihrer aktivierten App benötigen Sie Folgendes:

1. **Testen Ihre MAM-fähigen Anwendung mit Microsoft Intune**: Dieses Dokument führt Sie durch schrittweise MAM-fähigen IOS- oder android-apps mit Microsoft Intune zu testen. Sie finden dieses Dokument im Dokumentationsordner, der im heruntergeladenen Intune App SDK-Paket enthalten ist.
2. **Microsoft Intune Account**: um Ihre aktiviert MAM-apps mit Microsoft Intune zu testen, benötigen Sie ein Microsoft Intune-Konto. ISVs, die ihre iOS- oder Android-Store-Apps für MAM aktivieren, erhalten nach Abschluss ihrer Registrierung bei Microsoft Intune (wie unter Registrierung beschrieben) einen Promo-Code. Der Promo-Code bietet die Möglichkeit, sich für eine Microsoft Intune-Testversion (1 Jahr erweiterte Verwendung) anzumelden. Wenn Sie eine spartenspezifische App entwickeln, die nicht in den Store übertragen wird, sollten Sie über Ihre Organisation auf Microsoft Intune zugreifen können. Sie können auch für 1 Monat kostenlose Testversion mit anmelden [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0).



<!--HONumber=Mar16_HO1-->


