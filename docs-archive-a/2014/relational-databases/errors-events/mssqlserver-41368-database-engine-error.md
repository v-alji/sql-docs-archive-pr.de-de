---
title: MSSQLSERVER_41368 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41368 (Database Engine error)
ms.assetid: abc71559-4c4d-4cce-a08f-3299dd167842
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 10e187223a3f35b4b21ede6965e3c9efea2e30c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699632"
---
# <a name="mssqlserver_41368"></a><span data-ttu-id="f817f-102">MSSQLSERVER_41368</span><span class="sxs-lookup"><span data-stu-id="f817f-102">MSSQLSERVER_41368</span></span>
    
## <a name="details"></a><span data-ttu-id="f817f-103">Details</span><span class="sxs-lookup"><span data-stu-id="f817f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f817f-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="f817f-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="f817f-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="f817f-105">Event ID</span></span>|<span data-ttu-id="f817f-106">41368</span><span class="sxs-lookup"><span data-stu-id="f817f-106">41368</span></span>|  
|<span data-ttu-id="f817f-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="f817f-107">Event Source</span></span>|<span data-ttu-id="f817f-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f817f-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f817f-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="f817f-109">Component</span></span>|<span data-ttu-id="f817f-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f817f-110">SQLEngine</span></span>|  
|<span data-ttu-id="f817f-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="f817f-111">Symbolic Name</span></span>|<span data-ttu-id="f817f-112">SQL_IMPLICIT_AND_EXPLICIT_TX_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="f817f-112">SQL_IMPLICIT_AND_EXPLICIT_TX_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="f817f-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="f817f-113">Message Text</span></span>|<span data-ttu-id="f817f-114">Der Zugriff auf speicheroptimierte Tabellen mit der READ COMMITTED-Isolationsstufe wird nur für Autocommittransaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f817f-114">Accessing memory optimized tables using the READ COMMITTED isolation level is supported only for autocommit transactions.</span></span> <span data-ttu-id="f817f-115">Er wird nicht für explizite oder implizite Transaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f817f-115">It is not supported for explicit or implicit transactions.</span></span> <span data-ttu-id="f817f-116">Geben Sie eine unterstützte Isolationsstufe für die speicheroptimierte Tabelle mithilfe eines Tabellentipps wie WITH (SNAPSHOT) an.</span><span class="sxs-lookup"><span data-stu-id="f817f-116">Provide a supported isolation level for the memory optimized table using a table hint, such as WITH (SNAPSHOT).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f817f-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="f817f-117">Explanation</span></span>  
 <span data-ttu-id="f817f-118">Der Zugriff auf speicheroptimierte Tabellen mit der READ COMMITTED-Isolationsstufe wird nur für Autocommittransaktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f817f-118">Accessing memory-optimized tables using the READ COMMITTED isolation level is supported only for autocommit transactions.</span></span> <span data-ttu-id="f817f-119">Weitere Informationen finden Sie unter [Transaction Isolation Levels](../../database-engine/transaction-isolation-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f817f-119">For more information, see [Transaction Isolation Levels](../../database-engine/transaction-isolation-levels.md).</span></span>  
  
 <span data-ttu-id="f817f-120">Wenn Sie unter Verwendung einer expliziten Transaktion, die mit BEGIN TRANSACTION gestartet wurde, oder einer impliziten Transaktion auf eine speicheroptimierte Tabelle zugreifen, während IMPLICIT_TRANSACTIONS auf ON festgelegt ist, wird die READ COMMITTED-Isolationsstufe nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f817f-120">When accessing a memory-optimized table from an explicit transaction that was started with BEGIN TRANSACTION, or from an implicit transaction, if IMPLICIT_TRANSACTIONS is set to ON, the READ COMMITTED isolation level is not supported.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f817f-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="f817f-121">User Action</span></span>  
 <span data-ttu-id="f817f-122">Verwenden Sie für den Tabellenzugriff die SNAPSHOT-Isolationsstufe, wenn Sie von einer expliziten oder impliziten READ COMMITTED-Transaktion auf eine speicheroptimierte Tabelle zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f817f-122">When accessing a memory-optimized table from an explicit or implicit READ COMMITTED transaction, use SNAPSHOT to access the table.</span></span> <span data-ttu-id="f817f-123">Hierzu können Sie den Tabellen Hinweis with (Snapshot) verwenden (Weitere Informationen finden Sie unter [Richtlinien für Transaktions Isolations Stufen mit Speicher optimierten Tabellen](../in-memory-oltp/memory-optimized-tables.md)) oder indem Sie die Datenbankoption MEMORY_OPTIMIZED_ELEVATE_TO_SNAPSHOT auf on festlegen (Weitere Informationen finden Sie unter [ALTER DATABASE SET-Optionen &#40;Transact-SQL-&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options)).</span><span class="sxs-lookup"><span data-stu-id="f817f-123">This can be achieved by using the table hint WITH (SNAPSHOT) (for more information, see [Guidelines for Transaction Isolation Levels with Memory-Optimized Tables](../in-memory-oltp/memory-optimized-tables.md)) or by setting the database option MEMORY_OPTIMIZED_ELEVATE_TO_SNAPSHOT to ON (for more information, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f817f-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f817f-124">See Also</span></span>  
 [<span data-ttu-id="f817f-125">In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;</span><span class="sxs-lookup"><span data-stu-id="f817f-125">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
