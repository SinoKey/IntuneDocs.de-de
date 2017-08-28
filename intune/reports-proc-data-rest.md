---
title: Abrufen von Daten aus der Data Warehouse-API mit einem REST-Client
description: Rufen Sie Daten aus dem Intune-Data Warehouse mit einer RESTful-API ab.
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: D6D15039-4036-446C-A58F-A5E18175720A
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1bbb0e8ba84e221df3a434da79c513939267648b
ms.sourcegitcommit: b8ef9d8387b4d9b2ea4e6ce937635304771e6532
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2017
---
# <a name="get-data-from-the-intune-data-warehouse-api-with-a-rest-client"></a>Abrufen von Daten aus der Intune-Data Warehouse-API mit einem REST-Client

Sie können auf das Intune-Data Warehouse-Datenmodell über RESTful-Endpunkte zugreifen. Um auf Ihre Daten zuzugreifen, muss sich der Client mithilfe von OAuth 2.0 bei Microsoft Azure Active Directory (Azure AD) autorisieren. Richten Sie zum Aktivieren des Zugriffs zuerst eine native App in Azure ein, und erteilen Sie ihr Berechtigungen für die Microsoft Intune-API. Ihr lokaler Client ruft die Autorisierung ab, und dann kann der Client über die native App mit den Data Warehouse-Endpunkten kommunizieren.

Für die Einrichtung eines Clients zum Abrufen von Daten aus der Data Warehouse-API bestehen die folgenden Anforderungen:

1. Erstellen Sie eine Client-App als eine native App in Azure.
3. Erteilen Sie der Client-App Zugriff auf die Microsoft Intune-API.
3. Erstellen Sie einen lokalen REST-Client zum Abrufen der Daten.

