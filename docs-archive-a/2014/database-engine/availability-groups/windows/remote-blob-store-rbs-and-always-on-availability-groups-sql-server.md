---
title: Remote BLOB Store (RBS) und AlwaysOn-Verfügbarkeitsgruppen (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 01a70258-d4fd-40bc-bc44-c490b5d6c420
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f12a11162d286731b2b510a9051183e6c3025b2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615607"
---
# <a name="remote-blob-store-rbs-and-alwayson-availability-groups-sql-server"></a><span data-ttu-id="52e30-102">Remote Blob Store (RBS) und AlwaysOn-Verfügbarkeitsgruppen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="52e30-102">Remote Blob Store (RBS) and AlwaysOn Availability Groups (SQL Server)</span></span>
  [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]<span data-ttu-id="52e30-103">kann eine Lösung für hohe Verfügbarkeit und Notfall Wiederherstellung für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [Remote BLOB-Speicher (RBS)](../../../relational-databases/blob/remote-blob-store-rbs-sql-server.md) -BLOB-Objekte (BLOBs) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="52e30-103">can provide a high-availability and disaster recovery solution for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)][Remote Blob Store (RBS)](../../../relational-databases/blob/remote-blob-store-rbs-sql-server.md) BLOB objects (blobs).</span></span> [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] <span data-ttu-id="52e30-104">schützt alle in einer Verfügbarkeitsdatenbank gespeicherten RBS-Metadaten und -Schemas, indem sie an die sekundären Replikate repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="52e30-104">protects any RBS metadata and schemas stored in an availability database by replicating them to the secondary replicas.</span></span> <span data-ttu-id="52e30-105">Dabei handelt es sich um die SharePoint-Inhaltsdatenbank.</span><span class="sxs-lookup"><span data-stu-id="52e30-105">This is the SharePoint Content Database.</span></span> <span data-ttu-id="52e30-106">Im Allgemeinen speichert [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] diese RBS-Metadaten unabhängig vom BLOB.</span><span class="sxs-lookup"><span data-stu-id="52e30-106">Generally speaking, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stores this RBS metadata independently from the blob.</span></span>  
  
 <span data-ttu-id="52e30-107">Der Schutz der RBD-BLOB-Daten hängt vom Speicherort des BLOB-Speichers ab:</span><span class="sxs-lookup"><span data-stu-id="52e30-107">The protection for RBD BLOB data depends on the BLOB Store Location, as follows:</span></span>  
  
|<span data-ttu-id="52e30-108">Speicherort des BLOB-Speichers</span><span class="sxs-lookup"><span data-stu-id="52e30-108">BLOB Store Location</span></span>|<span data-ttu-id="52e30-109">Können diese BLOB-Daten von Verfügbarkeitsgruppen geschützt werden?</span><span class="sxs-lookup"><span data-stu-id="52e30-109">Can Availability Groups Protect This BLOB Data?</span></span>|  
|-------------------------|-----------------------------------------------------|  
|<span data-ttu-id="52e30-110">Dieselbe Datenbank, in der die (mithilfe eines RBS-FILESTREAM-Anbieters gespeicherten) RBS-Metadaten enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="52e30-110">The same database that contains the RBS metadata  (stored using a RBS remote FILESTREAM provider)</span></span>|<span data-ttu-id="52e30-111">Ja</span><span class="sxs-lookup"><span data-stu-id="52e30-111">Yes</span></span>|  
|<span data-ttu-id="52e30-112">Eine andere Datenbank in derselben Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (die mithilfe eines RBS-FILESTREAM-Anbieters gespeichert wurde)</span><span class="sxs-lookup"><span data-stu-id="52e30-112">Another database in the same instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (stored using a RBS remote FILESTREAM provider)</span></span>|<span data-ttu-id="52e30-113">Ja</span><span class="sxs-lookup"><span data-stu-id="52e30-113">Yes</span></span><br /><br /> <span data-ttu-id="52e30-114">Es empfiehlt sich, diese Datenbank in derselben Verfügbarkeitsgruppe anzulegen wie die Datenbank, in der die RBS-Metadaten enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="52e30-114">We recommend that you put this database in the same availability group as the database that contains the RBS metadata.</span></span>|  
|<span data-ttu-id="52e30-115">Eine andere Datenbank in einer anderen Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (die mithilfe eines RBS-FILESTREAM-Anbieters gespeichert wurde)</span><span class="sxs-lookup"><span data-stu-id="52e30-115">Another database in a different instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (stored using a RBS remote FILESTREAM provider)</span></span>|<span data-ttu-id="52e30-116">Ja</span><span class="sxs-lookup"><span data-stu-id="52e30-116">Yes</span></span><br /><br /> <span data-ttu-id="52e30-117">Diese Datenbank muss in einer separaten Verfügbarkeitsgruppe enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="52e30-117">This database must be in a separate availability group.</span></span>|  
|<span data-ttu-id="52e30-118">Ein BLOB-Speicher eines Drittanbieters</span><span class="sxs-lookup"><span data-stu-id="52e30-118">A third-party BLOB store</span></span>|<span data-ttu-id="52e30-119">Nein</span><span class="sxs-lookup"><span data-stu-id="52e30-119">No</span></span><br /><br /> <span data-ttu-id="52e30-120">Um diese BLOB-Daten zu schützen, verwenden Sie die Hochverfügbarkeitsmechanismen des BLOB-Speicheranbieters.</span><span class="sxs-lookup"><span data-stu-id="52e30-120">To protect this BLOB data, use the high-availability mechanisms of the BLOB store provider.</span></span>|  
  
