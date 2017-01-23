---
title: "Beschränken des E-Mail-Zugriffs auf Exchange lokal | Microsoft-Dokumentation"
description: "Schützen und steuern Sie den Zugriff auf Unternehmens-E-Mail in Exchange lokal mit bedingtem Zugriff."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a55071f5-101e-4829-908d-07d3414011fc
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 51e06bafef761eaf06d35343b459262524ad9168
ms.openlocfilehash: c090d4bbc539d4174deee139e51242bae94feeb3


---

# <a name="restrict-email-access-to-exchange-on-premises-and-legacy-exchange-online-dedicated-with-intune"></a>Beschränken des E-Mail-Zugriffs auf lokale Exchange- und ältere Exchange Online Dedicated-Umgebungen mit Intune

> [!NOTE]
> Wenn Sie über eine Exchange Online Dedicated-Umgebung verfügen und herausfinden müssen, ob es sich um die neue oder die ältere Konfiguration handelt, wenden Sie sich an Ihren Kundenbetreuer.


Um den E-Mail-Zugriff auf lokales Exchange oder Ihre ältere Exchange Online Dedicated-Umgebung zu steuern, können Sie den bedingten Zugriff für lokales Exchange in Microsoft Intune konfigurieren.
Weitere Informationen zur Funktionsweise des bedingten Zugriffs finden Sie im Artikel [Beschränken des Zugriffs auf E-Mail- und Office 365-Dienste]( restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

**Bevor** Sie den bedingten Zugriff konfigurieren können, müssen Sie Folgendes überprüfen:

-   Bei Ihrer Exchange-Version muss es sich um **Exchange 2010 oder höher** handeln. Exchange Server-Clientzugriffsserver-Arrays werden unterstützt.

-   Sie müssen den **lokalen Exchange Connector** verwenden, der [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] mit dem lokalen Exchange verbindet. Auf diese Weise können Sie Geräte über die [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Konsole verwalten. Informationen zum Connector finden Sie unter [Lokaler Exchange-Connector für Intune](intune-on-premises-exchange-connector.md).

    -   Der lokale Exchange Connector, der Ihnen in der Intune-Konsole zur Verfügung steht, ist spezifisch für Ihren Intune-Mandanten und kann mit keinem anderen Mandanten verwendet werden. Es wird empfohlen sicherzustellen, dass der Exchange-Connector für Ihren Mandanten **nur auf einem Computer** installiert ist.

        Sie können den Connector aus der Intune-Verwaltungskonsole herunterladen. Eine exemplarische Vorgehensweise zum Konfigurieren des lokalen Exchange-Connectors finden Sie unter [Konfigurieren des lokalen Exchange-Connectors für lokales oder gehostetes Exchange](intune-on-premises-exchange-connector.md).

    -   Sie können den Connector auf jedem Computer installieren, solange der jeweilige Computer mit dem Exchange-Server kommunizieren kann.

    -   Der Connector unterstützt die **Exchange-Clientzugriffsserver-Umgebung**. Technisch können Sie nach Wunsch den Connector auf dem Exchange-Clientzugriffsserver direkt installieren. Allerdings wird dies nicht empfohlen, da dadurch die Last auf dem Server erhöht wird. Sie müssen den Connector so konfigurieren, dass er mit einem der Exchange-Clientzugriffsserver kommuniziert.

-   Sie müssen **Exchange ActiveSync** für die zertifikatbasierte Authentifizierung oder die Eingabe von Anmeldeinformationen durch Benutzer konfigurieren.

Wenn Sie Richtlinien für bedingten Zugriff konfigurieren und auf einen Benutzer anwenden, muss das **Gerät**, das der Benutzer zum Abrufen von E-Mails verwendet, folgende Voraussetzungen erfüllen:

-  Es muss ein in die Domäne eingebundener PC oder bei [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] **registriert** sein.

-  **Es muss in Azure Active Directory registriert sein**. Darüber hinaus muss die Exchange ActiveSync-ID des Clients in Azure Active Directory registriert sein.

  Der Azure Active Directory-Geräteregistrierungsdienst wird automatisch für Intune- und Office 365-Kunden aktiviert. Kunden, die bereits den AD FS Device Registration Service bereitgestellt haben, sehen keine registrierten Geräte im lokalen Active Directory. **Dies gilt nicht für Windows-PCs und Windows Phone-Geräte.**

-   Es muss mit allen für das Gerät festgelegten [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Kompatibilitätsrichtlinien **kompatibel** sein.

Das folgende Diagramm veranschaulicht den Ablauf, der von den Richtlinien für bedingten Zugriff für die lokale Exchange-Umgebung verwendet wird, um zu bewerten, ob Geräte zugelassen oder blockiert werden.

![Diagramm mit den Entscheidungspunkten, die bestimmen, ob der Zugriff eines Geräts auf lokales Exchange zugelassen oder blockiert wird](../media/ConditionalAccess8-2.png)

Wenn eine Bedingung für bedingten Zugriff nicht erfüllt wird, erhält der Benutzer bei der Anmeldung die folgenden Meldungen:

- Wenn das Gerät nicht bei [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] oder in Azure Active Directory registriert ist, wird eine Meldung mit Anweisungen zum Installieren der Unternehmensportal-App, zum Registrieren des Geräts und zum Aktivieren des E-Mail-Zugriffs angezeigt. Dieser Prozess verknüpft auch die Exchange ActiveSync-ID mit dem Eintrag des Geräts in Azure Active Directory.

-   Wenn das Gerät nicht kompatibel ist, wird eine Meldung angezeigt, die den Benutzer zur [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Unternehmensportalwebsite oder zur Unternehmensportal-App weiterleitet. Dort findet der Benutzer Informationen zum Problem und zur Lösung.

## <a name="support-for-mobile-devices"></a>Unterstützung für mobile Geräte
Die folgenden Betriebssysteme werden unterstützt:
-   Windows Phone 8.1 und höher.

-   Die native E-Mail-App unter iOS.

-   Exchange ActiveSync-E-Mail-Clients wie Gmail unter Android 4 oder höher.
- Exchange ActiveSync-E-Mail-Clients für **Android for Work-Geräte:** Nur **Gmail**- und **Nine Work**-Apps im **Arbeitsprofil** werden auf Android for Work-Geräten unterstützt. Damit der bedingte Zugriff unter Android for Work funktioniert, müssen Sie ein E-Mail-Profil für die Gmail- oder Nine Work-App sowie diese Apps als erforderliche Installation bereitstellen. 

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

> [!NOTE]
> Die Microsoft Outlook-App unter Android und iOS wird nicht unterstützt.

## <a name="support-for-pcs"></a>Unterstützung für PCs
Folgendes wird unterstützt:
-   Die **E-Mail**-Anwendung unter Windows 8.1 und höher (bei Registrierung des PC bei [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)])

##  <a name="configure-a-conditional-access-policy"></a>Konfigurieren einer Richtlinie für bedingten Zugriff

1.  Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) auf **Richtlinie** > **Bedingter Zugriff** > **Richtlinie für lokales Exchange**.
![IntuneSA5aSelectExchOnPremPolicy](../media/IntuneSA5aSelectExchOnPremPolicy.png)

2.  Konfigurieren Sie die Richtlinie mit den Einstellungen, die Sie benötigen: ![Screenshot der Seite mit der Richtlinie für lokales Exchange](../media/IntuneSA5bExchangeOnPremPolicy.png)

  - **Blockieren Sie den lokalen Exchange-Zugriff von E-Mail-Apps, wenn das Gerät nicht kompatibel oder nicht bei Microsoft Intune registriert ist**: Bei Auswahl dieser Option wird der Zugriff auf Exchange-Dienste für Geräte blockiert, die nicht von [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] verwaltet werden oder eine Kompatibilitätsrichtlinie nicht erfüllen.

  - **Standardregelüberschreibung – Den Zugriff auf Exchange durch registrierte und kompatible Geräte immer zulassen**: Wenn Sie diese Option aktivieren, dürfen Geräte, die bei Intune angemeldet sind und die Kompatibilitätsrichtlinie erfüllen, auf Exchange zugreifen.
  Diese Regel setzt die **Standardregel** außer Kraft, was bedeutet, dass, selbst wenn Sie die **Standardregel** so festlegen, dass der Zugriff isoliert bzw. blockiert wird, registrierte und kompatible Geräte weiterhin auf Exchange zugreifen können.

  - **Zielgruppen**: Wählen Sie die [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Benutzergruppen aus, die ihr Gerät bei [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] registrieren müssen, um auf Exchange zugreifen zu können.

  - **Ausgenommene Gruppen**: Wählen Sie die [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-Benutzergruppen aus, die von der Richtlinie für bedingten Zugriff ausgenommen werden sollen. Benutzer in dieser Liste werden ausgenommen, auch wenn sie auch in der Liste **Zielgruppen** befinden.

  - **Plattformausnahmen**: Wählen Sie **Regel hinzufügen** aus, um eine Regel zu konfigurieren, die Zugriffsebenen für angegebene mobile Gerätefamilien und -modelle definiert. Da diese Geräte einen beliebigen Typ aufweisen können, können Sie auch Gerätetypen konfigurieren, die nicht von [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] unterstützt werden.

  - **Standardregel**: Bei Geräten, die durch keine der anderen Regeln abgedeckt werden, können Sie auswählen, ob der Zugriff auf Exchange zugelassen oder blockiert oder das Gerät unter Quarantäne gestellt werden soll. Wenn Sie die Regel so festlegen, dass der Zugriff zugelassen wird, wird iOS-, Windows- und Samsung KNOX-Geräten, die registriert und kompatibel sind, der E-Mail-Zugriff automatisch gewährt. Benutzer müssen keinen Prozess durchlaufen, um an ihre E-Mails zu gelangen.

        Auf Android-Geräten, die nicht unter Samsung KNOX ausgeführt werden, erhalten Benutzer eine Quarantäne-E-Mail. Diese Mail enthält eine exemplarische Vorgehensweise, mit der die Benutzer die Registrierung und Kompatibilität überprüfen müssen, bevor der Zugriff auf die E-Mail erfolgen kann. Wenn Sie die Regel so festlegen, dass der Zugriff blockiert wird oder Geräte isoliert werden, wird der Zugriff aller Geräte auf Exchange blockiert, unabhängig davon, ob sie bereits bei Intune registriert sind oder nicht. Um zu verhindern, dass registrierte und kompatible Geräte von dieser Regel betroffen sind, aktivieren Sie die Option **Standardregelüberschreibung**.
>[!TIP]
>Wenn Sie beabsichtigen, zuerst alle Geräte zu blockieren, bevor Sie den Zugriff auf E-Mail gewähren, wählen Sie die Regel „Zugriff blockieren“ oder „Quarantäne“ aus. Die Standardregel gilt für alle Gerätetypen, sodass Gerätetypen, die Sie als Plattformausnahmen konfiguriert haben und die nicht von [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] unterstützt werden, ebenfalls betroffen sind.

  - **Benutzerbenachrichtigung**: Zusätzlich zu der von Exchange gesendeten Benachrichtigungs-E-Mail sendet Intune eine E-Mail mit Schritten zum Entsperren des Geräts. Sie können die Standardnachricht bearbeiten, um Sie an Ihre Bedürfnisse anzupassen. Da die Benachrichtigungs-E-Mail von Intune mit den Lösungsanweisungen an das Exchange-Postfach des Benutzers gesendet wird, kann es vorkommen, dass das Gerät blockiert wird, bevor der Benutzer die E-Mail-Nachricht erhält. In diesem Fall besteht die Möglichkeit, die Nachricht über ein freigeschaltetes Gerät oder eine andere Exchange-Zugriffsmethode anzuzeigen.

        This is especially true when the **Default Rule** is set to block or quarantine. In this case, the user has to go to their app store, download the Microsoft Company Portal app, and enroll their device. This is applicable to iOS, Windows, and Samsung KNOX devices. For devices that don't run Samsung KNOX, you need to send the quarantine email to an alternate email account. The user has to copy the email to their blocked device to complete the enrollment and compliance process.
  > [!NOTE]
  > Damit die Benachrichtigungs-E-Mail von Exchange gesendet werden kann, müssen Sie das Konto angeben, das dafür verwendet werden soll.
  >
  > Weitere Informationen finden Sie unter [Konfigurieren des lokalen Exchange Connectors für lokales oder gehostetes Exchange](intune-on-premises-exchange-connector.md).

3.  Wenn Sie fertig sind, wählen Sie **Speichern** aus.

-   Die Richtlinie für bedingten Zugriff wird sofort wirksam und muss nicht explizit bereitgestellt werden.

-   Nachdem ein Benutzer ein Exchange ActiveSync-Profil eingerichtet hat, kann es ein bis drei Stunden dauern, bis das Gerät blockiert wird (wenn es nicht von [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] verwaltet wird).

-   Wenn ein blockierter Benutzer das Gerät anschließend bei [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] registriert und die Nichtkompatibilität behebt, wird der E-Mail-Zugriff innerhalb von zwei Minuten entsperrt.

-   Wenn der Benutzer das Gerät bei [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] deregistriert, kann es ein bis drei Stunden dauern, bis das Gerät blockiert wird.

**Beispielszenarien für die Konfiguration von Richtlinien für bedingten Zugriff zur Beschränkung des Gerätezugriffs[ finden Sie unter ](restrict-email-access-example-scenarios.md)Beispielszenarien für die Beschränkung des E-Mail-Zugriffs**.

## <a name="next-steps"></a>Nächste Schritte
-   [Beschränken des Zugriffs auf SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

-   [Beschränken des Zugriffs auf Skype for Business Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


