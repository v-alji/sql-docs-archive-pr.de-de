---
title: Verwalten der Triggersicherheit | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- triggers [SQL Server], security
ms.assetid: e94720a8-a3a2-4364-b0a3-bbe86e3ce4d5
author: rothja
ms.author: jroth
ms.openlocfilehash: fdc176dcad50c3bf28f058c3724a01267975bfc5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621917"
---
# <a name="manage-trigger-security"></a><span data-ttu-id="81534-102">Verwalten der Triggersicherheit</span><span class="sxs-lookup"><span data-stu-id="81534-102">Manage Trigger Security</span></span>
  <span data-ttu-id="81534-103">Standardmäßig werden sowohl DML- als auch DDL-Trigger im Kontext des Benutzers ausgeführt, der den Trigger aufruft.</span><span class="sxs-lookup"><span data-stu-id="81534-103">By default, both DML and DDL triggers execute under the context of the user that calls the trigger.</span></span> <span data-ttu-id="81534-104">Genauer ist der Benutzer, der den Trigger aufruft, derjenige Benutzer, der die Anweisung ausführt, die zum Ausführen des Triggers führt.</span><span class="sxs-lookup"><span data-stu-id="81534-104">The caller of a trigger is the user that executes the statement that causes the trigger to run.</span></span> <span data-ttu-id="81534-105">Wenn die Benutzerin **Mary** beispielsweise eine DELETE-Anweisung ausführt, die dazu führt, dass der DML-Trigger **DML_trigMary** ausgeführt wird, wird der Code in **DML_trigMary** im Kontext der Privilegien für **Mary**ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="81534-105">For example, if user **Mary** executes a DELETE statement that causes DML trigger **DML_trigMary** to run, the code inside **DML_trigMary** executes in the context of the user privileges for **Mary**.</span></span> <span data-ttu-id="81534-106">Dieses Standardverhalten kann von Benutzern ausgenutzt werden, die bösartigen Code in die Datenbank oder Serverinstanz einschleusen möchten.</span><span class="sxs-lookup"><span data-stu-id="81534-106">This default behavior can be exploited by users who want to introduce malicious code in the database or server instance.</span></span> <span data-ttu-id="81534-107">Beispielsweise wird der folgende DDL-Trigger vom Benutzer `JohnDoe`erstellt:</span><span class="sxs-lookup"><span data-stu-id="81534-107">For example, the following DDL trigger is created by user `JohnDoe`:</span></span>  
  
 `CREATE TRIGGER DDL_trigJohnDoe`  
  
 `ON DATABASE`  
  
 `FOR ALTER_TABLE`  
  
 `AS`  
  
 `GRANT CONTROL SERVER TO JohnDoe ;`  
  
 `GO`  
  
 <span data-ttu-id="81534-108">Dieser Trigger bewirkt Folgendes: Sobald ein Benutzer mit der Berechtigung, `GRANT CONTROL SERVER` -Anweisungen auszuführen, wie z. B. ein Mitglied der festen Serverrolle **sysadmin** , eine `ALTER TABLE` -Anweisung ausführt, wird `JohnDoe` die `CONTROL SERVER` -Berechtigung erteilt.</span><span class="sxs-lookup"><span data-stu-id="81534-108">What this trigger means is that as soon as a user that has permission to execute a `GRANT CONTROL SERVER` statement, such as a member of the **sysadmin** fixed server role, executes an `ALTER TABLE` statement, `JohnDoe` is granted `CONTROL SERVER` permission.</span></span> <span data-ttu-id="81534-109">Mit anderen Worten heißt dies, dass `JohnDoe` zwar die `CONTROL SERVER` -Berechtigung nicht sich selbst erteilen darf, jedoch den Triggercode aktivieren kann, der ihm diese Berechtigung verschafft.</span><span class="sxs-lookup"><span data-stu-id="81534-109">In other words, although `JohnDoe` cannot grant `CONTROL SERVER` permission to himself, he enabled the trigger code that grants him this permission to execute under escalated privileges.</span></span> <span data-ttu-id="81534-110">Sowohl DML- als auch DDL-Trigger sind diesen Sicherheitsrisiken ausgesetzt.</span><span class="sxs-lookup"><span data-stu-id="81534-110">Both DML and DDL triggers are open to this kind of security threat.</span></span>  
  
## <a name="trigger-security-best-practices"></a><span data-ttu-id="81534-111">Bewährte Methoden für die Triggersicherheit</span><span class="sxs-lookup"><span data-stu-id="81534-111">Trigger Security Best Practices</span></span>  
 <span data-ttu-id="81534-112">Sie können folgende Maßnahmen ergreifen, um zu vermeiden, dass Triggercode mit ausgeweiteten Privilegien ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="81534-112">You can take the following measures to prevent trigger code from executing under escalated privileges:</span></span>  
  
