---
title: "Exchange-Zugriffsregeln für mobile Geräte | Microsoft Intune"
description: "Exchange ActiveSync-Zugriffsregeln, die Geräteverbindungen mit EAS zulassen oder blockieren"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 208b9f45-02d9-413a-b86a-8bad9b5008fa
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c49e19e8c478af252d7b59c380d5500a57b71db5
ms.openlocfilehash: 7714a338d02afedde2ac090964e4d18d4410a80e


---

# Exchange-Zugriffsregeln für mobile Geräte
Die Exchange-Zugriffsregeln für mobile Geräte bestimmen die Ebene des Zugriffs, den diese Geräte auf Exchange ActiveSync erhalten. Diese Einstellungen betreffen alle mobilen Geräte, einschließlich der nicht in Microsoft Intune registrierten. Sie können zunächst eine **Standardregel** definieren, die für alle mobilen Geräte gilt, auf welche keine benutzerdefinierten Regeln angewendet werden. Die folgende Tabelle enthält die Zugriffsebenen, die von Exchange ActiveSync verwaltet werden:

|Zugriffsebene|Beschreibung|
|----------------|---------------|
|**Zugriff auf Exchange für Geräte zulassen**|Mit dem Status *Zugriff zulassen* können mobile Geräte mithilfe von Exchange ActiveSync synchronisieren und eine Verbindung mit dem Exchange-Server herstellen, um E-Mails abzurufen und Kalender, Kontakte, Aufgaben und Notizen zu verwalten. Dies wird so lange fortgeführt, wie das Gerät der von Ihnen in Exchange konfigurierten Richtlinie für das Exchange ActiveSync-Postfach entspricht, es sei denn, der Benutzer oder das jeweilige mobile Gerät wurde vom Exchange-Administrator blockiert.|
|**Zugriff auf Exchange für Geräte blockieren**|Im Status *Zugriff blockieren* sind mobile Geräte blockiert, und das Herstellen von Verbindungen mit dem Exchange-Server wird nicht zugelassen. Die Geräte empfangen einen Fehler „HTTP 403 Forbidden“. Der Benutzer erhält eine E-Mail-Nachricht vom Exchange-Server, in der er darüber informiert wird, dass das mobile Gerät nicht mehr auf sein Postfach zugreifen kann. Diese Nachricht kann nicht mit dem gesperrten mobilen Gerät empfangen werden. Sie können dieser Nachricht angepassten Text hinzufügen, um mithilfe der Aufgabe **Nachricht an Benutzer festlegen** Anweisungen für Benutzer bereitzustellen, deren Geräte blockiert wurden.|
|**Geräte unter Quarantäne stellen, sodass Sie sie später zulassen oder blockieren können**|Wenn ein mobiles Gerät unter Quarantäne gestellt wird, kann es weiterhin eine Verbindung zum Exchange-Server herstellen. Ihm wird jedoch nur ein beschränkter Zugriff auf die Daten gewährt. Der Benutzer des Geräts kann seinen eigenen Ordnern mit dem Kalender, Kontakten, Aufgaben und Notizen Inhalt hinzufügen, aber das Gerät kann keine Inhalte aus dem Postfach des Benutzers abrufen. Der Benutzer empfängt eine einzelne E-Mail-Nachricht, die besagt, dass das mobile Gerät unter Quarantäne gestellt wurde. Diese Nachricht wird auf dem Gerät und im Posteingang des Benutzers empfangen. Sie können dieser Nachricht über die Aufgabe **Nachricht an Benutzer festlegen** angepassten Text hinzufügen, um den Benutzern, deren Geräte unter Quarantäne gestellt wurden, Anweisungen mitzuteilen.|

Eine Zugriffsstrategie enthält eine **Standardregel** und **Plattformausnahmen** und gilt für alle mobilen Geräte, die mit Exchange verbunden sind. Die folgende Tabelle enthält einige Beispiele für Zugriffsmethoden.

|Zugriffsmethode|Beschreibung|
|-------------------|---------------|
|Liste „Zulassen“|Mit der *Liste „Zulassen“* können Sie einer Liste bekannter Geräte Zugriff gewähren und den Zugriff für alle anderen Geräte blockieren. Hierzu müssen Sie benutzerdefinierte Regeln für Geräteplattformen erstellen, die auf die Postfächer der Benutzer zugreifen können. Nachdem Sie eine solche Regel erstellt haben, müssen Sie in der Standardzugriffsregel festlegen, dass alle anderen Geräte blockiert oder unter Quarantäne gestellt werden. Zum Hinzufügen eines neuen Geräts zur Liste „Zulassen“ müssen Sie eine neue benutzerdefinierte Regel erstellen.|
|Liste „Blockieren“|Mit der *Liste „Blockieren“* können Sie allen Geräten standardmäßig Zugriff gewähren, aber eine Gruppe von Geräten blockieren, die keinen Zugriff auf Ihr Unternehmen haben sollen. Erstellen Sie die Liste „Blockieren“ mithilfe benutzerdefinierter Regeln, um die Geräteplattformen zu blockieren, die nicht mit den Postfächern Ihres Unternehmens synchronisiert werden sollen. Die Standardzugriffsregel sollte so festgelegt werden, dass sie den Zugriff auf alle Geräte gewährt, die durch die bestehenden Regeln nicht explizit blockiert werden. Zum Hinzufügen eines neuen Geräts oder einer Gerätegruppe zur Liste „Blockieren“ müssen Sie eine neue benutzerdefinierte Regel erstellen.|
|Gemischtes Zulassen und Blockieren|Sie können nicht nur die Listen „Zulassen“ und „Blockieren“ erstellen, sondern auch neue mobile Geräte unter Quarantäne stellen, wenn sie ganz neu in das Unternehmen eingeführt und noch geprüft werden. Wenn Sie z. B. eine Liste „Blockieren“ für mobile Geräte erstellt haben, die nicht in Ihrem Unternehmen zugelassen sind, und eine Liste „Zulassen“ für mobile Geräte, die im Unternehmen zugelassen sind, können Sie in der Standardregel festlegen, dass Geräte unter Quarantäne gestellt werden sollen. Alle anderen Geräte werden automatisch unter Quarantäne gestellt. Dadurch können Sie neue Geräte erkennen, wenn sie in die Organisation eingeführt werden, und entscheiden, ob sie der Liste „Zulassen“ oder der Liste „Blockieren“ hinzugefügt werden sollen.|
Im folgenden Verfahren wird das Erstellen einer benutzerdefinierten Regel beschrieben.

## Erstellen einer Standardzugriffsregel

1.  In der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) &gt; **Richtlinie** &gt; **Exchange ActiveSync**.

2.  Wählen Sie in der Liste **Standardregel** die Zugriffsregel aus, die Sie auf alle mobilen Geräte anwenden möchten, die nicht durch eine Regel oder persönliche Ausnahme abgedeckt werden. Wählen Sie **Speichern** aus.

Im folgenden Verfahren wird das Erstellen einer benutzerdefinierten Regel beschrieben.

## Erstellen einer benutzerdefinierten Zugriffsregel

1. In der [Microsoft Intune-Verwaltungskonsole](http://manage.microsoft.com) &gt; **Richtlinie** &gt; **Exchange ActiveSync**.

2.  Wählen Sie in der Liste **Plattformausnahmen** die Option **Regel hinzufügen** aus, und erstellen Sie eine benutzerdefinierte Regel. Wählen Sie **Speichern** aus.



<!--HONumber=Aug16_HO1-->


