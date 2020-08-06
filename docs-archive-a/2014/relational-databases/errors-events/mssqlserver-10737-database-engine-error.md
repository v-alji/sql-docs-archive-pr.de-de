---
title: MSSQLSERVER_10737 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10737 (Database Engine error)
ms.assetid: 208af6ed-b271-4ab8-803e-7666025385c8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: df8a4de014552d3aca00b3eb244f7ff8df56756b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620441"
---
# <a name="mssqlserver_10737"></a><span data-ttu-id="02f55-102">MSSQLSERVER_10737</span><span class="sxs-lookup"><span data-stu-id="02f55-102">MSSQLSERVER_10737</span></span>
    
## <a name="details"></a><span data-ttu-id="02f55-103">Details</span><span class="sxs-lookup"><span data-stu-id="02f55-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="02f55-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="02f55-104">Product Name</span></span>|<span data-ttu-id="02f55-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="02f55-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="02f55-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="02f55-106">Event ID</span></span>|<span data-ttu-id="02f55-107">10737</span><span class="sxs-lookup"><span data-stu-id="02f55-107">10737</span></span>|  
|<span data-ttu-id="02f55-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="02f55-108">Event Source</span></span>|<span data-ttu-id="02f55-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="02f55-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="02f55-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="02f55-110">Component</span></span>|<span data-ttu-id="02f55-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="02f55-111">SQLEngine</span></span>|  
|<span data-ttu-id="02f55-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="02f55-112">Symbolic Name</span></span>|<span data-ttu-id="02f55-113">REBUILD_PARTITION_ALL_NOT_SPECIFIED</span><span class="sxs-lookup"><span data-stu-id="02f55-113">REBUILD_PARTITION_ALL_NOT_SPECIFIED</span></span>|  
|<span data-ttu-id="02f55-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="02f55-114">Message Text</span></span>|<span data-ttu-id="02f55-115">In einer ALTER TABLE REBUILD-Anweisung oder einer ALTER INDEX REBUILD-Anweisung muss PARTITION=ALL angegeben werden, wenn in einer DATA_COMPRESSION-Klausel eine Partition angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="02f55-115">In an ALTER TABLE REBUILD or ALTER INDEX REBUILD statement, when a partition is specified in a DATA_COMPRESSION clause, PARTITION=ALL must be specified.</span></span> <span data-ttu-id="02f55-116">Mit der PARTITION=ALL-Klausel wird erzwungen, dass alle Partitionen der Tabelle oder des Indexes auch dann neu erstellt werden, wenn nur eine Teilmenge in der DATA_COMPRESSION-Klausel angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="02f55-116">The PARTITION=ALL clause is used to reinforce that all partitions of the table or index will be rebuilt, even if only a subset is specified in the DATA_COMPRESSION clause.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="02f55-117">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="02f55-117">User Action</span></span>  
 <span data-ttu-id="02f55-118">Fügen Sie die PARTITION=ALL-Klausel der ALTER TABLE-Anweisung oder der ALTER INDEX-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="02f55-118">Add the PARTITION=ALL clause to the ALTER TABLE or ALTER INDEX statement.</span></span> <span data-ttu-id="02f55-119">Alternativ dazu können Sie REBUILD PARTITION = \<partition-number-expr> WITH (DATA_COMPRESSION={ON | OFF}) verwenden, um eine bestimmte Partition neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="02f55-119">Or, to rebuild a specific partition, use REBUILD PARTITION = \<partition-number-expr> WITH (DATA_COMPRESSION={ON | OFF}).</span></span>  
  
  
