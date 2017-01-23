---
title: "Querladen von Apps für Windows und Windows Phone | Microsoft-Dokumentation"
description: "Erfahren Sie, wie Sie branchenspezifische Apps signieren, um sie mit Intune bereitstellen zu können."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: e44f1756-52e1-4ed5-bf7d-0e80363a8674
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 2e8220f850e3b38a24aa4c48bcc3a59088251c24


---
# <a name="sign-line-of-business-apps-so-they-can-be-deployed-to-windows-devices-with-intune"></a>Signieren Sie branchenspezifische Apps, damit sie mit Intune auf Windows-Geräten bereitgestellt werden können

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Als Intune-Administrator können Sie branchenspezifische Apps – einschließlich der Unternehmensportal-App – auf Windows- und Windows 10 Mobile-Geräten bereitstellen. Um APPX- oder XAP-Apps auf Windows 10- und Windows 10 Mobile-Geräten oder beliebige branchenspezifische App auf Windows 8.1- oder Windows Phone 8.1-Geräten bereitzustellen, müssen Sie ein **Symantec Enterprise Mobile Code Signing-Zertifikat** erwerben. Nur das Symantec-Zertifikat wird für diese Apps auf den jeweiligen Windows-Geräten als vertrauenswürdig eingestuft. Für Windows 10-Apps und universelle Apps können Sie Ihre eigene Zertifizierungsstelle verwenden. Dieses Zertifikat ist für folgende Zwecke erforderlich:

-   Signieren der Unternehmensportal-App für die Bereitstellung auf Windows-PCs, Windows 10 Mobile- und Windows Phone-Geräten

-   Signieren von branchenspezifischen Apps eines Unternehmens, damit sie über Intune für Windows-Geräte bereitgestellt werden können

Mithilfe der folgenden Schritte können Sie das erforderliche Zertifikat bereitstellen und die Apps signieren. Sie benötigen ein Windows Phone Dev Center-Konto, und Sie müssen ein Symantec-Zertifikat erwerben.


