---
title: Behandeln von Problemen mit der mobilen Anwendungsverwaltung | Microsoft Docs
description: "Dieses Thema enthält einige Tipps zur Behandlung von Problemen bei Bereitstellungen mit bedingtem Zugriff."
keywords: 
author: NathBarn
ms.author: oldang
manager: angerobe
ms.date: 09/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
translationtype: Human Translation
ms.sourcegitcommit: d50a5751a5afd987196336e9443dc5a429a283fd
ms.openlocfilehash: b333c0f5097fec38bf0dd78726a028fd7aaccd2f


---

# <a name="troubleshoot-mobile-application-management"></a>Problembehandlung der Verwaltung von mobilen Geräten

Wenn bei der mobilen Anwendungsverwaltung mit Intune Probleme auftreten, beginnen Sie hier. Dieses Thema behandelt einige allgemeine Probleme und Fragen, die bei Ihnen auftreten könnten, und stellt Lösungen und Antworten bereit.

## <a name="common-it-administrator-issues"></a>Allgemeine Probleme von IT-Administratoren

1. **Problem:** Eine App-Schutzrichtlinie ohne im Azure-Portal vorgenommene Geräteanmeldung wird auf iOS- und Android-Geräten nicht auf die Skype for Business-App angewendet.

  **Lösung**: Skype for Business muss für moderne Authentifizierung eingerichtet werden.  Führen Sie die Anweisungen in [Enable your tenant for modern authentication (Aktivieren Ihres Mandanten für moderne Authentifizierung)](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) aus, um moderne Authentifizierung für Skype einzurichten.

2. **Problem:** App-Schutzrichtlinien werden für keinen Benutzer und auf keine [unterstützte Office-App](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) angewendet.

  **Lösung**: Vergewissern Sie sich, dass der Benutzer für Intune lizenziert ist und dass die Office-Apps als Ziel einer bereitgestellten App-Schutzrichtlinie festgelegt sind. Es kann bis zu 8 Stunden dauern, bis eine neu bereitgestellte App-Schutzrichtlinie angewendet wird.

