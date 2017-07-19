---
title: "Migrieren von Richtlinien für bedingten Zugriff über das klassische Intune-Porta zum neuen Azure-Portal"
titleSuffix: Intune on Azure
description: "Migrieren von Richtlinien für bedingten Zugriff über das klassische Intune-Porta zum neuen Azure-Portal"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4
ms.reviewer: chrisgree
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2450a878424d8c992a43e8028ba59b7136e1d530
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2017
---
# <a name="reassign-conditional-access-policies-from-intune-classic-portal-to-the-new-azure-portal"></a>Erneutes Zuweisen von Richtlinien für bedingten Zugriff über das klassische Intune-Porta zum neuen Azure-Portal

Ab dem neuen Azure-Portal bietet der bedingt Zugriff Unterstützung für mehrere Richtlinien pro Anwendung zusammen mit erweiterter Anpassbarkeit.

## <a name="before-you-begin"></a>Vorbereitung

Wenn Sie bereit für das neue Azure-Portal sind, können Sie die unten angegebenen Schritte befolgen, um die Richtlinien des bedingten Zugriffs, die zuvor im klassischen Intune-Portal erstellt wurden, erneut zuzuweisen:

- Sammeln Sie die Richtlinien für bedingten Zugriff, die zuvor im klassischen Intune-Portal erstellt wurden, damit Sie wissen, welche Einstellungen Sie für die spätere Neuzuweisung benötigen.

- Führen Sie die Schritte in diesem Thema aus, um diese Richtlinien im neuen Azure-Portal neu zu erstellen.

- Deaktivieren Sie die bedingten Richtlinien in der klassischen Intune-Konsole, nachdem Sie überprüft haben, dass die neuen Richtlinien im neuen Azure-Portal wie erwartet funktionieren.
<br /><br />
    - **Vor dem Deaktivieren** der Richtlinien für bedingten Zugriff im klassischen Intune-Portal, planen Sie, wie Sie Benutzer zur neuen Richtlinie verschieben. Es gibt zwei Ansätze:
<br /><br />
        - **Verwenden Sie dieselbe Einschlussgruppe, um die im neuen Azure-Portal erstellten Richtlinien anzuwenden, und erstellen Sie eine neue Ausnahmegruppe, die mit den vom klassischen Intune-Portal angewendeten Richtlinien verwendet wird**.
            - Verschieben Sie einige Benutzer allmählich in die Ausnahmegruppe, die im klassischen Portal angegeben ist.  Dies verhindert, dass die Richtlinien, die das Ziel des klassischen Intune-Portals sind, angewendet werden. Die Richtlinien, die für die gleiche Benutzergruppe im neuen Azure-Portal erstellt wurden und konzipiert sind, werden zusätzlich zu den im klassischen Intune-Portal angewendeten Richtlinien angewendet. 
<br /><br />
        - **Erstellen Sie eine neue Gruppe für Richtlinien für bedingten Zugriff im neuen Azure-Portal**. Wenn Sie sich für diese Vorgehensweise entscheiden, müssen Sie folgende Aktionen ausführen:
            - Entfernen Sie Benutzer allmählich aus den Sicherheitsgruppen, die speziell für das klassische Intune-Portal Richtlinien für bedingten Zugriff besitzen.
            - Sobald Sie bestätigt haben, dass die neue Richtlinie für diese Benutzer funktioniert, können Sie die Richtlinie im klassischen Intune-Portal deaktivieren. 
