---
title: Anzeigen der Abhängigkeiten einer gespeicherten Prozedur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], dependencies
- displaying stored procedure dependencies
- viewing stored procedure dependencies
ms.assetid: 6ae0a369-1bc7-4ae4-be89-2b483697cd1f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 790684035d2db3b697fb8b718c96182eda8f1186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630607"
---
# <a name="view-the-dependencies-of-a-stored-procedure"></a><span data-ttu-id="756c1-102">Anzeigen der Abhängigkeiten einer gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="756c1-102">View the Dependencies of a Stored Procedure</span></span>
    
##  <a name="this-topic-describes-how-to-view-stored-procedure-dependencies-in-sscurrent-by-using-ssmanstudiofull-or-tsql"></a><a name="Top"></a> <span data-ttu-id="756c1-103">In diesem Thema wird beschrieben, wie mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)] Abhängigkeiten von gespeicherten Prozeduren in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="756c1-103">This topic describes how to view stored procedure dependencies in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="756c1-104">**Vorbereitungen:**  [Sicherheit](#Security)</span><span class="sxs-lookup"><span data-stu-id="756c1-104">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="756c1-105">**So zeigen Sie die Abhängigkeiten einer Prozedur an mit:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="756c1-105">**To view the dependencies of a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="756c1-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="756c1-106">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="756c1-107">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="756c1-107">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="756c1-108">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="756c1-108">Permissions</span></span>  
 <span data-ttu-id="756c1-109">Systemfunktion: `sys.dm_sql_referencing_entities`</span><span class="sxs-lookup"><span data-stu-id="756c1-109">System Function: `sys.dm_sql_referencing_entities`</span></span>  
 <span data-ttu-id="756c1-110">Erfordert die CONTROL-Berechtigung für die Entität, auf die verwiesen wird, und die SELECT-Berechtigung für sys.dm_sql_referencing_entities.</span><span class="sxs-lookup"><span data-stu-id="756c1-110">Requires CONTROL permission on the referenced entity and SELECT permission on sys.dm_sql_referencing_entities.</span></span> <span data-ttu-id="756c1-111">Wenn es sich bei der Entität, auf die verwiesen wird, um eine Partitionsfunktion handelt, ist die CONTROL-Berechtigung für die Datenbank erforderlich.</span><span class="sxs-lookup"><span data-stu-id="756c1-111">When the referenced entity is a partition function, CONTROL permission on the database is required.</span></span> <span data-ttu-id="756c1-112">Standardmäßig wird die SELECT-Berechtigung der public-Rolle erteilt.</span><span class="sxs-lookup"><span data-stu-id="756c1-112">By default, SELECT permission is granted to public.</span></span>  
  
 <span data-ttu-id="756c1-113">Systemfunktion: `sys.dm_sql_referenced_entities`</span><span class="sxs-lookup"><span data-stu-id="756c1-113">System Function: `sys.dm_sql_referenced_entities`</span></span>  
 <span data-ttu-id="756c1-114">Erfordert die SELECT-Berechtigung für sys.dm_sql_referenced_entities und die VIEW DEFINITION-Berechtigung für die verweisende Entität.</span><span class="sxs-lookup"><span data-stu-id="756c1-114">Requires SELECT permission on sys.dm_sql_referenced_entities and VIEW DEFINITION permission on the referencing entity.</span></span> <span data-ttu-id="756c1-115">Standardmäßig wird die SELECT-Berechtigung der public-Rolle erteilt.</span><span class="sxs-lookup"><span data-stu-id="756c1-115">By default, SELECT permission is granted to public.</span></span> <span data-ttu-id="756c1-116">Erfordert die Berechtigung VIEW DEFINITION oder ALTER DATABASE DDL TRIGGER für die Datenbank, wenn es sich bei der verweisenden Entität um einen DDL-Trigger auf Datenbankebene handelt.</span><span class="sxs-lookup"><span data-stu-id="756c1-116">Requires VIEW DEFINITION permission on the database or ALTER DATABASE DDL TRIGGER permission on the database when the referencing entity is a database-level DDL trigger.</span></span> <span data-ttu-id="756c1-117">Erfordert die VIEW ANY DEFINITION-Berechtigung für den Server, wenn es sich bei der verweisenden Entität um einen DDL-Trigger auf Serverebene handelt.</span><span class="sxs-lookup"><span data-stu-id="756c1-117">Requires VIEW ANY DEFINITION permission on the server when the referencing entity is a server-level DDL trigger.</span></span>  
  
 <span data-ttu-id="756c1-118">Objektkatalogsicht: `sys.sql_expression_dependencies`</span><span class="sxs-lookup"><span data-stu-id="756c1-118">Object Catalog View: `sys.sql_expression_dependencies`</span></span>  
 <span data-ttu-id="756c1-119">Erfordert die VIEW DEFINITION-Berechtigung für die Datenbank und die SELECT-Berechtigung für sys.sql_expression_dependencies für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="756c1-119">Requires VIEW DEFINITION permission on the database and SELECT permission on sys.sql_expression_dependencies for the database.</span></span> <span data-ttu-id="756c1-120">Standardmäßig wird die SELECT-Berechtigung nur Mitgliedern der festen Datenbankrolle db_owner gewährt.</span><span class="sxs-lookup"><span data-stu-id="756c1-120">By default, SELECT permission is granted only to members of the db_owner fixed database role.</span></span> <span data-ttu-id="756c1-121">Wenn einem anderen Benutzer die SELECT-Berechtigung und die VIEW DEFINITION-Berechtigung erteilt werden, kann dieser Berechtigte alle Abhängigkeiten in der Datenbank anzeigen.</span><span class="sxs-lookup"><span data-stu-id="756c1-121">When SELECT and VIEW DEFINITION permissions are granted to another user, the grantee can view all dependencies in the database.</span></span>  
  
