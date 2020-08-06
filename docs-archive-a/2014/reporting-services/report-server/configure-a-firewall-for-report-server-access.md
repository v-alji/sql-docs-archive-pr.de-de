---
title: Konfigurieren einer Firewall für den Zugriff auf den Berichtsserver | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- firewall systems [Reporting Services]
- configuring servers [Reporting Services]
ms.assetid: 04dae07a-a3a4-424c-9bcb-a8000e20dc93
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b578c980522d24f5a24a73fdfd080ec425335aac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619607"
---
# <a name="configure-a-firewall-for-report-server-access"></a><span data-ttu-id="0f77a-102">Konfigurieren einer Firewall für den Zugriff auf den Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="0f77a-102">Configure a Firewall for Report Server Access</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="0f77a-103">-Berichtsserveranwendungen und veröffentlichte Berichte erfolgt über URLs, die eine IP-Adresse, einen Port und ein virtuelles Verzeichnis angeben.</span><span class="sxs-lookup"><span data-stu-id="0f77a-103">Report server applications and published reports are accessed through URLs that specify an IP address, port, and virtual directory.</span></span> <span data-ttu-id="0f77a-104">Wenn die Windows-Firewall aktiviert ist, ist der Port, für den der Berichtsserver konfiguriert ist, höchstwahrscheinlich geschlossen.</span><span class="sxs-lookup"><span data-stu-id="0f77a-104">If Windows Firewall is turned on, the port that the report server is configured to use is most likely closed.</span></span> <span data-ttu-id="0f77a-105">Ein Anzeichen dafür, dass der Port geschlossen ist, ist das Erscheinen einer leeren Webseite nach dem Anfordern eines Berichts oder eine leere Seite, wenn Sie versuchen, den Berichts-Manager von einem Remoteclientcomputer aus zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0f77a-105">Indications that a port might be closed are the appearance of a blank Web page after requesting a report, or a blank page when you attempt to open Report Manager from a remote client computer.</span></span>  
  
 <span data-ttu-id="0f77a-106">Um einen Port zu öffnen, müssen Sie das Hilfsprogramm Windows-Firewall auf dem Berichtsservercomputer verwenden.</span><span class="sxs-lookup"><span data-stu-id="0f77a-106">To open a port, you must use the Windows Firewall utility on the report server computer.</span></span> <span data-ttu-id="0f77a-107">Reporting Services öffnet keine Ports für Sie; Sie müssen diesen Schritt manuell ausführen.</span><span class="sxs-lookup"><span data-stu-id="0f77a-107">Reporting Services will not open ports for you; you must perform this step manually.</span></span>  
  
 <span data-ttu-id="0f77a-108">Standardmäßig lauscht der Berichtsserver HTTP-Anforderungen an Port 80.</span><span class="sxs-lookup"><span data-stu-id="0f77a-108">By default, the report server listens for HTTP requests on port 80.</span></span> <span data-ttu-id="0f77a-109">Die folgenden Anweisungen beinhalten daher Schritte, die diesen Port angeben.</span><span class="sxs-lookup"><span data-stu-id="0f77a-109">As such, the following instructions include steps that specify that port.</span></span> <span data-ttu-id="0f77a-110">Wenn Sie die Berichtsserver-URLs für einen anderen Port konfiguriert haben, müssen Sie die entsprechende Portnummer beim Ausführen der unten stehenden Anweisungen angeben.</span><span class="sxs-lookup"><span data-stu-id="0f77a-110">If you configured the report server URLs to use a different port, you must specify that port number when following the instructions below.</span></span>  
  
 <span data-ttu-id="0f77a-111">Wenn Sie auf relationale [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken auf externen Computern zugreifen oder wenn sich die Berichtsserver-Datenbank auf einer externen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz befindet, müssen Sie Port 1433 und Port 1434 auf dem externen Computer öffnen.</span><span class="sxs-lookup"><span data-stu-id="0f77a-111">If you are accessing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] relational databases on external computers, or if the report server database is on an external [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, you must open port 1433 and 1434 on the external computer.</span></span> <span data-ttu-id="0f77a-112">Weitere Informationen zur Windows-Firewall finden Sie unter [Konfigurieren einer Windows-Firewall für Datenbank-Engine-Zugriff](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="0f77a-112">For more information, see [Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="0f77a-113">Weitere Informationen zu den Standardeinstellungen der Windows-Firewall und eine Beschreibung der TCP-Ports, die sich auf das [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]und die [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]auswirken, finden Sie unter [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) (Konfigurieren der Windows-Firewall für den SQL Server-Zugriff) in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="0f77a-113">For more information about the default Windows firewall settings, and a description of the TCP ports that affect the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0f77a-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="0f77a-114">Prerequisites</span></span>  
 <span data-ttu-id="0f77a-115">Diese Anweisungen setzen voraus, dass Sie das Dienstkonto bereits konfiguriert, die Berichtsserver-Datenbank erstellt und die URLs für den Berichtsserver-Webdienst und Berichts-Manager konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="0f77a-115">These instructions assume that you already configured the service account, created the report server database, and configured URLs for the Report Server Web service and Report Manager.</span></span> <span data-ttu-id="0f77a-116">Weitere Informationen finden Sie unter [Verwalten eines Berichtsservers von Reporting Services im einheitlichen Modus](manage-a-reporting-services-native-mode-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="0f77a-116">For more information, see [Manage a Reporting Services Native Mode Report Server](manage-a-reporting-services-native-mode-report-server.md).</span></span>  
  
 <span data-ttu-id="0f77a-117">Außerdem sollten Sie überprüft haben, dass auf den Berichtsserver über eine lokale Webbrowserverbindung mit der lokalen Berichtsserverinstanz zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="0f77a-117">You should also have verified that the report server is accessible over a local Web browser connection to the local report server instance.</span></span> <span data-ttu-id="0f77a-118">Dieser Schritt setzt voraus, dass Sie eine Arbeitsinstallation haben.</span><span class="sxs-lookup"><span data-stu-id="0f77a-118">This step establishes that you have a working installation.</span></span> <span data-ttu-id="0f77a-119">Sie sollten überprüfen, ob die Installation ordnungsgemäß konfiguriert ist, bevor Sie mit dem Öffnen von Ports beginnen.</span><span class="sxs-lookup"><span data-stu-id="0f77a-119">You should verify that the installation is configured correctly before you begin opening ports.</span></span> <span data-ttu-id="0f77a-120">Um diesen Schritt auf Windows Server auszuführen, müssen Sie die Berichtsserversite außerdem zu den vertrauenswürdigen Sites hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="0f77a-120">To complete this step on  Windows Server, you must have also added the report server site to Trusted Sites.</span></span> <span data-ttu-id="0f77a-121">Weitere Informationen finden Sie unter [Konfigurieren eines Berichtsservers im einheitlichen Modus für die lokale Verwaltung &#40;SSRS&#41;](configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0f77a-121">For more information, see [Configure a Native Mode Report Server for Local Administration &#40;SSRS&#41;](configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span></span>  
  
## <a name="opening-ports-in-windows-firewall"></a><span data-ttu-id="0f77a-122">Öffnen von Ports in der Windows-Firewall</span><span class="sxs-lookup"><span data-stu-id="0f77a-122">Opening Ports in Windows Firewall</span></span>  
 <span data-ttu-id="0f77a-123">Für verschiedene Versionen der Windows-Firewall gibt es jeweils unterschiedliche Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="0f77a-123">There are separate instructions for different versions of Windows Firewall.</span></span>  
  
#### <a name="to-open-port-80-on-windows-7-windows-server-2008-r2-windows-server-2012-and-2012-r2"></a><span data-ttu-id="0f77a-124">So öffnen Sie Port 80 unter Windows 7, Windows Server 2008 R2, Windows Server 2012 und 2012 R2</span><span class="sxs-lookup"><span data-stu-id="0f77a-124">To open port 80 on Windows 7, Windows Server 2008 R2, Windows Server 2012 and 2012 R2</span></span>  
  
1.  <span data-ttu-id="0f77a-125">Klicken Sie im Menü **Start** auf **Systemsteuerung**und dann auf **System und Sicherheit**und **Windows-Firewall**.</span><span class="sxs-lookup"><span data-stu-id="0f77a-125">From the **Start** menu, click **Control Panel**, click **System and Security**, and then click **Windows Firewall**.</span></span> <span data-ttu-id="0f77a-126">Wenn die Systemsteuerung nicht für die Kategorieansicht konfiguriert ist, müssen Sie nur **Windows-Firewall**auswählen.</span><span class="sxs-lookup"><span data-stu-id="0f77a-126">Control Panel is not configured for 'Category' view, you only need to select **Windows Firewall.**</span></span>  
  
2.  <span data-ttu-id="0f77a-127">Klicken Sie auf **Erweiterte Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="0f77a-127">Click **Advanced Settings**.</span></span>  
  
3.  <span data-ttu-id="0f77a-128">Klicken Sie auf **Eingehende Regeln**.</span><span class="sxs-lookup"><span data-stu-id="0f77a-128">Click **Inbound Rules.**</span></span>  
  
4.  <span data-ttu-id="0f77a-129">Klicken Sie im Fenster **Aktionen** auf **Neue Regel\*\*\*\*.**</span><span class="sxs-lookup"><span data-stu-id="0f77a-129">Click **New Rule** in the **Actions** window **.**</span></span>  
  
5.  <span data-ttu-id="0f77a-130">Wählen Sie **Port** als **Regeltyp**aus.</span><span class="sxs-lookup"><span data-stu-id="0f77a-130">Click **Rule Type** of **Port.**</span></span>  
  
6.  <span data-ttu-id="0f77a-131">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="0f77a-131">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="0f77a-132">Klicken Sie auf der Seite **Protokolle und Ports** auf **TCP**.</span><span class="sxs-lookup"><span data-stu-id="0f77a-132">On the **Protocol and Ports** page click **TCP**.</span></span>  
  
8.  <span data-ttu-id="0f77a-133">Wählen Sie **Bestimmte lokale Ports** aus, und geben Sie den Wert **80**ein.</span><span class="sxs-lookup"><span data-stu-id="0f77a-133">Select **Specific Local Ports** and type a value of **80**.</span></span>  
  
9. <span data-ttu-id="0f77a-134">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="0f77a-134">Click **Next**.</span></span>  
  
10. <span data-ttu-id="0f77a-135">Klicken Sie auf der Seite **Aktion** auf **Verbindung zulassen**.</span><span class="sxs-lookup"><span data-stu-id="0f77a-135">On the **Action** page click **Allow the connection**.</span></span>  
  
11. <span data-ttu-id="0f77a-136">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="0f77a-136">Click **Next**.</span></span>  
  
12. <span data-ttu-id="0f77a-137">Klicken Sie auf der Seite **Profil** auf die entsprechenden Optionen für die Umgebung.</span><span class="sxs-lookup"><span data-stu-id="0f77a-137">On the **Profile** page click the appropriate options for your environment.</span></span>  
  
13. <span data-ttu-id="0f77a-138">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="0f77a-138">Click **Next**.</span></span>  
  
14. <span data-ttu-id="0f77a-139">Geben Sie auf der Seite **Name** den Namen**ReportServer (TCP an Port 80)** ein.</span><span class="sxs-lookup"><span data-stu-id="0f77a-139">On the **Name** page enter a name of**ReportServer (TCP on port 80)**</span></span>  
  
15. <span data-ttu-id="0f77a-140">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="0f77a-140">Click **Finish**.</span></span>  
  
16. <span data-ttu-id="0f77a-141">Starten Sie den Computer neu.</span><span class="sxs-lookup"><span data-stu-id="0f77a-141">Restart the computer.</span></span>  
  
#### <a name="to-open-port-80-on-windows-vista-or-windows-server-2008"></a><span data-ttu-id="0f77a-142">So öffnen Sie Port 80 unter Windows Vista oder Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="0f77a-142">To open port 80 on Windows Vista or Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="0f77a-143">Klicken Sie im **Startmenü** auf **Systemsteuerung**, klicken Sie auf **Sicherheit**, und klicken Sie dann auf **Windows-Firewall**.</span><span class="sxs-lookup"><span data-stu-id="0f77a-143">From the **Start** menu, click **Control Panel**, click **Security**, and then click **Windows Firewall**.</span></span>  
  
2.  <span data-ttu-id="0f77a-144">Klicken Sie auf **Programm durch die Windows-Firewall kommunizieren lassen**.</span><span class="sxs-lookup"><span data-stu-id="0f77a-144">Click **Allow a program through Windows Firewall**.</span></span>  
  
3.  <span data-ttu-id="0f77a-145">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="0f77a-145">Click **Continue**.</span></span>  
  
4.  <span data-ttu-id="0f77a-146">Klicken Sie auf der Registerkarte Ausnahmen auf **Port hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0f77a-146">On the Exceptions tab, click **Add Port**.</span></span>  
  
5.  <span data-ttu-id="0f77a-147">Geben Sie unter Name **den Namen Report Server (TCP an Port 80)** ein.</span><span class="sxs-lookup"><span data-stu-id="0f77a-147">In Name, type **ReportServer (TCP on port 80)**.</span></span>  
  
6.  <span data-ttu-id="0f77a-148">Geben Sie unter Port Nummer den Wert **80**ein.</span><span class="sxs-lookup"><span data-stu-id="0f77a-148">In Port number, type **80**.</span></span>  
  
7.  <span data-ttu-id="0f77a-149">Überprüfen Sie, ob **TCP** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="0f77a-149">Verify that **TCP** is selected.</span></span>  
  
8.  <span data-ttu-id="0f77a-150">Klicken Sie auf **Bereich ändern**.</span><span class="sxs-lookup"><span data-stu-id="0f77a-150">Click **Change Scope**.</span></span>  
  
9. <span data-ttu-id="0f77a-151">Klicken Sie auf eigenes **Netzwerk (Subnetz)**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f77a-151">Click **My network (subnet) only**, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="0f77a-152">Klicken Sie auf **OK** , um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="0f77a-152">Click **OK** to close the dialog box.</span></span>  
  
11. <span data-ttu-id="0f77a-153">Starten Sie den Computer neu.</span><span class="sxs-lookup"><span data-stu-id="0f77a-153">Restart the computer.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0f77a-154">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="0f77a-154">Next Steps</span></span>  
 <span data-ttu-id="0f77a-155">Nach dem Öffnen des Ports und vor dem Bestätigen, ob Remotebenutzer auf den Berichtsserver über den von Ihnen geöffneten Port zugreifen können, müssen Sie Benutzerzugriff auf den Berichtsserver über Rollenzuweisungen für den Stammordner und auf Siteebene erteilen.</span><span class="sxs-lookup"><span data-stu-id="0f77a-155">After you open the port and before you confirm whether remote users can access the report server on the port that you open, you must grant user access to the report server through role assignments on Home and at the site level.</span></span> <span data-ttu-id="0f77a-156">Ein Port kann richtig geöffnet sein und dennoch fehlgeschlagene Berichtsserververbindungen verursachen, wenn Benutzer nicht über entsprechende Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="0f77a-156">You can open a port correctly and still have report server connections fail if users do not have sufficient permissions.</span></span> <span data-ttu-id="0f77a-157">Weitere Informationen finden Sie unter [Gewähren von Benutzerzugriff auf einen Berichtsserver (Berichts-Manager)](../security/grant-user-access-to-a-report-server.md) in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="0f77a-157">For more information, see [Grant User Access to a Report Server &#40;Report Manager&#41;](../security/grant-user-access-to-a-report-server.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="0f77a-158">Sie können auch überprüfen, ob der Port richtig geöffnet ist, indem Sie den Berichts-Manager auf einem anderen Computer starten.</span><span class="sxs-lookup"><span data-stu-id="0f77a-158">You can also verify that the port is opened correctly by starting Report Manager on a different computer.</span></span> <span data-ttu-id="0f77a-159">Weitere Informationen finden Sie unter [Berichts-Manager (einheitlicher SSRS-Modus)](../report-manager-ssrs-native-mode.md) in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="0f77a-159">For more information, see [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f77a-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0f77a-160">See Also</span></span>  
 <span data-ttu-id="0f77a-161">[Konfigurieren des Berichtsserver-Dienstkontos &#40;SSRS-Konfigurations-Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="0f77a-161">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="0f77a-162">[Konfigurieren von Berichtsserver-URLs &#40;SSRS-Konfigurations-Manager&#41;](../install-windows/configure-report-server-urls-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="0f77a-162">[Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;](../install-windows/configure-report-server-urls-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="0f77a-163">[Erstellen einer Berichts Server-Datenbank &#40;SSRS-Configuration Manager&#41;](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="0f77a-163">[Create a Report Server Database  &#40;SSRS Configuration Manager&#41;](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="0f77a-164">[Konfigurieren des Berichtsserver-Dienstkontos &#40;SSRS-Konfigurations-Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="0f77a-164">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 [<span data-ttu-id="0f77a-165">Manage a Reporting Services Native Mode Report Server (Verwalten eines Berichtsservers von Reporting Services im einheitlichen Modus)</span><span class="sxs-lookup"><span data-stu-id="0f77a-165">Manage a Reporting Services Native Mode Report Server</span></span>](manage-a-reporting-services-native-mode-report-server.md)  
  
  
