---
title: Entfernen des Protokollversands (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], removing
- removing log shipping
- deleting log shipping
ms.assetid: 859373db-c744-4a4b-8479-45163f61e8cb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 14fdc36c66073e89dcc2014aed4319a2ce78a98f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618247"
---
# <a name="remove-log-shipping-sql-server"></a><span data-ttu-id="35f0f-102">Entfernen des Protokollversands (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="35f0f-102">Remove Log Shipping (SQL Server)</span></span>
  <span data-ttu-id="35f0f-103">In diesem Thema wird beschrieben, wie der Protokollversand in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="35f0f-103">This topic describes how to remove log shipping in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="35f0f-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="35f0f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="35f0f-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="35f0f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="35f0f-106">Security</span><span class="sxs-lookup"><span data-stu-id="35f0f-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="35f0f-107">**So entfernen Sie den Protokollversand mit:**</span><span class="sxs-lookup"><span data-stu-id="35f0f-107">**To remove log shipping, using:**</span></span>  
  
     [<span data-ttu-id="35f0f-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="35f0f-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="35f0f-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="35f0f-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="35f0f-110">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="35f0f-110">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="35f0f-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="35f0f-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="35f0f-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="35f0f-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="35f0f-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="35f0f-113">Permissions</span></span>  
 <span data-ttu-id="35f0f-114">Die gespeicherten Prozeduren für den Protokollversand erfordern die Mitgliedschaft in der festen Serverrolle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="35f0f-114">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="35f0f-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="35f0f-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-log-shipping"></a><span data-ttu-id="35f0f-116">So entfernen Sie den Protokollversand</span><span class="sxs-lookup"><span data-stu-id="35f0f-116">To remove log shipping</span></span>  
  
1.  <span data-ttu-id="35f0f-117">Stellen Sie eine Verbindung mit der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] her, die derzeit als primärer Server für den Protokollversand verwendet wird, und erweitern Sie diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="35f0f-117">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is currently the log shipping primary server and expand that instance.</span></span>  
  
2.  <span data-ttu-id="35f0f-118">Erweitern Sie **Datenbanken**, klicken Sie mit der rechten Maustaste auf die primäre Datenbank für den Protokollversand, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="35f0f-118">Expand **Databases**, right-click the log shipping primary database, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="35f0f-119">Klicken Sie unter **Seite auswählen**auf **Transaktionsprotokollversand**.</span><span class="sxs-lookup"><span data-stu-id="35f0f-119">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
4.  <span data-ttu-id="35f0f-120">Entfernen Sie das Kontrollkästchen vor **Diese Datenbank als primäre Datenbank in einer Protokollversandkonfiguration aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="35f0f-120">Clear the **Enable this as a primary database in a log shipping configuration** check box.</span></span>  
  
5.  <span data-ttu-id="35f0f-121">Klicken Sie auf **OK** , um den Protokollversand aus dieser primären Datenbank zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="35f0f-121">Click **OK** to remove log shipping from this primary database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="35f0f-122">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="35f0f-122">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-log-shipping"></a><span data-ttu-id="35f0f-123">So entfernen Sie den Protokollversand</span><span class="sxs-lookup"><span data-stu-id="35f0f-123">To Remove Log Shipping</span></span>  
  
1.  <span data-ttu-id="35f0f-124">Führen Sie auf dem primären Server für den Protokollversand [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) aus, um die Informationen zur sekundären Datenbank vom primären Server zu löschen.</span><span class="sxs-lookup"><span data-stu-id="35f0f-124">On the log shipping primary server, execute [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) to delete the information about the secondary database from the primary server.</span></span>  
  
2.  <span data-ttu-id="35f0f-125">Führen Sie auf dem sekundären Server für den Protokollversand [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) aus, um die sekundäre Datenbank zu löschen.</span><span class="sxs-lookup"><span data-stu-id="35f0f-125">On the log shipping secondary server, execute [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) to delete the secondary database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="35f0f-126">Falls keine anderen sekundären Datenbanken mit der gleichen sekundären ID vorhanden sind, wird **sp_delete_log_shipping_secondary_primary** von **sp_delete_log_shipping_secondary_database** aufgerufen und löscht den Eintrag für die sekundäre ID sowie die Kopier- und Wiederherstellungsaufträge.</span><span class="sxs-lookup"><span data-stu-id="35f0f-126">If there are no other secondary databases with the same secondary ID, **sp_delete_log_shipping_secondary_primary** is invoked from **sp_delete_log_shipping_secondary_database** and deletes the entry for the secondary ID and the copy and restore jobs.</span></span>  
  
3.  <span data-ttu-id="35f0f-127">Führen Sie auf dem primären Server für den Protokollversand **sp_delete_log_shipping_primary_database** aus, um die Informationen zur Protokollversandkonfiguration vom primären Server zu löschen.</span><span class="sxs-lookup"><span data-stu-id="35f0f-127">On the log shipping primary server, execute **sp_delete_log_shipping_primary_database** to delete information about the log shipping configuration from the primary server.</span></span> <span data-ttu-id="35f0f-128">Dadurch wird auch der Sicherungsauftrag gelöscht.</span><span class="sxs-lookup"><span data-stu-id="35f0f-128">This also deletes the backup job.</span></span>  
  
4.  <span data-ttu-id="35f0f-129">Deaktivieren Sie auf dem primären Server für den Protokollversand den Sicherungsauftrag.</span><span class="sxs-lookup"><span data-stu-id="35f0f-129">On the log shipping primary server, disable the backup job.</span></span> <span data-ttu-id="35f0f-130">Weitere Informationen finden sie unter [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="35f0f-130">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
5.  <span data-ttu-id="35f0f-131">Deaktivieren Sie auf dem sekundären Server für den Protokollversand den Kopier- und Wiederherstellungsauftrag.</span><span class="sxs-lookup"><span data-stu-id="35f0f-131">On the log shipping secondary server, disable the copy and restore jobs.</span></span>  
  
6.  <span data-ttu-id="35f0f-132">Wenn Sie die sekundäre Datenbank für den Protokollversand nicht mehr verwenden, können Sie sie auch vom sekundären Server löschen.</span><span class="sxs-lookup"><span data-stu-id="35f0f-132">Optionally, if you are no longer using the log shipping secondary database, you can delete it from the secondary server.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="35f0f-133">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="35f0f-133">Related Tasks</span></span>  
  
-   [<span data-ttu-id="35f0f-134">Aktualisieren des Protokoll Versands auf SQL Server 2014 &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="35f0f-134">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="35f0f-135">Konfigurieren des Protokollversands &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="35f0f-135">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="35f0f-136">Hinzufügen einer sekundären Datenbank zu einer Protokollversandkonfiguration &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="35f0f-136">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="35f0f-137">Entfernen einer sekundären Datenbank aus einer Protokollversandkonfiguration &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="35f0f-137">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="35f0f-138">Überwachen des Protokollversands &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="35f0f-138">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="35f0f-139">Failover zu einer sekundären Datenbank für den Protokollversand &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="35f0f-139">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="35f0f-140">Disable or Enable a Job</span><span class="sxs-lookup"><span data-stu-id="35f0f-140">Disable or Enable a Job</span></span>](../../ssms/agent/disable-or-enable-a-job.md)  
  
## <a name="see-also"></a><span data-ttu-id="35f0f-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="35f0f-141">See Also</span></span>  
 <span data-ttu-id="35f0f-142">[Informationen zum Protokollversand &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="35f0f-142">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="35f0f-143">Protokollversandtabellen und gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="35f0f-143">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