##  <a name="how-to-view-the-dependencies-of-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="756c1-122">So zeigen Sie die Abhängigkeiten einer gespeicherten Prozedur an</span><span class="sxs-lookup"><span data-stu-id="756c1-122">How to View the Dependencies of a Stored Procedure</span></span>  
 <span data-ttu-id="756c1-123">Sie können eine der folgenden Anwendungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="756c1-123">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="756c1-124">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="756c1-124">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="756c1-125">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="756c1-125">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="756c1-126">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="756c1-126">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="756c1-127">**So zeigen Sie die Abhängigkeiten von einer Prozedur im Objekt-Explorer an**</span><span class="sxs-lookup"><span data-stu-id="756c1-127">**To view the dependencies of a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="756c1-128">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="756c1-128">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="756c1-129">Erweitern Sie **Datenbanken**, erweitern Sie die Datenbank, zu der die Prozedur gehört, und erweitern Sie dann **Programmierbarkeit**.</span><span class="sxs-lookup"><span data-stu-id="756c1-129">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="756c1-130">Erweitern Sie **Gespeicherte Prozeduren**, klicken Sie mit der rechten Maustaste auf die Prozedur, und klicken Sie dann auf **Abhängigkeiten anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="756c1-130">Expand **Stored Procedures**, right-click the procedure and then click **View Dependencies**.</span></span>  
  
4.  <span data-ttu-id="756c1-131">Zeigen Sie die Liste der Objekte an, die von der Prozedur abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="756c1-131">View the list of objects that depend on the procedure.</span></span>  
  
5.  <span data-ttu-id="756c1-132">Zeigen Sie die Liste der Objekte an, von denen die Prozedur abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="756c1-132">View the list of objects on which the procedure depends.</span></span>  
  
6.  <span data-ttu-id="756c1-133">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="756c1-133">Click **OK**.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="756c1-134">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="756c1-134">Using Transact-SQL</span></span>  
 <span data-ttu-id="756c1-135">**So zeigen Sie die Abhängigkeiten einer Prozedur im Abfrage-Editor an**</span><span class="sxs-lookup"><span data-stu-id="756c1-135">**To view the dependencies of a procedure in Query Editor**</span></span>  
  
 <span data-ttu-id="756c1-136">Systemfunktion: `sys.dm_sql_referencing_entities`</span><span class="sxs-lookup"><span data-stu-id="756c1-136">System Function: `sys.dm_sql_referencing_entities`</span></span>  
 <span data-ttu-id="756c1-137">Diese Funktion dient zum Anzeigen der Objekte, die von einer Prozedur abhängen.</span><span class="sxs-lookup"><span data-stu-id="756c1-137">This function is used to display the objects that depend on a procedure.</span></span>  
  
1.  <span data-ttu-id="756c1-138">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="756c1-138">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="756c1-139">Erweitern Sie **Datenbanken**, und erweitern Sie die Datenbank, der die Prozedur angehört.</span><span class="sxs-lookup"><span data-stu-id="756c1-139">Expand **Databases**, expand the database in which the procedure belongs.</span></span>  
  
3.  <span data-ttu-id="756c1-140">Klicken Sie im Menü **Datei** auf **Neue Abfrage** .</span><span class="sxs-lookup"><span data-stu-id="756c1-140">Click on **New Query** under the **File** menu.</span></span>  
  
