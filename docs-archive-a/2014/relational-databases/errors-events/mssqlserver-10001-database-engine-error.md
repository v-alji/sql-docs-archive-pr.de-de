---
title: MSSQLSERVER_10001 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10001 (Database Engine error)
ms.assetid: f8fd2d8d-a4af-4b6a-ba51-9123b7e4c9bf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0542f6d52a4fd194c4b0ae5d1aad501f5e3b8c2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719963"
---
# <a name="mssqlserver_10001"></a><span data-ttu-id="d64dd-102">MSSQLSERVER_10001</span><span class="sxs-lookup"><span data-stu-id="d64dd-102">MSSQLSERVER_10001</span></span>
    
## <a name="details"></a><span data-ttu-id="d64dd-103">Details</span><span class="sxs-lookup"><span data-stu-id="d64dd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d64dd-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="d64dd-104">Product Name</span></span>|<span data-ttu-id="d64dd-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d64dd-105">SQL Server</span></span>|  
|<span data-ttu-id="d64dd-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="d64dd-106">Event ID</span></span>|<span data-ttu-id="d64dd-107">10001</span><span class="sxs-lookup"><span data-stu-id="d64dd-107">10001</span></span>|  
|<span data-ttu-id="d64dd-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="d64dd-108">Event Source</span></span>|<span data-ttu-id="d64dd-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d64dd-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d64dd-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="d64dd-110">Component</span></span>|<span data-ttu-id="d64dd-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d64dd-111">SQLEngine</span></span>|  
|<span data-ttu-id="d64dd-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="d64dd-112">Symbolic Name</span></span>|<span data-ttu-id="d64dd-113">HR_E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="d64dd-113">HR_E_UNEXPECTED</span></span>|  
|<span data-ttu-id="d64dd-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="d64dd-114">Message Text</span></span>|<span data-ttu-id="d64dd-115">Der Anbieter hat einen unerwarteten schwerwiegenden Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="d64dd-115">The provider reported an unexpected catastrophic failure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d64dd-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="d64dd-116">Explanation</span></span>  
 <span data-ttu-id="d64dd-117">Bei der Verarbeitung von verteilten Abfragen ist ein generischer Fehler beim Aufrufen des OLE DB-Anbieters aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d64dd-117">Distributed query processing encountered a generic error while calling into the OLE DB provider.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d64dd-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="d64dd-118">User Action</span></span>  
 <span data-ttu-id="d64dd-119">Listen Sie OLE DB-Ablaufverfolgungsereignisse mit [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] auf, und stellen Sie diese Daten für den Produktsupport des OLE DB-Anbieters bereit.</span><span class="sxs-lookup"><span data-stu-id="d64dd-119">Collect OLE DB trace events using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] and  provide this data to product support for the OLE DB provider.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d64dd-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d64dd-120">See Also</span></span>  
 <span data-ttu-id="d64dd-121">[Vorlagen und Berechtigungen in SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="d64dd-121">[SQL Server Profiler Templates and Permissions](../../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="d64dd-122">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="d64dd-122">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
