---
title: Zugriff auf Unternehmens-E-Mail mithilfe von E-Mail-Profilen | Microsoft Intune
description: "Mithilfe der Einstellungen von E-Mail-Profilen können die Einstellungen für den E-Mail-Zugriff für bestimmte E-Mail-Clients auf mobilen Geräten konfiguriert werden."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 07/021/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 10f0cd61-e514-4e44-b13e-aeb85a8e53ae
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb0aeac2f94dfde50d9398b09c6b21c7ae40624
ms.openlocfilehash: cddc1a68b14520774555416dcd496a06a0f89385


---

# Konfigurieren des Zugriffs auf Unternehmens-E-Mail mithilfe von E-Mail-Profilen in Microsoft Intune
Viele mobile Plattformen enthalten einen *systemeigenen* E-Mail-Client, der als Teil des Betriebssystems bereitgestellt wird.  Einige dieser Clients können mithilfe von E-Mail-Profilen konfiguriert werden, die in diesem Thema beschrieben werden.

Wenn ein zusätzlicher Schutz vor Datenverlust erforderlich ist, wählen Sie [Bedingter Zugriff](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) aus, um den Zugriff auf das Postfach des Benutzers für alle E-Mail-Clients zu kontrollieren, einschließlich systemeigener E-Mail-Clients.

Mithilfe der Einstellungen von E-Mail-Profilen können die Einstellungen für den E-Mail-Zugriff für bestimmte E-Mail-Clients auf mobilen Geräten konfiguriert werden. Die meisten mobilen Plattformen enthalten einen *systemeigenen* E-Mail-Client, der als Teil des Betriebssystems bereitgestellt wird.  Auf unterstützten Plattformen können die E-Mail-Clients mithilfe von Microsoft Intune konfiguriert werden, damit Benutzer ohne vorherige Einrichtung über private Geräte auf ihre E-Mails im Unternehmen zugreifen können.  

IT-Administratoren oder Benutzer können auch alternative E-Mail-Clients wie Microsoft Outlook für Android oder iOS installieren.  Diese E-Mail-Clients unterstützen möglicherweise keine E-Mail-Profile und können nicht mithilfe der E-Mail-Profile von Microsoft Intune konfiguriert werden.  

Sie können E-Mail-Profile verwenden, um den systemeigenen E-Mail-Client auf den folgenden Gerätetypen zu konfigurieren:
-   Windows Phone 8 und höher
-   Windows 10 Desktop, Windows 10 Mobile) und höher
-   iOS 7.1 und höher
-   Samsung KNOX Standard (4.0 und höher)


Sie können nicht nur ein E-Mail-Konto auf dem Gerät konfigurieren, sondern auch Synchronisierungseinstellungen (beispielsweise wie viele E-Mails synchronisiert werden sollen und abhängig vom Gerätetyp die zu synchronisierenden Inhaltstypen).
>[!NOTE]
>
>Wenn der Benutzer ein E-Mail-Profil installiert hat, bevor ein Profil durch Intune bereitgestellt wurde, hat die Bereitstellung des Intune-E-Mail-Profils je nach Geräteplattform folgende Auswirkungen:

>-**iOS**: Intune erkennt basierend auf dem Hostnamen und der E-Mail-Adresse ein vorhandenes doppeltes E-Mail-Profil. Das vom Benutzer erstellte doppelte E-Mail-Profil blockiert die Bereitstellung eines Profils, das vom Intune-Administrator erstellt wurde. Das ist ein häufig auftretendes Problem, da iOS-Benutzer in der Regel ein E-Mail-Profil erstellen und anschließend die Registrierung vornehmen. Das Unternehmensportal informiert den Benutzer darüber, dass es aufgrund seines manuell konfigurierten E-Mail-Profils nicht kompatibel ist, und fordert ihn dazu auf, dieses Profil zu entfernen. Der Benutzer sollte sein E-Mail-Profil entfernen, damit das Intune-Profil bereitgestellt werden kann. Weisen Sie Ihre Benutzer an, sich vor der Installation eines E-Mail-Profils zu registrieren und die Bereitstellung des Profils durch Intune zuzulassen, um das Problem zu vermeiden.

>-**Windows**: Intune erkennt basierend auf dem Hostnamen und der E-Mail-Adresse ein vorhandenes doppeltes E-Mail-Profil. Intune überschreibt das vorhandene, vom Benutzer erstellte E-Mail-Profil.

