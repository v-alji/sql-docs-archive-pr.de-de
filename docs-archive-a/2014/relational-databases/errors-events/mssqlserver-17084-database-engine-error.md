---
title: MSSQLSERVER_17084 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17084 (Database Engine error)
ms.assetid: e579d104-3307-4edd-8587-b14ecbc02ed9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 59b0fc3e0884ddd89809767a068b937b5c145f9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620930"
---
# <a name="mssqlserver_17084"></a><span data-ttu-id="76a23-102">MSSQLSERVER_17084</span><span class="sxs-lookup"><span data-stu-id="76a23-102">MSSQLSERVER_17084</span></span>
    
## <a name="details"></a><span data-ttu-id="76a23-103">Details</span><span class="sxs-lookup"><span data-stu-id="76a23-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="76a23-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="76a23-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="76a23-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="76a23-105">Event ID</span></span>|<span data-ttu-id="76a23-106">17084</span><span class="sxs-lookup"><span data-stu-id="76a23-106">17084</span></span>|  
|<span data-ttu-id="76a23-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="76a23-107">Event Source</span></span>|<span data-ttu-id="76a23-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="76a23-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="76a23-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="76a23-109">Component</span></span>|<span data-ttu-id="76a23-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="76a23-110">SQLEngine</span></span>|  
|<span data-ttu-id="76a23-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="76a23-111">Symbolic Name</span></span>|<span data-ttu-id="76a23-112">P3_ATOMIC_WITH_MISSING_OPTION</span><span class="sxs-lookup"><span data-stu-id="76a23-112">P3_ATOMIC_WITH_MISSING_OPTION</span></span>|  
|<span data-ttu-id="76a23-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="76a23-113">Message Text</span></span>|<span data-ttu-id="76a23-114">Die WITH-Klausel der Anweisung BEGIN ATOMIC muss einen Wert für die Option "%ls" angeben.</span><span class="sxs-lookup"><span data-stu-id="76a23-114">The WITH clause of BEGIN ATOMIC statement must specify a value for the option '%ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="76a23-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="76a23-115">Explanation</span></span>  
 <span data-ttu-id="76a23-116">Die WITH-Klausel der Anweisung BEGIN ATOMIC gab keinen Wert für eine Option an.</span><span class="sxs-lookup"><span data-stu-id="76a23-116">The WITH clause of BEGIN ATOMIC statement did not specify a value for an option.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="76a23-117">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="76a23-117">User Action</span></span>  
 <span data-ttu-id="76a23-118">`ATOMIC`-Blöcke erfordern Werte für die `WITH`-Optionen `TRANSACTION ISOLATION LEVEL` und `LANGUAGE`.</span><span class="sxs-lookup"><span data-stu-id="76a23-118">`ATOMIC` blocks require values for the `WITH` options `TRANSACTION ISOLATION LEVEL` and `LANGUAGE`.</span></span> <span data-ttu-id="76a23-119">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="76a23-119">For example::</span></span>  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE= N'us_english')  
```  
  
 <span data-ttu-id="76a23-120">Weitere Informationen finden Sie unter [In-Memory OLTP &#40;Arbeitsspeicheroptimierung&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="76a23-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76a23-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76a23-121">See Also</span></span>  
 [<span data-ttu-id="76a23-122">In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;</span><span class="sxs-lookup"><span data-stu-id="76a23-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
