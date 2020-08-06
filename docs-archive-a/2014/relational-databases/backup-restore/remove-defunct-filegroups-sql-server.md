---
title: Entfernen von veralteten Dateigruppen (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- piecemeal restores [SQL Server], defunct filegroups
- defunct filegroups
- restoring filegroups [SQL Server]
- deferred transactions
- filegroups [SQL Server], defunct
- unrestored filegroups
ms.assetid: 055f9c6a-5c18-4942-98e7-ec918f0ff975
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a2bcba095d668c5c1ab317269a18af4dc996f63b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721517"
---
# <a name="remove-defunct-filegroups-sql-server"></a><span data-ttu-id="3b026-102">Entfernen von veralteten Dateigruppen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3b026-102">Remove Defunct Filegroups (SQL Server)</span></span>
  <span data-ttu-id="3b026-103">In diesem Thema wird beschrieben, wie veraltete Dateigruppen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="3b026-103">This topic describes how to remove defunct filegroups in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="3b026-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="3b026-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3b026-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="3b026-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3b026-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="3b026-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="3b026-107">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="3b026-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="3b026-108">Security</span><span class="sxs-lookup"><span data-stu-id="3b026-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3b026-109">**So entfernen Sie veraltete Dateigruppen mit**</span><span class="sxs-lookup"><span data-stu-id="3b026-109">**To remove defunct filegroups, using:**</span></span>  
  
     [<span data-ttu-id="3b026-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3b026-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3b026-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3b026-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3b026-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="3b026-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3b026-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="3b026-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="3b026-114">Dieses Thema ist nur für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken relevant, die mehrere Dateien oder Dateigruppen enthalten, und unter dem einfachen Wiederherstellungsmodell nur für schreibgeschützte Dateigruppen.</span><span class="sxs-lookup"><span data-stu-id="3b026-114">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases that contain multiple files or filegroups; and, under the simple model, only for read-only filegroups.</span></span>  
  
-   <span data-ttu-id="3b026-115">Alle Dateien in einer Dateigruppe erhalten den Status "defunct", wenn eine Offlinedateigruppe entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="3b026-115">All files in a filegroup become defunct when an offline filegroup is removed.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="3b026-116">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="3b026-116">Recommendations</span></span>  
  
-   <span data-ttu-id="3b026-117">Wenn eine nicht wiederhergestellte Dateigruppe auch zu keinem späteren Zeitpunkt mehr wiederhergestellt werden soll, können Sie sie als *veraltet* aus der Datenbank entfernen.</span><span class="sxs-lookup"><span data-stu-id="3b026-117">If an unrestored filegroup will never have to be restored, you can make the filegroup *defunct* by removing it from the database.</span></span> <span data-ttu-id="3b026-118">Die veraltete Dateigruppe kann zu keinem Zeitpunkt in dieser Datenbank wiederhergestellt werden, die zugehörigen Metadaten bleiben jedoch erhalten.</span><span class="sxs-lookup"><span data-stu-id="3b026-118">The defunct filegroup can never be restored to this database, but its metadata remains.</span></span> <span data-ttu-id="3b026-119">Nachdem die Dateigruppe veraltet ist, d. h. außer Kraft gesetzt wurde, kann die Datenbank neu gestartet werden, und durch die Wiederherstellung wird die Datenbank über alle wiederhergestellten Dateigruppen hinweg konsistent.</span><span class="sxs-lookup"><span data-stu-id="3b026-119">After the filegroup is defunct, the database can be restarted, and recovery will make the database consistent across the restored filegroups.</span></span>  
  
     <span data-ttu-id="3b026-120">Eine Dateigruppe außer Kraft zu setzen, stellt eine Option zum Auflösen verzögerter Transaktionen dar, die durch eine Offline-Dateigruppe ausgelöst wurden, die nicht mehr in der Datenbank enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="3b026-120">For example, making a filegroup defunct is an option for resolving deferred transactions that were caused by an offline filegroup that you no longer want in the database.</span></span> <span data-ttu-id="3b026-121">Transaktionen, die sich verzögert haben, weil eine Dateigruppe offline ist, befinden sich, nachdem eine Dateigruppe außer Kraft gesetzt wird, nicht mehr im Verzögerungsmodus.</span><span class="sxs-lookup"><span data-stu-id="3b026-121">Transactions that were deferred because the filegroup was offline are moved out of the deferred state after the filegroup becomes defunct.</span></span> <span data-ttu-id="3b026-122">Weitere Informationen finden Sie unter [Markierte Transaktionen &#40;SQL Server&#41;](deferred-transactions-sql-server.md)entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="3b026-122">For more information, see [Deferred Transactions &#40;SQL Server&#41;](deferred-transactions-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3b026-123">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3b026-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3b026-124">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="3b026-124">Permissions</span></span>  
 <span data-ttu-id="3b026-125">Erfordert die ALTER-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="3b026-125">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3b026-126">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3b026-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-defunct-filegroups"></a><span data-ttu-id="3b026-127">So entfernen Sie veraltete Dateigruppen</span><span class="sxs-lookup"><span data-stu-id="3b026-127">To remove defunct filegroups</span></span>  
  
1.  <span data-ttu-id="3b026-128">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="3b026-128">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="3b026-129">Erweitern Sie **Datenbanken**, klicken Sie mit der rechten Maustaste auf die Datenbank, aus der Sie die Datei löschen möchten, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="3b026-129">Expand **Databases**, right-click the database from which to delete the file, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="3b026-130">Wählen Sie die Seite **Dateien** aus.</span><span class="sxs-lookup"><span data-stu-id="3b026-130">Select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="3b026-131">Wählen Sie im Raster **Datenbankdateien** die zu löschende Datei aus, klicken Sie auf **Entfernen**und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b026-131">In the **Database files** grid, select the files to delete, click **Remove**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="3b026-132">Wählen Sie die Seite **Dateigruppen** aus.</span><span class="sxs-lookup"><span data-stu-id="3b026-132">Select the **Filegroups** page.</span></span>  
  
6.  <span data-ttu-id="3b026-133">Wählen Sie im Raster **Zeilen** die zu löschende Dateigruppe aus, klicken Sie auf **Entfernen**und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b026-133">In the **Rows** grid, select the filegroup to delete, click **Remove**, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3b026-134">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3b026-134">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-defunct-filegroups"></a><span data-ttu-id="3b026-135">So entfernen Sie veraltete Dateigruppen</span><span class="sxs-lookup"><span data-stu-id="3b026-135">To remove defunct filegroups</span></span>  
  
1.  <span data-ttu-id="3b026-136">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="3b026-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3b026-137">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="3b026-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3b026-138">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3b026-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="3b026-139">(**Hinweis:** Bei diesem Beispiel wird vorausgesetzt, dass die Dateien und die Dateigruppen bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="3b026-139">(**Note:** This example assumes that the files and filegroup already exist.</span></span> <span data-ttu-id="3b026-140">Weitere Informationen zum Erstellen dieser Objekte finden Sie in Beispiel B im Thema [ALTER DATABASE-Optionen Datei und Dateigruppe](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).) Im ersten Beispiel werden die `test1dat3`- und `test1dat4`-Dateien aus der veralteten Dateigruppe unter Verwendung der `ALTER DATABASE`-Anweisung mit der `REMOVE FILE`-Klausel entfernt.</span><span class="sxs-lookup"><span data-stu-id="3b026-140">To create these objects, see example B in the [ALTER DATABASE File and Filegroup Options](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) topic.) The first example removes the `test1dat3` and `test1dat4` files from the defunct filegroup by using the `ALTER DATABASE` statement with the `REMOVE FILE` clause.</span></span> <span data-ttu-id="3b026-141">Im zweiten Beispiel wird die veraltete Dateigruppe `Test1FG1`mithilfe der `REMOVE FILEGROUP` -Klausel entfernt.</span><span class="sxs-lookup"><span data-stu-id="3b026-141">The second example removes the defunct filegroup `Test1FG1`by using the `REMOVE FILEGROUP` clause.</span></span>  
  
```sql  
USE master;  
GO  
ALTER DATABASE AdventureWorks2012  
REMOVE FILE test1dat3 ;  
ALTER DATABASE AdventureWorks2012  
REMOVE FILE test1dat4 ;  
GO  
  
```  
  
```sql  
USE master;  
GO  
ALTER DATABASE AdventureWorks2012  
REMOVE FILEGROUP Test1FG1 ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="3b026-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3b026-142">See Also</span></span>  
 <span data-ttu-id="3b026-143">[ALTER DATABASE-Optionen Datei und Dateigruppe &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) </span><span class="sxs-lookup"><span data-stu-id="3b026-143">[ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) </span></span>  
 <span data-ttu-id="3b026-144">[Markierte Transaktionen &#40;SQL Server&#41;](deferred-transactions-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3b026-144">[Deferred Transactions &#40;SQL Server&#41;](deferred-transactions-sql-server.md) </span></span>  
 <span data-ttu-id="3b026-145">[Dateiwiederherstellungen &#40;vollständiges Wiederherstellungsmodell&#41;](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="3b026-145">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="3b026-146">[Dateiwiederherstellungen &#40;einfaches Wiederherstellungsmodell&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="3b026-146">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="3b026-147">[Onlinewiederherstellungen &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3b026-147">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="3b026-148">[Wiederherstellung von Seiten &#40;SQL Server&#41;](restore-pages-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3b026-148">[Restore Pages &#40;SQL Server&#41;](restore-pages-sql-server.md) </span></span>  
 [<span data-ttu-id="3b026-149">Schrittweise Wiederherstellungen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3b026-149">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
