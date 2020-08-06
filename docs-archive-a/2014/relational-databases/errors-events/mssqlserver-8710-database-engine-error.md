---
title: MSSQLSERVER_8710 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8710 (Database Engine error)
ms.assetid: 78b9f9da-5489-4be0-94df-f065d86ed18c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 65fb6b3efb42c282347f560353a2b21edc337859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630666"
---
# <a name="mssqlserver_8710"></a><span data-ttu-id="ad94f-102">MSSQLSERVER_8710</span><span class="sxs-lookup"><span data-stu-id="ad94f-102">MSSQLSERVER_8710</span></span>
    
## <a name="details"></a><span data-ttu-id="ad94f-103">Details</span><span class="sxs-lookup"><span data-stu-id="ad94f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ad94f-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="ad94f-104">Product Name</span></span>|<span data-ttu-id="ad94f-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ad94f-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ad94f-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="ad94f-106">Event ID</span></span>|<span data-ttu-id="ad94f-107">8710</span><span class="sxs-lookup"><span data-stu-id="ad94f-107">8710</span></span>|  
|<span data-ttu-id="ad94f-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="ad94f-108">Event Source</span></span>|<span data-ttu-id="ad94f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ad94f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ad94f-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="ad94f-110">Component</span></span>|<span data-ttu-id="ad94f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ad94f-111">SQLEngine</span></span>|  
|<span data-ttu-id="ad94f-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="ad94f-112">Symbolic Name</span></span>|<span data-ttu-id="ad94f-113">QUERY2_CUBE_ILLEGAL_AGG_FUNC</span><span class="sxs-lookup"><span data-stu-id="ad94f-113">QUERY2_CUBE_ILLEGAL_AGG_FUNC</span></span>|  
|<span data-ttu-id="ad94f-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="ad94f-114">Message Text</span></span>|<span data-ttu-id="ad94f-115">Aggregatfunktionen, die mit CUBE-, ROLLUP- oder GROUPING SET-Abfragen verwendet werden, müssen das Zusammenführen von Unteraggregaten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ad94f-115">Aggregate functions that are used with CUBE, ROLLUP, or GROUPING SET queries must provide for the merging of subaggregates.</span></span> <span data-ttu-id="ad94f-116">Entfernen Sie die Aggregatfunktion, oder schreiben Sie die Abfrage mit UNION ALL über GROUP BY-Klauseln, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="ad94f-116">To fix this problem, remove the aggregate function or write the query using UNION ALL over GROUP BY clauses.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ad94f-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="ad94f-117">Explanation</span></span>  
 <span data-ttu-id="ad94f-118">Es wurde eine Aggregatfunktion mit CUBE, ROLLUP oder GROUPING SETS verwendet, die keine Methode zum Zusammenführen von Unteraggregaten zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="ad94f-118">An aggregate function has been used with CUBE, ROLLUP, or GROUPING SETS that does not provide a method for merging subaggregates.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ad94f-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="ad94f-119">User Action</span></span>  
 <span data-ttu-id="ad94f-120">Entfernen Sie die Aggregatfunktion, oder schreiben Sie die Abfrage mit UNION ALL über GROUP BY-Klauseln, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="ad94f-120">To fix this problem, remove the aggregate function or write the query using UNION ALL over GROUP BY clauses.</span></span>  
  
  
