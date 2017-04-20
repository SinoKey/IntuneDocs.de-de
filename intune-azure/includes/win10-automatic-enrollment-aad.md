## <a name="enable-windows-10-automatic-enrollment"></a>Aktivieren der automatischen Registrierung von Windows 10

Mit der automatischen Registrierung können Benutzer entweder unternehmenseigene oder private Windows 10-PCs und Windows 10 Mobile-Geräte in Intune registrieren, indem Sie ein Geschäfts- oder Schulkonto hinzufügen und zustimmen, dass das Gerät verwaltet wird. So einfach ist das. Im Hintergrund registriert sich das Gerät des Benutzers und tritt Azure Active Directory bei. Nach der Registrierung wird das Gerät mit Intune verwaltet.

**Voraussetzungen**
- Azure Active Directory Premium-Abonnement ([Testabonnement](http://go.microsoft.com/fwlink/?LinkID=816845))
- Microsoft Intune-Abonnement


### <a name="configure-automatic-mdm-enrollment"></a>Konfigurieren der automatischen MDM-Registrierung

1. Melden Sie sich im [Azure-Verwaltungsportal](https://portal.azure.com) (https://manage.windowsazure.com) an, und wählen Sie **Azure Active Directory** aus.

  ![Screenshot des Azure-Portals](../media/auto-enroll-azure-main.png)

2. Wählen Sie **Mobilität (MDM und MAM)** aus.

  ![Screenshot des Azure-Portals](../media/auto-enroll-mdm.png)

3. Wählen Sie **Microsoft Intune** aus.

  ![Screenshot des Azure-Portals](../media/auto-enroll-intune.png)

4. Konfigurieren Sie, welche Benutzer automatisch registriert werden.

  ![Screenshot des Azure-Portals](../media/auto-enroll-scope.png)

  Verwenden Sie die Standardwerte für die folgenden URLs:
  - **MDM-Registrierung**
  - **MDM-Nutzungsbedingungen**
  - **MDM-Konformität**

5. Geben Sie an, welche Geräte von Benutzern von Microsoft Intune verwaltet werden sollen. Die Windows 10-Geräte dieser Benutzer werden automatisch für die Verwaltung mit Microsoft Intune registriert.

  - **Alle**
  - **Gruppen**
  - **Keine**

6. Wählen Sie **Speichern** aus.
