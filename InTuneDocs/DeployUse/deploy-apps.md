---
# required metadata

title: Bereitstellen von Apps | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ad5ea85c-aa2e-4110-a184-172cd0b8f270

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Bereitstellen von Apps mit Microsoft Intune

In diesem Thema werden einige Grundlagen erläutert, die Sie kennen müssen, bevor Sie mit dem Bereitstellen von Apps mit Microsoft Intune beginnen.

## Der Intune-Softwareherausgeber
Der **Microsoft Intune-Softwareherausgeber** wird gestartet, wenn Sie in der Microsoft Intune-Administratorkonsole Apps hinzufügen oder ändern. Im Herausgeber wählen Sie einen Software-Installationsprogrammtyp aus und konfigurieren ihn, der zum Hochladen von Apps (Programme für Computer oder Apps für mobile Geräte) für die Speicherung im Intune-Cloudspeicher oder zum Bereitstellen eines Links zu einem Onlineshop bzw.einer Webanwendung dient.

### Anforderungen
Bevor Sie mit der Verwendung des Microsoft Intune -Softwareherausgebers beginnen, müssen Sie die Vollversion von [Microsoft .NET Framework 4.0](https://www.microsoft.com/download/details.aspx?id=17851) installieren. Nach der Installation müssen Sie möglicherweise den Computer neu starten, damit der Softwareherausgeber ordnungsgemäß geöffnet wird.

## Cloudspeicherplatz
Alle Apps, die Sie mithilfe des Software-Installationsprogrammtyps bereitstellen, müssen verpackt und in den Microsoft Intune-Cloudspeicher hochgeladen werden. Ein Testabonnement von Intune enthält 2 GB cloudbasierten Speicher, der zum Speichern von verwalteten Apps und Updates verwendet wird. Ein kostenpflichtiges Abonnement beinhaltet 20 GB und bietet die Option zum Erwerb von weiterem Speicher.

Sie können sehen, wie viel Speicherplatz Sie verwenden, und weiteren Speicher im Knoten **Speichernutzung** des **Administrator**-Arbeitsbereichs kaufen.

Diese Regeln gelten für den Kauf von zusätzlichem Cloudspeicherplatz für Intune:

-   Sie benötigen ein aktives kostenpflichtiges Abonnement, um zusätzlichen Speicherplatz zu kaufen.

-   Nur Rechnungsadministratoren oder globale Administratoren für Ihren Microsoft Online Service können zusätzlichen Speicher über das Intune-Kontenportal erwerben. Um diese Administratoren hinzuzufügen, zu löschen oder zu verwalten, müssen Sie ein globaler Administrator und beim Intune-Kontenportal angemeldet sein.

-   Volumenlizenzkunden, die Intune oder das Microsoft Intune-Add-On über ein Enterprise Agreement gekauft haben, erhalten Preisinformationen und zusätzlichen Speicherplatz beim zuständigen Microsoft-Kundenbetreuer oder Microsoft-Partner.

#### Anforderungen für Cloudspeicherplatz

-   Alle einer App zugeordneten Dateien müssen sich am gleichen Ort befinden und von Intune aus erreichbar sein.

-   Die maximale Dateigröße für hochgeladene Dateien beträgt 2 GB.

-   Zum Hochladen von Dateien benötigen Sie mindestens eine Verbindungsgeschwindigkeit von 768 KBit/s.

## App-Bereitstellungsaktionen
Wenn Sie Apps bereitstellen, können Sie eine der folgenden Bereitstellungsaktionen auswählen:

-   **Erforderliche Installation** – Die App wird auf dem Gerät installiert, ohne dass ein Benutzereingriff erforderlich ist.

    > [!TIP]
    > Bei iOS-Geräten, die nicht betreut werden, und bei allen Android-Geräten muss der Benutzer das App-Angebot vor der Installation akzeptieren.
    >
    > Sie können keine neuen App-Bereitstellungen für iOS-Geräte mehr erstellen, auf denen ein älteres Betriebssystem als iOS 7.1 ausgeführt wird. Alle vorhandenen App-Bereitstellungen auf Geräten, auf denen ein älteres Betriebssystem als iOS 7.1 ausgeführt wird, funktionieren weiterhin und werden auch weiterhin von Intune verwaltet.

-   **Verfügbare Installation** – Die App wird im Unternehmensportal angezeigt, und Endbenutzer können sie bei Bedarf installieren.

-   **Deinstallieren** : Die App wird vom Gerät deinstalliert.

-   **Nicht verfügbar** : Die App wird nicht im Unternehmensportal angezeigt und wird auf keinem Gerät installiert.

#### Verfügbare Bereitstellungsaktionen für die verschiedenen Installationsprogrammtypen

|Typ des Installationsprogramms|Erforderliche Installation|Verfügbare Installation|Deinstallieren|Nicht verfügbar|
|------------------|--------------------|---------------------|-------------|------------------|
|Windows-App-Paket (für eine Benutzergruppe bereitgestellt)|Ja|Ja|Ja|Ja|
|Windows-App-Paket (auf einer Gerätegruppe bereitgestellt)|Ja|Nein|Ja|Ja|
|App-Paket für mobile Geräte (für eine Benutzergruppe bereitgestellt)|Ja|Ja|Ja|Ja|
|App-Paket für mobile Geräte (auf einer Gerätegruppe bereitgestellt)|Ja|Nein|Ja|Ja|
|Windows Installer (für eine Benutzergruppe bereitgestellt)|Nein|Ja|Nein|Ja|
|Windows Installer (auf einer Gerätegruppe bereitgestellt)|Ja|Nein|Ja|Ja|
|Externer Link (für eine Benutzergruppe bereitgestellt)|Nein|Ja|Nein|Ja|
|Externer Link (auf einer Gerätegruppe bereitgestellt)|Nein|Nein|Nein|Nein|
|Verwaltete iOS-App aus dem App Store (für eine Benutzergruppe bereitgestellt)|Ja|Ja|Ja|Ja|
|Verwaltete iOS-App aus dem App Store (auf einer Gerätegruppe bereitgestellt)|Ja|Nein|Ja|Ja|
> [!TIP]
> Wenn Sie beim Bereitstellen von Apps sowohl Benutzer- als auch Gerätegruppen auswählen, können Sie die App nur als **Verfügbare Installation** bereitstellen..

## Bereitstellungskonflikte
Wenn zwei Bereitstellungen mit der gleichen Bereitstellungsaktion von einem Gerät empfangen werden, gelten die folgenden Regeln:

-   Bereitstellungen auf einer Gerätegruppe haben Vorrang vor Bereitstellung für eine Benutzergruppe. Wenn jedoch eine App für eine Benutzergruppe mit der Bereitstellungsaktion **Verfügbar** bereitgestellt wird und dieselbe App auf einer Gerätegruppe mit der Bereitstellungsaktion **Nicht verfügbar**bereitgestellt wird, wird die App im Unternehmensportal Benutzern zur Installation zur Verfügung gestellt.

-   Die Absicht des IT-Administrators hat Vorrang vor dem Wunsch des Benutzers.

-   Eine Installationsaktion hat Vorrang vor einer Deinstallationsaktion.

-   Wenn eine erforderliche Installation und eine verfügbare Installation von einem Gerät empfangen werden, werden die Aktionen zusammengefasst (die App ist erforderlich und verfügbar).


## Nächste Schritte

Erfahren Sie mehr zum [Bereitstellen von Apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md).

<!--HONumber=May16_HO1-->


