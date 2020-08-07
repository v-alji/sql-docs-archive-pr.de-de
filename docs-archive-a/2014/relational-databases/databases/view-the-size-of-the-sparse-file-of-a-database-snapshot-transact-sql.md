---
title: Anzeigen der Größe der Datei mit geringer Dichte einer Datenbank-Momentaufnahme (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- snapshots [SQL Server database snapshots], sparse files
- space [SQL Server], sparse files
- sparse files [SQL Server]
- size [SQL Server], sparse files
- maximum sparse file size
- database snapshots [SQL Server], sparse files
- space [SQL Server], database snapshots
ms.assetid: 1867c5f8-d57c-46d3-933d-3642ab0a8e24
author: stevestein
ms.author: sstein
ms.openlocfilehash: 424399b9915c8e7e26e1076fd2e553aafe06fcf0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720002"
---
# <a name="view-the-size-of-the-sparse-file-of-a-database-snapshot-transact-sql"></a><span data-ttu-id="898a5-102">Anzeigen der Größe der Datei mit geringer Dichte einer Datenbank-Momentaufnahme (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="898a5-102">View the Size of the Sparse File of a Database Snapshot (Transact-SQL)</span></span>
  <span data-ttu-id="898a5-103">In diesem Thema wird beschrieben, wie Sie mit [!INCLUDE[tsql](../../includes/tsql-md.md)] überprüfen, ob eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbankdatei eine Sparsedatei ist, und wie Sie die tatsächliche und maximale Größe ermitteln.</span><span class="sxs-lookup"><span data-stu-id="898a5-103">This topic describes how to use [!INCLUDE[tsql](../../includes/tsql-md.md)] to verify that a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database file is a sparse file and to find out its actual and maximum sizes.</span></span> <span data-ttu-id="898a5-104">Dateien mit geringer Dichte, die in Verbindung mit dem NTFS-Dateisystem vorkommen, werden von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbankmomentaufnahmen verwendet.</span><span class="sxs-lookup"><span data-stu-id="898a5-104">Sparse files, which are a feature of the NTFS file system, are used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database snapshots.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="898a5-105">Beim Erstellen von Datenbankmomentaufnahmen werden Sparsedateien mithilfe der Dateinamen in der CREATE DATABASE-Anweisung erstellt.</span><span class="sxs-lookup"><span data-stu-id="898a5-105">During database snapshot creation, sparse files are created by using the file names in the CREATE DATABASE statement.</span></span> <span data-ttu-id="898a5-106">Diese Dateinamen werden in der Spalte **physical_name** in **sys.master_files** gespeichert.</span><span class="sxs-lookup"><span data-stu-id="898a5-106">These file names are stored in **sys.master_files** in the **physical_name** column.</span></span> <span data-ttu-id="898a5-107">In **sys.database_files** (sowohl in der Quelldatenbank wie auch in einer Momentaufnahme) enthält die Spalte **physical_name** immer die Namen der Quelldatenbankdateien.</span><span class="sxs-lookup"><span data-stu-id="898a5-107">In **sys.database_files** (whether in the source database or in a snapshot), the **physical_name** column always contains the names of the source database files.</span></span>  
  
## <a name="verify-that-a-database-file-is-a-sparse-file"></a><span data-ttu-id="898a5-108">Überprüfen, ob eine Datenbankdatei eine Datei mit geringer Dichte ist</span><span class="sxs-lookup"><span data-stu-id="898a5-108">Verify that a Database File is a Sparse File</span></span>  
  
1.  <span data-ttu-id="898a5-109">Auf der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="898a5-109">On the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
     <span data-ttu-id="898a5-110">Wählen Sie entweder in der Datenbank-Momentaufnahme unter **sys.database_files** oder in **sys.master_files** die Spalte **is_sparse**aus.</span><span class="sxs-lookup"><span data-stu-id="898a5-110">Select the **is_sparse** column from either **sys.database_files** in the database snapshot or from **sys.master_files**.</span></span> <span data-ttu-id="898a5-111">Der Wert gibt wie folgt an, ob die Datei eine Sparsedatei ist:</span><span class="sxs-lookup"><span data-stu-id="898a5-111">The value indicates whether the file is a sparse file, as follows:</span></span>  
  
     <span data-ttu-id="898a5-112">1 = Die Datei ist eine Sparsedatei.</span><span class="sxs-lookup"><span data-stu-id="898a5-112">1 = File is a sparse file.</span></span>  
  
     <span data-ttu-id="898a5-113">0 = Die Datei ist keine Sparsedatei.</span><span class="sxs-lookup"><span data-stu-id="898a5-113">0 = File is not a sparse file.</span></span>  
  
## <a name="find-out-the-actual-size-of-a-sparse-file"></a><span data-ttu-id="898a5-114">Ermitteln der tatsächlichen Größe einer Datei mit geringer Dichte</span><span class="sxs-lookup"><span data-stu-id="898a5-114">Find Out the Actual Size of a Sparse File</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="898a5-115">Sparsedateien wachsen in 64-KB-Schritten, weshalb die Größe einer Sparsedatei auf dem Datenträger immer einem Vielfachen von 64 KB entspricht.</span><span class="sxs-lookup"><span data-stu-id="898a5-115">Sparse files grow in 64-kilobyte (KB) increments; thus, the size of a sparse file on disk is always a multiple of 64 KB.</span></span>  
  
 <span data-ttu-id="898a5-116">Um die Anzahl der Bytes anzuzeigen, die die einzelnen sparsedateien einer Momentaufnahme zurzeit auf dem Datenträger verwenden, Fragen Sie die **size_on_disk_bytes** Spalte der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dynamischen Verwaltungs Sicht [sys. dm_io_virtual_file_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-io-virtual-file-stats-transact-sql) ab.</span><span class="sxs-lookup"><span data-stu-id="898a5-116">To view the number of bytes that each sparse file of a snapshot is currently using on disk, query the **size_on_disk_bytes** column of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][sys.dm_io_virtual_file_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-io-virtual-file-stats-transact-sql) dynamic management view.</span></span>  
  
 <span data-ttu-id="898a5-117">Zum Anzeigen des Speicherplatzes, der durch eine Sparsedatei in Anspruch genommen wird, klicken Sie in Microsoft Windows mit der rechten Maustaste auf **Eigenschaften**, und lesen Sie den Wert unter **Größe auf Datenträger** ab.</span><span class="sxs-lookup"><span data-stu-id="898a5-117">To view the disk space used by a sparse file, right-click the file in Microsoft Windows, click **Properties**, and look at the **Size on disk** value.</span></span>  
  
