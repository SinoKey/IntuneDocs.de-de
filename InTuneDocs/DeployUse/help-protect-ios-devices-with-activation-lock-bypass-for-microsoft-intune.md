---
title: Unterstützen des Schutz von iOS-Geräten durch Umgehung der Aktivierungssperre für Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2804b69c-f210-4a11-aaee-b47ecc430d9c
author: robstackmsft
---
# Unterstützen des Schutz von iOS-Geräten durch Umgehung der Aktivierungssperre für Microsoft Intune
Microsoft Intune hilft Ihnen die Verwaltung von iOS Aktivierungssperre, ein Feature der Suche mein iPhone-app für iOS 7.1 und höher. Die Aktivierungssperre wird automatisch aktiviert, wenn die iPhone-App „Mein iPhone suchen“ auf einem Gerät verwendet wird. Nach der Aktivierung müssen die Apple-ID und das Kennwort des Benutzers eingegeben werden, bevor folgende Vorgänge möglich sind:

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
Intune kann der Aktivierung Sperrstatus überwachtes und unüberwachtes Geräte anfordern, die iOS 7.1 und höher. Für überwachte Geräte kann Intune den Umgehungscode der Aktivierungssperre abrufen und ihn direkt auf das Gerät anwenden. Wenn das Gerät zurückgesetzt wurde, können Sie direkt zum Gerät mithilfe von Code wie den Benutzernamen und ein leeres Kennwort zugreifen).

**Die Vorteile sind**:

-   Der Benutzer erhält die Sicherheitsvorteile der Suche mein iPhone-app.

-   Sie können die Benutzer ihre Arbeit zu wissen, dass wenn das Gerät umgestaltet werden muss, können Sie das Zurückziehen oder Entsperren aktivieren.

## Verwenden der Umgehung der Aktivierungssperre über die Intune-Verwaltungskonsole
> [!IMPORTANT]
> Nachdem Sie die Aktivierungssperre auf einem Gerät umgangen sind, wird automatisch eine neue Aktivierungssperre angewendet, wenn die App „Mein iPhone suchen“ geöffnet wird. Aus diesem Grund **Sie müssen im Besitz des Geräts befinden, bevor Sie dieses Verfahren ausführen**.

1.  In der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com), wählen Sie **Gruppen** & Gt; **Alle Geräte** & Gt; **Alle firmeneigenen Geräte**.

2.  Wählen Sie das Gerät, dessen Aktivierungssperre umgangen werden soll. Wählen Sie **Aktivierungssperre**.

3.  Lesen Sie die Warnung. Wählen Sie **Ja** um den Vorgang fortzusetzen.

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

    Bei Auswahl von einem Gerät in der **Alle firmeneigenen Geräte** Knoten und der Aktivierung des Geräts aktiviert ist, sehen Sie auch den umgehungscode. Dieser Code kann dazu verwendet werden, um die Umgehung einer Aktivierungssperre manuell auszuführen.

### Siehe auch
[Außerkraftsetzen von Daten und Geräten in der Microsoft Intune-Verwaltung](retire-data-and-devices-from-microsoft-intune-management.md)



<!--HONumber=Mar16_HO4-->


