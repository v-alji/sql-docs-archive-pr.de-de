---
title: Anzeigen von Fehlern, die während des Stagingprozesses auftreten (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- staging process [Master Data Services], viewing errors
ms.assetid: 6d2bff84-624b-47fc-a4a5-d9ea01d13412
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3b39d039b29090f3021c764126ebb782ce25cbfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699878"
---
# <a name="view-errors-that-occur-during-the-staging-process-master-data-services"></a><span data-ttu-id="ce135-102">Anzeigen von Fehlern, die während des Stagingprozesses auftreten (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ce135-102">View Errors that Occur During the Staging Process (Master Data Services)</span></span>
  <span data-ttu-id="ce135-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]können Sie Fehler anzeigen, die während des Stagingprozesses auftreten.</span><span class="sxs-lookup"><span data-stu-id="ce135-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can view errors that occur during the staging process.</span></span> <span data-ttu-id="ce135-104">In der Datenbank [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] gibt es zwei Sichten, die Fehler anzeigen:</span><span class="sxs-lookup"><span data-stu-id="ce135-104">In the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database, there are two views that show errors:</span></span>  
  
-   <span data-ttu-id="ce135-105">stg.viw_name_MemberErrorDetails für Blatt- oder konsolidierte Elementupdates.</span><span class="sxs-lookup"><span data-stu-id="ce135-105">stg.viw_name_MemberErrorDetails for leaf or consolidated member updates.</span></span>  
  
-   <span data-ttu-id="ce135-106">stg.viw_name_RelationshipErrorDetails für Hierarchiebeziehungsupdates.</span><span class="sxs-lookup"><span data-stu-id="ce135-106">stg.viw_name_RelationshipErrorDetails for hierarchy relationship updates.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ce135-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ce135-107">Prerequisites</span></span>  
 <span data-ttu-id="ce135-108">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="ce135-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="ce135-109">In der Datenbank [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] müssen Sie entweder für stg.viw_name_MemberErrorDetails oder stg.viw_name_RelationshipErrorDetails über SELECT-Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="ce135-109">In the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database, you must have SELECT permissions to either the stg.viw_name_MemberErrorDetails or stg.viw_name_RelationshipErrorDetails view.</span></span>  
  
-   <span data-ttu-id="ce135-110">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="ce135-110">You must be a model administrator.</span></span> <span data-ttu-id="ce135-111">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ce135-111">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-view-staging-errors"></a><span data-ttu-id="ce135-112">So zeigen Sie bereitstellende Fehler an</span><span class="sxs-lookup"><span data-stu-id="ce135-112">To view staging errors</span></span>  
  
1.  <span data-ttu-id="ce135-113">Öffnen Sie [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , und stellen Sie eine Verbindung mit der [!INCLUDE[ssDE](../includes/ssde-md.md)] -Instanz für die [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Datenbank her.</span><span class="sxs-lookup"><span data-stu-id="ce135-113">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="ce135-114">Öffnen Sie eine neue Abfrage.</span><span class="sxs-lookup"><span data-stu-id="ce135-114">Open a new query.</span></span>  
  
3.  <span data-ttu-id="ce135-115">Geben Sie den folgenden Text ein, und ersetzen Sie den Namen durch den Namen der Stagingtabelle, z. B. viw_Product_MemberErrorDetails.</span><span class="sxs-lookup"><span data-stu-id="ce135-115">Type the following text, replacing name with the name of your staging table, for example, viw_Product_MemberErrorDetails.</span></span>  
  
     `SELECT * FROM stg.viw_name_MemberErrorDetails`  
  
4.  <span data-ttu-id="ce135-116">Führen Sie die Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="ce135-116">Excecute the query.</span></span> <span data-ttu-id="ce135-117">Fehlerdetails werden im **ErrorDescription** -Feld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ce135-117">Error details are displayed in the **ErrorDescription** field.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ce135-118">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ce135-118">Next Steps</span></span>  
 <span data-ttu-id="ce135-119">Weitere Informationen zu Fehlermeldungen finden Sie unter [Fehler des Stagingprozesses &#40;Master Data Services&#41;](../../2014/master-data-services/staging-process-errors-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ce135-119">For more details on error messages, see [Staging Process Errors &#40;Master Data Services&#41;](../../2014/master-data-services/staging-process-errors-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce135-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ce135-120">See Also</span></span>  
 <span data-ttu-id="ce135-121">[Daten Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ce135-121">[Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md) </span></span>  
 [<span data-ttu-id="ce135-122">Problembehandlung des Stagingprozesses (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ce135-122">Troubleshooting the Staging Process (Master Data Services)</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-the-staging-process-master-data-services.aspx)  
  
  
