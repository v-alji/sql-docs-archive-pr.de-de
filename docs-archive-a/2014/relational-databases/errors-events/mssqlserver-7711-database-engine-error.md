---
title: MSSQLSERVER_7711 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7711 (Database Engine error)
ms.assetid: a5c7cd6e-18d6-47ef-902b-db9dd64bba34
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e29b2ea993e8e5332ef03b05f628dc791e20aba9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618017"
---
# <a name="mssqlserver_7711"></a><span data-ttu-id="b618f-102">MSSQLSERVER_7711</span><span class="sxs-lookup"><span data-stu-id="b618f-102">MSSQLSERVER_7711</span></span>
    
## <a name="details"></a><span data-ttu-id="b618f-103">Details</span><span class="sxs-lookup"><span data-stu-id="b618f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b618f-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="b618f-104">Product Name</span></span>|<span data-ttu-id="b618f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b618f-105">SQL Server</span></span>|  
|<span data-ttu-id="b618f-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b618f-106">Event ID</span></span>|<span data-ttu-id="b618f-107">7711</span><span class="sxs-lookup"><span data-stu-id="b618f-107">7711</span></span>|  
|<span data-ttu-id="b618f-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="b618f-108">Event Source</span></span>|<span data-ttu-id="b618f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b618f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b618f-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="b618f-110">Component</span></span>|<span data-ttu-id="b618f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b618f-111">SQLEngine</span></span>|  
|<span data-ttu-id="b618f-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="b618f-112">Symbolic Name</span></span>|<span data-ttu-id="b618f-113">PRT_RANGE_OVERLAP</span><span class="sxs-lookup"><span data-stu-id="b618f-113">PRT_RANGE_OVERLAP</span></span>|  
|<span data-ttu-id="b618f-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="b618f-114">Message Text</span></span>|<span data-ttu-id="b618f-115">Die DATA_COMPRESSION-Option wurde für die Tabelle oder, sofern sie partitioniert ist, für mindestens eine ihrer Partitionen mehrfach angegeben.</span><span class="sxs-lookup"><span data-stu-id="b618f-115">The DATA_COMPRESSION option was specified more than once for the table or index or one of its partitions.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b618f-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="b618f-116">Explanation</span></span>  
 <span data-ttu-id="b618f-117">In einer der folgenden Anweisungen ist ein Fehler in der DATA_COMPRESSION-Option aufgetreten:</span><span class="sxs-lookup"><span data-stu-id="b618f-117">An error occurred in the DATA_COMPRESSION option in one of the following statements:</span></span>  
  
-   <span data-ttu-id="b618f-118">CREATE TABLE</span><span class="sxs-lookup"><span data-stu-id="b618f-118">CREATE TABLE</span></span>  
  
-   <span data-ttu-id="b618f-119">ALTER TABLE</span><span class="sxs-lookup"><span data-stu-id="b618f-119">ALTER TABLE</span></span>  
  
-   <span data-ttu-id="b618f-120">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="b618f-120">CREATE INDEX</span></span>  
  
-   <span data-ttu-id="b618f-121">ALTER INDEX</span><span class="sxs-lookup"><span data-stu-id="b618f-121">ALTER INDEX</span></span>  
  
 <span data-ttu-id="b618f-122">Wenn die angegebene Tabelle bzw. der angegebene Index partitioniert ist, wurde die DATA_COMPRESSION-Option für mindestens eine der Partitionen mehrfach aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="b618f-122">If the table or index cited is partitioned, the DATA_COMPRESSION option was listed more than one time for at least one of the partitions.</span></span> <span data-ttu-id="b618f-123">Wenn die Tabelle bzw. der Index nicht partitioniert ist, wurde die DATA_COMPRESSION-Option mehrfach angegeben.</span><span class="sxs-lookup"><span data-stu-id="b618f-123">If the table or index is not partitioned, the DATA_COMPRESSION option was cited more than one time.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b618f-124">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="b618f-124">User Action</span></span>  
 <span data-ttu-id="b618f-125">Stellen Sie bei einer partitionierten Tabelle bzw. einem partitionierten Index sicher, dass die DATA_COMPRESSION-Option für jede Partition nur einmal angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b618f-125">For a partitioned table or index, make sure that the DATA_COMPRESSION option is specified only one time for each partition.</span></span> <span data-ttu-id="b618f-126">Verwenden Sie für eine nicht partitionierte Tabelle bzw. einen nicht partitionierten Index die DATA_COMPRESSION-Option nur einmal in der Anweisung.</span><span class="sxs-lookup"><span data-stu-id="b618f-126">For a table or index that is not partitioned, use the DATA_COMPRESSION option only one time in the statement.</span></span>  
  
  
