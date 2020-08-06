---
title: Konfigurieren der Serverkonfigurationsoption „Kostenschwellenwert für Parallelität“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/26/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- cost threshold for parallelism option
ms.assetid: dad21bee-fe28-41f6-9d2f-e6ababfaf9db
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 675055a753e84ace3a4fcb44b41b8c914326c5c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609445"
---
# <a name="configure-the-cost-threshold-for-parallelism-server-configuration-option"></a><span data-ttu-id="96b2e-102">Konfigurieren der Serverkonfigurationsoption Kostenschwellenwert für Parallelität</span><span class="sxs-lookup"><span data-stu-id="96b2e-102">Configure the cost threshold for parallelism Server Configuration Option</span></span>
  <span data-ttu-id="96b2e-103">In diesem Thema wird beschrieben, wie die Serverkonfigurationsoption **Kostenschwellenwert für Parallelität** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="96b2e-103">This topic describes how to configure the **cost threshold for parallelism** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="96b2e-104">Mit der Option **Kostenschwellenwert für Parallelität** geben Sie den Schwellenwert an, bei dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] parallele Pläne für Abfragen erstellt und ausführt.</span><span class="sxs-lookup"><span data-stu-id="96b2e-104">The **cost threshold for parallelism** option specifies the threshold at which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creates and runs parallel plans for queries.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="96b2e-105">erstellt und führt einen parallelen Plan für eine Abfrage nur dann aus, wenn die geschätzten Kosten für das Ausführen eines seriellen Plans für dieselbe Abfrage höher liegen als der Wert, der in **Kostenschwellenwert für Parallelität**festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="96b2e-105">creates and runs a parallel plan for a query only when the estimated cost to run a serial plan for the same query is higher than the value set in **cost threshold for parallelism**.</span></span> <span data-ttu-id="96b2e-106">Die Kosten beziehen sich auf eine geschätzte Zeit in Sekunden, die für das Ausführen des seriellen Plans bei einer bestimmten Hardwarekonfiguration benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="96b2e-106">The cost refers to an estimated elapsed time in seconds required to run the serial plan on a specific hardware configuration.</span></span> <span data-ttu-id="96b2e-107">Die Option **Kostenschwellenwert für Parallelität** kann auf einen beliebigen Wert zwischen 0 und 32767 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="96b2e-107">The **cost threshold for parallelism** option can be set to any value from 0 through 32767.</span></span> <span data-ttu-id="96b2e-108">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="96b2e-108">The default value is 5.</span></span>  
  
 <span data-ttu-id="96b2e-109">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="96b2e-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="96b2e-110">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="96b2e-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="96b2e-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="96b2e-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="96b2e-112">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="96b2e-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="96b2e-113">Security</span><span class="sxs-lookup"><span data-stu-id="96b2e-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="96b2e-114">**So konfigurieren Sie die Option Kostenschwelle für Parallelität mit:**</span><span class="sxs-lookup"><span data-stu-id="96b2e-114">**To configure the cost threshold for parallelism option, using:**</span></span>  
  
     [<span data-ttu-id="96b2e-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="96b2e-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="96b2e-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="96b2e-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="96b2e-117">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Kostenschwellenwert für Parallelität“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="96b2e-117">**Follow Up:**  [After you configure the cost threshold for parallelism option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="96b2e-118">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="96b2e-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="96b2e-119">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="96b2e-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="96b2e-120">Die Kosten beziehen sich auf eine geschätzte Zeit in Sekunden, die für das Ausführen des seriellen Plans bei einer bestimmten Hardwarekonfiguration benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="96b2e-120">The cost refers to an estimated elapsed time in seconds required to run the serial plan on a specific hardware configuration.</span></span> <span data-ttu-id="96b2e-121">Legen Sie die Option **cost threshold for parallelism** nur auf SMP-Systemen (Symmetric Multiprocessor) fest.</span><span class="sxs-lookup"><span data-stu-id="96b2e-121">Only set **cost threshold for parallelism** on symmetric multiprocessors.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="96b2e-122">ignoriert den Wert von **Kostenschwellenwert für Parallelität** unter den folgenden Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="96b2e-122">ignores the **cost threshold for parallelism** value under the following conditions:</span></span>  
  
    -   <span data-ttu-id="96b2e-123">Ihr Computer verfügt nur über einen logischen Prozessor.</span><span class="sxs-lookup"><span data-stu-id="96b2e-123">Your computer has only one logical processor.</span></span>  
  
    -   <span data-ttu-id="96b2e-124">Für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] steht wegen der Konfigurationsoption **Affinitätsmaske** nur ein logischer Prozessor zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="96b2e-124">Only a single logical processor is available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] because of the **affinity mask** configuration option.</span></span>  
  
    -   <span data-ttu-id="96b2e-125">Die Option **Max. Grad an Parallelität** ist auf den Wert 1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="96b2e-125">The **max degree of parallelism** option is set to 1.</span></span>  
  
 <span data-ttu-id="96b2e-126">Ein logischer Prozessor ist die grundlegende Einheit von Prozessorhardware, die dem Betriebssystem ermöglicht, einen Task weiterzuleiten oder einen Threadkontext auszuführen.</span><span class="sxs-lookup"><span data-stu-id="96b2e-126">A logical processor is the basic unit of processor hardware that allows the operating system to dispatch a task or execute a thread context.</span></span> <span data-ttu-id="96b2e-127">Jeder logische Prozessor kann an einem bestimmten Zeitpunkt nur einen Threadkontext ausführen.</span><span class="sxs-lookup"><span data-stu-id="96b2e-127">Each logical processor can execute only one thread context at a time.</span></span> <span data-ttu-id="96b2e-128">Der Prozessorkern ist die Schaltungstechnik, mit der Anweisungen decodiert und ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="96b2e-128">The processor core is the circuitry that provides ability to decode and execute instructions.</span></span> <span data-ttu-id="96b2e-129">Ein Prozessorkern enthält möglicherweise einen oder mehrere logische Prozessoren.</span><span class="sxs-lookup"><span data-stu-id="96b2e-129">A processor core may contain one or more logical processors.</span></span> <span data-ttu-id="96b2e-130">Die folgende [!INCLUDE[tsql](../../includes/tsql-md.md)] -Abfrage kann zum Abrufen von CPU-Informationen für das System verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="96b2e-130">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] query can be used for obtaining CPU information for the system.</span></span>  
  
