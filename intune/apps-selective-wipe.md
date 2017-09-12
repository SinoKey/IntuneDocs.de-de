---
title: "So setzen Sie nur die Unternehmensdaten in einer App zurück"
titleSuffix: Azure portal
description: "Erfahren Sie, wie Sie Apps mit Microsoft Intune selektiv zurücksetzen.\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9aeb3525016bf820dc23402659c2c953143385c9
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Zurücksetzen nur von Unternehmensdaten in einer in Intune verwalteten App

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Wenn ein Gerät verloren geht oder gestohlen wird oder wenn der Mitarbeiter das Unternehmen verlässt, müssen Sie sicherstellen, dass Unternehmensdaten in Apps vom Gerät entfernt werden. Allerdings sollten Sie persönliche Daten nicht vom Gerät entfernen, insbesondere dann nicht, wenn das Gerät dem Mitarbeiter gehört.

Um Unternehmensdaten aus Apps selektiv zu entfernen, erstellen Sie mithilfe der Schritte in diesem Thema eine Zurücksetzungsanforderung. Nach Abschluss der Anforderung werden die Unternehmensdaten beim nächsten Ausführen der Anwendung aus der App entfernt.

>[!IMPORTANT]
> Direkt aus der App mit dem nativen Adressbuch synchronisierte Kontakte werden entfernt. Kontakte, die aus dem nativen Adressbuch mit einer anderen externen Quelle synchronisiert werden, können nicht zurückgesetzt werden. Dies betrifft derzeit nur die Microsoft Outlook-App.

## <a name="create-a-wipe-request"></a>Erstellen einer Zurücksetzungsanforderung

1.  Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.

2.  Wählen Sie **Weitere Dienste** aus, geben Sie in das Filtertextfeld **Intune** ein, und wählen Sie **Intune** aus. Das Intune-Blatt wird geöffnet. Wählen Sie das Blatt **Apps verwalten** aus.

    ![Screenshot des Blatts „Neue Zurücksetzungsanforderung“](./media/intune-azure-preview-blade.png)

3.  Wählen Sie dem Blatt **Mobile Apps** die Option **Neue Zurücksetzungsanforderung** aus. Dadurch wird das Blatt **Neue Zurücksetzungsanforderung** geöffnet.

4.  Wählen Sie **Neue Zurücksetzungsanforderung** aus. Dadurch wird das Blatt **Neue Zurücksetzungsanforderung** geöffnet.

    ![Screenshot des Blatts „Neue Zurücksetzungsanforderung“](./media/AzurePortal_MAM_NewWipeRequest.png)

5.  Wählen Sie **Benutzer** aus, um das Blatt **Benutzer** zu öffnen, und den Benutzer auszuwählen, dessen App-Daten gelöscht werden sollen.

6.  Wählen Sie **Gerät** aus. Damit öffnen Sie das Blatt **Gerät**, auf dem alle Geräte aufgeführt werden, die dem ausgewählten Benutzer zugeordnet sind. Es enthält außerdem zwei Spalten – eine mit dem Gerätenamen, einem vom Benutzer festgelegten Anzeigenamen, und eine mit dem Gerätetyp und der Geräteplattform. Wählen Sie das Gerät aus, das zurückgesetzt werden soll.

7.  Sie befinden sich nun wieder auf dem Blatt **Neue Zurücksetzungsanforderung**. Wählen Sie **OK** aus, um eine Zurücksetzungsanforderung zu erstellen. 

Der Dienst erstellt für jede geschützte App auf dem Gerät und den zugeordneten Benutzer eine separate Zurücksetzungsanforderung und überwacht diese.

## <a name="monitor-your-wipe-requests"></a>Überwachen der Löschanforderungen

Sie erhalten einen zusammengefassten Bericht, der den Gesamtstatus der Zurücksetzungsanforderung zeigt und die Anzahl der ausstehenden Anforderungen und Fehler enthält. Um weitere Informationen zu erhalten, gehen Sie folgendermaßen vor:

1.  Auf dem Blatt **Mobile Apps – Selektive App-Zurücksetzung** wird eine Liste mit Ihren Anforderungen, gruppiert nach Benutzer, angezeigt. Da das System für jede geschützte App, die auf dem Gerät ausgeführt wird, eine Zurücksetzungsanforderung erstellt, werden möglicherweise für einen Benutzer mehrere Anforderungen angezeigt. Der Status gibt an, ob eine Zurücksetzungsaufforderung noch **aussteht**oder **fehlgeschlagen**ist, bzw. **erfolgreich**ausgeführt wurde.

    ![Screenshot des Blatts „Neue Zurücksetzungsanforderung“](./media/wipe-request-status-1.png)

Darüber hinaus können Sie den Gerätenamen und den Gerätetyp anzeigen. Diese Informationen sind beim Lesen von Berichten hilfreich.

>[!IMPORTANT]
> Der Benutzer muss die App für das Zurücksetzen öffnen, und das Zurücksetzen dauert bis zu 30 Minuten, nachdem die Anforderung gestellt wurde.

## <a name="delete-a-wipe-request"></a>Löschen einer Zurücksetzungsanforderung

Zurücksetzungen mit Status „Ausstehend“ werden angezeigt, bis Sie sie manuell löschen.  So löschen Sie manuell eine Zurücksetzungsanforderung

1.  Wählen Sie auf dem Blatt **Zurücksetzungsanforderung** die Kachel **Zurücksetzungsanforderung** aus, um das Blatt **Zurücksetzungsanforderung** zu öffnen.

2.  Klicken Sie mit der rechten Maustaste auf die Zurücksetzungsanforderung, die Sie löschen möchten, und wählen Sie dann **Zurücksetzungsanforderung abbrechen** aus.

    ![Screenshot des Blatts „Neue Zurücksetzungsanforderung“](./media/delete-wipe-request.png)

3.  Sie werden aufgefordert, den Löschvorgang zu bestätigen. Wählen Sie **Ja** oder **Nein** aus, und klicken Sie dann auf **OK**.

### <a name="see-also"></a>Weitere Informationen:
[Was sind App-Schutzrichtlinien?](app-protection-policy.md)

[Was ist die App-Verwaltung?](app-management.md)