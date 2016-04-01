---
title: Beispielszenarien für den e-Mail-Zugriff einschränken | Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 09c82f5d-531c-474d-add6-784c83f96d93
author: karthikaraman
---
# Einschränken des e-Mail-Zugriffs mit Microsoft Intune: Beispielszenarien

## Alle iOS-Geräte, die auf lokales Exchange zugreifen, müssen von Intune verwaltet werden
In diesem Beispiel verwendet die Organisation nur Geräte mit iOS. Alle diese Geräte müssen durch [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] verwaltet werden, bevor sie auf Exchange zugreifen können.

Dazu muss in der Richtlinie für bedingten Zugriff Folgendes konfiguriert werden:

-   Wählen Sie die Option **Bedingte Zugriffsrichtlinie für Exchange Online aktivieren**aus.

-   Wählen Sie für Apps mit modernen Authentifizierung **iOS** für die Plattform aus.

-   Wählen Sie für Exchange ActiveSync-Apps **Anfordern, dass Mobilgeräte kompatibel sind**  aus, und blockieren Sie den Zugriff auf E-Mail auf Geräten, die nicht von [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]unterstützt werden.

-   Eine Plattformausnahme, die Geräten mit iOS erlaubt, auf Exchange zuzugreifen.

-   Eine Standardregel, die angibt, dass ein Gerät blockiert werden sollte, wenn es nicht durch andere Regeln abgedeckt wird.

Der folgende Ablauf wird verwendet, um zu entscheiden, welche Geräte auf Exchange zugreifen können:

![](./media/ConditionalAccess8-3.png)

## Android-Geräte können nicht auf Exchange lokal zugreifen. Alle anderen Geräte, die auf Exchange zugreifen, müssen von Intune verwaltet werden.
In diesem Beispiel möchte die Organisation Geräten mit Android nicht den Zugriff auf Exchange ermöglichen. Alle anderen unterstützten Geräte können auf Exchange zugreifen, solange sie von [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]verwaltet werden.

Dazu muss in der Richtlinie für bedingten Zugriff Folgendes konfiguriert werden:

-   Wählen Sie die Option **Bedingte Zugriffsrichtlinie für Exchange Online aktivieren**aus.

-   Eine Plattformausnahme, die verhindert, dass Geräte mit Android auf Exchange zugreifen.

-   Eine Standardregel, die angibt, dass ein Gerät zugelassen werden sollte, wenn es nicht durch andere Regeln abgedeckt wird.

Der folgende Ablauf wird verwendet, um zu entscheiden, welche Geräte auf Exchange zugreifen können:

![](./media/ConditionalAccess8-4.png)

## Exchange Online-Zugriff für Benutzer nicht konformer Geräte in einer angegebenen Active Directory-Sicherheitsgruppe blockieren. Geräte in einer anderen Sicherheitsgruppe ausnehmen
In diesem Szenario müssen alle Benutzer in der Active Directory-Sicherheitsgruppe **Accounting** am Zugriff auf Exchange Online gehindert werden, wenn das Gerät einer von Ihnen bereitgestellten Konformitätsrichtlinie nicht entspricht. Darüber hinaus müssen alle Benutzer in der Active Directory-Sicherheitsgruppe **Finance** von der Richtlinie ausgenommen werden, auch wenn sie ebenfalls in der Sicherheitsgruppe **Accounting** enthalten sind. Schließlich müssen alle Benutzer in dieser Gruppe, deren Geräte nicht von [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)]unterstützt werden, am Zugriff auf Exchange Online über dieses Gerät gehindert werden.

Dazu muss in der Richtlinie für bedingten Zugriff Folgendes konfiguriert werden:

-   Wählen Sie die Option **Bedingten Zugriff für Exchange Online aktivieren**aus.

-   Wählen Sie **Accounting** unter **Zielgruppen**aus.

-   Wählen Sie **Finance** unter **Ausgenommene Gruppen**aus.

-   Wählen Sie unter **Exchange ActiveSync-E-Mail-Apps**die Option **Anfordern, dass Mobilgeräte kompatibel sind**aus.

Der folgende Ablauf wird verwendet, um zu entscheiden, welche Geräte auf Exchange zugreifen können:

![](./media/ConditionalAccess8-5.png)


<!--HONumber=Mar16_HO4-->


