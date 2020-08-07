---
title: Konfigurieren der Serverkonfigurationsoption „Maximale Anzahl von Arbeitsthreads“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- worker threads [SQL Server]
- max worker threads option
ms.assetid: abeadfa4-a14d-469a-bacf-75812e48fac1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4881cefee350d34d93b539c56be6f43866d3ddfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619343"
---
# <a name="configure-the-max-worker-threads-server-configuration-option"></a><span data-ttu-id="49d59-102">Konfigurieren der Serverkonfigurationsoption Maximale Anzahl von Arbeitsthreads</span><span class="sxs-lookup"><span data-stu-id="49d59-102">Configure the max worker threads Server Configuration Option</span></span>
  <span data-ttu-id="49d59-103">In diesem Thema wird beschrieben, wie die Serverkonfigurationsoption **Max. Anzahl von Arbeitsthreads** in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="49d59-103">This topic describes how to configure the **max worker threads** server configuration option in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="49d59-104">Sie können mithilfe der Option **Max. Anzahl von Arbeitsthreads** die Anzahl von Arbeitsthreads konfigurieren, die für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Prozesse zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="49d59-104">The **max worker threads** option configures the number of worker threads that are available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="49d59-105">verwendet die systemeigenen Threaddienste der Betriebssysteme, sodass jedes Netzwerk, das gleichzeitig von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützt wird, von mindestens einem Thread unterstützt wird. Ein weiterer Thread verarbeitet die Datenbank-Prüfpunkte, und ein Threadpool verarbeitet alle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="49d59-105">uses the native thread services of the operating systems so that one or more threads support each network that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supports simultaneously, another thread handles database checkpoints, and a pool of threads handles all users.</span></span> <span data-ttu-id="49d59-106">Der Standardwert für **Max. Anzahl von Arbeitsthreads** ist 0.</span><span class="sxs-lookup"><span data-stu-id="49d59-106">The default value for **max worker threads** is 0.</span></span> <span data-ttu-id="49d59-107">Auf diese Weise kann [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die Anzahl der Arbeitsthreads beim Starten automatisch konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="49d59-107">This enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to automatically configure the number of worker threads at startup.</span></span> <span data-ttu-id="49d59-108">Die Standardeinstellung ist für die meisten Systeme am besten geeignet.</span><span class="sxs-lookup"><span data-stu-id="49d59-108">The default setting is best for most systems.</span></span> <span data-ttu-id="49d59-109">Abhängig von der Konfiguration des Systems kann durch Festlegen von **Max. Anzahl von Arbeitsthreads** auf einen bestimmten Wert manchmal die Leistung verbessert werden.</span><span class="sxs-lookup"><span data-stu-id="49d59-109">However, depending on your system configuration, setting **max worker threads** to a specific value sometimes improves performance.</span></span>  
  
 <span data-ttu-id="49d59-110">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="49d59-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="49d59-111">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="49d59-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="49d59-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="49d59-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="49d59-113">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="49d59-113">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="49d59-114">Security</span><span class="sxs-lookup"><span data-stu-id="49d59-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="49d59-115">**So konfigurieren Sie die Option Maximale Anzahl von Arbeitsthreads mit:**</span><span class="sxs-lookup"><span data-stu-id="49d59-115">**To configure the max worker threads option, using:**</span></span>  
  
     [<span data-ttu-id="49d59-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="49d59-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="49d59-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="49d59-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="49d59-118">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Max. Anzahl von Arbeitsthreads“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="49d59-118">**Follow Up:**  [After you configure the max worker threads option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="49d59-119">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="49d59-119">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="49d59-120">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="49d59-120">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="49d59-121">Wenn die tatsächliche Anzahl von Abfrageanforderungen geringer als der für **Max. Anzahl von Arbeitsthreads**festgelegte Wert ist, werden alle Abfrageanforderungen von einem Thread verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="49d59-121">When the actual number of query requests is less than the amount set in **max worker threads**, one thread handles each query request.</span></span> <span data-ttu-id="49d59-122">Wenn die tatsächliche Anzahl der Abfrage Anforderungen jedoch den in maximale Anzahl von **Arbeitsthreads**festgelegten Wert überschreitet, werden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die Arbeitsthreads von in einem Pool so verarbeitet, dass der nächste verfügbare Arbeits Thread die Anforderung verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="49d59-122">However, if the actual number of query request exceeds the amount set in **max worker threads**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pools the worker threads so that the next available worker thread can handle the request.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="49d59-123">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="49d59-123">Recommendations</span></span>  
  
-   <span data-ttu-id="49d59-124">Diese Option ist eine erweiterte Option und sollte ausschließlich von einem erfahrenen Datenbankadministrator oder einem zertifizierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Techniker geändert werden.</span><span class="sxs-lookup"><span data-stu-id="49d59-124">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="49d59-125">Threadpools erleichtern das Optimieren der Leistung, wenn sehr viele Clients mit dem Server verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="49d59-125">Thread pooling helps optimize performance when large numbers of clients are connected to the server.</span></span> <span data-ttu-id="49d59-126">Üblicherweise wird ein separater Betriebssystemthread für jede Abfrageanforderung erstellt.</span><span class="sxs-lookup"><span data-stu-id="49d59-126">Usually, a separate operating system thread is created for each query request.</span></span> <span data-ttu-id="49d59-127">Wenn jedoch bei Hunderten von Verbindungen mit dem Server weiterhin ein Thread pro Abfrageanforderung verwendet wird, kann dabei eine große Menge an Systemressourcen verbraucht werden.</span><span class="sxs-lookup"><span data-stu-id="49d59-127">However, with hundreds of connections to the server, using one thread per query request can consume large amounts of system resources.</span></span> <span data-ttu-id="49d59-128">Die Option **Max. Anzahl von Arbeitsthreads** ermöglicht [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] das Erstellen eines Pools mit Arbeitsthreads, der eine große Anzahl von Abfrageanforderungen versorgen kann und so zur Verbesserung der Leistung beiträgt.</span><span class="sxs-lookup"><span data-stu-id="49d59-128">The **max worker threads** option enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to create a pool of worker threads to service a larger number of query requests, which improves performance.</span></span>  
  
-   <span data-ttu-id="49d59-129">In der folgenden Tabelle werden die automatisch konfigurierte maximale Anzahl von Arbeitsthreads für verschiedene Kombinationen von CPUs und Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]dargestellt.</span><span class="sxs-lookup"><span data-stu-id="49d59-129">The following table shows the automatically configured number of max worker threads for various combinations of CPUs and versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    |<span data-ttu-id="49d59-130">Anzahl von CPUs</span><span class="sxs-lookup"><span data-stu-id="49d59-130">Number of CPUs</span></span>|<span data-ttu-id="49d59-131">32-Bit-Computer</span><span class="sxs-lookup"><span data-stu-id="49d59-131">32-bit computer</span></span>|<span data-ttu-id="49d59-132">64-Bit-Computer</span><span class="sxs-lookup"><span data-stu-id="49d59-132">64-bit computer</span></span>|  
    |--------------------|----------------------|----------------------|  
    |<span data-ttu-id="49d59-133">\<= 4 Prozessoren</span><span class="sxs-lookup"><span data-stu-id="49d59-133">\<= 4 processors</span></span>|<span data-ttu-id="49d59-134">256</span><span class="sxs-lookup"><span data-stu-id="49d59-134">256</span></span>|<span data-ttu-id="49d59-135">512</span><span class="sxs-lookup"><span data-stu-id="49d59-135">512</span></span>|  
    |<span data-ttu-id="49d59-136">8 Prozessoren</span><span class="sxs-lookup"><span data-stu-id="49d59-136">8 processors</span></span>|<span data-ttu-id="49d59-137">288</span><span class="sxs-lookup"><span data-stu-id="49d59-137">288</span></span>|<span data-ttu-id="49d59-138">576</span><span class="sxs-lookup"><span data-stu-id="49d59-138">576</span></span>|  
    |<span data-ttu-id="49d59-139">16 Prozessoren</span><span class="sxs-lookup"><span data-stu-id="49d59-139">16 processors</span></span>|<span data-ttu-id="49d59-140">352</span><span class="sxs-lookup"><span data-stu-id="49d59-140">352</span></span>|<span data-ttu-id="49d59-141">704</span><span class="sxs-lookup"><span data-stu-id="49d59-141">704</span></span>|  
    |<span data-ttu-id="49d59-142">32 Prozessoren</span><span class="sxs-lookup"><span data-stu-id="49d59-142">32 processors</span></span>|<span data-ttu-id="49d59-143">480</span><span class="sxs-lookup"><span data-stu-id="49d59-143">480</span></span>|<span data-ttu-id="49d59-144">960</span><span class="sxs-lookup"><span data-stu-id="49d59-144">960</span></span>|  
    |<span data-ttu-id="49d59-145">64 Prozessoren</span><span class="sxs-lookup"><span data-stu-id="49d59-145">64 processors</span></span>|<span data-ttu-id="49d59-146">736</span><span class="sxs-lookup"><span data-stu-id="49d59-146">736</span></span>|<span data-ttu-id="49d59-147">1472</span><span class="sxs-lookup"><span data-stu-id="49d59-147">1472</span></span>|  
    |<span data-ttu-id="49d59-148">128 Prozessoren</span><span class="sxs-lookup"><span data-stu-id="49d59-148">128 processors</span></span>|<span data-ttu-id="49d59-149">4224</span><span class="sxs-lookup"><span data-stu-id="49d59-149">4224</span></span>|<span data-ttu-id="49d59-150">4480</span><span class="sxs-lookup"><span data-stu-id="49d59-150">4480</span></span>|  
    |<span data-ttu-id="49d59-151">256 Prozessoren</span><span class="sxs-lookup"><span data-stu-id="49d59-151">256 processors</span></span>|<span data-ttu-id="49d59-152">8320</span><span class="sxs-lookup"><span data-stu-id="49d59-152">8320</span></span>|<span data-ttu-id="49d59-153">8576</span><span class="sxs-lookup"><span data-stu-id="49d59-153">8576</span></span>|  
  
    > [!NOTE]  
    >  <span data-ttu-id="49d59-154">Empfehlungen zur Verwendung von mehr als 64 CPUs finden Sie unter [Bewährte Methoden zum Ausführen von SQL Server auf Computern mit mehr als 64 CPUs](https://technet.microsoft.com/library/ee210547\(SQL.105\).aspx).</span><span class="sxs-lookup"><span data-stu-id="49d59-154">For recommendations on using more than 64 CPUs, refer to [Best Practices for Running SQL Server on Computers That Have More Than 64 CPUs](https://technet.microsoft.com/library/ee210547\(SQL.105\).aspx).</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="49d59-155">1024 ist der empfohlene Wert für die maximale Anzahl von Arbeitsthreads auf einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz, die auf einem 32-Bit-Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="49d59-155">We recommend 1024 as the maximum number of worker threads for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on a 32-bit computer.</span></span>  
  
-   <span data-ttu-id="49d59-156">Wenn alle Arbeitsthreads aktiviert sind, kann es sein, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bei Abfragen mit langer Ausführungszeit scheinbar nicht mehr reagiert, bis ein Arbeitsthread abgeschlossen wird und verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="49d59-156">When all worker threads are active with long running queries, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] might appear unresponsive until a worker thread completes and becomes available.</span></span> <span data-ttu-id="49d59-157">Dies ist zwar kein Fehler, aber in bestimmten Situationen unerwünscht.</span><span class="sxs-lookup"><span data-stu-id="49d59-157">Although this is not a defect, it can sometimes be undesirable.</span></span> <span data-ttu-id="49d59-158">Wenn ein Prozess scheinbar nicht mehr reagiert und keine neuen Abfragen verarbeitet werden können, stellen Sie mithilfe der dedizierten Administratorverbindung (DAC) eine Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] her, und brechen Sie den Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="49d59-158">If a process appears to be unresponsive and no new queries can be processed, then connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the dedicated administrator connection (DAC), and kill the process.</span></span> <span data-ttu-id="49d59-159">Um diese Situation zu verhindern, erhöhen Sie den Wert für die maximale Anzahl von Arbeitsthreads.</span><span class="sxs-lookup"><span data-stu-id="49d59-159">To prevent this, increase the number of max worker threads.</span></span>  
  
 <span data-ttu-id="49d59-160">Die Serverkonfigurationsoption **Max. Anzahl von Arbeitsthreads** berücksichtigt keine Kontothreads, die für alle Systemtasks wie Verfügbarkeitsgruppen, Service Broker, Sperren-Manager und andere erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="49d59-160">The **max worker threads** server configuration option does not take into account threads that are required for all the system tasks such as Availibility Groups, Service Broker, Lock Manager, and others.</span></span>  <span data-ttu-id="49d59-161">Wenn die Anzahl der konfigurierten Threads überschritten wird, stellt die folgende Abfrage Informationen zu den Systemtasks bereit, durch die die zusätzlichen Threads generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="49d59-161">If the number of threads configured are being exceeded, the following query will provide information about the system tasks that have spawned the additional threads.</span></span>  
  
```  
SELECT  
s.session_id,  
r.command,  
r.status,  
r.wait_type,  
r.scheduler_id,  
w.worker_address,  
w.is_preemptive,  
w.state,  
t.task_state,  
t.session_id,  
t.exec_context_id,  
t.request_id  
FROM sys.dm_exec_sessions AS s  
INNERJOIN sys.dm_exec_requests AS r  
    ON s.session_id = r.session_id  
INNER JOIN sys.dm_os_tasks AS t  
    ON r.task_address = t.task_address  
INNER JOIN sys.dm_os_workers AS w  
    ON t.worker_address = w.worker_address  
WHERE s.is_user_process = 0;  
  
```  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="49d59-162">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="49d59-162">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="49d59-163">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="49d59-163">Permissions</span></span>  
 <span data-ttu-id="49d59-164">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="49d59-164">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="49d59-165">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="49d59-165">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="49d59-166">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="49d59-166">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="49d59-167">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="49d59-167">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-max-worker-threads-option"></a><span data-ttu-id="49d59-168">So konfigurieren Sie die Option Max. Anzahl von Arbeitsthreads</span><span class="sxs-lookup"><span data-stu-id="49d59-168">To configure the max worker threads option</span></span>  
  
1.  <span data-ttu-id="49d59-169">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="49d59-169">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="49d59-170">Klicken Sie auf den Knoten **Prozessoren** .</span><span class="sxs-lookup"><span data-stu-id="49d59-170">Click the **Processors** node.</span></span>  
  
3.  <span data-ttu-id="49d59-171">Geben Sie im Feld Max. Anzahl von **Arbeitsthreads** einen Wert zwischen 128 und 32767 ein, oder wählen Sie diesen aus.</span><span class="sxs-lookup"><span data-stu-id="49d59-171">In the **Max worker threads** box, type or select a value from 128 through 32767.</span></span>  
  
     <span data-ttu-id="49d59-172">Sie können mithilfe der Option **Max. Anzahl von Arbeitsthreads** die Anzahl von Arbeitsthreads konfigurieren, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Prozessen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="49d59-172">Use the **max worker threads** option to configure the number of worker threads available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes.</span></span> <span data-ttu-id="49d59-173">Die Standardeinstellung für **Max. Anzahl von Arbeitsthreads** eignet sich für die meisten Systeme am besten.</span><span class="sxs-lookup"><span data-stu-id="49d59-173">The default setting for **max worker threads** is best for most systems.</span></span> <span data-ttu-id="49d59-174">Abhängig von der Konfiguration des Systems kann die Leistung manchmal verbessert werden, indem **Max. Anzahl von Arbeitsthreads** auf einen niedrigeren Wert festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="49d59-174">However, depending on your system configuration, setting **max worker threads** to a smaller value sometimes improves performance.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="49d59-175">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="49d59-175">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-max-worker-threads-option"></a><span data-ttu-id="49d59-176">So konfigurieren Sie die Option Max. Anzahl von Arbeitsthreads</span><span class="sxs-lookup"><span data-stu-id="49d59-176">To configure the max worker threads option</span></span>  
  
1.  <span data-ttu-id="49d59-177">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="49d59-177">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="49d59-178">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="49d59-178">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="49d59-179">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="49d59-179">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="49d59-180">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) verwendet wird, um die Option `max worker threads` auf `900`festzulegen.</span><span class="sxs-lookup"><span data-stu-id="49d59-180">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `max worker threads` option to `900`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'max worker threads', 900 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="49d59-181">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="49d59-181">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-max-worker-threads-option"></a><a name="FollowUp"></a><span data-ttu-id="49d59-182">Nächster Schritt: Nach dem Konfigurieren der Option „Max. Anzahl von Arbeitsthreads“</span><span class="sxs-lookup"><span data-stu-id="49d59-182">Follow Up: After you configure the max worker threads option</span></span>  
 <span data-ttu-id="49d59-183">Die Änderung wird sofort wirksam, ohne dass ein Neustart von [!INCLUDE[ssDE](../../includes/ssde-md.md)] erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="49d59-183">The change will take effect immediately without requiring the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49d59-184">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="49d59-184">See Also</span></span>  
 <span data-ttu-id="49d59-185">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="49d59-185">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="49d59-186">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="49d59-186">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="49d59-187">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="49d59-187">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="49d59-188">Diagnoseverbindung für Datenbankadministratoren</span><span class="sxs-lookup"><span data-stu-id="49d59-188">Diagnostic Connection for Database Administrators</span></span>](diagnostic-connection-for-database-administrators.md)  
  
  
