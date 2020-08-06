---
title: MSSQLSERVER_3156 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3156 (Database Engine error)
ms.assetid: 345d8ed4-177e-4ec3-bab3-25d30000e323
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 25b5a037012a6d6b47b91e763a49cfb67b89f43c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618024"
---
# <a name="mssqlserver_3156"></a><span data-ttu-id="b8141-102">MSSQLSERVER_3156</span><span class="sxs-lookup"><span data-stu-id="b8141-102">MSSQLSERVER_3156</span></span>
    
## <a name="details"></a><span data-ttu-id="b8141-103">Details</span><span class="sxs-lookup"><span data-stu-id="b8141-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b8141-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="b8141-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="b8141-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b8141-105">Event ID</span></span>|<span data-ttu-id="b8141-106">3156</span><span class="sxs-lookup"><span data-stu-id="b8141-106">3156</span></span>|  
|<span data-ttu-id="b8141-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="b8141-107">Event Source</span></span>|<span data-ttu-id="b8141-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b8141-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b8141-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="b8141-109">Component</span></span>|<span data-ttu-id="b8141-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b8141-110">SQLEngine</span></span>|  
|<span data-ttu-id="b8141-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="b8141-111">Symbolic Name</span></span>|<span data-ttu-id="b8141-112">LDDB_CANT_WRITE</span><span class="sxs-lookup"><span data-stu-id="b8141-112">LDDB_CANT_WRITE</span></span>|  
|<span data-ttu-id="b8141-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="b8141-113">Message Text</span></span>|<span data-ttu-id="b8141-114">Die Datei '%ls' kann nicht in '%ls' wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b8141-114">File '%ls' cannot be restored to '%ls'.</span></span> <span data-ttu-id="b8141-115">Verwenden Sie WITH MOVE, um einen gültigen Speicherort für die Datei zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b8141-115">Use WITH MOVE to identify a valid location for the file.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b8141-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="b8141-116">Explanation</span></span>  
 <span data-ttu-id="b8141-117">Mit dieser allgemeinen Meldung werden die logischen oder physischen Dateinamen der Dateien angegeben, die aufgrund eines Problems mit dem angegebenen Speicherort nicht wiederhergestellt werden konnten.</span><span class="sxs-lookup"><span data-stu-id="b8141-117">This general message identifies the logical or physical file names of files that could not be restored because of a problem with the specified location.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="b8141-118">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="b8141-118">Possible Causes</span></span>  
 <span data-ttu-id="b8141-119">Die folgenden Ursachen sind möglich:</span><span class="sxs-lookup"><span data-stu-id="b8141-119">The possible causes include the following:</span></span>  
  
-   <span data-ttu-id="b8141-120">Möglicherweise müssen Sie auf das angegebene Windows-Verzeichnis zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b8141-120">You might need access to the specified Windows directory.</span></span>  
  
-   <span data-ttu-id="b8141-121">Möglicherweise haben Sie den Pfad falsch eingegeben, oder Sie haben einen Pfad angegeben, der nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b8141-121">You might have mistyped the path or specified a path that does not exist.</span></span>  
  
-   <span data-ttu-id="b8141-122">Der Dateiname wird möglicherweise für eine Datei verwendet, die nicht überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="b8141-122">The file name might be being used by a file that cannot be overwritten.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b8141-123">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="b8141-123">User Action</span></span>  
 <span data-ttu-id="b8141-124">Suchen Sie in den Fehlerprotokollen nach anderen Meldungen, in denen weitere Details angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b8141-124">Look at the error logs for other messages that provide more details.</span></span>  
  
 <span data-ttu-id="b8141-125">Beheben Sie das Problem mit dem angegebenen Speicherort beispielsweise durch das Gewähren von Zugriff, oder verwenden Sie die Option WITH MOVE in Ihrer RESTORE-Anweisung, um die Datei zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="b8141-125">Correct the problem with the specified location, for example, by granting access, or use the WITH MOVE option in your RESTORE statement to relocate the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8141-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b8141-126">See Also</span></span>  
 <span data-ttu-id="b8141-127">[Wiederherstellen einer Datenbank an einem neuen Speicherort &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b8141-127">[Restore a Database to a New Location &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="b8141-128">[Wiederherstellen von Dateien an einem neuen Speicherort &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b8141-128">[Restore Files to a New Location &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span></span>  
 [<span data-ttu-id="b8141-129">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b8141-129">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
