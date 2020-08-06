---
title: Anzeigen oder Ändern von Servereigenschaften (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- viewing server properties
- server properties [SQL Server]
- displaying server properties
- servers [SQL Server], viewing
ms.assetid: 55f3ac04-5626-4ad2-96bd-a1f1b079659d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 415d4e2d1aaa3166ae4df2dea53b34e064544e06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697150"
---
# <a name="view-or-change-server-properties-sql-server"></a><span data-ttu-id="8d38a-102">Anzeigen oder Ändern von Servereigenschaften (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8d38a-102">View or Change Server Properties (SQL Server)</span></span>
  <span data-ttu-id="8d38a-103">In diesem Thema wird beschrieben, wie Sie die Eigenschaften einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]oder dem SQL Server-Konfigurations-Manager anzeigen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="8d38a-103">This topic describes how to view or change the properties of an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Configuration Manager.</span></span>  
  
 <span data-ttu-id="8d38a-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="8d38a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8d38a-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="8d38a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8d38a-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="8d38a-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8d38a-107">Security</span><span class="sxs-lookup"><span data-stu-id="8d38a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8d38a-108">**Anzeigen oder Ändern von Servereigenschaften mit:**</span><span class="sxs-lookup"><span data-stu-id="8d38a-108">**To view or change server properties, using:**</span></span>  
  
     [<span data-ttu-id="8d38a-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8d38a-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8d38a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8d38a-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="8d38a-111">SQL Server-Konfigurations-Manager</span><span class="sxs-lookup"><span data-stu-id="8d38a-111">SQL Server Configuration Manager</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="8d38a-112">**Nachverfolgung:**  [Nach dem Ändern von Servereigenschaften](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="8d38a-112">**Follow Up:**  [After you change server properties](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8d38a-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="8d38a-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8d38a-114">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="8d38a-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8d38a-115">Wenn Sie sp_configure verwenden, müssen Sie nach dem Festlegen einer Konfigurationsoption entweder RECONFIGURE oder RECONFIGURE WITH OVERRIDE ausführen.</span><span class="sxs-lookup"><span data-stu-id="8d38a-115">When using sp_configure, you must run either RECONFIGURE or RECONFIGURE WITH OVERRIDE after setting a configuration option.</span></span> <span data-ttu-id="8d38a-116">Die RECONFIGURE WITH OVERRIDE-Anweisung ist in der Regel für Konfigurationsoptionen reserviert, die nur mit äußerster Vorsicht verwendet werden sollten.</span><span class="sxs-lookup"><span data-stu-id="8d38a-116">The RECONFIGURE WITH OVERRIDE statement is usually reserved for configuration options that should be used with extreme caution.</span></span> <span data-ttu-id="8d38a-117">Sie können jedoch RECONFIGURE WITH OVERRIDE für alle Konfigurationsoptionen und auch statt RECONFIGURE verwenden.</span><span class="sxs-lookup"><span data-stu-id="8d38a-117">However, RECONFIGURE WITH OVERRIDE works for all configuration options, and you can use it in place of RECONFIGURE.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8d38a-118">RECONFIGURE wird in einer Transaktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8d38a-118">RECONFIGURE executes within a transaction.</span></span> <span data-ttu-id="8d38a-119">Schlägt einer der RECONFIGURE-Vorgänge fehl, tritt keiner der RECONFIGURE-Vorgänge in Kraft.</span><span class="sxs-lookup"><span data-stu-id="8d38a-119">If any of the reconfigure operations fail, none of the reconfigure operations will take effect.</span></span>  
  
-   <span data-ttu-id="8d38a-120">Auf einigen Eigenschaftenseiten werden Informationen angezeigt, die aus der Windows-Verwaltungsinstrumentation (WMI, Windows Management Instrumentation) abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="8d38a-120">Some property pages present information obtained via Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="8d38a-121">Zum Anzeigen dieser Seiten muss die WMI auf dem Computer installiert sein, auf dem [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8d38a-121">To display those pages, WMI must be installed on the computer running [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8d38a-122">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8d38a-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8d38a-123">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8d38a-123">Permissions</span></span>  
 <span data-ttu-id="8d38a-124">Weitere Informationen finden Sie unter [Rollen auf Serverebene](../../relational-databases/security/authentication-access/server-level-roles.md).</span><span class="sxs-lookup"><span data-stu-id="8d38a-124">For more information, see [Server-Level Roles](../../relational-databases/security/authentication-access/server-level-roles.md).</span></span>  
  
 <span data-ttu-id="8d38a-125">Ausführungs Berechtigungen für `sp_configure` ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="8d38a-125">Execute permissions on `sp_configure` with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="8d38a-126">Zum Ausführen `sp_configure` von mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="8d38a-126">To execute `sp_configure` with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="8d38a-127">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8d38a-127">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8d38a-128">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8d38a-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-server-properties"></a><span data-ttu-id="8d38a-129">So zeigen Sie Servereigenschaften an oder ändern sie</span><span class="sxs-lookup"><span data-stu-id="8d38a-129">To view or change server properties</span></span>  
  
1.  <span data-ttu-id="8d38a-130">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="8d38a-130">In Object Explorer, right-click a server, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="8d38a-131">Klicken Sie im Dialogfeld **Servereigenschaften** auf eine Seite, für die Sie Serverinformationen anzeigen oder ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="8d38a-131">In the **Server Properties** dialog box, click a page to view or change server information about that page.</span></span> <span data-ttu-id="8d38a-132">Einige Eigenschaften sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="8d38a-132">Some properties are read-only.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8d38a-133">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8d38a-133">Using Transact-SQL</span></span>  
  
#### <a name="to-view-server-properties-by-using-the-serverproperty-built-in-function"></a><span data-ttu-id="8d38a-134">So zeigen Sie Servereigenschaften mit der integrierten SERVERPROPERTY-Funktion an</span><span class="sxs-lookup"><span data-stu-id="8d38a-134">To view server properties by using the SERVERPROPERTY built-in function</span></span>  
  
1.  <span data-ttu-id="8d38a-135">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="8d38a-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8d38a-136">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="8d38a-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8d38a-137">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="8d38a-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8d38a-138">In diesem Beispiel wird die integrierte [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) -Funktion in einer `SELECT` -Anweisung verwendet, um Informationen zum aktuellen Server zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="8d38a-138">This example uses the [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) built-in function in a `SELECT` statement to return information about the current server.</span></span> <span data-ttu-id="8d38a-139">Dieses Szenario ist hilfreich, wenn auf einem Windows-basierten Server mehrere Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installiert sind und der Client eine weitere Verbindung mit der Instanz herstellen muss, die auch von der aktuellen Verbindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8d38a-139">This scenario is useful when there are multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installed on a Windows-based server, and the client must open another connection to the same instance that is used by the current connection.</span></span>  
  
    ```sql  
    SELECT CONVERT( sysname, SERVERPROPERTY('servername'));  
    GO  
    ```  
  
#### <a name="to-view-server-properties-by-using-the-sysservers-catalog-view"></a><span data-ttu-id="8d38a-140">So zeigen Sie Servereigenschaften mit der sys.servers-Katalogsicht an</span><span class="sxs-lookup"><span data-stu-id="8d38a-140">To view server properties by using the sys.servers catalog view</span></span>  
  
1.  <span data-ttu-id="8d38a-141">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="8d38a-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8d38a-142">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="8d38a-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8d38a-143">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="8d38a-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8d38a-144">In diesem Beispiel wird die [sys.servers](/sql/relational-databases/system-catalog-views/sys-servers-transact-sql) -Katalogsicht abgefragt, um den Namen (`name`) und die ID (`server_id`) des aktuellen Servers sowie den Namen des OLE DB-Anbieters (`provider`) zum Herstellen einer Verbindung mit einem Verbindungsserver zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="8d38a-144">This example queries the [sys.servers](/sql/relational-databases/system-catalog-views/sys-servers-transact-sql) catalog view to return the name (`name`) and ID (`server_id`) of the current server, and the name of the OLE DB provider (`provider`) for connecting to a linked server.</span></span>  
  
    ```sql  
    USE AdventureWorks2012;   
    GO  
    SELECT name, server_id, provider  
    FROM sys.servers ;   
    GO
    ```  
  
#### <a name="to-view-server-properties-by-using-the-sysconfigurations-catalog-view"></a><span data-ttu-id="8d38a-145">So zeigen Sie Servereigenschaften mit der sys.configurations-Katalogsicht an</span><span class="sxs-lookup"><span data-stu-id="8d38a-145">To view server properties by using the sys.configurations catalog view</span></span>  
  
1.  <span data-ttu-id="8d38a-146">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="8d38a-146">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8d38a-147">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="8d38a-147">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8d38a-148">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="8d38a-148">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8d38a-149">In diesem Beispiel wird die [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) -Katalogsicht abgefragt, um Informationen zu jeder Serverkonfigurationsoption des aktuellen Servers zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="8d38a-149">This example queries the [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) catalog view to return information about each server configuration option on the current server.</span></span> <span data-ttu-id="8d38a-150">Im Beispiel werden der Name (`name`) und die Beschreibung (`description`) der Option zurückgegeben sowie ein Hinweis dazu, ob die Option eine erweiterte Option ist (`is_advanced`).</span><span class="sxs-lookup"><span data-stu-id="8d38a-150">The example returns the name (`name`) and description (`description`) of the option and whether the option is an advanced option (`is_advanced`).</span></span>  
  
    ```sql
    USE AdventureWorks2012;
    GO  
    SELECT name, description, is_advanced  
    FROM sys.configurations ;
    GO
    ```  
  
#### <a name="to-change-a-server-property-by-using-sp_configure"></a><span data-ttu-id="8d38a-151">So ändern Sie eine Servereigenschaft mit sp_configure</span><span class="sxs-lookup"><span data-stu-id="8d38a-151">To change a server property by using sp_configure</span></span>  
  
1.  <span data-ttu-id="8d38a-152">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="8d38a-152">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8d38a-153">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="8d38a-153">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8d38a-154">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="8d38a-154">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8d38a-155">In diesem Beispiel wird gezeigt, wie Sie eine Servereigenschaft mithilfe von [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) ändern.</span><span class="sxs-lookup"><span data-stu-id="8d38a-155">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to change a server property.</span></span> <span data-ttu-id="8d38a-156">Im Beispiel wird der Wert der `fill factor` -Option in `100`geändert.</span><span class="sxs-lookup"><span data-stu-id="8d38a-156">The example changes the value of the `fill factor` option to `100`.</span></span> <span data-ttu-id="8d38a-157">Der Server muss neu gestartet werden, bevor die Änderung wirksam werden kann.</span><span class="sxs-lookup"><span data-stu-id="8d38a-157">The server must be restarted before the change can take effect.</span></span>  
  
```sql  
Use AdventureWorks2012;  
GO  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'fill factor', 100;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="8d38a-158">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="8d38a-158">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="8d38a-159">Verwenden des SQL Server-Konfigurations-Managers</span><span class="sxs-lookup"><span data-stu-id="8d38a-159">Using SQL Server Configuration Manager</span></span>  
 <span data-ttu-id="8d38a-160">Einige Servereigenschaften können mit dem SQL Server-Konfigurations-Manager angezeigt oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="8d38a-160">Some server properties can be viewed or changed by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="8d38a-161">Sie können z. B. die Version und Edition der SQL Server-Instanz anzeigen oder den Speicherort ändern, an dem Fehlerprotokolldateien gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="8d38a-161">For example, you can view the version and edition of the instance of SQL Server, or change the location where error log files are stored.</span></span> <span data-ttu-id="8d38a-162">Diese Eigenschaften können auch durch Abfragen der [serverbezogenen dynamischen Verwaltungssichten und Funktionen](/sql/relational-databases/system-dynamic-management-views/server-related-dynamic-management-views-and-functions-transact-sql)angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8d38a-162">These properties can also be viewed by querying the [Server-Related Dynamic Management Views and Functions](/sql/relational-databases/system-dynamic-management-views/server-related-dynamic-management-views-and-functions-transact-sql).</span></span>  
  
#### <a name="to-view-or-change-server-properties"></a><span data-ttu-id="8d38a-163">So zeigen Sie Servereigenschaften an oder ändern sie</span><span class="sxs-lookup"><span data-stu-id="8d38a-163">To view or change server properties</span></span>  
  
1.  <span data-ttu-id="8d38a-164">Zeigen Sie im Menü **Start** auf **Alle Programme**, zeigen Sie auf [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], zeigen Sie auf **Konfigurationstools**, und klicken Sie dann auf **SQL Server-Konfigurations-Manager**.</span><span class="sxs-lookup"><span data-stu-id="8d38a-164">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="8d38a-165">Klicken Sie im **SQL Server-Konfigurations-Manager**auf **SQL Server-Dienste**.</span><span class="sxs-lookup"><span data-stu-id="8d38a-165">In **SQL Server Configuration Manager**, click **SQL Server Services**.</span></span>  
  
3.  <span data-ttu-id="8d38a-166">Klicken Sie im Detailbereich mit der rechten Maustaste auf **SQL Server (\<***instancename***>)** , und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="8d38a-166">In the details pane, right-click **SQL Server (\<***instancename***>)**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="8d38a-167">Ändern Sie im Dialogfeld **SQL Server (\<***instancename***>) Eigenschaften** die Servereigenschaften auf der Registerkarte **Dienst** oder der Registerkarte **Erweitert**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d38a-167">In the **SQL Server (\<***instancename***>) Properties** dialog box, change the server properties on the **Service** tab or the **Advanced** tab, and then click **OK**.</span></span>  
  
##  <a name="follow-up-after-you-change-server-properties"></a><a name="FollowUp"></a> <span data-ttu-id="8d38a-168">Nachverfolgung: Nach dem Ändern von Servereigenschaften</span><span class="sxs-lookup"><span data-stu-id="8d38a-168">Follow Up: After you change server properties</span></span>  
 <span data-ttu-id="8d38a-169">Für einige Eigenschaften muss der Server u. U. neu gestartet werden, bevor die Änderung wirksam werden kann.</span><span class="sxs-lookup"><span data-stu-id="8d38a-169">For some properties, the server might have to be restarted before the change can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d38a-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8d38a-170">See Also</span></span>  
 <span data-ttu-id="8d38a-171">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8d38a-171">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="8d38a-172">[SET-Anweisungen (Transact-SQL)](/sql/t-sql/statements/set-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8d38a-172">[SET Statements &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statements-transact-sql) </span></span>  
 <span data-ttu-id="8d38a-173">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8d38a-173">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span></span>  
 <span data-ttu-id="8d38a-174">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8d38a-174">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="8d38a-175">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8d38a-175">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="8d38a-176">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8d38a-176">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 <span data-ttu-id="8d38a-177">[Konfigurieren von WMI zum Anzeigen des Serverstatus in SQL Server-Tools](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md) </span><span class="sxs-lookup"><span data-stu-id="8d38a-177">[Configure WMI to Show Server Status in SQL Server Tools](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md) </span></span>  
 <span data-ttu-id="8d38a-178">[SQL Server-Konfigurations-Manager](../../relational-databases/sql-server-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="8d38a-178">[SQL Server Configuration Manager](../../relational-databases/sql-server-configuration-manager.md) </span></span>  
 <span data-ttu-id="8d38a-179">[Konfigurationsfunktionen (Transact-SQL)](/sql/t-sql/functions/configuration-functions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8d38a-179">[Configuration Functions &#40;Transact-SQL&#41;](/sql/t-sql/functions/configuration-functions-transact-sql) </span></span>  
 [<span data-ttu-id="8d38a-180">Serverbezogene dynamische Verwaltungssichten und -funktionen (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8d38a-180">Server-Related Dynamic Management Views and Functions &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/server-related-dynamic-management-views-and-functions-transact-sql)  
