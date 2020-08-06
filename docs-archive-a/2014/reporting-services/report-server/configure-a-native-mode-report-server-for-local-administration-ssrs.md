---
title: Konfigurieren eines Berichtsservers im einheitlichen Modus für die lokale Verwaltung (SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- UAC
- installing Reporting Services
- Windows Vista
- Localhost
- windows server 2008
- Vista
ms.assetid: 312c6bb8-b3f7-4142-a55f-c69ee15bbf52
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ad53f293ef825a382d9e39b58527a36ef291687a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619606"
---
# <a name="configure-a-native-mode-report-server-for-local-administration-ssrs"></a><span data-ttu-id="ba6d6-102">Konfigurieren eines Berichtsservers im einheitlichen Modus für die lokale Verwaltung (SSRS)</span><span class="sxs-lookup"><span data-stu-id="ba6d6-102">Configure a Native Mode Report Server for Local Administration (SSRS)</span></span>
  <span data-ttu-id="ba6d6-103">Für die Bereitstellung eines [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Berichtsservers unter einem der folgenden Betriebssysteme sind weitere Konfigurationsschritte erforderlich, wenn die Berichtsserverinstanz lokal verwaltet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-103">Deploying a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report server on one of the following operating systems requires more configuration steps if you want to administer the report server instance locally.</span></span> <span data-ttu-id="ba6d6-104">In diesem Thema wird beschrieben, wie der Berichtsserver für die lokale Verwaltung konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-104">This topic explains how to configure the report server for local administration.</span></span> <span data-ttu-id="ba6d6-105">Wenn Sie den Berichts Server noch nicht installiert oder konfiguriert haben, finden Sie weitere [Informationen unter Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md) und [manage a Reporting Services Report Server](manage-a-reporting-services-native-mode-report-server.md)(einheitlicher Modus).</span><span class="sxs-lookup"><span data-stu-id="ba6d6-105">If you have not yet installed or configured the report server, see [Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md) and [Manage a Reporting Services Native Mode Report Server](manage-a-reporting-services-native-mode-report-server.md).</span></span>  
  
||  
|-|  
|<span data-ttu-id="ba6d6-106">**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] im einheitlichen Modus</span><span class="sxs-lookup"><span data-stu-id="ba6d6-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode</span></span>|  
  
-   [!INCLUDE[winblue_server_2](../../includes/winblue-server-2-md.md)]  
  
-   [!INCLUDE[winblue_client_2](../../includes/winblue-client-2-md.md)]  
  
-   [!INCLUDE[win8](../../includes/win8-md.md)]  
  
-   [!INCLUDE[win8srv](../../includes/win8srv-md.md)]  
  
-   [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)]  
  
-   [!INCLUDE[win7](../../includes/win7-md.md)]  
  
-   [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)]  
  
 <span data-ttu-id="ba6d6-107">Da Berechtigungen durch die angegebenen Betriebssysteme beschränkt werden, führen Mitglieder der lokalen Gruppe Administratoren die meisten Anwendungen auf die gleiche Weise wie bei der Verwendung des Standardbenutzerkontos aus.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-107">Because the noted operating systems limit permissions, members of the local Administrators group run most applications as if they are using the Standard User account.</span></span>  
  
 <span data-ttu-id="ba6d6-108">Dieses Verfahren verbessert zwar die allgemeine Sicherheit des Systems, verhindert jedoch, dass Sie die vordefinierten integrierten Rollenzuweisungen verwenden, die von Reporting Services für lokale Administratoren erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-108">While this practice improves the overall security of your system, it prevents you from using the predefined, built-in role assignments that Reporting Services creates for local administrators.</span></span>  
  
