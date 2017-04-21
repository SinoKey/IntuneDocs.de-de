---
title: "Evaluieren der Verwaltung mobiler Geräte (MDM) in Microsoft Intune | Microsoft-Dokumentation"
description: Evaluieren von MDM in Ihrer kostenlosen Intune-Testversion.
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47806f69-303d-41d9-9b0e-9b9445ea24ac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 9a988945c499c3145208b86d6832d02c28136ece
ms.lasthandoff: 04/14/2017


---

# <a name="evaluate-mobile-device-management-in-microsoft-intune"></a>Evaluieren der Verwaltung mobiler Geräte (MDM) in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

In diesem Evaluierungshandbuch wird die Funktionsweise der Verwaltung mobiler Geräte in Intune beschrieben. Sie lernen Folgendes:
- Registrieren eines Geräts für die Verwaltung mit Intune
- Erstellen von Gruppen zum Organisieren von Benutzern und Geräten
- Erstellen und Bereitstellen einiger Geräteverwaltungsrichtlinien für Ihre Gruppen
- Veröffentlichen einer App, die Benutzer mit registrierten Geräten auf ihrem Gerät installieren können
<!--- - Monitor the device? View a report of compliant devices?--->
<!--- - Remove the device from management--->

## <a name="assumptions"></a>Annahmen
In diesem Handbuch wird davon ausgegangen, dass Sie die Testversion nur zu Evaluierungszwecken verwenden und beim Abschluss des Abonnements mit einer sauberen Umgebung starten möchten.

Um Ihnen den Einstieg in die Testversion zu erleichtern, richten wir eine sehr einfache Umgebung ein, in der nur Intune verwendet wird. Außerdem wird davon ausgegangen, dass Intune Ihre Autorität für die Verwaltung mobiler Geräte ist. Allerdings finden Sie im gesamten Handbuch Verweise auf weitergehende technische Inhalte, wenn Sie ein Thema genauer untersuchen möchten.

In der Testversion stehen alle Funktionen zur Verfügung, die Sie auch in einer Abonnementversion ausführen können. Der einzige Unterschied besteht darin, dass die Testversion auf 100 Benutzerkonten beschränkt ist.

