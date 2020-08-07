---
title: Konfigurieren der Serverkonfigurationsoption „Max. Grad an Parallelität“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- parallel queries [SQL Server]
- processors [SQL Server], parallel queries
- number of processors for parallel queries
- max degree of parallelism option
ms.assetid: 86b65bf1-a6a1-4670-afc0-cdfad1558032
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 824dc837142acc4a0898cb04b4a8687bc5be4043
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619345"
---
# <a name="configure-the-max-degree-of-parallelism-server-configuration-option"></a><span data-ttu-id="4cb54-102">Konfigurieren der Serverkonfigurationsoption Max. Grad an Parallelität</span><span class="sxs-lookup"><span data-stu-id="4cb54-102">Configure the max degree of parallelism Server Configuration Option</span></span>
  <span data-ttu-id="4cb54-103">In diesem Thema wird beschrieben, wie die `max degree of parallelism` Server Konfigurationsoption in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von oder konfiguriert wird [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4cb54-103">This topic describes how to configure the `max degree of parallelism` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="4cb54-104">Wenn eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf einem Computer mit mehreren Mikroprozessoren oder CPUs ausgeführt wird, wird der am besten geeignete Grad an Parallelität erkannt, also die Anzahl an Prozessoren, die für die Ausführung einer einzigen Anweisung eingesetzt werden. Dies gilt für die einzelnen Ausführungen paralleler Pläne.</span><span class="sxs-lookup"><span data-stu-id="4cb54-104">When an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] runs on a computer that has more than one microprocessor or CPU, it detects the best degree of parallelism, that is, the number of processors employed to run a single statement, for each parallel plan execution.</span></span> <span data-ttu-id="4cb54-105">Sie können mithilfe der `max degree of parallelism`-Option die Anzahl der Prozessoren beschränken, die für die Ausführung paralleler Pläne verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4cb54-105">You can use the `max degree of parallelism` option to limit the number of processors to use in parallel plan execution.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="4cb54-106">berücksichtigt parallele Ausführungspläne für Abfragen, DDL-Indizes (Index Data Definition Language) sowie die statische und keysetgesteuerte Cursor Population.</span><span class="sxs-lookup"><span data-stu-id="4cb54-106">considers parallel execution plans for queries, index data definition language (DDL) operations, and static and keyset-driven cursor population.</span></span>  
  
 <span data-ttu-id="4cb54-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="4cb54-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4cb54-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="4cb54-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4cb54-109">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4cb54-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4cb54-110">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="4cb54-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="4cb54-111">Security</span><span class="sxs-lookup"><span data-stu-id="4cb54-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4cb54-112">**So konfigurieren Sie die Option Max. Grad an Parallelität mit:**</span><span class="sxs-lookup"><span data-stu-id="4cb54-112">**To configure the max degree of parallelism option, using:**</span></span>  
  
     [<span data-ttu-id="4cb54-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4cb54-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4cb54-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4cb54-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="4cb54-115">Nach **Verfolgung:**[nach dem Konfigurieren der Option max. Grad an Parallelität](#FollowUp)  </span><span class="sxs-lookup"><span data-stu-id="4cb54-115">**Follow Up:**  [After you configure the max degree of parallelism option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4cb54-116">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="4cb54-116">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4cb54-117">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4cb54-117">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="4cb54-118">Wenn die Option Affinity Mask nicht auf den Standardwert festgelegt ist, steht [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf Systemen mit symmetrischem Multiprocessing (SMP) möglicherweise nur eine beschränkte Anzahl an Prozessoren zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="4cb54-118">If the affinity mask option is not set to the default, it may restrict the number of processors available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on symmetric multiprocessing (SMP) systems.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="4cb54-119">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="4cb54-119">Recommendations</span></span>  
  
-   <span data-ttu-id="4cb54-120">Diese Option ist eine erweiterte Option und sollte ausschließlich von einem erfahrenen Datenbankadministrator oder einem zertifizierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Techniker geändert werden.</span><span class="sxs-lookup"><span data-stu-id="4cb54-120">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="4cb54-121">Um den Server für die Ermittlung des maximalen Parallelitätsgrads zu aktivieren, legen Sie diese Option auf den Standardwert 0 fest.</span><span class="sxs-lookup"><span data-stu-id="4cb54-121">To enable the server to determine the maximum degree of parallelism, set this option to 0, the default value.</span></span> <span data-ttu-id="4cb54-122">Durch das Festlegen des maximalen Parallelitätsgrads auf 0 kann [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alle verfügbaren Prozessoren verwenden (bis maximal 64 Prozessoren).</span><span class="sxs-lookup"><span data-stu-id="4cb54-122">Setting maximum degree of parallelism to 0 allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use all the available processors up to 64 processors.</span></span> <span data-ttu-id="4cb54-123">Legen Sie `max degree of parallelism` auf 1 fest, um das Generieren paralleler Pläne zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="4cb54-123">To suppress parallel plan generation, set `max degree of parallelism` to 1.</span></span> <span data-ttu-id="4cb54-124">Legen Sie den Wert auf eine Zahl von 1 bis 32.767 fest, um die maximale Anzahl von Prozessorkernen anzugeben, die von einer einzelnen Abfrageausführung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="4cb54-124">Set the value to a number from 1 to 32,767 to specify the maximum number of processor cores that can be used by a single query execution.</span></span> <span data-ttu-id="4cb54-125">Wenn ein Wert angegeben wird, der über der Anzahl der verfügbaren Prozessoren liegt, wird die tatsächliche Anzahl der Prozessoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="4cb54-125">If a value greater than the number of available processors is specified, the actual number of available processors is used.</span></span> <span data-ttu-id="4cb54-126">Verfügt der Computer nur über einen Prozessor, wird der Wert von `max degree of parallelism` ignoriert.</span><span class="sxs-lookup"><span data-stu-id="4cb54-126">If the computer has only one processor, the `max degree of parallelism` value is ignored.</span></span>  
  
-   <span data-ttu-id="4cb54-127">In Abfragen kann der Wert "Max. Grad an Parallelität" überschrieben werden; geben Sie hierzu den Abfragehinweis MAXDOP in der Abfrageanweisung an.</span><span class="sxs-lookup"><span data-stu-id="4cb54-127">You can override the max degree of parallelism value in queries by specifying the MAXDOP query hint in the query statement.</span></span> <span data-ttu-id="4cb54-128">Weitere Informationen finden Sie unter [Abfragehinweise &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query).</span><span class="sxs-lookup"><span data-stu-id="4cb54-128">For more information, see [Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query).</span></span>  
  
-   <span data-ttu-id="4cb54-129">Indizierungsoperationen, bei denen ein Index erstellt oder neu aufgebaut wird bzw. an deren Ende ein gruppierter Index steht, können ressourcenintensiv sein.</span><span class="sxs-lookup"><span data-stu-id="4cb54-129">Index operations that create or rebuild an index, or that drop a clustered index, can be resource intensive.</span></span> <span data-ttu-id="4cb54-130">In Indizierungsoperationen kann der Wert "Max. Grad an Parallelität" überschrieben werden; geben Sie hierzu die Indexoption MAXDOP in der Indexanweisung an.</span><span class="sxs-lookup"><span data-stu-id="4cb54-130">You can override the max degree of parallelism value for index operations by specifying the MAXDOP index option in the index statement.</span></span> <span data-ttu-id="4cb54-131">Der Wert MAXDOP wird zur Ausführungszeit auf die Anweisung angewendet und wird nicht in den Metadaten für den Index gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4cb54-131">The MAXDOP value is applied to the statement at execution time and is not stored in the index metadata.</span></span> <span data-ttu-id="4cb54-132">Weitere Informationen finden Sie unter [Konfigurieren von Parallelindexvorgängen](../../relational-databases/indexes/configure-parallel-index-operations.md).</span><span class="sxs-lookup"><span data-stu-id="4cb54-132">For more information, see [Configure Parallel Index Operations](../../relational-databases/indexes/configure-parallel-index-operations.md).</span></span>  
  
-   <span data-ttu-id="4cb54-133">Neben Abfragen und Indexoperationen steuert diese Option auch die Parallelität von DBCC CHECKTABLE, DBCC CHECKDB und DBCC CHECKFILEGROUP.</span><span class="sxs-lookup"><span data-stu-id="4cb54-133">In addition to queries and index operations, this option also controls the parallelism of DBCC CHECKTABLE, DBCC CHECKDB, and DBCC CHECKFILEGROUP.</span></span> <span data-ttu-id="4cb54-134">Sie können Pläne für die parallele Ausführung für diese Anweisungen deaktivieren, und zwar mithilfe des Ablaufverfolgungsflags 2528.</span><span class="sxs-lookup"><span data-stu-id="4cb54-134">You can disable parallel execution plans for these statements by using trace flag 2528.</span></span> <span data-ttu-id="4cb54-135">Weitere Informationen finden Sie unter [Ablaufverfolgungsflags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4cb54-135">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4cb54-136">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4cb54-136">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4cb54-137">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4cb54-137">Permissions</span></span>  
 <span data-ttu-id="4cb54-138">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="4cb54-138">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="4cb54-139">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="4cb54-139">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="4cb54-140">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4cb54-140">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4cb54-141">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4cb54-141">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-max-degree-of-parallelism-option"></a><span data-ttu-id="4cb54-142">So konfigurieren Sie die Option Max. Grad an Parallelität</span><span class="sxs-lookup"><span data-stu-id="4cb54-142">To configure the max degree of parallelism option</span></span>  
  
1.  <span data-ttu-id="4cb54-143">Klicken Sie im **Objekt-Explorer**mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="4cb54-143">In **Object Explorer**, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="4cb54-144">Klicken Sie auf den **Erweitert** -Knoten.</span><span class="sxs-lookup"><span data-stu-id="4cb54-144">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="4cb54-145">Wählen Sie im Feld **Max. Grad an Parallelität** die maximale Anzahl der Prozessoren aus, die bei der Ausführung paralleler Pläne verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4cb54-145">In the **Max Degree of Parallelism** box, select the maximum number of processors to use in parallel plan execution.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4cb54-146">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4cb54-146">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-max-degree-of-parallelism-option"></a><span data-ttu-id="4cb54-147">So konfigurieren Sie die Option Max. Grad an Parallelität</span><span class="sxs-lookup"><span data-stu-id="4cb54-147">To configure the max degree of parallelism option</span></span>  
  
1.  <span data-ttu-id="4cb54-148">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="4cb54-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4cb54-149">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="4cb54-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4cb54-150">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="4cb54-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4cb54-151">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) verwendet wird, um die Option `max degree of parallelism` auf `8`festzulegen.</span><span class="sxs-lookup"><span data-stu-id="4cb54-151">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `max degree of parallelism` option to `8`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO   
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE WITH OVERRIDE;  
GO  
EXEC sp_configure 'max degree of parallelism', 8;  
GO  
RECONFIGURE WITH OVERRIDE;  
GO  
```  
  
 <span data-ttu-id="4cb54-152">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="4cb54-152">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-max-degree-of-parallelism-option"></a><a name="FollowUp"></a><span data-ttu-id="4cb54-153">Nächster Schritt: Nach dem Konfigurieren der Option „Max. Grad an Parallelität“</span><span class="sxs-lookup"><span data-stu-id="4cb54-153">Follow Up: After you configure the max degree of parallelism option</span></span>  
 <span data-ttu-id="4cb54-154">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="4cb54-154">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cb54-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4cb54-155">See Also</span></span>  
 <span data-ttu-id="4cb54-156">[Affinitätsmaske (Serverkonfigurationsoption)](affinity-mask-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="4cb54-156">[affinity mask Server Configuration Option](affinity-mask-server-configuration-option.md) </span></span>  
 <span data-ttu-id="4cb54-157">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cb54-157">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="4cb54-158">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4cb54-158">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="4cb54-159">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cb54-159">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="4cb54-160">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cb54-160">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="4cb54-161">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cb54-161">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="4cb54-162">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cb54-162">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 <span data-ttu-id="4cb54-163">[DBCC CHECKTABLE &#40;Transact-SQL-&#41;](/sql/t-sql/database-console-commands/dbcc-checktable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cb54-163">[DBCC CHECKTABLE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checktable-transact-sql) </span></span>  
 <span data-ttu-id="4cb54-164">[DBCC CHECKDB &#40;Transact-SQL-&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cb54-164">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 <span data-ttu-id="4cb54-165">[DBCC Check File Group &#40;Transact-SQL-&#41;](/sql/t-sql/database-console-commands/dbcc-checkfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cb54-165">[DBCC CHECKFILEGROUP &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="4cb54-166">[Konfigurieren von Parallelindexvorgängen](../../relational-databases/indexes/configure-parallel-index-operations.md) </span><span class="sxs-lookup"><span data-stu-id="4cb54-166">[Configure Parallel Index Operations](../../relational-databases/indexes/configure-parallel-index-operations.md) </span></span>  
 <span data-ttu-id="4cb54-167">[Abfragehinweise (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="4cb54-167">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="4cb54-168">Festlegen von Indexoptionen</span><span class="sxs-lookup"><span data-stu-id="4cb54-168">Set Index Options</span></span>](../../relational-databases/indexes/set-index-options.md)  
  
  
