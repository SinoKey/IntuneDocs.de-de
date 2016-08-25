---
title: "Suchen eines Paketfamiliennamens (PFN) für VPN pro App | Microsoft Intune"
description: "Suchen Sie einen Paketfamiliennamen (PFN), den Sie zum Konfigurieren eines anwendungsbezogenen VPN („VPN pro App“) benötigen."
keywords: 
author: nbigman
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 74643d1d-4fd9-4cff-ac79-1a42281d2f76
ms.reviewer: tycast
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3cc73e43f09709b71c78a81c73b044d92d4ef401
ms.openlocfilehash: 77977ea32ea37a54e9d67638bb0e4c3bb6841fb3


---

# Suchen eines Paketfamiliennamens (PFN) für eine Konfiguration mit VPN pro App

Es gibt zwei Möglichkeiten zum Suchen eines Paketfamiliennamens (PFN), den Sie zum Einrichten eines anwendungsbezogenen VPNs benötigen.

## Suchen eines PFN für eine App, die auf einem Windows 10-Computer installiert ist

Wenn die App, mit der Sie arbeiten, bereits auf einem Windows 10-Computer installiert ist, können Sie den PFN mit dem PowerShell-Cmdlet [Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx) abrufen.

Die Syntax für die „Get-AppxPackage“ lautet:

` Parameter Set: __AllParameterSets`
` Get-AppxPackage [[-Name] <String> ] [[-Publisher] <String> ] [-AllUsers] [-User <String> ] [ <CommonParameters>]`

> [!NOTE]
Möglicherweise müssen Sie PowerShell als Administrator ausführen, um den PFN abzurufen.

Beispielsweise rufen Sie mit `Get-AppxPackage` die Informationen über alle auf dem Computer installierten universellen Apps ab.

Wenn Sie Informationen über eine App abrufen möchten, von der Sie den Namen oder einen Teil des Namens kennen, verwenden Sie `Get-AppxPackage *<app_name>`. Das Verwenden des Platzhalterzeichens ist besonders nützlich, wenn Sie den vollständigen Namen der App nicht genau kennen. Zum Beispiel können Sie mit `Get-AppxPackage *OneNote` Informationen über OneNote abrufen.


Für OneNote werden folgende Informationen abgerufen:

`Name                   : Microsoft.Office.OneNote`

`Publisher              : CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US`

`Architecture           : X64`

`ResourceId             :`

`Version                : 17.6769.57631.0`

`PackageFullName        : Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`InstallLocation        : C:\Program Files\WindowsApps`

`\Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`IsFramework            : False`

**`PackageFamilyName      : Microsoft.Office.OneNote_8wekyb3d8bbwe`**

`PublisherId            : 8wekyb3d8bbwe`



## Suchen eines PFN, wenn die App nicht auf dem Computer installiert ist

1.  Navigieren Sie zu „https://www.microsoft.com/en-us/store/apps“.
2.  Geben Sie in der Suchleiste den Namen der App ein. Suchen Sie z.B. nach OneNote.
3.  Wählen Sie den Link zu der App aus. Am Ende der URL finden Sie eine Reihe von Buchstaben. In unserem Beispiel sieht die URL folgendermaßen aus: `https://www.microsoft.com/en-us/store/apps/onenote/9wzdncrfhvjl`.
4.  Fügen Sie in eine andere Registerkarte die folgende URL ein: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata`. Ersetzen Sie `<app id>` durch die App-ID, die Sie unter „https://www.microsoft.com/en-us/store/apps“ gefunden haben (die Reihe von Buchstaben am Ende der URL aus Schritt 3). In unserem Beispiel für OneNote fügen Sie `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata` ein.

In Microsoft Edge werden die gewünschten Informationen angezeigt. In Internet Explorer müssen Sie **Öffnen** auswählen, um die Informationen anzuzeigen. Der PFN wird in der ersten Zeile angegeben. Dies sind die Ergebnisse für unser Beispiel:


`{`
`  "packageFamilyName": "Microsoft.Office.OneNote_8wekyb3d8bbwe",`
`  "packageIdentityName": "Microsoft.Office.OneNote",`
`  "windowsPhoneLegacyId": "ca05b3ab-f157-450c-8c49-a1f127f5e71d",`
`  "publisherCertificateName": "CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US"`
`}`



<!--HONumber=Aug16_HO3-->


