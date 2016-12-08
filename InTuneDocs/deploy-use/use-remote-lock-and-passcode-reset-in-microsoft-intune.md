---
title: "Remotesperre und Zurücksetzen der Kennung | Microsoft Intune"
description: "Intune enthält Funktionen zum Remotesperren und zum Zurücksetzen der Kennung."
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 11/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 970f8c81-7c7f-4789-9ed4-2133d50b9db6
ms.reviewer: chrisgre
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 8dc7f1c7eb32828854b4e2309c915f4fd0cba9a2

---
# <a name="help-protect-your-devices-with-remote-lock-and-passcode-reset"></a>Geräteschutz durch Remotesperre und Zurücksetzen der Kennung
Microsoft Intune enthält Funktionen zum Remotesperren und zum Zurücksetzen der Kennung.

## <a name="lock-a-device-remotely"></a>Remotesperrung eines Geräts
Wenn ein Benutzer sein Gerät verliert, können Sie es remote sperren. In der folgenden Tabelle ist die Funktionsweise der Remotesperrung auf verschiedenen mobilen Plattformen aufgeführt.

|Plattform|Remotesperre|
|------------|---------------|
|macOS|Nicht unterstützt|
|iOS|Unterstützt|
|Android|Unterstützt|
|Windows 10 und Windows 10 Mobile|Unterstützt|
|Windows Phone 8 und Windows Phone 8.1|Unterstützt|
|Windows RT 8.1 und Windows RT|Unterstützt, wenn der aktuelle Benutzer des Geräts derjenige ist, der das Gerät registriert hat.|
|Windows 8.1|Unterstützt, wenn der aktuelle Benutzer des Geräts derjenige ist, der das Gerät registriert hat.|

Die Remotesperre wird für Windows-PCs, die mit dem Intune-Softwareclient registriert wurden, nicht unterstützt.

### <a name="lock-a-mobile-device-remotely-through-the-intune-console"></a>Sperren eines mobilen Geräts remote über die Intune-Konsole

1.  Wählen Sie in der [Intune-Verwaltungskonsole](https://manage.microsoft.com/) **Gruppen** &gt; **Alle Geräte** &gt; **Alle mobilen Geräte** aus.

2.  Wählen Sie bei Geräten, die bei Intune registriert sind, **Alle direkt verwalteten Geräte** aus. Andernfalls wählen Sie **Alle mit Exchange ActiveSync verwalteten Geräte** aus.

    > [!TIP]
    > Sie können auch nach Benutzer zu einem Gerät navigieren. Klicken Sie auf **Alle Benutzer**. Klicken Sie auf der Eigenschaftenseite des Benutzers auf **Geräte** und dann auf den Namen des mobilen Geräts, das Sie sperren möchten.

3.  Wählen Sie in der Liste die Geräte aus, die Sie sperren möchten. Wählen Sie auf der Taskleiste **Remoteaufgaben** und **Remotesperre** aus.

## <a name="reset-the-passcode-on-a-device"></a>Zurücksetzen der Kennung auf einem Gerät
Wenn ein Benutzer eine Kennung vergisst, können Sie ihm helfen, indem Sie die Kennung von einem Gerät entfernen oder eine neue temporäre Kennung auf einem Gerät erzwingen. Die folgende Tabelle erläutert, wie das Zurücksetzen der Kennung auf verschiedenen mobilen Plattformen funktioniert.

|Plattform|Zurücksetzen der Kennung|
|------------|------------------|
|macOS|Nicht unterstützt|
|iOS|Wird für das Löschen der Kennung von einem Gerät unterstützt. Es wird keine neue temporäre Kennung erstellt.|
|Android|Unterstützt auf früheren Versionen als Android 7.0. Erstellt eine temporäre Kennung.|
|Windows 10 Mobile|Unterstützt|
|Windows Phone 8 und Windows Phone 8.1|Unterstützt|
|Windows RT 8.1|Nicht unterstützt|
|Windows 8.1|Nicht unterstützt|
|Windows 10 Desktop|Nicht unterstützt|

Das Zurücksetzen der Kennung wird für Windows-PCs, die mit dem Intune-Softwareclient registriert wurden, nicht unterstützt.

### <a name="reset-a-passcode"></a>Zurücksetzen einer Kennung

1.  Wählen Sie in der [Intune-Verwaltungskonsole](https://manage.microsoft.com/) **Gruppen** &gt; **Alle Geräte** &gt; **Alle mobilen Geräte** aus.

2.  Wählen Sie bei Geräten, die bei Intune registriert sind, **Alle direkt verwalteten Geräte** aus. Andernfalls wählen Sie **Alle mit Exchange ActiveSync verwalteten Geräte** aus.

    > [!TIP]
    > Sie können auch nach Benutzer zu einem Gerät navigieren. Klicken Sie auf **Alle Benutzer**. Klicken Sie auf der Eigenschaftenseite des Benutzers auf **Geräte** und dann auf den Namen des mobilen Geräts, das Sie zurücksetzen möchten.

3.  Wählen Sie in der Liste die Geräte aus, die Sie sperren möchten. Wählen Sie auf der Taskleiste **Remoteaufgaben** und **Kennungsrückstellung** aus.


### <a name="see-also"></a>Weitere Informationen:
[Abkoppeln von Geräten](retire-devices-from-microsoft-intune-management.md) und [Windows Selective Wipe for Device Data Management](http://technet.microsoft.com/library/dn486874.aspx) (Selektives Zurücksetzen bei der Gerätedatenverwaltung in Windows)



<!--HONumber=Nov16_HO4-->