Anhand der folgenden Schritte erfahren Sie, wie Postman als Client autorisiert und verwendet wird. Bei Postman handelt es sich um ein häufig verwendetes Tool zur Problembehandlung und Entwicklung von REST-Clients für APIs. Weitere Informationen zu Postman finden Sie auf der [Postman](https://www.getpostman.com)-Website. Dieses Thema enthält auch ein C#-Codebeispiel. Darin wird gezeigt, wie ein Client autorisiert und Daten aus der API abgerufen werden.

## <a name="create-a-native-app-in-azure"></a>Erstellen einer nativen App in Azure

Erstellen Sie eine native App in Azure. Diese native App ist die Client-App. Der Client auf dem lokalen Computer verweist auf die Intune-Data Warehouse-API, wenn der lokale Client Anmeldeinformationen anfordert. 

1. Melden Sie sich für Ihren Mandanten beim Azure-Portal an. Klicken Sie auf **Azure Active Directory** > **App-Registrierungen**, um das Blatt **App-Registrierungen** zu öffnen.
2. Klicken Sie auf **New app registration** (Neue App-Registrierung).
3. Geben Sie die App-Informationen ein.
    1.  Geben Sie unter **Name** einen Anzeigenamen wie „Intune-Data Warehouse-Client“ ein.
    2.  Wählen Sie für den **Anwendungstyp** die Option **Nativ** aus.
    3.  Geben Sie eine URL als **Anmelde-URL** ein. Die Anmelde-URL richtet sich nach dem jeweiligen Szenario. Wenn Sie jedoch planen, Postman zu verwenden, geben Sie `https://www.getpostman.com/oauth2/callback` ein. Sie verwenden bei der Authentifizierung in Azure AD den Schritt zum Rückruf der Client-Authentifizierung.
4.  Klicken Sie auf **Erstellen**.

     ![Intune Data Warehouse-API](media\reports-get_rest_data_client_overview.png)

5. Notieren Sie sich die **Anwendungs-ID** dieser App. Sie benötigen sie im nächsten Abschnitt.
6. Wenn Sie Postman verwenden möchten, fügen Sie einen Schlüssel hinzu. Der Schlüssel wird bei der Azure AD-Authentifizierung als geheimer Clientschlüssel verwendet. So fügen Sie einen Schlüssel hinzu:
    1.  Klicken Sie im Einstellungsblatt der App unter **API-Zugriff** auf **Schlüssel**.
    2.  Geben Sie unter **Beschreibung** einen Namen für Ihren Schlüssel ein, z.B. „Client-Secret“ (geheimer Clientschlüssel).
    3.  Wählen Sie bei „Dauer“ **1 Jahr** aus.
    4.  Klicken Sie auf **Speichern**. 
    5.  Kopieren Sie den Wert Ihres Schlüssels. Sie können den Schlüssel nicht mehr abrufen, nachdem das Blatt **Einstellungen** für die Schlüssel geschlossen wurde.

## <a name="grant-the-native-app-access-to-the-microsoft-intune-api"></a>Erteilen Sie der nativen App Zugriff auf die Microsoft Intune-API.

Sie haben jetzt eine in Azure definierte App. Erteilen Sie Zugriff von der nativen App auf die Microsoft Intune-API.

1.  Klicken Sie auf die native App. Sie haben der App einen Namen wie „Intune-Data Warehouse-Client“ gegeben.
2.  Klicken Sie auf dem Blatt **Einstellungen** auf **Erforderliche Berechtigungen**.
3.  Klicken Sie auf dem Blatt **Erforderliche Berechtigungen** auf **Hinzufügen**.
4.  Klicken Sie auf **Hiermit wählen Sie eine API aus.**.
5.  Suchen Sie nach dem Namen der Web-App. Sie heißt **Microsoft Intune-API**.
6.  Klicken Sie in der Liste auf die App.
7.  Klicken Sie auf **Auswählen**.
8.  Aktivieren Sie das Kontrollkästchen **Delegierte Berechtigungen**, um **Get data warehouse information from Microsoft Intune** (Data Warehouse-Informationen aus Microsoft Intune abrufen) hinzuzufügen.

    ![Zugriff aktivieren](media\reports-get_rest_data_client_access.png)

9.  Klicken Sie auf **Auswählen**.
10.  Klicken Sie auf **Fertig**.
11.  Sie können optional auch auf dem Blatt „Erforderliche Berechtigungen“ auf **Berechtigungen erteilen** klicken. Dadurch wird der Zugriff auf alle Konten im aktuellen Verzeichnis gewährt. Außerdem wird so verhindert, dass das Zustimmungsdialogfeld für jeden Benutzer im Mandanten angezeigt wird. Weitere Informationen finden Sie unter [Integrieren von Anwendungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications).
12.  Klicken Sie auf **Ja**.

## <a name="get-data-from-the-microsoft-intune-api-with-postman"></a>Abrufen von Daten aus der Microsoft Intune-API mit Postman

Sie können mit der Intune-Data Warehouse-API und einem generischen REST-Client wie Postman arbeiten. Postman kann einen Einblick in die Funktionen der API und das zugrunde liegende OData-Datenmodell sowie eine Problembehandlung für die Verbindung mit den API-Ressourcen durchführen. In diesem Abschnitt finden Sie Informationen zum Generieren eines Auth2.0-Tokens für den lokalen Client. Der Client benötigt das Token zum Authentifizieren bei Azure AD und den Zugriff auf die API-Ressourcen.

### <a name="information-you-will-need-to-make-the-call"></a>Informationen, die Sie für den Aufruf benötigen

Sie benötigen die folgenden Informationen für einen REST-Aufruf mit Postman:

| Attribut        | Beschreibung                                                                                                                                                                          | Beispiel                                                                                       |
|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| Rückruf-URL     | Legen Sie dies auf der Seite „Einstellungen“ Ihrer App als die Rückruf-URL fest.                                                                                                                              | https://www.getpostman.com/oauth2/callback                                                    |
| Tokenname       | Eine Zeichenfolge, mit der die Anmeldeinformationen der Azure-App übergeben werden. Der Prozess generiert Ihr Token, sodass Sie die Data Warehouse-API aufrufen können.                          | Bearer                                                                                        |
| Authentifizierungs-URL         | Dies ist die URL, die zum Authentifizieren verwendet wird. | https://login.microsoftonline.com/common/oauth2/authorize?resource=https://api.manage.microsoft.com |
| Zugriffstoken-URL | Mit dieser URL wird das Token erteilt.                                                                                                                                              | https://login.microsoftonline.com/common/oauth2/token |
| Client-ID        | Diese haben Sie erstellt und sich bei der Erstellung der nativen App in Azure notiert.                                                                                               | 4184c61a-e324-4f51-83d7-022b6a81b991                                                          |
| Geheimer Clientschlüssel    | Diese haben Sie erstellt und beim Hinzufügen eines Schlüssels zur Client-App in Azure notiert.                                                                                              | JZoRZGPmN9xwsUnfX9UW877dkV5Fn/qQClhr7SuyMUQ=                                                  |
| Bereich (Optional) | Leer                                                                                                                                                                               | Sie können das Feld leer lassen.                                                                     |
| Gewährungstyp       | Das Token ist ein Autorisierungscode.                                                                                                                                                  | Autorisierungscode                                                                            |

Sie brauchen den Endpunkt. In diesem Beispiel werden wir Daten aus der **Datumsentität** abrufen. Die **Datumsentität** hat das folgende Format: `https://fef.{aus}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`. Sie verwenden die Verwaltungs-URL Ihres Mandanten, die Sie bereits bei der Erstellung Ihrer Web-App verwendet haben.

### <a name="make-the-rest-call"></a>Ausführen des REST-Aufrufs

Um ein neues Zugriffstoken für Postman abzurufen, müssen Sie die URL der Azure AD-Autorisierung, Ihre Client-ID und den geheimen Clientschlüssel hinzufügen. Postman lädt die Autorisierungsseite, auf der Sie Ihre Anmeldeinformationen eingeben.

#### <a name="add-the-information-used-to-request-the-token"></a>Fügen Sie die Informationen zum Anfordern des Tokens hinzu.

1.  Wenn Sie es nicht bereits installiert haben, laden Sie Postman herunter. Postman können Sie unter [www.getpostman](https://www.getpostman.com) herunterladen.
2.  Öffnen Sie Postman. Wählen Sie den HTTP-Vorgang **GET** aus.
3.  Fügen Sie die Endpunkt-URL in die Adresse ein. Sie sollte etwa wie folgt aussehen:  

    `https://fef.msua06.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`
4.  Klicken Sie auf die Registerkarte **Autorisierung**, und wählen Sie aus der Liste **Typ** die Option **OAuth 2.0** aus.
5.  Klicken Sie auf **Get New Access Token** (Neues Zugriffstoken abrufen).
6.  Stellen Sie sicher, dass Sie die Rückruf-URL bereits zu Ihrer App in Azure hinzugefügt haben. Die Rückruf-URL lautet `https://www.getpostman.com/oauth2/callback`.
7.  Geben Sie „Bearer“ als **Tokenname** ein.
8.  Fügen Sie die **Authentifizierungs-URL** hinzu. Sie sollte etwa wie folgt aussehen:  

    `https://login.microsoftonline.com/common/oauth2/authorize?resource=https://api.manage.microsoft.com`
9.  Fügen Sie das **Zugriffstoken** hinzu. Sie sollte etwa wie folgt aussehen:  

     `https://login.microsoftonline.com/common/oauth2/token`

10. Fügen Sie die **Client-ID** aus der nativen Anwendung hinzu, die Sie in Azure erstellt und `Intune Data Warehouse Client` genannt haben. Sie sollte etwa wie folgt aussehen:  

     `4184c61a-e324-4f51-83d7-022b6a81b991`

11. Fügen Sie den **geheimen Clientschlüssel** hinzu, den Sie bei der Erstellung der nativen App in Azure als Schlüssel definiert haben. Sie sollte etwa wie folgt aussehen: 

     `F360R69M0MS72OB6YAqTyXO9MsXZx/OJTgAE2HB4k2k=`

12. Wählen Sie **Autorisierungscode** und „Request access token locally“ (Zugriffstoken lokal anfordern) aus.

13. Klicken Sie auf **Request Token** (Token anfordern).

    ![Informationen für das Token](media\reports-postman_getnewtoken.png)

14. Geben Sie Ihre Anmeldeinformationen auf der Azure AD-Autorisierungsseite ein. Die Liste der vorhandenen Token in Postman enthält jetzt das Token mit dem Namen `Bearer`.
16. Wählen Sie das Token aus. Wählen Sie **Header** für „Add token to“ (Token hinzufügen zu) aus.
17. Klicken Sie auf **Use Token** (Token verwenden). Die Liste der Header enthält den neuen Schlüsselwert von „Authorization“ (Autorisierung) und den Wert `Bearer <your-authorization-token>`.

#### <a name="send-the-call-to-the-endpoint-using-postman"></a>Senden des Aufrufs an den Endpunkt mit Postman

1.  Klicken Sie auf **Senden**.
2.  Die Rückgabedaten werden im Antworttextfeld von Postman angezeigt.

    ![Postman 200OK](media\reports-postman_200OK.png)

## <a name="create-a-rest-client-c-to-get-data-from-the-intune-data-warehouse"></a>Erstellen eines REST-Clients (C#), um Daten aus der Intune-Data Warehouse-API abzurufen

Das folgende Beispiel enthält einen einfachen REST-Client. Der Code verwendet die **httpClient**-Klasse aus der .NET-Bibliothek. Sobald der Client Anmeldeinformationen für Azure AD erhält, erstellt er einen GET REST-Aufruf, um die Datumsentität aus der Data Warehouse-API abzurufen.

> [!Note]  
> Sie können [auf GitHub](https://github.com/Microsoft/Intune-Data-Warehouse/blob/master/Samples/CSharp/Program.cs) auf das folgende Codebeispiel zugreifen. Im GitHub-Repository finden Sie auch die neuesten Änderungen und Updates des Beispiels.

1.  Öffnen Sie **Microsoft Visual Studio**.
2.  Klicken Sie auf **Datei** > **Neues Projekt**. Erweitern Sie **Visual C#**, und wählen Sie **Konsolen-App (.NET Framework)** aus. 
3.  Nennen Sie das Projekt ` IntuneDataWarehouseSamples`, navigieren Sie dorthin, wo Sie das Projekt speichern möchten, und klicken Sie dann auf **OK**.
3.  Klicken Sie mit der rechten Maustaste auf den Namen der Projektmappe im Projektmappen-Explorer, und wählen Sie dann **NuGet-Pakete für Projektmappe verwalten** aus. Klicken Sie auf **Durchsuchen**, und geben Sie dann in das Suchfeld „Microsoft.IdentityModel.Clients.ActiveDirectory“ ein.
4. Wählen Sie das Paket aus, wählen Sie unter „Manage Packages for Your Solution“ (Pakete für Ihre Projektmappe verwalten) das Projekt **IntuneDataWarehouseSamples** aus, und klicken Sie dann auf **Installieren**. 
5. Klicken Sie auf **I Accept** (Ich stimme zu), um die NuGet-Paketlizenz anzunehmen.
6. Öffnen Sie `Program.cs` über den Projektmappen-Explorer.

    ![Projekt in Visual Studio](media\reports-get_rest_data_in.png)

7.  Ersetzen Sie den Code in „Program.cs“ durch den folgenden Code:  
    ```csharp
namespace IntuneDataWarehouseSamples
{
    using System;
    using System.Net.Http;
    using System.Net.Http.Headers;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;

    class Program
    {
     static void Main(string[] args)
  {
   /**
    * TODO: Replace the below values with your own.
    * emailAddress - The email address of the user that you will authenticate as.
    *
    * password  - The password for the above email address.
    *    This is inline only for simplicity in this sample. We do not 
    *    recommend storing passwords in plaintext.
    *
    * applicationId - The application ID of the native app that was created in AAD.
    *
    * warehouseUrl   - The data warehouse URL for your tenant. This can be found in 
    *      the Azure portal.
    * 
    * collectionName - The name of the warehouse entity collection you would like to 
    *      access.
    */
   var emailAddress = "intuneadmin@yourcompany.com";
   var password = "password_of(intuneadmin@yourcompany.com)";
   var applicationId = "<Application ID>";
   var warehouseUrl = "https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta";
   var collectionName = "dates";

   var adalContext = new AuthenticationContext("https://login.windows.net/common/oauth2/token");
   AuthenticationResult authResult = adalContext.AcquireTokenAsync(
    resource: "https://api.manage.microsoft.com/",
    clientId: applicationId,
    userCredential: new UserPasswordCredential(emailAddress, password)).Result;

   var httpClient = new HttpClient();
   httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue("Bearer", authResult.AccessToken);

   var uriBuilder = new UriBuilder(warehouseUrl);
   uriBuilder.Path += "/" + collectionName;

   HttpResponseMessage response = httpClient.GetAsync(uriBuilder.Uri).Result;

   Console.Write(response.Content.ReadAsStringAsync().Result);
   Console.ReadKey();
  }
    }
    ```

8.  Aktualisieren Sie die `TODO`s im Codebeispiel.
9.  Drücken Sie **STRG + F5**, um den Intune.DataWarehouseAPIClient im Debugmodus zu erstellen und auszuführen.

    ![Im JSON-Format abgerufene Datumsentität](media\reports-get_rest_data_output.png)

10.  Überprüfen Sie die Konsolenausgabe. Die Ausgabe enthält die Daten im JSON-Format, die aus der **Datumsentität** in Ihrem Intune-Mandanten abgerufen wurden.

## <a name="next-steps"></a>Nächste Schritte

Informationen zur Autorisierung, der API-URL-Struktur und den OData-Endpunkten finden Sie unter [Endpunkt der Intune Data Warehouse-API](reports-api-url.md). 

Auch im Intune Data Warehouse-Datenmodell finden Sie die in der API enthaltenen Datenentitäten. Weitere Informationen finden Sie unter [Datenmodell von Data Warehouse](reports-ref-data-model.md).