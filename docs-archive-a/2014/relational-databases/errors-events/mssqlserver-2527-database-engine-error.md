---
title: MSSQLSERVER_2527 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2527 (Database Engine error)
ms.assetid: 1cef90ef-9c39-44e6-bc7f-316c8f53c10c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 900707634a016ecfd29f9f676e68b4d2f557ccea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616085"
---
# <a name="mssqlserver_2527"></a><span data-ttu-id="b11a7-102">MSSQLSERVER_2527</span><span class="sxs-lookup"><span data-stu-id="b11a7-102">MSSQLSERVER_2527</span></span>
    
## <a name="details"></a><span data-ttu-id="b11a7-103">Details</span><span class="sxs-lookup"><span data-stu-id="b11a7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b11a7-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="b11a7-104">Product Name</span></span>|<span data-ttu-id="b11a7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b11a7-105">SQL Server</span></span>|  
|<span data-ttu-id="b11a7-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b11a7-106">Event ID</span></span>|<span data-ttu-id="b11a7-107">2527</span><span class="sxs-lookup"><span data-stu-id="b11a7-107">2527</span></span>|  
|<span data-ttu-id="b11a7-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="b11a7-108">Event Source</span></span>|<span data-ttu-id="b11a7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b11a7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b11a7-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="b11a7-110">Component</span></span>|<span data-ttu-id="b11a7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b11a7-111">SQLEngine</span></span>|  
|<span data-ttu-id="b11a7-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="b11a7-112">Symbolic Name</span></span>|<span data-ttu-id="b11a7-113">DBCC_INDEX_FILEGROUP_IS_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="b11a7-113">DBCC_INDEX_FILEGROUP_IS_OFFLINE</span></span>|  
|<span data-ttu-id="b11a7-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="b11a7-114">Message Text</span></span>|<span data-ttu-id="b11a7-115">Der I_NAME-Index der O_NAME-Tabelle kann nicht bearbeitet werden, da die Dateigruppe F_NAME offline ist.</span><span class="sxs-lookup"><span data-stu-id="b11a7-115">Unable to process index I_NAME of table O_NAME because filegroup F_NAME is offline.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b11a7-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="b11a7-116">Explanation</span></span>  
 <span data-ttu-id="b11a7-117">Diese Informationsmeldung gibt an, dass der Index nicht überprüft werden kann, da eine der Dateigruppen, die die Daten für den Index speichert, offline ist.</span><span class="sxs-lookup"><span data-stu-id="b11a7-117">This informational message indicates that the index cannot be checked because one of the filegroups that stores data for the index is offline.</span></span> <span data-ttu-id="b11a7-118">Der Status der Dateien in einer Dateigruppe legt die Verfügbarkeit der gesamten Dateigruppe fest.</span><span class="sxs-lookup"><span data-stu-id="b11a7-118">The state of the files in a filegroup determines the availability of the whole filegroup.</span></span> <span data-ttu-id="b11a7-119">Damit eine Dateigruppe verfügbar ist, müssen alle Dateien in der Dateigruppe online sein.</span><span class="sxs-lookup"><span data-stu-id="b11a7-119">For a filegroup to be available, all files within the filegroup must be online.</span></span> <span data-ttu-id="b11a7-120">Wenn keine weiteren Probleme vorhanden sind, werden alle anderen Indizes des gleichen Objekts überprüft.</span><span class="sxs-lookup"><span data-stu-id="b11a7-120">If there are no other problems, all other indexes of the same object will be checked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b11a7-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="b11a7-121">User Action</span></span>  
 <span data-ttu-id="b11a7-122">Wenn Sie den Status der Dateien für die angegebene Dateigruppe anzeigen möchten, verwenden Sie die **sys.database_files**- oder **sys.master_files**-Katalogsicht.</span><span class="sxs-lookup"><span data-stu-id="b11a7-122">To view the state of the files for the specified filegroup, query either the **sys.database_files** or **sys.master_files** catalog view.</span></span>  
  
 <span data-ttu-id="b11a7-123">Stellen Sie die Offlinedatei aus einer Sicherung wieder her.</span><span class="sxs-lookup"><span data-stu-id="b11a7-123">Restore the offline file from a backup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b11a7-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b11a7-124">See Also</span></span>  
 <span data-ttu-id="b11a7-125">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b11a7-125">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 <span data-ttu-id="b11a7-126">[sys. master_files &#40;Transact-SQL-&#41;](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b11a7-126">[sys.master_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) </span></span>  
 [<span data-ttu-id="b11a7-127">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b11a7-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
