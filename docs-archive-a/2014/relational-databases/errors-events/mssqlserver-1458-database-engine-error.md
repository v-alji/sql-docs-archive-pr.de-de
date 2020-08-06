---
title: MSSQLSERVER_1458 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1458 (Database Engine error)
ms.assetid: adc78c59-a6f2-432b-9a07-fdd1dc2b9026
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: efa45177a92402b25099be5bb3e3dcc91a5fa6d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620951"
---
# <a name="mssqlserver_1458"></a><span data-ttu-id="6c881-102">MSSQLSERVER_1458</span><span class="sxs-lookup"><span data-stu-id="6c881-102">MSSQLSERVER_1458</span></span>
    
## <a name="details"></a><span data-ttu-id="6c881-103">Details</span><span class="sxs-lookup"><span data-stu-id="6c881-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6c881-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="6c881-104">Product Name</span></span>|<span data-ttu-id="6c881-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6c881-105">SQL Server</span></span>|  
|<span data-ttu-id="6c881-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="6c881-106">Event ID</span></span>|<span data-ttu-id="6c881-107">1458</span><span class="sxs-lookup"><span data-stu-id="6c881-107">1458</span></span>|  
|<span data-ttu-id="6c881-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="6c881-108">Event Source</span></span>|<span data-ttu-id="6c881-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6c881-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6c881-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="6c881-110">Component</span></span>|<span data-ttu-id="6c881-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6c881-111">SQLEngine</span></span>|  
|<span data-ttu-id="6c881-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="6c881-112">Symbolic Name</span></span>|<span data-ttu-id="6c881-113">DBM_FAILREDO_ON_PRIMARY</span><span class="sxs-lookup"><span data-stu-id="6c881-113">DBM_FAILREDO_ON_PRIMARY</span></span>|  
|<span data-ttu-id="6c881-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="6c881-114">Message Text</span></span>|<span data-ttu-id="6c881-115">Bei der Prinzipalkopie der %.\*ls-Datenbank ist der Fehler %d, Status %d, Schweregrad %d, aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="6c881-115">The principal copy of the '%.\*ls' database encountered error %d, status %d, severity %d.</span></span> <span data-ttu-id="6c881-116">Die Datenbankspiegelung wurde angehalten.</span><span class="sxs-lookup"><span data-stu-id="6c881-116">Database mirroring has been suspended.</span></span> <span data-ttu-id="6c881-117">Beheben Sie den Fehler, und setzen Sie die Spiegelung fort.</span><span class="sxs-lookup"><span data-stu-id="6c881-117">Try to resolve the error condition, and resume mirroring.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6c881-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="6c881-118">Explanation</span></span>  
 <span data-ttu-id="6c881-119">In dieser Meldung wird angegeben, dass in der Prinzipaldatenbank ein Fehler aufgetreten ist, durch den die Datenbankspiegelung angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="6c881-119">This messages indicates that the principal database encountered an error that caused database mirroring to be suspended.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6c881-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="6c881-120">User Action</span></span>  
 <span data-ttu-id="6c881-121">Dieser Fehler wird in den meisten Fällen automatisch behoben.</span><span class="sxs-lookup"><span data-stu-id="6c881-121">Most cases of this error are self correcting.</span></span> <span data-ttu-id="6c881-122">Wenn das Problem weiterhin besteht, kann das Problem normalerweise durch einen Neustart der Datenbank- oder Serverinstanz behoben werden.</span><span class="sxs-lookup"><span data-stu-id="6c881-122">If the problem persists, restarting the database or server instance typically corrects the problem.</span></span> <span data-ttu-id="6c881-123">Weitere Informationen finden Sie im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll auf jedem Partner für den zugeordneten Fehler, der dieser Meldung vorausging.</span><span class="sxs-lookup"><span data-stu-id="6c881-123">For more information, look in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log on each partner for the associated error that preceded this message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c881-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6c881-124">See Also</span></span>  
 [<span data-ttu-id="6c881-125">Überwachen der Datenbankspiegelung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6c881-125">Monitoring Database Mirroring &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/database-mirroring-sql-server.md)  
  
  
