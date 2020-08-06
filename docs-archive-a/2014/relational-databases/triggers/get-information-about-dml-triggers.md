---
title: Abrufen von Informationen zu DML-Triggern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- metadata [SQL Server], triggers
- viewing DML triggers
- DML triggers, metadata
- displaying DML triggers
- status information [SQL Server], triggers
- DML triggers, viewing
ms.assetid: 37574aac-181d-4aca-a2cc-8abff64237dc
author: rothja
ms.author: jroth
ms.openlocfilehash: 2f65976d2f517137e23bd9e5e1c98cc76324bc49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621929"
---
# <a name="get-information-about-dml-triggers"></a><span data-ttu-id="7def3-102">Abrufen von Informationen zu DML-Triggern</span><span class="sxs-lookup"><span data-stu-id="7def3-102">Get Information About DML Triggers</span></span>
  <span data-ttu-id="7def3-103">In diesem Thema wird beschrieben, wie Sie Informationen zu DML-Triggern in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]abrufen.</span><span class="sxs-lookup"><span data-stu-id="7def3-103">This topic describes how to get information about DML triggers in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="7def3-104">Zu diesen Informationen können die Triggertypen für eine Tabelle, der Name eines Triggers, sein Besitzer und das Erstellungs- oder Änderungsdatum zählen.</span><span class="sxs-lookup"><span data-stu-id="7def3-104">This information can include the types of triggers on a table, the name of a trigger, its owner and the date it was created or modified.</span></span> <span data-ttu-id="7def3-105">Wenn der Trigger bei der Erstellung nicht verschlüsselt wurde, erhalten Sie die Definition des Triggers.</span><span class="sxs-lookup"><span data-stu-id="7def3-105">If the trigger was not encrypted when it was created, you obtain the definition of the trigger.</span></span> <span data-ttu-id="7def3-106">Die Definition gibt Aufschluss darüber, wie sich ein Trigger auf die Tabelle auswirkt, für die er definiert ist.</span><span class="sxs-lookup"><span data-stu-id="7def3-106">You can use the definition to help you understand how a trigger affects the table up on which it is defined.</span></span> <span data-ttu-id="7def3-107">Zudem können Sie die Objekte feststellen, die von einem bestimmten Trigger verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7def3-107">Also, you can find out the objects that a specific trigger uses.</span></span> <span data-ttu-id="7def3-108">Mithilfe dieser Informationen können Sie die Objekte identifizieren, deren Änderung oder Löschung in der Datenbank sich auf den Trigger auswirkt.</span><span class="sxs-lookup"><span data-stu-id="7def3-108">With this information, you can identify the objects that affect the trigger if they are changed or deleted in the database.</span></span>  
  
 <span data-ttu-id="7def3-109">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="7def3-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7def3-110">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="7def3-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7def3-111">Security</span><span class="sxs-lookup"><span data-stu-id="7def3-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7def3-112">**Abrufen von Informationen zu DML-Triggern mit:**</span><span class="sxs-lookup"><span data-stu-id="7def3-112">**To get information about DML triggers, using:**</span></span>  
  
     [<span data-ttu-id="7def3-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7def3-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7def3-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7def3-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7def3-115">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="7def3-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7def3-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7def3-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7def3-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7def3-117">Permissions</span></span>  
 <span data-ttu-id="7def3-118">**sys.sql.modules**, **sys.object**, **sys.triggers**, **sys.events**, **sys.trigger_events**</span><span class="sxs-lookup"><span data-stu-id="7def3-118">**sys.sql.modules**, **sys.object**, **sys.triggers**, **sys.events**, **sys.trigger_events**</span></span>  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] <span data-ttu-id="7def3-119">Weitere Informationen finden Sie unter [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="7def3-119">For more information, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
 <span data-ttu-id="7def3-120">OBJECT_DEFINITION, OBJECTPROPERTY, **sp_helptext**</span><span class="sxs-lookup"><span data-stu-id="7def3-120">OBJECT_DEFINITION, OBJECTPROPERTY, **sp_helptext**</span></span>  
 <span data-ttu-id="7def3-121">Erfordert die Mitgliedschaft in der **public** -Rolle.</span><span class="sxs-lookup"><span data-stu-id="7def3-121">Requires membership in the **public** role.</span></span> <span data-ttu-id="7def3-122">Die Definition von Benutzerobjekten ist für den Objektbesitzer sichtbar oder für Berechtigte, die über eine der folgenden Berechtigungen verfügen: ALTER, CONTROL, TAKE OWNERSHIP oder VIEW DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="7def3-122">The definition of user objects is visible to the object owner or grantees that have any one of the following permissions: ALTER, CONTROL, TAKE OWNERSHIP, or VIEW DEFINITION.</span></span> <span data-ttu-id="7def3-123">Über diese Berechtigungen verfügen implizit Mitglieder der festen Datenbankrollen **db_owner**, **db_ddladmin**und **db_securityadmin** .</span><span class="sxs-lookup"><span data-stu-id="7def3-123">These permissions are implicitly held by members of the **db_owner**, **db_ddladmin**, and **db_securityadmin** fixed database roles.</span></span>  
  
 <span data-ttu-id="7def3-124">**sys.sql_expression_dependencies**</span><span class="sxs-lookup"><span data-stu-id="7def3-124">**sys.sql_expression_dependencies**</span></span>  
 <span data-ttu-id="7def3-125">Erfordert die Berechtigung VIEW DEFINITION für die Datenbank und die Berechtigung SELECT für **sys.sql_expression_dependencies** für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="7def3-125">Requires VIEW DEFINITION permission on the database and SELECT permission on **sys.sql_expression_dependencies** for the database.</span></span> <span data-ttu-id="7def3-126">Standardmäßig wird die SELECT-Berechtigung nur Mitgliedern der festen Datenbankrolle **db_owner** gewährt.</span><span class="sxs-lookup"><span data-stu-id="7def3-126">By default, SELECT permission is granted only to members of the **db_owner** fixed database role.</span></span> <span data-ttu-id="7def3-127">Wenn einem anderen Benutzer die SELECT-Berechtigung und die VIEW DEFINITION-Berechtigung erteilt werden, kann dieser Berechtigte alle Abhängigkeiten in der Datenbank anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7def3-127">When SELECT and VIEW DEFINITION permissions are granted to another user, the grantee can view all dependencies in the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7def3-128">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7def3-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-definition-of-a-dml-trigger"></a><span data-ttu-id="7def3-129">So zeigen Sie die Definition eines DML-Triggers an</span><span class="sxs-lookup"><span data-stu-id="7def3-129">To view the definition of a DML trigger</span></span>  
  
1.  <span data-ttu-id="7def3-130">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="7def3-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="7def3-131">Erweitern Sie die gewünschte Datenbank, **Tabellen**und dann die Tabelle mit dem Trigger, dessen Definition Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="7def3-131">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger for which you want to view the definition.</span></span>  
  
3.  <span data-ttu-id="7def3-132">Erweitern Sie **Trigger**, klicken Sie mit der rechten Maustaste auf den gewünschten Trigger, und klicken Sie anschließend auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="7def3-132">Expand **Triggers**, right-click the trigger you want, and then click **Modify**.</span></span> <span data-ttu-id="7def3-133">Die Definition des DML-Triggers wird im Abfragefenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7def3-133">The definition of the DML trigger appears in the query window.</span></span>  
  
#### <a name="to-view-the-dependencies-of-a-dml-trigger"></a><span data-ttu-id="7def3-134">So zeigen Sie die Abhängigkeiten eines DML-Triggers an</span><span class="sxs-lookup"><span data-stu-id="7def3-134">To view the dependencies of a DML trigger</span></span>  
  
1.  <span data-ttu-id="7def3-135">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="7def3-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="7def3-136">Erweitern Sie die gewünschte Datenbank, **Tabellen**und dann die Tabelle mit dem Trigger, dessen Abhängigkeiten Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="7def3-136">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger and its dependencies that you want to view.</span></span>  
  
3.  <span data-ttu-id="7def3-137">Erweitern Sie **Trigger**, klicken Sie mit der rechten Maustaste auf den gewünschten Trigger, und klicken Sie anschließend auf **Abhängigkeiten anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="7def3-137">Expand **Triggers**, right-click the trigger you want, and then click **View Dependencies**.</span></span>  
  
4.  <span data-ttu-id="7def3-138">Klicken Sie im Fenster **Objektabhängigkeiten** auf **Objekte, die von \<DML trigger name> abhängig sind**, um die Objekte anzuzeigen, die vom DML-Trigger abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="7def3-138">In the **Object Dependencies** window, to view the objects that depend on the DML trigger, select **Objects that depend on \<DML trigger name>**.</span></span> <span data-ttu-id="7def3-139">Die Objekte werden im Bereich **Abhängigkeiten** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7def3-139">The objects appear in the **Dependencies** area.</span></span>  
  
     <span data-ttu-id="7def3-140">Klicken Sie auf **Objekte, von denen \<DML trigger name> abhängt**, um die Objekte anzuzeigen, von denen der DML-Trigger abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="7def3-140">To view the objects on which the DML depends, select **Objects on which \<DML trigger name> depends**.</span></span> <span data-ttu-id="7def3-141">Die Objekte werden im Bereich **Abhängigkeiten** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7def3-141">The objects appear in the **Dependencies** area.</span></span> <span data-ttu-id="7def3-142">Erweitern Sie jeden Knoten, um alle Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7def3-142">Expand each node to see all the objects.</span></span>  
  
5.  <span data-ttu-id="7def3-143">Wenn Sie Informationen zu einem im Bereich **Abhängigkeiten** angezeigten Objekt anzeigen möchten, klicken Sie auf das Objekt.</span><span class="sxs-lookup"><span data-stu-id="7def3-143">To obtain information about an object that appears in the **Dependencies** area, click the object.</span></span> <span data-ttu-id="7def3-144">Im Feld **Ausgewähltes Objekt** sind Informationen in den Feldern **Name**, **Typ**und **Abhängigkeitstyp** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7def3-144">In the **Selected object** field, information is provided in the **Name**, **Type**, and **Dependency type** boxes.</span></span>  
  
6.  <span data-ttu-id="7def3-145">Klicken Sie auf **OK** , um das Fenster **Objektabhängigkeiten**zu schließen.</span><span class="sxs-lookup"><span data-stu-id="7def3-145">To close the **Object Dependencies** window, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7def3-146">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7def3-146">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-definition-of-a-dml-trigger"></a><span data-ttu-id="7def3-147">So zeigen Sie die Definition eines DML-Triggers an</span><span class="sxs-lookup"><span data-stu-id="7def3-147">To view the definition of a DML trigger</span></span>  
  
1.  <span data-ttu-id="7def3-148">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="7def3-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7def3-149">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="7def3-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7def3-150">Kopieren Sie eines der folgenden Beispiele, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7def3-150">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="7def3-151">In den Beispielen wird gezeigt, wie Sie die Definition des `iuPerson` -Triggers anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="7def3-151">Each example shows how you can view the definition of the `iuPerson` trigger.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT definition   
FROM sys.sql_modules  
WHERE object_id = OBJECT_ID(N'Person.iuPerson');   
GO  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT OBJECT_DEFINITION (OBJECT_ID(N'Person.iuPerson')) AS ObjectDefinition;   
GO  
  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
EXEC sp_helptext 'Person.iuPerson'  
GO  
  
```  
  
#### <a name="to-view-the-dependencies-of-a-dml-trigger"></a><span data-ttu-id="7def3-152">So zeigen Sie die Abhängigkeiten eines DML-Triggers an</span><span class="sxs-lookup"><span data-stu-id="7def3-152">To view the dependencies of a DML trigger</span></span>  
  
1.  <span data-ttu-id="7def3-153">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="7def3-153">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7def3-154">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="7def3-154">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7def3-155">Kopieren Sie eines der folgenden Beispiele, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7def3-155">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="7def3-156">In den Beispielen wird gezeigt, wie Sie die Abhängigkeiten des `iuPerson` -Triggers anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="7def3-156">Each example shows how you can view the dependencies of `iuPerson` trigger.</span></span>  
  
```  
USE AdventureWorks2012;   
GO  
SELECT OBJECT_NAME(referencing_id) AS referencing_entity_name,   
    o.type_desc AS referencing_desciption,   
    COALESCE(COL_NAME(referencing_id, referencing_minor_id), '(n/a)') AS referencing_minor_id,   
    referencing_class_desc, referenced_class_desc,   
    referenced_server_name, referenced_database_name, referenced_schema_name,   
    referenced_entity_name,   
    COALESCE(COL_NAME(referenced_id, referenced_minor_id), '(n/a)') AS referenced_column_name,   
    is_caller_dependent, is_ambiguous  
FROM sys.sql_expression_dependencies AS sed  
INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
WHERE referencing_id = OBJECT_ID(N'Person.iuPerson');   
GO  
  
```  
  
#### <a name="to-view-information-about-dml-triggers-in-the-database"></a><span data-ttu-id="7def3-157">So zeigen Sie Informationen zu DML-Triggern in der Datenbank an</span><span class="sxs-lookup"><span data-stu-id="7def3-157">To view information about DML triggers in the database</span></span>  
  
1.  <span data-ttu-id="7def3-158">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="7def3-158">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7def3-159">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="7def3-159">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7def3-160">Kopieren Sie eines der folgenden Beispiele, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7def3-160">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="7def3-161">In den Beispielen wird gezeigt, wie Sie Informationen zu DML-Triggern (`TR`) in der Datenbank anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="7def3-161">Each example shows how you can view information about DML triggers (`TR`) in the database.</span></span>  
  
```  
USE AdventureWorks2012;   
GO  
SELECT  name, parent_id, create_date, modify_date, is_instead_of_trigger  
FROM sys.triggers  
WHERE type = 'TR';   
GO  
  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT  name, object_id, schema_id, parent_object_id, type_desc, create_date, modify_date, is_published  
FROM sys.objects  
WHERE type = 'TR';   
GO  
  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT OBJECTPROPERTY(OBJECT_ID(N'Person.iuPerson'), 'ExecIsInsteadOfTrigger');   
GO  
  
```  
  
#### <a name="to-view-information-about-events-that-fire-a-dml-trigger"></a><span data-ttu-id="7def3-162">So zeigen Sie Informationen zu Ereignissen an, die einen DML-Trigger auslösen</span><span class="sxs-lookup"><span data-stu-id="7def3-162">To view information about events that fire a DML trigger</span></span>  
  
1.  <span data-ttu-id="7def3-163">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="7def3-163">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7def3-164">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="7def3-164">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7def3-165">Kopieren Sie eines der folgenden Beispiele, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7def3-165">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="7def3-166">In den Beispielen wird gezeigt, wie Sie die Ereignisse anzeigen können, die den `iuPerson` -Trigger auslösen.</span><span class="sxs-lookup"><span data-stu-id="7def3-166">Each example shows how you can view the events that fire the `iuPerson` trigger.</span></span>  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT object_id, type, type_desc, is_trigger_event, event_group_type, event_group_type_desc   
FROM sys.events  
WHERE object_id = OBJECT_ID('Person.iuPerson');   
GO  
```  
  
```sql  
USE AdventureWorks2012;   
GO   
SELECT object_id, type,is_first, is_last  
FROM sys.trigger_events  
WHERE object_id = OBJECT_ID('Person.iuPerson');   
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="7def3-167">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7def3-167">See Also</span></span>  
 <span data-ttu-id="7def3-168">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7def3-168">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="7def3-169">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7def3-169">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 <span data-ttu-id="7def3-170">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7def3-170">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="7def3-171">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7def3-171">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="7def3-172">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7def3-172">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span></span>  
 <span data-ttu-id="7def3-173">[sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7def3-173">[sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span></span>  
 <span data-ttu-id="7def3-174">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7def3-174">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span></span>  
 <span data-ttu-id="7def3-175">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7def3-175">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span></span>  
 <span data-ttu-id="7def3-176">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7def3-176">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span></span>  
 <span data-ttu-id="7def3-177">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7def3-177">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span></span>  
 <span data-ttu-id="7def3-178">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7def3-178">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="7def3-179">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7def3-179">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="7def3-180">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7def3-180">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="7def3-181">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7def3-181">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span></span>  
 <span data-ttu-id="7def3-182">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7def3-182">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="7def3-183">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7def3-183">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="7def3-184">[sys.server_assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7def3-184">[sys.server_assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="7def3-185">[OBJECTPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectpropertyex-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7def3-185">[OBJECTPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectpropertyex-transact-sql) </span></span>  
 [<span data-ttu-id="7def3-186">OBJECT_DEFINITION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7def3-186">OBJECT_DEFINITION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/object-definition-transact-sql)  
  
  
