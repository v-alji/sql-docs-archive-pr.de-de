---
title: Konfigurieren der Serverkonfigurationsoption „Sperren“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- locks option [SQL Server]
ms.assetid: b0cf0f86-7652-4574-a9fb-908e10d03973
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e45f4cc539be585966eb0beb30d4938b504c3419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724929"
---
# <a name="configure-the-locks-server-configuration-option"></a><span data-ttu-id="703d3-102">Konfigurieren der Serverkonfigurationsoption Sperren</span><span class="sxs-lookup"><span data-stu-id="703d3-102">Configure the locks Server Configuration Option</span></span>
  <span data-ttu-id="703d3-103">In diesem Thema wird beschrieben, wie die Serverkonfigurationsoption **Sperren** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="703d3-103">This topic describes how to configure the **locks** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="703d3-104">Mithilfe der Option **Sperren** können Sie die maximale Anzahl verfügbarer Sperren festlegen und so die Menge an Arbeitsspeicher begrenzen, die [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] für Sperren verwendet.</span><span class="sxs-lookup"><span data-stu-id="703d3-104">The **locks** option sets the maximum number of available locks, thereby limiting the amount of memory the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses for them.</span></span> <span data-ttu-id="703d3-105">Die Standardeinstellung ist 0. Dadurch kann [!INCLUDE[ssDE](../../includes/ssde-md.md)] Sperrstrukturen je nach Systemanforderungen dynamisch zuordnen oder die Zuordnung von Sperrstrukturen aufheben.</span><span class="sxs-lookup"><span data-stu-id="703d3-105">The default setting is 0, which allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to allocate and deallocate lock structures dynamically, based on changing system requirements.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="703d3-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="703d3-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="703d3-107">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="703d3-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="703d3-108">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="703d3-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="703d3-109">Security</span><span class="sxs-lookup"><span data-stu-id="703d3-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="703d3-110">**So konfigurieren Sie die Option Sperren mit:**</span><span class="sxs-lookup"><span data-stu-id="703d3-110">**To configure the locks option, using:**</span></span>  
  
     [<span data-ttu-id="703d3-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="703d3-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="703d3-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="703d3-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="703d3-113">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Sperren“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="703d3-113">**Follow Up:**  [After you configure the locks option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="703d3-114">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="703d3-114">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="703d3-115">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="703d3-115">Recommendations</span></span>  
  
-   <span data-ttu-id="703d3-116">Diese Option ist eine erweiterte Option und sollte ausschließlich von einem erfahrenen Datenbankadministrator oder einem zertifizierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Techniker geändert werden.</span><span class="sxs-lookup"><span data-stu-id="703d3-116">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="703d3-117">Wenn der Server gestartet wird, während die Option **Sperren** auf 0 festgelegt ist, richtet der Sperren-Manager ausreichend Arbeitsspeicher von [!INCLUDE[ssDE](../../includes/ssde-md.md)] für einen ersten Pool von 2.500 Sperrstrukturen ein.</span><span class="sxs-lookup"><span data-stu-id="703d3-117">When the server is started with **locks** set to 0, the lock manager acquires sufficient memory from the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for an initial pool of 2,500 lock structures.</span></span> <span data-ttu-id="703d3-118">Wenn der Sperrenpool verbraucht ist, wird zusätzlicher Arbeitsspeicher für den Pool eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="703d3-118">As the lock pool is exhausted, additional memory is acquired for the pool.</span></span>  
  
     <span data-ttu-id="703d3-119">Wenn für den Sperrenpool mehr Arbeitsspeicher benötigt wird als im [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Speicherpool verfügbar ist und auf dem Computer weiterer Speicher zur Verfügung steht (wenn also der Schwellenwert **Max. Serverarbeitsspeicher** noch nicht erreicht ist), weist [!INCLUDE[ssDE](../../includes/ssde-md.md)] in der Regel dynamisch Speicher zu, um die Sperrenanforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="703d3-119">Generally, if more memory is required for the lock pool than is available in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] memory pool, and more computer memory is available (the **max server memory** threshold has not been reached), the [!INCLUDE[ssDE](../../includes/ssde-md.md)] allocates memory dynamically to satisfy the request for locks.</span></span> <span data-ttu-id="703d3-120">Wenn durch das Zuweisen dieses Speichers jedoch eine Auslagerung auf Betriebssystemebene ausgelöst würde (wenn beispielsweise eine weitere Anwendung auf dem gleichen Computer als Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgeführt wird und diesen Arbeitsspeicher verwendet), wird kein weiterer Speicherplatz für Sperren zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="703d3-120">However, if allocating that memory would cause paging at the operating system level (for example, if another application is running on the same computer as an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and using that memory), more lock space is not allocated.</span></span> <span data-ttu-id="703d3-121">Der dynamische Sperrenpool ruft nicht mehr als 60 Prozent des Speichers ab, der dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="703d3-121">The dynamic lock pool does not acquire more than 60 percent of the memory allocated to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="703d3-122">Wenn der Sperrenpool 60 Prozent des von einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)]angeforderten Speichers erreicht hat oder wenn auf dem Computer kein weiterer Speicher verfügbar ist, wird bei weiteren Sperrenanforderungen ein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="703d3-122">After the lock pool has reached 60 percent of the memory acquired by an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], or no more memory is available on the computer, further requests for locks generate an error.</span></span>  
  
     <span data-ttu-id="703d3-123">Wenn Sperren von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dynamisch verwendet werden dürfen, entspricht dies der empfohlenen Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="703d3-123">Allowing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use locks dynamically is the recommended configuration.</span></span> <span data-ttu-id="703d3-124">Sie können **Sperren** jedoch festlegen und die Möglichkeit der dynamischen Zuweisung von Sperrenressourcen durch [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="703d3-124">However, you can set **locks** and override the ability of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to allocate lock resources dynamically.</span></span> <span data-ttu-id="703d3-125">Wenn **Sperren** auf einen anderen Wert als 0 festgelegt wird, kann [!INCLUDE[ssDE](../../includes/ssde-md.md)] dem unter **Sperren**angegebenen Wert keine weiteren Sperren zuweisen.</span><span class="sxs-lookup"><span data-stu-id="703d3-125">When **locks** is set to a value other than 0, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] cannot allocate more locks than the value specified in **locks**.</span></span> <span data-ttu-id="703d3-126">Erhöhen Sie diesen Wert, wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die Meldung anzeigt, dass die Anzahl der verfügbaren Sperren überschritten wurde.</span><span class="sxs-lookup"><span data-stu-id="703d3-126">Increase this value if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] displays a message that you have exceeded the number of available locks.</span></span> <span data-ttu-id="703d3-127">Da jede Sperre Arbeitsspeicher verbraucht (96 Bytes pro Sperre), kann es bei Erhöhung dieses Werts erforderlich werden, dem Server mehr Speicher zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="703d3-127">Because each lock consumes memory (96 bytes per lock), increasing this value can require increasing the amount of memory dedicated to the server.</span></span>  
  
