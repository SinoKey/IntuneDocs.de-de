---
title: Konfigurieren Sie iOS-apps mit Konfigurationsrichtlinien für mobile Anwendung in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
author: robstackmsft
---
# Konfigurieren Sie iOS-apps mit Konfigurationsrichtlinien für mobile Anwendung in Microsoft Intune
Verwenden von Konfigurationsrichtlinien für mobile Anwendung in Microsoft Intune Einstellungen angeben, die möglicherweise erforderlich, wenn der Benutzer eine Anwendung ausgeführt wird. Beispielsweise kann eine App vom Benutzer Folgendes anfordern:

-   Eine benutzerdefinierte Portnummer für die Ausführung

-   Spracheinstellungen

-   Sicherheitseinstellungen

-   Brandingeinstellungen wie z. B. ein Unternehmenslogo

Wenn diese Einstellungen vom Benutzer nicht ordnungsgemäß eingegeben werden, kann dies zur erhöhten Belastung Ihres Helpdesks führen und auch die Annahme der neuen Apps verlangsamen..

Mit Konfigurationsrichtlinien für mobile Apps können Sie diese Probleme beseitigen, da Sie diese Einstellungen für Benutzer in einer Richtlinie bereitstellen können, bevor die Benutzer die App ausführen. Die Einstellungen werden dann automatisch bereitgestellt, und der Benutzer muss keine weitere Aktion durchführen.

Sie stellen diese Richtlinien nicht direkt für Benutzer und Geräte bereit. Stattdessen verknüpfen Sie die Richtlinie mit einer App und stellen dann die App bereit. Die Richtlinieneinstellungen werden immer dann verwendet, wenn die Anwendung danach sucht (in der Regel beim ersten Ausführen).

> [!TIP]
> Dieser Richtlinientyp ist zurzeit nur für Geräte unter iOS 7.1 und höher verfügbar und unterstützt die folgenden App-Installationstypen:
> 
> -   **Verwaltete iOS-App aus dem App Store**
> -   **App-Paket für iOS**
> 
> Weitere Informationen zu app-Installationstypen finden Sie unter [Planen der Bereitstellung von Apps in Microsoft Intune](../Topic/plan-for-app-deployment-in-Microsoft-Intune.md).

## Konfigurieren einer Konfigurationsrichtlinie für mobile Apps

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com)auf **Richtlinie** &gt; **Übersicht** &gt; **Richtlinie hinzufügen**.

2.  Erweitern Sie in der Liste der Richtlinien den Eintrag **iOS**, klicken Sie auf **Mobile App-Konfiguration**, und klicken Sie dann auf **Richtlinie erstellen**.

    > [!TIP]
    > Sie können für diesen Richtlinientyp nur benutzerdefinierte Einstellungen konfigurieren. Empfohlene Einstellungen sind nicht verfügbar.

3.  Im Abschnitt **Allgemein** der Seite **Richtlinie erstellen** geben Sie einen Namen und eine optionale Beschreibung für die Konfigurationsrichtlinie für mobile Apps an.