## <a name="whats-not-covered"></a>Was nicht behandelt wird
|Wenn Sie folgende Themen interessieren ... |... finden Sie hier weitere Informationen |
|------------------------|----------|
|Verwaltung mobiler Geräte (MDM) in einer Produktionsumgebung | [Erste Schritte](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune) |
|MDM mit Intune und System Center Configuration Manager | [Hybride Verwaltung mobiler Geräte](https://docs.microsoft.com/sccm/mdm/understand/hybrid-mobile-device-management) |

Da die oben genannten Handbücher Ihnen helfen, Intune in Produktionsumgebungen einzurichten, sind sie länger und enthalten viel mehr Entscheidungspunkte, die Sie durcharbeiten müssen, als das Evaluierungshandbuch.

Um sich schnell mit Intune vertraut zu machen, empfehlen wir, mit dem Evaluierungshandbuch zu beginnen und dann mit den anderen Handbüchern fortzufahren.

## <a name="prerequisites-for-this-evaluation"></a>Voraussetzungen für diese Evaluierung
- Internet Explorer 10 oder höher
- Ein Gerät, mit dem Sie testen, wie sich Intune-Benutzer mithilfe des Unternehmensportals registrieren und ihre Geräte verwalten. In diesem Handbuch wird ein iPad und ein Android-Telefon verwendet.
- Um das iPad oder ein anderes iOS-Gerät zu verwalten, benötigen Sie ein [Apple Push Notification Service-Zertifikat](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).
- Ein [Intune-Testabonnement](sign-up-for-30-day-trial-microsoft-intune.md)

## <a name="set-your-mdm-authority"></a>Festlegen der MDM-Autorität
Als ersten Schritt zum Verwalten mobiler Geräte mit Intune müssen Sie Ihre **Autorität für die Verwaltung mobiler Geräte (MDM-Autorität)** festlegen.

Wenn Sie Intune als eigenständige Anwendung nutzen, wovon in dieser Testversion ausgegangen wird, oder wenn Sie Intune als Teil eines EMS-Abonnements (Enterprise Mobility + Security) verwenden, müssen Sie Intune als Autorität für die Verwaltung mobiler Geräte festlegen. Legen Sie Intune also als den Dienst fest, der zum Verwalten mobiler Geräte in Ihrer Organisation verwendet wird.

Kunden, die Intune mit System Center Configuration Manager zum Verwalten mobiler Geräte verwenden möchten, müssen entscheiden, ob Intune oder Configuration Manager als MDM-Autorität verwendet werden soll. Das ist eine wichtige Entscheidung in einer Produktionsumgebung, da sich die Einstellung, nachdem sie einmal festgelegt wurde, aktuell nur sehr schwer ändern lässt. Dies geht aber über den Rahmen dieses Handbuchs hinaus. Weitere Informationen zu den Auswirkungen der Entscheidung, Intune oder Configuration Manager als MDM-Autorität festzulegen, finden Sie unter [Auswahl zwischen eigenständiger Intune MDM und Hybrid-MDM](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management).

Für diese Testversion wird Intune als MDM-Autorität festgelegt. Dies wirkt sich nicht auf Ihre Produktionsumgebung aus, solange Sie die Testsoftware nicht für Ihre Produktionsumgebung verwenden.

1. Wählen Sie in der [Intune-Verwaltungskonsole](https://manage.microsoft.com/) **Admin** &gt; **Verwaltung mobiler Geräte** aus.
2. Wählen Sie in der Liste **Aufgaben** die Option **MDM-Autorität festlegen** aus. Das Dialogfeld **MDM-Autorität festlegen** wird geöffnet. <!---screen shot--->
3. Intune erfordert eine Bestätigung, dass es als MDM-Autorität verwendet werden soll. Aktivieren Sie das Kontrollkästchen, und wählen Sie dann **Ja** aus, um Intune zum Verwalten mobiler Geräte zu verwenden.

## <a name="enroll-your-test-devices-into-intune"></a>Registrieren der Testgeräte bei Intune

In diesem Handbuch werden ein Android-Telefon und ein Apple iPad registriert. Am Ende dieses Abschnitts werden jedoch auch [Links zu weiteren Informationen zur Geräteregistrierung in Intune](#Learn-more-about-device-enrollment) bereitgestellt.
### <a name="android"></a>Android
Installieren Sie die **Intune-Unternehmensportal**-App der Microsoft Corporation, die in [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612) verfügbar ist, und melden Sie sich mit den [Benutzeranmeldeinformationen](sign-up-for-30-day-trial-microsoft-intune.md#add-users) für Intune an, die Sie bei der Registrierung für die kostenlose Textversion erstellt haben.

### <a name="ios"></a>iOS
Bevor Benutzer ihre iOS-Geräte registrieren können, müssen Sie Intune für die Verwaltung dieser Geräte einrichten.

1. **Abrufen einer Zertifikatsignierungsanforderung**<br/>
Melden Sie sich mit Ihrem Administratorkonto bei Intune an, und navigieren Sie zu **Verwaltung** > **Verwaltung mobiler Geräte** > **iOS und Mac OS X** > **APNs-Zertifikat hochladen**, und wählen Sie **APNs-Zertifikatanforderung herunterladen** aus. Speichern Sie die Zertifikatsignierungsanforderung (CSR-Datei) lokal. Die CSR-Datei wird verwendet, um ein Vertrauensstellungszertifikat vom Apple Push Certificates-Portal anzufordern. <!--- screen shot--->
2.    **Abrufen eines Apple Push Notification Service-Zertifikats**<BR/>
Wechseln Sie zum [Apple Push Certificates-Portal](https://idmsa.apple.com/IDMSWebAuth/login?appIdKey=3fbfc9ad8dfedeb78be1d37f6458e72adc3160d1ad5b323a9e5c5eb2f8e7e3e2&rv=2), und melden Sie sich mit Ihrer Unternehmens-Apple-ID an, um das APNs-Zertifikat mithilfe der CSR-Datei zu erstellen. Nachdem Sie im Portal für Apple-Push-Zertifikate **Hochladen** ausgewählt haben, erhalten Sie eine JSON-Datei, die für APNs nicht verwendet werden kann. Schließen Sie den Download ab, kehren Sie zum Apple Push Certificates-Portal für Zertifikate für Drittanbieterserver zurück, und wählen Sie anschließend **Herunterladen** aus.<br/>
Laden Sie das APNs-Zertifikat (.pem) herunter, und speichern Sie die Datei lokal. Diese Apple-ID muss später verwendet werden, um das APNs-Zertifikat zu erneuern.
3.    **Hinzufügen des APNs-Zertifikats zu Intune**<BR/>
Navigieren Sie in der Microsoft Intune-Verwaltungskonsole zu **Verwaltung** > **Verwaltung mobiler Geräte** > **iOS und Mac OS X** > **APNs-Zertifikat hochladen**, und wählen Sie anschließend **APNs-Zertifikat hochladen** aus. Wechseln Sie zur Zertifikatdatei (.pem), wählen Sie **Öffnen** aus, und geben Sie anschließend Ihre Apple-ID ein. Mit dem APNs-Zertifikat. Intune kann iOS-Geräte registrieren und verwalten, indem die Richtlinie per Push auf registrierte mobile Geräte übertragen wird.
4.    **Benutzern erklären, wie sie ihre Geräte registrieren, um auf Unternehmensressourcen zugreifen zu können**<br/>
Registrierungsanleitungen für Endbenutzer finden Sie unter [Registrieren Ihres iOS-Geräts bei Intune](https://docs.microsoft.com/Intune/enduser/enroll-your-device-in-intune-ios) oder unter [Registrieren Ihres Mac OS X-Geräts bei Intune](https://docs.microsoft.com/Intune/enduser/enroll-your-device-in-intune-mac-os-x). Im Laufe des Registrierungsprozesses werden Benutzer darüber informiert, was sie erwarten können und was IT-Administratoren auf ihren Geräten sehen können und was nicht.


### <a name="learn-more-about-device-enrollment"></a>Weitere Informationen zur Geräteregistrierung

Intune unterstützt folgende Geräteplattformen:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Die Anforderungen zum Aktivieren der Geräteverwaltung hängen von den Plattformen ab, die Sie verwalten möchten.
- Mobile **Android**-Geräte ermöglichen Benutzern die [Registrierung über die Unternehmensportal-App](/intune/deploy-use/set-up-android-management-with-microsoft-intune), die in Google Play zur Verfügung steht. Es ist keine weitere Konfiguration in Intune erforderlich.
- [Setupanforderungen für **iOS und Mac OS X**](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)
- [Setupanforderungen für **Windows Phone**](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune)

<!--- ## Verify enrollment--->
<!--- START HERE

### iOS and Mac OS X
Install the **Microsoft Intune Company Portal** app from Microsoft Corporation available in the App Store and sign in with Intune user credentials added above. View **Enrolled devices** to add your device.



### Windows Phone 8.1
Users install the **Company Portal** app from Microsoft Corporation, available in the Windows Phone store, and sign in with the Intune user credentials added above.  View **Enrolled devices** to add your device.

## Install the previously deployed app
Open the Company Portal on the mobile device, choose **Apps**, and then install **Microsoft Skype**.--->



## <a name="next-steps"></a>Nächste Schritte
[Erstellen von Gruppen zum Organisieren von Benutzern und Geräten](get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)

