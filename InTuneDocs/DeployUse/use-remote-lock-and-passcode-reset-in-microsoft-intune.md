---
title: Verwenden der Remotesperre und Zurücksetzen der Kennung | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 970f8c81-7c7f-4789-9ed4-2133d50b9db6

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: [ALIAS]
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:
---
# Geräteschutz durch Remotesperre und Zurücksetzen der Kennung
Microsoft Intune enthält Funktionen zum Remotesperren und zum Zurücksetzen der Kennung.

## Remotesperrung eines Geräts
Wenn ein Benutzer sein Gerät verliert, können Sie es remote sperren. In der folgenden Tabelle ist die Funktionsweise der Remotesperrung auf verschiedenen mobilen Plattformen aufgeführt.

|Plattform|Remotesperre|
|------------|---------------|
|iOS|Unterstützt|
|Android|Unterstützt|
|Windows 10 Mobile|Unterstützt|
|Windows Phone 8 und Windows Phone 8.1|Unterstützt|
|Windows RT 8.1 und Windows RT|Unterstützt, wenn der aktuelle Benutzer des Geräts derjenige ist, der das Gerät registriert hat.|
|Windows 8.1|Unterstützt, wenn der aktuelle Benutzer des Geräts derjenige ist, der das Gerät registriert hat.|


### So sperren Sie ein mobiles Gerät remote über die Intune-Konsole

1.  Klicken Sie in der [Intune-Administratorkonsole](https://manage.microsoft.com/) auf **Gruppen** &gt; **Alle Geräte** &gt; **Alle mobilen Geräte**..

2.  Klicken Sie bei Geräten, die bei Intune registriert sind, auf **Alle direkt verwalteten Geräte**. Andernfalls klicken Sie auf **Alle mit Exchange ActiveSync verwalteten Geräte**..

    > [!TIP]
    > Sie können auch nach Benutzer zu einem Gerät navigieren. Klicken Sie auf **Alle Benutzer**. Klicken Sie auf der Eigenschaftenseite des Benutzers auf **Geräte** und dann auf den Namen des mobilen Geräts, das Sie zurücksetzen möchten.

3.  Wählen Sie in der Liste die Geräte aus, die Sie sperren möchten. Klicken Sie auf der Taskleiste auf **Remoteaufgaben**, und wählen Sie **Remotesperre** aus..

## Zurücksetzen der Kennung auf einem Gerät
Wenn ein Benutzer seine Kennung vergisst, können Sie die Kennung von einem Gerät entfernen oder eine neue temporäre Kennung auf einem Gerät erzwingen. In der folgenden Tabelle ist die Funktionsweise der Kennungszurücksetzung auf verschiedenen mobilen Plattformen aufgeführt.

|Plattform|Zurücksetzen der Kennung|
|------------|------------------|
|iOS|Wird für das Löschen der Kennung von einem Gerät unterstützt. Es wird keine neue temporäre Kennung erstellt.|
|Android|Wird unterstützt. Zudem wird eine temporäre Kennung erstellt.|
|Windows 10 Mobile|Unterstützt|
|Windows Phone 8 und Windows Phone 8.1|Unterstützt|
|Windows RT 8.1 und Windows RT|Nicht unterstützt|
|Windows 8.1|Nicht unterstützt|

### So setzen Sie eine Kennung zurück

1.  Klicken Sie in der [Intune-Administratorkonsole](https://manage.microsoft.com/) auf **Gruppen** &gt; **Alle Geräte** &gt; **Alle mobilen Geräte**..

2.  Klicken Sie bei Geräten, die bei Intune registriert sind, auf **Alle direkt verwalteten Geräte**. Andernfalls klicken Sie auf **Alle mit Exchange ActiveSync verwalteten Geräte**..

    > [!TIP]
    > Sie können auch nach Benutzer zu einem Gerät navigieren. Klicken Sie auf **Alle Benutzer**. Klicken Sie auf der Eigenschaftenseite des Benutzers auf **Geräte** und dann auf den Namen des mobilen Geräts, das Sie zurücksetzen möchten.

3.  Wählen Sie in der Liste die Geräte aus, die Sie sperren möchten. Klicken Sie auf der Taskleiste auf **Remoteaufgaben**, und wählen Sie **Kennungsrückstellung** aus..


### Weitere Informationen:
[Abkoppeln von Geräten](retire-devices-from-microsoft-intune-management.md)
[Windows Selective Wipe for Device Data Management (Selektives Zurücksetzen bei der Gerätedatenverwaltung in Windows)](http://technet.microsoft.com/library/dn486874.aspx)


<!--HONumber=May16_HO1-->


