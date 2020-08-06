---
title: MSSQLSERVER_41325 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41325 (Database Engine error)
ms.assetid: 97c6a8bb-139a-44f3-9ed5-f46d047e8ed3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a512d7db6529876259d889d04aabf3d07747cafe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701228"
---
# <a name="mssqlserver_41325"></a><span data-ttu-id="8ad56-102">MSSQLSERVER_41325</span><span class="sxs-lookup"><span data-stu-id="8ad56-102">MSSQLSERVER_41325</span></span>
    
## <a name="details"></a><span data-ttu-id="8ad56-103">Details</span><span class="sxs-lookup"><span data-stu-id="8ad56-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8ad56-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="8ad56-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="8ad56-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="8ad56-105">Event ID</span></span>|<span data-ttu-id="8ad56-106">41325</span><span class="sxs-lookup"><span data-stu-id="8ad56-106">41325</span></span>|  
|<span data-ttu-id="8ad56-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="8ad56-107">Event Source</span></span>|<span data-ttu-id="8ad56-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8ad56-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8ad56-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="8ad56-109">Component</span></span>|<span data-ttu-id="8ad56-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8ad56-110">SQLEngine</span></span>|  
|<span data-ttu-id="8ad56-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="8ad56-111">Symbolic Name</span></span>|<span data-ttu-id="8ad56-112">HK_TX_COMMIT_SR_VALIDATION</span><span class="sxs-lookup"><span data-stu-id="8ad56-112">HK_TX_COMMIT_SR_VALIDATION</span></span>|  
|<span data-ttu-id="8ad56-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="8ad56-113">Message Text</span></span>|<span data-ttu-id="8ad56-114">Für die aktuelle Transaktion wurde aufgrund eines serialisierbaren Überprüfungsfehlers kein Commit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8ad56-114">The current transaction failed to commit due to a serializable validation failure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8ad56-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="8ad56-115">Explanation</span></span>  
 <span data-ttu-id="8ad56-116">Bei der Transaktion trat ein Überprüfungsfehler auf, sie kann nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="8ad56-116">The transaction encountered a validation failure and is now doomed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8ad56-117">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="8ad56-117">User Action</span></span>  
 <span data-ttu-id="8ad56-118">Wiederholen Sie die fehlgeschlagene Transaktion.</span><span class="sxs-lookup"><span data-stu-id="8ad56-118">Retry the failed transaction.</span></span> <span data-ttu-id="8ad56-119">Weitere Informationen finden Sie unter [In-Memory OLTP &#40;Arbeitsspeicheroptimierung&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="8ad56-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ad56-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8ad56-120">See Also</span></span>  
 [<span data-ttu-id="8ad56-121">In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;</span><span class="sxs-lookup"><span data-stu-id="8ad56-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
