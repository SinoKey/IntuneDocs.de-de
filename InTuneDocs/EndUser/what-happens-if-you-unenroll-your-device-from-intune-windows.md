---
Titel: Was geschieht, wenn Sie Ihr Gerät aus Intune Abmelden?
MS.Custom: Na
MS.Reviewer: Na
MS.Service: Microsoft Intune
MS.Suite: Na
MS.tgt_pltfrm: Na
MS.topic: Artikel
MS.AssetId: 
Autor: Staciebarker

# Was geschieht, wenn Sie Ihr Gerät aus Intune Abmelden?

Wenn Sie die Unternehmensportal-app von Ihrem Gerät deinstallieren, unenrolls es auch Ihres Geräts aus Intune. Weitere Informationen darüber, was geschieht verwenden Sie den Link, der den Typ des Geräts entspricht, die Sie verwenden.

- [Windows 10 8.1, Windows 8, Windows 7, Windows Vista](BKMK_what_happens_unenroll_win81_8_7_vista)
- [Windows 8.1 oder Windows Phone 8](BKMK_what_happens_unenroll_wp81)
- [Windows RT unter Windows 8.1 oder Windows RT](BKMK_what_happens_unenroll_win81_rt)


## <a name="BKMK_what_happens_unenroll_win81_8_7_vista">Windows 8.1, Windows 8, Windows 7, Windows Vista

-   Ihr Gerät wird nicht mehr im Unternehmensportal angezeigt, und Sie können keine apps mehr über das Unternehmensportal installieren.

-   Wenn die [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)]-Clientsoftware installiert ist, wird diese von Ihrem Computer entfernt.

-   Die [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] Endpoint Protection-Software wird von Ihrem Computer entfernt. Wenn auf dem Computer eine andere Virenschutzsoftware installiert ist und diese deaktiviert wurde, wird sie unter Umständen nach dem Entfernen von [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)] Endpoint Protection wieder aktiviert. Sie sollten Ihren Computer nach dem Entfernen aus dem Unternehmensportal überprüfen.

    > [!IMPORTANT]
    > Wenn die andere Virenschutzsoftware nicht wieder aktiviert wird oder keine andere Virenschutzsoftware installiert ist, bleibt der Computer unter Umständen anfällig für Viren und Malware.

-   Alle Einstellungen, die auf dem Gerät geändert wurden, als Sie es hinzugefügt (z. B. das Deaktivieren der Kamera nicht mehr angewendet wird).

-   Automatische Updates der Software bzw. Updates der Antivirensoftware vom [!INCLUDE[wit_nextref](./includes/wit_nextref_md.md)]-Dienst werden möglicherweise nicht mehr auf dem Computer empfangen. Der Computer kann jedoch je nach Konfiguration weiterhin Updates von Windows Server Update Services, Windows Update oder Microsoft Update empfangen.

Außerdem ist für Windows 8.1:

-   Sie können keine Unternehmens-Apps und Unternehmensdaten mehr auf dem Gerät verwenden.

-   In einigen Mail-Apps wie Windows Mail kann nicht mehr auf Unternehmens-E-Mails zugegriffen werden, die auf dem Gerät gespeichert sind.

-   Möglicherweise können Sie keine Verbindung zum Unternehmensnetzwerk über WiFi oder ein virtuelles privates Netzwerk herstellen.

-   Unter Umständen haben Sie auf dem Gerät keinen Zugriff mehr auf einige Unternehmensressourcen, z. B. Dateifreigaben oder interne Websites.

## <a name="BKMK_what_happens_unenroll_wp81">Windows Phone 8.1 oder Windows Phone 8

-   Unternehmensportal-app wird von Ihrem Gerät deinstalliert, was bedeutet, dass das Gerät nicht mehr im Unternehmensportal angezeigt und kann nicht zum Installieren von apps aus dem Unternehmensportal-app oder die Unternehmensportal-Website.

-   Sie können keine Unternehmens-Apps und Unternehmensdaten mehr auf dem Gerät verwenden.

-   Alle Einstellungen, die beim Hinzufügen des Geräts auf diesem geändert wurden, z. B. das Deaktivieren der Kamera oder die Anforderung einer bestimmten Kennwortlänge, werden unwirksam.

    > [!IMPORTANT]
    > Die einzige Ausnahme sind die Verschlüsselungsrichtlinien, die weiterhin wirksam sind. Wenn Unternehmensrichtlinie erforderlich, dass Windows Phone verschlüsselt werden, ist die einzige Möglichkeit, Ihr Telefon zu entschlüsseln Zurücksetzen Ihrer Telefon mithilfe der **Einstellungen** Menü auf Ihrem Windows Phone.

## <a name="BKMK_what_happens_unenroll_win81_rt">Windows RT unter Windows 8.1 oder Windows RT

-   Unternehmensportal-app wird von Ihrem Gerät deinstalliert, was bedeutet, dass das Gerät nicht mehr im Unternehmensportal angezeigt und kann nicht über das Unternehmensportal apps installieren.

-   Sie können keine Unternehmens-Apps und Unternehmensdaten mehr auf dem Gerät verwenden.

-   Alle Einstellungen, die beim Hinzufügen des Geräts auf diesem geändert wurden, z. B. das Deaktivieren der Kamera oder die Anforderung einer bestimmten Kennwortlänge, werden unwirksam.

-   Möglicherweise können Sie keine Verbindung mehr zum Unternehmensnetzwerk über WiFi oder ein virtuelles privates Netzwerk herstellen.

-   Unter Umständen haben Sie auf dem Gerät keinen Zugriff mehr auf einige Unternehmensressourcen, z. B. Dateifreigaben oder interne Websites.

-   In einigen Mail-Apps wie Windows Mail kann nicht mehr auf Unternehmens-E-Mails zugegriffen werden, die auf dem Gerät gespeichert sind.

Wenn Sie Ihr Windows RT-Gerät entfernen, geschieht Folgendes:

-   Unternehmensportal-app wird von Ihrem Gerät deinstalliert, was bedeutet, dass das Gerät nicht mehr im Unternehmensportal angezeigt und kann nicht über das Unternehmensportal apps installieren.

-   Sie können keine Unternehmens-Apps und Unternehmensdaten mehr auf dem Gerät verwenden.

-   Alle Einstellungen, die beim Hinzufügen des Geräts auf diesem geändert wurden, z. B. das Deaktivieren der Kamera oder die Anforderung einer bestimmten Kennwortlänge, werden unwirksam.


### Weitere Informationen:
[Verwenden Ihres Windows-Geräts mit Intune](using-your-windows-device-with-intune.md)

<!--HONumber=Mar16_HO3-->


