---
title: MSSQLSERVER_1401 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1401 (Database Engine error)
ms.assetid: 02928770-aa63-4509-8713-406c73e4cedc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 720263939e2f1685649fc41896e8ea10907d92ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620962"
---
# <a name="mssqlserver_1401"></a><span data-ttu-id="e5bc3-102">MSSQLSERVER_1401</span><span class="sxs-lookup"><span data-stu-id="e5bc3-102">MSSQLSERVER_1401</span></span>
    
## <a name="details"></a><span data-ttu-id="e5bc3-103">Details</span><span class="sxs-lookup"><span data-stu-id="e5bc3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e5bc3-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="e5bc3-104">Product Name</span></span>|<span data-ttu-id="e5bc3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e5bc3-105">SQL Server</span></span>|  
|<span data-ttu-id="e5bc3-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e5bc3-106">Event ID</span></span>|<span data-ttu-id="e5bc3-107">1401</span><span class="sxs-lookup"><span data-stu-id="e5bc3-107">1401</span></span>|  
|<span data-ttu-id="e5bc3-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="e5bc3-108">Event Source</span></span>|<span data-ttu-id="e5bc3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e5bc3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e5bc3-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="e5bc3-110">Component</span></span>|<span data-ttu-id="e5bc3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e5bc3-111">SQLEngine</span></span>|  
|<span data-ttu-id="e5bc3-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="e5bc3-112">Symbolic Name</span></span>|<span data-ttu-id="e5bc3-113">DBM_MASTERSTARTUP</span><span class="sxs-lookup"><span data-stu-id="e5bc3-113">DBM_MASTERSTARTUP</span></span>|  
|<span data-ttu-id="e5bc3-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="e5bc3-114">Message Text</span></span>|<span data-ttu-id="e5bc3-115">Fehler beim Starten der Masterthreadroutine für die Datenbankspiegelung mit folgender Ursache: %ls.</span><span class="sxs-lookup"><span data-stu-id="e5bc3-115">Startup of the database-mirroring master thread routine failed for the following reason: %ls.</span></span> <span data-ttu-id="e5bc3-116">Beheben Sie die Fehlerursache, und starten Sie den SQL Server-Dienst erneut.</span><span class="sxs-lookup"><span data-stu-id="e5bc3-116">Correct the cause of this error, and restart the SQL Server service.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e5bc3-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="e5bc3-117">Explanation</span></span>  
 <span data-ttu-id="e5bc3-118">Beim Starten des Spiegelungssteuerungsthreads ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e5bc3-118">Startup of the mirroring control thread failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e5bc3-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="e5bc3-119">User Action</span></span>  
 <span data-ttu-id="e5bc3-120">Suchen Sie im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll nach dem entsprechenden Fehler, der vor dieser Meldung angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="e5bc3-120">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, look for the associated error that preceded this message.</span></span> <span data-ttu-id="e5bc3-121">Beheben Sie die Fehlerursache, und starten Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienst (MSSQLSERVER) anschließend erneut.</span><span class="sxs-lookup"><span data-stu-id="e5bc3-121">Correct the cause of this error, and then restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service (MSSQLSERVER).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5bc3-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e5bc3-122">See Also</span></span>  
 [<span data-ttu-id="e5bc3-123">Starten, Beenden, Anhalten, Fortsetzen und Neustarten der Datenbank-Engine, SQL Server-Agent oder des SQL Server-Browsers</span><span class="sxs-lookup"><span data-stu-id="e5bc3-123">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)  
  
  