## <a name="find-out-the-maximum-size-of-a-sparse-file"></a><span data-ttu-id="898a5-118">Ermitteln der maximalen Größe einer Datei mit geringer Dichte</span><span class="sxs-lookup"><span data-stu-id="898a5-118">Find Out the Maximum Size of a Sparse File</span></span>  
 <span data-ttu-id="898a5-119">Eine Datei mit geringer Dichte kann maximal die Größe der Quelldatenbankdatei erreichen, die zum Zeitpunkt der Momentaufnahmeerstellung festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="898a5-119">The maximum size to which a sparse can grow is the size of the corresponding source database file at the time of the snapshot creation.</span></span> <span data-ttu-id="898a5-120">Zur Ermittlung dieser Größe stehen Ihnen die folgenden Alternativen zur Auswahl:</span><span class="sxs-lookup"><span data-stu-id="898a5-120">To learn this size, you can use one of the following alternatives:</span></span>  
  
-   <span data-ttu-id="898a5-121">Verwenden der Windows-Eingabeaufforderung:</span><span class="sxs-lookup"><span data-stu-id="898a5-121">Using Windows Command Prompt:</span></span>  
  
    1.  <span data-ttu-id="898a5-122">Verwenden Sie die **dir** -Befehle an der Eingabeaufforderung von Windows.</span><span class="sxs-lookup"><span data-stu-id="898a5-122">Use Windows **dir** commands.</span></span>  
  
    2.  <span data-ttu-id="898a5-123">Wählen Sie die Datei mit geringer Größe aus, öffnen Sie in Windows das Dialogfeld **Eigenschaften** der Datei, und lesen Sie den Wert für die **Größe** ab.</span><span class="sxs-lookup"><span data-stu-id="898a5-123">Select the sparse file, open the file **Properties** dialog box in Windows, and look at the **Size** value.</span></span>  
  
-   <span data-ttu-id="898a5-124">Auf der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="898a5-124">On the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
     <span data-ttu-id="898a5-125">Wählen Sie entweder in **sys.database_files** in der Datenbank-Momentaufnahme oder in **sys.master_files** die **size**-Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="898a5-125">Select the **size** column from either **sys.database_files** in the database snapshot or from **sys.master_files**.</span></span> <span data-ttu-id="898a5-126">Der Wert in der **size** -Spalte gibt den maximal durch eine Momentaufnahme verwendbaren Speicherplatz in SQL-Seiten an. Dieser Wert entspricht dem Feld **Größe** in Windows. Der einzige Unterschied besteht darin, dass hierbei die Anzahl der SQL-Seiten in der Datei angegeben wird. Die Größe in Bytes kann daraus wie folgt errechnet werden:</span><span class="sxs-lookup"><span data-stu-id="898a5-126">The value of **size** column reflects the maximum space, in SQL pages, that the snapshot can ever use; this value is equivalent to the Windows **Size** field, except that it is represented in terms of the number of SQL pages in the file; the size in bytes is:</span></span>  
  
     <span data-ttu-id="898a5-127">( *Seitenanzahl* \* 8192)</span><span class="sxs-lookup"><span data-stu-id="898a5-127">( *number_of_pages* \* 8192)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="898a5-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="898a5-128">See Also</span></span>  
 <span data-ttu-id="898a5-129">[Datenbank-Momentaufnahmen &#40;SQL Server&#41;](database-snapshots-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="898a5-129">[Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md) </span></span>  
 <span data-ttu-id="898a5-130">[sys.fn_virtualfilestats &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-virtualfilestats-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="898a5-130">[sys.fn_virtualfilestats &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-virtualfilestats-transact-sql) </span></span>  
 <span data-ttu-id="898a5-131">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="898a5-131">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 [<span data-ttu-id="898a5-132">sys.master_files &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="898a5-132">sys.master_files &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql)  
  
  