4.  <span data-ttu-id="756c1-141">Kopieren Sie die folgenden Beispiele, und fügen Sie sie in den Abfrage-Editor ein.</span><span class="sxs-lookup"><span data-stu-id="756c1-141">Copy and paste the following examples into the query editor.</span></span> <span data-ttu-id="756c1-142">Im ersten Beispiel wird die `uspVendorAllInfo` -Prozedur erstellt. Diese Prozedur gibt die Namen, die gelieferten Produkte, die Bonität und die Verfügbarkeit aller Hersteller in der [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] -Datenbank, die das Unternehmen beliefern, zurück.</span><span class="sxs-lookup"><span data-stu-id="756c1-142">The first example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  <span data-ttu-id="756c1-143">Nachdem die Prozedur erstellt wurde, wird im zweiten Beispiel die sys.dm_sql_referencing_entities-Funktion verwendet, um die Objekte anzuzeigen, die von der Prozedur abhängen.</span><span class="sxs-lookup"><span data-stu-id="756c1-143">After the procedure is created, the second example uses the sys.dm_sql_referencing_entities function to display the objects that depend on the procedure.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT referencing_schema_name, referencing_entity_name, referencing_id, referencing_class_desc, is_caller_dependent  
    FROM sys.dm_sql_referencing_entities ('Purchasing.uspVendorAllInfo', 'OBJECT');   
    GO  
  
    ```  
  
 <span data-ttu-id="756c1-144">Systemfunktion: `sys.dm_sql_referenced_entities`</span><span class="sxs-lookup"><span data-stu-id="756c1-144">System Function: `sys.dm_sql_referenced_entities`</span></span>  
 <span data-ttu-id="756c1-145">Diese Funktion dient zum Anzeigen der Objekte, von denen eine Prozedur abhängt.</span><span class="sxs-lookup"><span data-stu-id="756c1-145">This function is used to display the objects a procedure depends on.</span></span>  
  
1.  <span data-ttu-id="756c1-146">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="756c1-146">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="756c1-147">Erweitern Sie **Datenbanken**, und erweitern Sie die Datenbank, der die Prozedur angehört.</span><span class="sxs-lookup"><span data-stu-id="756c1-147">Expand **Databases**, expand the database in which the procedure belongs.</span></span>  
  
3.  <span data-ttu-id="756c1-148">Klicken Sie im Menü **Datei** auf **Neue Abfrage** .</span><span class="sxs-lookup"><span data-stu-id="756c1-148">Click on **New Query** under the **File** menu.</span></span>  
  
4.  <span data-ttu-id="756c1-149">Kopieren Sie die folgenden Beispiele, und fügen Sie sie in den Abfrage-Editor ein.</span><span class="sxs-lookup"><span data-stu-id="756c1-149">Copy and paste the following examples into the query editor.</span></span> <span data-ttu-id="756c1-150">Im ersten Beispiel wird die `uspVendorAllInfo` -Prozedur erstellt. Diese Prozedur gibt die Namen, die gelieferten Produkte, die Bonität und die Verfügbarkeit aller Hersteller in der [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] -Datenbank, die das Unternehmen beliefern, zurück.</span><span class="sxs-lookup"><span data-stu-id="756c1-150">The first example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  <span data-ttu-id="756c1-151">Nachdem die Prozedur erstellt wurde, wird im zweiten Beispiel die sys.dm_sql_referenced_entities-Funktion verwendet, um die Objekte anzuzeigen, von denen die Prozedur abhängt.</span><span class="sxs-lookup"><span data-stu-id="756c1-151">After the procedure is created, the second example uses the sys.dm_sql_referenced_entities function to display the objects that the procedure depends on.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT referenced_schema_name, referenced_entity_name,  
    referenced_minor_name,referenced_minor_id, referenced_class_desc,  
    is_caller_dependent, is_ambiguous  
    FROM sys.dm_sql_referencing_entities ('Purchasing.uspVendorAllInfo', 'OBJECT');  
    GO  
    ```  
  
 <span data-ttu-id="756c1-152">Objektkatalogsicht: `sys.sql_expression_dependencies`</span><span class="sxs-lookup"><span data-stu-id="756c1-152">Object Catalog View: `sys.sql_expression_dependencies`</span></span>  
 <span data-ttu-id="756c1-153">Diese Sicht kann verwendet werden, um die Objekte anzuzeigen, von denen eine Prozedur abhängt, bzw. um die von einer Prozedur abhängigen Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="756c1-153">This view can be used to display objects that a procedure depends on or that depend on a procedure.</span></span>  
  
 <span data-ttu-id="756c1-154">Anzeigen der Objekte, die von einer Prozedur abhängen.</span><span class="sxs-lookup"><span data-stu-id="756c1-154">Displaying the objects that depend on a procedure.</span></span>  
 1.  <span data-ttu-id="756c1-155">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="756c1-155">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="756c1-156">Erweitern Sie **Datenbanken**, und erweitern Sie die Datenbank, der die Prozedur angehört.</span><span class="sxs-lookup"><span data-stu-id="756c1-156">Expand **Databases**, expand the database in which the procedure belongs.</span></span>  
  