```  
SELECT (cpu_count / hyperthread_ratio) AS PhysicalCPUs,   
cpu_count AS logicalCPUs   
FROM sys.dm_os_sys_info  
```  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="96b2e-131">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="96b2e-131">Recommendations</span></span>  
  
-   <span data-ttu-id="96b2e-132">Diese Option ist eine erweiterte Option und sollte ausschließlich von einem erfahrenen Datenbankadministrator oder einem zertifizierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Techniker geändert werden.</span><span class="sxs-lookup"><span data-stu-id="96b2e-132">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="96b2e-133">In bestimmten Fällen kann ein paralleler Plan ausgewählt werden, obwohl der Kostenplan der Abfrage unter dem aktuellen Wert der Option **Kostenschwellenwert für Parallelität** liegt.</span><span class="sxs-lookup"><span data-stu-id="96b2e-133">In certain cases, a parallel plan may be chosen even though the query's cost plan is less than the current **cost threshold for parallelism** value.</span></span> <span data-ttu-id="96b2e-134">Dieser Fall kann eintreten, wenn die Entscheidung zum Verwenden eines parallelen oder seriellen Plans auf einer Kostenabschätzung basiert, die vor dem Abschluss der vollständigen Optimierung zur Verfügung gestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="96b2e-134">This can happen because the decision to use a parallel or serial plan is based on a cost estimate provided before the full optimization is complete.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="96b2e-135">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="96b2e-135">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="96b2e-136">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="96b2e-136">Permissions</span></span>  
 <span data-ttu-id="96b2e-137">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="96b2e-137">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="96b2e-138">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="96b2e-138">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="96b2e-139">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="96b2e-139">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="96b2e-140">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="96b2e-140">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-cost-threshold-for-parallelism-option"></a><span data-ttu-id="96b2e-141">So konfigurieren Sie die Option Kostenschwelle für Parallelität</span><span class="sxs-lookup"><span data-stu-id="96b2e-141">To configure the cost threshold for parallelism option</span></span>  
  
1.  <span data-ttu-id="96b2e-142">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="96b2e-142">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="96b2e-143">Klicken Sie auf den **Erweitert** -Knoten.</span><span class="sxs-lookup"><span data-stu-id="96b2e-143">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="96b2e-144">Legen Sie unter **Parallelität**für die Option **CostThresholdForParallelism** den gewünschten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="96b2e-144">Under **Parallelism**, change the **CostThresholdForParallelism** option to the value you want.</span></span> <span data-ttu-id="96b2e-145">Geben Sie einen Wert zwischen 0 und 32767 ein bzw. wählen Sie diesen aus.</span><span class="sxs-lookup"><span data-stu-id="96b2e-145">Type or select a value from 0 to 32767.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="96b2e-146">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="96b2e-146">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-cost-threshold-for-parallelism-option"></a><span data-ttu-id="96b2e-147">So konfigurieren Sie die Option Kostenschwelle für Parallelität</span><span class="sxs-lookup"><span data-stu-id="96b2e-147">To configure the cost threshold for parallelism option</span></span>  
  
1.  <span data-ttu-id="96b2e-148">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="96b2e-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="96b2e-149">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="96b2e-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="96b2e-150">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="96b2e-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="96b2e-151">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) verwendet wird, um den Wert der Option `cost threshold for parallelism` auf `10`festzulegen.</span><span class="sxs-lookup"><span data-stu-id="96b2e-151">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `cost threshold for parallelism` option to `10`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'cost threshold for parallelism', 10 ;  
GO  
RECONFIGURE  
GO  
```  
  
 <span data-ttu-id="96b2e-152">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="96b2e-152">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-cost-threshold-for-parallelism-option"></a><a name="FollowUp"></a><span data-ttu-id="96b2e-153">Nächster Schritt: Nach dem Konfigurieren der Option „Kostenschwellenwert für Parallelität“</span><span class="sxs-lookup"><span data-stu-id="96b2e-153">Follow Up: After you configure the cost threshold for parallelism option</span></span>  
 <span data-ttu-id="96b2e-154">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="96b2e-154">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96b2e-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="96b2e-155">See Also</span></span>  
 <span data-ttu-id="96b2e-156">[Konfigurieren von Parallelindexvorgängen](../../relational-databases/indexes/configure-parallel-index-operations.md) </span><span class="sxs-lookup"><span data-stu-id="96b2e-156">[Configure Parallel Index Operations](../../relational-databases/indexes/configure-parallel-index-operations.md) </span></span>  
 <span data-ttu-id="96b2e-157">[Abfragehinweise (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="96b2e-157">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 <span data-ttu-id="96b2e-158">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="96b2e-158">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="96b2e-159">[Affinitätsmaske (Serverkonfigurationsoption)](affinity-mask-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="96b2e-159">[affinity mask Server Configuration Option](affinity-mask-server-configuration-option.md) </span></span>  
 <span data-ttu-id="96b2e-160">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="96b2e-160">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="96b2e-161">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="96b2e-161">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="96b2e-162">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="96b2e-162">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
