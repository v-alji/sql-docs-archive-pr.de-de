---
title: PowerPivot für SharePoint 2010-Installation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 8d47dde7-c941-4280-a934-e2fe3f9a938f
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: ba04dfdc69b1c510a800c062586e45f8873c8e8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620715"
---
# <a name="powerpivot-for-sharepoint-2010-installation"></a><span data-ttu-id="e94d9-102">PowerPivot for SharePoint 2010 Installation</span><span class="sxs-lookup"><span data-stu-id="e94d9-102">PowerPivot for SharePoint 2010 Installation</span></span>
  [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)] <span data-ttu-id="e94d9-103">ist eine Sammlung von Serverkomponenten, mit denen die Abfrageverarbeitung und Verwaltung der in SharePoint veröffentlichten [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)]-Arbeitsmappen gesteuert werden kann.</span><span class="sxs-lookup"><span data-stu-id="e94d9-103">is a collection of server components that provide query processing and management control over [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbooks that you publish to SharePoint.</span></span> <span data-ttu-id="e94d9-104">Die Dienste umfassen die Analysis Services-Engine und den [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] -Systemdienst.</span><span class="sxs-lookup"><span data-stu-id="e94d9-104">Services include the Analysis Services engine and [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] System Service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e94d9-105">Informationen zu [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)] und der Installation mit SharePoint Server 2013 finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="e94d9-105">For information regarding [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)] and installation with SharePoint Server 2013, see the following:</span></span>  
>   
>  -   <span data-ttu-id="e94d9-106">Der Abschnitt "SQL Server 2012 SP1" von [Übersicht über SQL Server Wartungs Installation](../../../2014/sql-server/install/overview-of-sql-server-servicing-installation.md).</span><span class="sxs-lookup"><span data-stu-id="e94d9-106">The "SQL Server 2012 SP1" section of [Overview of SQL Server Servicing Installation](../../../2014/sql-server/install/overview-of-sql-server-servicing-installation.md).</span></span>  
  
 <span data-ttu-id="e94d9-107">Analysis Services unterstützen die serverseitige Verarbeitung von Excel-Arbeitsmappen, die [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] -Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="e94d9-107">Analysis Services provides server-side processing for Excel workbooks that contain [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] data.</span></span> <span data-ttu-id="e94d9-108">Der [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)]-Systemdienst wird zusammen mit Analysis Services verwendet und erweitert den Funktionsumfang um SharePoint-Integration, Lastausgleich und Verbindungsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="e94d9-108">[!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] System Service works alongside Analysis Services, adding SharePoint integration, load balancing and connection management.</span></span> [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)]<span data-ttu-id="e94d9-109">erweitert Excel Services, indem seine umfangreiche Datenverarbeitungs Funktion mit den von Excel bereitgestellten datenrenderingdiensten gekoppelt wird.</span><span class="sxs-lookup"><span data-stu-id="e94d9-109">extends Excel Services by pairing its large scale data processing capability with the data rendering services that Excel provides.</span></span>  
  
 <span data-ttu-id="e94d9-110">Installieren Sie [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)]mit den Installationsmedien von [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e94d9-110">To install [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)], use the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]installation media.</span></span>  
  
 <span data-ttu-id="e94d9-111">Anweisungen zu erweiterten Bereitstellungs Szenarien finden Sie unter Bereitstellungs Prüfliste [: Reporting Services, Power View und PowerPivot für SharePoint](deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) und Bereitstellungs Prüfliste: horizontales [skalieren durch Hinzufügen von Power Pivot-Servern zu einer SharePoint 2010-Farm](../../../2014/sql-server/install/deployment-checklist-scale-out-adding-powerpivot-servers-sharepoint-2010-farm.md).</span><span class="sxs-lookup"><span data-stu-id="e94d9-111">For instructions on advanced deployment scenarios, see [Deployment Checklist: Reporting Services, Power View, and PowerPivot for SharePoint](deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) and [Deployment Checklist: Scale-out by adding PowerPivot Servers to a SharePoint 2010 farm](../../../2014/sql-server/install/deployment-checklist-scale-out-adding-powerpivot-servers-sharepoint-2010-farm.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e94d9-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e94d9-112">In This Section</span></span>  
 [<span data-ttu-id="e94d9-113">Installieren von PowerPivot für SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="e94d9-113">Install PowerPivot for SharePoint 2010</span></span>](../../../2014/sql-server/install/install-powerpivot-for-sharepoint-2010.md)  
  
 [<span data-ttu-id="e94d9-114">Installieren des Analysis Services OLE DB-Anbieters auf SharePoint-Servern</span><span class="sxs-lookup"><span data-stu-id="e94d9-114">Install the Analysis Services OLE DB Provider on SharePoint Servers</span></span>](../../../2014/sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md)  
  
 [<span data-ttu-id="e94d9-115">Installieren von ADOMD.NET auf Web-Front-End-Servern, auf denen die Zentraladministration ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="e94d9-115">Install ADOMD.NET on Web Front-End Servers Running Central Administration</span></span>](../../../2014/sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md)  
  
 [<span data-ttu-id="e94d9-116">Installieren von ADO.NET Data Services, um Datenfeedexporte von SharePoint-Listen zu unterstützen</span><span class="sxs-lookup"><span data-stu-id="e94d9-116">Install ADO.NET Data Services to support data feed exports of SharePoint lists</span></span>](../../../2014/sql-server/install/install-ado-net-data-services-to-support-data-feed-exports-of-sharepoint-lists.md)  
  
 [<span data-ttu-id="e94d9-117">Installieren von PowerPivot über die Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="e94d9-117">Install PowerPivot from the Command Prompt</span></span>](../../../2014/sql-server/install/install-powerpivot-from-the-command-prompt.md)  
  
 [<span data-ttu-id="e94d9-118">Deinstallieren von PowerPivot für SharePoint</span><span class="sxs-lookup"><span data-stu-id="e94d9-118">Uninstall PowerPivot for SharePoint</span></span>](../../../2014/sql-server/install/uninstall-power-pivot-for-sharepoint.md)  
  
 [<span data-ttu-id="e94d9-119">Reparieren von PowerPivot für SharePoint</span><span class="sxs-lookup"><span data-stu-id="e94d9-119">Repair PowerPivot for SharePoint</span></span>](../../../2014/sql-server/install/repair-powerpivot-for-sharepoint.md)  
  
 [<span data-ttu-id="e94d9-120">Anfängliche Konfiguration &#40;PowerPivot für SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="e94d9-120">Initial Configuration &#40;PowerPivot for SharePoint&#41;</span></span>](../../../2014/sql-server/install/initial-configuration-powerpivot-for-sharepoint.md)  
  
## <a name="see-also"></a><span data-ttu-id="e94d9-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e94d9-121">See Also</span></span>  
 [<span data-ttu-id="e94d9-122">PowerPivot-Serververwaltung und -konfiguration in der Zentraladministration</span><span class="sxs-lookup"><span data-stu-id="e94d9-122">PowerPivot Server Administration and Configuration in Central Administration</span></span>](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-server-administration-and-configuration-in-central-administration)  
  
  
