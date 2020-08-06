---
title: Verknüpfen einer sekundären Datenbank mit einer Verfügbarkeitsgruppe (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.joindbs.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- secondary databases [SQL Server]
- Availability Groups [SQL Server], joining
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: fd7efe79-c1f9-497d-bfe7-b2a2b2321cf5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b0d79325bcde33d13688003de079a42a9601cc41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617268"
---
# <a name="join-a-secondary-database-to-an-availability-group-sql-server"></a><span data-ttu-id="08fed-102">Verknüpfen einer sekundären Datenbank mit einer Verfügbarkeitsgruppe (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="08fed-102">Join a Secondary Database to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="08fed-103">In diesem Thema wird beschrieben, wie eine sekundäre Datenbank in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]mithilfe von [!INCLUDE[tsql](../../../includes/tsql-md.md)], [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]oder PowerShell mit einer AlwaysOn-Verfügbarkeitsgruppe verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="08fed-103">This topic explains how to join a secondary database to an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="08fed-104">Nachdem Sie eine sekundäre Datenbank auf ein sekundäres Replikat vorbereitet haben, müssen Sie die Datenbank so schnell wie möglich mit der Verfügbarkeitsgruppe verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="08fed-104">After you prepare a secondary database for a secondary replica, you need to join the database to the availability group as soon as possible.</span></span> <span data-ttu-id="08fed-105">So wird die Datenverschiebung aus der entsprechenden primären Datenbank in die sekundäre Datenbank gestartet.</span><span class="sxs-lookup"><span data-stu-id="08fed-105">This will start data movement from the corresponding primary database to the secondary database.</span></span>  
  
-   <span data-ttu-id="08fed-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="08fed-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="08fed-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="08fed-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="08fed-108">Security</span><span class="sxs-lookup"><span data-stu-id="08fed-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="08fed-109">**So bereiten Sie eine sekundäre Datenbank vor mit:**</span><span class="sxs-lookup"><span data-stu-id="08fed-109">**To prepare a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="08fed-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="08fed-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="08fed-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="08fed-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="08fed-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="08fed-112">PowerShell</span></span>](#PowerShellProcedure)  
  
> [!NOTE]  
>  <span data-ttu-id="08fed-113">Informationen dazu, was geschieht, nachdem eine sekundäre Datenbank der Gruppe angehört, finden Sie unter [Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="08fed-113">For information about what happens after a secondary database joins the group, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="08fed-114">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="08fed-114">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="08fed-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="08fed-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="08fed-116">Sie müssen mit der Serverinstanz verbunden sein, auf der das sekundäre Replikat gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="08fed-116">You must be connected to the server instance that hosts the secondary replica.</span></span>  
  
-   <span data-ttu-id="08fed-117">Das sekundäre Replikat muss bereits mit der Verfügbarkeitsgruppe verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="08fed-117">The secondary replica must already be joined to the availability group.</span></span> <span data-ttu-id="08fed-118">Weitere Informationen finden Sie unter [Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md)mit einer Always On-Verfügbarkeitsgruppe verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="08fed-118">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
-   <span data-ttu-id="08fed-119">Die sekundäre Datenbank muss vor kurzem vorbereitet worden sein.</span><span class="sxs-lookup"><span data-stu-id="08fed-119">The secondary database must have been prepared recently.</span></span> <span data-ttu-id="08fed-120">Weitere Informationen finden Sie unter [Manuelles Vorbereiten einer sekundären Datenbank auf eine Verfügbarkeitsgruppe &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)erstellt und konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="08fed-120">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="08fed-121">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="08fed-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="08fed-122">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="08fed-122">Permissions</span></span>  
 <span data-ttu-id="08fed-123">Erfordert die ALTER AVAILABILITY GROUP-Berechtigung für die Verfügbarkeitsgruppe, die CONTROL AVAILABILITY GROUP-Berechtigung, die ALTER ANY AVAILABILITY GROUP-Berechtigung oder die CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="08fed-123">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="08fed-124">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="08fed-124">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="08fed-125">**So verknüpfen Sie eine sekundäre Datenbank mit einer Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="08fed-125">**To join a secondary database to an availability group**</span></span>  
  
1.  <span data-ttu-id="08fed-126">Stellen Sie im Objekt-Explorer eine Verbindung mit der Serverinstanz her, die das sekundäre Replikat hostet, und erweitern Sie die Serverstruktur.</span><span class="sxs-lookup"><span data-stu-id="08fed-126">In Object Explorer, connect to the server instance that hosts the secondary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="08fed-127">Erweitern Sie den Knoten **Hohe Verfügbarkeit (immer aktiviert)** und den Knoten **Verfügbarkeitsgruppen** .</span><span class="sxs-lookup"><span data-stu-id="08fed-127">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="08fed-128">Erweitern Sie die Verfügbarkeitsgruppe, die Sie ändern möchten, und erweitern Sie den Knoten **Verfügbarkeitsdatenbanken** .</span><span class="sxs-lookup"><span data-stu-id="08fed-128">Expand the availability group that you want to change, and expand the **Availability Databases** node.</span></span>  
  
4.  <span data-ttu-id="08fed-129">Klicken Sie mit der rechten Maustaste auf die Datenbank, und klicken Sie auf **Verfügbarkeitsgruppe beitreten**.</span><span class="sxs-lookup"><span data-stu-id="08fed-129">Right-click the database, and click **Join to Availability Group**.</span></span>  
  
5.  <span data-ttu-id="08fed-130">Das Dialogfeld **Datenbanken mit Verfügbarkeitsgruppe verknüpfen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="08fed-130">This opens the **Join Databases to Availability Group** dialog box.</span></span> <span data-ttu-id="08fed-131">Überprüfen Sie den Namen der Verfügbarkeitsgruppe, der in der Titelleiste angezeigt wird, und den im Raster angezeigten Datenbanknamen bzw. andere Namen, und klicken Sie auf **OK**, oder klicken Sie auf **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="08fed-131">Verify the availability group name, which is displayed on the title bar, and database name or names displayed in the grid, and click **OK**, or click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="08fed-132">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="08fed-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="08fed-133">**So verknüpfen Sie eine sekundäre Datenbank mit einer Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="08fed-133">**To join a secondary database to an availability group**</span></span>  
  
1.  <span data-ttu-id="08fed-134">Stellen Sie eine Verbindung mit der Serverinstanz her, die das sekundäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="08fed-134">Connect to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="08fed-135">Verwenden Sie die [SET HADR-Klausel der ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) -Anweisung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="08fed-135">Use the [SET HADR clause of the ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) statement, as follows:</span></span>  
  
     <span data-ttu-id="08fed-136">ALTER DATABASE *Datenbankname* SET HADR AVAILABILITY GROUP = *Gruppenname*,</span><span class="sxs-lookup"><span data-stu-id="08fed-136">ALTER DATABASE *database_name* SET HADR AVAILABILITY GROUP = *group_name*</span></span>  
  
     <span data-ttu-id="08fed-137">dabei ist *Datenbankname* der Name einer hinzuzufügenden Datenbank und *Gruppenname* der Name der Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="08fed-137">where *database_name* is the name of a database to be joined and *group_name* is the name of the availability group.</span></span>  
  
     <span data-ttu-id="08fed-138">Im folgenden Beispiel wird die sekundäre Datenbank `Db1` mit dem lokalen sekundären Replikat der `MyAG`-Verfügbarkeitsgruppe verknüpft.</span><span class="sxs-lookup"><span data-stu-id="08fed-138">The following example joins the secondary database, `Db1`, to the local secondary replica of the `MyAG` availability group.</span></span>  
  
    ```sql
    ALTER DATABASE Db1 SET HADR AVAILABILITY GROUP = MyAG;  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="08fed-139">Unter [Erstellen einer Verfügbarkeitsgruppe &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md) können Sie die Verwendung dieser [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Anweisung im Kontext sehen.</span><span class="sxs-lookup"><span data-stu-id="08fed-139">To see this [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement used in context, see [Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="08fed-140">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="08fed-140">Using PowerShell</span></span>  
 <span data-ttu-id="08fed-141">**So verknüpfen Sie eine sekundäre Datenbank mit einer Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="08fed-141">**To join a secondary database to an availability group**</span></span>  
  
1.  <span data-ttu-id="08fed-142">Ändern Sie das Verzeichnis (`cd`) in die Serverinstanz, die das sekundäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="08fed-142">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="08fed-143">Verwenden Sie das `Add-SqlAvailabilityDatabase`-Cmdlet, um eine oder mehrere sekundäre Datenbanken mit der Verfügbarkeitsgruppe zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="08fed-143">Use the `Add-SqlAvailabilityDatabase` cmdlet to join one or more secondary databases to the availability group.</span></span>  
  
     <span data-ttu-id="08fed-144">Beispielsweise wird durch den folgenden Befehl die sekundäre Datenbank `Db1`mit der Verfügbarkeitsgruppe `MyAG` in einer der Serverinstanzen verknüpft, von denen ein sekundäres Replikat gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="08fed-144">For example, the following command joins a secondary database, `Db1`, to the availability group `MyAG` on one of the server instances that hosts a secondary replica.</span></span>  
  
    ```powershell
    Add-SqlAvailabilityDatabase -Path SQLSERVER:\SQL\SecondaryServer\InstanceName\AvailabilityGroups\MyAG -Database "Db1"  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="08fed-145">Um die Syntax eines Cmdlets anzuzeigen, verwenden Sie das `Get-Help`-Cmdlet in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="08fed-145">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="08fed-146">Weitere Informationen finden Sie unter [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="08fed-146">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="08fed-147">**Einrichten und Verwenden des SQL Server PowerShell-Anbieters**</span><span class="sxs-lookup"><span data-stu-id="08fed-147">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="08fed-148">SQL Server PowerShell-Anbieter</span><span class="sxs-lookup"><span data-stu-id="08fed-148">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="08fed-149">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="08fed-149">Related Tasks</span></span>  
  
-   [<span data-ttu-id="08fed-150">Verknüpfen eines sekundären Replikats mit einer Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="08fed-150">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="08fed-151">Manuelles Vorbereiten einer sekundären Datenbank auf eine Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="08fed-151">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="08fed-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="08fed-152">See Also</span></span>  
 <span data-ttu-id="08fed-153">[ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="08fed-153">[ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql) </span></span>  
 <span data-ttu-id="08fed-154">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="08fed-154">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="08fed-155">Problembehandlung AlwaysOn-Verfügbarkeitsgruppen Konfigurations &#40;SQL Server&#41;gelöscht</span><span class="sxs-lookup"><span data-stu-id="08fed-155">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