-   <span data-ttu-id="703d3-128">Die Option **Sperren** wirkt sich auch darauf aus, wann eine Sperrenausweitung stattfindet.</span><span class="sxs-lookup"><span data-stu-id="703d3-128">The **locks** option also affects when lock escalation occurs.</span></span> <span data-ttu-id="703d3-129">Wenn **Sperren** auf 0 festgelegt ist, findet eine Sperrenausweitung statt, sobald der von den aktuellen Sperrenstrukturen verwendete Speicher 40 Prozent des [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Speicherpools erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="703d3-129">When **locks** is set to 0, lock escalation occurs when the memory used by the current lock structures reaches 40 percent of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] memory pool.</span></span> <span data-ttu-id="703d3-130">Wenn **Sperren** nicht auf 0 festgelegt ist, findet eine Sperrenausweitung statt, sobald die Anzahl der Sperren 40 Prozent des für **Sperren**festgelegten Werts erreicht.</span><span class="sxs-lookup"><span data-stu-id="703d3-130">When **locks** is not set to 0, lock escalation occurs when the number of locks reaches 40 percent of the value specified for **locks**.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="703d3-131">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="703d3-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="703d3-132">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="703d3-132">Permissions</span></span>  
 <span data-ttu-id="703d3-133">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="703d3-133">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="703d3-134">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="703d3-134">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="703d3-135">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="703d3-135">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="703d3-136">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="703d3-136">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-locks-option"></a><span data-ttu-id="703d3-137">So konfigurieren Sie die Option locks</span><span class="sxs-lookup"><span data-stu-id="703d3-137">To configure the locks option</span></span>  
  
1.  <span data-ttu-id="703d3-138">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="703d3-138">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="703d3-139">Klicken Sie auf den **Erweitert** -Knoten.</span><span class="sxs-lookup"><span data-stu-id="703d3-139">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="703d3-140">Geben Sie unter **Parallelität**den gewünschten Wert für die Option **Sperren** ein.</span><span class="sxs-lookup"><span data-stu-id="703d3-140">Under **Parallelism**, type the desired value for the **locks** option.</span></span>  
  
     <span data-ttu-id="703d3-141">Mithilfe der Option **Sperren** können Sie die maximale Anzahl verfügbarer Sperren festlegen und so die Menge an Arbeitsspeicher begrenzen, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] für Sperren verwendet.</span><span class="sxs-lookup"><span data-stu-id="703d3-141">Use the **locks** option to set the maximum number of available locks, thereby limiting the amount of memory [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses for them.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="703d3-142">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="703d3-142">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-locks-option"></a><span data-ttu-id="703d3-143">So konfigurieren Sie die Option locks</span><span class="sxs-lookup"><span data-stu-id="703d3-143">To configure the locks option</span></span>  
  
1.  <span data-ttu-id="703d3-144">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="703d3-144">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="703d3-145">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="703d3-145">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="703d3-146">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="703d3-146">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="703d3-147">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) zum Festlegen des Werts der Option `locks` verwendet wird, um die Anzahl der für alle Benutzer verfügbaren Sperren auf `20000`zu setzen.</span><span class="sxs-lookup"><span data-stu-id="703d3-147">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `locks` option to set the number of locks available for all users to `20000`.</span></span>  
  
```sql  
Use AdventureWorks2012 ;  
GO  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'locks', 20000;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="703d3-148">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="703d3-148">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-locks-option"></a><a name="FollowUp"></a><span data-ttu-id="703d3-149">Nächster Schritt: Nach dem Konfigurieren der Option „Sperren“</span><span class="sxs-lookup"><span data-stu-id="703d3-149">Follow Up: After you configure the locks option</span></span>  
 <span data-ttu-id="703d3-150">Der Server muss neu gestartet werden, bevor die Einstellung wirksam werden kann.</span><span class="sxs-lookup"><span data-stu-id="703d3-150">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="703d3-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="703d3-151">See Also</span></span>  
 <span data-ttu-id="703d3-152">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="703d3-152">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="703d3-153">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="703d3-153">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="703d3-154">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="703d3-154">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
