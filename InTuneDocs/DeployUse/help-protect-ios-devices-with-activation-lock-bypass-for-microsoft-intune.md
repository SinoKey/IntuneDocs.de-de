---
title: "Verwalten der iOS-Aktivierungssperre auf Geräten | Microsoft Intune"
description: "Microsoft Intune kann Sie beim Verwalten der iOS-Aktivierungssperre unterstützen, einem Feature der App „Mein iPhone suchen“ für iOS 7.1 und höher."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb49e926-15c4-4f01-b6eb-cee6f7ee1984
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6716a3d1fb53dc3de0189f637d5664d0a2023d05
ms.openlocfilehash: 3980d1a498ccab3eb5683e03e0cce252959b89dc


---

# Unterstützen des Schutz von iOS-Geräten durch Umgehung der Aktivierungssperre für Microsoft Intune
Microsoft Intune kann Sie beim Verwalten der iOS-Aktivierungssperre unterstützen, einem Feature der App „Mein iPhone suchen“ für iOS 7.1 und höher. Die Aktivierungssperre wird automatisch aktiviert, wenn die iPhone-App „Mein iPhone suchen“ auf einem Gerät verwendet wird. Nach der Aktivierung müssen die Apple-ID und das Kennwort des Benutzers eingegeben werden, bevor folgende Vorgänge möglich sind:

-   Deaktivieren von „Mein iPhone suchen“

-   Löschen des Geräts

-   Reaktivieren des Geräts

## Auswirkungen der Aktivierungssperre
Obwohl die Aktivierungssperre zum Schutz von iOS-Geräten beiträgt und die Chancen einer Wiederherstellung bei Verlust oder Diebstahl erhöht, kann diese Funktion Sie als IT-Administrator vor eine Reihe von Herausforderungen stellen. Beispiel:

-   Einer Ihrer Benutzer richtet die Aktivierungssperre auf einem Gerät ein. Anschließend verlässt der Benutzer das Unternehmen und gibt das Gerät zurück. Ohne die Apple-ID und das Kennwort des Benutzers gibt es keine Möglichkeit, das Gerät zu reaktivieren.

-   Sie benötigen einen Bericht über alle Geräte, bei denen die Aktivierungssperre aktiviert ist.

-   Während einer Geräteaktualisierung in Ihrem Unternehmen möchten Sie einige Geräte einer anderen Abteilung zuweisen. Es können nur Geräte neu zugewiesen werden, bei denen die Aktivierungssperre nicht aktiviert ist.

Apple hat zur Behebung dieser Probleme eine Umgehung der Aktivierungssperre in iOS 7.1 eingeführt. Auf diese Weise können Sie die Aktivierungssperre von überwachten Geräten ohne Apple-ID und Kennwort des Benutzers entfernen. Überwachte Geräte können einen gerätespezifischen Umgehungscode für die Aktivierungssperre generieren, der auf dem Aktivierungsserver von Apple gespeichert wird.

> [!TIP]
> Im überwachten Modus für iOS-Geräte können Sie mit dem Apple Configurator Tool ein Gerät sperren, um die Funktionen auf bestimmte geschäftliche Zwecke einzuschränken. Der überwachte Modus ist in der Regel nur für firmeneigene Geräte vorgesehen.

## Unterstützung von Intune beim Verwalten der Aktivierungssperre
Intune kann den Status der Aktivierungssperre von überwachten und nicht überwachten Geräten anfordern, die iOS 7.1 und höher ausführen. Ausschließlich für überwachte Geräte kann Intune den Umgehungscode der Aktivierungssperre abrufen und ihn direkt auf das Gerät anwenden. Wenn das Gerät zurückgesetzt wurde, können Sie mithilfe des Codes als Benutzername und einem leeren Kennwort direkt auf das Gerät zugreifen.

**Folgende Geschäftsvorteile ergeben sich**:

-   Der Benutzer erhält die Sicherheitsvorteile der App „Mein iPhone suchen“.

-   Sie können dem Benutzer ermöglichen, seine Arbeit zu erledigen, in dem Wissen, dass Sie das Gerät außer Kraft setzen oder entsperren können, wenn es einem neuen Zweck zugewiesen werden soll.

## Verwenden der Umgehung der Aktivierungssperre über die Intune-Verwaltungskonsole
> [!IMPORTANT]
> Nachdem Sie die Aktivierungssperre auf einem Gerät umgangen sind, wird automatisch eine neue Aktivierungssperre angewendet, wenn die App „Mein iPhone suchen“ geöffnet wird. Aus diesem Grund **muss das Gerät physisch verfügbar sein, bevor Sie dieses Verfahren ausführen**.

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Optionen **Gruppen** &gt; **Alle Geräte** &gt; **Alle unternehmenseigenen Geräte** aus.

2.  Wählen Sie das Gerät aus, dessen Aktivierungssperre Sie umgehen möchten. Wählen Sie **Umgehung der iOS-Aktivierungssperre** aus.

3.  Lesen Sie die Warnmeldung. Klicken Sie auf **Ja**, um den Vorgang fortzusetzen.

Sie können den Status der Entsperranforderung auf der Detailseite für das Gerät überprüfen.

## Ermitteln der Geräte mit Aktivierungssperre
Es gibt zwei Möglichkeiten zur Ermittlung, welche Geräte die Aktivierungssperre verwenden:

-   Führen Sie die **Bestandsberichte zu mobilen Geräten**aus. In diesem Bericht werden die Spalten **Activation Lock Status** und **Supervised** angezeigt, um den Status der Geräte anzugeben. Die Werte für **Supervised** sind **Yes** oder **No**, und die Werte für **Activation Lock Status** lauten:

    -   Enabled with bypass code

    -   Enabled without bypass code (device is not supervised)

    -   Enabled without bypass code (device cannot be reached)

    -   Nicht aktiviert

    Das Feld **Activation Lock Status** ist für Geräte leer, die nicht iOS 7.1 oder höher ausführen.

-   Wählen Sie ein Gerät in einer Gruppenansicht aus, um den Status der Aktivierungssperre im Gerätedetailbereich anzuzeigen.

    Wenn Sie ein Gerät im Knoten **Alle firmeneigenen Geräte** auswählen und die Aktivierungssperre für das Gerät aktiviert ist, dann wird auch der Umgehungscode angezeigt. Dieser Code kann dazu verwendet werden, um die Umgehung einer Aktivierungssperre manuell auszuführen.

    > [!IMPORTANT]
    >Intune erfasst alle 7 Tage den Status der Aktivierungssperre auf Geräten. Aus diesem Grund werden Geräte in der Intune-Konsole möglicherweise nicht sofort mit dem richtigen Status der Aktivierungssperre angezeigt.


### Weitere Informationen:
[Abkoppeln von Geräten](retire-devices-from-microsoft-intune-management.md)
[Geräteschutz durch Remotesperre und Zurücksetzen der Kennung](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


