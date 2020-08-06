---
title: Entfernen der Datenbankspiegelung (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], removing
- removing database mirroring [SQL Server]
ms.assetid: bbc4d7f7-3bc7-40d6-a822-af195fe7f8c0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19c1d0449fa1c7434aeaf9c51e3b2dc7bc6b68c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701799"
---
# <a name="remove-database-mirroring-sql-server"></a><span data-ttu-id="57b1f-102">Entfernen der Datenbankspiegelung (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="57b1f-102">Remove Database Mirroring (SQL Server)</span></span>
  <span data-ttu-id="57b1f-103">In diesem Thema wird beschrieben, wie Sie eine Datenbankspiegelung aus einer Datenbank in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]entfernen.</span><span class="sxs-lookup"><span data-stu-id="57b1f-103">This topic describes how to remove database mirroring from a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  <span data-ttu-id="57b1f-104">Der Datenbankbesitzer kann eine Datenbank-Spiegelungssitzung jederzeit manuell beenden, indem er die Spiegelung von der Datenbank entfernt.</span><span class="sxs-lookup"><span data-stu-id="57b1f-104">At any time, the database owner can manually stop a database mirroring session by removing mirroring from the database.</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="57b1f-105">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="57b1f-105">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="57b1f-106">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="57b1f-106">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="57b1f-107">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="57b1f-107">Permissions</span></span>  
 <span data-ttu-id="57b1f-108">Erfordert die ALTER-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="57b1f-108">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="57b1f-109">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="57b1f-109">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-database-mirroring"></a><span data-ttu-id="57b1f-110">So entfernen Sie die Datenbankspiegelung</span><span class="sxs-lookup"><span data-stu-id="57b1f-110">To remove database mirroring</span></span>  
  
1.  <span data-ttu-id="57b1f-111">Stellen Sie während einer Datenbank-Spiegelungssitzung eine Verbindung mit der Prinzipalserverinstanz her, und klicken Sie im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="57b1f-111">During a database mirroring session, connect to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="57b1f-112">Erweitern Sie **Datenbanken**, und wählen Sie die Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="57b1f-112">Expand **Databases**, and select the database.</span></span>  
  
3.  <span data-ttu-id="57b1f-113">Klicken Sie mit der rechten Maustaste auf die Datenbank, wählen Sie **Tasks**aus, und klicken Sie dann auf **Spiegeln**.</span><span class="sxs-lookup"><span data-stu-id="57b1f-113">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="57b1f-114">Dadurch wird die Seite **Spiegelung** im Dialogfeld **Datenbankeigenschaften** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="57b1f-114">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="57b1f-115">Klicken Sie im Bereich **Seite auswählen** auf **Spiegelung**.</span><span class="sxs-lookup"><span data-stu-id="57b1f-115">In the **Select a Page** pane, click **Mirroring**.</span></span>  
  
5.  <span data-ttu-id="57b1f-116">Zum Entfernen der Spiegelung klicken Sie auf **Spiegeln entfernen**.</span><span class="sxs-lookup"><span data-stu-id="57b1f-116">To remove mirroring, click **Remove Mirroring**.</span></span> <span data-ttu-id="57b1f-117">Es wird eine Bestätigungsaufforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="57b1f-117">A prompt asks for confirmation.</span></span> <span data-ttu-id="57b1f-118">Wenn Sie auf **Ja**klicken, wird die Sitzung beendet, und die Spiegelung wird aus der Datenbank entfernt.</span><span class="sxs-lookup"><span data-stu-id="57b1f-118">If you click **Yes**, the session is stopped and mirroring is removed from the database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="57b1f-119">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="57b1f-119">Using Transact-SQL</span></span>  
 <span data-ttu-id="57b1f-120">Zum Entfernen der Datenbankspiegelung verwenden Sie die **Datenbankeigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="57b1f-120">To remove database mirroring, use the **Database Properties**.</span></span> <span data-ttu-id="57b1f-121">Verwenden Sie die Seite **Spiegelung** im Dialogfeld **Datenbankeigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="57b1f-121">use the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
#### <a name="to-remove-database-mirroring"></a><span data-ttu-id="57b1f-122">So entfernen Sie die Datenbankspiegelung</span><span class="sxs-lookup"><span data-stu-id="57b1f-122">To remove database mirroring</span></span>  
  
1.  <span data-ttu-id="57b1f-123">Stellen Sie für einen der Spiegelungspartner eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="57b1f-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] of either mirroring partner.</span></span>  
  
2.  <span data-ttu-id="57b1f-124">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="57b1f-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="57b1f-125">Führen Sie die folgende [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="57b1f-125">Issue the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    ALTER DATABASE database_name SET PARTNER OFF  
    ```  
  
     <span data-ttu-id="57b1f-126">wobei *Datenbankname* für die gespiegelte Datenbank steht, deren Sitzung Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="57b1f-126">where *database_name* is the mirrored database whose session you want to remove.</span></span>  
  
     <span data-ttu-id="57b1f-127">Im folgenden Beispiel wird die Datenbankspiegelung aus der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Beispieldatenbank entfernt.</span><span class="sxs-lookup"><span data-stu-id="57b1f-127">The following example removes database mirroring from the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET PARTNER OFF;  
    ```  
  
