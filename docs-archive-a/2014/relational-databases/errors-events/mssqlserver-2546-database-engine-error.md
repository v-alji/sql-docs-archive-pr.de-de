---
title: MSSQLSERVER_2546 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2546 (Database Engine error)
ms.assetid: c8f0e1b4-c7c4-45f2-9221-746714172313
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5c1c5f64ca0daba413f2b71c05f5b8e57b2d55df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696873"
---
# <a name="mssqlserver_2546"></a><span data-ttu-id="2fbad-102">MSSQLSERVER_2546</span><span class="sxs-lookup"><span data-stu-id="2fbad-102">MSSQLSERVER_2546</span></span>
    
## <a name="details"></a><span data-ttu-id="2fbad-103">Details</span><span class="sxs-lookup"><span data-stu-id="2fbad-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2fbad-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="2fbad-104">Product Name</span></span>|<span data-ttu-id="2fbad-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2fbad-105">SQL Server</span></span>|  
|<span data-ttu-id="2fbad-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2fbad-106">Event ID</span></span>|<span data-ttu-id="2fbad-107">2546</span><span class="sxs-lookup"><span data-stu-id="2fbad-107">2546</span></span>|  
|<span data-ttu-id="2fbad-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="2fbad-108">Event Source</span></span>|<span data-ttu-id="2fbad-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2fbad-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2fbad-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="2fbad-110">Component</span></span>|<span data-ttu-id="2fbad-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2fbad-111">SQLEngine</span></span>|  
|<span data-ttu-id="2fbad-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="2fbad-112">Symbolic Name</span></span>|<span data-ttu-id="2fbad-113">DBCC_INDEX_MARKED_DISABLED</span><span class="sxs-lookup"><span data-stu-id="2fbad-113">DBCC_INDEX_MARKED_DISABLED</span></span>|  
|<span data-ttu-id="2fbad-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="2fbad-114">Message Text</span></span>|<span data-ttu-id="2fbad-115">Der 'INDEX_NAME'-Index für die 'OBJECT_NAME'-Tabelle ist als deaktiviert markiert.</span><span class="sxs-lookup"><span data-stu-id="2fbad-115">Index 'INDEX_NAME' on table 'OBJECT_NAME' is marked as disabled.</span></span> <span data-ttu-id="2fbad-116">Erstellen Sie den Index neu, um ihn online zu schalten.</span><span class="sxs-lookup"><span data-stu-id="2fbad-116">Rebuild the index to bring it online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2fbad-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="2fbad-117">Explanation</span></span>  
 <span data-ttu-id="2fbad-118">Der angegebene Index ist als offline markiert oder deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2fbad-118">The specified index is marked as offline or is disabled.</span></span> <span data-ttu-id="2fbad-119">Daher kann dieser Index nicht geprüft werden.</span><span class="sxs-lookup"><span data-stu-id="2fbad-119">Therefore, this index cannot be checked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2fbad-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="2fbad-120">User Action</span></span>  
 <span data-ttu-id="2fbad-121">Erstellen Sie den Index mithilfe von ALTER INDEX neu.</span><span class="sxs-lookup"><span data-stu-id="2fbad-121">Rebuild the index by using ALTER INDEX.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fbad-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2fbad-122">See Also</span></span>  
 <span data-ttu-id="2fbad-123">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2fbad-123">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 [<span data-ttu-id="2fbad-124">Neuorganisieren und Neuerstellen von Indizes</span><span class="sxs-lookup"><span data-stu-id="2fbad-124">Reorganize and Rebuild Indexes</span></span>](../indexes/indexes.md)  
  
  
