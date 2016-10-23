---
title: Migrieren zu Azure Active Directory-Gruppen | Microsoft Intune
description: So werden Ihre Gruppen von Intune zu Azure AD migriert
keywords: 
author: nbigman
manager: angerobe
ms.date: 10/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 03b69afa-3548-4033-9039-191528f3fd99
translationtype: Human Translation
ms.sourcegitcommit: d92c9ffe42b36770a32c28941de3c402aec9dd68
ms.openlocfilehash: 08bcc258f64e6385ae6fa648ddb8f2b5fe68942e


---

## Die neue Administratoroberfläche für Gruppen
    
Um Ihren Wünschen nach einer einheitlichen Oberfläche für Gruppierung und Adressierung in Enterprise Mobility + Security gerecht zu werden, konvertieren wir Intune-Gruppen in Azure Active Directory-basierte Sicherheitsgruppen. Dies vereinheitlicht die Gruppenverwaltung in Intune und Azure Active Directory (Azure AD). Durch die neue Benutzeroberfläche müssen Sie keine Gruppen zwischen Diensten duplizieren, und es wird eine Erweiterung unter Verwendung von PowerShell und Graph bereitgestellt. 

### Wie und wann werde ich zur neuen Gruppenoberfläche migrieren?
Aktuelle Kunden werden innerhalb eines Zeitraums migriert, der nicht vor Dezember 2016 beginnt. Bevor Ihre Gruppen migriert werden, erhalten Sie eine Benachrichtigung. Kontaktieren Sie unser Migrationsteam unter [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com), wenn Sie Probleme mit der Migration haben.

### Welche neuen Funktionen sind für mich verfügbar?
Hier werden die neuen Funktionen erklärt: 
 
-    Azure AD-Sicherheitsgruppen werden in Intune für alle Bereitstellungsarten unterstützt. 
-    Azure AD-Sicherheitsgruppen unterstützen das Gruppieren von Geräten und Benutzern.
-    Azure AD-Sicherheitsgruppen unterstützen dynamische Gruppen mit Intune-Geräteattributen. Sie können beispielsweise Geräte basierend auf einer Plattform dynamisch gruppieren, z.B. iOS. Wenn ein neues iOS-Gerät in Ihrer Organisation registriert wird, wird es auf diese Weise automatisch der dynamischen iOS-Gerätegruppe hinzugefügt.
-    Gemeinsam genutzte Administratoroberflächen für Gruppenverwaltung in Azure AD und Intune.
- Die Rolle *Intune-Dienstadministrator* wird Azure AD hinzugefügt, um Dienstadministratoren in Intune die Ausführung von Gruppenverwaltungstasks in Azure AD zu erlauben.

 
### Welche Intune-Funktion wird nicht verfügbar sein?
Obwohl sich die Gruppenoberfläche verbessern wird, gibt es einige Intune-Funktionen, die nach der Migration nicht verfügbar sein werden.

#### Gruppenverwaltungsfunktion

