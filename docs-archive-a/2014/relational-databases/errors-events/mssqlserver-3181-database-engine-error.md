---
title: MSSQLSERVER_3181 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3181 (Database Engine error)
ms.assetid: e6d2e716-5263-477c-ad0e-7bcbfef4c1f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f18509d9a18ba8be1f4e40c93bff5abfcae3d69c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618019"
---
# <a name="mssqlserver_3181"></a><span data-ttu-id="7d82d-102">MSSQLSERVER_3181</span><span class="sxs-lookup"><span data-stu-id="7d82d-102">MSSQLSERVER_3181</span></span>
    
## <a name="details"></a><span data-ttu-id="7d82d-103">Details</span><span class="sxs-lookup"><span data-stu-id="7d82d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7d82d-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="7d82d-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="7d82d-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="7d82d-105">Event ID</span></span>|<span data-ttu-id="7d82d-106">3181</span><span class="sxs-lookup"><span data-stu-id="7d82d-106">3181</span></span>|  
|<span data-ttu-id="7d82d-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="7d82d-107">Event Source</span></span>|<span data-ttu-id="7d82d-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7d82d-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7d82d-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="7d82d-109">Component</span></span>|<span data-ttu-id="7d82d-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7d82d-110">SQLEngine</span></span>|  
|<span data-ttu-id="7d82d-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="7d82d-111">Symbolic Name</span></span>|<span data-ttu-id="7d82d-112">LDDB_STORAGE_VERIFY</span><span class="sxs-lookup"><span data-stu-id="7d82d-112">LDDB_STORAGE_VERIFY</span></span>|  
|<span data-ttu-id="7d82d-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="7d82d-113">Message Text</span></span>|<span data-ttu-id="7d82d-114">Beim Wiederherstellen dieser Sicherung können Speicherplatzprobleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="7d82d-114">Attempting to restore this backup may encounter storage space problems.</span></span> <span data-ttu-id="7d82d-115">Nachfolgende Meldungen enthalten weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="7d82d-115">Subsequent messages will provide details.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7d82d-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="7d82d-116">Explanation</span></span>  
 <span data-ttu-id="7d82d-117">Mit der RESTORE VERIFYONLY-Anweisung wird der verfügbare Speicherplatz auf dem Datenträger geprüft, auf dem die Datenbank wiederhergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7d82d-117">The RESTORE VERIFYONLY statement checks the available storage space on the disk to which the database is to be restored.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="7d82d-118">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="7d82d-118">Possible Causes</span></span>  
 <span data-ttu-id="7d82d-119">Möglicherweise reicht der verfügbare Speicherplatz für die Wiederherstellung der zu prüfenden Sicherung nicht aus.</span><span class="sxs-lookup"><span data-stu-id="7d82d-119">The available disk space may be insufficient to restore the backup being verified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7d82d-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="7d82d-120">User Action</span></span>  
 <span data-ttu-id="7d82d-121">Stellen Sie die Sicherung an einem Speicherort mit ausreichendem Speicherplatz wieder her, oder stellen Sie auf dem Datenträger mehr Speicherplatz bereit.</span><span class="sxs-lookup"><span data-stu-id="7d82d-121">Restore the backup to a location with sufficient disk space, or provide more space on the disk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d82d-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d82d-122">See Also</span></span>  
 <span data-ttu-id="7d82d-123">[Wiederherstellen einer Datenbank an einem neuen Speicherort &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7d82d-123">[Restore a Database to a New Location &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="7d82d-124">[Wiederherstellen von Dateien an einem neuen Speicherort &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7d82d-124">[Restore Files to a New Location &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="7d82d-125">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7d82d-125">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="7d82d-126">RESTORE VERIFYONLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7d82d-126">RESTORE VERIFYONLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql)  
  
  
