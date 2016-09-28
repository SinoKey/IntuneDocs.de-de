---
title: "Verwenden von Konfigurationsrichtlinien für mobile iOS-Apps | Microsoft Intune"
description: "Verwenden Sie Konfigurationsrichtlinien für mobile Apps in Intune, um Einstellungen anzugeben, die beim Ausführen einer iOS-App durch Benutzer erforderlich sind."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 360865bcd97230e264ee3439407e8dd3017d0055
ms.openlocfilehash: 1f239270c26a70b161e52c24e94ca5c2cae9ca3a


---

# Konfigurieren von iOS-Apps mit Konfigurationsrichtlinien für mobile Apps in Microsoft Intune
Verwenden Sie Konfigurationsrichtlinien für mobile Apps in Microsoft Intune, um Einstellungen anzugeben, die beim Ausführen einer App durch Benutzer erforderlich sind. Beispielsweise kann eine App vom Benutzer Folgendes anfordern:

-   Eine benutzerdefinierte Portnummer

-   Spracheinstellungen

-   Sicherheitseinstellungen

-   Brandingeinstellungen, z. B. ein Unternehmenslogo

Wenn Benutzer diese Einstellungen nicht ordnungsgemäß eingeben, kann dies zur erhöhten Belastung Ihres Helpdesks führen und die Annahme der neuen Apps verlangsamen.

Mit Konfigurationsrichtlinien für mobile Apps können Sie diese Probleme beseitigen, da Sie diese Einstellungen für Benutzer in einer Richtlinie bereitstellen können, bevor die Benutzer die App ausführen. Die Einstellungen werden dann automatisch bereitgestellt, und die Benutzer müssen keine weitere Aktion durchführen.

Sie stellen diese Richtlinien nicht direkt für Benutzer und Geräte bereit. Stattdessen verknüpfen Sie eine Richtlinie mit einer App und stellen dann die App bereit. Die Richtlinieneinstellungen werden immer dann verwendet, wenn die Anwendung danach sucht (in der Regel beim ersten Ausführen).

> [!TIP]
> Dieser Richtlinientyp ist zurzeit nur für Geräte unter iOS 8.0 und höher verfügbar. Er unterstützt die folgenden App-Installationstypen:
>
> -   **Verwaltete iOS-App aus dem App Store**
> -   **App-Paket für iOS**
>
> Weitere Informationen zu Installationstypen von Apps finden Sie unter [Bereitstellen von Apps mit Microsoft Intune](deploy-apps.md).

## Konfigurieren einer Konfigurationsrichtlinie für mobile Apps

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Optionen **Richtlinie** &gt; **Übersicht** &gt; **Richtlinie hinzufügen**.

2.  Erweitern Sie in der Liste der Richtlinien den Eintrag **iOS**, wählen Sie **Mobile App-Konfiguration** und dann **Richtlinie erstellen** aus.

    > [!TIP]
    > Sie können für diesen Richtlinientyp nur benutzerdefinierte Einstellungen konfigurieren. Empfohlene Einstellungen sind nicht verfügbar.

3.  Im Abschnitt **Allgemein** der Seite **Richtlinie erstellen** geben Sie einen Namen und eine optionale Beschreibung für die Konfigurationsrichtlinie für mobile Apps an.

4.  Geben oder fügen Sie im Abschnitt **Konfigurationsrichtlinie für mobile Apps** der Seite eine XML-Eigenschaftenliste mit den App-Konfigurationseinstellungen in das Feld ein, die verwendet werden sollen. Das Format der XML-Eigenschaftenliste variiert je nach der App, die Sie konfigurieren. Wenden Sie sich an den Hersteller der App, um ausführliche Informationen über das genau zu verwendende Format zu erhalten.

    > [!TIP]
    > Weitere Informationen zu XML-Eigenschaftenlisten finden Sie unter [Understanding XML Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) in der iOS Developer Library.

5.  Klicken Sie auf **Überprüfen** um sicherzustellen, dass der eingegebene XML-Code einem gültigen Format für Eigenschaftenlisten entspricht.

    > [!IMPORTANT]
    > Beim Klicken auf **Überprüfen** prüft Intune, ob der von Ihnen eingegebene XML-Code in einem gültigen Format vorliegt. Es wird nicht überprüft, ob die XML-Eigenschaftenliste mit der App verwendet werden kann, der sie zugeordnet ist.

6.  Klicken Sie abschließend auf **Richtlinie speichern**.

Die neue Richtlinie wird im Knoten **Konfigurationsrichtlinien** angezeigt.

## Informationen zum XML-Dateiformat

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

## Zuordnen einer Konfigurationsrichtlinie für mobile Apps zu einer App
Nachdem Sie eine Konfigurationsrichtlinie für mobile Apps erstellt haben, müssen Sie sie der iOS-App zuordnen, für die die Einstellungen in der Konfigurationsrichtlinie gelten sollen.

Führen Sie dazu die Schritte zum Erstellen einer App-Bereitstellung in [Hinzufügen von Apps für mobile Geräte in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) und [Bereitstellen von Apps mit Microsoft Intune](deploy-apps-in-microsoft-intune.md) aus. Wenn Sie die Seite **Mobile App-Konfiguration** des Assistenten erreichen, wählen Sie in der Dropdownliste **App-Konfigurationsrichtlinie** die Richtlinie aus, die Sie der App zuordnen möchten.

Fahren Sie mit dem Bereitstellen und Überwachen der App-Bereitstellung wie gewohnt fort.

Wenn die bereitgestellte App auf einem Gerät gestartet wird, wird sie mit den Einstellungen ausgeführt, die Sie in der Konfigurationsrichtlinie für mobile Apps konfiguriert haben.

> [!TIP]
> Wenn mindestens eine Konfigurationsrichtlinie für mobile Apps einen Konflikt verursacht, wird keine Richtlinie durchgesetzt. Der Konflikt wird im **Dashboard ** der Intune-Verwaltungskonsole gemeldet.

## Beispielformat für die XML-Datei für die Konfiguration mobiler Apps

Wenn Sie eine Datei für die Konfiguration mobiler Apps erstellen, können Sie einen oder mehrere der folgenden Werte mit diesem Format angeben:

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



<!--HONumber=Sep16_HO3-->


