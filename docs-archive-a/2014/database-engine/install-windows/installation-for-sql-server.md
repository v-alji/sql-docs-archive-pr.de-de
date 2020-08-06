---
title: Installation für SQL Server 2014 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/09/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
f1_keywords:
- sql12.portal.Installation.f1
helpviewer_keywords:
- installing SQL Server, initial installation
- installation [SQL Server]
- initial installation [SQL Server]
ms.assetid: edd75f68-dc62-4479-a596-57ce8ad632e5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 62630400f276b00de8acfa875244558cdb39e47b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697109"
---
# <a name="installation-for-sql-server-2014"></a><span data-ttu-id="91928-102">Installation für SQLServer 2014</span><span class="sxs-lookup"><span data-stu-id="91928-102">Installation for SQL Server 2014</span></span>
 ## <a name="download-sql-server-2014-express"></a>[<span data-ttu-id="91928-103">Download SQL Server 2014 Express</span><span class="sxs-lookup"><span data-stu-id="91928-103">Download SQL Server 2014 Express</span></span>](http://www.hanselman.com/blog/DownloadSQLServerExpress.aspx)
  <span data-ttu-id="91928-104">**Vielen Dank, dass [Scott Hanselman](http://www.hanselman.com/) alle installerpaketverknüpfungen an einem Ort sammelt!**</span><span class="sxs-lookup"><span data-stu-id="91928-104">**Thank you to [Scott Hanselman](http://www.hanselman.com/) for collecting all of the installer package links in one place!**</span></span>
  
  <span data-ttu-id="91928-105">Der Installations-Assistent für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] enthält eine einzelne Funktionsstruktur für die Installation aller [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Komponenten:</span><span class="sxs-lookup"><span data-stu-id="91928-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard provides a single feature tree to install all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components:</span></span>  
  
-   [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]  
  
-   [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)]  
  
-   [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)]  
  
-   <span data-ttu-id="91928-106">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="91928-106">Management tools</span></span>  
  
