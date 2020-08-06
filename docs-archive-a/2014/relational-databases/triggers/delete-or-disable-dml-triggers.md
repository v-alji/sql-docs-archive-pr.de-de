---
title: Löschen oder Deaktivieren von DML-Triggern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- DML triggers, disabling
- removing DML triggers
- disabling DML triggers
- dropping DML triggers
- deleting DML triggers
- DML triggers, removing
ms.assetid: 0f97f953-33c5-4b26-afeb-db2a26ce38b4
author: rothja
ms.author: jroth
ms.openlocfilehash: 39b345ade1258987df06938791ac0024e8612365
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621933"
---
# <a name="delete-or-disable-dml-triggers"></a><span data-ttu-id="f0092-102">Löschen oder Deaktivieren von DML-Triggern</span><span class="sxs-lookup"><span data-stu-id="f0092-102">Delete or Disable DML Triggers</span></span>
  <span data-ttu-id="f0092-103">In diesem Thema wird beschrieben, wie Sie einen DML-Trigger in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]löschen oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f0092-103">This topic describes how to delete or disable a DML trigger in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f0092-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="f0092-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f0092-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="f0092-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f0092-106">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="f0092-106">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="f0092-107">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f0092-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f0092-108">**Löschen oder Deaktivieren eines DML-Triggers mit:**</span><span class="sxs-lookup"><span data-stu-id="f0092-108">**To delete or disable a DML trigger, using:**</span></span>  
  
     [<span data-ttu-id="f0092-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0092-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f0092-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f0092-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f0092-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="f0092-111">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="f0092-112">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="f0092-112">Recommendations</span></span>  
  
-   <span data-ttu-id="f0092-113">Wenn ein Trigger gelöscht wird, wird er aus der aktuellen Datenbank entfernt.</span><span class="sxs-lookup"><span data-stu-id="f0092-113">When a trigger is deleted, it is dropped from the current database.</span></span> <span data-ttu-id="f0092-114">Dies hat jedoch keine Auswirkung auf die Tabelle und Daten, auf denen der Trigger basiert.</span><span class="sxs-lookup"><span data-stu-id="f0092-114">The table and the data upon which it is based are not affected.</span></span> <span data-ttu-id="f0092-115">Durch das Löschen einer Tabelle werden automatisch alle Trigger für die Tabelle gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f0092-115">Deleting a table automatically deletes any triggers on the table.</span></span>  
  
-   <span data-ttu-id="f0092-116">Ein Trigger wird standardmäßig aktiviert, wenn er erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f0092-116">A trigger is enabled by default when it is created.</span></span>  
  
-   <span data-ttu-id="f0092-117">Durch das Deaktivieren wird ein Trigger nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f0092-117">Disabling a trigger does not drop it.</span></span> <span data-ttu-id="f0092-118">Der Trigger ist weiterhin als Objekt in der aktuellen Datenbank vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f0092-118">The trigger still exists as an object in the current database.</span></span> <span data-ttu-id="f0092-119">Ein deaktivierter Trigger wird jedoch nicht ausgelöst, wenn eine INSERT-, UPDATE- oder DELETE-Anweisung ausgeführt wird, für die er programmiert war.</span><span class="sxs-lookup"><span data-stu-id="f0092-119">However, the trigger will not fire when any INSERT, UPDATE, or DELETE statement on which it was programmed is executed.</span></span> <span data-ttu-id="f0092-120">Deaktivierte Trigger können erneut aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f0092-120">Triggers that are disabled can be reenabled.</span></span> <span data-ttu-id="f0092-121">Durch das Aktivieren eines Triggers wird dieser nicht neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="f0092-121">Enabling a trigger does not re-create it.</span></span> <span data-ttu-id="f0092-122">Der Trigger wird auf die gleiche Weise ausgelöst wie bei seiner ursprünglichen Erstellung.</span><span class="sxs-lookup"><span data-stu-id="f0092-122">The trigger fires in the same manner as when it was originally created.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f0092-123">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f0092-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f0092-124">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f0092-124">Permissions</span></span>  
 <span data-ttu-id="f0092-125">Zum Löschen eines DML-Triggers ist die ALTER-Berechtigung für die Tabelle oder Sicht erforderlich, in der der Trigger definiert ist.</span><span class="sxs-lookup"><span data-stu-id="f0092-125">To delete a DML trigger requires ALTER permission on the table or view on which the trigger is defined.</span></span>  
  
 <span data-ttu-id="f0092-126">Zum Deaktivieren oder Aktivieren eines DML-Triggers muss ein Benutzer mindestens die ALTER-Berechtigung für die Tabelle oder Sicht besitzen, für die der Trigger erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="f0092-126">To disable or enable a DML trigger, at a minimum, a user must have ALTER permission on the table or view on which the trigger was created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f0092-127">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0092-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-dml-trigger"></a><span data-ttu-id="f0092-128">So löschen Sie einen DML-Trigger</span><span class="sxs-lookup"><span data-stu-id="f0092-128">To delete a DML trigger</span></span>  
  
1.  <span data-ttu-id="f0092-129">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="f0092-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f0092-130">Erweitern Sie die gewünschte Datenbank, **Tabellen**und dann die Tabelle, die den zu löschenden Trigger enthält.</span><span class="sxs-lookup"><span data-stu-id="f0092-130">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger that you want to delete.</span></span>  
  
3.  <span data-ttu-id="f0092-131">Erweitern Sie **Trigger**, klicken Sie mit der rechten Maustaste auf den zu löschenden Trigger, und klicken Sie anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="f0092-131">Expand **Triggers**, right-click the trigger to delete, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="f0092-132">Überprüfen Sie im Dialogfeld **Objekt löschen** , ob der richtige Trigger ausgewählt ist, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0092-132">In the **Delete Object** dialog box, verify the trigger to delete, and then click **OK**.</span></span>  
  
#### <a name="to-disable-and-enable-a-dml-trigger"></a><span data-ttu-id="f0092-133">So deaktivieren und aktivieren Sie einen DML-Trigger</span><span class="sxs-lookup"><span data-stu-id="f0092-133">To disable and enable a DML trigger</span></span>  
  
1.  <span data-ttu-id="f0092-134">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="f0092-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f0092-135">Erweitern Sie die gewünschte Datenbank, **Tabellen**und dann die Tabelle, die den zu deaktivierenden Trigger enthält.</span><span class="sxs-lookup"><span data-stu-id="f0092-135">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger that you want to disable.</span></span>  
  
3.  <span data-ttu-id="f0092-136">Erweitern Sie **Trigger**, klicken Sie mit der rechten Maustaste auf den zu deaktivierenden Trigger, und klicken Sie anschließend auf **Deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="f0092-136">Expand **Triggers**, right-click the trigger to disable, and then click **Disable**.</span></span>  
  
4.  <span data-ttu-id="f0092-137">Um den Trigger zu aktivieren, klicken Sie auf **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="f0092-137">To enable the trigger, click **Enable**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f0092-138">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f0092-138">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-dml-trigger"></a><span data-ttu-id="f0092-139">So löschen Sie einen DML-Trigger</span><span class="sxs-lookup"><span data-stu-id="f0092-139">To delete a DML trigger</span></span>  
  
1.  <span data-ttu-id="f0092-140">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="f0092-140">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f0092-141">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="f0092-141">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f0092-142">Kopieren Sie die folgenden Beispiele, und fügen Sie sie in das Abfrage-Fenster ein.</span><span class="sxs-lookup"><span data-stu-id="f0092-142">Copy and paste the following examples into the query window.</span></span> <span data-ttu-id="f0092-143">Führen Sie die [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql) -Anweisung aus, um den `Sales.bonus_reminder` -Trigger zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f0092-143">Execute the [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql) statement to create the `Sales.bonus_reminder` trigger.</span></span> <span data-ttu-id="f0092-144">Führen Sie die [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) -Anweisung aus, um den Trigger zu löschen.</span><span class="sxs-lookup"><span data-stu-id="f0092-144">To delete the trigger, execute the [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) statement.</span></span>  
  
```sql  
--Create the trigger.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID(N'Sales.bonus_reminder', N'TR') IS NOT NULL  
    DROP TRIGGER Sales.bonus_reminder;  
GO  
CREATE TRIGGER Sales.bonus_reminder  
ON Sales.SalesPersonQuotaHistory  
WITH ENCRYPTION  
AFTER INSERT, UPDATE   
AS RAISERROR ('Notify Compensation', 16, 10);  
GO  
  
```  
  
```sql  
--Delete the trigger.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ('Sales.bonus_reminder', 'TR') IS NOT NULL  
   DROP TRIGGER Sales.bonus_reminder;  
GO  
  
```  
  
#### <a name="to-disable-and-enable-a-dml-trigger"></a><span data-ttu-id="f0092-145">So deaktivieren und aktivieren Sie einen DML-Trigger</span><span class="sxs-lookup"><span data-stu-id="f0092-145">To disable and enable a DML trigger</span></span>  
  
1.  <span data-ttu-id="f0092-146">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="f0092-146">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f0092-147">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="f0092-147">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f0092-148">Kopieren Sie die folgenden Beispiele, und fügen Sie sie in das Abfrage-Fenster ein.</span><span class="sxs-lookup"><span data-stu-id="f0092-148">Copy and paste the following examples into the query window.</span></span> <span data-ttu-id="f0092-149">Führen Sie die [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql) -Anweisung aus, um den `Sales.bonus_reminder` -Trigger zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f0092-149">Execute the [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql) statement to create the `Sales.bonus_reminder` trigger.</span></span> <span data-ttu-id="f0092-150">Führen Sie die [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) - und [die ENABLE TRIGGER](/sql/t-sql/statements/enable-trigger-transact-sql) -Anweisungen aus, um den Trigger zu deaktivieren und zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f0092-150">To disable and enable the trigger, execute the [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) and [ENABLE TRIGGER](/sql/t-sql/statements/enable-trigger-transact-sql) statements, respectively.</span></span>  
  
```sql  
--Create the trigger.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID(N'Sales.bonus_reminder', N'TR') IS NOT NULL  
    DROP TRIGGER Sales.bonus_reminder;  
GO  
CREATE TRIGGER Sales.bonus_reminder  
ON Sales.SalesPersonQuotaHistory  
WITH ENCRYPTION  
AFTER INSERT, UPDATE   
AS RAISERROR ('Notify Compensation', 16, 10);  
GO  
  
```  
  
```sql  
--Disable the trigger.  
USE AdventureWorks2012;  
GO  
DISABLE TRIGGER Sales.bonus_reminder ON Sales.SalesPersonQuotaHistory;  
GO  
  
```  
  
```sql  
--Enable the trigger.  
USE AdventureWorks2012;  
GO  
ENABLE TRIGGER Sales.bonus_reminder ON Sales.SalesPersonQuotaHistory;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0092-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0092-151">See Also</span></span>  
 <span data-ttu-id="f0092-152">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0092-152">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span></span>  
 <span data-ttu-id="f0092-153">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0092-153">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="f0092-154">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0092-154">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 <span data-ttu-id="f0092-155">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0092-155">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="f0092-156">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0092-156">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="f0092-157">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0092-157">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span></span>  
 <span data-ttu-id="f0092-158">[Abrufen von Informationen zu DML-Triggern](dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="f0092-158">[Get Information About DML Triggers](dml-triggers.md) </span></span>  
 <span data-ttu-id="f0092-159">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0092-159">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span></span>  
 <span data-ttu-id="f0092-160">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0092-160">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span></span>  
 <span data-ttu-id="f0092-161">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0092-161">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span></span>  
 <span data-ttu-id="f0092-162">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0092-162">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="f0092-163">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0092-163">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="f0092-164">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0092-164">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="f0092-165">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0092-165">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span></span>  
 <span data-ttu-id="f0092-166">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0092-166">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="f0092-167">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0092-167">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span></span>  
 [<span data-ttu-id="f0092-168">sys.server_assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f0092-168">sys.server_assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql)  
  
  
