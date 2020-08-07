---
title: Konfigurieren eines Berichts Servers für die e-Mail-Übermittlung (SSRS-Configuration Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], distributing
- report servers [Reporting Services], e-mail delivery
- remote SMTP service [Reporting Services]
- distributing reports [Reporting Services], e-mail
- CDO
- Collaboration Data Objects
- SMTP settings [Reporting Services]
- e-mail [Reporting Services]
- sending reports
- mail [Reporting Services]
- local SMTP service [Reporting Services]
ms.assetid: b838f970-d11a-4239-b164-8d11f4581d83
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3122dbbb5debc90afa73ca0f8ab0d8e23d38a0ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619563"
---
# <a name="configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager"></a><span data-ttu-id="380b8-102">Konfigurieren eines Berichtsservers für die E-Mail-Übermittlung (SSRS-Konfigurations-Manager)</span><span class="sxs-lookup"><span data-stu-id="380b8-102">Configure a Report Server for E-Mail Delivery (SSRS Configuration Manager)</span></span>


  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="380b8-103">enthält eine Erweiterung zur E-Mail-Übermittlung, damit Sie Berichte per E-Mail verteilen können.</span><span class="sxs-lookup"><span data-stu-id="380b8-103">includes an e-mail delivery extension so that you can distribute reports through e-mail.</span></span> <span data-ttu-id="380b8-104">Je nachdem, wie Sie das Abonnieren von E-Mails definieren, kann eine E-Mail-Übermittlung aus einer Nachricht, einem Link, einem Anhang oder einem eingebetteten Bericht bestehen.</span><span class="sxs-lookup"><span data-stu-id="380b8-104">Depending on how you define the e-mail subscription, a delivery might consist of a notification, link, attachment, or embedded report.</span></span> <span data-ttu-id="380b8-105">Die Erweiterung der E-Mail-Übermittlung arbeitet mit Ihrer vorhandenen E-Mail-Server-Technologie.</span><span class="sxs-lookup"><span data-stu-id="380b8-105">The e-mail delivery extension works with your existing mail server technology.</span></span> <span data-ttu-id="380b8-106">Der E-Mail-Server muss ein SMTP-Server oder eine Weiterleitung sein.</span><span class="sxs-lookup"><span data-stu-id="380b8-106">The mail server must be an SMTP server or forwarder.</span></span> <span data-ttu-id="380b8-107">Der Berichtsserver stellt über CDO-Bibliotheken (Collaboration Data Objects, cdosys.dll), die das Betriebssystem stellt, eine Verbindung zu einem SMTP-Server her.</span><span class="sxs-lookup"><span data-stu-id="380b8-107">The report server connects to an SMTP server through Collaboration Data Objects (CDO) libraries (cdosys.dll) that are provided by the operating system.</span></span>  
  
 <span data-ttu-id="380b8-108">Die E-Mail-Übermittlungserweiterung des Berichtsservers ist standardmäßig nicht konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="380b8-108">The report server e-mail delivery extension is not configured by default.</span></span> <span data-ttu-id="380b8-109">Sie müssen den Reporting Services-Konfigurations-Manager verwenden, um die Erweiterung minimal zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="380b8-109">You must use the Reporting Services Configuration Manager to minimally configure the extension.</span></span> <span data-ttu-id="380b8-110">Sie müssen die Datei `RSReportServer.config` bearbeiten, um die erweiterten Eigenschaften festzulegen.</span><span class="sxs-lookup"><span data-stu-id="380b8-110">To set advanced properties, you must edit the `RSReportServer.config` file.</span></span> <span data-ttu-id="380b8-111">Wenn Sie den Berichtsserver für die Verwendung dieser Erweiterung nicht konfigurieren können, können Sie stattdessen Berichte an einen freigegebenen Ordner übermitteln.</span><span class="sxs-lookup"><span data-stu-id="380b8-111">If you cannot configure the report server to use this extension, you can deliver reports to a shared folder instead.</span></span> <span data-ttu-id="380b8-112">Weitere Informationen finden Sie unter [File Share Delivery in Reporting Services](../../reporting-services/subscriptions/file-share-delivery-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="380b8-112">For more information, see [File Share Delivery in Reporting Services](../../reporting-services/subscriptions/file-share-delivery-in-reporting-services.md).</span></span>  
  
||  
|-|  
|[!INCLUDE[applies](../../includes/applies-md.md)]<span data-ttu-id="380b8-113">Einheitlicher [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Modus</span><span class="sxs-lookup"><span data-stu-id="380b8-113">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode</span></span>|  
  
 
  
##  <a name="configuration-requirements"></a><a name="bkmk_configuration_requirements"></a><span data-ttu-id="380b8-114">Konfigurations Anforderungen</span><span class="sxs-lookup"><span data-stu-id="380b8-114">Configuration Requirements</span></span>  
  
-   <span data-ttu-id="380b8-115">Die E-Mail-Übermittlung des Berichtsservers wird über Collaboration Data Objects (CDO) implementiert und erfordert einen SMTP-Remoteserver oder einen lokalen SMTP-Server (Simple Mail Transfer Protocol) bzw. eine SMTP-Weiterleitung.</span><span class="sxs-lookup"><span data-stu-id="380b8-115">Report server e-mail delivery is implemented on Collaboration Data Objects (CDO) and requires a local or remote Simple Mail Transfer Protocol (SMTP) server or SMTP forwarder.</span></span> <span data-ttu-id="380b8-116">SMTP wird nicht von allen Windows-Betriebssystemen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="380b8-116">SMTP is not supported on all Windows operating systems.</span></span> <span data-ttu-id="380b8-117">Wenn Sie die Itanium-basierte Edition von Windows Server 2008 verwenden, wird SMTP nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="380b8-117">If you are using the Itanium-based edition of Windows Server 2008, SMTP is not supported.</span></span> <span data-ttu-id="380b8-118">Weitere Informationen zu den Konfigurationsoptionen von CDO finden Sie unter [Configuration CoClass](https://go.microsoft.com/fwlink/?LinkId=98237) auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="380b8-118">For more information about configuration options provided through CDO, see [Configuration CoClass](https://go.microsoft.com/fwlink/?LinkId=98237) on MSDN.</span></span>  
  
-   <span data-ttu-id="380b8-119">Das Berichtsserver-Dienstkonto muss auf dem SMTP-Server berechtigt sein, E-Mails zu senden.</span><span class="sxs-lookup"><span data-stu-id="380b8-119">The Report Server service account must have permission on the SMTP server to send mail.</span></span>  
  
-   <span data-ttu-id="380b8-120">Für die Erweiterung der E-Mail-Übermittlung wird in E-Mail-Anlagen die UTF-8-Codierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="380b8-120">The e-mail delivery extension uses UTF-8 encoding in e-mail attachments.</span></span> <span data-ttu-id="380b8-121">Die Codierung kann nicht geändert werden. Die HTML-Renderingerweiterung unterstützt ausschließlich UTF-8.</span><span class="sxs-lookup"><span data-stu-id="380b8-121">You cannot modify the encoding; the HTML rendering extension only supports UTF-8.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="380b8-122">Die standardmäßige E-Mail-Übermittlungserweiterung bietet keine Unterstützung für digitale Signaturen oder für die Verschlüsselung ausgehender E-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="380b8-122">The default e-mail delivery extension does not provide support for digitally signing or encrypting outgoing mail messages.</span></span>  
  
 
  
##  <a name="configuring-a-report-server-for-local-or-remote-smtp-service"></a><a name="bkmk_configure_for_local_or_remote_SMTP"></a><span data-ttu-id="380b8-123">Konfigurieren eines Berichts Servers für einen lokalen oder Remote-SMTP-Dienst</span><span class="sxs-lookup"><span data-stu-id="380b8-123">Configuring a Report Server for Local or Remote SMTP Service</span></span>  
 <span data-ttu-id="380b8-124">Zur Unterstützung der E-Mail-Übermittlung können Sie einen lokalen SMTP-Dienst oder einen SMTP-Remoteserver bzw. eine SMTP-Weiterleitung verwenden.</span><span class="sxs-lookup"><span data-stu-id="380b8-124">You can use a local SMTP service or a remote SMTP server or forwarder to support e-mail delivery.</span></span> <span data-ttu-id="380b8-125">Wenn Sie auf einen vorhandenen SMTP-Remoteserver zugreifen können, sollten Sie ihn verwenden.</span><span class="sxs-lookup"><span data-stu-id="380b8-125">If you have access to an existing remote SMTP server, you should consider using it.</span></span> <span data-ttu-id="380b8-126">Wenn kein SMTP-Server verfügbar ist oder wenn zu einem späteren Zeitpunkt Berichtsübermittlungsfehler auftreten, die auf Fehler bei der Computerverbindung zurückzuführen sind, sollten Sie stattdessen einen lokalen SMTP-Dienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="380b8-126">If there is no SMTP server available or if you subsequently encounter report delivery errors that can be attributed to computer connection failures, you should switch to using a local SMTP service.</span></span> <span data-ttu-id="380b8-127">Informationen zum Konfigurieren eines Berichtsservers für lokale Dienste und Remotedienste finden Sie weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="380b8-127">Details about how to configure a report server for local or remote service are provided further on in this topic.</span></span>  
  
  
  
##  <a name="setting-configuration-options-for-e-mail-delivery"></a><a name="bkmk_setting_email_delivery"></a><span data-ttu-id="380b8-128">Festlegen von Konfigurationsoptionen für e-Mail-Übermittlung</span><span class="sxs-lookup"><span data-stu-id="380b8-128">Setting Configuration Options for E-Mail Delivery</span></span>  
 <span data-ttu-id="380b8-129">Bevor Sie die E-Mail-Übermittlung des Berichtsservers verwenden können, müssen Sie Konfigurationswerte festlegen, die angeben, welcher SMTP-Server verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="380b8-129">Before you can use Report Server e-mail delivery, you must set configuration values that provide information about which SMTP server to use.</span></span>  
  
 <span data-ttu-id="380b8-130">Gehen Sie wie folgt vor, um einen Berichtsserver für die E-Mail-Übermittlung zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="380b8-130">To configure a report server for e-mail delivery, do the following:</span></span>  
  
-   <span data-ttu-id="380b8-131">Verwenden Sie den Reporting Services-Konfigurations-Manager, wenn Sie nur einen SMTP-Server und ein Benutzerkonto angeben, das über die Berechtigung zum Senden von E-Mail verfügt.</span><span class="sxs-lookup"><span data-stu-id="380b8-131">Use the Reporting Services Configuration Manager if you are specifying just an SMTP server and a user account that has permission to send e-mail.</span></span> <span data-ttu-id="380b8-132">Dies sind die zum Konfigurieren der E-Mail-Übermittlungserweiterung für einen Berichtsserver erforderlichen Mindesteinstellungen.</span><span class="sxs-lookup"><span data-stu-id="380b8-132">These are the minimum settings that are required for configuring the Report Server e-mail delivery extension.</span></span> <span data-ttu-id="380b8-133">Weitere Informationen finden Sie unter [e-Mail-Einstellungen-Configuration Manager &#40;SSRS im einheitlichen Modus&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md) und [e-Mail-Übermittlung in Reporting Services](../../reporting-services/subscriptions/e-mail-delivery-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="380b8-133">For more information, see [E-mail Settings - Configuration Manager &#40;SSRS Native Mode&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md) and [E-Mail Delivery in Reporting Services](../../reporting-services/subscriptions/e-mail-delivery-in-reporting-services.md).</span></span>  
  
-   <span data-ttu-id="380b8-134">(Optional) Verwenden Sie einen Text-Editor, um zusätzliche Einstellungen in der Datei RSreportserver.config anzugeben.</span><span class="sxs-lookup"><span data-stu-id="380b8-134">(Optionally) Use a text editor to specify additional settings in the RSreportserver.config file.</span></span> <span data-ttu-id="380b8-135">Diese Datei enthält alle Konfigurationseinstellungen für die Berichtsserver-E-Mail-Übermittlung.</span><span class="sxs-lookup"><span data-stu-id="380b8-135">This file contains all of the configuration settings for Report Server e-mail delivery.</span></span> <span data-ttu-id="380b8-136">Wenn Sie einen lokalen SMTP-Server verwenden oder die E-Mail-Übermittlung auf bestimmte Hosts beschränken, müssen Sie zusätzliche Einstellungen in diesen Dateien angeben.</span><span class="sxs-lookup"><span data-stu-id="380b8-136">Specifying additional settings in these files is required if you are using a local SMTP server or if you are restricting e-mail delivery to specific hosts.</span></span> <span data-ttu-id="380b8-137">Weitere Informationen zum Suchen und Ändern von Konfigurationsdateien finden Sie unter [Ändern einer Reporting Services Konfigurationsdatei &#40;RSreportserver.config&#41;](../../reporting-services/report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) in SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="380b8-137">For more information about finding and modifying configuration files, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](../../reporting-services/report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) in SQL Server Books Online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="380b8-138">E-Mail-Einstellungen für den Berichtsserver basieren auf CDO (Collaboration Data Objects).</span><span class="sxs-lookup"><span data-stu-id="380b8-138">Report server e-mail settings are based on CDO.</span></span> <span data-ttu-id="380b8-139">Ausführlichere Informationen zu bestimmten Einstellungen finden Sie in der CDO-Produktdokumentation.</span><span class="sxs-lookup"><span data-stu-id="380b8-139">If you want more detail about specific settings, you can refer to the CDO production documentation.</span></span>  
  

  
##  <a name="example-report-server-e-mail-configuration"></a><a name="bkmk_example_config_file"></a><span data-ttu-id="380b8-140">Beispiel für eine e-Mail-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="380b8-140">Example Report Server E-Mail Configuration</span></span>  
 <span data-ttu-id="380b8-141">Das folgende Beispiel veranschaulicht die Einstellungen für einen SMTP-Remoteserver in der Datei RSreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="380b8-141">The following example illustrates the settings in the RSreportserver.config file for a remote SMTP server.</span></span> <span data-ttu-id="380b8-142">Informationen zu Ein derstellungsbeschreibungen und gültigen Werten fin derden Sie unter [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Onlin dere or the CDO product documentation.</span><span class="sxs-lookup"><span data-stu-id="380b8-142">To read about the setting descriptions and valid values, see [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online or the CDO product documentation.</span></span>  
  
```  
<RSEmailDPConfiguration>  
     <SMTPServer>mySMTPServer.Adventure-Works.com</SMTPServer>  
     <SMTPServerPort></SMTPServerPort>  
     <SMTPAccountName></SMTPAccountName>  
     <SMTPConnectionTimeout></SMTPConnectionTimeout>  
     <SMTPServerPickupDirectory></SMTPServerPickupDirectory>  
     <SMTPUseSSL></SMTPUseSSL>  
     <SendUsing>2</SendUsing>  
     <SMTPAuthenticate></SMTPAuthenticate>  
     <From>my-rs-email-account@Adventure-Works.com</From>  
     <EmbeddedRenderFormats>  
          <RenderingExtension>MHTML</RenderingExtension>  
     </EmbeddedRenderFormats>  
     <PrivilegedUserRenderFormats></PrivilegedUserRenderFormats>  
     <ExcludedRenderFormats>  
          <RenderingExtension>HTMLOWC</RenderingExtension>  
          <RenderingExtension>NULL</RenderingExtension>  
     </ExcludedRenderFormats>  
     <SendEmailToUserAlias>True</SendEmailToUserAlias>  
     <DefaultHostName></DefaultHostName>  
     <PermittedHosts>  
          <HostName>Adventure-Works.com</HostName>  
          <HostName>hotmail.com</HostName>  
     </PermittedHosts>  
</RSEmailDPConfiguration>  
```  
  

  
##  <a name="configuration-options-for-setting-the-to-field-in-a-message"></a><a name="bkmk_setting_TO_field"></a><span data-ttu-id="380b8-143">Konfigurationsoptionen zum Festlegen des Felds an: in einer Nachricht</span><span class="sxs-lookup"><span data-stu-id="380b8-143">Configuration Options for Setting the To: Field in a Message</span></span>  
 <span data-ttu-id="380b8-144">Benutzerdefinierte Abonnements, die gemäß den durch den Task **einzelne Abonnements verwalten** erteilten Berechtigungen erstellt werden, enthalten einen vorab festgelegten Benutzernamen, der auf dem Domänen Benutzerkonto basiert.</span><span class="sxs-lookup"><span data-stu-id="380b8-144">User-defined subscriptions that are created according to the permissions granted by the **Manage individual subscriptions** task contain a pre-set user name that is based on the domain user account.</span></span> <span data-ttu-id="380b8-145">Wenn der Benutzer das Abonnement erstellt, wird der Empfängername im **An:** -Feld mit dem Domänenbenutzerkonto der Person ausgefüllt, die das Abonnement erstellt.</span><span class="sxs-lookup"><span data-stu-id="380b8-145">When the user creates the subscription, the recipient name in the **To:** field is self-addressed using the domain user account of the person creating the subscription.</span></span>  
  
 <span data-ttu-id="380b8-146">Bei Verwendung eines SMTP-Servers bzw. einer Weiterleitung, der bzw. die E-Mail-Konten verwendet, die mit dem Domänenbenutzerkonto nicht übereinstimmen, erzeugt die Berichtsübermittlung einen Fehler, wenn der SMTP-Server den Bericht an diesen Benutzer übermitteln will.</span><span class="sxs-lookup"><span data-stu-id="380b8-146">If you are using an SMTP server or forwarder that uses e-mail accounts that are different from the domain user account, the report delivery will fail when the SMTP server tries to deliver the report to that user.</span></span>  
  
 <span data-ttu-id="380b8-147">Sie können die Konfigurationseinstellungen ändern, die Benutzern das Eingeben eines Namens im Feld **An:** ermöglichen, um das Problem zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="380b8-147">To workaround this issue, you can modify configuration settings that allow users to enter a name in the **To:** field:</span></span>  
  
1.  <span data-ttu-id="380b8-148">Öffnen Sie RSReportServer.config mit einem Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="380b8-148">Open RSReportServer.config with a text editor.</span></span>  
  
2.  <span data-ttu-id="380b8-149">Legen Sie `SendEmailToUserAlias` auf `False` fest.</span><span class="sxs-lookup"><span data-stu-id="380b8-149">Set `SendEmailToUserAlias` to `False`.</span></span>  
  
3.  <span data-ttu-id="380b8-150">Legen Sie `DefaultHostName` auf den DNS-Namen (Domain Name System) oder die IP-Adresse des SMTP-Servers bzw. der Weiterleitung fest.</span><span class="sxs-lookup"><span data-stu-id="380b8-150">Set `DefaultHostName` to the Domain Name System (DNS) name or IP address of the SMTP server or forwarder.</span></span>  
  
4.  <span data-ttu-id="380b8-151">Speichern Sie die Datei .</span><span class="sxs-lookup"><span data-stu-id="380b8-151">Save the file.</span></span>  
  
  
  
##  <a name="configuration-options-for-remote-smtp-service"></a><a name="bkmk_options_remote_SMTP"></a><span data-ttu-id="380b8-152">Konfigurationsoptionen für den SMTP-Remote Dienst</span><span class="sxs-lookup"><span data-stu-id="380b8-152">Configuration Options for Remote SMTP Service</span></span>  
 <span data-ttu-id="380b8-153">Die Verbindung zwischen dem Berichtsserver und einem SMTP-Server oder einer SMTP-Weiterleitung wird durch die folgenden Konfigurationseinstellungen bestimmt:</span><span class="sxs-lookup"><span data-stu-id="380b8-153">The connection between the report server and an SMTP server or forwarder is determined by the following configuration settings:</span></span>  
  
-   <span data-ttu-id="380b8-154">`SendUsing` gibt eine Methode für das Senden von Nachrichten an.</span><span class="sxs-lookup"><span data-stu-id="380b8-154">`SendUsing` specifies a method for sending messages.</span></span> <span data-ttu-id="380b8-155">Sie können zwischen einem SMTP-Netzwerkdienst und einem lokalen SMTP-Dienstabholverzeichnis wählen.</span><span class="sxs-lookup"><span data-stu-id="380b8-155">You can choose between a network SMTP service or a local SMTP service pickup directory.</span></span> <span data-ttu-id="380b8-156">Um einen SMTP-Remotedienst zu verwenden, muss dieser Wert in der Datei RSReportServer.config auf **2** eingestellt werden.</span><span class="sxs-lookup"><span data-stu-id="380b8-156">To use a remote SMTP service, this value must be set to **2** in the RSReportServer.config file.</span></span>  
  
-   <span data-ttu-id="380b8-157">`SMTPServer` gibt den SMTP-Remoteserver bzw. die SMTP-Weiterleitung an.</span><span class="sxs-lookup"><span data-stu-id="380b8-157">`SMTPServer` specifies the remote SMTP server or forwarder.</span></span> <span data-ttu-id="380b8-158">Dieser Wert ist erforderlich, wenn Sie einen SMTP-Remoteserver oder eine SMTP-Weiterleitung verwenden.</span><span class="sxs-lookup"><span data-stu-id="380b8-158">This value is a required value if you are using a remote SMTP server or forwarder.</span></span>  
  
-   <span data-ttu-id="380b8-159">`From` legt den Wert fest, der in der **Von:** -Zeile einer E-Mail angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="380b8-159">`From` sets the value that appears in the **From:** line of an e-mail message.</span></span> <span data-ttu-id="380b8-160">Dieser Wert ist erforderlich, wenn Sie einen SMTP-Remoteserver oder eine SMTP-Weiterleitung verwenden.</span><span class="sxs-lookup"><span data-stu-id="380b8-160">This value is a required value if you are using a remote SMTP server or forwarder.</span></span>  
  
 <span data-ttu-id="380b8-161">Andere Werte, die für den SMTP-Remotedienst verwendet werden, sind folgende (diese Werte müssen Sie nur angeben, wenn Sie die Standardwerte überschreiben möchten).</span><span class="sxs-lookup"><span data-stu-id="380b8-161">Other values that are used for remote SMTP service include the following (note that you do not need to specify these values unless you want to override the default values).</span></span>  
  
-   <span data-ttu-id="380b8-162">**SMTPServerPort** wird für Port 25 konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="380b8-162">**SMTPServerPort** is configured for port 25.</span></span>  
  
-   <span data-ttu-id="380b8-163">**SMTPAuthenticate** gibt an, wie der Berichtsserver eine Verbindung zum SMTP-Remoteserver herstellt.</span><span class="sxs-lookup"><span data-stu-id="380b8-163">**SMTPAuthenticate** specifies how the report server connects to the remote SMTP server.</span></span> <span data-ttu-id="380b8-164">Der Standardwert ist 0 (d. h. keine Authentifizierung).</span><span class="sxs-lookup"><span data-stu-id="380b8-164">The default value is 0 (or no authentication).</span></span> <span data-ttu-id="380b8-165">In diesem Fall wird die Verbindung über den anonymen Zugriff hergestellt.</span><span class="sxs-lookup"><span data-stu-id="380b8-165">In this case, the connection is made through Anonymous access.</span></span> <span data-ttu-id="380b8-166">Je nach Domänenkonfiguration müssen der Berichtsserver und der SMTP-Server unter Umständen zu derselben Domäne gehören.</span><span class="sxs-lookup"><span data-stu-id="380b8-166">Depending on your domain configuration, the report server and the SMTP server may need to be members of the same domain.</span></span>  
  
     <span data-ttu-id="380b8-167">Um E-Mail an eingeschränkte Verteilerlisten zu senden (z. B. Verteilerlisten, die nur eingehende Nachrichten von authentifizierten Konten akzeptieren), legen Sie **SMTPAuthenticate** auf **2**fest.</span><span class="sxs-lookup"><span data-stu-id="380b8-167">To send e-mail to restricted distribution lists (for example, distribution lists that accept incoming messages only from authenticated accounts), set **SMTPAuthenticate** to **2**.</span></span>  
  

  
##  <a name="configuration-options-for-local-smtp-service"></a><a name="bkmk_options_local_SMTP"></a><span data-ttu-id="380b8-168">Konfigurationsoptionen für den lokalen SMTP-Dienst</span><span class="sxs-lookup"><span data-stu-id="380b8-168">Configuration Options for Local SMTP Service</span></span>  
 <span data-ttu-id="380b8-169">Das Konfigurieren eines lokalen SMTP-Dienstes ist sinnvoll, wenn Sie die E-Mail-Übermittlung des Berichtsservers testen oder entsprechende Probleme behandeln.</span><span class="sxs-lookup"><span data-stu-id="380b8-169">Configuring a local SMTP service is useful if you are testing or troubleshooting report server e-mail delivery.</span></span> <span data-ttu-id="380b8-170">Der lokale SMTP-Dienst ist standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="380b8-170">The local SMTP service is not enabled by default.</span></span> <span data-ttu-id="380b8-171">Anweisungen zur Aktivierung finden Sie unter [Konfigurieren eines Berichts Servers für die e-Mail-Übermittlung (SSRS Configuration Manager)](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) und [e-Mail-Einstellungen-Configuration Manager &#40;SSRS-&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md)im einheitlichen Modus.</span><span class="sxs-lookup"><span data-stu-id="380b8-171">For instructions on how to enable it, see [Configure a Report Server for E-Mail Delivery (SSRS Configuration Manager)](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) and [E-mail Settings - Configuration Manager &#40;SSRS Native Mode&#41;](../../reporting-services/install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md).</span></span>  
  
 <span data-ttu-id="380b8-172">Die Verbindung zwischen dem Berichtsserver und einem lokalen SMTP-Server oder einer SMTP-Weiterleitung wird durch die folgenden Konfigurationseinstellungen bestimmt:</span><span class="sxs-lookup"><span data-stu-id="380b8-172">The connection between the report server and a local SMTP server or forwarder is determined by the following configuration settings:</span></span>  
  
-   <span data-ttu-id="380b8-173">`SendUsing` ist auf **1** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="380b8-173">`SendUsing` is set to **1**.</span></span>  
  
-   <span data-ttu-id="380b8-174">Für**SMTPServerPickupDirectory** ist ein Ordner auf dem lokalen Laufwerk festgelegt.</span><span class="sxs-lookup"><span data-stu-id="380b8-174">**SMTPServerPickupDirectory** is set to a folder on the local drive.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="380b8-175">Stellen Sie sicher, dass Sie nicht festlegen, `SMTPServer` Wenn Sie einen lokalen SMTP-Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="380b8-175">Be sure that you do not set `SMTPServer` if you are using a local SMTP server.</span></span>  
  
-   <span data-ttu-id="380b8-176">`From` legt den Wert fest, der in der **Von:** -Zeile einer E-Mail angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="380b8-176">`From` sets the value that appears in the **From:** line of an e-mail message.</span></span> <span data-ttu-id="380b8-177">Dieser Wert ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="380b8-177">This value is required.</span></span>  
  
 
  
##  <a name="to-configure-report-server-e-mail-using-the-reporting-services-configuration-manager"></a><a name="bkmk_use_configuration_manager"></a><span data-ttu-id="380b8-178">So konfigurieren Sie Berichts Server-e-Mails mithilfe der Konfigurations-Manager für Reporting Services</span><span class="sxs-lookup"><span data-stu-id="380b8-178">To configure report server e-mail using the Reporting Services Configuration Manager</span></span>  
  
1.  <span data-ttu-id="380b8-179">Überprüfen Sie, ob der Report Server-Windows-Dienst über `Send As`-Berechtigungen auf dem SMTP-Server verfügt.</span><span class="sxs-lookup"><span data-stu-id="380b8-179">Verify that the Report Server Windows service has `Send As` permissions on the SMTP server.</span></span>  
  
2.  <span data-ttu-id="380b8-180">Starten Sie den Reporting Services-Konfigurations-Manager, und stellen Sie eine Verbindung mit der Berichtsserverinstanz her.</span><span class="sxs-lookup"><span data-stu-id="380b8-180">Start the Reporting Services Configuration Manager and connect to the report server instance.</span></span>  
  
3.  <span data-ttu-id="380b8-181">Geben Sie auf der Seite E-Mail-Einstellungen den Namen des SMTP-Servers ein.</span><span class="sxs-lookup"><span data-stu-id="380b8-181">On the Email Settings page, enter the name of the SMTP server.</span></span> <span data-ttu-id="380b8-182">Bei diesem Wert kann es sich um eine IP-Adresse, den UNC-Namen eines Computers im Firmenintranet oder um einen vollqualifizierten Domänennamen handeln.</span><span class="sxs-lookup"><span data-stu-id="380b8-182">This value can be an IP address, a UNC name of a computer on your corporate intranet, or a fully qualified domain name.</span></span>  
  
4.  <span data-ttu-id="380b8-183">Geben Sie in **Absenderadresse**den Namen eines Kontos ein, das über die Berechtigung zum Senden von E-Mail vom SMTP-Server verfügt.</span><span class="sxs-lookup"><span data-stu-id="380b8-183">In **Sender Address**, enter the name an account that has permission to send e-mail from the SMTP server.</span></span>  
  
5.  <span data-ttu-id="380b8-184">Klicken Sie auf **Übernehmen**.</span><span class="sxs-lookup"><span data-stu-id="380b8-184">Click **Apply**.</span></span>  
  

  
##  <a name="to-configure-a-remote-smtp-service-for-the-report-server"></a><a name="bkmk_confiugre_remote_SMTP"></a><span data-ttu-id="380b8-185">So konfigurieren Sie einen SMTP-Remote Dienst für den Berichts Server</span><span class="sxs-lookup"><span data-stu-id="380b8-185">To configure a remote SMTP Service for the report server</span></span>  
  
1.  <span data-ttu-id="380b8-186">Überprüfen Sie, ob der Report Server-Windows-Dienst über `Send As`-Berechtigungen auf dem SMTP-Server verfügt.</span><span class="sxs-lookup"><span data-stu-id="380b8-186">Verify that the Report Server Windows service has `Send As` permissions on the SMTP server.</span></span>  
  
2.  <span data-ttu-id="380b8-187">Öffnen Sie die Datei RSReportServer.config in einem Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="380b8-187">Open the RSReportServer.config file in a text editor.</span></span>  
  
3.  <span data-ttu-id="380b8-188">Vergewissern Sie sich, dass <`UrlRoot`> auf die URL-Adresse des Berichts Servers festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="380b8-188">Verify that <`UrlRoot`> is set to the report server URL address.</span></span> <span data-ttu-id="380b8-189">Dieser Wert wird beim Konfigurieren des Berichtsservers festgelegt und sollte bereits ausgefüllt sein.</span><span class="sxs-lookup"><span data-stu-id="380b8-189">This value is set when you configure the report server and it should be filled in already.</span></span> <span data-ttu-id="380b8-190">Geben Sie andernfalls die URL-Adresse des Berichtsservers ein.</span><span class="sxs-lookup"><span data-stu-id="380b8-190">If it is not set, type the report server URL address.</span></span>  
  
4.  <span data-ttu-id="380b8-191">Suchen Sie im Abschnitt "Delivery" nach <`ReportServerEmail`>.</span><span class="sxs-lookup"><span data-stu-id="380b8-191">In the Delivery section, find <`ReportServerEmail`>.</span></span>  
  
5.  <span data-ttu-id="380b8-192">Geben Sie in <`SMTPServer`> den Namen des SMTP-Servers ein.</span><span class="sxs-lookup"><span data-stu-id="380b8-192">In <`SMTPServer`>, type the name of the SMTP server.</span></span> <span data-ttu-id="380b8-193">Bei diesem Wert kann es sich um eine IP-Adresse, den UNC-Namen eines Computers im Firmenintranet oder um einen vollqualifizierten Domänennamen handeln.</span><span class="sxs-lookup"><span data-stu-id="380b8-193">This value can be an IP address, a UNC name of a computer on your corporate intranet, or a fully qualified domain name.</span></span>  
  
6.  <span data-ttu-id="380b8-194">Vergewissern Sie sich, dass <`SendUsing`> auf 2 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="380b8-194">Verify that <`SendUsing`> is set to 2.</span></span> <span data-ttu-id="380b8-195">Bei einem anderen Wert ist der Berichtsserver nicht für die Verwendung eines Remote-SMTP-Diensts konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="380b8-195">If it is set another value, the report server is not configured to use a remote SMTP service.</span></span>  
  
7.  <span data-ttu-id="380b8-196">`From`Geben Sie in <> den Namen eines Kontos ein, das über die Berechtigung zum Senden von e-Mails vom SMTP-Server verfügt.</span><span class="sxs-lookup"><span data-stu-id="380b8-196">In <`From`>, type the name an account that has permission to send e-mail from the SMTP server.</span></span>  
  
8.  <span data-ttu-id="380b8-197">Speichern Sie die Datei .</span><span class="sxs-lookup"><span data-stu-id="380b8-197">Save the file.</span></span>  
  
     <span data-ttu-id="380b8-198">Die neuen Einstellungen werden automatisch vom Berichtsserver verwendet, Sie müssen den Dienst nicht neu starten.</span><span class="sxs-lookup"><span data-stu-id="380b8-198">The report server will use the new settings automatically; you do not need to restart the service.</span></span> <span data-ttu-id="380b8-199">Sie können weitere SMTP-Einstellungen angeben, um die Verwendung des SMTP-Servers für die Berichtsserver-E-Mail-Übermittlung weiter zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="380b8-199">You can specify additional SMTP settings to further configure how the SMTP server is used for report server e-mail delivery.</span></span> <span data-ttu-id="380b8-200">Weitere Informationen fin derden Sie unter [Configurin derg a Report Server for E-Mail Delivery](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) und [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Onlin dere.</span><span class="sxs-lookup"><span data-stu-id="380b8-200">For more information, see [Configuring a Report Server for E-Mail Delivery](../../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) and [RSReportServer Configuration File](../../reporting-services/report-server/rsreportserver-config-configuration-file.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  

  
##  <a name="to-configure-a-local-smtp-service-for-the-report-server"></a><a name="bkmk_confiugre_local_SMTP"></a><span data-ttu-id="380b8-201">So konfigurieren Sie einen lokalen SMTP-Dienst für den Berichts Server</span><span class="sxs-lookup"><span data-stu-id="380b8-201">To configure a local SMTP Service for the report server</span></span>  
  
1.  <span data-ttu-id="380b8-202">Klicken Sie in der Systemsteuerung auf **Software**.</span><span class="sxs-lookup"><span data-stu-id="380b8-202">In Control Panel, click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="380b8-203">Klicken Sie auf **Windows-Komponenten hinzufügen/entfernen** , um den Assistenten für Windows-Komponenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="380b8-203">Click **Add/Remove Windows Components** to start the Windows Component Wizard.</span></span>  
  
3.  <span data-ttu-id="380b8-204">Wählen Sie **Anwendungsserver** aus, und klicken Sie auf **Details**.</span><span class="sxs-lookup"><span data-stu-id="380b8-204">Select **Application Server** and click **Details**.</span></span>  
  
4.  <span data-ttu-id="380b8-205">Wählen Sie **Internetinformationsdienste (IIS)** aus, und klicken Sie auf **Details**.</span><span class="sxs-lookup"><span data-stu-id="380b8-205">Select **Internet Information Services (IIS)** and click **Details**.</span></span>  
  
5.  <span data-ttu-id="380b8-206">Aktivieren Sie das Kontrollkästchen **SMTP-Dienst** , und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="380b8-206">Select the **SMTP Service** checkbox and click **OK**.</span></span>  
  
6.  <span data-ttu-id="380b8-207">Klicken Sie im Assistenten für Windows-Komponenten auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="380b8-207">On the Windows Component Wizard, click **Next**.</span></span> <span data-ttu-id="380b8-208">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="380b8-208">Click **Finish**.</span></span>  
  
7.  <span data-ttu-id="380b8-209">Überprüfen Sie in der \*\*\*\* Dienstekonsole, ob der Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="380b8-209">Verify that the service is running in the **Services** console.</span></span>  
  
8.  <span data-ttu-id="380b8-210">Öffnen Sie die Datei **RSReportServer.config** in einem Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="380b8-210">Open the **RSReportServer.config** file in a text editor.</span></span>  
  
9. <span data-ttu-id="380b8-211">Überprüfen Sie, ob `<UrlRoot>` auf die URL-Adresse des Berichtsservers festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="380b8-211">Verify that `<UrlRoot>` is set to the report server URL address.</span></span> <span data-ttu-id="380b8-212">Dieser Wert wird beim Konfigurieren des Berichtsservers festgelegt und sollte bereits ausgefüllt sein.</span><span class="sxs-lookup"><span data-stu-id="380b8-212">This value is set when you configure the report server and it should be filled in already.</span></span> <span data-ttu-id="380b8-213">Geben Sie andernfalls die URL-Adresse des Berichtsservers ein.</span><span class="sxs-lookup"><span data-stu-id="380b8-213">If it is not set, type the report server URL address.</span></span>  
  
10. <span data-ttu-id="380b8-214">Suchen Sie im Abschnitt Delivery nach `<ReportServerEmail>.`</span><span class="sxs-lookup"><span data-stu-id="380b8-214">In the Delivery section, find `<ReportServerEmail>.`</span></span>  
  
11. <span data-ttu-id="380b8-215">Deaktivieren Sie in `<SMTPServer>`die Werte für diese Einstellung, aber löschen Sie nicht die Tags.</span><span class="sxs-lookup"><span data-stu-id="380b8-215">In `<SMTPServer>`, clear any values for this setting, but do not delete the tags.</span></span>  
  
12. <span data-ttu-id="380b8-216">Legen Sie `<SendUsing>` auf 1 fest.</span><span class="sxs-lookup"><span data-stu-id="380b8-216">Set `<SendUsing>` to 1.</span></span> <span data-ttu-id="380b8-217">Bei einem anderen Wert ist der Berichtsserver nicht für die Verwendung eines lokalen SMTP-Diensts konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="380b8-217">If it is set another value, the report server is not configured to use a local SMTP service.</span></span>  
  
13. <span data-ttu-id="380b8-218">Legen Sie `<SMTPServerPickupDirectory>` auf einen Ordner auf dem lokalen Laufwerk fest.</span><span class="sxs-lookup"><span data-stu-id="380b8-218">Set `<SMTPServerPickupDirectory>` to a folder on the local drive.</span></span>  
  
14. <span data-ttu-id="380b8-219">Legen Sie `<From>` auf ein Konto fest, das über die Berechtigung zum Senden von E-Mail vom SMTP-Server verfügt.</span><span class="sxs-lookup"><span data-stu-id="380b8-219">Set `<From>` to an account that has permission to send e-mail from the SMTP server.</span></span>  
  
15. <span data-ttu-id="380b8-220">Speichern Sie die Datei .</span><span class="sxs-lookup"><span data-stu-id="380b8-220">Save the file.</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="380b8-221">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="380b8-221">See Also</span></span>  
 [<span data-ttu-id="380b8-222">Reporting Services-Konfigurations-Manager &#40;einheitlicher Modus&#41;</span><span class="sxs-lookup"><span data-stu-id="380b8-222">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