##  <a name="limitations"></a><a name="Limitations"></a> <span data-ttu-id="52e30-121">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="52e30-121">Limitations</span></span>  
  
-   <span data-ttu-id="52e30-122">Für RBS-Maintainer muss das primäre Replikat als Ziel angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="52e30-122">RBS maintainers need to be targeted on the primary replica.</span></span>  
  
##  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="52e30-123">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="52e30-123">Recommendations</span></span>  
  
-   <span data-ttu-id="52e30-124">Verwenden Sie einen Verfügbarkeitsgruppenlistener.</span><span class="sxs-lookup"><span data-stu-id="52e30-124">Use an availability group listener.</span></span> <span data-ttu-id="52e30-125">Weitere Informationen finden Sie unter [Verfügbarkeitsgruppenlistener, Clientkonnektivität und Anwendungsfailover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md)wichtig sind.</span><span class="sxs-lookup"><span data-stu-id="52e30-125">For more information, see [Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span></span>  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="52e30-126">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="52e30-126">Related Content</span></span>  
  
-   <span data-ttu-id="52e30-127">[Wartung von Remote BLOB-Speicher](https://msdn.microsoft.com/library/gg316773\(SQL.105\).aspx) (in der [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] -Onlinedokumentation)</span><span class="sxs-lookup"><span data-stu-id="52e30-127">[Maintaining Remote BLOB Store](https://msdn.microsoft.com/library/gg316773\(SQL.105\).aspx) (in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] Books Online)</span></span>  
  
-   <span data-ttu-id="52e30-128">[Ausführen des RBS-Maintainers](https://blogs.msdn.com/b/sqlrbs/archive/2010/03/19/running-rbs-maintainer.aspx) (Blog)</span><span class="sxs-lookup"><span data-stu-id="52e30-128">[Running RBS Maintainer](https://blogs.msdn.com/b/sqlrbs/archive/2010/03/19/running-rbs-maintainer.aspx) (blog)</span></span>  
  
-   <span data-ttu-id="52e30-129">[Konfigurieren von Remote BLOB Storage (RBS) mit dem FILESTREAM-Anbieter (SharePoint 2010)](https://blogs.msdn.com/b/mvpawardprogram/archive/2012/04/02/configure-remote-blob-storage-rbs-with-the-filestream-provider-sharepoint-2010.aspx) (Blog)</span><span class="sxs-lookup"><span data-stu-id="52e30-129">[Configure Remote BLOB Storage (RBS) with the FILESTREAM provider (SharePoint 2010)](https://blogs.msdn.com/b/mvpawardprogram/archive/2012/04/02/configure-remote-blob-storage-rbs-with-the-filestream-provider-sharepoint-2010.aspx) (blog)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52e30-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52e30-130">See Also</span></span>  
 <span data-ttu-id="52e30-131">[AlwaysOn-Client Konnektivität &#40;SQL Server&#41;](always-on-client-connectivity-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="52e30-131">[AlwaysOn Client Connectivity &#40;SQL Server&#41;](always-on-client-connectivity-sql-server.md) </span></span>  
 [<span data-ttu-id="52e30-132">Remote Blob Store &#40;RBS&#41; &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="52e30-132">Remote Blob Store &#40;RBS&#41; &#40;SQL Server&#41;</span></span>](../../../relational-databases/blob/remote-blob-store-rbs-sql-server.md)  
  
  
