---
title: "Verwenden von Intune-App-Konfigurationsrichtlinien für iOS"
titleSuffix: Intune on Azure
description: "Erfahren Sie, wie Sie App-Konfigurationsrichtlinien zum Bereitstellen von Konfigurationsdaten für eine iOS-App beim Ausführen verwenden.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b261834c85a9dd3cbc6f8fae40933dd7a79acf93
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-ios"></a>Verwenden von Microsoft Intune-App-Konfigurationsrichtlinien für iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Verwenden Sie App-Konfigurationsrichtlinien in Microsoft Intune, um Einstellungen anzugeben, die beim Ausführen einer iOS-App durch Benutzer verwendet werden. Beispielsweise kann eine App vom Benutzer Folgendes anfordern:

-   Eine benutzerdefinierte Portnummer

-   Spracheinstellungen

-   Sicherheitseinstellungen

-   Brandingeinstellungen, z. B. ein Unternehmenslogo

Wenn Benutzer diese Einstellungen nicht ordnungsgemäß eingeben, kann dies zur erhöhten Belastung Ihres Helpdesks führen und die Annahme der neuen Apps verlangsamen.

Mit App-Konfigurationsrichtlinien können Sie diese Probleme beseitigen, da Sie diese Einstellungen in einer Richtlinie Benutzern zuweisen können, bevor diese die App ausführen. Die Einstellungen werden dann automatisch bereitgestellt, und die Benutzer müssen keine weitere Aktion durchführen. Apps müssen geschrieben werden, um die Verwendung von App-Konfigurationen zu unterstützen. Wenden Sie sich für mehr Informationen an Ihren App-Anbieter.

Sie weisen diese Richtlinien nicht direkt Benutzern und Geräten zu. Stattdessen verknüpfen Sie eine Richtlinie mit einer App und weisen dann die App zu. Die Richtlinieneinstellungen werden immer dann verwendet, wenn die Anwendung danach sucht (in der Regel beim ersten Ausführen).

> [!TIP]
> Dieser Richtlinientyp ist zurzeit nur für Geräte unter iOS 8.0 und höher verfügbar. Er unterstützt die folgenden App-Installationstypen:
>
> -   **Verwaltete iOS-App aus dem App Store**
> -   **App-Paket für iOS**
>
> Weitere Informationen zu Installationstypen von Apps finden Sie unter [Hinzufügen von Apps zu Microsoft Intune](apps-add.md).

## <a name="create-an-app-configuration-policy"></a>Erstellen einer Konfigurationsrichtlinie für Apps
1.  Melden Sie sich beim Azure-Portal an.
2.  Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3.  Wählen Sie auf dem Blatt **Intune** die Option **Mobile Apps** aus.
4.  Wählen Sie in der Workload **Mobile Apps** die Option **Verwalten** > **App-Konfigurationsrichtlinien** aus.
5.  Wählen Sie auf dem Blatt mit der Liste der Richtlinien die Option **Hinzufügen** aus.
6.  Geben Sie auf dem Blatt **Konfigurationsrichtlinie hinzufügen** einen **Namen** und optional eine **Beschreibung** für die App-Konfigurationsrichtlinie an.
7.  Wählen Sie für den **Geräteregistrierungstyp** eine der folgenden Optionen aus:
    - **Bei Intune registriert**: Für Apps, die von Intune verwaltet werden.
    - **Nicht bei Intune registriert**: Für Apps die nicht von Intune oder einer anderen Lösung verwaltete werden.
8.  Wählen Sie für **Plattform** **iOS** aus (für Geräte, die nur bei Intune registriert sind)
9.  Wählen Sie **Zugeordnete App** aus, und wählen Sie auf dem Blatt **Zugeordnete App** die verwaltete App aus, auf die Sie die Konfiguration anwenden möchten.
10. Wählen Sie auf dem Blatt **Konfigurationsrichtlinie hinzufügen** die Option **Konfigurationseinstellungen** aus.
11. Wählen Sie auf dem Blatt **Konfigurationsrichtlinie hinzufügen** aus, wie die XML-Werte für das Konfigurationsprofil angegeben werden sollen:
    - **XML-Daten eingeben:** (für Geräte, die nur bei Intune registriert sind): Geben Sie eine Liste von XML-Eigenschaften mit den gewünschten App-Konfigurationseinstellungen ein, oder fügen Sie sie aus der Zwischenablage ein. Das Format der XML-Eigenschaftenliste variiert je nach der App, die Sie konfigurieren. Wenden Sie sich an den Hersteller der App, um ausführliche Informationen über das genau zu verwendende Format zu erhalten.
