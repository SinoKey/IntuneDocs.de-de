---
title: "Verwenden von Gerätekategorien in Intune | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie Gerätekategorien verwenden, die Benutzer auswählen können, wenn sie ihre Geräte in Intune registrieren."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1609ed2f127fe9d7d1f1c3b3e923bd12f1088200
ms.openlocfilehash: 41b3cfb8006a7390094d01b4f0fdc38417e858be


---

# <a name="map-device-groups"></a>Zuordnen von Gerätegruppen


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Verwenden Sie die Gerätekategorien in Microsoft Intune, damit Geräte basierend auf Kategorien, die Sie definieren, automatisch Gruppen hinzugefügt werden, sodass Sie diese Geräte einfacher verwalten können.

Gerätekategorien verwenden den folgenden Workflow:
1.    Erstellen Sie Kategorien, die Benutzer beim Registrieren ihrer Geräte verwenden können.
4.    Wenn Endbenutzer ihre Geräte registrieren, müssen sie eine Kategorie aus der Liste mit den von Ihnen konfigurierten Kategorien auswählen. Wenn ein Gerät bereits registriert ist, wird der Benutzer beim nächsten Aufruf der Unternehmensportal-App aufgefordert, eine Kategorie auszuwählen.


Sie können beliebige Gerätekategorien erstellen, z.B.:
- POS-Gerät (Point of Sale)
- Demogerät
- Sales
- Kontoführung
- Manager

## <a name="how-to-configure-device-categories"></a>Konfigurieren von Gerätekategorien

### <a name="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal"></a>Schritt 1: Erstellen von Gerätekategorien auf dem Blatt „Intune“ im Azure-Portal
1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Andere** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte registrieren** aus.
3. Wählen Sie auf dem Blatt **Registrierung** die Option **Gerätekategorien** aus.
4. Wählen Sie auf der Seite **Gerätekategorien** die Option **Erstellen** aus, um eine neue Kategorie hinzuzufügen.
5. Geben Sie auf dem nächsten Blatt einen **Namen** für die neue Kategorie und optional eine **Beschreibung** ein.
6. Klicken Sie auf **Erstellen**, wenn Sie fertig sind. Die gerade von Ihnen erstellte Kategorie wird in der Liste der Kategorien angezeigt.

Verwenden Sie den Kategorienamen des Geräts zum Erstellen von Azure Active Directory-Sicherheitsgruppen in Schritt 2.

### <a name="step-2---create-azure-active-directory-security-groups"></a>Schritt 2: Erstellen von Active Directory-Sicherheitsgruppen
In diesem Schritt erstellen Sie dynamische Gruppen im Azure-Portal auf Basis der Gerätekategorie und des Gerätekategorienamens.

Lesen Sie das Thema [Verwenden von Attributen zum Erstellen erweiterter Regeln](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) in der Dokumentation zu Azure Active Directory, um den Vorgang fortzusetzen. 

Verwenden Sie die Informationen in diesem Abschnitt zum Erstellen einer Gerätegruppe mit einer erweiterten Regel mithilfe des Attributs **deviceCategory**. Beispiel: (**device.deviceCategory -eq** "*<the device category name you got from the Intune portal>*")

Wenn nach dem Konfigurieren von Gerätegruppen Benutzer ihre Geräte registrieren, wird ihnen eine Liste der von Ihnen konfigurierten Kategorien angezeigt. Nachdem sie eine Kategorie ausgewählt und die Registrierung abgeschlossen haben, wird ihr Gerät der Active Directory-Sicherheitsgruppe hinzugefügt, die der gewählten Kategorie entspricht.

### <a name="how-to-view-the-categories-of-devices-you-manage"></a>Anzeigen der Kategorien von Geräten, die Sie verwalten
1.    Wählen Sie im Azure-Portal auf dem Blatt „Intune“ die Option **Geräte und Gruppen** aus.

2.    Klicken Sie unter **Verwalten** auf **Alle Geräte**.

3.    Sehen Sie sich in der Liste der Geräte die Spalte **Kategorie** an.

Wenn die Spalte **Kategorie** nicht angezeigt wird, klicken Sie auf **Spalten**, wählen Sie in der Liste **Kategorie** aus, und klicken Sie dann auf **Anwenden**.

### <a name="to-change-the-category-of-a-device"></a>So ändern Sie die Kategorie eines Geräts

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Andere** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte & Gruppen** aus.
4. Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Verwalten** > **Alle Geräte** aus.
5. Wählen Sie in der Liste der Geräte das gewünschte Gerät und anschließend auf dem Blatt mit den Geräteeigenschaften **Verwalten** > **Eigenschaften** aus.
6. Auf dem nächsten Blatt können Sie die **Gerätekategorie** des ausgewählten Geräts in einen beliebigen Kategorienamen ändern, den Sie zuvor konfiguriert haben.



## <a name="further-information"></a>Weitere Informationen
- Sie können eine Gerätekategorie im Azure-Portal bearbeiten. Sie müssen dann aber manuell alle Azure Active Directory-Sicherheitsgruppen aktualisieren, die auf diese Kategorie verweisen.

- Wenn Sie eine Kategorie löschen, tragen alle Geräte, die dieser zuvor zugewiesen waren, anschließend den Kategorienamen **Nicht zugewiesen**.





<!--HONumber=Feb17_HO2-->