>-**Samsung KNOX**: Intune identifiziert basierend auf der E-Mail-Adresse ein doppeltes E-Mail-Konto und überschreibt es mit dem Intune-Profil. Wenn der Benutzer dieses Konto konfiguriert, wird es erneut durch das Intune-Profil überschrieben. Dies kann für den Benutzer, dessen Kontokonfiguration überschrieben wird, verwirrend sein.

>Da Samsung KNOX zum Identifizieren des Profils keinen Hostnamen verwendet, wird davon abgeraten, mehrere E-Mail-Profile für die Bereitstellung unter derselben E-Mail-Adresse auf unterschiedlichen Hosts zu erstellen, da sie sich gegenseitig überschreiben.
    

## Schützen von E-Mail-Profilen
E-Mail-Profile können mit einer von zwei Methoden geschützt werden:

### Zertifikate
Beim Erstellen des E-Mail-Profils wählen Sie ein Zertifikatprofil aus, das Sie zuvor in Intune erstellt haben. Dieses wird als Identitätszertifikat bezeichnet und dient zur Authentifizierung anhand eines vertrauenswürdigen Zertifikatprofils (oder eines Stammzertifikats), mit dem überprüft wird, ob das Gerät des Benutzers eine Verbindung herstellen darf. Das vertrauenswürdige Zertifikat wird auf dem Computer bereitgestellt, der die E-Mail-Verbindung authentifiziert. In der Regel ist dies der systemeigene Mailserver.

Weitere Informationen zum Erstellen und Verwenden von Zertifikatprofilen in Intune finden Sie unter [Sicherer Zugriff auf Ressourcen mit Zertifikatprofilen](secure-resource-access-with-certificate-profiles.md).

### Benutzername und Kennwort
Der Benutzer authentifiziert sich beim systemeigenen Mailserver durch Angabe seines Benutzernamens und Kennworts.

Das Kennwort ist nicht im E-Mail-Profil enthalten, sodass der Benutzer dieses beim Herstellen einer Verbindung zum E-Mail-System bereitstellen muss.

### Erstellen eines E-Mail-Profils

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) auf **Richtlinie** &gt; **Richtlinie hinzufügen**.

2.  Konfigurieren Sie einen der folgenden Richtlinientypen:

    -   **E-Mail-Profil für Samsung KNOX Standard (4.0 oder höher)**

    -   **E-Mail-Profil (iOS 7.1 und höher)**

    -   **E-Mail-Profil (Windows Phone 8 und höher)**

    -   **E-Mail-Profil (Windows 10 Desktop und Windows 10 Mobile oder höher)**

    Sie können nur benutzerdefinierte E-Mail-Profilrichtlinien erstellen. Empfohlene Einstellungen sind nicht verfügbar.

