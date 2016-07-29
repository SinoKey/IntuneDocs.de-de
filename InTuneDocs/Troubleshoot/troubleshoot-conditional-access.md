---
title: Problembehandlung beim bedingten Zugriff| Microsoft Intune
description: "Was zu tun ist, wenn Ihre Benutzer durch bedingten Intune-Zugriff nicht auf Ressourcen zugreifen können."
keywords: 
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 433fc32c-ca9c-4bad-9616-852c72faf996
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c1e215320168c659d5f838355f6350111d6979b0
ms.openlocfilehash: 21ae91f0d2866b621d9353929bab6d41d95dc8cc


---

# Problembehandlung beim bedingten Zugriff

In diesem Thema wird beschrieben, was zu tun ist, wenn Ihre Benutzer durch bedingten Intune-Zugriff nicht auf Ressourcen zugreifen können. 

### Die Grundlagen für den erfolgreichen bedingten Zugriff

Sie müssen folgende Bedingungen erfüllen, damit der bedingte Zugriff funktioniert:

-   Das Gerät muss von Intune verwaltet werden.
-   Der Benutzer muss bei Azure Active Directory (AAD) registriert sein
-   Das Gerät muss mit den Kompatibilitätsrichtlinien kompatibel sein, die Sie in Intune konfiguriert haben. 
-   EAS muss auf dem Gerät aktiviert werden, wenn der Benutzer E-Mails über den nativen E-Mail-Client des Geräts anstatt über Outlook empfängt.

Diese Bedingungen können für jedes Gerät im Azure-Verwaltungsportal und im Geräteinventurbericht angezeigt werden.





In der Regel versucht ein Benutzer, auf E-Mail oder SharePoint zuzugreifen, und wird zur Registrierung aufgefordert. Diese Aufforderung führt den Benutzer zum Unternehmensportal. Im Folgenden finden Sie mögliche Erklärungen für dieses Verhalten und Lösungsvorschläge:

## Moderne Authentifizierungsszenarios

### Probleme bei der Registrierung

 -  Das Gerät ist nicht registriert, somit wird das Problem durch die Registrierung gelöst.
 -  Der Benutzer hat das Gerät registriert, bei der Arbeitsplatzeinbindung ist jedoch ein Fehler aufgetreten. Der Benutzer sollte die Registrierung über das Unternehmensportal aktualisieren. 
 
### Kompatibilitätsprobleme

 -  Das Gerät ist mit der Intune-Richtlinie nicht kompatibel. Häufige Probleme sind Verschlüsselungs- und Kennwortanforderungen. Der Benutzer wird auf das Unternehmensportal umgeleitet, wo er sein Gerät dahingehend konfigurieren kann, dass es kompatibel ist.
 -  Bei iOS-Geräten blockiert ein bestehendes E-Mail-Profil, das vom Benutzer erstellt wurde, die Bereitstellung eines kompatiblen Profils (erstellt durch den Intune-Administrator) von Intune. Das ist ein häufig auftretendes Problem, da iOS-Benutzer in der Regel ein E-Mail-Profil erstellen und anschließend die Registrierung vornehmen. Das Unternehmensportal informiert den Benutzer darüber, dass es aufgrund seines manuell konfigurierten E-Mail-Profils nicht kompatibel ist, und fordert ihn dazu auf, dieses Profil zu entfernen. Der Benutzer sollte sein E-Mail-Profil entfernen, damit das Intune-Profil bereitgestellt werden kann. Weisen Sie Ihre Benutzer an, die Registrierung ohne das Installieren eines E-Mail-Profils vorzunehmen und Intune die Bereitstellung des Profils zu erlauben, um das Problem zu vermeiden.  
 -  Die Registrierung der Kompatibilitätsinformationen für ein Gerät kann einige Zeit in Anspruch nehmen. Warten Sie einige Minuten, und versuchen Sie es erneut.

### Probleme mit Richtlinien

Wenn Sie eine Kompatibilitätsrichtlinie erstellen und mit einer E-Mail-Richtlinie verknüpfen, müssen beide Richtlinien für denselben Benutzer bereitgestellt werden. Gehen Sie daher bei der Planung der Bereitstellung der verschiedenen Richtlinien für die verschiedenen Gruppen sorgfältig vor. Benutzer, die nur eine Richtlinie angewendet haben, werden wahrscheinlich feststellen, dass ihre Geräte nicht kompatibel sind.


## Exchange ActiveSync-Szenarios


- Bei einem Android-Gerät, das registriert und kompatibel ist, kann dennoch ein Quarantänehinweis erscheinen, wenn versucht wird, auf Unternehmensressourcen zuzugreifen. Bevor sie den Link **Starten** auswählen, sollte sich der Benutzer vergewissern, dass das Unternehmensportal nicht offen war, als er versuchte, auf die Ressourcen zuzugreifen. Der Benutzer sollte das Unternehmensportal schließen, erneut versuchen, auf die Ressourcen zuzugreifen, und anschließend den Link **Starten** auswählen.

- Ein abgekoppeltes Gerät hat nach der Abkopplung möglicherweise noch für mehrere Stunden Zugriff. Dies liegt daran, dass Exchange die Zugriffsrechte 6 Stunden lang zwischenspeichert. Ziehen Sie in diesem Szenario andere Möglichkeiten zum Datenschutz auf abgekoppelten Geräten in Betracht.
- Ein mögliches Problem ist, dass EASid nicht mit AAD abgeglichen werden kann. Eine häufige Ursache für dieses Problem ist die Drosselung. Warten Sie daher einige Minuten, und versuchen Sie es erneut. 

## Sammeln von OWA-Postfachprotokollen

Wenn Ihre Exchange-Konnektivitätsprobleme weiterhin bestehen, nachdem Sie die Probleme mit Ihrer Bereitstellung behandelt haben, sammeln Sie die OWA-Postfachprotokolle, bevor Sie Kontakt mit Microsoft Support aufnehmen, wie unter [Anfordern von Support für Microsoft Intune](how-to-get-support-for-microsoft-intune.md) beschrieben.

1. Melden Sie sich über OWA an, und wählen Sie das Symbol „Einstellungen“ (Zahnrad) neben Ihrem Namen in der oberen rechten Ecke aus. 
2. Wählen Sie **Optionen** aus
3. Wählen Sie in der Spalte auf der linken Seite **Telefon** (oder **Mobiltelefone**) aus.
4. Wählen Sie im oberen Menü **Mobiltelefone** aus. 
5. Wählen Sie Ihr Gerät aus der Liste aus, und wählen Sie anschließend **Protokollierung starten** aus. 
6. Wenn Sie dazu aufgefordert werden, wählen Sie im Popupdialogfenster **Ja** aus. 
7. Führen Sie die Aktion aus, die das Problem verursacht hat, damit Sie es reproduzieren können. 
8. Warten Sie 1-2 Minuten, gehen Sie anschließend zurück zur Telefonliste in OWA (vergewissern Sie sich, dass Ihr Telefon in der Liste ausgewählt ist), und wählen Sie aus dem oberen Menü **Protokoll abrufen** aus. 
9. Sie sollten jetzt eine E-Mail von Ihnen selbst mit einem Anhang haben. Stellen Sie Microsoft Support beim Öffnen eines Supporttickets den Inhalt der E-Mail zur Verfügung.


### Nächste Schritte
Wenn diese Informationen zur Problembehandlung für Sie nicht hilfreich waren, wenden Sie sich wie in [Anfordern von Support für Microsoft Intune](how-to-get-support-for-microsoft-intune.md) beschrieben an den Microsoft Support.



<!--HONumber=Jul16_HO3-->


