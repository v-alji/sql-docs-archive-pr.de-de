---
title: MSSQLSERVER_3176 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3176 (Database Engine error)
ms.assetid: 4be24c64-2d52-4cb4-b4d7-36efbe4555b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 64e1a836995fe8738bb5c2ff0cb4de10d84d1f29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618020"
---
# <a name="mssqlserver_3176"></a><span data-ttu-id="0ef49-102">MSSQLSERVER_3176</span><span class="sxs-lookup"><span data-stu-id="0ef49-102">MSSQLSERVER_3176</span></span>
    
## <a name="details"></a><span data-ttu-id="0ef49-103">Details</span><span class="sxs-lookup"><span data-stu-id="0ef49-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0ef49-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="0ef49-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="0ef49-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="0ef49-105">Event ID</span></span>|<span data-ttu-id="0ef49-106">3176</span><span class="sxs-lookup"><span data-stu-id="0ef49-106">3176</span></span>|  
|<span data-ttu-id="0ef49-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="0ef49-107">Event Source</span></span>|<span data-ttu-id="0ef49-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0ef49-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0ef49-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="0ef49-109">Component</span></span>|<span data-ttu-id="0ef49-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0ef49-110">SQLEngine</span></span>|  
|<span data-ttu-id="0ef49-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="0ef49-111">Symbolic Name</span></span>|<span data-ttu-id="0ef49-112">LDDB_FILE_CLAIM</span><span class="sxs-lookup"><span data-stu-id="0ef49-112">LDDB_FILE_CLAIM</span></span>|  
|<span data-ttu-id="0ef49-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="0ef49-113">Message Text</span></span>|<span data-ttu-id="0ef49-114">Die Datei '%ls' wird von '%ls'(%d) und '%ls'(%d) beansprucht.</span><span class="sxs-lookup"><span data-stu-id="0ef49-114">File '%ls' is claimed by '%ls'(%d) and '%ls'(%d).</span></span> <span data-ttu-id="0ef49-115">Mithilfe der WITH MOVE-Klausel kann nach einer oder mehreren Dateien gesucht werden.</span><span class="sxs-lookup"><span data-stu-id="0ef49-115">The WITH MOVE clause can be used to relocate one or more files.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0ef49-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="0ef49-116">Explanation</span></span>  
 <span data-ttu-id="0ef49-117">Es wird versucht, eine Datei für mehr als einen Zweck zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0ef49-117">Attempting to use a file for more than one purpose.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="0ef49-118">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="0ef49-118">Possible Causes</span></span>  
 <span data-ttu-id="0ef49-119">Der Dateiname wird bereits von einer anderen Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="0ef49-119">Another database is already using the file name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0ef49-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="0ef49-120">User Action</span></span>  
 <span data-ttu-id="0ef49-121">Stellen Sie die Datenbankdateien an einem anderen Speicherort wieder her.</span><span class="sxs-lookup"><span data-stu-id="0ef49-121">Restore the database files to a different location.</span></span> <span data-ttu-id="0ef49-122">Verwenden Sie in einer RESTORE-Anweisung eine WITH MOVE-Klausel, um die einzelnen Dateien zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="0ef49-122">In a RESTORE statement, use a WITH MOVE clause to move each file.</span></span> <span data-ttu-id="0ef49-123">Ändern Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] auf der Seite Optionen die Dateispeicherorte im Raster **Datenbankdateien wiederherstellen als** des Dialogfelds **Datenbank wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="0ef49-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], change the file locations in the **Restore the database files as** grid of the **Restore Database Options** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ef49-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0ef49-124">See Also</span></span>  
 <span data-ttu-id="0ef49-125">[Wiederherstellen einer Datenbank an einem neuen Speicherort &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0ef49-125">[Restore a Database to a New Location &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="0ef49-126">[Wiederherstellen von Dateien an einem neuen Speicherort &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0ef49-126">[Restore Files to a New Location &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span></span>  
 [<span data-ttu-id="0ef49-127">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0ef49-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
