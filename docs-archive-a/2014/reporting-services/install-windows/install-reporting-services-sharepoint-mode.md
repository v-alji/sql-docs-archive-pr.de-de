---
title: Reporting Services Installation im SharePoint-Modus (SharePoint 2010 und SharePoint 2013) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- default configuration [Reporting Services]
- installing Reporting Services, SharePoint integrated mode
- installation options [Reporting Services]
ms.assetid: ac6cba68-2665-4a39-8fa3-cb7d7e6723c0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c27b6f9fbeebcc896b1a6097cb51e8d2e15924bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609037"
---
# <a name="reporting-services-sharepoint-mode-installation-sharepoint-2010-and-sharepoint-2013"></a><span data-ttu-id="abf6c-102">Reporting Services-Installation im SharePoint-Modus (SharePoint 2010 und SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="abf6c-102">Reporting Services SharePoint Mode Installation (SharePoint 2010 and SharePoint 2013)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]<span data-ttu-id="abf6c-103">im SharePoint-Modus ist eine Auflistung von Serverkomponenten, die die Generierung und Übermittlung von Berichten bereitstellen, basierend auf [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -und [!INCLUDE[msCoName](../../includes/msconame-md.md)] SharePoint-Produkten.</span><span class="sxs-lookup"><span data-stu-id="abf6c-103">in SharePoint mode is a collection of server components that provide report generation and delivery, based on [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[msCoName](../../includes/msconame-md.md)] SharePoint products.</span></span>  
  
 <span data-ttu-id="abf6c-104">Bei Ausführung von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] im SharePoint-Modus werden [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)]- und Datenwarnungsfunktionen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="abf6c-104">Running [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode provides the [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] and data alerting features.</span></span> <span data-ttu-id="abf6c-105">Weitere Informationen zu Funktionen im SharePoint-Modus finden Sie im Abschnitt "Funktions Unterstützung und Verhaltensunterschiede nach Server Modus" in [Reporting Services Berichts Servers](../reporting-services-report-server.md) .</span><span class="sxs-lookup"><span data-stu-id="abf6c-105">For more information regarding features in SharePoint mode, see the section "Feature Support and Behavior Differences by Server Mode" in [Reporting Services Report Server](../reporting-services-report-server.md)</span></span>  
  
 <span data-ttu-id="abf6c-106">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] im SharePoint-Modus erfordert zwei grundlegende Installationen:</span><span class="sxs-lookup"><span data-stu-id="abf6c-106">There are two fundamental installations needed for [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode:</span></span>  
  
|<span data-ttu-id="abf6c-107">Installation</span><span class="sxs-lookup"><span data-stu-id="abf6c-107">Installation</span></span>|<span data-ttu-id="abf6c-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="abf6c-108">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="abf6c-109">Das [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Add-in für SharePoint-Produkte.</span><span class="sxs-lookup"><span data-stu-id="abf6c-109">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] add-in for SharePoint products.</span></span>|<span data-ttu-id="abf6c-110">Durch das Add-In werden die Seiten und Funktionen der [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Benutzeroberfläche auf einem SharePoint-Web-Front-End-Server installiert.</span><span class="sxs-lookup"><span data-stu-id="abf6c-110">The add-in installs the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] user interface (UI) pages and features on a SharePoint web front-end server.</span></span> <span data-ttu-id="abf6c-111">Die Benutzeroberflächenfunktionen umfassen [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)], Verwaltungsseiten in der SharePoint-Zentraladministration, innerhalb der SharePoint-Dokumentbibliotheken verwendete Funktionsseiten sowie Seiten für [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Datenwarnungen.</span><span class="sxs-lookup"><span data-stu-id="abf6c-111">The UI features include [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)], administration pages in SharePoint Central Administration, feature pages used within SharePoint document libraries, and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Data Alerting pages.</span></span>|  
|<span data-ttu-id="abf6c-112">Der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] im SharePoint-Modus installierte Berichts Server</span><span class="sxs-lookup"><span data-stu-id="abf6c-112">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report server installed in SharePoint Mode</span></span>|<span data-ttu-id="abf6c-113">Der Berichtsserver ist für die Daten- und Berichtsverarbeitung, das Rendern von Berichten sowie für die Verarbeitung von Abonnements und Datenwarnungen zuständig.</span><span class="sxs-lookup"><span data-stu-id="abf6c-113">The report server handles the data and report processing and rendering as well subscription and Data Alert processing.</span></span> <span data-ttu-id="abf6c-114">Der im SharePoint-Modus ausgeführte Berichtsserver ist als gemeinsamer SharePoint-Dienst konzipiert und wird in dieser Form installiert.</span><span class="sxs-lookup"><span data-stu-id="abf6c-114">The SharePoint mode report server is architected and installed as a SharePoint Shared Service.</span></span>|  
  
 <span data-ttu-id="abf6c-115">Verwenden Sie zur Installation von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] die [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]-Installationsmedien.</span><span class="sxs-lookup"><span data-stu-id="abf6c-115">To install [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], use the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] installation media.</span></span>  
  
 <span data-ttu-id="abf6c-116">Anweisungen zu erweiterten Bereitstellungs Szenarien finden Sie unter Bereitstellungs Prüfliste [: Reporting Services, Power View und PowerPivot für SharePoint](../../sql-server/install/deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) -und Bereitstellungs Prüfliste [: Installieren von Reporting Services in einer vorhandenen SharePoint-Farm](../../sql-server/install/deployment-checklist-install-reporting-services-existing-sharepoint-farm.md).</span><span class="sxs-lookup"><span data-stu-id="abf6c-116">For instructions on advanced deployment scenarios, see [Deployment Checklist: Reporting Services, Power View, and PowerPivot for SharePoint](../../sql-server/install/deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) and [Deployment Checklist: Install Reporting Services into an Existing SharePoint Farm](../../sql-server/install/deployment-checklist-install-reporting-services-existing-sharepoint-farm.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="abf6c-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="abf6c-117">In This Section</span></span>  
 [<span data-ttu-id="abf6c-118">Unterstützte Kombinationen von SharePoint-und Reporting Services Server-und Add-in-&#40;SQL Server 2014&#41;</span><span class="sxs-lookup"><span data-stu-id="abf6c-118">Supported Combinations of SharePoint and Reporting Services Server and Add-in &#40;SQL Server 2014&#41;</span></span>](supported-combinations-of-sharepoint-and-reporting-services-server.md)  
  
 [<span data-ttu-id="abf6c-119">Installieren des SharePoint-Modus von Reporting Services für SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="abf6c-119">Install Reporting Services SharePoint Mode for SharePoint 2013</span></span>](../../sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2013.md)  
  
 [<span data-ttu-id="abf6c-120">Installieren Reporting Services SharePoint-Modus für SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="abf6c-120">Install Reporting Services SharePoint Mode for SharePoint 2010</span></span>](../../sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md)  
  
 [<span data-ttu-id="abf6c-121">Installieren oder Deinstallieren des Reporting Services-Add-Ins für SharePoint &#40;SharePoint 2010 und SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="abf6c-121">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
 [<span data-ttu-id="abf6c-122">Verfügbarkeit des Reporting Services-Add-Ins für SharePoint-Produkte</span><span class="sxs-lookup"><span data-stu-id="abf6c-122">Where to find the Reporting Services add-in for SharePoint Products</span></span>](where-to-find-the-reporting-services-add-in-for-sharepoint-products.md)  
  
 [<span data-ttu-id="abf6c-123">Hinzufügen eines zusätzlichen Berichtsservers zu einer Farm &#40;Horizontales Skalieren für SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="abf6c-123">Add an Additional Report Server to a Farm &#40;SSRS Scale-out&#41;</span></span>](add-an-additional-report-server-to-a-farm-ssrs-scale-out.md)  
  
 [<span data-ttu-id="abf6c-124">Hinzufügen eines zusätzlichen Reporting Services-Web-Front-Ends zu einer Farm</span><span class="sxs-lookup"><span data-stu-id="abf6c-124">Add an Additional Reporting Services Web Front-end to a Farm</span></span>](add-an-additional-reporting-services-web-front-end-to-a-farm.md)  
  
 [<span data-ttu-id="abf6c-125">Konfigurieren von E-Mail für eine Reporting Services-Dienstanwendung &#40;SharePoint 2010 und SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="abf6c-125">Configure E-mail for a Reporting Services Service Application &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](configure-e-mail-for-a-reporting-services-service-application.md)  
  
 [<span data-ttu-id="abf6c-126">Bereitstellen von Abonnements und Warnungen für SSRS-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="abf6c-126">Provision Subscriptions and Alerts for SSRS Service Applications</span></span>](provision-subscriptions-and-alerts-for-ssrs-service-applications.md)  
  
 [<span data-ttu-id="abf6c-127">Claims to Windows Token Service &#40;C2WTS&#41; und Reporting Services</span><span class="sxs-lookup"><span data-stu-id="abf6c-127">Claims to Windows Token Service &#40;C2WTS&#41; and Reporting Services</span></span>](../../sql-server/install/claims-to-windows-token-service-c2wts-and-reporting-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="abf6c-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="abf6c-128">See Also</span></span>  
 <span data-ttu-id="abf6c-129">[Architektur und Workflow für Daten Warnungen](../reporting-services-data-alerts.md#AlertingWF) </span><span class="sxs-lookup"><span data-stu-id="abf6c-129">[Data Alerts Architecture and Workflow](../reporting-services-data-alerts.md#AlertingWF) </span></span>  
 [<span data-ttu-id="abf6c-130">Datenwarnungs-Manager für Warnungsadministratoren</span><span class="sxs-lookup"><span data-stu-id="abf6c-130">Data Alert Manager for Alerting Administrators</span></span>](../data-alert-manager-for-alerting-administrators.md)  
  
  
