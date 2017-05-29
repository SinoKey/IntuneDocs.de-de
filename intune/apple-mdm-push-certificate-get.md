---
title: Abrufen eines Apple-MDM-Push-Zertifikats
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Lernen Sie die Schritte zum Abrufen eines Apple-MDM-Push-Zertifikats zum Verwalten von iOS-Geräten mit Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: e3ff50fa65eff897147081f2ec9ab366dbf50140
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---

# <a name="get-an-apple-mdm-push-certificate"></a>Abrufen eines Apple-MDM-Push-Zertifikats

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Intune ermöglicht die Verwaltung mobiler Geräte (mobile device management, MDM) wie iPads, iPhones und Mac-Computer und ermöglicht Benutzern den Zugriff auf Unternehmens-E-Mails und -Apps. Für die Verwaltung von iOS- und Mac-Geräten ist ein MDM-Push-Zertifikat erforderlich. Wenn Sie das Zertifikat in Intune hinzugefügt haben, können Ihre Benutzer die Unternehmensportal-App installieren, um ihre Geräte zu registrieren. Sie können auch die Verwaltung firmeneigener iOS-Geräte mit dem Geräteregistrierungsprogramm von Apple einrichten oder Geräte beispielsweise mithilfe von Apple Configurator registrieren. Weitere Informationen zu Registrierungsoptionen finden Sie unter [Auswählen der Registrierungsmethode für iOS-Geräte](enrollment-method-choose-ios.md).

## <a name="steps-to-get-your-certificate"></a>Erforderliche Schritte, um Ihr Zertifikat abzurufen
Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** > **Apple-Registrierung** > **Apple-MDM-Push-Zertifikat** aus, und führen Sie im Azure-Portal die folgenden nummerierten Schritte aus:

**Schritt 1: Laden Sie die erforderliche Anforderung zur Signierung eines Intune-Zertifikats herunter, um ein Apple-MDM-Push-Zertifikat erstellen zu können.**<br>
Wählen Sie **CSR herunterladen** aus, um die CSR-Datei herunterzuladen und lokal zu speichern. Die CSR-Datei wird verwendet, um ein Vertrauensstellungszertifikat vom Apple Push Certificates-Portal anzufordern.

**Schritt 2: Erstellen Sie ein Apple-MDM-Push-Zertifikat.**<br>
Wählen Sie **Eigenes MDM-Push-Zertifikat erstellen** aus, um zum Apple Push Certificates Portal zu gelangen. Melden Sie sich mit der Apple-ID Ihres Unternehmens an, um das Push-Zertifikat mithilfe der CSR-Datei zu erstellen. Nachdem Sie im Apple Push Certificates Portal **Hochladen** ausgewählt haben, erhalten Sie eine JSON-Datei. Verwenden Sie diese Datei für das Push-Zertifikat. Schließen Sie den Download ab, kehren Sie zum Apple Push Certificates-Portal für Zertifikate für Drittanbieterserver zurück, und wählen Sie anschließend **Herunterladen** aus. Laden Sie das Push-Zertifikat (PEM-Datei) herunter, und speichern Sie die Datei lokal.

> [!NOTE]
> Das Zertifikat ist mit der Apple-ID verknüpft, die verwendet wurde, um es zu erstellen. Als bewährte Methode verwenden Sie eine Unternehmens-Apple-ID für Verwaltungsaufgaben. Verwenden Sie niemals eine persönliche Apple-ID.

**Schritt 3: Geben Sie die zum Erstellen Ihres Apple-MDM-Push-Zertifikats verwendete Apple-ID ein.**

**Schritt 4: Navigieren Sie zu Ihrem hochzuladenden Apple-MDM-Push-Zertifikat.**<br>
Wechseln Sie zur Zertifikatsdatei (.pem), wählen Sie **Öffnen** aus, und wählen Sie dann **Hochladen**aus. Mit dem Push-Zertifikat kann Intune iOS-Geräte registrieren und verwalten, indem die Richtlinie auf registrierte mobile Geräte übertragen wird.

## <a name="renew-apple-mdm-push-certificate"></a>Erneuern eines Apple-MDM-Push-Zertifikats
Das Apple-MDM-Push-Zertifikat ist für ein Jahr gültig und muss jährlich erneuert werden, um die Geräteverwaltung von iOS und macOS beizubehalten. Wenn Ihr Zertifikat abläuft können registrierte Apple-Geräte nicht kontaktiert werden.

Das Zertifikat ist mit der Apple-ID verknüpft, die verwendet wurde, um es zu erstellen. Erneuern Sie das MDM-Push-Zertifikat mit derselben Apple-ID, mit der es erstellt wurde.

> [!NOTE]
> Das Zertifikat ist mit der Apple-ID verknüpft, die verwendet wurde, um es zu erstellen. Als bewährte Methode verwenden Sie eine Unternehmens-Apple-ID für Verwaltungsaufgaben. Verwenden Sie niemals eine persönliche Apple-ID.

1. Wählen Sie im [Azure Intune-Portal](https://portal.azure.com) auf dem Blatt „Intune“ die Option **Geräteregistrierung** > **Apple-Registrierung** und dann**Apple-MDM-Push-Zertifikat** aus.
2. Wählen Sie **CSR herunterladen** aus, um die CSR-Datei herunterzuladen und lokal zu speichern. Die CSR-Datei wird verwendet, um ein Vertrauensstellungszertifikat vom Apple Push Certificates-Portal anzufordern.
3. Suchen Sie das Zertifikat, das Sie erneuern möchten, und wählen Sie **Erneuern** aus.
4. Schreiben Sie auf dem Bildschirm **Push-Zertifikat erneuern** Notizen, die Ihnen zukünftig bei der Identifizierung des Zertifikats helfen. Wählen Sie **Datei auswählen** aus, um die neue CSR-Datei zu durchsuchen, die Sie heruntergeladen haben, und wählen Sie **Hochladen** aus.
5. Wählen Sie auf dem Bildschirm **Bestätigen** die Option **Herunterladen** aus, und speichern Sie die PEM-Datei lokal.
6. Wählen Sie im Azure Intune-Portal das Symbol zum Durchsuchen **Apple-MDM-Push-Zertifikat** aus, wählen Sie die PEM-Datei, die Sie von Apple heruntergeladen und anschließend **Hochladen** aus.

Ihr Apple MDM-Push-Zertifikat erscheint als **aktiv** und läuft in 365 Tagen ab.