-   <span data-ttu-id="81534-113">Eruieren Sie die in der Datenbank und der Serverinstanz vorhandenen DML- und DDL-Trigger, indem Sie die Katalogsichten [sys.triggers](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) und [sys.server_triggers](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) abfragen.</span><span class="sxs-lookup"><span data-stu-id="81534-113">Be aware of the DML and DDL triggers that exist in the database and on the server instance by querying the [sys.triggers](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) and [sys.server_triggers](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) catalog views.</span></span> <span data-ttu-id="81534-114">Die folgende Abfrage gibt alle DML-Trigger und DDL-Trigger auf Datenbankebene der aktuellen Datenbank zurück, sowie alle DDL-Trigger auf Serverebene der Serverinstanz:</span><span class="sxs-lookup"><span data-stu-id="81534-114">The following query returns all DML and database-level DDL triggers in the current database, and all server-level DDL triggers on the server instance:</span></span>  
  
    ```  
    SELECT type, name, parent_class_desc FROM sys.triggers  
    UNION  
    SELECT type, name, parent_class_desc FROM sys.server_triggers ;  
    ```  
  
-   <span data-ttu-id="81534-115">Verwenden Sie [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) , um die Trigger zu deaktivieren, die die Integrität der Datenbank oder des Servers beeinträchtigen können, falls sie mit ausgeweiteten Privilegien ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="81534-115">Use [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) to disable triggers that can harm the integrity of the database or server if the triggers execute under escalated privileges.</span></span> <span data-ttu-id="81534-116">Die folgende Anweisung deaktiviert alle DDL-Trigger auf Datenbankebene in der aktuellen Datenbank:</span><span class="sxs-lookup"><span data-stu-id="81534-116">The following statement disables all database-level DDL triggers in the current database:</span></span>  
  
    ```  
    DISABLE TRIGGER ALL ON DATABASE  
    ```  
  
     <span data-ttu-id="81534-117">Die folgende Anweisung deaktiviert alle DDL-Trigger auf Serverebene in der Serverinstanz:</span><span class="sxs-lookup"><span data-stu-id="81534-117">This statement disables all server-level DDL triggers on the server instance:</span></span>  
  
    ```  
    DISABLE TRIGGER ALL ON ALL SERVER  
    ```  
  
     <span data-ttu-id="81534-118">Die folgende Anweisung deaktiviert alle DML-Trigger in der aktuellen Datenbank:</span><span class="sxs-lookup"><span data-stu-id="81534-118">This statement disables all DML triggers in the current database:</span></span>  
  
    ```  
    DECLARE @schema_name sysname, @trigger_name sysname, @object_name sysname ;  
    DECLARE @sql nvarchar(max) ;  
    DECLARE trig_cur CURSOR FORWARD_ONLY READ_ONLY FOR  
        SELECT SCHEMA_NAME(schema_id) AS schema_name,  
            name AS trigger_name,  
            OBJECT_NAME(parent_object_id) as object_name  
        FROM sys.objects WHERE type in ('TR', 'TA') ;  
  
    OPEN trig_cur ;  
    FETCH NEXT FROM trig_cur INTO @schema_name, @trigger_name, @object_name ;  
  
    WHILE @@FETCH_STATUS = 0  
    BEGIN  
        SELECT @sql = 'DISABLE TRIGGER ' + QUOTENAME(@schema_name) + '.'  
            + QUOTENAME(@trigger_name) +  
            ' ON ' + QUOTENAME(@schema_name) + '.'   
            + QUOTENAME(@object_name) + ' ; ' ;  
        EXEC (@sql) ;  
        FETCH NEXT FROM trig_cur INTO @schema_name, @trigger_name, @object_name ;  
    END  
    GO  
  
    -- Verify triggers are disabled. Should return an empty result set.  
    SELECT * FROM sys.triggers WHERE is_disabled = 0 ;  
    GO  
  
    CLOSE trig_cur ;  
    DEALLOCATE trig_cur;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="81534-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="81534-119">See Also</span></span>  
 <span data-ttu-id="81534-120">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="81534-120">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="81534-121">[DML-Trigger](../triggers/dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="81534-121">[DML Triggers](../triggers/dml-triggers.md) </span></span>  
 [<span data-ttu-id="81534-122">DDL-Trigger</span><span class="sxs-lookup"><span data-stu-id="81534-122">DDL Triggers</span></span>](../triggers/ddl-triggers.md)  
  
  
