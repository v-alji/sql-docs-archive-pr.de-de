---
title: MSSQLSERVER_617 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 617 (Database Engine error)
ms.assetid: 213545d9-08a7-4427-bfd1-8b7e16644281
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 88e9feb7c3ac5d8cf646d2243319b2b160b7757e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718154"
---
# <a name="mssqlserver_617"></a><span data-ttu-id="272bb-102">MSSQLSERVER_617</span><span class="sxs-lookup"><span data-stu-id="272bb-102">MSSQLSERVER_617</span></span>
    
## <a name="details"></a><span data-ttu-id="272bb-103">Details</span><span class="sxs-lookup"><span data-stu-id="272bb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="272bb-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="272bb-104">Product Name</span></span>|<span data-ttu-id="272bb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="272bb-105">SQL Server</span></span>|  
|<span data-ttu-id="272bb-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="272bb-106">Event ID</span></span>|<span data-ttu-id="272bb-107">617</span><span class="sxs-lookup"><span data-stu-id="272bb-107">617</span></span>|  
|<span data-ttu-id="272bb-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="272bb-108">Event Source</span></span>|<span data-ttu-id="272bb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="272bb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="272bb-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="272bb-110">Component</span></span>|<span data-ttu-id="272bb-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="272bb-111">SQLEngine</span></span>|  
|<span data-ttu-id="272bb-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="272bb-112">Symbolic Name</span></span>|<span data-ttu-id="272bb-113">NODESHASH</span><span class="sxs-lookup"><span data-stu-id="272bb-113">NODESHASH</span></span>|  
|<span data-ttu-id="272bb-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="272bb-114">Message Text</span></span>|<span data-ttu-id="272bb-115">Der Deskriptor für die Objekt-ID %ld in der Datenbank mit der ID %d wurde in der Hashtabelle beim Versuch, ihn aus dieser zu entfernen, nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="272bb-115">Descriptor for object ID %ld in database ID %d not found in the hash table during attempt to unhash it.</span></span> <span data-ttu-id="272bb-116">In einer Arbeitstabelle fehlt ein Eintrag.</span><span class="sxs-lookup"><span data-stu-id="272bb-116">A work table is missing an entry.</span></span> <span data-ttu-id="272bb-117">Führen Sie die Abfrage erneut aus.</span><span class="sxs-lookup"><span data-stu-id="272bb-117">Rerun the query.</span></span> <span data-ttu-id="272bb-118">Falls ein Cursor beteiligt ist, schließen Sie den Cursor, und öffnen Sie ihn erneut.</span><span class="sxs-lookup"><span data-stu-id="272bb-118">If a cursor is involved, close and reopen the cursor.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="272bb-119">Erklärung</span><span class="sxs-lookup"><span data-stu-id="272bb-119">Explanation</span></span>  
 <span data-ttu-id="272bb-120">SQL Server kann die Arbeitstabelle für einen bestimmten Eintrag nicht finden.</span><span class="sxs-lookup"><span data-stu-id="272bb-120">SQL Server cannot locate the work table for a specific entry.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="272bb-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="272bb-121">User Action</span></span>  
  
1.  <span data-ttu-id="272bb-122">Falls ein Cursor beteiligt ist, schließen Sie den Cursor, und öffnen Sie ihn dann erneut.</span><span class="sxs-lookup"><span data-stu-id="272bb-122">If a cursor is involved, close the cursor and re-open the cursor.</span></span>  
  
2.  <span data-ttu-id="272bb-123">Führen Sie die Abfrage erneut aus.</span><span class="sxs-lookup"><span data-stu-id="272bb-123">Run the query again.</span></span>  
  
  