Intune prüft, ob der eingegebene XML-Code in einem gültigen Format vorliegt. Es wird nicht überprüft, ob die XML-Eigenschaftenliste mit der App verwendet werden kann, der sie zugeordnet ist.
Weitere Informationen zu XML-Eigenschaftenlisten finden Sie unter [Understanding XML Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) in der iOS Developer Library.
    - **Konfigurations-Designer verwenden:** (egal, ob das Gerät bei Intune registriert ist oder nicht )ermöglicht Ihnen, XML-Schlüssel-Wert-Paare direkt im Portal einzugeben
11. Navigieren Sie, wenn Sie fertig sind, zurück zum Blatt **Konfigurationsrichtlinie hinzufügen**, und klicken Sie auf **Erstellen**.

Die Richtlinie wird erstellt und auf dem Blatt mit der Richtlinienliste angezeigt.



>[!Note]
>Sie können das [Intune App SDK](https://docs.microsoft.com/intune/app-sdk-ios) verwenden, um branchenspezifische Apps darauf vorzubereiten, dass Sie von den Intune-App-Schutzrichtlinien sowie App-Konfigurationsrichtlinien verwaltet werden, egal ob das Gerät bei Intune registriert ist oder nicht. Sie können beispielsweise eine App-Konfigurationsrichtlinie verwenden, um zugelassene oder blockierte URLs für den [Intune Managed Browser](app-configuration-managed-browser.md) zu konfigurieren. Sobald eine App richtlinienkonform ist, können Sie diese mithilfe einer Richtlinie konfigurieren.


Wenn die zugewiesene App auf einem Gerät gestartet wird, wird sie mit den Einstellungen ausgeführt, die Sie in der App-Konfigurationsrichtlinie konfiguriert haben.
In der Dokumentation für die App, die Sie konfigurieren, finden Sie Informationen zu den Geschehnissen, wenn eine oder mehrere App-Konfigurationsrichtlinien in Konflikt geraten.

>[!Tip]
>Zusätzlich können Sie die Graph-API verwenden, um diese Aufgaben auszuführen. Weitere Informationen finden Sie in der [Graph-API-Referenz für die MAM-Zielkonfiguration](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).


## <a name="information-about-the-xml-file-format"></a>Informationen zum XML-Dateiformat

Intune unterstützt die folgenden Datentypen in einer Eigenschaftenliste:

- &lt;integer&gt;
- &lt;real&gt;
- &lt;string&gt;
- &lt;array&gt;
- &lt;dict&gt;
- &lt;true /&gt; oder &lt;false /&gt;

Weitere Informationen zu Datentypen finden Sie unter [About Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) in der iOS Developer Library.

Darüber hinaus unterstützt Intune die folgenden Tokentypen in der Eigenschaftenliste:
- \{\{userprincipalname\}\} – (Beispiel: **John@contoso.com**)
- \{\{mail\}\} – (Beispiel: **John@contoso.com**)
- \{\{partialupn\}\} – (Beispiel: **John**)
- \{\{accountid\}\} – (Beispiel: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
- \{\{deviceid\}\} – (Beispiel: **b9841cd9-9843-405f-be28-b2265c59ef97**)
- \{\{userid\}\} – (Beispiel: **3ec2c00f-b125-4519-acf0-302ac3761822**)
- \{\{username\}\} – (Beispiel: **John Doe**)
- \{\{serialnumber\}\} – (Beispiel: **F4KN99ZUG5V2**) für iOS-Geräte
- \{\{serialnumberlast4digits\}\} – (Beispiel: **G5V2**) für iOS-Geräte

Die Zeichen \{\{ und \}\} werden nur von Tokentypen verwendet und dürfen nicht für andere Zwecke verwendet werden.

## <a name="example-format-for-an-app-configuration-xml-file"></a>Beispielformat für eine App-Konfigurations-XML-Datei

Wenn Sie eine App-Konfigurationsdatei erstellen, können Sie die folgenden Werte in diesem Format angeben:

```
<dict>
  <key>userprincipalname</key>
  <string>{{userprincipalname}}</string>
  <key>mail</key>
  <string>{{mail}}</string>
  <key>partialupn</key>
  <string>{{partialupn}}</string>
  <key>accountid</key>
  <string>{{accountid}}</string>
  <key>deviceid</key>
  <string>{{deviceid}}</string>
  <key>userid</key>
  <string>{{userid}}</string>
  <key>username</key>
  <string>{{username}}</string>
  <key>serialnumber</key>
  <string>{{serialnumber}}</string>
  <key>serialnumberlast4digits</key>
  <string>{{serialnumberlast4digits}}</string>
  <key>udidlast4digits</key>
  <string>{{udidlast4digits}}</string>
</dict>

```

## <a name="next-steps"></a>Nächste Schritte

Fahren Sie wie gewöhnlich mit dem [Zuweisen](apps-deploy.md) und [Überwachen](apps-monitor.md) der App fort.