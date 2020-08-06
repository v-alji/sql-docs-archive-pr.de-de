---
title: MSSQLSERVER_1406 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1406 (Database Engine error)
ms.assetid: 915f97de-9b74-41f8-8bd5-b2d061416718
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: adaa0084b875f720c477189e0e8e085af124f4cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718208"
---
# <a name="mssqlserver_1406"></a><span data-ttu-id="56233-102">MSSQLSERVER_1406</span><span class="sxs-lookup"><span data-stu-id="56233-102">MSSQLSERVER_1406</span></span>
    
## <a name="details"></a><span data-ttu-id="56233-103">Details</span><span class="sxs-lookup"><span data-stu-id="56233-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="56233-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="56233-104">Product Name</span></span>|<span data-ttu-id="56233-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="56233-105">SQL Server</span></span>|  
|<span data-ttu-id="56233-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="56233-106">Event ID</span></span>|<span data-ttu-id="56233-107">1406</span><span class="sxs-lookup"><span data-stu-id="56233-107">1406</span></span>|  
|<span data-ttu-id="56233-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="56233-108">Event Source</span></span>|<span data-ttu-id="56233-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="56233-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="56233-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="56233-110">Component</span></span>|<span data-ttu-id="56233-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="56233-111">SQLEngine</span></span>|  
|<span data-ttu-id="56233-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="56233-112">Symbolic Name</span></span>|<span data-ttu-id="56233-113">DBM_BADSTATEFORFORCESERVICE</span><span class="sxs-lookup"><span data-stu-id="56233-113">DBM_BADSTATEFORFORCESERVICE</span></span>|  
|<span data-ttu-id="56233-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="56233-114">Message Text</span></span>|<span data-ttu-id="56233-115">Der Dienst kann nicht auf sichere Weise erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="56233-115">Unable to force service safely.</span></span> <span data-ttu-id="56233-116">Entfernen Sie die Datenbankspiegelung, und stellen Sie die "%.\*ls"-Datenbank wieder her, um Zugriff zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="56233-116">Remove database mirroring and recover database "%.\*ls" to gain access.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="56233-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="56233-117">Explanation</span></span>  
 <span data-ttu-id="56233-118">Der Dienst kann von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] nicht erzwungen werden, da mit dem Spiegelungsstatus nicht garantiert werden kann, dass der erzwungene Dienstvorgang ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="56233-118">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] cannot force service because the mirroring state cannot guarantee that the force service process would work correctly.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="56233-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="56233-119">User Action</span></span>  
 <span data-ttu-id="56233-120">Entfernen Sie die Datenbankspiegelung.</span><span class="sxs-lookup"><span data-stu-id="56233-120">Remove database mirroring.</span></span> <span data-ttu-id="56233-121">Sie können anschließend die Spiegeldatenbank wiederherstellen, um Zugriff zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="56233-121">You can then recover the mirror database to gain access to it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56233-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56233-122">See Also</span></span>  
 <span data-ttu-id="56233-123">[Erzwingen des Diensts in einer Datenbank-Spiegelungssitzung (Transact-SQL)](../../database-engine/database-mirroring/force-service-in-a-database-mirroring-session-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="56233-123">[Force Service in a Database Mirroring Session &#40;Transact-SQL&#41;](../../database-engine/database-mirroring/force-service-in-a-database-mirroring-session-transact-sql.md) </span></span>  
 [<span data-ttu-id="56233-124">Entfernen der Datenbankspiegelung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="56233-124">Removing Database Mirroring &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/database-mirroring-sql-server.md)  
  
  
