---
title: Aktivieren von Indizes und Einschränkungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- indexes [SQL Server], enabling
- nonclustered indexes [SQL Server], enabling a disabled index
- index enabling [SQL Server]
- disabled indexes [SQL Server], how to enable
- constraints [SQL Server], enabling
- clustered indexes, enabling disabled indexes
ms.assetid: c55c8865-322e-4ab0-ba04-ea1f56735353
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4d4e79689b80a40d00958fa557fe51df2adf9c14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622105"
---
# <a name="enable-indexes-and-constraints"></a><span data-ttu-id="19856-102">Aktivieren von Indizes und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="19856-102">Enable Indexes and Constraints</span></span>
  <span data-ttu-id="19856-103">In diesem Thema wird beschrieben, wie ein deaktivierter Index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="19856-103">This topic describes how to enable a disabled index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="19856-104">Nach dem Deaktivieren eines Indexes bleibt er deaktiviert, bis er neu erstellt oder gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="19856-104">After an index is disabled, it remains in a disabled state until it is rebuilt or dropped</span></span>  
  
 <span data-ttu-id="19856-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="19856-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="19856-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="19856-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="19856-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="19856-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="19856-108">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="19856-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="19856-109">**So aktivieren Sie einen deaktivierten Index mit:**</span><span class="sxs-lookup"><span data-stu-id="19856-109">**To enable a disabled index, using:**</span></span>  
  
     [<span data-ttu-id="19856-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="19856-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="19856-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="19856-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="19856-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="19856-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="19856-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="19856-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="19856-114">Nachdem der Index neu erstellt wurde, müssen alle Einschränkungen, die aufgrund der Deaktivierung des Indexes deaktiviert wurden, manuell aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="19856-114">After rebuilding the index, any constraints that were disabled because of disabling the index must be manually enabled.</span></span> <span data-ttu-id="19856-115">PRIMARY KEY- und UNIQUE-Einschränkungen werden durch Neuerstellen des zugehörigen Indexes aktiviert.</span><span class="sxs-lookup"><span data-stu-id="19856-115">PRIMARY KEY and UNIQUE constraints are enabled by rebuilding the associated index.</span></span> <span data-ttu-id="19856-116">Dieser Index muss neu erstellt (aktiviert) werden, bevor Sie FOREIGN KEY-Einschränkungen aktivieren können, die auf die PRIMARY KEY- oder UNIQUE-Einschränkung verweisen.</span><span class="sxs-lookup"><span data-stu-id="19856-116">This index must be rebuilt (enabled) before you can enable FOREIGN KEY constraints that reference the PRIMARY KEY or UNIQUE constraint.</span></span> <span data-ttu-id="19856-117">FOREIGN KEY-Einschränkungen werden mithilfe der ALTER TABLE CHECK CONSTRAINT-Anweisung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="19856-117">FOREIGN KEY constraints are enabled by using the ALTER TABLE CHECK CONSTRAINT statement.</span></span>  
  
-   <span data-ttu-id="19856-118">Das Neuerstellen eines deaktivierten gruppierten Indexes kann nicht ausgeführt werden, wenn die Option ONLINE auf ON festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="19856-118">Rebuilding a disabled clustered index cannot be performed when the ONLINE option is set to ON.</span></span>  
  
-   <span data-ttu-id="19856-119">Wenn der gruppierte Index deaktiviert oder aktiviert und der nicht gruppierte Index deaktiviert ist, besitzt die Aktion des gruppierten Indexes die folgenden Auswirkungen auf den deaktivierten nicht gruppierten Index.</span><span class="sxs-lookup"><span data-stu-id="19856-119">When the clustered index is disabled or enabled and the nonclustered index is disabled, the clustered index action has the following results on the disabled nonclustered index.</span></span>  
  
    |<span data-ttu-id="19856-120">Gruppierte Index-Aktion</span><span class="sxs-lookup"><span data-stu-id="19856-120">Clustered Index Action</span></span>|<span data-ttu-id="19856-121">Deaktivierter nicht gruppierter Index ...</span><span class="sxs-lookup"><span data-stu-id="19856-121">Disabled Nonclustered Index ...</span></span>|  
    |----------------------------|-----------------------------------|  
    |<span data-ttu-id="19856-122">ALTER INDEX REBUILD</span><span class="sxs-lookup"><span data-stu-id="19856-122">ALTER INDEX REBUILD.</span></span>|<span data-ttu-id="19856-123">Bleibt deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="19856-123">Remains disabled.</span></span>|  
    |<span data-ttu-id="19856-124">ALTER INDEX ALL REBUILD.</span><span class="sxs-lookup"><span data-stu-id="19856-124">ALTER INDEX ALL REBUILD.</span></span>|<span data-ttu-id="19856-125">Wird neu erstellt und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="19856-125">Is rebuilt and enabled.</span></span>|  
    |<span data-ttu-id="19856-126">DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="19856-126">DROP INDEX.</span></span>|<span data-ttu-id="19856-127">Bleibt deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="19856-127">Remains disabled.</span></span>|  
    |<span data-ttu-id="19856-128">CREATE INDEX WITH DROP_EXISTING.</span><span class="sxs-lookup"><span data-stu-id="19856-128">CREATE INDEX WITH DROP_EXISTING.</span></span>|<span data-ttu-id="19856-129">Bleibt deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="19856-129">Remains disabled.</span></span>|  
  
     <span data-ttu-id="19856-130">Beim Erstellen eines neuen gruppierten Index tritt das gleiche Verhalten auf wie bei ALTER INDEX ALL REBUILD.</span><span class="sxs-lookup"><span data-stu-id="19856-130">Creating a new clustered index, behaves the same as ALTER INDEX ALL REBUILD.</span></span>  
  
-   <span data-ttu-id="19856-131">Zulässige Aktionen für nicht gruppierte Indizes, die einem gruppierten Index zugeordnet sind, hängen vom Status (deaktiviert oder aktiviert) der beiden Indextypen ab.</span><span class="sxs-lookup"><span data-stu-id="19856-131">Allowed actions on nonclustered indexes associated with a clustered index depend on the state, whether disabled or enabled, of both index types.</span></span> <span data-ttu-id="19856-132">In der folgenden Tabelle werden die zulässigen Aktionen für nicht gruppierte Indizes zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="19856-132">The following table summarizes the allowed actions on nonclustered indexes.</span></span>  
  
    |<span data-ttu-id="19856-133">Nicht gruppierte Index-Aktion</span><span class="sxs-lookup"><span data-stu-id="19856-133">Nonclustered Index Action</span></span>|<span data-ttu-id="19856-134">Wenn der gruppierte und der nicht gruppierte Index deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="19856-134">When both the clustered and nonclustered indexes are disabled.</span></span>|<span data-ttu-id="19856-135">Wenn der gruppierte Index aktiviert ist und der nicht gruppierte Index einen beliebigen Zustand aufweist.</span><span class="sxs-lookup"><span data-stu-id="19856-135">When the clustered index is enabled and the nonclustered index is in either state.</span></span>|  
    |-------------------------------|--------------------------------------------------------------------|----------------------------------------------------------------------------------------|  
    |<span data-ttu-id="19856-136">ALTER INDEX REBUILD</span><span class="sxs-lookup"><span data-stu-id="19856-136">ALTER INDEX REBUILD.</span></span>|<span data-ttu-id="19856-137">Die Aktion erzeugt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="19856-137">The action fails.</span></span>|<span data-ttu-id="19856-138">Die Aktion ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="19856-138">The action succeeds.</span></span>|  
    |<span data-ttu-id="19856-139">DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="19856-139">DROP INDEX.</span></span>|<span data-ttu-id="19856-140">Die Aktion ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="19856-140">The action succeeds.</span></span>|<span data-ttu-id="19856-141">Die Aktion ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="19856-141">The action succeeds.</span></span>|  
    |<span data-ttu-id="19856-142">CREATE INDEX WITH DROP_EXISTING.</span><span class="sxs-lookup"><span data-stu-id="19856-142">CREATE INDEX WITH DROP_EXISTING.</span></span>|<span data-ttu-id="19856-143">Die Aktion erzeugt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="19856-143">The action fails.</span></span>|<span data-ttu-id="19856-144">Die Aktion ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="19856-144">The action succeeds.</span></span>|  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="19856-145">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="19856-145">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="19856-146">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="19856-146">Permissions</span></span>  
 <span data-ttu-id="19856-147">Erfordert die ALTER-Berechtigung in der Tabelle oder Sicht.</span><span class="sxs-lookup"><span data-stu-id="19856-147">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="19856-148">Bei der Verwendung von DBCC DBREINDEX muss der Benutzer die Tabelle besitzen oder Mitglied der festen Serverrolle **sysadmin** oder der festen Datenbankrollen **db_ddladmin** und **db_owner** sein.</span><span class="sxs-lookup"><span data-stu-id="19856-148">If using DBCC DBREINDEX, eser must either own the table or be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="19856-149">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="19856-149">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enable-a-disabled-index"></a><span data-ttu-id="19856-150">So aktivieren Sie einen deaktivierten Index</span><span class="sxs-lookup"><span data-stu-id="19856-150">To enable a disabled index</span></span>  
  
1.  <span data-ttu-id="19856-151">Klicken Sie in Objekt-Explorer auf das Pluszeichen, um die Datenbank zu erweitern, die die Tabelle enthält, auf der Sie einen Index aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="19856-151">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to enable an index.</span></span>  
  
2.  <span data-ttu-id="19856-152">Klicken Sie auf das Pluszeichen, um den Ordner **Tabellen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="19856-152">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="19856-153">Klicken Sie auf das Pluszeichen, um die Tabelle zu erweitern, in der Sie einen Index aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="19856-153">Click the plus sign to expand the table on which you want to enable an index.</span></span>  
  
4.  <span data-ttu-id="19856-154">Klicken Sie auf das Pluszeichen, um den Ordner **Indizes** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="19856-154">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="19856-155">Klicken Sie mit der rechten Maustaste auf den Index, den Sie aktivieren möchten, und wählen Sie **Neu erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="19856-155">Right-click the index you want to enable and select **Rebuild**.</span></span>  
  
6.  <span data-ttu-id="19856-156">Überprüfen Sie im Dialogfeld **Indizes neu erstellen** , dass der richtige Index im Raster **Neu zu erstellende Indizes** ausgewählt ist, und klicken sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="19856-156">In the **Rebuild Indexes** dialog box, verify that the correct index is in the **Indexes to rebuild** grid and click **OK**.</span></span>  
  
#### <a name="to-enable-all-indexes-on-a-table"></a><span data-ttu-id="19856-157">So aktivieren Sie alle Indizes auf einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="19856-157">To enable all indexes on a table</span></span>  
  
1.  <span data-ttu-id="19856-158">Klicken Sie in Objekt-Explorer auf das Pluszeichen, um die Datenbank zu erweitern, die die Tabelle enthält, in der Sie die Indizes aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="19856-158">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to enable the indexes.</span></span>  
  
2.  <span data-ttu-id="19856-159">Klicken Sie auf das Pluszeichen, um den Ordner **Tabellen** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="19856-159">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="19856-160">Klicken Sie auf das Pluszeichen, um die Tabelle zu erweitern, in der Sie die Indizes aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="19856-160">Click the plus sign to expand the table on which you want to enable the indexes.</span></span>  
  
4.  <span data-ttu-id="19856-161">Klicken Sie mit der rechten Maustaste auf den Ordner **Indizes** , und wählen Sie **Alle neu erstellen**.</span><span class="sxs-lookup"><span data-stu-id="19856-161">Right-click the **Indexes** folder and select **Rebuild All**.</span></span>  
  
5.  <span data-ttu-id="19856-162">Überprüfen Sie im Dialogfeld **Indizes neu erstellen** , dass die richtigen Indizes im Raster **Neu zu erstellende Indizes** ausgewählt sind, und klicken sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="19856-162">In the **Rebuild Indexes** dialog box, verify that the correct indexes are in the **Indexes to rebuild** grid and click **OK**.</span></span> <span data-ttu-id="19856-163">Um einen Index aus dem Raster **Neu zu erstellende Indizes** zu entfernen, wählen Sie den Index aus, und drücken Sie die ENTF-Taste.</span><span class="sxs-lookup"><span data-stu-id="19856-163">To remove an index from the **Indexes to rebuild** grid, select the index and then press the Delete key.</span></span>  
  
 <span data-ttu-id="19856-164">Die folgenden Informationen sind im Dialogfeld **Indizes neu erstellen** verfügbar:</span><span class="sxs-lookup"><span data-stu-id="19856-164">The following information is available in the **Rebuild Indexes** dialog box:</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="19856-165">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="19856-165">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-a-disabled-index-using-alter-index"></a><span data-ttu-id="19856-166">So aktivieren Sie einen deaktivierten Index mit ALTER INDEX</span><span class="sxs-lookup"><span data-stu-id="19856-166">To enable a disabled index using ALTER INDEX</span></span>  
  
1.  <span data-ttu-id="19856-167">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="19856-167">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="19856-168">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="19856-168">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="19856-169">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="19856-169">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Enables the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table.  
  
    ALTER INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
    REBUILD;   
    GO  
    ```  
  
#### <a name="to-enable-a-disabled-index-using-create-index"></a><span data-ttu-id="19856-170">So aktivieren Sie einen deaktivierten Index mit CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="19856-170">To enable a disabled index using CREATE INDEX</span></span>  
  
1.  <span data-ttu-id="19856-171">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="19856-171">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="19856-172">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="19856-172">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="19856-173">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="19856-173">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- re-creates the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table  
    -- using the OrganizationLevel and OrganizationNode columns  
    -- and then deletes the existing IX_Employee_OrganizationLevel_OrganizationNode index  
    CREATE INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
       (OrganizationLevel, OrganizationNode)  
    WITH (DROP_EXISTING = ON);  
    GO  
    ```  
  
#### <a name="to-enable-a-disabled-index-using-dbcc-dbreindex"></a><span data-ttu-id="19856-174">So aktivieren Sie einen deaktivierten Index mit DBCC DBREINDEX</span><span class="sxs-lookup"><span data-stu-id="19856-174">To enable a disabled index using DBCC DBREINDEX</span></span>  
  
1.  <span data-ttu-id="19856-175">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="19856-175">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="19856-176">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="19856-176">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="19856-177">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="19856-177">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- enables the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table  
    DBCC DBREINDEX ("HumanResources.Employee", IX_Employee_OrganizationLevel_OrganizationNode);  
    GO  
    ```  
  
#### <a name="to-enable-all-indexes-on-a-table-using-alter-index"></a><span data-ttu-id="19856-178">So aktivieren Sie alle Indizes auf einer Tabelle mit ALTER INDEX</span><span class="sxs-lookup"><span data-stu-id="19856-178">To enable all indexes on a table using ALTER INDEX</span></span>  
  
1.  <span data-ttu-id="19856-179">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="19856-179">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="19856-180">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="19856-180">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="19856-181">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="19856-181">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- enables all indexes  
    -- on the HumanResources.Employee table  
    ALTER INDEX ALL ON HumanResources.Employee  
    REBUILD;  
    GO  
    ```  
  
#### <a name="to-enable-all-indexes-on-a-table-using-dbcc-dbreindex"></a><span data-ttu-id="19856-182">So aktivieren Sie alle Indizes auf einer Tabelle mit DBCC DBREINDEX</span><span class="sxs-lookup"><span data-stu-id="19856-182">To enable all indexes on a table using DBCC DBREINDEX</span></span>  
  
1.  <span data-ttu-id="19856-183">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="19856-183">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="19856-184">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="19856-184">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="19856-185">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="19856-185">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- enables all indexes  
    -- on the HumanResources.Employee table  
    DBCC DBREINDEX ("HumanResources.Employee", " ");  
    GO  
    ```  
  
 <span data-ttu-id="19856-186">Weitere Informationen finden Sie unter [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql), [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) und [DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="19856-186">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql), [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql), and [DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql).</span></span>  
  
  