-   Sie können keine Mitglieder oder Gruppen mehr ausschließen, wenn Sie eine neue Gruppe erstellen. Dynamische Azure AD-Gruppen ermöglichen Ihnen jedoch die Verwendung von Attributen zum Erstellen von erweiterten Regeln, um Mitglieder basierend auf Kriterien auszuschließen. So könnten Sie beispielsweise die erweiterte Regel `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")` erstellen, die alle Mitarbeiter der Abteilung „Vertrieb“ in einer Sicherheitsgruppe enthält, mit Ausnahme der Personen, deren Position das Wort „Assistent“ aufweist. Weitere Informationen finden Sie unter [Verwenden von Attributen zum Erstellen erweiterter Regeln](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
-   Für die Gruppen **Nicht gruppierte Benutzer** und **Nicht gruppierte Geräte** wird es keinen Support geben. Diese Gruppen werden nicht migriert.

#### Gruppenabhängige Funktionen

-   Die Serviceadministratorrolle wird über keine **Verwalten von Gruppen**-Berechtigungen verfügen.
-   Sie können keine Exchange ActiveSync-Geräte gruppieren.  Ihre Gruppe **Alle von EAS verwalteten Geräte** wird von einer Gruppe in eine Berichtsansicht konvertiert.
-  Pivotieren mit Gruppen in Berichten ist nicht verfügbar.
-  Adressierung benutzerdefinierter Zielgruppen mithilfe von Benachrichtigungsregeln ist nicht verfügbar.

### Wie sollte ich mich für die Änderung vorbereiten?
 Wir haben Empfehlungen für Sie, die Ihnen diese Umstellung vereinfachen:
 
- Bereinigen Sie alle unerwünschten oder nicht benötigten Intune-Gruppen vor der Migration.
- Bewerten Sie die Verwendung des Ausschlusses in Gruppen, und überlegen Sie, wie Sie Ihre Gruppen so umgestalten können, dass kein Ausschluss verwendet werden muss oder Sie erweiterte Regeln verwenden können, um das gleiche Ziel zu erreichen.
-  Wenn Sie Administratoren haben, die über keine Berechtigung verfügen, Gruppen in Azure AD zu erstellen, fragen Sie Ihren Azure AD-Administrator, ob er diese zur Azure AD-Rolle **Intune-Dienstadministrator** hinzufügen kann.

Sie können sich auch genauer über Azure AD-Sicherheitsgruppen informieren:
-  Eine Übersicht finden Sie unter [Verwalten des Zugriffs auf Ressourcen mit Azure Active Directory-Gruppen](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/).
-  Informationen zum Erstellen und Verwalten von Azure AD-Gruppen finden Sie unter [Verwalten von Gruppen in Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/).
-  Weitere Informationen zu erweiterten Regeln für Sicherheitsgruppen finden Sie unter [Verwenden von Attributen zum Erstellen erweiterter Regeln](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).

> [!NOTE]
Die Erstellung von Gruppen für Geräte wird in der Dokumentation zu Azure AD-Sicherheitsgruppen nicht behandelt. Diese Funktionalität wird in Azure AD vor dem Beginn der Intune-Gruppenmigration aktiviert.

## Einzelheiten zur Migration
Nachfolgend finden Sie Einzelheiten darüber, wie Ihre Intune-Gruppen zu Azure AD-Sicherheitsgruppen migriert werden.

### Migration vorhandener Gruppen

| Intune-Gruppe wird ...|... Azure AD-Sicherheitsgruppe|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Statische Benutzergruppen, die unter Intune-Richtlinien fallen|Statische Azure AD-Sicherheitsgruppen, die dieselben Benutzer enthalten|
|Dynamische Benutzergruppen, die unter Intune-Richtlinien fallen|Statische Azure AD-Sicherheitsgruppen mit einer Hierarchie von Azure AD-Sicherheitsgruppen|
|Statische Gerätegruppen, die unter Intune-Richtlinien fallen|Statische Azure AD-Sicherheitsgruppen mit Geräten|
|Dynamische Gerätegruppen mit Geräteattributen, die unter Intune-Richtlinien fallen|Dynamische Azure AD-Sicherheitsgruppen mit Geräteattributen|
|Eine Gruppe mit einer Einschlussbedingung|Eine separate statische Azure AD-Sicherheitsgruppe, die eine Gruppe sowie alle statischen/dynamischen Mitglieder enthält, die die Einschlussbedingung in Intune zugelassen hat|
|Eine Gruppe mit einer Ausschlussbedingung|... wird nicht migriert. Ausschlussbedingungen werden bei der Erstellung von statischen Gruppen in Azure AD nicht unterstützt. Eine Ausschlussbedingung kann beim Erstellen einer dynamischen Gruppe in Azure AD verwendet werden.|
|Die Standardgruppen **Alle Benutzer**, **Nicht gruppierte Benutzer**, **Alle Geräte**, **Nicht gruppierte Geräte**, **Alle Computer**, **Alle mobilen Geräte**, **Alle MDM-verwalteten Geräte** und **Alle EAS-verwalteten Geräte**, die Sie in Intune-Richtlinien verwenden  |Azure AD-Sicherheitsgruppen. Standardgruppen, die nicht verwendet werden, müssten bei Bedarf vom Kunden mithilfe von dynamischen Gruppen erstellt werden.|

### Änderungen in hierarchischen Ansichten
Eine hierarchische Ansicht für Gruppen in Intune. Die hierarchische Beziehung in Intune war eine Obermengen-Teilmengen-Beziehung, während das in Azure AD nicht der Fall ist. Das untergeordnete Element kann über Elemente verfügen, die das übergeordnete Element nicht enthält. In Azure AD können Gruppen auch zyklisch sein. Eine übergeordnete Gruppe kann das untergeordnete Element einer untergeordneten Gruppe sein.

### Attributkonvertierung während der Migration
Attribute sind Geräteeigenschaften, die bei der Definition von Gruppen verwendet werden können. In der folgenden Tabelle wird beschrieben, wie diese Kriterien zu Azure AD-Sicherheitsgruppen migriert werden.

| Intune-Attribut|Azure AD-Attribut|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|OE-Attribut (Organisationseinheit) für Gerätegruppen|OE-Attribut für dynamische Gruppen. Attributwerte, die dem Administrator für die einzelnen Mandanten zur Verfügung gestellt werden, indem sie als Mandantenkomponenten für die Anzeige hinzugefügt werden.|
|Domänennamenattribut für Gerätegruppen|Domänennamenattribut für dynamische Gruppen. Attributwerte, die dem Administrator für die einzelnen Mandanten zur Verfügung gestellt werden, indem sie als Mandantenkomponenten für die Anzeige hinzugefügt werden|
|Sicherheitsgruppe als Attribut für Benutzergruppen|In dynamischen Azure AD-Abfragen können Gruppen nicht als Attribute verwendet werden. Dynamische Gruppen dürfen nur benutzer- oder gerätespezifische Attribute enthalten.|
|Manager-Attribut für Benutzergruppen|Erweiterte Regel für das *Manager*-Attribut in dynamischen Gruppen|
|Alle Benutzer der übergeordneten Benutzergruppe|Statische Gruppe, die diese Gruppe als Mitglied enthält|
|Alle mobilen Geräte der übergeordneten Gerätegruppe|Statische Gruppe, die diese Gruppe als Mitglied enthält|
|Alle von der Microsoft Intune-Direktverwaltung verwalteten mobilen Geräte|Verwaltungstypattribut mit dem Wert „MDM“ für dynamische Gruppen|
|Alle von EAS verwalteten mobilen Geräte|In Azure AD können EAS-Geräte nicht gruppiert werden. Ihre Gruppe **Alle von EAS verwalteten Geräte** wird von einer Gruppe in eine Berichtsansicht konvertiert.|
|Verschachtelte Gruppen in statischen Gruppen |Verschachtelte Gruppen in statischen Gruppen|
|Verschachtelte Gruppen in dynamischen Gruppen|Dynamische Gruppe mit einer Schachtelungsebene|


## Migration von Richtlinien
Während die Gruppenmigration ausgeführt wird, können Sie Ihre Richtlinien weiterhin in der Intune-Konsole verwalten. Die Intune-Konsole enthält eine Verknüpfung zu Ihrer Azure-Verwaltungskonsole, in der Sie Ihre Gruppen verwalten. Ihre Richtlinien werden weiterhin für die migrierten Azure AD-Sicherheitsgruppen bereitgestellt, die Ihren alten Intune-Gruppen entsprechen.

Wenn alle Intune Funktionen zum Azure-Verwaltungsportal (im ersten Quartal 2017) migriert wurden, können Sie Richtlinien und Gruppen dort verwalten.

     
### Weitere Informationen:
[Verwalten des Zugriffs auf Ressourcen mit Azure Active Directory-Gruppen](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/)

[Verwalten von Gruppen in Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/)

[Verwenden von Attributen zum Erstellen erweiterter Regeln](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/)



<!--HONumber=Oct16_HO2-->


