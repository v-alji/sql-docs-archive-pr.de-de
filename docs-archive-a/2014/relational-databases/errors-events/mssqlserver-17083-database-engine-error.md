---
title: MSSQLSERVER_17083 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17083 (Database Engine error)
ms.assetid: 6c83737d-0531-4fd9-88f6-2da5a150532d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 598cf9b0182178aa13a6d8b965ac10bedaaf5d15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620935"
---
# <a name="mssqlserver_17083"></a><span data-ttu-id="fb519-102">MSSQLSERVER_17083</span><span class="sxs-lookup"><span data-stu-id="fb519-102">MSSQLSERVER_17083</span></span>
    
## <a name="details"></a><span data-ttu-id="fb519-103">Details</span><span class="sxs-lookup"><span data-stu-id="fb519-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fb519-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="fb519-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="fb519-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="fb519-105">Event ID</span></span>|<span data-ttu-id="fb519-106">17083</span><span class="sxs-lookup"><span data-stu-id="fb519-106">17083</span></span>|  
|<span data-ttu-id="fb519-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="fb519-107">Event Source</span></span>|<span data-ttu-id="fb519-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fb519-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fb519-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="fb519-109">Component</span></span>|<span data-ttu-id="fb519-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="fb519-110">SQLEngine</span></span>|  
|<span data-ttu-id="fb519-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="fb519-111">Symbolic Name</span></span>|<span data-ttu-id="fb519-112">P3_HEKATON_NOT_ATOMIC</span><span class="sxs-lookup"><span data-stu-id="fb519-112">P3_HEKATON_NOT_ATOMIC</span></span>|  
|<span data-ttu-id="fb519-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="fb519-113">Message Text</span></span>|<span data-ttu-id="fb519-114">Der Text einer systemintern kompilierten gespeicherten Prozedur muss ein ATOMIC-Block sein.</span><span class="sxs-lookup"><span data-stu-id="fb519-114">The body of a natively compiled stored procedure must be an ATOMIC block.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fb519-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="fb519-115">Explanation</span></span>  
 <span data-ttu-id="fb519-116">Der Text einer systemintern kompilierten gespeicherten Prozedur enthielt keinen ATOMIC-Block.</span><span class="sxs-lookup"><span data-stu-id="fb519-116">The body of a natively compiled stored procedure did not have an ATOMIC block.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fb519-117">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="fb519-117">User Action</span></span>  
 <span data-ttu-id="fb519-118">Eine systemintern kompilierte gespeicherte Prozedur muss einen ATOMIC-Block enthalten.</span><span class="sxs-lookup"><span data-stu-id="fb519-118">A natively compiled stored procedure must contain an ATOMIC block.</span></span> <span data-ttu-id="fb519-119">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fb519-119">For example:</span></span>  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE= N'us_english')  
```  
  
 <span data-ttu-id="fb519-120">Weitere Informationen finden Sie unter [In-Memory OLTP &#40;Arbeitsspeicheroptimierung&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="fb519-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb519-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fb519-121">See Also</span></span>  
 [<span data-ttu-id="fb519-122">In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;</span><span class="sxs-lookup"><span data-stu-id="fb519-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
