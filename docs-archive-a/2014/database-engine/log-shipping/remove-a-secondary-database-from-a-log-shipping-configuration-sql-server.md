---
title: Entfernen einer sekundären Datenbank aus einer Protokollversandkonfiguration (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- deleting secondary databases
- secondary databases [SQL Server], in log shipping
- removing secondary databases
- secondary data files [SQL Server], removing
- log shipping [SQL Server], secondary databases
ms.assetid: ebe368a4-ca1c-45d0-9a71-3ddbd5b26a8e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 119f2762d41d0787b6b3279507e9671e89fddfca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619316"
---
# <a name="remove-a-secondary-database-from-a-log-shipping-configuration-sql-server"></a><span data-ttu-id="90afb-102">Entfernen einer sekundären Datenbank aus einer Protokollversandkonfiguration (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="90afb-102">Remove a Secondary Database from a Log Shipping Configuration (SQL Server)</span></span>
  <span data-ttu-id="90afb-103">In diesem Thema wird beschrieben, wie eine sekundäre Datenbank für den Protokollversand in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="90afb-103">This topic describes how to remove a log shipping secondary database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="90afb-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="90afb-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="90afb-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="90afb-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="90afb-106">Security</span><span class="sxs-lookup"><span data-stu-id="90afb-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="90afb-107">**So entfernen Sie eine sekundäre Datenbank für den Protokollversand mit:**</span><span class="sxs-lookup"><span data-stu-id="90afb-107">**To remove a log shipping secondary database, using:**</span></span>  
  
     [<span data-ttu-id="90afb-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="90afb-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="90afb-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="90afb-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="90afb-110">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="90afb-110">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="90afb-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="90afb-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="90afb-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="90afb-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="90afb-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="90afb-113">Permissions</span></span>  
 <span data-ttu-id="90afb-114">Die gespeicherten Prozeduren für den Protokollversand erfordern die Mitgliedschaft in der festen Serverrolle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="90afb-114">The log-shipping stored procedures require membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="90afb-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="90afb-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-a-log-shipping-secondary-database"></a><span data-ttu-id="90afb-116">So entfernen Sie eine sekundäre Datenbank für den Protokollversand</span><span class="sxs-lookup"><span data-stu-id="90afb-116">To remove a log shipping secondary database</span></span>  
  
1.  <span data-ttu-id="90afb-117">Stellen Sie eine Verbindung mit der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] her, die derzeit als primärer Server für den Protokollversand verwendet wird, und erweitern Sie diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="90afb-117">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is currently the log shipping primary server and expand that instance.</span></span>  
  
2.  <span data-ttu-id="90afb-118">Erweitern Sie **Datenbanken**, klicken Sie mit der rechten Maustaste auf die primäre Datenbank für den Protokollversand, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="90afb-118">Expand **Databases**, right-click the log shipping primary database, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="90afb-119">Klicken Sie unter **Seite auswählen**auf **Transaktionsprotokollversand**.</span><span class="sxs-lookup"><span data-stu-id="90afb-119">Under **Select a page**, click **Transaction Log Shipping**.</span></span>  
  
4.  <span data-ttu-id="90afb-120">Klicken Sie unter **Sekundäre Serverinstanzen und Datenbanken**auf die Datenbank, die Sie entfernen wollen.</span><span class="sxs-lookup"><span data-stu-id="90afb-120">Under **Secondary server instances and databases**, click the database you want to remove.</span></span>  
  
5.  <span data-ttu-id="90afb-121">Klicken Sie auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="90afb-121">Click **Remove**.</span></span>  
  
6.  <span data-ttu-id="90afb-122">Klicken Sie auf **OK** , um die Konfiguration zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="90afb-122">Click **OK** to update the configuration.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="90afb-123">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="90afb-123">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-a-secondary-database"></a><span data-ttu-id="90afb-124">So entfernen Sie eine sekundäre Datenbank</span><span class="sxs-lookup"><span data-stu-id="90afb-124">To Remove a Secondary Database</span></span>  
  
1.  <span data-ttu-id="90afb-125">Führen Sie auf dem primären Server [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) aus, um die Informationen zur sekundären Datenbank vom primären Server zu löschen.</span><span class="sxs-lookup"><span data-stu-id="90afb-125">On the primary server, execute [sp_delete_log_shipping_primary_secondary](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql) to delete the information about the secondary database from the primary server.</span></span>  
  
2.  <span data-ttu-id="90afb-126">Führen Sie auf dem sekundären Server [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) aus, um die sekundäre Datenbank zu löschen.</span><span class="sxs-lookup"><span data-stu-id="90afb-126">On the secondary server, execute [sp_delete_log_shipping_secondary_database](/sql/relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql) to delete the secondary database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="90afb-127">Falls keine anderen sekundären Datenbanken mit der gleichen sekundären ID vorhanden sind, wird **sp_delete_log_shipping_secondary_primary** von **sp_delete_log_shipping_secondary_database** aufgerufen und löscht den Eintrag für die sekundäre ID sowie die Kopier- und Wiederherstellungsaufträge.</span><span class="sxs-lookup"><span data-stu-id="90afb-127">If there are no other secondary databases with the same secondary ID, **sp_delete_log_shipping_secondary_primary** is invoked from **sp_delete_log_shipping_secondary_database** and deletes the entry for the secondary ID and the copy and restore jobs.</span></span>  
  
3.  <span data-ttu-id="90afb-128">Deaktivieren Sie auf dem sekundären Server den Kopier- und Wiederherstellungsauftrag.</span><span class="sxs-lookup"><span data-stu-id="90afb-128">On the secondary server, disable the copy and restore jobs.</span></span> <span data-ttu-id="90afb-129">Weitere Informationen finden sie unter [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="90afb-129">For more information, see [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="90afb-130">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="90afb-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="90afb-131">Aktualisieren des Protokoll Versands auf SQL Server 2014 &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="90afb-131">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="90afb-132">Konfigurieren des Protokollversands &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="90afb-132">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="90afb-133">Hinzufügen einer sekundären Datenbank zu einer Protokollversandkonfiguration &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="90afb-133">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="90afb-134">Entfernen des Protokollversands &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="90afb-134">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="90afb-135">Anzeigen des Protokollversandberichts &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="90afb-135">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="90afb-136">Überwachen des Protokollversands &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="90afb-136">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="90afb-137">Failover zu einer sekundären Datenbank für den Protokollversand &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="90afb-137">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="90afb-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90afb-138">See Also</span></span>  
 <span data-ttu-id="90afb-139">[Informationen zum Protokollversand &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="90afb-139">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="90afb-140">Protokollversandtabellen und gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="90afb-140">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