<br /><br />
- Wenn Sie die Einstellungen für die Richtlinien für den bedingten Zugriff konfiguriert haben, um Exchange Active Sync (EAS) im klassischen Intune-Portal zu verwenden, gehen Sie zu den [Anweisungen in diesem Thema](#to-reassign-intune-device-based-conditional-access-policies-for-eas-clients), um **die Einstellungen der Richtlinie für bedingten Zugriff für EAS im neuen Azure-Portal erneut zuzuweisen**.

### <a name="to-verify-your-device-based-conditional-access-policies-in-the-intune-classic-portal"></a>So überprüfen Sie Ihre Richtlinien für den gerätebasierten bedingten Zugriff im klassischen Intune-Portal

1.  Wechseln Sie zum [klassischen Intune-Portal](https://manage.microsoft.com), und melden Sie sich mit Ihren Anmeldeinformationen an.

2.  Wählen Sie **Richtlinie** im linken Menü aus.

3.  Wählen Sie **Bedingter Zugriff** aus und anschließend den Microsoft-Clouddienst (Exchange Online, SharePoint Online usw.), für den Sie eine Richtlinie für bedingten Zugriff erstellt haben.

4.  Notieren Sie sich die Einstellungen für den bedingten Zugriff, und verwenden Sie diese Notizen als Referenz, um die gleichen Richtlinien für bedingten Zugriff im neuen Azure-Portal zu erstellen.

### <a name="app-and-device-based-conditional-access-policies-working-together"></a>Richtlinien für den App- und gerätebasierten bedingten Zugriffs, die zusammen arbeiten

Das Blatt **Intune-App-Schutz** im neuen Azure-Portal erlaubt Administratoren, App-basierte bedingte Regeln festzulegen, sodass nur Apps, die die App-Schutzrichtlinien von Intune unterstützen, auf Unternehmensressourcen zugreifen dürfen. Sie können diese Richtlinien für den App-basierten bedingten Zugriff mithilfe von Richtlinien für den gerätebasierten bedingten Zugriff überlappen. Dies geschieht, je nachdem, ob Sie die gerätebasierte und App-basierte bedingte Richtlinie kombinieren möchten (logischer UND-Vorgang) oder eine Option bereitstellen möchten (logischer ODER-Vorgang). Wenn die Anforderungen für Ihre Richtlinie für den bedingten Zugriffs Folgende sind:

- Das kompatible Gerät **UND** die Verwendung der genehmigten App sind erforderlich.
    - Sie müssen Ihre Richtlinie für den bedingten Zugriff mithilfe des [Blatts des bedingten Zugriffs von Azure AD](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) und des [Blatts des Intune-App-Schutzes](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0) festlegen.
<br /><br />
- Das kompatible Gerät **ODER** die Verwendung der genehmigten App sind erforderlich.
    - Sie müssen Ihre Richtlinie für den bedingten Zugriff mithilfe des [klassischen Intune-Portals](https://manage.microsoft.com) und dem [Blatt des Intune-App-Schutzes](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0) festlegen.

> [!TIP] 
> Dieses Thema enthält Screenshots, die die Benutzererfahrung im klassischen Intune-Portal und dem neue Azure-Portal vergleichen.

## <a name="to-re-assign-intune-device-based-conditional-access-policies"></a>So weisen Sie Richtlinien für den gerätebasierten bedingten Zugriff für Intune erneut zu

1. Wechseln Sie zum [bedingten Zugriff im neuen Azure-Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies), und melden Sie sich mit Ihren Anmeldeinformationen an.

2. Wählen Sie **Neue Richtlinie** aus.

3. Geben Sie einen Namen für die Richtlinie an.

4. Wählen Sie **Benutzer und Gruppen** unter dem Abschnitt **Zuweisungen** für die neue Richtlinie für den bedingten Zugriff aus.
    
    ![Vergleich der Benutzergruppenoberfläche zwischen dem klassischen Intune-Portal und dem neuen Azure-Portal](./media/reassign-ca-1.png)

    > [!IMPORTANT] 
    > Wenn Sie alle Benutzer im klassischen Intune-Portal ausgewählt haben, schließen Sie alle Benutzer mit ein. Das gleiche gilt für Gruppen; wenn Sie Gruppen ausgewählt haben, müssen Sie **einzelne Benutzer und Gruppen auswählen**, um diese Gruppen einzuschließen. Wenn Sie darüber hinaus die Option **Ausgenommene Gruppen** im klassischen Intune-Portal ausgewählt haben, müssen Sie diese ausgewählten Gruppen im neuen Azure-Portal ausschließen.

5. Nachdem Sie Ihre Gruppe ausgewählt haben, klicken Sie auf **Auswählen** und dann auf **Fertig**.

6. Wählen Sie **Cloud-Apps** unter dem Abschnitt **Zuweisungen** aus.

7. Wählen Sie auf dem **Cloud-Apps**-Blatt **Apps auswählen** aus.

8. Wählen Sie die App, für die Sie die neue Richtlinie für bedingten Zugriff anwenden möchten, und klicken Sie auf **Auswählen**.

9. Klicken Sie auf **Fertig**.

    ![Vergleich der Cloud-App-Benutzeroberfläche zwischen dem klassischen Intune-Portal und dem neuen Azure-Portal](./media/reassign-ca-3.png)

    > [!TIP] 
    > Wenn Sie mehrere Apps mit derselben Richtlinie haben, können Sie in Betracht ziehen, sie in einer einzelnen Richtlinie im neuen Azure-Portal zu konsolidieren.

10. Wählen Sie **Bedingungen** unter dem Abschnitt **Zuweisungen** aus.

11. Wählen Sie auf dem Blatt **Bedingungen** die Option **Geräteplattformen** aus, dann wählen Sie die zutreffende Geräteplattform aus.

12. Sobald Sie damit fertig sind, klicken Sie zweimal auf **Fertig**.

    ![Vergleich der Benutzeroberfläche der Geräteplattform zwischen dem klassischen Intune-Portal und dem neuen Azure-Portal](./media/reassign-ca-4.png)

    > [!TIP] 
    > Wenn Sie einzelne Plattformen im klassischen Intune-Portal ausgewählt haben, wählen Sie die einzelnen Plattformen im neuen Azure-Portal aus.

    > [!NOTE] 
    > Sie können später den Domänenbeitritt oder kompatible Optionen für Windows angeben.

13. Wählen Sie **Bedingungen** unter dem Abschnitt **Zuweisungen** aus.

14. Wählen Sie auf dem Blatt **Bedingungen** **Client-Apps** aus, wählen Sie dann die zutreffende Client-App aus.

15. Sobald Sie damit fertig sind, klicken Sie auf zweimal auf **Fertig**.

    ![Vergleich der Client-Apps-Benutzeroberfläche zwischen dem klassischen Intune-Portal und dem neuen Azure-Portal](./media/reassign-ca-6.png)

16. Wenn Sie die Browsereinstellungen im klassischen Intune-Portal ausgewählt haben, wählen Sie jeweils **Browser** und **Mobile Apps und Desktopclients** im neuen Azure-Portal aus. Wählen Sie für den Fall, dass Sie nicht die Browsereinstellungen im klassischen Intune-Portal ausgewählt haben, nur **Mobile Apps und Desktopclients** aus. 

17. Wählen Sie im Abschnitt **Zugriffssteuerung** die Option **Grant** (Gewähren) aus.

18. Wählen Sie **Markieren des Geräts als kompatibel erforderlich** unter **Grant Access Controls** (Zugriffssteuerungen gewähren) aus, klicken Sie dann auf **Auswählen**.

19. Wenn Sie eine Richtlinie besitzen, die mit einer Domäne verknüpfte Windows-Geräte erfordert, und Sie auch in Intune registrierte und mit Windows kompatible Geräte zulassen, wählen Sie **In Domäne eingebundenes Gerät anfordern** und **Markieren des Geräts als kompatibel erforderlich** zusammen mit **Eine der ausgewählten Kontrollen anfordern** aus.

20. Wenn Sie keine in Intune registrierten und mit Windows kompatiblen Geräte zulassen, nehmen Sie die Windows-Richtlinie aus der aktuellen Richtlinie aus, und erstellen Sie anschließend eine separate Richtlinie, für die **Geräteplattformen** auf **Windows** festgelegt sind, einschließlich der anderen Bedingungen, die wie oben festgelegt sind. Wählen Sie dann **In Domäne eingebundenes Gerät anfordern** unter **Grant Access Controls** (Zugriffssteuerungen genehmigen) aus.

21. Aktivieren Sie die Umschaltfläche **Richtlinie aktivieren** auf dem Blatt **Neu** der Richtlinie für den bedingten Zugriff, klicken Sie dann auf **Erstellen**.

    ![Vergleich der Benutzeroberfläche zum Aktivieren einer Richtlinie zwischen dem klassischen Intune-Portal und dem neuen Azure-Portal](./media/reassign-ca-11.png)

## <a name="to-reassign-intune-device-based-conditional-access-policies-for-eas-clients"></a>So weisen Sie Richtlinien für den gerätebasierten bedingten Zugriff für EAS-Clients für Intune erneut zu

Wenn Sie Exchange Active Sync-Einstellungen (EAS) als Teil einer Exchange Online-Richtlinie im klassischen Intune-Portal konfiguriert haben, müssen Sie eine zweite Richtlinie für den bedingten Zugriff im neuen Azure-Portal erstellen.

1. Wechseln Sie zum [bedingten Zugriff im neuen Azure-Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies), und melden Sie sich mit Ihren Anmeldeinformationen an.

2. Wählen Sie **Neue Richtlinie** aus.

3. Geben Sie einen Namen für die Richtlinie an.

4. Wählen Sie **Benutzer und Gruppen** unter dem Abschnitt **Zuweisungen** für die neue Richtlinie für den bedingten Zugriff aus.

    ![Vergleich der Benutzergruppenoberfläche zwischen dem klassischen Intune-Portal und dem neuen Azure-Portal](./media/reassign-ca-12.png)

    > [!IMPORTANT] 
    > Wenn Sie alle Benutzer im klassischen Intune-Portal ausgewählt haben, schließen Sie alle Benutzer mit ein. Das gleiche gilt für Gruppen; wenn Sie Gruppen ausgewählt haben, müssen Sie **einzelne Benutzer und Gruppen auswählen**, um diese Gruppen einzuschließen. Wenn Sie darüber hinaus die Option **Ausgenommene Gruppen** im klassischen Intune-Portal ausgewählt haben, müssen Sie diese ausgewählten Gruppen im neuen Azure-Portal ausschließen.

5. Nachdem Sie Ihre Gruppe ausgewählt haben, klicken Sie auf **Auswählen** und dann auf **Fertig**.

6. Wählen Sie **Cloud-Apps** unter dem Abschnitt **Zuweisungen** aus.

7. Klicken Sie auf dem Blatt **Cloud-Apps** auf **Ausgewählte Apps**, wählen Sie **Exchange Online** aus, **Auswählen** und dann **Fertig**.

    ![Vergleich der Cloud-Apps-Benutzeroberfläche zwischen dem klassischen Intune-Portal und dem neuen Azure-Portal](./media/reassign-ca-14.png)

    > [!IMPORTANT] 
    > Bedingte Zugriffsrichtlinien für EAS-Clients können keine andere Cloud-App enthalten.

8. Wählen Sie auf dem Blatt **Bedingungen** **Client-Apps** aus, wählen Sie dann die zutreffende Client-App aus. Wenn Sie Clients blockieren möchten, die nicht von Intune unterstützt werden, verwenden Sie die Option **Richtlinie nur auf unterstützte Plattformen anwenden**.

    ![Vergleich der Client-Apps-Benutzeroberfläche zwischen dem klassischen Intune-Portal und dem neuen Azure-Portal](./media/reassign-ca-15.png)

9. Sobald Sie damit fertig sind, klicken Sie auf zweimal auf **Fertig**.

10. Wählen Sie im Abschnitt **Zugriffssteuerung** die Option **Grant** (Gewähren) aus.

11. Wählen Sie **Markieren des Geräts als kompatibel erforderlich** unter **Grant Access Controls** (Zugriffssteuerungen gewähren) aus, klicken Sie dann auf **Auswählen**.

    ![Vergleich der Benutzeroberfläche zum Gewähren von Zugriff zwischen dem klassischen Intune-Portal und dem neuen Azure-Portal](./media/reassign-ca-16.png)

12. Aktivieren Sie die Umschaltfläche **Richtlinie aktivieren** auf dem Blatt **Neu** der Richtlinie für den bedingten Zugriff, klicken Sie dann auf **Erstellen**.

    ![Vergleich der Benutzeroberfläche zum Aktivieren einer Richtlinie zwischen dem klassischen Intune-Portal und dem neuen Azure-Portal](./media/reassign-ca-17.png)

## <a name="disable-conditional-access-policies-in-the-intune-classic-portal"></a>Deaktivieren von Richtlinien für bedingten Zugriff im klassischen Intune-Portal
### <a name="before-you-start"></a>Vorbereitung

Sobald Sie Ihre Richtlinien für den bedingten Zugriff erneut im neuen Azure-Portal zugewiesen haben, ist es wichtig, dass Sie die Richtlinien für bedingten Zugriff, die Sie zuvor im klassischen Intune-Portal erstellt haben, allmählich deaktivieren. Darüber hinaus müssen Sie möglicherweise die gleiche Sicherheitsgruppe verwenden, um die im neuen Azure-Portal erstellten Richtlinien für bedingten Zugriff anzuwenden.

- Sehen Sie sich den Abschnitt mit den [Vorbereitungen](#before-you-begin) zu Beginn dieses Themas an, bevor Sie Ihre Richtlinien für den bedingten Zugriff im klassischen Intune-Portal deaktivieren.

### <a name="to-disable-the-conditional-access-policies"></a>So deaktivieren Sie die Richtlinien für den bedingten Zugriff

1.  Wechseln Sie zum [klassischen Intune-Portal](https://manage.microsoft.com), und melden Sie sich mit Ihren Anmeldeinformationen an.

2.  Wählen Sie **Richtlinie** im linken Menü aus.

3.  Wählen Sie **Bedingter Zugriff** aus und anschließend den Microsoft-Clouddienst (Exchange Online, SharePoint Online usw.), für den Sie eine Richtlinie für bedingten Zugriff erstellt haben.

4.  Deaktivieren Sie die Option **Bedingte Zugriffsrichtlinie für Exchange Online aktivieren**, und klicken Sie dann auf **Speichern**.

    ![Deaktivieren von Richtlinien für bedingten Zugriff für das klassische Intune-Portal](./media/reassign-ca-18.png)

## <a name="see-also"></a>Weitere Informationen:

- [Gängige Möglichkeiten der Verwendung des bedingten Zugriffs in Intune](conditional-access-intune-common-ways-use.md)
- [App-basierter bedingter Zugriff mit Intune](app-based-conditional-access-intune.md)
- [Bedingter Zugriff in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)