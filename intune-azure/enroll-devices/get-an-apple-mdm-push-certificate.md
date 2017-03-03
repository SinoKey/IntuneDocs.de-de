---
title: Abrufen eines Apple-MDM-Push-Zertifikats | Intune in Azure (Vorschau) | Microsoft Docs
description: "Intune in Azure (Vorschau): Lernen Sie die Schritte zum Abrufen eines Apple-MDM-Push-Zertifikats zum Verwalten von iOS-Geräten mit Intune."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: a6ac1074055892f5ec42fb4057e47e9349fb5a33
ms.lasthandoff: 02/15/2017


---

# <a name="get-an-apple-mdm-push-certificate"></a>Abrufen eines Apple-MDM-Push-Zertifikats 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune ermöglicht die Verwaltung mobiler Geräte (mobile device management, MDM) wie iPads, iPhones und Mac OS X-Geräte und ermöglicht Benutzern den Zugriff auf Unternehmens-E-Mails und -Apps. Zum Verwalten von iOS- und Mac-Geräten benötigen Sie ein APNS-Zertifikat (Apple Push Notification Service). Sobald Sie das Zertifikat in Intune hinzufügen, können Ihre Benutzer die Unternehmensportal-App zur Registrierung ihrer Geräte installieren, oder Sie können die Verwaltung von firmeneigenen iOS-Geräten einrichten.

**So rufen Sie das MDM-Push-Zertifikat ab**<br>
Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** > **Apple-MDM-Push-Zertifikat** aus, und befolgen Sie die nachstehend dargestellten nummerierten Schritte im Azure-Portal.

**Schritt 1: Laden Sie die erforderliche Anforderung zur Signierung eines Intune-Zertifikats herunter, um ein Apple-MDM-Push-Zertifikat erstellen zu können.**<br>
Wählen Sie **CSR herunterladen** aus, um die CSR-Datei herunterzuladen und lokal zu speichern. Die CSR-Datei wird verwendet, um ein Vertrauensstellungszertifikat vom Apple Push Certificates-Portal anzufordern.

**Schritt 2: Erstellen Sie ein Apple-MDM-Push-Zertifikat.**<br>
Wählen Sie **Eigenes MDM-Push-Zertifikat erstellen** aus, um zum Apple Push Certificates Portal zu gelangen. Melden Sie sich mit der Apple-ID Ihres Unternehmens an, um das Push-Zertifikat mithilfe der CSR-Datei zu erstellen. Nachdem Sie im Apple Push Certificates Portal **Hochladen** ausgewählt haben, erhalten Sie eine JSON-Datei. Verwenden Sie diese Datei für das Push-Zertifikat. Schließen Sie den Download ab, kehren Sie zum Apple Push Certificates-Portal für Zertifikate für Drittanbieterserver zurück, und wählen Sie anschließend **Herunterladen** aus. Laden Sie das Push-Zertifikat (PEM-Datei) herunter, und speichern Sie die Datei lokal.
Hinweis

**Schritt 3: Geben Sie die zum Erstellen Ihres Apple-MDM-Push-Zertifikats verwendete Apple-ID ein.**

**Schritt 4: Navigieren Sie zu Ihrem hochzuladenden Apple-MDM-Push-Zertifikat.**<br>
Wechseln Sie zur Zertifikatsdatei (.pem), wählen Sie **Öffnen** aus, und wählen Sie dann **Hochladen**aus. Mit dem Push-Zertifikat kann Intune iOS-Geräte registrieren und verwalten, indem die Richtlinie auf registrierte mobile Geräte übertragen wird.

