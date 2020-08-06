---
title: Datenbankeigenschaften (Seite Dateigruppen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.filegroups.f1
ms.assetid: 8d06e859-73dd-4019-b6e8-99c5c5297697
author: stevestein
ms.author: sstein
ms.openlocfilehash: d0546a17491ed5d3b36890a605c5faa922c24fe6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617100"
---
# <a name="database-properties-filegroups-page"></a><span data-ttu-id="b3622-102">Datenbankeigenschaften (Seite Dateigruppen)</span><span class="sxs-lookup"><span data-stu-id="b3622-102">Database Properties (Filegroups Page)</span></span>
  <span data-ttu-id="b3622-103">Mithilfe dieser Seite können Sie Dateigruppen anzeigen oder der ausgewählten Datenbank eine neue Dateigruppe hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b3622-103">Use this page to view the filegroups or add a new filegroup to the selected database.</span></span> <span data-ttu-id="b3622-104">Dateigruppentypen werden in *Zeilen* dateigruppen, FILESTREAM-Datendateigruppen und speicheroptimierte Dateigruppen unterteilt.</span><span class="sxs-lookup"><span data-stu-id="b3622-104">Filegroup types are separated into *row* filegroups, FILESTREAM data, and memory-optimized filegroups.</span></span>  
  
 <span data-ttu-id="b3622-105">Zeilendateigruppen enthalten reguläre Daten und Protokolldateien.</span><span class="sxs-lookup"><span data-stu-id="b3622-105">Row filegroups contain regular data and log files.</span></span> <span data-ttu-id="b3622-106">FILESTREAM-Datendateigruppen enthalten FILESTREAM-Datendateien.</span><span class="sxs-lookup"><span data-stu-id="b3622-106">FILESTREAM data filegroups contain FILESTREAM data files.</span></span> <span data-ttu-id="b3622-107">Diese Datendateien speichern Informationen darüber, wie BLOB (Binary Large Object)-Daten im Dateisystem gespeichert werden, wenn Sie die FILESTREAM-Speicherung verwenden.</span><span class="sxs-lookup"><span data-stu-id="b3622-107">These data files store information about how binary large object (BLOB) data is stored on the file system when you are using FILESTREAM storage.</span></span> <span data-ttu-id="b3622-108">Die Optionen sind für beide Typen von Dateigruppen gleich.</span><span class="sxs-lookup"><span data-stu-id="b3622-108">The options are the same for both types of filegroups.</span></span>  
  
 <span data-ttu-id="b3622-109">Wenn FILESTREAM nicht aktiviert ist, ist der Abschnitt **Filestream** nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b3622-109">If FILESTREAM is not enabled, the **Filestream** section will not be available.</span></span> <span data-ttu-id="b3622-110">Die FILESTREAM-Speicherung kann über [Servereigenschaften (Seite „Erweitert“)](../../database-engine/configure-windows/server-properties-advanced-page.md)aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="b3622-110">You can enable FILESTREAM storage by using [Server Properties (Advanced Page)](../../database-engine/configure-windows/server-properties-advanced-page.md).</span></span>  
  
 <span data-ttu-id="b3622-111">Weitere Informationen dazu, wie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Zeilendateigruppen verwendet, finden Sie unter [Datenbankdateien und Dateigruppen](database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="b3622-111">For information about how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses row filegroups, see [Database Files and Filegroups](database-files-and-filegroups.md).</span></span> <span data-ttu-id="b3622-112">Weitere Informationen über FILESTREAM-Daten und -Dateigruppen finden Sie unter [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b3622-112">For more information about FILESTREAM data and filegroups, see [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span></span>  
  
 <span data-ttu-id="b3622-113">Speicheroptimierte Dateigruppen sind erforderlich, damit eine Datenbank mindestens eine speicheroptimierte Tabelle enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="b3622-113">Memory-optimized file groups are required for a database to contain one or more memory-optimized tables.</span></span>  
  
## <a name="row-and-filestream-data-filegroup-options"></a><span data-ttu-id="b3622-114">Optionen für Zeilen- und FILESTREAM-Datendateigruppen</span><span class="sxs-lookup"><span data-stu-id="b3622-114">Row and FILESTREAM Data Filegroup Options</span></span>  
 <span data-ttu-id="b3622-115">**Name**</span><span class="sxs-lookup"><span data-stu-id="b3622-115">**Name**</span></span>  
 <span data-ttu-id="b3622-116">Geben Sie den Namen der Dateigruppe ein.</span><span class="sxs-lookup"><span data-stu-id="b3622-116">Enter the name of the filegroup.</span></span>  
  
 <span data-ttu-id="b3622-117">**Dateien**</span><span class="sxs-lookup"><span data-stu-id="b3622-117">**Files**</span></span>  
 <span data-ttu-id="b3622-118">Zeigt die Anzahl der Dateien in der Dateigruppe an.</span><span class="sxs-lookup"><span data-stu-id="b3622-118">Displays the count of files in the filegroup.</span></span>  
  
 <span data-ttu-id="b3622-119">**Schreibgeschützt**</span><span class="sxs-lookup"><span data-stu-id="b3622-119">**Read-only**</span></span>  
 <span data-ttu-id="b3622-120">Wählen Sie diese Option aus, um für die Dateigruppe den schreibgeschützten Modus festzulegen.</span><span class="sxs-lookup"><span data-stu-id="b3622-120">Select to set the filegroup to a read-only status.</span></span>  
  
 <span data-ttu-id="b3622-121">**Standard**</span><span class="sxs-lookup"><span data-stu-id="b3622-121">**Default**</span></span>  
 <span data-ttu-id="b3622-122">Wählen Sie diese Option aus, um diese Dateigruppe zur Standarddateigruppe zu machen.</span><span class="sxs-lookup"><span data-stu-id="b3622-122">Select to make this filegroup the default filegroup.</span></span> <span data-ttu-id="b3622-123">Sie können eine Standarddateigruppe für Zeilen und eine Standarddateigruppe für FILESTREAM-Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="b3622-123">You can have one default filegroup for rows and one default filegroup for FILESTREAM data.</span></span>  
  
 <span data-ttu-id="b3622-124">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="b3622-124">**Add**</span></span>  
 <span data-ttu-id="b3622-125">Fügt dem Raster mit den Dateigruppen für die Datenbank eine neue leere Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3622-125">Adds a new blank row to the grid listing filegroups for the database.</span></span>  
  
 <span data-ttu-id="b3622-126">**Remove**</span><span class="sxs-lookup"><span data-stu-id="b3622-126">**Remove**</span></span>  
 <span data-ttu-id="b3622-127">Entfernt die ausgewählte Dateigruppenzeile aus dem Raster.</span><span class="sxs-lookup"><span data-stu-id="b3622-127">Removes the selected filegroup row from the grid.</span></span>  
  
## <a name="memory-optimized-data-filegroup-options"></a><span data-ttu-id="b3622-128">Optionen für speicheroptimierte Datendateigruppen</span><span class="sxs-lookup"><span data-stu-id="b3622-128">Memory-Optimized Data Filegroup Options</span></span>  
 <span data-ttu-id="b3622-129">**Name**</span><span class="sxs-lookup"><span data-stu-id="b3622-129">**Name**</span></span>  
 <span data-ttu-id="b3622-130">Geben Sie den Namen der speicheroptimierten Dateigruppe ein.</span><span class="sxs-lookup"><span data-stu-id="b3622-130">Enter the name of the memory-optimized filegroup.</span></span>  
  
 <span data-ttu-id="b3622-131">**FILESTREAM-Dateien**</span><span class="sxs-lookup"><span data-stu-id="b3622-131">**Filestream Files**</span></span>  
 <span data-ttu-id="b3622-132">Zeigt die Anzahl der Dateien (Container) in der speicheroptimierten Datendateigruppe an.</span><span class="sxs-lookup"><span data-stu-id="b3622-132">Displays the number of files (containers) in the memory-optimized data filegroup.</span></span> <span data-ttu-id="b3622-133">Sie können Container auf der Seite **Dateien** hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b3622-133">You can add containers in the **Files** page.</span></span>  
  
 <span data-ttu-id="b3622-134">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="b3622-134">**Add**</span></span>  
 <span data-ttu-id="b3622-135">Fügt dem Raster mit den Dateigruppen für die Datenbank eine neue leere Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3622-135">Adds a new blank row to the grid listing filegroups for the database.</span></span>  
  
 <span data-ttu-id="b3622-136">**Remove**</span><span class="sxs-lookup"><span data-stu-id="b3622-136">**Remove**</span></span>  
 <span data-ttu-id="b3622-137">Entfernt die ausgewählte Dateigruppenzeile aus dem Raster.</span><span class="sxs-lookup"><span data-stu-id="b3622-137">Removes the selected filegroup row from the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3622-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b3622-138">See Also</span></span>  
 <span data-ttu-id="b3622-139">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b3622-139">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="b3622-140">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b3622-140">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
