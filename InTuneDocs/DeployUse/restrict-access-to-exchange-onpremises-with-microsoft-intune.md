---
title: Einschränken des e-Mail-Zugriffs auf Exchange lokal | Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid:
author: karthikaraman
---
# Einschränken des e-Mail-Zugriffs auf Exchange lokal mit Microsoft Intune
Konfigurieren Sie bedingten Zugriff in Intune, zur Steuerung des e-Mail-Zugriffs auf Exchange Online.
Wenn Sie Sie mehr darüber, wie bedingte Zugriff funktioniert möchten, lesen Sie die [Einschränken des Zugriffs auf e-Mail und Office 365-Diensten]( restrict-access-to-email-and-o365-services-with-microsoft-intune.md) Artikel.

Bevor Sie konfigurieren können Bedingter Zugriff Folgendes überprüfen:

-   Die Exchange-Version muss **Exchange 2010 oder höher**. Exchange Server-Clientzugriffsserver-Arrays werden unterstützt.

-   Verwenden Sie die **lokale Exchange Connector** verbindet [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] zu Microsoft Exchange lokal. Dies ermöglicht Ihnen die Verwaltung von Geräten über die [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Konsole. (siehe [Verwaltung mobiler Geräte mit Exchange ActiveSync und Microsoft Intune](../Topic/Mobile-device-management-with-Exchange-ActiveSync-and-Microsoft-Intune.md)).

    -   Stellen Sie sicher, dass Sie die neueste Version von verwenden, werden die **lokale Exchange Connector**. Der lokale Exchange-Connector, der Ihnen in der Intune-Konsole zur Verfügung steht, ist spezifisch für Ihren Intune-Mandanten und kann mit keinem anderen Mandanten verwendet werden. Sie sollten auch sicherstellen, dass der Exchange-Connector für Ihren Mandanten auf genau einem Computer und nicht auf mehreren installiert ist.

        Dieser Connector muss von der Intune-Verwaltungskonsole heruntergeladen werden.  Eine exemplarische Vorgehensweise zum Konfigurieren des lokalen Exchange-Connector, finden Sie unter [Konfigurieren Sie Microsoft Intune lokalen Connector für lokales oder gehostetes Exchange](../Topic/Mobile-device-management-with-Exchange-ActiveSync-and-Microsoft-Intune.md#bkmk_EX_OP).

    -   Der Connector kann auf jedem Computer installiert werden, solange dieser Computer mit dem Exchange-Server kommunizieren kann.

    -   Der Connector in der Tat unterstützt **Exchange CAS-Umgebung**. Sie können technisch den Connector auf dem Exchange-Clientzugriffsserver direkt installieren, wenn Sie möchten, aber es nicht empfohlen wird, da er die Last auf dem Server erhöht.
    Wenn Sie den Connector konfigurieren, müssen Sie es einrichten, um eines der Exchange-Clientzugriffsserver zu kommunizieren.

-   **Exchange ActiveSync** mit zertifikatbasierter Authentifizierung oder Eingabe von Anmeldeinformationen konfiguriert werden müssen.

Wenn Richtlinien für bedingten Zugriff konfiguriert sind und für einen Benutzer bestimmt werden, bevor ein Benutzer auf ihre e-Mails verbinden kann die **Gerät** Verwendung muss sein:

-   **Registriert** mit [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] oder eine Domäne eingebundenen PC.

-  **In Azure Active Directory registrierten**. Darüber hinaus muss die Client-ID von Exchange ActiveSync mit Azure Active Directory registriert werden.

  AAD DRS wird automatisch für Intune und Office 365-Kunden aktiviert. Kunden, die bereits den AD FS Device Registration Service bereitgestellt haben, sehen keine registrierten Geräte in ihrem lokalen Active Directory. **Dies gilt nicht für Windows-PCs und Windows Phone-Geräten**.

-   **Kompatible** mit einem [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] für das Gerät festgelegten Konformitätsrichtlinien.

Das folgende Diagramm veranschaulicht den Ablauf werden Richtlinien für bedingten Zugriff für Exchange lokal überprüft, ob Geräte blockiert oder zugelassen.

![](../media/ConditionalAccess8-2.png)
Wenn eine Richtlinie für bedingten Zugriff nicht erfüllt ist, wird dem Benutzer bei der Anmeldung mit einem der folgenden Meldungen angezeigt.

- Wenn das Gerät nicht registriert [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], oder ist nicht registriert in Azure Active Directory, eine Meldung mit Anweisungen zum Installieren der Unternehmensportal-app, das Gerät zu registrieren und Aktivieren des e-Mail-angezeigt wird. Dabei wird auch Exchange ActiveSync-ID des Geräts mit dem Gerätedatensatz in Azure Active Directory zugeordnet.

-   Wenn das Gerät nicht kompatibel ist, wird eine Meldung angezeigt, die den Benutzer anweist die [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Unternehmensportal-Website oder die Unternehmensportal-app, wo sie Informationen über das Problem und dessen Lösung finden können.

## Unterstützung für mobile Geräte
-   Windows Phone 8 und höher

-   Systemeigene e-Mail-app für iOS.

-   Systemeigene E-Mail-App unter Android 4 oder höher

## Unterstützung für PCs
>[!IMPORTANT]
>Bedingter Zugriff für PCs ist nicht für alle Kunden, Intune derzeit verfügbar. Wenn Sie bereits bedingten Zugriff für PCs verwenden, brauchen Sie keine Maßnahmen ergreifen. Sie können weiterhin verwenden.
Wenn Sie keine Richtlinien für bedingten Zugriff für PCs erstellt haben, müssen Sie eine Anforderung für den Zugriff.  Sie finden weitere Informationen zu bekannten Problemen sowie für den Zugriff auf diese Funktion auf die [connect-Website](http://go.microsoft.com/fwlink/?LinkId=761472)

Die **Mail** Anwendung unter Windows 8 und höher (bei Registrierung mit [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)])

## <a name="BKMK_enableXchngOnprem"></a>Konfigurieren Sie eine Richtlinie für bedingten Zugriff

1.  In der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com), wählen Sie **Richtlinie** & Gt; **Bedingter Zugriff** & Gt; **Richtlinie für lokales Exchange**.
![IntuneSA5aSelectExchOnPremPolicy](../media/IntuneSA5aSelectExchOnPremPolicy.png)

2.  Konfigurieren Sie die Richtlinie mit den benötigten Einstellungen.
![IntuneSA5bExchangeOnPremPolicy](../media/IntuneSA5bExchangeOnPremPolicy.png)

  - **Blockieren von e-Mail-apps auf lokales Exchange zugreifen, wenn das Gerät nicht konform oder nicht bei Windows Intune angemeldet ist:** Wenn Sie diese Option aktivieren, Geräte, die nicht von verwaltet werden [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], oder Sie sind nicht kompatibel mit einer Kompatibilität Richtlinie bereitgestellt wurde der Zugriff auf Exchange-Dienste blockiert werden. <need to verify this: unless they have been defined as exempt>

  - **Außerkraftsetzung der Regel Standard - immer zulassen registrierte und kompatible Geräte auf Exchange zugreifen:** wenn Sie diese Option aktivieren, Geräte, die in Intune registriert und kompatibel mit den Richtlinien konformen sind auf Exchange zugreifen dürfen.  
  Außerkraftsetzungen für diese die **Standardregel**, das bedeutet, dass selbst wenn Sie festlegen, die **Standardregel** zu isolieren oder den Zugriff, registrierte und kompatible Geräte werden auf Exchange zugreifen können.

  - **Zielgruppen:** Wählen Sie die [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] von Benutzergruppen, die ihr Gerät mit registrieren müssen [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] auf Exchange zugreifen können.

  - **Ausgenommene Gruppen:**Wählen Sie die [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] von Benutzergruppen, die von der Richtlinie für bedingten Zugriff ausgenommen werden. In dieser Liste Einstellungen überschreiben die Optionen in der **Zielgruppen** Liste.

  - **Plattformausnahmen:** auswählen **Regel hinzufügen** eine Regel konfigurieren, die definiert die Zugriffsebenen für mobile gerätefamilien und Modelle. Da diese Geräte eines beliebigen Typs sein können, können Sie auch konfigurieren, Gerätetypen, die von nicht unterstützt werden [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

  - **Standardregel:** für ein Gerät, das durch keine der anderen Regeln abgedeckt wird, können Sie festlegen, dass es auf Exchange zugreifen, blockiert oder unter Quarantäne gestellt wird. Wenn Sie die Regel so festlegen, dass der Zugriff gewährt wird, wird iOS-, Windows- und Samsung Knox-Geräten, die registriert und kompatibel sind, der E-Mail-Zugriff automatisch gewährt. Der Endbenutzer muss keinen Prozess durchlaufen, um an seine E-Mails zu gelangen.  Auf Android-Geräte, die nicht Knox-basiert sind, erhalten Endbenutzer eine Quarantäne-E-Mail, die eine exemplarische Vorgehensweise zur Überprüfung der Registrierung und Kompatibilität enthält, die ausgeführt werden muss, bevor der Zugriff auf die E-Mail erfolgen kann. Wenn Sie die Regel so festlegen, dass der Zugriff blockiert oder isoliert wird, wird der Zugriff aller Geräte auf Exchange blockiert, unabhängig davon, ob sie bereits bei Intune registriert sind oder nicht. Um zu verhindern, dass registrierte und kompatible Geräte durch diese Regel beeinträchtigt wird, überprüfen Sie die **Standard Regel außer Kraft setzen.**
>[!TIP]
>Wenn Sie beabsichtigen, zuerst alle Geräte zu blockieren, bevor Sie den Zugriff auf E-Mail gewähren, kann es nützlich sein, die Regel „Zugriff blockieren“ oder „Isolieren“ zu aktivieren. Die Standardregel gilt für alle Gerätetypen, sodass Gerätetypen, die Sie als plattformausnahmen und das Konfigurieren von nicht unterstützt werden [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] sind ebenfalls betroffen.

  - **Benachrichtigung:** zusätzlich zu der von Exchange gesendeten e-Mail sendet Intune eine e-Mail, die Sie konfigurieren können, die Schritte zum Entsperren des Geräts enthält. Sie können die Standardnachricht bearbeiten und den Text mithilfe von HTML-Tags formatieren. Da die Benachrichtigungs-E-Mail von Intune mit den Lösungsanweisungen an das Exchange-Postfach des Benutzers gesendet wird, kann es vorkommen, dass das Gerät blockiert wird, bevor der Benutzer die E-Mail-Nachricht erhält. In diesem Fall besteht die Möglichkeit, die Nachricht über ein freigeschaltetes Gerät oder eine andere Exchange-Zugriffsmethode anzuzeigen. Dies gilt insbesondere, wenn die **Standardregel** Blockieren oder unter Quarantäne gestellt festgelegt ist.  In diesem Fall müssen die Endbenutzer wechseln zu ihrer app-Store Herunterladen der Microsoft-Unternehmensportal-app und ihr Gerät registrieren. Dies gilt für iOS-, Windows- und Samsung Knox-Geräte.  Für Android-Geräte, die nicht Knox basieren, müssen IT-Administrator senden der Quarantäne-e-Mail an eine alternative e-Mail-Adresse Firma, die der Endbenutzer hat auf ihr Gerät blockiert, um die Registrierung und Compliance abzuschließen kopieren. |
  > [!NOTE]
  > Damit die Benachrichtigungs-E-Mail in Exchange gesendet werden kann, müssen Sie das dafür verwendete Konto entsprechend konfigurieren.
  >
  > Weitere Informationen finden Sie unter [Konfigurieren Sie Microsoft Intune lokalen Connector für lokales oder gehostetes Exchange](../Topic/Mobile-device-management-with-Exchange-ActiveSync-and-Microsoft-Intune.md#bkmk_EX_OP).

3.  Wenn Sie fertig sind, wählen Sie **Speichern**.

-   Die Richtlinie für bedingten Zugriff wird sofort wirksam und muss nicht explizit bereitgestellt werden.

-   Nachdem ein Benutzer ein Exchange ActiveSync-Profil eingerichtet hat, kann es 1 bis 3 Stunden dauern, bis das Gerät blockiert wird (wenn es nicht von [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] verwaltet wird).

-   Wenn ein blockierter Benutzer das Gerät anschließend bei [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] registriert (oder die Nichtkompatibilität behebt), wird der E-Mail-Zugriff innerhalb von zwei Minuten entsperrt.

-   Wenn der Benutzer das Gerät bei [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] deregistriert, kann es 1 bis 3 Stunden dauern, bis das Gerät blockiert wird.

## Nächste Schritte
[Einschränken des Zugriffs auf SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

[Einschränken des Zugriffs auf Skype for Business Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)


### Weitere Informationen:
[Einschränken des Zugriffs auf Exchange Online] (Zugriff beschränken To-exchange-online-with-microsoft-intune.md)

[Einschränken des Zugriffs auf die neuen Exchange Online Dedicated] (Zugriff beschränken To-new-exchange-online-dedicated-with-microsoft-intune.md)

[Einschränken des Zugriffs auf ältere Exchange Online Dedicated] (Zugriff beschränken To-legacy-exchange-online-dedicated-with-microsoft-intune.md)


<!--HONumber=Mar16_HO4-->


