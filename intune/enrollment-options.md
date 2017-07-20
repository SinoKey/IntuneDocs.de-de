---
title: "Registrierungsoptionen für Intune"
description: 
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cf4ad6d4-423f-4826-ab8d-6eb7a7cfb559
ms.openlocfilehash: dcc97e5bcffb35752b65e8ce275d38b9578da6fa
ms.sourcegitcommit: bee30f4c9e04129d70305fcafc4152c6e062a8b0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2017
---
# <a name="enrollment-options-for-intune"></a>Registrierungsoptionen für Intune

Als Intune-Administrator können Sie die Geräteregistrierung konfigurieren, um Benutzer zu unterstützen und Intune-Funktionen zu aktivieren.  Intune umfasst folgende Registrierungsoptionen:

## <a name="terms-and-conditions"></a>Nutzungsbedingungen

Sie können festlegen, dass für Benutzer die Annahme der Geschäftsbedingungen Ihres Unternehmens erforderlich ist, bevor diese das Unternehmensportal verwenden können, um ihre Geräte zu registrieren und auf Ressourcen wie Unternehmens-Apps und -E-Mails zuzugreifen. Die Konfiguration der Geschäftsbedingungen ist optional. Weitere Informationen zu den [Nutzungsbedingungen](terms-and-conditions-create.md).

## <a name="enrollment-restrictions"></a>Registrierungseinschränkungen

Sie können auswählen, ob die Geräteregistrierung beschränkt werden soll, und zwar durch:
- Geräteplattform
- Anzahl von Geräten pro Benutzer
- Blockieren persönlicher Geräte

Weitere Informationen zu [Registrierungseinschränkungen](enrollment-restrictions-set.md).

## <a name="enable-apple-device-enrollment"></a>Aktivieren der Apple-Geräteregistrierung

Für die iOS- und macOS-Geräteregistrierung ist ein MDM-Push-Zertifikat erforderlich. Weitere Informationen zu [MDM-Push-Zertifikaten](apple-mdm-push-certificate-get.md).

## <a name="corporate-identifiers"></a>Unternehmensbezeichner

Sie können IMEI-Nummern (IMEI = International Mobile Equipment Identifier) und Seriennummern auflisten, um unternehmenseigene Geräte zu identifizieren. Weitere Informationen zu [Unternehmensbezeichnern](corporate-identifiers-add.md).

## <a name="device-enrollment-manager"></a>Geräteregistrierungs-Manager
Sie können Benutzer zu Geräteregistrierungs-Managern machen.  DEM-Benutzer (DEM = Device Enrollment Manager, Geräteregistrierungs-Manager) können eine große Anzahl mobiler Geräte mit einem einzelnen Benutzerkonto registrieren. Das DEM-Konto kann bis zu 1.000 Geräte registrieren. Weitere Informationen zu [Geräteregistrierungs-Managern](device-enrollment-manager-enroll.md).

## <a name="device-categories"></a>Gerätekategorien

Sie können mithilfe von Gerätekategorien basierend auf definierten Kategorien automatisch Geräte zu Gruppen hinzufügen. Durch die Organisation von Geräten in Gruppen wird die Verwaltung dieser Geräte vereinfacht. Weitere Informationen zu [Gerätekategorien](device-group-mapping.md).