-   [<span data-ttu-id="ba6d6-109">Übersicht der Konfigurationsänderungen</span><span class="sxs-lookup"><span data-stu-id="ba6d6-109">Overview of Configuration Changes</span></span>](#bkmk_configuraiton_overview)  
  
-   [<span data-ttu-id="ba6d6-110">So konfigurieren Sie den Berichtsserver und den Berichts-Manager für die lokale Verwaltung</span><span class="sxs-lookup"><span data-stu-id="ba6d6-110">To Configure Local Report Server and Report Manager Administration</span></span>](#bkmk_configure_local_server)  
  
-   [<span data-ttu-id="ba6d6-111">So konfigurieren Sie SQL Server Management Studio (SSMS) für die lokale Verwaltung des Berichtsservers</span><span class="sxs-lookup"><span data-stu-id="ba6d6-111">To Configure SQL Server Management Studio (SSMS) for local report server administration</span></span>](#bkmk_configure_ssms)  
  
-   [<span data-ttu-id="ba6d6-112">So konfigurieren Sie SQL Server Data Tools BI (SSDT) für die Veröffentlichung auf einem lokalen Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="ba6d6-112">To Configure SQL Server Data Tools BI (SSDT) to Publish to a Local Report Server</span></span>](#bkmk_configure_ssdt)  
  
-   [<span data-ttu-id="ba6d6-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ba6d6-113">Additional Information</span></span>](#bkmk_addiitonal_informaiton)  
  
##  <a name="overview-of-configuration-changes"></a><a name="bkmk_configuraiton_overview"></a><span data-ttu-id="ba6d6-114">Übersicht über Konfigurationsänderungen</span><span class="sxs-lookup"><span data-stu-id="ba6d6-114">Overview of Configuration Changes</span></span>  
 <span data-ttu-id="ba6d6-115">Durch die folgenden Konfigurationsänderungen wird der Server so konfiguriert, dass Berichtsserverinhalte und -vorgänge mit Standardbenutzerberechtigungen verwaltet werden können:</span><span class="sxs-lookup"><span data-stu-id="ba6d6-115">The following configuration changes configure the server so that you can use standard user permissions to manage report server content and operations:</span></span>  
  
-   <span data-ttu-id="ba6d6-116">Fügen Sie [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -URLs zu vertrauenswürdigen Websites hinzu.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-116">Add [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] URLs to trusted sites.</span></span> <span data-ttu-id="ba6d6-117">Internet Explorer wird unter den aufgelisteten Betriebssystemen standardmäßig im **geschützten Modus**ausgeführt. Diese Funktion verhindert, dass Browseranforderungen Prozesse auf hoher Ebene erreichen, die auf demselben Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-117">By default, Internet Explorer running on the listed operating systems runs in **Protected Mode**, a feature that blocks browser requests from reaching high-level processes that run on the same computer.</span></span> <span data-ttu-id="ba6d6-118">Sie können den geschützten Modus für die Berichtsserveranwendungen deaktivieren, indem Sie sie als vertrauenswürdige Sites hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-118">You can disable protected mode for the report server applications by adding them as Trusted Sites.</span></span>  
  
-   <span data-ttu-id="ba6d6-119">Erstellen Sie Rollenzuweisungen, die Ihnen als Berichtsserveradministrator die Berechtigung zur Verwaltung von Inhalt und Vorgängen verleihen, ohne die Funktion **Als Administrator ausführen** in Internet Explorer verwenden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-119">Create role assignments that grant you, the report server administrator, permission to manage content and operations without having to use the **Run as administrator** feature on Internet Explorer.</span></span> <span data-ttu-id="ba6d6-120">Durch das Erstellen von Rollenzuweisungen für Ihr Windows-Benutzerkonto erhalten Sie Zugriff auf einen Berichtsserver mit Inhalts-Manager- und Systemadministratorberechtigungen durch explizite Rollenzuweisungen, die die vordefinierten, integrierten Rollenzuweisungen ersetzen, die von Reporting Services erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-120">By creating role assignments for your Windows user account, you gain access to a report server with Content Manager and System Administrator permissions through explicit role assignments that replace the predefined, built-in role assignments that Reporting Services creates.</span></span>  
  
##  <a name="to-configure-local-report-server-and-report-manager-administration"></a><a name="bkmk_configure_local_server"></a><span data-ttu-id="ba6d6-121">So konfigurieren Sie den lokalen Berichts Server und die Berichts-Manager Verwaltung</span><span class="sxs-lookup"><span data-stu-id="ba6d6-121">To Configure Local Report Server and Report Manager Administration</span></span>  
 <span data-ttu-id="ba6d6-122">Führen Sie die Konfigurationsschritte in diesem Abschnitt aus, wenn beim Navigieren zu einem lokalen Berichtsserver eine mit der folgenden vergleichbare Fehlermeldung angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="ba6d6-122">Complete the configuration steps in this section if you are browsing to a local report server and you see errors similar to the following:</span></span>  
  
-   <span data-ttu-id="ba6d6-123">Der Benutzer `'Domain\[user name]`' verfügt nicht über die erforderlichen Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-123">User `'Domain\[user name]`' does not have required permissions.</span></span> <span data-ttu-id="ba6d6-124">Stellen Sie sicher, dass ausreichende Berechtigungen erteilt und die Einschränkungen der Windows-Benutzerkontensteuerung (UAC) behandelt wurden.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-124">Verify that sufficient permissions have been granted and Windows User Account Control (UAC) restrictions have been addressed.</span></span>  
  
###  <a name="trusted-site-settings-in-the-browser"></a><a name="bkmk_site_settings"></a><span data-ttu-id="ba6d6-125">Einstellungen für vertrauenswürdige Websites im Browser</span><span class="sxs-lookup"><span data-stu-id="ba6d6-125">Trusted Site Settings in the Browser</span></span>  
  
1.  <span data-ttu-id="ba6d6-126">Öffnen Sie ein Browserfenster mit "Als Administrator ausführen"-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-126">Open a browser window with Run as administrator permissions.</span></span> <span data-ttu-id="ba6d6-127">Klicken Sie im Menü **Start** auf **Alle Programme**, klicken Sie mit der rechten Maustaste auf **Internet Explorer**, und wählen Sie **Als Administrator ausführen**aus.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-127">From the **Start** menu, click **All Programs**, right-click **Internet Explorer**, and select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="ba6d6-128">Klicken Sie auf **Zulassen** , um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-128">Click **Allow** to continue.</span></span>  
  
3.  <span data-ttu-id="ba6d6-129">Geben Sie in der URL-Adresse die Berichts-Manager-URL ein.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-129">In the URL address, enter the Report Manager URL.</span></span> <span data-ttu-id="ba6d6-130">Anweisungen finden Sie unter [Berichts-Manager (einheitlicher SSRS-Modus)](../report-manager-ssrs-native-mode.md) in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-130">For instructions, see [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
4.  <span data-ttu-id="ba6d6-131">Klicken Sie auf **Extras**.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-131">Click **Tools**.</span></span>  
  
5.  <span data-ttu-id="ba6d6-132">Klicken Sie auf **Internetoptionen**.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-132">Click **Internet Options**.</span></span>  
  
6.  <span data-ttu-id="ba6d6-133">Klicken Sie auf **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-133">Click **Security**.</span></span>  
  
7.  <span data-ttu-id="ba6d6-134">Klicken Sie auf **Vertrauenswürdige Sites**.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-134">Click **Trusted Sites**.</span></span>  
  
8.  <span data-ttu-id="ba6d6-135">Klicken Sie auf **Websites**.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-135">Click **Sites**.</span></span>  
  
9. <span data-ttu-id="ba6d6-136">Fügen Sie `http://<your-server-name>`hinzu.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-136">Add `http://<your-server-name>`.</span></span>  
  
10. <span data-ttu-id="ba6d6-137">Deaktivieren Sie das Kontrollkästchen **Für Sites dieser Zone ist eine Serverüberprüfung (https:) erforderlich** , falls Sie HTTPS nicht für die Standardwebsite verwenden.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-137">Clear the check box **Require server certification (https:) for all sites in this zone** if you are not using HTTPS for the default site.</span></span>  
  
11. <span data-ttu-id="ba6d6-138">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-138">Click **Add**.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
###  <a name="report-manager-folder-settings"></a><a name="bkmk_configure_folder_settings"></a> <span data-ttu-id="ba6d6-139">Ordnereinstellungen im Berichts-Manager</span><span class="sxs-lookup"><span data-stu-id="ba6d6-139">Report Manager Folder Settings</span></span>  
  
1.  <span data-ttu-id="ba6d6-140">Klicken Sie im Berichts-Manager auf der Startseite auf **Ordnereinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-140">In Report Manager, on the Home page, click **Folder Settings**.</span></span>  
  
2.  <span data-ttu-id="ba6d6-141">Klicken Sie auf der Seite Ordnereinstellungen auf **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-141">In the Folder Settings page, click **Security**.</span></span>  
  
3.  <span data-ttu-id="ba6d6-142">Klicken Sie auf **Neue Rollenzuweisung**.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-142">Click **New Role Assignment**.</span></span>  
  
4.  <span data-ttu-id="ba6d6-143">Geben Sie im Feld **Gruppen- oder Benutzername** Ihr Windows-Benutzerkonto im folgenden Format ein: `<domain>\<user>`.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-143">In the **Group or user name** field, type your Windows user account in this format: `<domain>\<user>`.</span></span>  
  
5.  <span data-ttu-id="ba6d6-144">Wählen Sie **Inhalts-Manager**aus.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-144">Select **Content Manager**.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
###  <a name="report-manager-site-settings"></a><a name="bkmk_configure_site_settings"></a> <span data-ttu-id="ba6d6-145">Siteeinstellungen im Berichts-Manager</span><span class="sxs-lookup"><span data-stu-id="ba6d6-145">Report Manager Site Settings</span></span>  
  
1.  <span data-ttu-id="ba6d6-146">Öffnen Sie den Browser mit Administratorprivilegien, und navigieren Sie zum Berichts-Manager unter `http://<server name>/reports`.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-146">Open your browser with administrative privileges and browse to report manager, `http://<server name>/reports`.</span></span>  
  
2.  <span data-ttu-id="ba6d6-147">Klicken Sie in der oberen Ecke der Startseite auf **Siteeinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="ba6d6-147">Click **Site Settings** in the upper corner of the Home page.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="ba6d6-148">**Hinweis:** Wenn die Option **Siteeinstellungen** nicht angezeigt wird, schließen Sie den Browser, öffnen Sie ihn mit Administratorprivilegien erneut, und navigieren Sie zum Berichts-Manager.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-148">**Note:** If you do not see the **Site Settings** option, close and reopen your browser and browse to report manager with administrative privileges.</span></span>  
  
3.  <span data-ttu-id="ba6d6-149">Klicken Sie auf **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-149">Click **security**.</span></span>  
  
4.  <span data-ttu-id="ba6d6-150">Klicken Sie auf **Neue Rollenzuweisung**.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-150">Click **New Role Assignment**.</span></span>  
  
5.  <span data-ttu-id="ba6d6-151">Geben Sie im Feld **Gruppen- oder Benutzername** Ihr Windows-Benutzerkonto im folgenden Format ein: `<domain>\<user>`.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-151">In the **Group or user name** field, type your Windows user account in this format: `<domain>\<user>`.</span></span>  
  
6.  <span data-ttu-id="ba6d6-152">Wählen Sie **Systemadministrator**aus.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-152">Select **System Administrator**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="ba6d6-153">Schließen Sie den Berichts-Manager.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-153">Close Report Manager.</span></span>  
  
9. <span data-ttu-id="ba6d6-154">Öffnen Sie den Berichts-Manager in Internet Explorer erneut, ohne **Als Administrator ausführen**zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-154">Re-open Report Manager in Internet Explorer, without using **Run as administrator**.</span></span>  
  
##  <a name="to-configure-sql-server-management-studio-ssms-for-local-report-server-administration"></a><a name="bkmk_configure_ssms"></a><span data-ttu-id="ba6d6-155">So konfigurieren Sie SQL Server Management Studio (SSMS) für die lokale Verwaltung des Berichts Servers</span><span class="sxs-lookup"><span data-stu-id="ba6d6-155">To Configure SQL Server Management Studio (SSMS) for local report server administration</span></span>  
 <span data-ttu-id="ba6d6-156">Standardmäßig ist es nur möglich, auf alle in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] verfügbaren Berichtsservereigenschaften zuzugreifen, wenn Sie [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] mit Administratorprivilegien starten.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-156">By default, you cannot access all of the report server properties available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] unless you start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with administrative privileges.</span></span>  
  
 <span data-ttu-id="ba6d6-157">**So konfigurieren Sie [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]** , sodass [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] nicht jedes Mal mit erweiterten Berechtigungen gestartet werden muss:</span><span class="sxs-lookup"><span data-stu-id="ba6d6-157">**To configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]** role properties and role assignments so you do not need to start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with elevated permissions each time:</span></span>  
  
-   <span data-ttu-id="ba6d6-158">Klicken Sie im Menü **Start** auf **Alle Programme**und anschließend auf **SQL Server 2014**. Klicken Sie mit der rechten Maustaste auf **[!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**, und klicken Sie anschließend auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-158">From the **Start** menu, click **All Programs**, click **SQL Server 2014**, right-click **[!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**, and then click **Run as administrator**.</span></span>  
  
-   <span data-ttu-id="ba6d6-159">Stellen Sie eine Verbindung mit dem lokalen [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Server her.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-159">Connect to your local [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] server.</span></span>  
  
-   <span data-ttu-id="ba6d6-160">Klicken Sie im Knoten **Sicherheit** auf **Systemrollen**.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-160">In the **Security** node, click **System Roles**.</span></span>  
  
-   <span data-ttu-id="ba6d6-161">Klicken Sie mit der rechten Maustaste auf **Systemadministrator** , und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-161">Right-click **System Administrator** and then click **Properties**.</span></span>  
  
-   <span data-ttu-id="ba6d6-162">Wählen Sie auf der Seite **Systemrolleneigenschaften** die Option **Berichtsservereigenschaften anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-162">In the **System Role Properties** page, select **View report server properties**.</span></span> <span data-ttu-id="ba6d6-163">Wählen Sie weitere Eigenschaften aus, die Sie Mitgliedern der Systemadministratorrolle zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-163">Select any other properties you want associated with members of the system administrators role.</span></span>  
  
-   <span data-ttu-id="ba6d6-164">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-164">Click **OK**.</span></span>  
  
-   <span data-ttu-id="ba6d6-165">Schließen [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba6d6-165">Close [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]</span></span>  
  
-   <span data-ttu-id="ba6d6-166">Informationen zum Hinzufügen eines Benutzers zur Systemrolle "Systemadministrator" finden Sie im Abschnitt [Siteeinstellungen im Berichts-Manager](#bkmk_configure_site_settings) weiter oben in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-166">To add a user to the system role "system administrator", see the [Report Manager Site Settings](#bkmk_configure_site_settings) section earlier in this topic.</span></span>  
  
 <span data-ttu-id="ba6d6-167">Wenn Sie jetzt [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] öffnen und nicht explizit **Als Administrator ausführen** auswählen, haben Sie Zugriff auf die Berichtsservereigenschaften.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-167">Now when you open [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and do not explicitly select **Run as administrator** you have access to the report server properties.</span></span>  
  
##  <a name="to-configure-sql-server-data-tools-bi-ssdt-to-publish-to-a-local-report-server"></a><a name="bkmk_configure_ssdt"></a><span data-ttu-id="ba6d6-168">So konfigurieren Sie SQL Server Data Tools BI (SSDT) für die Veröffentlichung auf einem lokalen Berichts Server</span><span class="sxs-lookup"><span data-stu-id="ba6d6-168">To Configure SQL Server Data Tools BI (SSDT) to Publish to a Local Report Server</span></span>  
 <span data-ttu-id="ba6d6-169">Wenn Sie [!INCLUDE[SSDTDev11](../../includes/ssdtdev11-md.md)] unter einem der im ersten Abschnitt dieses Themas aufgeführten Betriebssysteme installiert haben und SSDT mit einem lokalen Berichtsserver im einheitlichen Modus interagieren soll, treten Berechtigungsfehler auf, sofern Sie [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] nicht mit erweiterten Berechtigungen öffnen oder Reporting Services-Rollen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-169">If you installed [!INCLUDE[SSDTDev11](../../includes/ssdtdev11-md.md)] on one of the operating systems listed in the first section of this topic, and you want SSDT to interact with a local Native mode report server, you will experiences permission errors unless you open [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] with elevated permissions or configure reporting services roles.</span></span> <span data-ttu-id="ba6d6-170">Wenn Sie nicht über ausreichende Berechtigungen verfügen, können z. B. folgende Probleme auftreten:</span><span class="sxs-lookup"><span data-stu-id="ba6d6-170">For example, if you do not have sufficient permissions, you experience issues similar to the following:</span></span>  
  
-   <span data-ttu-id="ba6d6-171">Beim Versuch, Berichtselemente auf dem lokalen Berichtsserver bereitzustellen, wird im Fenster **Fehlerliste** eine Fehlermeldung wie die folgende angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ba6d6-171">When you attempt to deploy report items to the local report server, you see an error message similar to the following in the **Error List** window:</span></span>  
  
    -   <span data-ttu-id="ba6d6-172">Die dem Benutzer „Domain\\<Benutzername\>“ erteilten Berechtigungen reichen zum Ausführen des Vorgangs nicht aus.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-172">The permissions granted to user 'Domain\\<user name\>' are insufficient for performing this operation.</span></span>  
  
 <span data-ttu-id="ba6d6-173">**So verwenden Sie bei jedem Öffnen von SSDT erweiterte Berechtigungen**</span><span class="sxs-lookup"><span data-stu-id="ba6d6-173">**To run with elevated permissions each time you open SSDT:**</span></span>  
  
1.  <span data-ttu-id="ba6d6-174">Geben Sie auf dem Startbildschirm ein, `sql server` und klicken Sie dann mit der rechten Maustaste auf **SQL Server Data Tools für Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-174">From the start screen, type `sql server` and then right-click **SQL Server Data Tools for Visual Studio**.</span></span> <span data-ttu-id="ba6d6-175">Klicken Sie auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-175">Click **Run as administrator**</span></span>  
  
     <span data-ttu-id="ba6d6-176">**Oder**verfahren Sie bei älteren Betriebssystemen wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ba6d6-176">**Or**, on older operating systems:</span></span>  
  
     <span data-ttu-id="ba6d6-177">Klicken Sie im Menü **Start** auf **Alle Programme**und dann auf **SQL Server 2014**. Klicken Sie mit der rechten Maustaste auf **SQL Server Data Tools**und dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-177">From the **Start** menu, click **All Programs**, click **SQL Server 2014**, right-click **SQL Server Data Tools**, and then click **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="ba6d6-178">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-178">Click **Continue**.</span></span>  
  
3.  <span data-ttu-id="ba6d6-179">Klicken Sie auf **Programm ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-179">Click **Run Program**.</span></span>  
  
 <span data-ttu-id="ba6d6-180">Sie können jetzt Berichte und andere Elemente auf einem lokalen Berichtsserver bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-180">You should now be able to deploy reports and other items to a local report server.</span></span>  
  
 <span data-ttu-id="ba6d6-181">**So konfigurieren Sie [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Rollenzuweisungen, damit SSDT nicht jedes Mal mit erweiterten Berechtigungen gestartet werden muss**</span><span class="sxs-lookup"><span data-stu-id="ba6d6-181">**To configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] role assignments so you do not need to start SSDT with elevated permissions each time:**</span></span>  
  
-   <span data-ttu-id="ba6d6-182">Siehe die Abschnitte [Ordnereinstellungen im Berichts-Manager](#bkmk_configure_folder_settings) und [Siteeinstellungen im Berichts-Manager](#bkmk_configure_site_settings) weiter oben in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-182">See the [Report Manager Folder Settings](#bkmk_configure_folder_settings) and [Report Manager Site Settings](#bkmk_configure_site_settings) sections earlier in this topic.</span></span>  
  
##  <a name="additional-information"></a><a name="bkmk_addiitonal_informaiton"></a><span data-ttu-id="ba6d6-183">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ba6d6-183">Additional Information</span></span>  
 <span data-ttu-id="ba6d6-184">Ein weiterer häufiger Konfigurationsschritt in Verbindung mit der Verwaltung von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] besteht darin, Port 80 in der Windows-Firewall zu öffnen, um den Zugriff auf den Berichtsservercomputer zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="ba6d6-184">An additional and common configuration step related to [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] administration is to open port 80 in Windows Firewall to allow access to the report server computer.</span></span> <span data-ttu-id="ba6d6-185">Anweisungen finden Sie unter [Configure a Firewall for Report Server Access](configure-a-firewall-for-report-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="ba6d6-185">For instructions, see [Configure a Firewall for Report Server Access](configure-a-firewall-for-report-server-access.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba6d6-186">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ba6d6-186">See Also</span></span>  
 [<span data-ttu-id="ba6d6-187">Manage a Reporting Services Native Mode Report Server (Verwalten eines Berichtsservers von Reporting Services im einheitlichen Modus)</span><span class="sxs-lookup"><span data-stu-id="ba6d6-187">Manage a Reporting Services Native Mode Report Server</span></span>](manage-a-reporting-services-native-mode-report-server.md)  
  
  
