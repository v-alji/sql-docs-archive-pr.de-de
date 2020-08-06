---
title: Anhalten oder Fortsetzen einer Datenbank-Spiegelungssitzung (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- resuming database mirroring
- database mirroring [SQL Server], sessions
- database mirroring [SQL Server], pausing
- database mirroring [SQL Server], resuming
- pausing database mirroring
ms.assetid: 05ede3b4-6abe-4442-abb7-9f5aee1d6bc0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b8a9e30bed3ff268fcfdc6e352ad15ebedfe4e8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701859"
---
# <a name="pause-or-resume-a-database-mirroring-session-sql-server"></a><span data-ttu-id="74811-102">Anhalten oder Fortsetzen einer Datenbank-Spiegelungssitzung (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="74811-102">Pause or Resume a Database Mirroring Session (SQL Server)</span></span>
  <span data-ttu-id="74811-103">In diesem Thema wird beschrieben, wie Sie eine Datenbankspiegelung in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]anhalten oder fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="74811-103">This topic describes how to pause or resume database mirroring in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="74811-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="74811-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="74811-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="74811-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="74811-106">Security</span><span class="sxs-lookup"><span data-stu-id="74811-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="74811-107">**So ReplaceThisText mit:**</span><span class="sxs-lookup"><span data-stu-id="74811-107">**To ReplaceThisText, using:**</span></span>  
  
     [<span data-ttu-id="74811-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="74811-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="74811-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="74811-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="74811-110">**Nachverfolgung:**  [Nach dem Anhalten oder Fortsetzen der Datenbankspiegelung](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="74811-110">**Follow Up:**  [After Pausing or Resuming Database Mirroring](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="74811-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="74811-111">Before You Begin</span></span>  
 <span data-ttu-id="74811-112">Eine Datenbank-Spiegelungssitzung kann jederzeit angehalten werden. Dadurch kann die Leistung bei Engpässen ggf. verbessert werden, und anschließend können Sie die angehaltene Sitzung jederzeit fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="74811-112">At any time, you can suspend a database mirroring session, which might improve performance during bottlenecks, and you can resume a suspended session at any time.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="74811-113">Nach einem erzwungenen Dienst, wenn der ursprüngliche Prinzipalserver die Verbindung wiederherstellt, wird die Spiegelung angehalten.</span><span class="sxs-lookup"><span data-stu-id="74811-113">After a forced service, when the original principal server reconnects, mirroring is suspended.</span></span> <span data-ttu-id="74811-114">Das Fortsetzen der Spiegelung in dieser Situation könnte auf dem ursprünglichen Prinzipalserver zu Datenverlust führen.</span><span class="sxs-lookup"><span data-stu-id="74811-114">Resuming mirroring in this situation could possibly cause data loss on the original principal server.</span></span> <span data-ttu-id="74811-115">Informationen zum Verwalten des potenziellen Datenverlusts finden Sie unter [Rollenwechsel während einer Datenbank-Spiegelungssitzung &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="74811-115">For information about managing the potential data loss, see [Role Switching During a Database Mirroring Session &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="74811-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="74811-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="74811-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="74811-117">Permissions</span></span>  
 <span data-ttu-id="74811-118">Erfordert die ALTER-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="74811-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="74811-119">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="74811-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="74811-120">Eine Datenbank-Spiegelungssitzung können Sie auf der Seite **Spiegelung** der Datenbankeigenschaften anhalten bzw. fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="74811-120">To pause or resume a database mirroring session use the **Database Properties Mirroring** page.</span></span>  
  
#### <a name="to-pause-or-resume-database-mirroring"></a><span data-ttu-id="74811-121">So halten Sie eine Datenbankspiegelung an bzw. setzen sie fort</span><span class="sxs-lookup"><span data-stu-id="74811-121">To pause or resume database mirroring</span></span>  
  
1.  <span data-ttu-id="74811-122">Stellen Sie während einer Datenbank-Spiegelungssitzung eine Verbindung mit der Prinzipalserverinstanz her, und klicken Sie im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="74811-122">During a database mirroring session, connect to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="74811-123">Erweitern Sie **Datenbanken**, und wählen Sie die Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="74811-123">Expand **Databases**, and select the database.</span></span>  
  
3.  <span data-ttu-id="74811-124">Klicken Sie mit der rechten Maustaste auf die Datenbank, wählen Sie **Tasks**aus, und klicken Sie dann auf **Spiegeln**.</span><span class="sxs-lookup"><span data-stu-id="74811-124">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="74811-125">Dadurch wird die Seite **Spiegelung** im Dialogfeld **Datenbankeigenschaften** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="74811-125">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="74811-126">Klicken Sie zum Anhalten der Sitzung auf **Anhalten**.</span><span class="sxs-lookup"><span data-stu-id="74811-126">To pause the session, click **Pause**.</span></span>  
  
     <span data-ttu-id="74811-127">Wenn Sie in der Bestätigungsaufforderung auf **Ja**klicken, wird die Sitzung angehalten und die Schaltfläche erhält die Bezeichnung **Fortsetzen**.</span><span class="sxs-lookup"><span data-stu-id="74811-127">A prompt asks for confirmation; if you click **Yes**, the session is paused, and the button changes to **Resume**.</span></span>  
  
     <span data-ttu-id="74811-128">Weitere Informationen über die Auswirkung des Anhaltens einer Sitzung finden Sie unter [Anhalten und Fortsetzen der Datenbankspiegelung &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="74811-128">For more information about the impact of pausing a session, see [Pausing and Resuming Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="74811-129">Klicken Sie zum Fortsetzen der Sitzung auf **Fortsetzen**.</span><span class="sxs-lookup"><span data-stu-id="74811-129">To resume the session, click **Resume**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="74811-130">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="74811-130">Using Transact-SQL</span></span>  
  
#### <a name="to-pause-database-mirroring"></a><span data-ttu-id="74811-131">So halten Sie die Datenbankspiegelung an</span><span class="sxs-lookup"><span data-stu-id="74811-131">To pause database mirroring</span></span>  
  
1.  <span data-ttu-id="74811-132">Stellen Sie für einen der Partner eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="74811-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for either partner.</span></span>  
  
2.  <span data-ttu-id="74811-133">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="74811-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="74811-134">Führen Sie die folgende [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="74811-134">Issue the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
     <span data-ttu-id="74811-135">ALTER DATABASE *Datenbankname* SET PARTNER SUSPEND</span><span class="sxs-lookup"><span data-stu-id="74811-135">ALTER DATABASE *database_name* SET PARTNER SUSPEND</span></span>  
  
     <span data-ttu-id="74811-136">wobei *Datenbankname* für die gespiegelte Datenbank steht, deren Sitzung Sie anhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="74811-136">where *database_name* is the mirrored database whose session you want to you want to suspend.</span></span>  
  
     <span data-ttu-id="74811-137">Im folgenden Beispiel wird die Beispieldatenbank [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] angehalten.</span><span class="sxs-lookup"><span data-stu-id="74811-137">The following example pauses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET PARTNER SUSPEND;  
    ```  
  
##### <a name="to-resume-database-mirroring"></a><span data-ttu-id="74811-138">So setzen Sie die Datenbankspiegelung fort</span><span class="sxs-lookup"><span data-stu-id="74811-138">To resume database mirroring</span></span>  
  
1.  <span data-ttu-id="74811-139">Stellen Sie für einen der Partner eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="74811-139">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for either partner.</span></span>  
  
2.  <span data-ttu-id="74811-140">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="74811-140">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="74811-141">Führen Sie die folgende Transact-SQL-Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="74811-141">Issue the following Transact-SQL statement:</span></span>  
  
     <span data-ttu-id="74811-142">ALTER DATABASE *Datenbankname* SET PARTNER RESUME</span><span class="sxs-lookup"><span data-stu-id="74811-142">ALTER DATABASE *database_name* SET PARTNER RESUME</span></span>  
  
     <span data-ttu-id="74811-143">wobei *Datenbankname* für die gespiegelte Datenbank steht, deren Sitzung Sie fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="74811-143">where *database_name* is the mirrored database whose session you want to resume.</span></span>  
  
     <span data-ttu-id="74811-144">Im folgenden Beispiel wird die Beispieldatenbank [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] angehalten.</span><span class="sxs-lookup"><span data-stu-id="74811-144">The following example pauses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET PARTNER RESUME;  
    ```  
  
##  <a name="follow-up-after-pausing-or-resuming-database-mirroring"></a><a name="FollowUp"></a><span data-ttu-id="74811-145">Nachverfolgung: nach dem Anhalten oder Fortsetzen der Daten Bank Spiegelung</span><span class="sxs-lookup"><span data-stu-id="74811-145">Follow Up: After Pausing or Resuming Database Mirroring</span></span>  
  
-   <span data-ttu-id="74811-146">**Nach dem Anhalten der Datenbankspiegelung**</span><span class="sxs-lookup"><span data-stu-id="74811-146">**After pausing database mirroring**</span></span>  
  
     <span data-ttu-id="74811-147">Treffen Sie auf der primären Datenbank entsprechende Vorkehrungen, um ein Überlaufen des Transaktionsprotokolls zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="74811-147">On the primary database, take precautions to avoid a full transaction log.</span></span> <span data-ttu-id="74811-148">Weitere Informationen finden Sie unter [Das Transaktionsprotokoll &#40;SQL Server&#41;](../../relational-databases/logs/the-transaction-log-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="74811-148">For more information, see [The Transaction Log &#40;SQL Server&#41;](../../relational-databases/logs/the-transaction-log-sql-server.md).</span></span>  
  
-   <span data-ttu-id="74811-149">**Nach dem Fortsetzen der Datenbankspiegelung**</span><span class="sxs-lookup"><span data-stu-id="74811-149">**After resuming database mirroring**</span></span>  
  
     <span data-ttu-id="74811-150">Durch das Fortsetzen einer Datenbankspiegelung wird die Spiegeldatenbank in den SYNCHRONIZING-Status gesetzt.</span><span class="sxs-lookup"><span data-stu-id="74811-150">Resuming database mirroring places the mirror database in the SYNCHRONIZING state.</span></span> <span data-ttu-id="74811-151">Ist die Sicherheitsstufe auf FULL festgelegt, holt der Spiegel den aktuellen Verarbeitungsstand des Prinzipals auf, und die Spiegeldatenbank geht in den SYNCHRONIZED-Status über.</span><span class="sxs-lookup"><span data-stu-id="74811-151">If the safety level is FULL, the mirror catches up with the principal and the mirror database enters the SYNCHRONIZED state.</span></span> <span data-ttu-id="74811-152">Zu diesem Zeitpunkt ist das Ausführen eines Failovers möglich.</span><span class="sxs-lookup"><span data-stu-id="74811-152">At this point, failover becomes possible.</span></span> <span data-ttu-id="74811-153">Ist der Zeuge vorhanden und auf ON festgelegt, ist ein automatisches Failover möglich.</span><span class="sxs-lookup"><span data-stu-id="74811-153">If the witness is present and ON, automatic failover is possible.</span></span> <span data-ttu-id="74811-154">Bei Abwesenheit eines Zeugen ist ein manuelles Failover möglich.</span><span class="sxs-lookup"><span data-stu-id="74811-154">In the absence of a witness, manual failover is possible.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="74811-155">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="74811-155">Related Tasks</span></span>  
  
-   [<span data-ttu-id="74811-156">Entfernen der Datenbankspiegelung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="74811-156">Remove Database Mirroring &#40;SQL Server&#41;</span></span>](remove-database-mirroring-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="74811-157">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="74811-157">See Also</span></span>  
 [<span data-ttu-id="74811-158">Datenbankspiegelung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="74811-158">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