4.  Geben oder fügen Sie im Abschnitt **Konfigurationsrichtlinie für mobile Apps** der Seite eine XML-Eigenschaftenliste mit den App-Konfigurationseinstellungen ein, die im Feld verwendet werden sollen.

    > [!TIP]
    > Weitere Informationen zu XML-Listen finden Sie unter [Grundlegendes zu XML-Eigenschaft listet](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) im iOS-Entwicklerbibliothek.
    > 
    > Das Format der XML-Eigenschaftenliste variiert je nach der App, die Sie konfigurieren. Wenden Sie sich an den Hersteller der App, um ausführliche Informationen über das genau zu verwendende Format zu erhalten.
    > 
    > Intune unterstützt die folgenden Datentypen in einer Eigenschaftenliste:
    > 
    > & Lt; Integer & Gt;
    > & Lt; Real & Gt;
    > &lt;Zeichenfolge&gt;
    > & Lt; Array & Gt;
    > & Lt; Dict & Gt;
    > & Lt; true / & Gt; oder & Lt; "false" / & Gt;
    > 
    > Weitere Informationen zu Datentypen finden Sie unter [About Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) in der iOS Developer Library.
    >
        > Darüber hinaus unterstützt Intune die folgenden Tokentypen in der Eigenschaftenliste:
    >    
    > \{\{userprincipalname\}\} - (Beispiel: **John@contoso.com**)
    > \{\{mail\}\} - (Beispiel: **John@contoso.com**)
    > \{\{partialupn\}\} - (Beispiel: **John**)
    > \{\{accountid\}\} - (Beispiel: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
    > \{\{deviceid\}\} - (Beispiel: **b9841cd9-9843-405f-be28-b2265c59ef97**)
    > \{\{userid\}\} - (Beispiel: **3ec2c00f-b125-4519-acf0-302ac3761822**)
    > \{\{username\}\} - (Beispiel: **John Doe**)
    > \{\{serialnumber\}\} - (Beispiel: **F4KN99ZUG5V2**) für iOS-Geräte
    > \{\{serialnumberlast4digits\}\} - (Beispiel: **G5V2**) für iOS-Geräte
>
> Die \ {\ {und \} \} Zeichen von nur Tokentypen verwendet werden und dürfen nicht für andere Zwecke verwendet werden.




5.  Klicken Sie auf **Überprüfen** um sicherzustellen, dass der eingegebene XML-Code einem gültigen Format für Eigenschaftenlisten entspricht.

    > [!IMPORTANT]
    > Beim Klicken auf **Validate**, Intune überprüft, ob der eingegebene XML-Code in einem gültigen Format ist. Es wird nicht überprüft, ob die XML-Eigenschaftenliste mit der App verwendet werden kann, der sie zugeordnet ist.

6.  Klicken Sie abschließend auf **Richtlinie speichern**.

Die neue Richtlinie wird im Knoten **Konfigurationsrichtlinien** angezeigt.

## Zuordnen einer Konfigurationsrichtlinie für mobile Apps zu einer App
Nachdem Sie eine Konfigurationsrichtlinie für mobile Apps erstellt haben, müssen Sie sie der iOS-App zuordnen, für die die Einstellungen in der Konfigurationsrichtlinie gelten sollen.

Führen Sie dazu die Schritte zum Erstellen einer app-Bereitstellung in [Bereitstellen von apps für mobile Geräte in Microsoft Intune](Deploy-apps-to-mobile-devices-in-Microsoft-Intune.md). Wenn Sie erreichen die **Mobile App-Konfiguration** Seite des Assistenten wählen Sie die Richtlinie, die Sie mit der app zuordnen möchten die **App-Konfigurationsrichtlinie** Dropdown-Liste.

Fahren Sie mit dem Bereitstellen und Überwachen der App-Bereitstellung wie gewohnt fort.

Wenn die bereitgestellte App auf einem Gerät gestartet wird, wird sie mit den Einstellungen ausgeführt, die Sie in der Konfigurationsrichtlinie für mobile Apps konfiguriert haben.

> [!TIP]
> Wenn eine oder mehrere Konfigurationsrichtlinien für mobile Anwendung in Konflikt stehen, weder Richtlinie wird erzwungen, und in der Intune-Verwaltungskonsole wird der Konflikt gemeldet **Dashboard**.

## Beispiel für das Format für die mobile Anwendung XML-Konfigurationsdatei

Wenn Sie eine mobile app-Konfigurationsdatei erstellen, können Sie eine oder mehrere der folgenden Werte mit diesem Format angeben:

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


### Siehe auch
[Bereitstellen und Konfigurieren von Apps mit Microsoft Intune](deploy-and-configure-apps-with-microsoft-intune.md)
[Bereitstellen von Apps für mobile Geräte in Microsoft Intune](deploy-apps-to-mobile-devices-in-microsoft-intune.md)



<!--HONumber=Mar16_HO4-->