##  <a name="follow-up-removing-database-mirroring"></a><a name="FollowUp"></a><span data-ttu-id="57b1f-128">Nächster Schritt: Entfernen der Datenbankspiegelung</span><span class="sxs-lookup"><span data-stu-id="57b1f-128">Follow Up: Removing Database Mirroring</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="57b1f-129">Weitere Informationen zu den Auswirkungen des Entfernens der Datenbankspiegelung finden Sie unter [Entfernen der Datenbankspiegelung &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="57b1f-129">For information about the impact of removing mirroring, see [Removing Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
-   <span data-ttu-id="57b1f-130">**Wenn Sie die Datenbankspiegelung erneut starten möchten**</span><span class="sxs-lookup"><span data-stu-id="57b1f-130">**If you intend to restart mirroring on the database**</span></span>  
  
     <span data-ttu-id="57b1f-131">Vor dem erneuten Starten der Spiegelung müssen alle Protokollsicherungen, die nach dem Entfernen der Spiegelung für die Prinzipaldatenbank erstellt wurden, auf die Spiegeldatenbank angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="57b1f-131">Any log backups taken on the principal database after mirroring was removed must all be applied to the mirror database before you can restart mirroring.</span></span>  
  
-   <span data-ttu-id="57b1f-132">**Wenn Sie die Datenbankspiegelung nicht erneut starten möchten**</span><span class="sxs-lookup"><span data-stu-id="57b1f-132">**If you do not intent to restart mirroring**</span></span>  
  
     <span data-ttu-id="57b1f-133">Sie haben auch die Möglichkeit, die frühere Spiegeldatenbank wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="57b1f-133">Optionally, you can recover the former mirror database.</span></span> <span data-ttu-id="57b1f-134">Auf der Serverinstanz, die den Spiegelserver darstellte, können Sie die folgende [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung ausführen:</span><span class="sxs-lookup"><span data-stu-id="57b1f-134">On the server instance that was the mirror server, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    RESTORE DATABASE database_name WITH RECOVERY;  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="57b1f-135">Wenn Sie diese Datenbank wiederherstellen, sind zwei voneinander abweichende Datenbanken mit demselben Namen online.</span><span class="sxs-lookup"><span data-stu-id="57b1f-135">If you recover this database, two divergent databases with the same name are online.</span></span> <span data-ttu-id="57b1f-136">Deshalb müssen Sie sicherstellen, dass Clients nur auf eine der beiden zugreifen können (in der Regel die aktuellere Prinzipaldatenbank).</span><span class="sxs-lookup"><span data-stu-id="57b1f-136">Therefore, you need to ensure that clients can access only one of them-typically the most recent principal database.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="57b1f-137">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="57b1f-137">Related Tasks</span></span>  
  
-   [<span data-ttu-id="57b1f-138">Anhalten oder Fortsetzen einer Datenbank-Spiegelungssitzung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="57b1f-138">Pause or Resume a Database Mirroring Session &#40;SQL Server&#41;</span></span>](pause-or-resume-a-database-mirroring-session-sql-server.md)  
  
-   [<span data-ttu-id="57b1f-139">Entfernen des Zeugen aus einer Datenbank-Spiegelungssitzung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="57b1f-139">Remove the Witness from a Database Mirroring Session &#40;SQL Server&#41;</span></span>](remove-the-witness-from-a-database-mirroring-session-sql-server.md)  
  
-   [<span data-ttu-id="57b1f-140">Einrichten einer Datenbank-Spiegelungssitzung mithilfe der Windows-Authentifizierung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="57b1f-140">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="57b1f-141">Einrichten einer Datenbank-Spiegelungssitzung mithilfe der Windows-Authentifizierung &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="57b1f-141">Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](database-mirroring-establish-session-windows-authentication.md)  
  
-   [<span data-ttu-id="57b1f-142">Beispiel: Einrichten der Datenbankspiegelung mithilfe von Zertifikaten &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="57b1f-142">Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;</span></span>](example-setting-up-database-mirroring-using-certificates-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="57b1f-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="57b1f-143">See Also</span></span>  
 <span data-ttu-id="57b1f-144">[Datenbankspiegelung &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="57b1f-144">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="57b1f-145">[Einrichten der Datenbankspiegelung &#40;SQL Server&#41;](setting-up-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="57b1f-145">[Setting Up Database Mirroring &#40;SQL Server&#41;](setting-up-database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="57b1f-146">AlwaysOn-Verfügbarkeitsgruppen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="57b1f-146">AlwaysOn Availability Groups (SQL Server)</span></span>](../availability-groups/windows/always-on-availability-groups-sql-server.md)  
  
  
