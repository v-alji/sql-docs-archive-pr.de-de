---
title: Ändern der Rollen zwischen primärem und sekundärem Protokollversandserver (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], role changes
- secondary data files [SQL Server], roles changed between
- primary databases [SQL Server]
- initial role changes [SQL Server]
- log shipping [SQL Server], failover
- failover [SQL Server], log shipping
ms.assetid: 2d7cc40a-47e8-4419-9b2b-7c69f700e806
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 52ddb89bfd18eef4cd2140bc67cf93d1800138f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718670"
---
# <a name="change-roles-between-primary-and-secondary-log-shipping-servers-sql-server"></a><span data-ttu-id="0df15-102">Ändern der Rollen zwischen primärem und sekundärem Protokollversandserver (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0df15-102">Change Roles Between Primary and Secondary Log Shipping Servers (SQL Server)</span></span>
  <span data-ttu-id="0df15-103">Nachdem Sie für eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Protokollversandkonfiguration ein Failover zu einem sekundären Server ausgeführt haben, können Sie die sekundäre Datenbank so konfigurieren, dass sie als primäre Datenbank fungiert.</span><span class="sxs-lookup"><span data-stu-id="0df15-103">After you have failed over a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log shipping configuration to a secondary server, you can configure your secondary database to act as the primary database.</span></span> <span data-ttu-id="0df15-104">Anschließend können Sie primäre und sekundäre Datenbanken je nach Bedarf austauschen.</span><span class="sxs-lookup"><span data-stu-id="0df15-104">Then, you will be able to swap primary and secondary databases as needed.</span></span>  
  
## <a name="performing-the-initial-role-change"></a><span data-ttu-id="0df15-105">Ausführen der ersten Rollenänderung</span><span class="sxs-lookup"><span data-stu-id="0df15-105">Performing the Initial Role Change</span></span>  
 <span data-ttu-id="0df15-106">Bei erstmaligem Failover zu einer sekundären Datenbank und einer anschließenden Konfiguration als neuer primärer Datenbank müssen Sie mehrere Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="0df15-106">The first time you want to fail over to the secondary database and make it your new primary database, there is a series of steps you must take.</span></span> <span data-ttu-id="0df15-107">Nachdem Sie diese anfänglichen Schritte ausgeführt haben, können Sie die Rollen zwischen der primären und sekundären Datenbank problemlos wechseln.</span><span class="sxs-lookup"><span data-stu-id="0df15-107">After you have followed these initial steps, you will be able to swap roles between the primary database and the secondary database easily.</span></span>  
  
