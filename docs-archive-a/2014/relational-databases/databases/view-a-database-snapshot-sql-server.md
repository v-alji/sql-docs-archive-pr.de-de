---
title: Anzeigen einer Datenbank-Momentaufnahme (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], viewing
- displaying database snapshots
- viewing database snapshots
ms.assetid: 123f19b2-0850-4033-8507-59ebdfb368ee
author: stevestein
ms.author: sstein
ms.openlocfilehash: 92c5c557656e87be562e9d5477f14f66b2c39e7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724754"
---
# <a name="view-a-database-snapshot-sql-server"></a><span data-ttu-id="6708e-102">Anzeigen einer Datenbank-Momentaufnahme (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6708e-102">View a Database Snapshot (SQL Server)</span></span>
  <span data-ttu-id="6708e-103">In diesem Thema wird erläutert, wie eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank-Momentaufnahme mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6708e-103">This topic explains how to view a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database snapshot using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6708e-104">Wenn Sie Datenbank-Momentaufnahmen erstellen, wiederherstellen oder löschen möchten, müssen Sie [!INCLUDE[tsql](../../includes/tsql-md.md)]verwenden.</span><span class="sxs-lookup"><span data-stu-id="6708e-104">To create, revert to, or delete a database snapshot, you must use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="6708e-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="6708e-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6708e-106">**Anzeigen einer Datenbank-Momentaufnahme mit:**</span><span class="sxs-lookup"><span data-stu-id="6708e-106">**To view a database snapshot, using:**</span></span>  
  
     [<span data-ttu-id="6708e-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6708e-107">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6708e-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6708e-108">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6708e-109">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6708e-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="6708e-110">**So zeigen Sie eine Datenbankmomentaufnahme an**</span><span class="sxs-lookup"><span data-stu-id="6708e-110">**To view a database snapshot**</span></span>  
  
1.  <span data-ttu-id="6708e-111">Stellen Sie im Objekt-Explorer eine Verbindung mit der Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] her, und erweitern Sie die Instanz.</span><span class="sxs-lookup"><span data-stu-id="6708e-111">In Object Explorer, connect to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="6708e-112">Erweitern Sie **Datenbanken**.</span><span class="sxs-lookup"><span data-stu-id="6708e-112">Expand **Databases.**</span></span>  
  
3.  <span data-ttu-id="6708e-113">Erweitern Sie **Datenbank-Momentaufnahmen**, und wählen Sie die gewünschte Momentaufnahme aus.</span><span class="sxs-lookup"><span data-stu-id="6708e-113">Expand **Database Snapshots**, and select the snapshot you want to view.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6708e-114">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6708e-114">Using Transact-SQL</span></span>  
 <span data-ttu-id="6708e-115">**So zeigen Sie eine Datenbankmomentaufnahme an**</span><span class="sxs-lookup"><span data-stu-id="6708e-115">**To view a database snapshot**</span></span>  
  
1.  <span data-ttu-id="6708e-116">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="6708e-116">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6708e-117">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="6708e-117">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6708e-118">Zum Anzeigen der Datenbank-Momentaufnahmen der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz fragen Sie die Spalte **source_database_id** der [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) -Katalogsicht nach Nicht-NULL-Werten ab.</span><span class="sxs-lookup"><span data-stu-id="6708e-118">To list the database snapshots of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], query the **source_database_id** column of the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view for non-NULL values.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="6708e-119">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="6708e-119">Related Tasks</span></span>  
  
-   [<span data-ttu-id="6708e-120">Erstellen einer Datenbankmomentaufnahme &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6708e-120">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="6708e-121">Wiederherstellen einer Datenbank zu einer Datenbank-Momentaufnahme</span><span class="sxs-lookup"><span data-stu-id="6708e-121">Revert a Database to a Database Snapshot</span></span>](revert-a-database-to-a-database-snapshot.md)  
  
-   [<span data-ttu-id="6708e-122">Löschen einer Datenbankmomentaufnahme &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6708e-122">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](drop-a-database-snapshot-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="6708e-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6708e-123">See Also</span></span>  
 [<span data-ttu-id="6708e-124">Datenbank-Momentaufnahmen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6708e-124">Database Snapshots &#40;SQL Server&#41;</span></span>](database-snapshots-sql-server.md)  
  
  
