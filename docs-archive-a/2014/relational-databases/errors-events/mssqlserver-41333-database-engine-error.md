---
title: MSSQLSERVER_41333 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41333 (Database Engine error)
ms.assetid: c3c3ae9a-1e4c-4de6-ba72-2f393375b053
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6ba3cfc9627b4b44c3c9eccc620fb16bb94b861b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701229"
---
# <a name="mssqlserver_41333"></a><span data-ttu-id="d8f10-102">MSSQLSERVER_41333</span><span class="sxs-lookup"><span data-stu-id="d8f10-102">MSSQLSERVER_41333</span></span>
    
## <a name="details"></a><span data-ttu-id="d8f10-103">Details</span><span class="sxs-lookup"><span data-stu-id="d8f10-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d8f10-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="d8f10-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="d8f10-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="d8f10-105">Event ID</span></span>|<span data-ttu-id="d8f10-106">41333</span><span class="sxs-lookup"><span data-stu-id="d8f10-106">41333</span></span>|  
|<span data-ttu-id="d8f10-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="d8f10-107">Event Source</span></span>|<span data-ttu-id="d8f10-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d8f10-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d8f10-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="d8f10-109">Component</span></span>|<span data-ttu-id="d8f10-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d8f10-110">SQLEngine</span></span>|  
|<span data-ttu-id="d8f10-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="d8f10-111">Symbolic Name</span></span>|<span data-ttu-id="d8f10-112">CROSS_CONTAINER_ISOLATION_FAILURE</span><span class="sxs-lookup"><span data-stu-id="d8f10-112">CROSS_CONTAINER_ISOLATION_FAILURE</span></span>|  
|<span data-ttu-id="d8f10-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="d8f10-113">Message Text</span></span>|<span data-ttu-id="d8f10-114">Die folgenden Transaktionen müssen unter Verwendung der Momentaufnahmeisolation auf speicheroptimierte Tabellen und systemintern kompilierte gespeicherte Prozeduren zugreifen: RepeatableRead-Transaktionen, Serializable-Transaktionen und Transaktionen, die auf Tabellen zugreifen, die in der RepeatableRead-Isolation oder der Serializable-Isolation nicht speicheroptimiert sind.</span><span class="sxs-lookup"><span data-stu-id="d8f10-114">The following transactions must access memory optimized tables and natively compiled stored procedures under snapshot isolation: RepeatableRead transactions, Serializable transactions, and transactions that access tables that are not memory optimized in RepeatableRead or Serializable isolation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d8f10-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="d8f10-115">Explanation</span></span>  
 <span data-ttu-id="d8f10-116">Es gibt Einschränkungen für den Benutzer der höheren Isolationsstufen zwischen datenträgerbasierten Transaktionen und XTP-Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="d8f10-116">There are restrictions against the user of the higher isolation levels between disk based transactions and XTP transactions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d8f10-117">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="d8f10-117">User Action</span></span>  
 <span data-ttu-id="d8f10-118">Versuchen Sie nicht, Isolationsvorgänge auf hoher Ebene in speicheroptimierten Tabellen (und systemintern kompilierten Prozeduren) und datenträgerbasierten Tabellen durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="d8f10-118">Don't attempt high level isolation operations on memory-optimized tables (and natively compiled procedures) and disk based tables.</span></span>  
  
 <span data-ttu-id="d8f10-119">Weitere Informationen finden Sie unter [In-Memory OLTP &#40;Arbeitsspeicheroptimierung&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="d8f10-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8f10-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d8f10-120">See Also</span></span>  
 [<span data-ttu-id="d8f10-121">In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;</span><span class="sxs-lookup"><span data-stu-id="d8f10-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
