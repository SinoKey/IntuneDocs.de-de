---
title: Festlegen von Nutzungsbedingungen in Microsoft Intune
titleSuffix: Intune Azure preview
description: "Intune in Azure (Vorschau): Festlegen von Geschäftsbedingungen, die Benutzern im Unternehmensportal für Intune angezeigt werden "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 07a42cf8fa10d3223129fbb2932217ff90ac365b
ms.lasthandoff: 02/18/2017

---

# <a name="set-terms-and-conditions"></a>Festlegen von Geschäftsbedingungen 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Sie können Intune-Nutzungsbedingungen für Benutzergruppen bereitstellen, um zu erläutern, wie sich die Registrierung, der Zugriff auf Arbeitsressourcen und das Unternehmensportal auf Geräte und Benutzer auswirken. Benutzer müssen die Nutzungsbedingungen akzeptieren, bevor sie sich über das Unternehmensportal registrieren und auf ihre Arbeit zugreifen können.

Sie können mehrere Richtlinien erstellen und bereitstellen, die verschiedene Nutzungsbedingungen enthalten. Sie können auch Versionen derselben Nutzungsbedingungen in verschiedenen Sprachen erstellen und diese dann für die entsprechenden Gruppen bereitstellen.

**So erstellen Sie Geschäftsbedingungen**

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

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

