---
title: MSSQLSERVER_12304 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 12304 (Database Engine error)
ms.assetid: a2c252c2-e815-4ac8-a101-7af5b32e3233
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c2347fc46fe5ab83ef2ff46b81500cd737ed02d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619159"
---
# <a name="mssqlserver_12304"></a><span data-ttu-id="91289-102">MSSQLSERVER_12304</span><span class="sxs-lookup"><span data-stu-id="91289-102">MSSQLSERVER_12304</span></span>
    
## <a name="details"></a><span data-ttu-id="91289-103">Details</span><span class="sxs-lookup"><span data-stu-id="91289-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="91289-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="91289-104">Product Name</span></span>|<span data-ttu-id="91289-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="91289-105">SQL Server</span></span>|  
|<span data-ttu-id="91289-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="91289-106">Event ID</span></span>|<span data-ttu-id="91289-107">12304</span><span class="sxs-lookup"><span data-stu-id="91289-107">12304</span></span>|  
|<span data-ttu-id="91289-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="91289-108">Event Source</span></span>|<span data-ttu-id="91289-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="91289-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="91289-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="91289-110">Component</span></span>|<span data-ttu-id="91289-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="91289-111">SQLEngine</span></span>|  
|<span data-ttu-id="91289-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="91289-112">Symbolic Name</span></span>|<span data-ttu-id="91289-113">HK_UNSUPPORTED_IDENTITY_TABLE_VAR</span><span class="sxs-lookup"><span data-stu-id="91289-113">HK_UNSUPPORTED_IDENTITY_TABLE_VAR</span></span>|  
|<span data-ttu-id="91289-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="91289-114">Message Text</span></span>|<span data-ttu-id="91289-115">Die Verwendung eines speicheroptimierten Tabellentyps, der die IDENTITY-Eigenschaft für die zugehörigen Spalten einsetzt, wird nicht unterstützt, wenn der Typ außerhalb des Kontexts einer systemintern kompilierten gespeicherten Prozedur auftritt.</span><span class="sxs-lookup"><span data-stu-id="91289-115">Using a memory optimized table type that uses the IDENTITY property with any of its columns is not supported when using the type outside the context of a natively compiled stored procedure.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="91289-116">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="91289-116">User Action</span></span>  
 <span data-ttu-id="91289-117">Verwenden Sie keinen speicheroptimierten Tabellentyp, wenn für dessen Spalten die IDENTITY-Eigenschaft eingesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="91289-117">Do not use a memory-optimized table type that uses the identity property with any of its columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91289-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="91289-118">See Also</span></span>  
 [<span data-ttu-id="91289-119">In-Memory-OLTP &#40;Arbeitsspeicheroptimierung&#41;</span><span class="sxs-lookup"><span data-stu-id="91289-119">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