1. **Anmelden beim Windows Phone Dev Center**<br>
   Registrieren Sie sich mithilfe von Unternehmenskontodaten beim [Windows Phone Dev Center](http://go.microsoft.com/fwlink/?LinkId=268442) , wenn Sie sich anmelden, um Ihr Unternehmenskonto zu erwerben. Diese Anforderung muss von einem Mitglied der Geschäftsleitung autorisiert werden, bevor Sie ein Codesignaturzertifikat erhalten.

2. **Beziehen eines Symantec-Zertifikats für Unternehmen**<br>
  Erwerben Sie unter Verwendung Ihrer Symantec-ID ein Zertifikat von der [Symantec-Website](http://go.microsoft.com/fwlink/?LinkId=268441) . Nach dem Kauf des Zertifikats erhält die genehmigende Person in Ihrem Unternehmen, die Sie in Ihrem Windows Phone Dev Center-Konto bestimmt haben, eine E-Mail, in der die Genehmigung der Zertifikatanforderung angefordert wird. Weitere Informationen zu den Anforderungen des Symantec-Zertifikats finden Sie unter [Warum ist für Windows Phone ein Symantec-Zertifikat erforderlich?](https://technet.microsoft.com/en-us/library/dn764959.aspx#BKMK_Symantec) in den häufig gestellten Fragen zur Windows-Geräteregistrierung.

3.  **Importieren von Zertifikaten**<br>
    Nachdem die Anforderung genehmigt wurde, erhalten Sie eine E-Mail mit Anweisungen zum Importieren von Zertifikaten. Führen Sie die Anweisungen in der E-Mail aus, um die Zertifikate zu importieren.

4.  **Überprüfen der importierten Zertifikate**<br>
    Zum Überprüfen, ob die Zertifikate ordnungsgemäß importiert wurden, navigieren Sie zum Snap-In **Zertifikate**, klicken mit der rechten Maustaste auf **Zertifikate** und klicken dann auf **Zertifikate suchen**. Geben Sie „Symantec“ in das Feld **Enthält** ein, und klicken Sie auf **Jetzt suchen**. Die importierten Zertifikate werden in den Ergebnissen angezeigt.

    ![Suchen des Symantec-Zertifikats](./media/wit.gif)

5. **Exportieren eines Signaturzertifikats**<br>
   Wenn Sie überprüft haben, dass die Zertifikate vorhanden sind, können Sie die PFX-Datei exportieren, um das Unternehmensportal zu signieren. Wählen Sie das Symantec-Zertifikat mit „Codesignatur“ für **Beabsichtigter Zweck** aus. Klicken Sie mit der rechten Maustaste auf das Codesignaturzertifikat, und wählen Sie **Exportieren** aus.

    ![Exportieren des Signaturzertifikats](./media/wit-walk-cert2.gif)

    Wählen Sie im **Assistenten zum Exportieren von Zertifikaten**die Option **Ja, privaten Schlüssel exportieren** aus, und klicken Sie dann auf **Weiter**. Wählen Sie die Option **Privater Informationsaustausch –PKCS #12 (.PFX)** aus, und aktivieren Sie das Kontrollkästchen **Möglichst alle Zertifikate im Zertifizierungspfad berücksichtigen**. Schließen Sie den Assistenten ab. Weitere Informationen finden Sie unter [Exportieren eines Zertifikats mit dem privaten Schlüssel](http://go.microsoft.com/fwlink/?LinkID=203031).

6.  **Hochladen der App in Intune**<br>
    Laden Sie die signierte App-Datei und Ihr Codesignaturzertifikat hoch, um die App den Endbenutzern zur Verfügung zu stellen.

    1.  Klicken Sie in der [Intune-Administratorkonsole](http://manage.microsoft.com) auf **Verwaltung** &gt; **Windows Phone**.

    2.  Klicken Sie auf **Signierte App-Datei hochladen**, und melden Sie sich mit Ihrer Intune-Administrator-ID an.

    3.  Fügen Sie die Zertifikatdatei (.pfx) hinzu, die Sie in das **Codesignaturzertifikat** exportiert haben, und erstellen Sie ein Kennwort für das Zertifikat.

    4.  Schließen Sie den Assistenten ab.

## <a name="example-download-sign-and-deploy-the-company-portal-app-for-windows-devices"></a>Beispiel: Herunterladen, Signieren und Bereitstellen der Unternehmensportal-App für Windows-Geräte

Sie können die Unternehmensportal-App mit Intune auf Windows-Geräten (Windows Phone- und Windows 10 Mobile-Geräte eingeschlossen) bereitstellen, statt sie über den Windows Store zu installieren. Sie müssen hierzu die Unternehmensportal-App herunterladen und mit Ihrem Zertifikat signieren.  Dies ist nur erforderlich, wenn Ihre Benutzer nicht den Store des Unternehmens verwenden und Sie das Unternehmensportal für Windows Phone 8.1-Geräte bereitstellen möchten.


1.  **Herunterladen des Unternehmensportals**

    Um die Unternehmensportal-App mit Intune bereitzustellen, können Sie die [Microsoft Intune-Unternehmensportal-App für Windows Phone 8.1](http://go.microsoft.com/fwlink/?LinkId=615799) aus dem Download Center herunterladen und die selbstextrahierende Datei (.exe) ausführen. Diese Datei enthält zwei Dateien:

    -   CompanyPortal.appx: Die Installations-App des Unternehmensportals für Windows Phone 8.1

    -   WinPhoneCompanyPortal.ps1: Ein PowerShell-Skript, das Sie verwenden können, um die Unternehmensportal-App-Datei zu signieren, sodass sie für Windows Phone 8.1-Geräte bereitgestellt werden kann

    Alternativ können Sie das Windows Phone 8.1-Unternehmensportal (offline lizenziertes Paket) oder das Windows 10-Unternehmensportal (offline lizenziertes Paket) aus dem [Windows Store für Unternehmen](http://businessstore.microsoft.com/) herunterladen. Die Unternehmensportal-App muss mit einer Offlinelizenz und dem geeigneten Paket zur Offlineverwendung erworben werden. Einträge für die Plattformen Windows 8 und Windows Phone 8 in der Auswahl beziehen sich auf die entsprechenden 8.1-Komponenten. Weitere Informationen, wie Sie dies in Intune ausführen, finden Sie unter [Verwalten von Apps, die im Windows Store für Unternehmen erworben wurden](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md).

2.  **Herunterladen des Windows Phone SDK** Laden Sie das Windows Phone SDK 8.0](http://go.microsoft.com/fwlink/?LinkId=615570) herunter, und installieren Sie es auf Ihrem Computer. Dieses SDK ist erforderlich, um ein Anwendungsregistrierungstoken zu generieren.

3.  **Generieren einer AETX-Datei** Generieren Sie aus der Symantec PFX-Datei eine Anwendungsregistrierungstoken-Datei (.aetx) mithilfe von AETGenerator.exe. Dieses Tool ist Teil von Windows Phone SDK 8.0. Eine Anleitung zum Erstellen einer AETX-Datei finden Sie im Abschnitt über das [Generieren eines Anwendungsregistrierungstokens für Windows Phone](https://msdn.microsoft.com/library/windows/apps/jj735576.aspx).

4.  **Herunterladen des Windows SDK für Windows 8.1** Laden Sie das [Windows Phone SDK](http://go.microsoft.com/fwlink/?LinkId=613525) herunter (http://go.microsoft.com/fwlink/?LinkId=613525), und installieren Sie es. Beachten Sie, dass das in der Unternehmensportal-App verwendete PowerShell-Skript den Standardinstallationsort `${env:ProgramFiles(x86)}\Windows Kits\8.1`nutzt. Wenn Sie die App an einem anderen Ort installieren möchten, beziehen Sie den Speicherort in einem Cmdlet-Parameter ein.

5.  **Codesignieren der App mithilfe von PowerShell** Öffnen Sie als Administrator **Windows PowerShell** auf dem Hostcomputer, auf dem Windows SDK mit dem Symantec Enterprise Mobile Code Signing Certificate installiert wurde. Navigieren Sie zur Datei „Sign-WinPhoneCompanyPortal.ps1“, und führen Sie das Skript aus.

    **Beispiel 1**

    ```
    .\Sign-WinPhoneCompanyPortal.ps1 -InputAppx 'C:\temp\CompanyPortal.appx' -OutputAppx 'C:\temp\CompanyPortalEnterpriseSigned.appx' -PfxFilePath 'C:\signing\cert.pfx' -PfxPassword '1234' -AetxPath 'C:\signing\cert.aetx'
    ```
    In diesem Beispiel wird die Datei "CompanyPortal.appx" unter "C:\temp\" signiert und die Datei "CompanyPortalEnterpriseSigned.appx" erstellt. Das PFX-Kennwort "1234" wird verwendet und die Herausgeber-ID wird aus der PFX-Datei gelesen. Die Unternehmens-ID wird aus der Datei "cert.aetx" gelesen.

    **Beispiel 2**

    ```
    .\Sign-WinPhoneCompanyPortal.ps1 -InputAppx 'C:\temp\CompanyPortal.appx' -OutputAppx 'C:\temp\CompanyPortalEnterpriseSigned.appx' -PfxFilePath 'C:\signing\cert.pfx' -PfxPassword '1234' -PublisherId 'OID.0.9.2342.19200300.100.1.1=1000000001, CN="Test, Inc.", OU=Test 1' -EnterpriseId 1000000001
    ```
    In diesem Beispiel wird die Datei "CompanyPortal.appx" unter "C:\temp\" signiert und die Datei "CompanyPortalEnterpriseSigned.appx" erstellt. Das PFX-Kennwort "1234" und die festgelegte Herausgeber-ID werden verwendet.

    **Parameter:**

    -   `-InputAppx` : Der lokale Pfad zur Datei "CompanyPortal.appx" in einfachen Anführungszeichen. Beispiel: 'C:\temp\CompanyPortal.appx'

    -   `-OutputAppx` : Der lokale Pfad und Dateiname für die signierte Unternehmensportal-App in einfachen Anführungszeichen. Beispiel: 'C:\temp\CompanyPortalEnterpriseSigned.appx'

    -   `-PfxFilePath` : Der lokale Pfad und Dateiname für die exportierte PFX-Datei mit dem Symantec-Zertifikat. Beispiel: 'C:\signing\cert.pfx'

    -   `-PfxPassword` : Das Kennwort, das zum Signieren der PFX-Datei verwendet wird, in einfachen Anführungszeichen. Beispiel: '1234'

    -   `-AetxPath` : Der lokale Pfad zur AETX-Datei, die zum Lesen der Unternehmens-ID verwendet wird, wenn das Argument "EnterpriseId" nicht definiert ist. Dieses Argument oder EnterpriseId muss angegeben werden. Beispiel: 'C:\signing\cert.aetx'

    -   `-PublisherId`: Die Herausgeber-ID des Unternehmens. Wenn sie nicht vorhanden ist, wird das Feld "Subject" von Symantec Enterprise Mobile Code Signing Certificate verwendet. Beispiel: 'OID.0.9.2342.19200300.100.1.1=1000000001, CN="Test, Inc.", OU=Test 1'

    -   `-SdkPath`: Der Pfad zum Stammordner des Windows SDK für Windows 8.1. Dieses Argument ist optional und wird standardmäßig auf "${env:ProgramFiles(x86)}\Windows Kits\8.1" gesetzt.

    -   `-EnterpriseId`: Die Unternehmens-ID. Dieses Argument oder "AetxPath" muss angegeben werden. Wenn dieses Argument nicht angegeben ist, wird die Unternehmens-ID aus der AETX-Datei gelesen. Beispiel: 1000000001

6.  Stellen Sie die Unternehmensportal-App (SSP.appx) für Windows Phone 8.1 bereit. Einen Leitfaden finden Sie unter [Bereitstellen von Apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md).

## <a name="how-to-renew-the-symantec-enterprise-code-signing-certificate"></a>So wird das Symantec-Codesignaturzertifikat erneuert

Das zur Bereitstellung von mobilen Windows- und Windows Phone-Geräten verwendete Symantec-Zertifikat muss regelmäßig verlängert werden.

1.  Suchen Sie nach einer Erneuerungs-E-Mail, die ungefähr 14 Tage vor Ablauf des Zertifikats von Symantec gesendet wurde. Diese E-Mail enthält Anweisungen von Symantec zum Erneuern des Zertifikats für Ihr Unternehmen.

    Weitere Informationen zu Symantec-Zertifikaten erhalten Sie unter [www.symantec.com](http://www.symantec.com) oder telefonisch unter 1-877-438-8776 oder + 1-650-426-3400.

2.  Wechseln Sie zu der Website (z. B.: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)), und melden Sie sich mit der Symantec-Herausgeber-ID und der mit dem Zertifikat verbundenen E-Mail-Adresse an. Denken Sie daran, den gleichen Computer für das Starten der Erneuerung zu verwenden, den Sie auch zum Herunterladen des Zertifikats verwenden werden.

3.  Sobald die Erneuerung genehmigt und bezahlt wurde, können Sie das Zertifikat herunterladen.

### <a name="how-to-install-the-updated-certificate-for-line-of-business-lob-apps"></a>Installieren des aktualisierten Zertifikats für branchenspezifische Apps

1.  Signieren Sie die neueste Version Ihrer branchenspezifischen App.

2.  Öffnen Sie Ihre [Intune-Administratorkonsole](https://admin.manage.microsoft.com) (https://admin.manage.microsoft.com), gehen Sie zu **Admin** &gt; **Verwaltung mobiler Geräte** &gt; **Windows Phone**, und klicken Sie auf **Signierte App hochladen**.

3.  Laden Sie das neu signierte Unternehmensportal hoch. Sie benötigen die neu signierte SSP.XAP-Datei und die neue PFX-Datei, die Sie von Symantec erhalten, oder das Anwendungsregistrierungstoken, das mit dieser neuen PFX-Datei erstellt wurde.

4.  Wenn das Hochladen abgeschlossen ist, entfernen Sie die alte Version des Unternehmensportals im Arbeitsbereich **Software**.

5.  Signieren Sie alle neuen und aktualisierten Unternehmens-Apps unter Verwendung des neuen Zertifikats. Vorhandene Anwendungen müssen nicht erneut signiert und erneut bereitgestellt werden.



<!--HONumber=Dec16_HO2-->


