---
title: Ändern oder Umbenennen von DML-Triggern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- renaming triggers
- modifying triggers
- DML triggers, modifying
ms.assetid: c7317eec-c0e9-479e-a4a7-83b6b6c58d59
author: rothja
ms.author: jroth
ms.openlocfilehash: 65bb13552b552d54b5547eadedc412977e423a57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621916"
---
# <a name="modify-or-rename-dml-triggers"></a><span data-ttu-id="afd97-102">Ändern oder Umbenennen von DML-Triggern</span><span class="sxs-lookup"><span data-stu-id="afd97-102">Modify or Rename DML Triggers</span></span>
  <span data-ttu-id="afd97-103">In diesem Thema wird beschrieben, wie Sie einen DML-Trigger in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]umbenennen.</span><span class="sxs-lookup"><span data-stu-id="afd97-103">This topic describes how to modify or rename a DML trigger in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="afd97-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="afd97-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="afd97-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="afd97-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="afd97-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="afd97-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="afd97-107">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="afd97-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="afd97-108">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="afd97-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="afd97-109">**Ändern oder Umbenennen eines DML-Triggers mit:**</span><span class="sxs-lookup"><span data-stu-id="afd97-109">**To modify or rename a DML trigger, using:**</span></span>  
  
     [<span data-ttu-id="afd97-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="afd97-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="afd97-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="afd97-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="afd97-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="afd97-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="afd97-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="afd97-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="afd97-114">Wenn Sie einen Trigger umbenennen, muss der Trigger in der aktuellen Datenbank vorhanden sein, und der neue Name muss den Regeln für [Bezeichner](../databases/database-identifiers.md)entsprechen.</span><span class="sxs-lookup"><span data-stu-id="afd97-114">When you rename a trigger, the trigger must be in the current database, and the new name must follow the rules for [identifiers](../databases/database-identifiers.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="afd97-115">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="afd97-115">Recommendations</span></span>  
  
-   <span data-ttu-id="afd97-116">Es wird davon abgeraten, die gespeicherte Prozedur [sp_rename](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) zum Umbenennen eines Triggers zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="afd97-116">We recommend you do not use the [sp_rename](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) stored procedure to rename a trigger.</span></span> <span data-ttu-id="afd97-117">Wenn Sie Teile eines Objektnamens ändern, können Skripts und gespeicherte Prozeduren funktionsunfähig werden.</span><span class="sxs-lookup"><span data-stu-id="afd97-117">Changing any part of an object name can break scripts and stored procedures.</span></span> <span data-ttu-id="afd97-118">Durch das Umbenennen eines Triggers wird der entsprechende Objektname in der definition-Spalte der [sys.sql_modules-Katalogsicht](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="afd97-118">Renaming a trigger does not change the name of the corresponding object name in the definition column of the [sys.sql_modules](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) catalog view.</span></span> <span data-ttu-id="afd97-119">Es wird empfohlen, den Trigger stattdessen zu löschen und neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="afd97-119">We recommend that you drop and re-create the trigger instead.</span></span>  
  
-   <span data-ttu-id="afd97-120">Wenn Sie den Namen eines Objekts ändern, auf das ein DML-Trigger verweist, müssen Sie den Trigger so ändern, dass sein Text den neuen Namen widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="afd97-120">If you change the name of an object referenced by a DML trigger, you must modify the trigger so that its text reflects the new name.</span></span> <span data-ttu-id="afd97-121">Bevor Sie ein Objekt umbenennen, sollten Sie daher erst die Abhängigkeiten des Objekts anzeigen, um feststellen zu können, ob Trigger von der beabsichtigten Änderung betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="afd97-121">Therefore, before you rename an object, display the dependencies of the object first to determine whether any triggers are affected by the proposed change.</span></span>  
  
-   <span data-ttu-id="afd97-122">Sie können einen DML-Trigger auch ändern, um seine Definition zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="afd97-122">A DML trigger can also be modified to encrypt its definition.</span></span>  
  
-   <span data-ttu-id="afd97-123">Sie können die Abhängigkeiten eines Triggers mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder mit der folgenden Funktion und den Katalogsichten anzeigen:</span><span class="sxs-lookup"><span data-stu-id="afd97-123">To view the dependencies of a trigger, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or the following function and catalog views:</span></span>  
  
    -   [<span data-ttu-id="afd97-124">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="afd97-124">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
    -   [<span data-ttu-id="afd97-125">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="afd97-125">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
    -   [<span data-ttu-id="afd97-126">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="afd97-126">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql)  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="afd97-127">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="afd97-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="afd97-128">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="afd97-128">Permissions</span></span>  
 <span data-ttu-id="afd97-129">Zum Ändern eines DML-Triggers ist eine ALTER-Berechtigung für die Tabelle oder Sicht erforderlich, für die der Trigger definiert ist.</span><span class="sxs-lookup"><span data-stu-id="afd97-129">To alter a DML trigger requires ALTER permission on the table or view on which the trigger is defined.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="afd97-130">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="afd97-130">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-dml-trigger"></a><span data-ttu-id="afd97-131">So ändern Sie einen DML-Trigger</span><span class="sxs-lookup"><span data-stu-id="afd97-131">To modify a DML trigger</span></span>  
  
1.  <span data-ttu-id="afd97-132">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../../includes/ssde-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="afd97-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="afd97-133">Erweitern Sie die gewünschte Datenbank, **Tabellen**und dann die Tabelle, die den zu ändernden Trigger enthält.</span><span class="sxs-lookup"><span data-stu-id="afd97-133">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger that you want to modify.</span></span>  
  
3.  <span data-ttu-id="afd97-134">Erweitern Sie **Trigger**, klicken Sie mit der rechten Maustaste auf den zu ändernden Trigger, und klicken Sie anschließend auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="afd97-134">Expand **Triggers**, right-click the trigger to modify, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="afd97-135">Ändern Sie den Trigger, und klicken Sie dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="afd97-135">Modify the trigger, and then click **Execute**.</span></span>  
  
#### <a name="to-rename-a-dml-trigger"></a><span data-ttu-id="afd97-136">So benennen Sie einen DML-Trigger um</span><span class="sxs-lookup"><span data-stu-id="afd97-136">To rename a DML trigger</span></span>  
  
1.  <span data-ttu-id="afd97-137">[Löschen Sie den Trigger](../triggers/dml-triggers.md) , den Sie umbenennen möchten.</span><span class="sxs-lookup"><span data-stu-id="afd97-137">[Delete the trigger](../triggers/dml-triggers.md) that you want to rename.</span></span>  
  
2.  <span data-ttu-id="afd97-138">[Erstellen Sie den Trigger neu](../triggers/create-dml-triggers.md), und geben Sie dabei den neuen Namen an.</span><span class="sxs-lookup"><span data-stu-id="afd97-138">[Re-create the trigger](../triggers/create-dml-triggers.md), specifying the new name.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="afd97-139">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="afd97-139">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-trigger-using-alter-trigger"></a><span data-ttu-id="afd97-140">So ändern Sie einen Trigger mit ALTER TRIGGER</span><span class="sxs-lookup"><span data-stu-id="afd97-140">To modify a trigger using ALTER TRIGGER</span></span>  
  
1.  <span data-ttu-id="afd97-141">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="afd97-141">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="afd97-142">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="afd97-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="afd97-143">Kopieren Sie die folgenden Beispiele, und fügen Sie sie in das Abfragefenster ein.</span><span class="sxs-lookup"><span data-stu-id="afd97-143">Copy and paste the following examples into the query.</span></span> <span data-ttu-id="afd97-144">Führen Sie das erste Beispiel aus, um einen DML-Trigger zu erstellen, der eine benutzerdefinierte Meldung an den Client ausgibt, wenn ein Benutzer versucht, Daten in der `SalesPersonQuotaHistory` -Tabelle hinzuzufügen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="afd97-144">Execute the first example to create a DML trigger that prints a user-defined message to the client when a user tries to add or change data in the `SalesPersonQuotaHistory` table.</span></span> <span data-ttu-id="afd97-145">Führen Sie die [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) -Anweisung aus, um den Trigger so zu ändern, dass er nur bei `INSERT` -Aktivitäten ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="afd97-145">Execute the [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) statement to modify the trigger to fire only on `INSERT` activities.</span></span> <span data-ttu-id="afd97-146">Dieser Trigger ist hilfreich, da er den Benutzer beim Aktualisieren oder Einfügen von Zeilen in die Tabelle daran erinnert, dass auch die Abteilung `Compensation` benachrichtigt werden muss.</span><span class="sxs-lookup"><span data-stu-id="afd97-146">This trigger is helpful because it reminds the user that updates or inserts rows into this table to also notify the `Compensation` department.</span></span>  
  
```sql  
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
USE AdventureWorks2012;  
GO  
ALTER TRIGGER Sales.bonus_reminder  
ON Sales.SalesPersonQuotaHistory  
AFTER INSERT  
AS RAISERROR ('Notify Compensation', 16, 10);  
GO  
  
```  
  
#### <a name="to-rename-a-trigger-using-drop-trigger-and-alter-trigger"></a><span data-ttu-id="afd97-147">So benennen Sie einen Trigger mit DROP TRIGGER und ALTER TRIGGER um</span><span class="sxs-lookup"><span data-stu-id="afd97-147">To rename a trigger using DROP TRIGGER and ALTER TRIGGER</span></span>  
  
1.  <span data-ttu-id="afd97-148">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="afd97-148">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="afd97-149">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="afd97-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="afd97-150">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="afd97-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="afd97-151">In diesem Beispiel werden die [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) - und [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) -Anweisungen verwendet, um den `Sales.bonus_reminder` -Trigger in `Sales.bonus_reminder_2`umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="afd97-151">This example use the [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) and [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) statements to rename the `Sales.bonus_reminder` trigger to `Sales.bonus_reminder_2`.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID(N'Sales.bonus_reminder', N'TR') IS NOT NULL  
    DROP TRIGGER Sales.bonus_reminder;  
GO  
CREATE TRIGGER Sales.bonus_reminder_2  
ON Sales.SalesPersonQuotaHistory  
WITH ENCRYPTION  
AFTER INSERT, UPDATE   
AS RAISERROR ('Notify Compensation', 16, 10);  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="afd97-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="afd97-152">See Also</span></span>  
 <span data-ttu-id="afd97-153">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="afd97-153">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="afd97-154">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="afd97-154">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 <span data-ttu-id="afd97-155">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="afd97-155">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="afd97-156">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="afd97-156">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="afd97-157">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="afd97-157">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span></span>  
 <span data-ttu-id="afd97-158">[sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="afd97-158">[sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span></span>  
 <span data-ttu-id="afd97-159">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="afd97-159">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span></span>  
 <span data-ttu-id="afd97-160">[Abrufen von Informationen zu DML-Triggern](../triggers/get-information-about-dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="afd97-160">[Get Information About DML Triggers](../triggers/get-information-about-dml-triggers.md) </span></span>  
 <span data-ttu-id="afd97-161">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="afd97-161">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span></span>  
 <span data-ttu-id="afd97-162">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="afd97-162">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span></span>  
 <span data-ttu-id="afd97-163">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="afd97-163">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span></span>  
 <span data-ttu-id="afd97-164">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="afd97-164">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="afd97-165">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="afd97-165">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="afd97-166">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="afd97-166">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="afd97-167">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="afd97-167">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span></span>  
 <span data-ttu-id="afd97-168">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="afd97-168">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="afd97-169">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="afd97-169">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span></span>  
 [<span data-ttu-id="afd97-170">sys.server_assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="afd97-170">sys.server_assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql)  
  
  