3.  Verwenden Sie die folgende Tabelle, um Einstellungen von E-Mail-Profilen zu konfigurieren:
    |Name der Einstellung|Weitere Informationen|
    |----------------|-----------------------------------------------------------------------------|
    |**Name**|Eindeutiger Name für das E-Mail-Profil.|
    |**Beschreibung**|Eine Beschreibung, die Sie beim Identifizieren dieses Profils unterstützt.|
    |**Host**|Der Hostname des Unternehmensservers, der den systemeigenen E-Mail-Dienst hostet.|
    |**Account name**|Der Anzeigename für das E-Mail-Konto, wie er den Benutzern auf ihren Geräten angezeigt wird.|
    |**Benutzername**|Vorgehensweise beim Abrufen des Benutzernamens für das E-Mail-Konto. Wählen Sie **Benutzername** für einen lokalen Exchange-Server oder **Benutzerprinzipalname** für Office 365 aus.|
    |**E-Mail-Adresse**|Vorgehensweise beim Generieren der E-Mail-Adresse für den Benutzer auf den einzelnen Geräten. Wählen Sie **Primäre SMTP-Adresse** aus, um die primäre SMTP-Adresse zum Anmelden bei Exchange zu verwenden. Verwenden Sie **Benutzerprinzipalname**, um den vollständigen Benutzerprinzipalnamen als E-Mail-Adresse zu verwenden.|
    |**Authentifizierungsmethode** (Samsung KNOX und iOS)|Wählen Sie entweder **Benutzername und Kennwort** oder **Zertifikat** als Authentifizierungsmethode aus, die vom E-Mail-Profil verwendet werden soll.|
    |**Wählen Sie ein Clientzertifikat für die Clientauthentifizierung (Identitätszertifikat) aus** (Samsung KNOX und iOS)|Wählen Sie das zuvor erstellte SCEP-Clientzertifikat aus, das zur Authentifizierung der Exchange-Verbindung verwendet werden soll. Weitere Informationen zum Verwenden von Zertifikatprofilen in Intune finden Sie unter [Sicherer Zugriff auf Ressourcen mit Zertifikatprofilen](secure-resource-access-with-certificate-profiles.md).<br /><br />Diese Option wird nur für die Authentifizierungsmethode **Zertifikate** angezeigt.|
    |**S/MIME verwenden** (Samsung KNOX und iOS)|Ausgehende E-Mails werden mithilfe von S/MIME-Verschlüsselung gesendet.|
    |**Signaturzertifikat** (Samsung KNOX und iOS)|Wählen Sie das Signaturzertifikat aus, das zum Signieren von ausgehenden E-Mails verwendet werden soll.<br /><br />Diese Option wird nur angezeigt, wenn Sie **S/MIME verwenden** auswählen.|
    |**Anzahl der Tage für die E-Mail-Synchronisierung**|Die Anzahl der Tage von E-Mails, die synchronisiert werden sollen, oder wählen Sie **Unbegrenzt** aus, um alle verfügbaren E-Mail-Nachrichten zu synchronisieren.|
    |**Synchronisierungszeitplan** (Samsung KNOX, Windows Phone 8 und höher, Windows 10)|Wählen Sie den Zeitplan aus, nach dem Geräte mit Daten vom Exchange-Server synchronisiert werden. Sie können auch **Wenn Nachrichten eintreffen** auswählen, wobei die Daten sofort bei Eintreffen synchronisiert werden, oder **Manuell**, wobei der Benutzer des Geräts die Synchronisierung initiieren muss.|
    |**SSL verwenden**|Verwendet SSL-Kommunikation (Secure Sockets Layer) beim Senden und Empfangen von E-Mails sowie bei der Kommunikation mit dem Exchange-Server.<br /><br />Für Geräte mit Samsung KNOX 4.0 oder höher müssen Sie Ihr Exchange Server-SSL-Zertifikat exportieren und es als ein Android Trusted Certificate Profile in Intune bereitstellen. Intune unterstützt den Zugriff auf dieses Zertifikat nicht, wenn es auf andere Weise auf dem Exchange Server installiert wurde.|
    |**Zu synchronisierender Inhaltstyp**|Wählen Sie die Inhaltstypen aus, die auf Geräten synchronisiert werden sollen.|
    |**Senden von E-Mails über Anwendungen von Drittanbietern zulassen** (nur iOS)|Benutzern die Auswahl dieses Profils als das Standardkonto für das Versenden von E-Mails erlauben und Anwendungen von Drittanbietern das Öffnen von E-Mails in der nativen E-Mal-App erlauben, um beispielsweise Dateien an E-Mails anzuhängen.|

    > [!IMPORTANT]
    > Wenn Sie ein E-Mail-Profil bereitgestellt haben und dann die Werte für **Host** oder **E-Mail-Adresse** ändern möchten, müssen Sie das vorhandene E-Mail-Profil löschen und ein neues mit den erforderlichen Werten erstellen.

4.  Klicken Sie danach auf **Richtlinie speichern**.

Die neue Richtlinie wird im Knoten **Konfigurationsrichtlinien** des Arbeitsbereichs **Richtlinie** angezeigt.

## Bereitstellen der Richtlinie

1.  Wählen Sie im Arbeitsbereich **Richtlinie** die Richtlinie aus, die Sie bereitstellen möchten, und klicken Sie dann auf **Bereitstellung verwalten**.

2.  Führen Sie im Dialogfeld **Bereitstellung verwalten** folgende Schritte aus:

    -   **Zum Bereitstellen der Richtlinie**: Wählen Sie mindestens eine Gruppe aus, für die Sie die Richtlinie bereitstellen möchten, und klicken Sie auf **Hinzufügen** &gt; **OK**.

    -   **Wenn Sie das Dialogfeld schließen möchten, ohne die Richtlinie bereitzustellen:** Klicken Sie auf **Abbrechen**.

Eine Statuszusammenfassung und Warnungen auf der Seite **Übersicht** des Arbeitsbereichs **Richtlinie** identifiziert Probleme mit der Richtlinie, die Ihre Aufmerksamkeit erfordern. Darüber hinaus wird eine Statusübersicht im Arbeitsbereich „Dashboard“ angezeigt.

> [!NOTE]
> Wenn Sie ein E-Mail-Profil von einem Gerät entfernen, bearbeiten Sie die Bereitstellung, und entfernen Sie alle Gruppen, in denen das Gerät Mitglied ist.



<!--HONumber=Aug16_HO1-->


