---
title: MSSQLSERVER_2538 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2538 (Database Engine error)
ms.assetid: 0a0f7d79-f1ba-4749-8804-fb660cca3492
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9f4ae886a6fd0abee2f7aa22c6a234c0a6c2d040
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620911"
---
# <a name="mssqlserver_2538"></a><span data-ttu-id="e884d-102">MSSQLSERVER_2538</span><span class="sxs-lookup"><span data-stu-id="e884d-102">MSSQLSERVER_2538</span></span>
    
## <a name="details"></a><span data-ttu-id="e884d-103">Details</span><span class="sxs-lookup"><span data-stu-id="e884d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e884d-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="e884d-104">Product Name</span></span>|<span data-ttu-id="e884d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e884d-105">SQL Server</span></span>|  
|<span data-ttu-id="e884d-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e884d-106">Event ID</span></span>|<span data-ttu-id="e884d-107">2538</span><span class="sxs-lookup"><span data-stu-id="e884d-107">2538</span></span>|  
|<span data-ttu-id="e884d-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="e884d-108">Event Source</span></span>|<span data-ttu-id="e884d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e884d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e884d-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="e884d-110">Component</span></span>|<span data-ttu-id="e884d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e884d-111">SQLEngine</span></span>|  
|<span data-ttu-id="e884d-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="e884d-112">Symbolic Name</span></span>|<span data-ttu-id="e884d-113">DBCC_ALLOCATION_SUMMARY_PER_FILE</span><span class="sxs-lookup"><span data-stu-id="e884d-113">DBCC_ALLOCATION_SUMMARY_PER_FILE</span></span>|  
|<span data-ttu-id="e884d-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="e884d-114">Message Text</span></span>|<span data-ttu-id="e884d-115">Datei FILE.</span><span class="sxs-lookup"><span data-stu-id="e884d-115">File FILE.</span></span> <span data-ttu-id="e884d-116">Blockanzahl = EXTENTS, verwendete Seiten = USED_PAGES, reservierte Seiten = RESERVED_PAGES.</span><span class="sxs-lookup"><span data-stu-id="e884d-116">Number of extents = EXTENTS, used pages = USED_PAGES, reserved pages = RESERVED_PAGES.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e884d-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="e884d-117">Explanation</span></span>  
 <span data-ttu-id="e884d-118">Diese Informationen sind Teil der Ausgabe des Befehls DBCC CHECKALLOC.</span><span class="sxs-lookup"><span data-stu-id="e884d-118">This information is part of the output from the DBCC CHECKALLOC command.</span></span> <span data-ttu-id="e884d-119">Bei diesen Informationen handelt es sich um die Zusammenfassung von zugeordneten Blöcken, verwendeten Seiten und reservierten Seiten pro Datei für die angegebene Datenbank.</span><span class="sxs-lookup"><span data-stu-id="e884d-119">This information is the per-file summary of allocated extents, used pages, and reserved pages for the specified database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e884d-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="e884d-120">User Action</span></span>  
 <span data-ttu-id="e884d-121">Keine</span><span class="sxs-lookup"><span data-stu-id="e884d-121">None</span></span>  
  
  
