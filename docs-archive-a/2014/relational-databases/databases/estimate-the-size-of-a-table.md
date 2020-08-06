---
title: Schätzen der Größe einer Tabelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- pages [SQL Server], space
- space [SQL Server], tables
- row size [SQL Server]
- size [SQL Server], tables
- column size [SQL Server]
- predicting table size [SQL Server]
- table size [SQL Server]
- estimating table size
- clustered indexes, table size
- disk space [SQL Server], tables
- space allocation [SQL Server], table size
- designing databases [SQL Server], estimating size
- reserved free rows per page [SQL Server]
- calculating table size
ms.assetid: 15c17c92-616f-402e-894b-907a296efe5f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a16d439d3b2bc59479866b7bb36295ec4fc8950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721478"
---
# <a name="estimate-the-size-of-a-table"></a><span data-ttu-id="0df3c-102">Schätzen der Größe einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="0df3c-102">Estimate the Size of a Table</span></span>
  <span data-ttu-id="0df3c-103">Mit den folgenden Schritten können Sie den Umfang des Speicherplatzes schätzen, der zum Speichern von Daten in einer Tabelle erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="0df3c-103">You can use the following steps to estimate the amount of space required to store data in a table:</span></span>  
  
1.  <span data-ttu-id="0df3c-104">Berechnen Sie den erforderlichen Speicherplatz für den Heap oder gruppierten Index mithilfe der Anweisungen in den Artikeln [Schätzen der Größe eines Heaps](estimate-the-size-of-a-heap.md) oder [Schätzen der Größe eines gruppierten Indexes](estimate-the-size-of-a-clustered-index.md).</span><span class="sxs-lookup"><span data-stu-id="0df3c-104">Calculate the space required for the heap or clustered index following the instructions in [Estimate the Size of a Heap](estimate-the-size-of-a-heap.md) or [Estimate the Size of a Clustered Index](estimate-the-size-of-a-clustered-index.md).</span></span>  
  
2.  <span data-ttu-id="0df3c-105">Den für jeden nicht gruppierten Index benötigten Speicherplatz berechnen Sie, indem Sie die Anweisungen ausführen, die Sie unter [Schätzen der Größe eines nicht gruppierten Index](estimate-the-size-of-a-nonclustered-index.md)finden.</span><span class="sxs-lookup"><span data-stu-id="0df3c-105">For each nonclustered index, calculate the space required for it by following the instructions in [Estimate the Size of a Nonclustered Index](estimate-the-size-of-a-nonclustered-index.md).</span></span>  
  
3.  <span data-ttu-id="0df3c-106">Fügen Sie die in den Schritten 1 und 2 berechneten Werte hinzu.</span><span class="sxs-lookup"><span data-stu-id="0df3c-106">Add the values calculated in steps 1 and 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0df3c-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0df3c-107">See Also</span></span>  
 <span data-ttu-id="0df3c-108">[Schätzen der Größe einer Datenbank](estimate-the-size-of-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="0df3c-108">[Estimate the Size of a Database](estimate-the-size-of-a-database.md) </span></span>  
 <span data-ttu-id="0df3c-109">[Schätzen der Größe eines Heaps](estimate-the-size-of-a-heap.md) </span><span class="sxs-lookup"><span data-stu-id="0df3c-109">[Estimate the Size of a Heap](estimate-the-size-of-a-heap.md) </span></span>  
 <span data-ttu-id="0df3c-110">[Schätzen der Größe eines gruppierten Indexes](estimate-the-size-of-a-clustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="0df3c-110">[Estimate the Size of a Clustered Index](estimate-the-size-of-a-clustered-index.md) </span></span>  
 [<span data-ttu-id="0df3c-111">Schätzen der Größe eines nicht gruppierten Index</span><span class="sxs-lookup"><span data-stu-id="0df3c-111">Estimate the Size of a Nonclustered Index</span></span>](estimate-the-size-of-a-nonclustered-index.md)  
  
  