3. **Problem:** Der IT-Administratorbenutzer kann im Azure-Portal keine App-Schutzrichtlinien konfigurieren.

  **Lösung**:

  Folgende Benutzerrollen haben Zugriff auf das Azure-Portal:

  - Globaler Administrator, den Sie im [Office-Portal](http://portal.office.com/) einrichten können.
  - Besitzer, den Sie im [Azure-Portal](https://portal.azure.com/) einrichten können.
  - Mitwirkender, den Sie im [Azure-Portal](https://portal.azure.com/) einrichten können.<br>

  Hilfe zum Einrichten dieser Rollen finden Sie unter [Vorbereiten der Konfiguration von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md).

4. **Problem:** In den Berichten der Verwaltungskonsole werden keine Benutzerkonten angezeigt, für die vor Kurzem eine App-Schutzrichtlinie bereitgestellt wurde.

  **Lösung**: Wenn ein Benutzer neu als Ziel einer App-Schutzrichtlinie festgelegt worden ist, kann es bis zu 24 Stunden dauern, bis dieser Benutzer in Berichten als Zielbenutzer aufgeführt wird.

5. **Problem:** Änderungen/Aktualisierungen von Richtlinien werden u. U. erst nach 8 Stunden wirksam.  

  **Lösung**: Endbenutzer können sich bei der App abmelden und wieder anmelden, um die Synchronisierung mit dem Dienst zu erzwingen.  

6. **Problem:** Die App-Schutzrichtlinie wird nicht auf Apple DEP-Geräte angewendet.

  **Lösung**: Achten Sie darauf, User Affinity mit Apple DEP (Device Enrollment Program) zu verwenden. User Affinity ist für alle Apps erforderlich, die Benutzerauthentifizierung unter DEP benötigen.
Weitere Informationen zur iOS-DEP-Registrierung finden Sie unter [Registrieren unternehmenseigener iOS-Geräte mithilfe des Programm zur Geräteregistrierung (Device Enrollment Program, DEP)](../deploy-use/ios-device-enrollment-program-in-microsoft-intune.md).

## <a name="common-end-user-issues"></a>Häufige Probleme von Endbenutzern

### <a name="issues-on-ios"></a>Problemen unter iOS

Dialog/Fehlermeldung | Ursache | Wartung |
-- | --- | --- |
**App nicht eingerichtet**: Diese App wurde für Sie nicht zur Verwendung eingerichtet. Wenden Sie sich an Ihren IT-Administrator, um Unterstützung zu erhalten. | Fehler bei der Ermittlung der erforderlichen App-Schutzrichtlinie für die App. |Stellen Sie sicher, dass eine iOS-App-Schutzrichtlinie für die Sicherheitsgruppe des Benutzers bereitgestellt und diese App als Ziel festgelegt wurde.
**Willkommen bei Intune Managed Browser**: Diese App funktioniert am besten, wenn sie über Microsoft Intune verwaltet wird. Mit dieser App können Sie jederzeit das Web durchsuchen. Wenn sie über Microsoft Intune verwaltet wird, können Sie auf zusätzliche Features zum Schutz von Daten zugreifen. | Fehler bei der Ermittlung der erforderlichen App-Schutzrichtlinie für die Intune Managed Browser-App. <br><br>Der Benutzer kann die App trotzdem verwenden, um das Web zu durchsuchen, aber die App wird nicht von Intune verwaltet. | Stellen Sie sicher, dass eine iOS-App-Schutzrichtlinie für die Sicherheitsgruppe des Benutzers bereitgestellt und die Intune Managed Browser-App als Ziel festgelegt wurde.
**Fehler bei der Anmeldung**: Eine Anmeldung ist zurzeit nicht möglich. Wiederholen Sie den Vorgang zu einem späteren Zeitpunkt. | Fehler bei Registrierung des Benutzers beim MAM-Dienst nach dem Versuch des Benutzers, sich mit seinem Geschäfts-, Schul- oder Unikonto anzumelden. | Stellen Sie sicher, dass eine iOS-App-Schutzrichtlinie für die Sicherheitsgruppe des Benutzers bereitgestellt und diese App als Ziel festgelegt wurde.
**Konto nicht eingerichtet**: Ihre Organisation hat Ihr Konto nicht für den Zugriff auf Geschäfts-, Schul- oder Unidaten eingerichtet. Wenden Sie sich an Ihren IT-Administrator, um Hilfe zu erhalten. | Das Benutzerkonto verfügt über keine Windows Intune A Direct-Lizenz. | Stellen Sie sicher, dass dem Konto des Benutzers im [Office-Portal](http://portal.office.com) eine Intune-Lizenz zugewiesen ist.
**Gerät nicht kompatibel**: Diese App kann nicht verwendet werden, weil Sie ein Gerät mit Jailbreak verwenden. Wenden Sie sich an Ihren IT-Administrator, um Unterstützung zu erhalten. | Intune hat festgestellt, dass der Benutzer ein Gerät mit Jailbreak verwendet. | Setzen Sie das Gerät auf die Werkseinstellungen zurück. Führen Sie [diese Anweisungen](https://support.apple.com/en-us/HT201274) über die Apple-Support-Website aus.
**Internetverbindung erforderlich**: Sie benötigen eine Internetverbindung, um zu überprüfen, ob Sie diese App verwenden dürfen. | Das Gerät ist nicht mit dem Internet verbunden. | Verbinden Sie das Gerät mit einem WLAN oder Datennetzwerk.
**Unbekannter Fehler**: Versuchen Sie, die App neu zu starten. Wenn das Problem weiterhin besteht, wenden Sie sich an Ihren IT-Administrator, um Hilfe zu erhalten. | Ein unbekannter Fehler ist aufgetreten. | Warten Sie eine gewisse Zeit, und versuchen Sie es erneut. Wenn der Fehler weiterhin auftritt, erstellen Sie [hier](/how-to-get-support-for-microsoft-intune.md) ein Supportticket mit Intune.
**Zugriff auf Daten Ihrer Organisation**: Das angegebene Geschäfts-, Schul oder Unikonto hat keinen Zugriff auf diese App. Sie müssen sich möglicherweise mit einem anderen Konto anmelden. Wenden Sie sich an Ihren IT-Administrator, um Unterstützung zu erhalten. | Intune erkennt, dass der Benutzer versucht hat, sich mit einem anderen als dem bei MAM registrierten Geschäfts-, Schul- oder Unikonto für das Gerät anzumelden. Pro Gerät kann von MAM jeweils nur ein Geschäfts-, Schul- oder Unikonto verwaltet werden. | Fordern Sie den Benutzer auf, sich mit dem Konto anzumelden, mit dessen Benutzername die Anmeldeseite zuvor aufgefüllt wurde. <br> <br> Alternativ kann der Benutzer sich mit dem neuen Geschäfts-, Schul- oder Unikonto anmelden und das vorhandene, bei MAM registrierte Konto entfernen.
**Verbindungsproblem**: Es ist ein unerwartetes Verbindungsproblem aufgetreten. Überprüfen Sie Ihre Verbindung, und versuchen Sie es erneut.  |  Unerwarteter Fehler. | Warten Sie eine gewisse Zeit, und versuchen Sie es erneut. Wenn der Fehler weiterhin auftritt, erstellen Sie [hier](/how-to-get-support-for-microsoft-intune.md) ein Supportticket mit Intune.
**Warnung**: Diese App kann nicht mehr verwendet werden. Wenden Sie sich an Ihren IT-Administrator, um weitere Informationen zu erhalten. | Fehler beim Überprüfen des App-Zertifikats. | Stellen Sie sicher, dass die App-Version auf dem neuesten Stand ist. <br><br> Installieren Sie die App neu.
**Fehler**: Diese App hat ein Problem festgestellt und muss geschlossen werden. Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an Ihren IT-Administrator. | Fehler beim Lesen der PIN der MAM-App aus dem Apple iOS-Schlüsselbund. | Starten Sie das Gerät neu. Stellen Sie sicher, dass die App-Version auf dem neuesten Stand ist. <br><br> Installieren Sie die App neu.


### <a name="issues-on-android"></a>Probleme unter Android

Dialog/Fehlermeldung | Ursache | Wartung |
-- | --- | --- |
**App nicht eingerichtet**: Diese App wurde für Sie nicht zur Verwendung eingerichtet. Wenden Sie sich an Ihren IT-Administrator, um Unterstützung zu erhalten. | Fehler bei der Ermittlung der erforderlichen App-Schutzrichtlinie für die App. |Stellen Sie sicher, dass eine iOS-App-Schutzrichtlinie für die Sicherheitsgruppe des Benutzers bereitgestellt und diese App als Ziel festgelegt wurde.
**Fehler beim Starten der App**: Beim Starten Ihrer App ist ein Problem aufgetreten. Versuchen Sie, die App oder die Intune-Unternehmensportal-App zu aktualisieren. Wenn Sie Hilfe benötigen, wenden Sie sich an Ihren IT-Administrator. | Intune hat eine gültige App-Schutzrichtlinie für die App gefunden, aber die App stürzt während der Initialisierung von MAM ab. | Stellen Sie sicher, dass die App-Version auf dem neuesten Stand ist. <br><br> Stellen Sie sicher, dass die Intune-Unternehmensportal-App auf dem Gerät installiert und auf dem neuesten Stand ist. <br><br> Wenn der Fehler weiterhin auftritt, verwenden Sie die Unternehmensportal-App, um Protokolle an Intune zu senden, oder erstellen Sie [hier](/how-to-get-support-for-microsoft-intune.md) ein Supportticket.
**Keine Apps gefunden**: Auf diesem Gerät gibt es keine Apps, die von Ihrer Organisation zum Öffnen dieser Inhalte zugelassen werden. Wenden Sie sich an Ihren IT-Administrator, um Unterstützung zu erhalten. | Der Benutzer hat versucht, Geschäfts-, Schul- oder Unidaten mit einer anderen App zu öffnen, aber Intune kann keine anderen verwalteten Apps finden, die zum Öffnen der Daten zulässig sind. | Vergewissern Sie sich, dass eine Android-App-Schutzrichtlinie für die Sicherheit des Benutzers bereitgestellt wird und als Ziel mindestens eine andere MAM-fähige App festgelegt ist, die die betreffenden Daten öffnen kann.
**Fehler bei der Anmeldung**: Versuchen Sie erneut, sich anzumelden. Wenn das Problem weiterhin besteht, wenden Sie sich an Ihren IT-Administrator, um Hilfe zu erhalten. | Fehler bei der Authentifizierung des Kontos, mit dem der Benutzer versucht hat, sich anzumelden. | Vergewissern Sie sich, dass sich der Benutzer mit dem bereits beim Intune MAM-Dienst registrierten Geschäfts-, Schul- oder Unikonto anmeldet (dem ersten Geschäfts-, Schul- oder Unikonto, das erfolgreich bei dieser App registriert wurde). <br><br> Löschen Sie die Daten der App. <br><br> Stellen Sie sicher, dass die App-Version auf dem neuesten Stand ist. <br><br> Stellen Sie sicher, dass die Version des Unternehmensportals auf dem neuesten Stand ist.
**Internetverbindung erforderlich**: Sie benötigen eine Internetverbindung, um zu überprüfen, ob Sie diese App verwenden dürfen. | Das Gerät ist nicht mit dem Internet verbunden. | Verbinden Sie das Gerät mit einem WLAN oder Datennetzwerk.
**Gerät nicht kompatibel**: Sie können diese App nicht verwenden, da bei Ihrem Gerät die Nutzungsbeschränkungen entfernt wurden. Wenden Sie sich an Ihren IT-Administrator, um Unterstützung zu erhalten. | Intune hat festgestellt, dass der Benutzer ein Gerät verwendet, bei dem die Nutzungsbeschränkungen entfernt wurden. | Setzen Sie das Gerät auf die Werkseinstellungen zurück.
**Konto nicht eingerichtet**: Diese App muss mit Microsoft Intune verwaltet werden, Ihr Konto wurde jedoch noch nicht eingerichtet. Wenden Sie sich an Ihren IT-Administrator, um Unterstützung zu erhalten. | Das Benutzerkonto verfügt über keine Windows Intune A Direct-Lizenz. | Stellen Sie sicher, dass dem Konto des Benutzers im [Office-Portal](http://portal.office.com) eine Intune-Lizenz zugewiesen ist.
**Registrierung der App nicht möglich**: Diese App muss mit Microsoft Intune verwaltet werden, eine Registrierung der App ist momentan jedoch nicht möglich. Wenden Sie sich an Ihren IT-Administrator, um Unterstützung zu erhalten. | Bei der automatischen Registrierung der App beim MAM-Dienst tritt ein Fehler auf, wenn eine App-Schutzrichtlinie erforderlich ist. | Löschen Sie die Daten der App. <br><br> Senden Sie Protokolle über die Unternehmensportal-App an Intune, oder erstellen Sie [hier](/how-to-get-support-for-microsoft-intune.md) ein Supportticket.





### <a name="see-also"></a>Weitere Informationen:
- [Überprüfen des Setups für die Verwaltung Ihrer mobilen Anwendungen](../deploy-use/validate-mobile-application-management.md)
- [Vorbereiten der Konfiguration von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


