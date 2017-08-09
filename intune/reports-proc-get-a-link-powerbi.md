---
title: Verbinden mit dem Data Warehouse mit Power BI | Microsoft-Dokumentation
description: "Sie können eine Datei herunterladen, um Sie mit Microsoft Power BI zu verwenden, die es Ihnen ermöglicht, interaktive, dynamisch generierte Berichte für Ihren Intune-Mandanten zu laden."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5E5A35D3-88F8-441B-8A0B-C5D7A1E5137B
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a9d99b71b9f84eea45ae597ed0f69010f6e95805
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2017
---
# <a name="connect-to-the-data-warehouse-with-power-bi"></a>Verbinden mit dem Data Warehouse mit Power BI

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Sie können eine Datei herunterladen, um Sie mit Microsoft Power BI zu verwenden, die es Ihnen ermöglicht, interaktive, dynamisch generierte Berichte für Ihren Intune-Mandanten zu laden. Die Data Warehouse Power BI-Datei (PBIX) enthält die Verbindungseinstellungen für Ihren Mandanten und die folgenden Beispielberichte und Diagramme: 

  -  Geräte
  -  Anmeldung
  -  App-Schutzrichtlinie
  -  Kompatibilitätsrichtlinie
  -  Gerätekonfigurierungsprofile
  -  Softwareupdates
  -  Protokolle zum Gerätebestand

Es werden auch Trends für die Registrierung, die Konformität, das Gerätekonfigurierungsprofil und Softwareupdates hervorgehoben. Beispieldiagramme und Berichte wenden benutzerfreundliche Filter auf den Zeichenbereich an. Um erweiterte Filter zu verwenden, sehen Sie sich den Bereich **Filter** in Power BI Desktop an. 

Die folgenden Schritte zeigen, wie Sie die Power BI-Datei herunterladen und wie Sie den OData-Link mit Power BI verwenden.

## <a name="install-power-bi"></a>Installieren von Power BI

Installieren Sie die neueste Version von Power BI Desktop. Sie können Power BI Desktop aus [PowerBI.microsoft.com](https://powerbi.microsoft.com/en-us/desktop) herunterladen. 

## <a name="load-the-data-and-reports-using-the-power-bi-file-pbix"></a>Laden der Daten und Berichte mit der Power BI-Datei (PBIX)

Die Power BI-Datei (PBIX) enthält Verbindungsinformationen für Ihren Mandanten und eine Reihe von vordefinierten Berichten, die auf dem Data Warehouse-Datenmodell basieren. Öffnen Sie die Datei in Power BI Desktop, und melden Sie sich bei Azure AD an. Der Bericht lädt die Daten aus Ihrem Intune-Mandanten.

1.  Wählen Sie im Azure-Portal **Überwachung + Verwaltung** > **Intune** aus. Sie können auch Ressourcen nach **Intune** durchsuchen.  
2.  Öffnen Sie das Blatt **Microsoft Intune Data Warehouse API (Preview)** (Microsoft Intune Data Warehouse-API (Vorschau)).
3.  Klicken Sie auf **Power BI-Datei herunterladen**. Die Datei mit der Erweiterung PBIX wird an den angegebenen Speicherort heruntergeladen.
4.  Öffnen Sie die Datei mit Power BI. Die *Intune Data Warehouse-Berichte* werden geladen. Dies kann jedoch eine Weile dauern, da Ihre Mandantendaten abgerufen werden.
5.  Klicken Sie auf **Aktualisieren**, um Ihre Mandantendaten zu laden und die Berichte zu überprüfen.
6.  Wenn Power BI Ihre Azure Active Directory-Anmeldeinformationen noch nicht authentifiziert hat, werden Sie von Power BI aufgefordert, Ihre Anmeldeinformationen bereitzustellen. Wenn Sie Ihre Anmeldeinformationen auswählen, wählen Sie **Organisationskonto** als Authentifizierungsmethode aus.

## <a name="load-the-data-in-power-bi-using-the-odata-link"></a>Laden der Daten in Power BI mit dem OData-Link

Wenn der Client bei Azure AD authentifiziert ist, verbindet sich die OData-URL mit dem RESTful-Endpunkt in der Data Warehouse-API, der das Datenmodell für Ihren Berichtserstellungsclient verfügbar macht. Um mit Power BI Desktop eine Verbindung herzustellen und Ihre eigene Berichte zu erstellen, gehen Sie wie folgt vor. Sie sind nicht auf Power BI Desktop festgelegt, sondern können Ihres bevorzugtes analytisches Tools mit der OData-URL verwenden. Die gilt unter der Voraussetzung, dass der Client die OAuth 2.0-Authentifizierung und den OData v4. 0-Standard unterstützt.

1.  Rufen Sie die **OData-URL** aus dem Berichtsblatt ab, z.B. `https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`.
2.  Öffnen Sie **Power BI Desktop**.
3.  Wählen Sie **Startseite** > **Daten abrufen** aus. Wählen Sie **OData-Feed** aus.
4.  Wählen Sie **Standard**.
5.  Geben Sie die **OData-URL** in das URL-Feld ein, oder fügen Sie sie ein.
6.  Klicken Sie auf **OK**.
7.  Wenn Sie Ihren Mandanten noch nicht über den Power BI Desktop-Client bei Azure AD authentifiziert haben, geben Sie Ihre Anmeldeinformationen ein.  
    a.  Wählen Sie **Organisationskonto** aus.  
    b.  Geben Sie Ihren Benutzernamen und Ihr Kennwort ein.  
    c.  Klicken Sie auf **Anmelden**.  
    d.  Klicken Sie auf **Verbinden**.  
8.  Klicken Sie auf **Laden**.

## <a name="next-steps"></a>Nächste Schritte

Hier finden Sie Informationen zu Ihrer Umgebung, z.B. der Anzahl der registrierten Geräte, nach Tagen innerhalb der letzten Woche sortiert. Mithilfe der Berichte und mithilfe der Intune Data Warehouse-Power BI-Datei (PBIX), die aus dem Blatt in Azure abgerufen wurde, erhalten Sie auch Einblicke in Ihren Intune-Mandanten und die Clientauffüllung. Intune bietet jedoch eine Anzahl von weitere Möglichkeiten, um die Daten zu erweitern oder wiederzuverwenden. Power BI und die Intune Data-Warehouse-API bieten Ihnen noch viele weiter Vorteile:

<!-- -  You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
 -  Ihre Mandantendaten sind organisiert, damit Sie die Daten auswerten können. Weitere Informationen dazu, wie die Daten organisiert werden, finden Sie unter [Data Warehouse-Datenmodell](reports-ref-data-model.md). 
<!-- -  You can also access the data from a RESTful interface and incorporate the data into your own app. For more information, see [Get data from the Data Warehouse API with a REST client](reports-proc-data-rest.md). -->