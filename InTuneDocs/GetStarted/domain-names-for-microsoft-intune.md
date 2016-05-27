---
# required metadata

title: Domänennamen für Microsoft Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c3c136f0-330d-432a-a91f-16f7dd097e55

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---



# Domänennamen für Microsoft Intune

Bevor Sie Microsoft Intune einrichten, lesen Sie dieses Thema und andere Anforderungen, die unter [Was Sie wissen sollten, bevor Sie Microsoft Intune starten](what-to-know-before-you-start-microsoft-intune.md) aufgeführt sind..

Wenn Sie Ihre Organisation für einen cloudbasierten Dienst von Microsoft wie Intune registrieren, erhalten Sie zunächst einen Domänennamen, der dem folgenden ähnelt: **contoso.onmicrosoft.com**. In diesem Beispiel ist **contoso** der Domänenname, den Sie bei der Registrierung ausgewählt haben, und **onmicrosoft.com** ist das Suffix, das den Konten zugewiesen wird, die Sie Ihrem Abonnement hinzufügen. Nach Abschluss des Registrierungsvorgangs können Sie diesen Domänennamen nicht mehr ändern. Als globaler Administrator können Sie jedoch eigene Domänennamen Ihrer Organisation zur Verwendung mit dem Dienst hinzufügen oder Domänen entfernen, die Sie zuvor hinzugefügt haben.

Wenn Sie die Standarddomäne „onmicrosoft“ verwenden, erhält jeder importierte Benutzer das Suffix **onmicrosoft.com** für seinen Benutzerprinzipalnamen (UPN).

Um einen eigenen anstelle des bei der Registrierung zugewiesenen Domänennamens zu verwenden, können Sie diesen Azure Active Directory hinzufügen. Nachdem Sie die Domäne hinzugefügt haben und überprüft wurde, dass Sie der Besitzer der Domäne sind, können Sie Konten und Gruppen mit dem Domänennamen erstellen, indem Sie DNS-Ressourceneinträge bei Ihrem DNS-Hostinganbieter ändern. Falls Sie einen benutzerdefinierten Domänennamen verwenden möchten, konfigurieren Sie den benutzerdefinierten Domänennamen für Ihr Abonnement, bevor Sie damit beginnen, Benutzer aus Ihrem lokalen Active Directory zu synchronisieren, um die Verwaltung der Benutzerkonten zu vereinfachen.

Das Konfigurieren von Domänennamen und DNS-Ressourceneinträgen für Intune erfolgt in der gleichen Weise wie für andere Azure Active Directory-Mandanten. Anweisungen finden Sie unter [Hinzufügen Ihres benutzerdefinierten Domänennamens zum Vereinfachen der Registrierung mithilfe von Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

### Weitere Informationen:
[Was Sie wissen sollten, bevor Sie Microsoft Intune starten](what-to-know-before-you-start-microsoft-intune.md)


<!--HONumber=May16_HO1-->


