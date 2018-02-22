---
title: "Einstellungen für Geräteeinschränkungen für macOS"
titlesuffix: Azure portal
description: "In diesem Artikel lernen Sie die Intune-Einstellungen zur Steuerung von Geräteeinstellungen und -funktionen auf macOS-Geräten kennen."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 1/31/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a88cf11209726a622863339c3a6c117f7b83be1e
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2018
---
# <a name="macos-device-restriction-settings-in-microsoft-intune"></a>Einstellungen für Geräteeinschränkungen für macOS-Geräte in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Verwenden Sie diese Einstellungen zum Verwalten von macOS-Geräten in einem Geräteeinschränkungsprofil.

## <a name="password"></a>Kennwort
-   **Kennwort:** Der Endbenutzer muss ein Kennwort eingeben, um auf das Gerät zugreifen zu können.
    -   **Erforderlicher Kennworttyp:** Geben Sie an, ob das Kennwort rein numerisch sein darf oder ob es alphanumerisch sein muss (also Buchstaben und Zahlen enthalten muss). Diese Einstellung wird lediglich unter Mac OS X 10.10.3 und höher unterstützt.
    -   **Anzahl nicht alphanumerischer Zeichen im Kennwort:** Geben Sie die erforderliche Anzahl komplexer Zeichen im Kennwort an (**0** bis **4**).<br>Bei einem komplexen Zeichen handelt es sich um ein Symbol, z.B. **?**.
    -   **Minimale Kennwortlänge:** Geben Sie die Mindestanzahl von Zeichen an, die Benutzer für das Kennwort festlegen müssen (zwischen **4** und **16** Zeichen).
    -   **Einfache Kennwörter:** Erlauben Sie die Verwendung einfacher Kennwörter wie **0000** oder **1234**.
    -   **Maximaler Zeitraum der Bildschirmsperre (in Minuten) bis zur Anforderung eines Kennworts:** Geben Sie an, wie lange der Computer inaktiv sein muss, bevor er mithilfe eines Kennworts entsperrt werden muss.
    -   **Maximaler Zeitraum der Inaktivität (in Minuten) bis zur Bildschirmsperrung:** Geben Sie die Zeitdauer an, die der Computer inaktiv sein muss, bevor der Bildschirms gesperrt wird.
    -   **Kennwortablauf (Tage):** Geben Sie an, nach wie vielen Tagen der Benutzer das Kennwort ändern muss (**1** bis **255** Tage).
    -   **Wiederverwendung vorheriger Kennwörter verhindern:** Geben Sie die Anzahl von vorherigen Kennwörtern an, die nicht erneut verwendet werden dürfen (**1** bis **24**).

## <a name="restricted-apps"></a>Eingeschränkte Apps

In der Liste der eingeschränkten Apps können Sie eine der folgenden Listen konfigurieren:

- **Unzulässige Apps:** Listet die (nicht von Intune verwalteten) Apps auf, die Benutzer nicht installieren und ausführen dürfen. Benutzer werden nicht daran gehindert, eine verbotene App zu installieren. Wenn sie dies jedoch tun, wird es Ihnen gemeldet.
- **Genehmigte Apps:** Listet die Apps auf, die Benutzer installieren dürfen. Benutzer dürfen keine Apps installieren, die in dieser Liste nicht aufgeführt sind. Apps, die von Intune verwaltet werden, sind automatisch zugelassen. Benutzer werden nicht daran gehindert, eine App zu installieren, die nicht auf der Genehmigungsliste aufgeführt ist. Wenn sie dies jedoch tun, wird es Ihnen gemeldet.

Klicken Sie zum Konfigurieren einer Liste auf **Hinzufügen**. Geben Sie dann einen Namen Ihrer Wahl sowie optional den Herausgeber der App und die Paket-ID der App an (z.B. *com.apple.calculator*).

## <a name="domains"></a>Domains

### <a name="unmarked-email-domains"></a>Nicht markierte E-Mail-Domänen

Fügen Sie im Feld **E-Mail-Domänen-URL** eine oder mehrere URLs der Liste hinzu. Wenn Endbenutzer eine E-Mail von einer anderen Domäne als einer erhalten, die Sie konfiguriert haben, wird die E-Mail in der iOS-Mail-App als nicht vertrauenswürdig gekennzeichnet.

