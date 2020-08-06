---
title: Veraltete Master Data Services Features in SQL Server 2014 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: d8506bda-66dd-45a4-bfc9-3a10fa665acc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce532e9f407ec475f7e59c0d79659265a9e0bf3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695769"
---
# <a name="deprecated-master-data-services-features-in-sql-server-2014"></a><span data-ttu-id="5bdf8-102">Veraltete Master Data Services-Funktionen in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="5bdf8-102">Deprecated Master Data Services Features in SQL Server 2014</span></span>
  <span data-ttu-id="5bdf8-103">In diesem Thema werden die als veraltet markierten Funktionen von [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] beschrieben, die in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]noch verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5bdf8-103">This topic describes the deprecated [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] features that are still available in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="5bdf8-104">Diese Funktionen werden voraussichtlich in einer zukünftigen Version von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]entfernt.</span><span class="sxs-lookup"><span data-stu-id="5bdf8-104">These features are scheduled to be removed in a future release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5bdf8-105">Als veraltet markierte Funktionen sollten in neuen Anwendungen nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5bdf8-105">Deprecated features should not be used in new applications.</span></span>  
  
## <a name="staging-process"></a><span data-ttu-id="5bdf8-106">Stagingprozess</span><span class="sxs-lookup"><span data-stu-id="5bdf8-106">Staging Process</span></span>  
 <span data-ttu-id="5bdf8-107">Der Stagingprozess, der in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] verwendet wurde, ist nicht mehr in der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Webanwendung verfügbar; er ist jedoch immer noch in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5bdf8-107">The staging process that was used in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] is no longer available in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application; however it is still available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="5bdf8-108">Stagingfehler aus dem [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] -Stagingprozess werden nicht mehr in der Benutzeroberfläche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5bdf8-108">Staging errors from the [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] staging process are no longer displayed in the UI.</span></span> <span data-ttu-id="5bdf8-109">Fehlercodes, die während des Stagingprozesses aufgefüllt werden, sind in den Stagingtabellen weiterhin verfügbar. Sie finden Sie hier: [https://msdn.microsoft.com/library/ff487022.aspx](https://msdn.microsoft.com/library/ff487022.aspx) .</span><span class="sxs-lookup"><span data-stu-id="5bdf8-109">Error codes that are populated during the staging process are still available in the staging tables, and can be found here: [https://msdn.microsoft.com/library/ff487022.aspx](https://msdn.microsoft.com/library/ff487022.aspx).</span></span>  
  
 <span data-ttu-id="5bdf8-110">Die Stagingtabellen (tblStgMember, tblStgMemberAttribute und tblStgRelationship) sind nach wie vor in der Datenbank verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5bdf8-110">The staging tables (tblStgMember, tblStgMemberAttribute, and tblStgRelationship) are still available in the database.</span></span> <span data-ttu-id="5bdf8-111">Die gespeicherte Prozedur, die verwendet wurde, um den Stagingprozess (mdm.udpStagingSweep) zu initiieren, ist nach wie vor in der Datenbank verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5bdf8-111">The stored procedure used to initiate the staging process (mdm.udpStagingSweep) is still available in the database.</span></span>  
  
 <span data-ttu-id="5bdf8-112">Die Webdienstmethoden, die den Stagingprozess aufrufen, sind immer noch verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5bdf8-112">The web service methods that call the staging process are still available.</span></span>  
  
 <span data-ttu-id="5bdf8-113">Das in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] festgelegte Stagingintervall gilt für den Stagingprozess sowohl in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] als auch in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5bdf8-113">The staging interval set in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] applies to the staging process in both [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] and [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="5bdf8-114">Ein neuer, leistungsstärkerer Stagingprozess wurde in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]implementiert.</span><span class="sxs-lookup"><span data-stu-id="5bdf8-114">A new, higher performance staging process has been implemented in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="5bdf8-115">Weitere Informationen finden Sie unter [Datenimport &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5bdf8-115">For more information, see [Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span></span>  
  
## <a name="metadata"></a><span data-ttu-id="5bdf8-116">Metadaten</span><span class="sxs-lookup"><span data-stu-id="5bdf8-116">Metadata</span></span>  
 <span data-ttu-id="5bdf8-117">Obwohl das Metadatenmodell immer noch in der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Webanwendung angezeigt wird, sollte es nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5bdf8-117">Though the Metadata model is still displayed in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application, it should not be used.</span></span> <span data-ttu-id="5bdf8-118">Dieses Element wird in einer späteren Version entfernt.</span><span class="sxs-lookup"><span data-stu-id="5bdf8-118">It will be removed in a future release.</span></span> <span data-ttu-id="5bdf8-119">Benutzer können zudem keine Metadaten mehr im Funktionsbereich **Explorer** anzeigen, und Sie können keine Versionen des Metadatenmodells mehr erstellen.</span><span class="sxs-lookup"><span data-stu-id="5bdf8-119">Users can also no longer view metadata in the **Explorer** functional area, and you can no longer create versions of the Metadata model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bdf8-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5bdf8-120">See Also</span></span>  
 [<span data-ttu-id="5bdf8-121">Eingestellte Master Data Services-Funktionen in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="5bdf8-121">Discontinued Master Data Services Features in SQL Server 2014</span></span>](discontinued-master-data-services-features.md)  
  
  
