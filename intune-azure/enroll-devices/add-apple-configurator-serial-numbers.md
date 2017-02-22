---
title: "Hinzufügen von Apple Configurator-Seriennummern | Intune in Azure (Vorschau) | Microsoft Docs"
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie unternehmenseigenen iOS-Geräten mit Apple Configurator Seriennummern hinzufügen."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/03/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d408aa38-7d1e-40df-9067-246e53f6e26f
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 65a6b2e22359bdcb9b0c15a84c6b3586dafe4d6c
ms.openlocfilehash: 71d29a245f8f900a7427528167bae0b52565d42b


---

# <a name="add-apple-configurator-serial-numbers"></a>Hinzufügen von Apple Configurator-Seriennummern 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Wenden Sie diese Schritte an, um in Intune Seriennummern für das [Registrieren unternehmenseigener iOS-Geräte mit Apple Configurator mit Setup-Assistent]((enroll-ios-devices-with-apple-configurator-and-setup-assistant.md) hinzuzufügen. Sie können Seriennummern einzeln hinzufügen oder eine mit Trennzeichen getrennte CSV-Datei mit Seriennummern hochladen. Nachdem Sie Seriennummern hinzugefügt haben, können Sie ihnen ein Profil zuweisen. Das Profil enthält die spezifischen Verwaltungseinstellungen, die Sie auf Geräte anwenden möchten. 

Andere Methoden zum Registrieren von iOS-Geräten werden in [Auswählen der Registrierung von iOS-Geräten in Intune](choose-ios-enrollment-method.md) beschriebenen.

**So fügen Sie Apple Configurator-Seriennummern in Intune hinzu**

1. Erstellen Sie eine Liste mit zwei Spalten, die durch Trennzeichen getrennte werden (CSV), und ohne Header. Fügen Sie den IMEI-Bezeichner in der linken Spalte und die Details in der rechten Spalte hinzu. Der aktuelle Höchstwert für die Liste ist 500 Zeilen. In einem Text-Editor sieht die CSV-Liste etwa wie folgt aus:

    F7TLWCLBX196,Gerätedetails</br>
    DLXQPCWVGHMJ,Gerätedetails

2. Wählen Sie im Azure-Portal **Weitere Dienste** aus, geben Sie **Intune** in das Textfeld ein, und wählen Sie dann **Andere** > **Intune** aus.

3.  Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Apple-Registrierung** aus.

4. Wählen Sie unter **Apple Configurator-Registrierungseinstellungen verwalten** die Option **Apple Configurator-Seriennummern** aus.

5. Wählen Sie auf dem Blatt **Apple Configurator-Seriennummern** die Option **Hinzufügen** aus.

6. Wählen Sie auf dem Blatt **Seriennummern hinzufügen** ein Profil aus, das Sie auf die importierten Seriennummern anwenden möchten. Wenn Sie eine Datei mit den neuen Daten importieren, werden die bereits vorhandenen überschrieben. Wählen Sie „Hiermit überschreiben Sie Details für vorhandene Bezeichner“ aus, um die vorhandenen Bezeichner durch die neuen zu ersetzen.

7. Navigieren Sie zu der CSV-Datei mit den Seriennummern, und wählen Sie **Hinzufügen** aus.

## <a name="assign-a-profile-to-specific-serial-numbers"></a>Zuweisen eines Profils zu bestimmten Seriennummern

Mit Intune können Sie Profile von zwei verschiedenen Stellen im Azure-Portal zuweisen. Sie können anhand der folgenden Schritte vorgehen, oder Sie können Profilen vom Blatt „Apple Configurator-Registrierungsprofile“ zuweisen, auf dem Sie das Profil erstellt haben (siehe [Registrieren von iOS-Geräten mithilfe von Apple Configurator und Setup-Assistent](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md)). Anhand der folgenden Schritte können Sie das Profil nur zuweisen, wenn Sie es bereits erstellt haben.

1. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Apple-Registrierung** aus.

2. Wählen Sie auf dem Blatt **Apple Configurator-Seriennummern** die Seriennummern aus, denen Sie ein Profil zuweisen möchten, und wählen Sie dann **Profil zuweisen** aus.

3. Wählen Sie auf dem Blatt **Profil zuweisen** das Profil, das Sie zuweisen möchten, und dann **Zuweisen** aus.

## <a name="delete-serial-numbers"></a>Löschen von Seriennummern
Sie können Seriennummern löschen, die Sie zuvor importiert haben. Sie können Seriennummern nur dann löschen, wenn zunächst die Registrierung des Geräts aufgehoben wurde. Wenn Sie eine Seriennummer entfernen, können nicht Sie Apple Configurator nur dann über den Setup-Assistenten verwenden, wenn Sie die Seriennummer erneut hinzufügen.

## <a name="view-the-state-of-a-device"></a>Anzeigen des Status von Geräten
Die Seriennummern des Geräts kann einen von zwei Status aufweisen:

- Registriert – Das Gerät ist registriert, und es ist mit dem Intune-Dienst verbunden.
- Nicht kontaktiert – Das Gerät wurde nie mit dem Intune-Dienst verbunden.
- Zurücksetzen ausstehend – Das Gerät ist registriert, aber es wurde eine Änderung vorgenommen (z.B. an den Registrierungseinstellungen oder am angewendeten DEP-Profil). Wenn Sie das DEP-Profil eines Geräts ändern, werden die Änderungen erst übernommen, wenn die Registrierung des Geräts aufgehoben und es erneut registriert wurde.

**So zeigen Sie den Status einer Seriennummer an**

Wählen Sie auf dem Blatt **Apple Configurator-Seriennummern** die Seriennummer aus, deren Status Sie anzeigen möchten, und sehen Sie unter dem Element **Zustand** nach.



<!--HONumber=Feb17_HO1-->