-   <span data-ttu-id="91928-107">Konnektivitätskomponenten</span><span class="sxs-lookup"><span data-stu-id="91928-107">Connectivity components</span></span>  
  
 <span data-ttu-id="91928-108">Sie können jede Komponente einzeln installieren oder eine Kombination der oben aufgelisteten Komponenten auswählen.</span><span class="sxs-lookup"><span data-stu-id="91928-108">You can install each component individually or select a combination of the components listed above.</span></span> <span data-ttu-id="91928-109">Informationen zu den in verfügbaren Editionen und Komponenten finden Sie unter [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [Editionen und Komponenten von SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) und Features, [die von den Editionen von SQL Server 2014 unterstützt](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)werden.</span><span class="sxs-lookup"><span data-stu-id="91928-109">To make the best choice among the editions and components available in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Editions and Components of SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) and [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="91928-110">ist als 32- und 64-Bit-Edition verfügbar.</span><span class="sxs-lookup"><span data-stu-id="91928-110">is available in 32-bit and 64-bit editions.</span></span>
 
 <span data-ttu-id="91928-111">**Probieren Sie es aus:**</span><span class="sxs-lookup"><span data-stu-id="91928-111">**Try it out:**</span></span>  
  
-   <span data-ttu-id="91928-112">Sie haben ein Azure-Konto?</span><span class="sxs-lookup"><span data-stu-id="91928-112">Have an Azure account?</span></span>  <span data-ttu-id="91928-113">Wechseln Sie anschließend **[hierhin](https://ms.portal.azure.com/?flight=1#create/Microsoft.SQLServer2016RTMEnterpriseWindowsServer2012R2)** , um einen virtuellen Computer zu starten, auf dem SQL Server 2014 Service Pack 1 (SP1) bereits installiert ist.</span><span class="sxs-lookup"><span data-stu-id="91928-113">Then go **[Here](https://ms.portal.azure.com/?flight=1#create/Microsoft.SQLServer2016RTMEnterpriseWindowsServer2012R2)** to spin up a Virtual Machine with SQL Server 2014 Service Pack 1 (SP1) already installed.</span></span> <span data-ttu-id="91928-114">Weitere Informationen zu SQL Server 2014 (SP1) finden Sie unter [SQL Server 2014 Service Pack 1 Release Information](https://support.microsoft.com/kb/3058865).</span><span class="sxs-lookup"><span data-stu-id="91928-114">For more information on SQL Server 2014 (SP1), see [SQL Server 2014 Service Pack 1 release information](https://support.microsoft.com/kb/3058865).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="91928-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="91928-115">In This Section</span></span>  
 <span data-ttu-id="91928-116">Unabhängig davon, ob Sie die Installation von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe des Installations-Assistenten für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]oder über die Eingabeaufforderung vornehmen, umfasst das Setup immer folgende Schritte:</span><span class="sxs-lookup"><span data-stu-id="91928-116">Regardless of whether you use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard or the command prompt to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Setup involves the following steps:</span></span>  
  
 [<span data-ttu-id="91928-117">Planen einer SQL Server-Installation</span><span class="sxs-lookup"><span data-stu-id="91928-117">Planning a SQL Server Installation</span></span>](../../sql-server/install/planning-a-sql-server-installation.md)  
 <span data-ttu-id="91928-118">Beschreibt, wie der Computer auf [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]vorbereitet wird:</span><span class="sxs-lookup"><span data-stu-id="91928-118">Describes how to prepare your computer for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="91928-119">Hardware- und Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="91928-119">Hardware and software requirements.</span></span>  
  
-   <span data-ttu-id="91928-120">Anforderungen für die Systemkonfigurationsprüfung sowie Blockadefaktoren.</span><span class="sxs-lookup"><span data-stu-id="91928-120">System Configuration Checker requirements and blocking issues.</span></span>  
  
-   <span data-ttu-id="91928-121">Überlegungen zur Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="91928-121">Security considerations.</span></span>  
  
 [<span data-ttu-id="91928-122">Installieren von SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="91928-122">Install SQL Server 2014</span></span>](install-sql-server.md)  
 <span data-ttu-id="91928-123">Beschreibt Installationsoptionen für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91928-123">Describes installation options for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="91928-124">Upgrade auf SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="91928-124">Upgrade to SQL Server 2014</span></span>](upgrade-sql-server.md)  
 <span data-ttu-id="91928-125">Beschreibt Optionen zum Aktualisieren auf [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91928-125">Describes options for upgrading to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="91928-126">Deinstallieren von SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="91928-126">Uninstall SQL Server 2014</span></span>](../../sql-server/install/uninstall-sql-server.md)  
 <span data-ttu-id="91928-127">Beschreibt Verfahren zum Deinstallieren von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91928-127">Describes procedures to uninstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)].</span></span>  
  
 [<span data-ttu-id="91928-128">SQL Server-Failoverclusterinstallation</span><span class="sxs-lookup"><span data-stu-id="91928-128">SQL Server Failover Cluster Installation</span></span>](../../sql-server/failover-clusters/install/sql-server-failover-cluster-installation.md)  
 <span data-ttu-id="91928-129">In diesem Abschnitt der Dokumentation zum [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Setup wird die Installation und Konfiguration von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Failoverclustern beschrieben.</span><span class="sxs-lookup"><span data-stu-id="91928-129">This section of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup documentation explains how to install, and configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster.</span></span>  
  
 [<span data-ttu-id="91928-130">Installieren von SQL Server 2014-BI-Funktionen</span><span class="sxs-lookup"><span data-stu-id="91928-130">Install SQL Server 2014 BI Features</span></span>](../../sql-server/install/install-sql-server-business-intelligence-features.md)  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="91928-131">Funktionen, die Teil der Microsoft BI-Plattform darstellen, sind [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]sowie mehrere Clientanwendungen, die zum Erstellen von oder Arbeiten mit analytischen Daten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="91928-131">features that are part of the Microsoft BI platform include [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and several client applications used for creating or working with analytical data.</span></span> <span data-ttu-id="91928-132">In diesem Abschnitt der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Setupdokumentation wird erläutert, wie [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] und [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]installiert werden.</span><span class="sxs-lookup"><span data-stu-id="91928-132">This section of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup documentation explains how to install [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="91928-133">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="91928-133">Related Sections</span></span>  
 [<span data-ttu-id="91928-134">Themen zu Vorgehensweisen für die Installation</span><span class="sxs-lookup"><span data-stu-id="91928-134">Installation How-to Topics</span></span>](../../sql-server/install/installation-how-to-topics.md)  
 <span data-ttu-id="91928-135">Enthält Links zu verfahrensspezifischen Themen für die Installation von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit dem Installations-Assistenten, über die Eingabeaufforderung, unter Verwendung von Konfigurationsdateien sowie mithilfe von "SysPrep".</span><span class="sxs-lookup"><span data-stu-id="91928-135">Provides links to procedural topics for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] from the installation wizard, from the command prompt, by using configuration files, and by using SysPrep.</span></span>  
  
 [<span data-ttu-id="91928-136">Installieren Sie SQL Server BI-Funktionen mit SharePoint &#40;Power Pivot und Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="91928-136">Install SQL Server BI Features with SharePoint &#40;PowerPivot and Reporting Services&#41;</span></span>](../../sql-server/install/install-sql-server-bi-features-sharepoint-powerpivot-reporting-services.md)  
 <span data-ttu-id="91928-137">In diesem Abschnitt wird erläutert, wie Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Funktionen in einer SharePoint-Umgebung installieren.</span><span class="sxs-lookup"><span data-stu-id="91928-137">This section explains how to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features in a SharePoint environment.</span></span> <span data-ttu-id="91928-138">Es wird angegeben, welche [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Funktionen für eine bestimmte Version oder Edition von SharePoint verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="91928-138">It identifies which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features are available given a specific version and edition of SharePoint.</span></span> <span data-ttu-id="91928-139">Außerdem umfasst der Abschnitt Installationsschritte für PowerPivot für SharePoint und Reporting Services im SharePoint-Modus.</span><span class="sxs-lookup"><span data-stu-id="91928-139">It also includes installation procedures for PowerPivot for SharePoint and Reporting Services in SharePoint mode.</span></span>  
  
 [<span data-ttu-id="91928-140">Installieren der SQL Server-Beispiele und -Beispieldatenbanken</span><span class="sxs-lookup"><span data-stu-id="91928-140">Installing SQL Server Samples and Sample Databases</span></span>](https://sqlserversamples.codeplex.com/)  
 <span data-ttu-id="91928-141">Beschreibt, wie Sie die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Beispiele und -Beispieldatenbanken installieren und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="91928-141">Describes how to install and configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] samples and sample databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91928-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="91928-142">See Also</span></span>  
 <span data-ttu-id="91928-143">[Neuerungen bei der SQL Server Installation](../../sql-server/install/what-s-new-in-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="91928-143">[What's New in SQL Server Installation](../../sql-server/install/what-s-new-in-sql-server-installation.md) </span></span>  
 [<span data-ttu-id="91928-144">Hardware- und Softwareanforderungen für die Installation von SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="91928-144">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md)  
  
