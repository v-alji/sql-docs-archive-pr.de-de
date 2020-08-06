---
title: MSSQLSERVER_1105 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1105 (Database Engine error)
ms.assetid: e7f4ad02-8c7f-4bb9-9781-2c86253f2138
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dea326fab7edd6a5c155c8f0182bffc044505eb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608743"
---
# <a name="mssqlserver_1105"></a><span data-ttu-id="25351-102">MSSQLSERVER_1105</span><span class="sxs-lookup"><span data-stu-id="25351-102">MSSQLSERVER_1105</span></span>
    
## <a name="details"></a><span data-ttu-id="25351-103">Details</span><span class="sxs-lookup"><span data-stu-id="25351-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="25351-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="25351-104">Product Name</span></span>|<span data-ttu-id="25351-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="25351-105">SQL Server</span></span>|  
|<span data-ttu-id="25351-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="25351-106">Event ID</span></span>|<span data-ttu-id="25351-107">1105</span><span class="sxs-lookup"><span data-stu-id="25351-107">1105</span></span>|  
|<span data-ttu-id="25351-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="25351-108">Event Source</span></span>|<span data-ttu-id="25351-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="25351-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="25351-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="25351-110">Component</span></span>|<span data-ttu-id="25351-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="25351-111">SQLEngine</span></span>|  
|<span data-ttu-id="25351-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="25351-112">Symbolic Name</span></span>|<span data-ttu-id="25351-113">NO_MORE_SPACE_IN_FG</span><span class="sxs-lookup"><span data-stu-id="25351-113">NO_MORE_SPACE_IN_FG</span></span>|  
|<span data-ttu-id="25351-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="25351-114">Message Text</span></span>|<span data-ttu-id="25351-115">Speicherplatz für das '%.\*ls'%.\*ls-Objekt in der '%.\*ls'-Datenbank konnte nicht zugeordnet werden, da die '%.\*ls'-Dateigruppe voll ist.</span><span class="sxs-lookup"><span data-stu-id="25351-115">Could not allocate space for object '%.\*ls'%.\*ls in database '%.\*ls' because the '%.\*ls' filegroup is full.</span></span> <span data-ttu-id="25351-116">Speicherplatz kann durch Löschen nicht benötigter Dateien, Löschen von Objekten in der Dateigruppe, Hinzufügen von Dateien zur Dateigruppe oder Festlegen der automatischen Vergrößerung für vorhandene Dateien in der Dateigruppe gewonnen werden.</span><span class="sxs-lookup"><span data-stu-id="25351-116">Create disk space by deleting unneeded files, dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="25351-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="25351-117">Explanation</span></span>  
 <span data-ttu-id="25351-118">In einer Dateigruppe ist kein Speicherplatz verfügbar.</span><span class="sxs-lookup"><span data-stu-id="25351-118">No disk space is available in a filegroup.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="25351-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="25351-119">User Action</span></span>  
 <span data-ttu-id="25351-120">Durch die folgenden Aktionen kann Speicherplatz in der Dateigruppe verfügbar gemacht werden:</span><span class="sxs-lookup"><span data-stu-id="25351-120">The following actions may make space available in the filegroup:</span></span>  
  
-   <span data-ttu-id="25351-121">Aktivieren Sie die automatische Vergrößerung.</span><span class="sxs-lookup"><span data-stu-id="25351-121">Turn on autogrow.</span></span>  
  
-   <span data-ttu-id="25351-122">Fügen Sie der Dateigruppe weitere Dateien hinzu.</span><span class="sxs-lookup"><span data-stu-id="25351-122">Add more files to the file group.</span></span>  
  
-   <span data-ttu-id="25351-123">Geben Sie Speicherplatz frei, indem Sie Indizes oder Tabellen löschen, die nicht mehr benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="25351-123">Free disk space by dropping index or tables that are no longer needed.</span></span>  
  
-   <span data-ttu-id="25351-124">Weitere Informationen finden Sie unter "Problembehandlung bei unzureichendem Speicherplatz" in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="25351-124">For more information, see "Troubleshooting Insufficient Data Disk Space" in SQL Server Books Online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="25351-125">Wenn sich ein Index in mehreren Dateien befindet, kann `ALTER INDEX REORGANIZE` Fehler 1105 zurückgeben, wenn eine der Dateien voll ist.</span><span class="sxs-lookup"><span data-stu-id="25351-125">When an index is located on several files, `ALTER INDEX REORGANIZE` can return error 1105 when one of the files is full.</span></span> <span data-ttu-id="25351-126">Der Neuorganisationsvorgang wird blockiert, wenn während des Prozesses versucht wird, Zeilen in die volle Datei zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="25351-126">The reorganization process is blocked when the process tries to move rows to the full file.</span></span> <span data-ttu-id="25351-127">Führen Sie `ALTER INDEX REBUILD` statt `ALTER INDEX REORGANIZE` aus, oder erhöhen Sie die Erweiterungsgrenze voller Dateien, um diese Einschränkung zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="25351-127">To work around this limitation perform an `ALTER INDEX REBUILD` instead of `ALTER INDEX REORGANIZE` or increase the file growth limit of any files that are full.</span></span>  
  
  
