---
title: MSSQLSERVER_2596 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2596 (Database Engine error)
ms.assetid: 49ab892f-8ba3-4ba1-b562-ddf205019802
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 27b2ceed40274df4ba57c4d61a83fbc60b6a7f80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618043"
---
# <a name="mssqlserver_2596"></a><span data-ttu-id="238f7-102">MSSQLSERVER_2596</span><span class="sxs-lookup"><span data-stu-id="238f7-102">MSSQLSERVER_2596</span></span>
    
## <a name="details"></a><span data-ttu-id="238f7-103">Details</span><span class="sxs-lookup"><span data-stu-id="238f7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="238f7-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="238f7-104">Product Name</span></span>|<span data-ttu-id="238f7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="238f7-105">SQL Server</span></span>|  
|<span data-ttu-id="238f7-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="238f7-106">Event ID</span></span>|<span data-ttu-id="238f7-107">2596</span><span class="sxs-lookup"><span data-stu-id="238f7-107">2596</span></span>|  
|<span data-ttu-id="238f7-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="238f7-108">Event Source</span></span>|<span data-ttu-id="238f7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="238f7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="238f7-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="238f7-110">Component</span></span>|<span data-ttu-id="238f7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="238f7-111">SQLEngine</span></span>|  
|<span data-ttu-id="238f7-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="238f7-112">Symbolic Name</span></span>|<span data-ttu-id="238f7-113">DBCC_DATABASE_IN_READ_ONLY_MODE</span><span class="sxs-lookup"><span data-stu-id="238f7-113">DBCC_DATABASE_IN_READ_ONLY_MODE</span></span>|  
|<span data-ttu-id="238f7-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="238f7-114">Message Text</span></span>|<span data-ttu-id="238f7-115">Die REPAIR-Anweisung wurde nicht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="238f7-115">The repair statement was not processed.</span></span> <span data-ttu-id="238f7-116">Die Datenbank kann nicht im schreibgeschützten Modus sein.</span><span class="sxs-lookup"><span data-stu-id="238f7-116">The database cannot be in read-only mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="238f7-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="238f7-117">Explanation</span></span>  
 <span data-ttu-id="238f7-118">Diese Meldung gibt an, dass sich die Datenbank im schreibgeschützten Modus befindet.</span><span class="sxs-lookup"><span data-stu-id="238f7-118">This message indicates that the database is in read-only mode.</span></span> <span data-ttu-id="238f7-119">Reparaturen sind nicht möglich, wenn sich eine Datenbank im schreibgeschützten Modus befindet.</span><span class="sxs-lookup"><span data-stu-id="238f7-119">Repairs are not possible when a database is in read-only mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="238f7-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="238f7-120">User Action</span></span>  
 <span data-ttu-id="238f7-121">Legen Sie die Datenbank mithilfe der ALTER DATABASE-Anweisung auf Lese-/Schreibzugriff fest, und führen Sie anschließend den DBCC-Befehl erneut aus.</span><span class="sxs-lookup"><span data-stu-id="238f7-121">Set the database to read-write by using ALTER DATABASE, and then re-run the DBCC command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="238f7-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="238f7-122">See Also</span></span>  
 [<span data-ttu-id="238f7-123">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="238f7-123">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
