---
title: "Festlegen von Geschäftsbedingungen in Windows Intune | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Festlegen von Geschäftsbedingungen, die Benutzern im Unternehmensportal für Intune angezeigt werden "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: 694e5ac5eff0e2d39d44d992fe9dcc2262c112ce

---

# <a name="set-terms-and-conditions"></a>Festlegen von Geschäftsbedingungen 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Sie können Intune-Nutzungsbedingungen für Benutzergruppen bereitstellen, um zu erläutern, wie sich die Registrierung, der Zugriff auf Arbeitsressourcen und das Unternehmensportal auf Geräte und Benutzer auswirken. Benutzer müssen die Nutzungsbedingungen akzeptieren, bevor sie sich über das Unternehmensportal registrieren und auf ihre Arbeit zugreifen können.

Sie können mehrere Richtlinien erstellen und bereitstellen, die verschiedene Nutzungsbedingungen enthalten. Sie können auch Versionen derselben Nutzungsbedingungen in verschiedenen Sprachen erstellen und diese dann für die entsprechenden Gruppen bereitstellen.

**So erstellen Sie Geschäftsbedingungen**

1. Wählen Sie im Azure-Portal **Weitere Dienste** aus, geben Sie **Intune** in das Textfeld ein, und wählen Sie dann **Andere** > **Intune** aus.

2. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Nutzungsbedingungen** aus.

3. Wählen Sie **Erstellen** aus.

4. Geben Sie auf dem Blatt **Geschäftsbedingungen erstellen** die folgenden Informationen an:

   - **Anzeigename:** Name für die Geschäftsbedingungen. Dieser Name wird Benutzern in der Unternehmensportal-App angezeigt.

   - **Beschreibung:** Optionale Details, die Ihnen dabei helfen, die Richtlinie im Azure-Portal zu identifizieren.

5. Wählen Sie den Pfeil neben „Nutzungsbedingungen definieren“ aus, um das Blatt „Nutzungsbedingungen“ zu öffnen, und geben Sie dann die folgende Informationen ein:

   - **Titel:** Der Titel, der Benutzern im Unternehmensportal angezeigt wird.

   - **Zusammenfassung der Nutzungsbedingungen:** Text, aus dem hervorgeht, welche Folgen die Annahme der Bedingungen für den Benutzer hat.

   - **Nutzungsbedingungen:** Die rechtliche Bezeichnung, die Benutzern angezeigt wird und die sie annehmen oder ablehnen müssen, z.B. „Ich stimme den Geschäftsbedingungen zu“.

6. Wählen Sie **OK** aus.



<!--HONumber=Feb17_HO1-->


