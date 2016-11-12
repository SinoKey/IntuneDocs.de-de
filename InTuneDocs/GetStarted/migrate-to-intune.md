---
title: Migrieren zu Intune | Microsoft Intune
description: 
keywords: 
author: jeffgilb
ms.author: jeffgilb
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 88936b8a-7453-4410-b6db-29f636ba3e72
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: 8ebe9c29f4155a2aac39b502252f3225372d374f


---

# <a name="migrate-to-intune"></a>Migrieren zu Intune


Die Migration aus einer vorhandenen Enterprise Mobility-Verwaltungslösung zu Intune kann anhand der folgenden allgemeinen Abfolge von Schritten durchgeführt werden:

![Migrationsschritte für Intune](./media/migrate-intune-steps.png)

## <a name="notify-users"></a>Benachrichtigen der Benutzer

Wenn Sie sicher sind, dass die Intune-Pilotbereitstellung Ihre Anforderungen erfüllt, informieren Sie die Benutzer über die anstehende Migration ihrer Geräte zu Intune. E-Mail-Nachrichten, Anweisungen, und [Poster](https://gallery.technet.microsoft.com/Intune-End-User-Enrollment-3a0c9b0c?WT.mc_id=Blog_Intune_General_PCIT) können bei der Formulierung von Erwartungen helfen und die Registrierungsdetails für die Schritte bieten, die die Benutzer ausführen müssen, um eine unterbrechungsfreie Konnektivität mit Unternehmensressourcen und -anwendungen sicherzustellen. Vergewissern Sie sich, dass Ihr Supportteam zur Unterstützung der Benutzer während der Migration bereit ist.

## <a name="modify-your-existing-enterprise-mobility-management-solution"></a>Ändern Ihrer vorhandenen Enterprise Mobility-Verwaltungslösung

Je nachdem, wie Sie Richtlinien für bedingten Zugriff zwischen Ihrer vorhandenen Enterprise Mobility-Verwaltungslösung und Intune behandeln möchten, kann es erforderlich sein, die vorhandenen Richtlinien für den bedingten Zugriff zu deaktivieren. Sie müssen Ihre vorhandenen Richtlinien für bedingten Zugriff deaktivieren ODER den Umfang der vorhandenen Richtlinien für bedingten Zugriff so anpassen, dass sie die zu Intune migrierten Benutzer/Geräte nicht einschließen.  Achten Sie darauf, dass nicht sowohl von Intune als auch von Ihrer vorhandenen Enterprise Mobility-Verwaltungslösung Richtlinien für bedingten Zugriff auf die gleichen Benutzer/Geräte angewendet werden.

## <a name="enable-intune-conditional-access-policy-optional"></a>Aktivieren einer Intune-Richtlinie für bedingten Zugriff (optional)

Wenn Sie entschieden haben, die Richtlinien für bedingten Zugriff für die Migration von Geräten ohne Karenzzeit sofort zu erzwingen, aktivieren Sie die Richtlinien für bedingten Zugriff in Intune in diesem Schritt.  Stellen Sie sicher, dass diese Entscheidung Ihren Benutzern und dem Helpdeskteam gut kommuniziert wird.  Wenn Geräte nicht bei Intune registriert und nicht mit Intune-Richtlinien kompatibel sind, können Benutzer erst wieder auf Unternehmensressourcen zugreifen, wenn sie ihre Geräte bei Intune registrieren und wenn diese Geräte mit den Intune-Richtlinien kompatibel sind.

## <a name="unenrolling-devices-from-your-existing-enterprise-mobility-management-solution"></a>Aufheben der Registrierung von Geräten aus der vorhandenen Enterprise Mobility-Verwaltungslösung

Sie müssen die Registrierung von Geräten bei der vorhandenen Enterprise Mobility-Verwaltungslösung aufheben, bevor Sie sie bei Intune registrieren können. Um eine optimale Benutzererfahrung zu gewährleisten, sollten Sie Benutzern erlauben, die Registrierung ihrer Geräte selbst aufzuheben.  Befolgen Sie die Anleitung des Lösungsanbieters zum Aufheben der Registrierung, um sicherzustellen, dass Benutzer und Geräte ordnungsgemäß aus der Plattform entfernt werden und potenzielle Unterbrechungen für Ihre Endbenutzer so gering wie möglich zu halten.

## <a name="enrolling-devices-in-intune"></a>Registrieren von Geräten bei Intune

Benutzer, deren Migration geplant ist, sollten sich sofort bei Intune registrieren, entweder, um einen Verlust des Zugriffs auf Unternehmensressourcen, E-Mail und Anwendungen zu verhindern bzw. den Zugriff wiederzuerlangen. Wenn Sie den bedingten Zugriff konfiguriert haben und Benutzer versuchen, auf E-Mails zuzugreifen, bevor sie sich bei Intune registriert haben, wird der Zugriff blockiert, und sie erhalten eine Registrierungs-E-Mail mit einer Begrüßung. Diese E-Mail enthält Anweisungen zur Registrierung ihres Geräts bei Intune.  Alternativ können Benutzer sich über die Intune-Unternehmensportal-App oder direkt über das Betriebssystem (Windows 8.1 und Windows 10 Mobile) bei Intune registrieren. Weitere Anleitungen zu den Registrierungsschritten für die verschiedenen Plattformen finden Sie unter [Informieren der Endbenutzer über den Einsatz von Microsoft Intune](/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune).

## <a name="configure-intune-conditional-access-optional"></a>Konfigurieren des bedingten Zugriffs für Intune (optional)

Wenn Sie eine Karenzzeit bis zur Erzwingung des bedingten Zugriffs eingeräumt haben, aktivieren Sie Richtlinien für bedingten Zugriff in Intune, um die Erzwingung nach Ablauf der Karenzzeit, die Sie Ihren Endbenutzern mitgeteilt haben, zu starten. Dadurch müssen sofort alle Geräte die Anforderungen der Intune-Richtlinie für bedingten Zugriff erfüllen.

## <a name="enroll-remaining-devices-and-users"></a>Registrieren der übrigen Geräte und Benutzer

Nachdem der bedingte Zugriff nun aktiviert wurde, müssen sich alle Benutzer bei Intune registrieren und die Kompatibilitätsrichtlinien Ihres Unternehmens für den Zugriff auf Unternehmensressourcen erfüllen. Wenn Sie die Benutzer in einer gestaffelten (nicht gleichzeitigen) Registrierung migriert haben, wiederholen die oben genannten Schritte, bis alle Geräte und Benutzer registriert sind und von Intune verwaltet werden.

## <a name="retire-the-previous-enterprise-mobility-management-solution"></a>Außerkraftsetzen Ihrer vorhandenen Enterprise Mobility-Verwaltungslösung

Nachdem Sie alle Ihre Benutzer und Geräte zu Intune migriert und überprüft haben, dass die Migrationen zu Intune erfolgreich waren, können Sie die vorherigen Enterprise Mobility-Verwaltungslösung außer Kraft setzen und/oder den Dienst kündigen. Befolgen Sie die Anleitung des Lösungsanbieters, um sicherzustellen, dass alle nicht benötigten Infrastrukturanforderungen ordnungsgemäß entfernt und alle Abonnements/Lizenzen gekündigt werden.

## <a name="additional-migration-resources"></a>Zusätzliche Ressourcen für die Migration

Benötigen Sie zusätzliche Hilfe bei der Migration zu Intune? Wir bieten Optionen zur Unterstützung durch Experten, um eine problemlose Migration sicherzustellen:

<!--- - [Microsoft Intune Onboarding](/em/solutions/fasttrack-center-benefit-for-enterprise-mobility-suite-ems)--->
- [Microsoft Consulting Services](https://www.microsoft.com/en-us/microsoftservices/default.aspx)
- [Technischer und nicht technischer Intune-Support](/intune/troubleshoot/how-to-get-support-for-microsoft-intune)
- [Microsoft Intune TechNet-Forum](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

## <a name="get-a-downloadable-copy-of-this-guide"></a>Abrufen einer herunterladbaren Version dieses Handbuchs

Eine herunterladbare Kopie dieses Artikels finden Sie in der [TechNet Gallery](https://gallery.technet.microsoft.com/Migrating-to-Intune-ea439387).



<!--HONumber=Nov16_HO2-->


