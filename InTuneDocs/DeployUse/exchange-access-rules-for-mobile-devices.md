---
# required metadata

title: Exchange-Zugriffsregeln für mit Microsoft Intune verwaltete mobile Geräte | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 208b9f45-02d9-413a-b86a-8bad9b5008fa

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Exchange-Zugriffsregeln für mobile Geräte
Die Exchange-Zugriffsregeln für mobile Geräte bestimmen das Ausmaß des Zugriffs, das diese Geräte auf Exchange erhalten. Diese Einstellungen betreffen alle mobilen Geräte, einschließlich der nicht in Microsoft Intune registrierten. Sie können zunächst eine **Standardregel** definieren, die für alle mobilen Geräte gilt, auf welche keine benutzerdefinierten Regeln angewendet werden. Die folgende Tabelle enthält die Zugriffsebenen, die von Exchange ActiveSync verwaltet werden:

|Zugriffsebene|Beschreibung|
|----------------|---------------|
|**Zugriff auf Exchange für alle mobilen Geräte zulassen, sofern nicht durch eine benutzerdefinierte Regel anders festgelegt**|Mit dem Status *Zugriff zulassen* können mobile Geräte mithilfe von Exchange ActiveSync synchronisieren und eine Verbindung mit dem Exchange-Server herstellen, um E-Mails abzurufen und Kalender, Kontakte, Aufgaben und Notizen zu verwalten. Dies wird so lange fortgeführt, wie das Gerät der von Ihnen konfigurierten **Intune-Sicherheitsrichtlinie für mobile Geräte** entspricht, es sei denn, der Benutzer oder das bestimmte mobile Gerät sind vom Exchange-Administrator blockiert worden.|
|**Zugriff auf Exchange für alle mobilen Geräte blockieren, sofern nicht durch eine benutzerdefinierte Regel anders festgelegt**|Im Status *Zugriff blockieren* sind mobile Geräte blockiert, und das Herstellen von Verbindungen mit dem Exchange-Server wird nicht zugelassen. Die Geräte empfangen einen Fehler „HTTP 403 Forbidden“. Der Benutzer erhält eine E-Mail-Nachricht vom Exchange-Server, in der er darüber informiert wird, dass das mobile Gerät nicht mehr auf sein Postfach zugreifen kann. Diese Nachricht kann nicht mit dem gesperrten mobilen Gerät empfangen werden. Sie können dieser Nachricht angepassten Text hinzufügen, um mithilfe der Aufgabe **Nachricht an Benutzer festlegen** Anweisungen für Benutzer bereitzustellen, deren Geräte blockiert wurden.|
|**Alle mobilen Geräte unter Quarantäne stellen und später für jedes mobile Gerät im Einzelfall entscheiden, sofern nicht durch eine benutzerdefinierte Regel anders festgelegt**|Wenn ein mobiles Gerät unter Quarantäne gestellt wird, kann es weiterhin eine Verbindung zum Exchange-Server herstellen. Ihm wird jedoch nur ein beschränkter Zugriff auf die Daten gewährt. Der Benutzer des Geräts kann seinen eigenen Ordnern mit dem Kalender, Kontakten, Aufgaben und Notizen Inhalt hinzufügen, aber das Gerät kann keine Inhalte aus dem Postfach des Benutzers abrufen. Der Benutzer empfängt eine einzelne E-Mail-Nachricht, die besagt, dass das mobile Gerät unter Quarantäne gestellt wurde. Diese Nachricht wird auf dem Gerät und im Posteingang des Benutzers empfangen. Sie können dieser Nachricht über die Aufgabe **Nachricht an Benutzer festlegen** angepassten Text hinzufügen, um den Benutzern, deren Geräte unter Quarantäne gestellt wurden, Anweisungen mitzuteilen.|

Eine Zugriffsmethode enthält eine **Standardregel** und **Benutzerdefinierte Regeln** und gilt für alle mobilen Geräte, die mit Exchange verbunden sind. Die folgende Tabelle enthält einige Beispiele für Zugriffsmethoden.

|Zugriffsmethode|Beschreibung|
|-------------------|---------------|
|Liste „Zulassen“|Mit der *Liste „Zulassen“* können Sie einer Liste bekannter Geräte Zugriff gewähren und den Zugriff für alle anderen Geräte blockieren. Hierzu müssen Sie benutzerdefinierte Regeln erstellen, sodass die gewünschten Geräte auf die Postfächer des Benutzers zugreifen können. Nachdem Sie eine solche Regel erstellt haben, müssen Sie in der Standardzugriffsregel festlegen, dass alle anderen Geräte blockiert oder unter Quarantäne gestellt werden. Zum Hinzufügen eines neuen Geräts zur Liste „Zulassen“ müssen Sie eine neue benutzerdefinierte Regel erstellen.|
|Liste „Blockieren“|Mit der *Liste „Blockieren“* können Sie allen Geräten standardmäßig Zugriff gewähren, aber eine Gruppe von Geräten blockieren, die keinen Zugriff auf Ihr Unternehmen haben sollen. Erstellen Sie die Liste „Blockieren“ mithilfe von benutzerdefinierten Regeln, um die Geräte zu blockieren, die nicht mit den Postfächern Ihres Unternehmens synchronisiert werden sollen. Die Standardzugriffsregel sollte so festgelegt werden, dass sie den Zugriff auf alle Geräte gewährt, die durch die bestehenden Regeln nicht explizit blockiert werden. Zum Hinzufügen eines neuen Geräts oder einer Gerätegruppe zur Liste „Blockieren“ müssen Sie eine neue benutzerdefinierte Regel erstellen.|
|Gemischtes Zulassen und Blockieren|Sie können nicht nur die Listen „Zulassen“ und „Blockieren“ erstellen, sondern auch neue mobile Geräte unter Quarantäne stellen, wenn sie ganz neu in das Unternehmen eingeführt und noch geprüft werden. Wenn Sie z. B. eine Liste „Blockieren“ für mobile Geräte erstellt haben, die nicht in Ihrem Unternehmen zugelassen sind, und eine Liste „Zulassen“ für mobile Geräte, die im Unternehmen zugelassen sind, können Sie in der Standardregel festlegen, dass Geräte unter Quarantäne gestellt werden sollen. Alle anderen Geräte werden automatisch unter Quarantäne gestellt. Dadurch können Sie neue Geräte erkennen, wenn sie in die Organisation eingeführt werden, und entscheiden, ob sie der Liste „Zulassen“ oder der Liste „Blockieren“ hinzugefügt werden sollen.|
Im folgenden Verfahren wird das Erstellen einer benutzerdefinierten Regel beschrieben.

## Erstellen einer Standardzugriffsregel

1.  In der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) &gt; **Zugriff** &gt; **Exchange-Zugriff für mobile Geräte**.

2.  Wählen Sie in der Liste **Standardregel** die Zugriffsregel aus, die Sie auf alle mobilen Geräte anwenden möchten, die nicht durch eine Regel oder persönliche Ausnahme abgedeckt werden. Wählen Sie **Speichern** aus..

Im folgenden Verfahren wird das Erstellen einer benutzerdefinierten Regel beschrieben.

## Erstellen einer benutzerdefinierten Zugriffsregel

1. In der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) &gt; **Zugriff** &gt; **Exchange-Zugriff für mobile Geräte**.

2.  Wählen Sie in der Liste **Benutzerdefinierte Regeln** die Option **Regel hinzufügen** aus, und erstellen Sie eine benutzerdefinierte Regel. Wählen Sie **Speichern** aus..


<!--HONumber=May16_HO1-->