1.  <span data-ttu-id="0df15-108">Führen Sie ein manuelles Failover von der primären Datenbank zu einer sekundären Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="0df15-108">Manually fail over from the primary database to a secondary database.</span></span> <span data-ttu-id="0df15-109">Sichern Sie das aktive Transaktionsprotokoll auf dem primären Server mit NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="0df15-109">Be sure to back up the active transaction log on your primary server with NORECOVERY.</span></span> <span data-ttu-id="0df15-110">Weitere Informationen finden Sie unter [Failover zu einer sekundären Datenbank für den Protokollversand &#40;SQL Server&#41;](fail-over-to-a-log-shipping-secondary-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0df15-110">For more information, see [Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;](fail-over-to-a-log-shipping-secondary-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="0df15-111">Deaktivieren Sie den Protokollversand-Sicherungsauftrag auf dem ursprünglichen primären Server, und kopieren Sie die Aufträge auf den ursprünglichen sekundären Server, um sie dort wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="0df15-111">Disable the log shipping backup job on the original primary server, and the copy and restore jobs on the original secondary server.</span></span>  
  
3.  <span data-ttu-id="0df15-112">Konfigurieren Sie für die sekundäre Datenbank (die neue primäre Datenbank) den Protokollversand mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0df15-112">On your secondary database (the database you want to be the new primary), configure log shipping using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="0df15-113">Weitere Informationen finden Sie unter [Konfigurieren des Protokollversands &#40;SQL Server&#41;](configure-log-shipping-sql-server.md)eingeführt.</span><span class="sxs-lookup"><span data-stu-id="0df15-113">For more information, see [Configure Log Shipping &#40;SQL Server&#41;](configure-log-shipping-sql-server.md).</span></span> <span data-ttu-id="0df15-114">Berücksichtigen Sie folgende Punkte:</span><span class="sxs-lookup"><span data-stu-id="0df15-114">Include the following steps:</span></span>  
  
    1.  <span data-ttu-id="0df15-115">Verwenden Sie dieselbe Freigabe zum Erstellen von Sicherungen, die Sie für den ursprünglichen primären Server erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="0df15-115">Use the same share for creating backups that you created for the original primary server.</span></span>  
  
    2.  <span data-ttu-id="0df15-116">Geben Sie beim Hinzufügen der sekundären Datenbank im Dialogfeld **Einstellungen für die sekundäre Datenbank** im Feld **Sekundäre Datenbank** den Namen der ursprünglichen primären Datenbank ein.</span><span class="sxs-lookup"><span data-stu-id="0df15-116">When adding the secondary database, in the **Secondary Database Settings** dialog box, enter the name of the original primary database in the **Secondary database** box.</span></span>  
  
    3.  <span data-ttu-id="0df15-117">Wählen Sie im Dialogfeld **Einstellungen für die sekundäre Datenbank** die Option **Nein, die sekundäre Datenbank ist initialisiert**aus.</span><span class="sxs-lookup"><span data-stu-id="0df15-117">In the **Secondary Database Settings** dialog box, select **No, the secondary database is initialized**.</span></span>  
  
4.  <span data-ttu-id="0df15-118">Wenn für die frühere Protokollversandkonfiguration die Protokollversandüberwachung aktiviert war, konfigurieren Sie die Protokollversandüberwachung neu, sodass die neue Protokollversandkonfiguration überwacht wird.</span><span class="sxs-lookup"><span data-stu-id="0df15-118">If log shipping monitoring was enabled on your former log shipping configuration, reconfigure log shipping monitoring to monitor the new log shipping configuration.</span></span>  <span data-ttu-id="0df15-119">Führen Sie die folgenden Befehle aus, und ersetzen Sie *database_name* durch den Namen Ihrer Datenbank:</span><span class="sxs-lookup"><span data-stu-id="0df15-119">Execute the following commands, replacing *database_name* with the name of your database:</span></span>  
  
    1.  <span data-ttu-id="0df15-120">**Auf dem neuen primären Server**</span><span class="sxs-lookup"><span data-stu-id="0df15-120">**On the new primary server**</span></span>  
  
         <span data-ttu-id="0df15-121">Führen Sie die folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen aus:</span><span class="sxs-lookup"><span data-stu-id="0df15-121">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
        ```  
        -- Statement to execute on the new primary server  
        USE msdb  
        GO  
        EXEC master.dbo.sp_change_log_shipping_secondary_database @secondary_database = N'database_name', @threshold_alert_enabled = 0;  
        GO  
        ```  
  
    2.  <span data-ttu-id="0df15-122">**Auf dem neuen sekundären Server**</span><span class="sxs-lookup"><span data-stu-id="0df15-122">**On the new secondary server**</span></span>  
  
         <span data-ttu-id="0df15-123">Führen Sie die folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen aus:</span><span class="sxs-lookup"><span data-stu-id="0df15-123">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
        ```  
        -- Statement to execute on the new secondary server  
        USE msdb  
        GO  
        EXEC master.dbo.sp_change_log_shipping_primary_database @database=N'database_name', @threshold_alert_enabled = 0;  
        GO  
        ```  
  
## <a name="swapping-roles"></a><span data-ttu-id="0df15-124">Tauschen der Rollen</span><span class="sxs-lookup"><span data-stu-id="0df15-124">Swapping Roles</span></span>  
 <span data-ttu-id="0df15-125">Nachdem Sie die oben aufgeführten Schritte für den erstmaligen Rollenwechsel ausgeführt haben, können Sie die Rollen zwischen der primären und der sekundären Datenbank mithilfe der im folgenden Abschnitt beschriebenen Schritte tauschen.</span><span class="sxs-lookup"><span data-stu-id="0df15-125">After you have completed the steps above for the initial role change, you can change roles between the primary database and the secondary database by following the steps in this section.</span></span> <span data-ttu-id="0df15-126">Führen Sie für einen Rollenwechsel die folgenden allgemeinen Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="0df15-126">To perform a role change, follow these general steps:</span></span>  
  
1.  <span data-ttu-id="0df15-127">Schalten Sie die sekundäre Datenbank online. Sichern Sie das Transaktionsprotokoll auf dem primären Server mit NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="0df15-127">Bring the secondary database online, backing up the transaction log on the primary server with NORECOVERY.</span></span>  
  
2.  <span data-ttu-id="0df15-128">Deaktivieren Sie den Protokollversand-Sicherungsauftrag auf dem ursprünglichen primären Server, und kopieren Sie die Aufträge auf den ursprünglichen sekundären Server, um sie dort wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="0df15-128">Disable the log shipping backup job on the original primary server, and the copy and restore jobs on the original secondary server.</span></span>  
  
3.  <span data-ttu-id="0df15-129">Aktivieren Sie den Protokollversand-Sicherungsauftrag auf dem sekundären Server (dem neuen primären Server), und kopieren Sie die Aufträge auf den primären Server (den neuen sekundären Server), um sie dort wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="0df15-129">Enable the log shipping backup job on the secondary server (the new primary server), and the copy and restore jobs on the primary server (the new secondary server).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0df15-130">Wenn sich der Wechsel zwischen sekundärer und primärer Datenbank für Benutzer und Anwendungen so reibungslos wie möglich gestalten soll, müssen Sie ggf. einige oder alle Metadaten für die Datenbank, wie z. B. Anmeldenamen und Aufträge, auf der neuen primären Serverinstanz neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0df15-130">When you change a secondary database to the primary database, to provide a consistent experience to users and applications, you might have to re-create some or all of the metadata for the database, such as logins and jobs, on the new primary server instance.</span></span> <span data-ttu-id="0df15-131">Weitere Informationen finden Sie unter [Verwalten von Metadaten beim Bereitstellen einer Datenbank auf einer anderen Serverinstanz &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="0df15-131">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="0df15-132">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="0df15-132">Related Tasks</span></span>  
  
-   [<span data-ttu-id="0df15-133">Failover zu einer sekundären Datenbank für den Protokollversand &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0df15-133">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="0df15-134">Verwaltung von Anmeldenamen und Aufträgen nach einem Rollenwechsel &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0df15-134">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="0df15-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0df15-135">See Also</span></span>  
 [<span data-ttu-id="0df15-136">Protokollversandtabellen und gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0df15-136">Log Shipping Tables and Stored Procedures</span></span>](log-shipping-tables-and-stored-procedures.md)  
  
  