3.  <span data-ttu-id="756c1-157">Klicken Sie im Menü **Datei** auf **Neue Abfrage** .</span><span class="sxs-lookup"><span data-stu-id="756c1-157">Click on **New Query** under the **File** menu.</span></span>  
  
4.  <span data-ttu-id="756c1-158">Kopieren Sie die folgenden Beispiele, und fügen Sie sie in den Abfrage-Editor ein.</span><span class="sxs-lookup"><span data-stu-id="756c1-158">Copy and paste the following examples into the query editor.</span></span> <span data-ttu-id="756c1-159">Im ersten Beispiel wird die `uspVendorAllInfo` -Prozedur erstellt. Diese Prozedur gibt die Namen, die gelieferten Produkte, die Bonität und die Verfügbarkeit aller Hersteller in der [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] -Datenbank, die das Unternehmen beliefern, zurück.</span><span class="sxs-lookup"><span data-stu-id="756c1-159">The first example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  <span data-ttu-id="756c1-160">Nachdem die Prozedur erstellt wurde, wird im zweiten Beispiel die sys.sql_expression_dependencies-Sicht verwendet, um die Objekte anzuzeigen, die von der Prozedur abhängen.</span><span class="sxs-lookup"><span data-stu-id="756c1-160">After the procedure is created, the second example uses the sys.sql_expression_dependencies view to display the objects that depend on the procedure.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT OBJECT_SCHEMA_NAME ( referencing_id ) AS referencing_schema_name,  
        OBJECT_NAME(referencing_id) AS referencing_entity_name,   
        o.type_desc AS referencing_desciption,   
        COALESCE(COL_NAME(referencing_id, referencing_minor_id), '(n/a)') AS referencing_minor_id,   
        referencing_class_desc, referenced_class_desc,  
        referenced_server_name, referenced_database_name, referenced_schema_name,  
        referenced_entity_name,   
        COALESCE(COL_NAME(referenced_id, referenced_minor_id), '(n/a)') AS referenced_column_name,  
        is_caller_dependent, is_ambiguous  
    FROM sys.sql_expression_dependencies AS sed  
    INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
    WHERE referenced_id = OBJECT_ID(N'Purchasing.uspVendorAllInfo')  
    GO  
    ```  
  
 <span data-ttu-id="756c1-161">Anzeigen der Objekte, von denen eine Prozedur abhängt.</span><span class="sxs-lookup"><span data-stu-id="756c1-161">Displaying the objects a procedure depends on.</span></span>  
 1.  <span data-ttu-id="756c1-162">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="756c1-162">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="756c1-163">Erweitern Sie **Datenbanken**, und erweitern Sie die Datenbank, der die Prozedur angehört.</span><span class="sxs-lookup"><span data-stu-id="756c1-163">Expand **Databases**, expand the database in which the procedure belongs.</span></span>  
  
3.  <span data-ttu-id="756c1-164">Klicken Sie im Menü **Datei** auf **Neue Abfrage** .</span><span class="sxs-lookup"><span data-stu-id="756c1-164">Click on **New Query** under the **File** menu.</span></span>  
  
4.  <span data-ttu-id="756c1-165">Kopieren Sie die folgenden Beispiele, und fügen Sie sie in den Abfrage-Editor ein.</span><span class="sxs-lookup"><span data-stu-id="756c1-165">Copy and paste the following examples into the query editor.</span></span> <span data-ttu-id="756c1-166">Im ersten Beispiel wird die `uspVendorAllInfo` -Prozedur erstellt. Diese Prozedur gibt die Namen, die gelieferten Produkte, die Bonität und die Verfügbarkeit aller Hersteller in der [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] -Datenbank, die das Unternehmen beliefern, zurück.</span><span class="sxs-lookup"><span data-stu-id="756c1-166">The first example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  <span data-ttu-id="756c1-167">Nachdem die Prozedur erstellt wurde, wird im zweiten Beispiel die sys.sql_expression_dependencies-Sicht verwendet, um die Objekte anzuzeigen, von denen die Prozedur abhängt.</span><span class="sxs-lookup"><span data-stu-id="756c1-167">After the procedure is created, the second example uses the sys.sql_expression_dependencies view to display the objects the procedure depends on.</span></span>  
  
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
    WHERE referencing_id = OBJECT_ID(N'Purchasing.uspVendorAllInfo')  
    GO  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="756c1-168">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="756c1-168">See Also</span></span>  
 <span data-ttu-id="756c1-169">[Umbenennen einer gespeicherten Prozedur](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="756c1-169">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="756c1-170">[sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="756c1-170">[sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql) </span></span>  
 <span data-ttu-id="756c1-171">[sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="756c1-171">[sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql) </span></span>  
 [<span data-ttu-id="756c1-172">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="756c1-172">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
  
