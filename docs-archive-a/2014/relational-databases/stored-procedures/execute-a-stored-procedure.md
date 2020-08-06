---
title: Ausführen einer gespeicherten Prozedur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.executeprocedure.f1
- sql12.swb.executeprocedure.general.f1
helpviewer_keywords:
- stored procedures [SQL Server], parameters
- extended stored procedures [SQL Server], executing
- system stored procedures [SQL Server], executing
- stored procedures [SQL Server], executing
- user-defined stored procedures [SQL Server]
ms.assetid: a0b1337d-2059-4872-8c62-3f967d8b170f
author: stevestein
ms.author: sstein
ms.openlocfilehash: c679ba7af3ac9f60d312b33c0346e50687387476
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621400"
---
# <a name="execute-a-stored-procedure"></a><span data-ttu-id="e3c93-102">Ausführen einer gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="e3c93-102">Execute a Stored Procedure</span></span>
  <span data-ttu-id="e3c93-103">In diesem Thema wird beschrieben, wie Sie eine gespeicherte Prozedur in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]ausführen.</span><span class="sxs-lookup"><span data-stu-id="e3c93-103">This topic describes how to execute a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="e3c93-104">Zum Ausführen einer gespeicherten Prozedur stehen zwei Möglichkeiten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e3c93-104">There are two different ways to execute a stored procedure.</span></span> <span data-ttu-id="e3c93-105">Der erste und gebräuchlichste Ansatz besteht darin, dass eine Anwendung oder ein Benutzer die Prozedur aufruft.</span><span class="sxs-lookup"><span data-stu-id="e3c93-105">The first and most common approach is for an application or user to call the procedure.</span></span> <span data-ttu-id="e3c93-106">Der zweite Ansatz ist das Einrichten der Prozedur zur automatischen Ausführung beim Start einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3c93-106">The second approach is to set the procedure to run automatically when an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] starts.</span></span> <span data-ttu-id="e3c93-107">Wenn eine Prozedur von einer Anwendung oder einem Benutzer aufgerufen wird, wird das [!INCLUDE[tsql](../../includes/tsql-md.md)] EXECUTE- oder EXEC-Schlüsselwort explizit im Aufruf angegeben.</span><span class="sxs-lookup"><span data-stu-id="e3c93-107">When a procedure is called by an application or user, the [!INCLUDE[tsql](../../includes/tsql-md.md)] EXECUTE or EXEC keyword is explicitly stated in the call.</span></span> <span data-ttu-id="e3c93-108">Falls es sich bei der Prozedur um die erste Anweisung im [!INCLUDE[tsql](../../includes/tsql-md.md)] -Batch handelt, kann sie alternativ ohne das Schlüsselwort aufgerufen und ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e3c93-108">Alternatively, the procedure can be called and executed without the keyword if the procedure is the first statement in the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch.</span></span>  
  
 <span data-ttu-id="e3c93-109">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="e3c93-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e3c93-110">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="e3c93-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e3c93-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e3c93-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e3c93-112">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="e3c93-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="e3c93-113">Security</span><span class="sxs-lookup"><span data-stu-id="e3c93-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e3c93-114">**Ausführen einer gespeicherten Prozedur mit:**</span><span class="sxs-lookup"><span data-stu-id="e3c93-114">**To execute a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="e3c93-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e3c93-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e3c93-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e3c93-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e3c93-117">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="e3c93-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e3c93-118">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e3c93-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e3c93-119">Die Sortierung der aufrufenden Datenbank wird beim Zuordnen von Systemprozedurnamen verwendet.</span><span class="sxs-lookup"><span data-stu-id="e3c93-119">The calling database collation is used when matching system procedure names.</span></span> <span data-ttu-id="e3c93-120">Aus diesem Grund muss in Prozeduraufrufen immer die genaue Groß-/Kleinschreibung von Systemprozedurnamen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e3c93-120">Therefore, always use the exact case of system procedure names in procedure calls.</span></span> <span data-ttu-id="e3c93-121">Der folgende Code schlägt z. B. fehl, wenn er im Kontext einer Datenbank ausgeführt wird, bei deren Sortierung die Groß-/Kleinschreibung beachtet wird:</span><span class="sxs-lookup"><span data-stu-id="e3c93-121">For example, this code will fail if it is executed in the context of a database that has a case-sensitive collation:</span></span>  
  
    ```sql  
    EXEC SP_heLP; -- Will fail to resolve because SP_heLP does not equal sp_help  
    ```  
  
     <span data-ttu-id="e3c93-122">Fragen Sie die Katalogsichten [sys.system_objects](/sql/relational-databases/system-catalog-views/sys-system-objects-transact-sql) und [sys.system_parameters](/sql/relational-databases/system-catalog-views/sys-system-parameters-transact-sql) ab, um die genauen Systemprozedurnamen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e3c93-122">To display the exact system procedure names, query the [sys.system_objects](/sql/relational-databases/system-catalog-views/sys-system-objects-transact-sql) and [sys.system_parameters](/sql/relational-databases/system-catalog-views/sys-system-parameters-transact-sql) catalog views.</span></span>  
  
-   <span data-ttu-id="e3c93-123">Wenn eine benutzerdefinierte Prozedur den gleichen Namen besitzt wie eine Systemprozedur, wird die benutzerdefinierte Prozedur möglicherweise nie ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e3c93-123">If a user-defined procedure has the same name as a system procedure, the user-defined procedure might not ever execute.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="e3c93-124">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="e3c93-124">Recommendations</span></span>  
  
-   <span data-ttu-id="e3c93-125">Ausführen von gespeicherten Systemprozeduren</span><span class="sxs-lookup"><span data-stu-id="e3c93-125">Executing System Stored Procedures</span></span>  
  
     <span data-ttu-id="e3c93-126">Systemprozeduren beginnen mit dem Präfix **sp_** .</span><span class="sxs-lookup"><span data-stu-id="e3c93-126">System procedures begin with the prefix **sp_**.</span></span> <span data-ttu-id="e3c93-127">Da sie in allen benutzer- und systemdefinierten Datenbanken logisch angezeigt werden, können sie in jeder Datenbank ausgeführt werden, ohne den Prozedurnamen voll zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="e3c93-127">Because they logically appear in all user- and system- defined databases, they can be executed from any database without having to fully quality the procedure name.</span></span> <span data-ttu-id="e3c93-128">Es wird jedoch empfohlen, die Namen aller Systemprozeduren mit dem **sys** -Schemanamen für das Schema zu qualifizieren, um Namenskonflikte zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="e3c93-128">However, we recommend schema-qualifying all system procedure names with the **sys** schema name to prevent name conflicts.</span></span> <span data-ttu-id="e3c93-129">Das folgende Beispiel zeigt die empfohlene Methode für das Aufrufen einer Systemprozedur.</span><span class="sxs-lookup"><span data-stu-id="e3c93-129">The following example demonstrates the recommended method of calling a system procedure.</span></span>  
  
    ```sql  
    EXEC sys.sp_who;  
    ```  
  
-   <span data-ttu-id="e3c93-130">Ausführen von benutzerdefinierten gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="e3c93-130">Executing User-defined Stored Procedures</span></span>  
  
     <span data-ttu-id="e3c93-131">Beim Ausführen einer benutzerdefinierten Prozedur empfiehlt es sich, den Prozedurnamen mit dem Schemanamen zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="e3c93-131">When executing a user-defined procedure, we recommend qualifying the procedure name with the schema name.</span></span> <span data-ttu-id="e3c93-132">Auf diese Weise lässt sich die Leistung geringfügig verbessern, da [!INCLUDE[ssDE](../../../includes/ssde-md.md)] nicht mehrere Schemas durchsuchen muss.</span><span class="sxs-lookup"><span data-stu-id="e3c93-132">This practice gives a small performance boost because the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] does not have to search multiple schemas.</span></span> <span data-ttu-id="e3c93-133">Zudem können Sie so verhindern, dass die falsche Prozedur ausgeführt, wenn eine Datenbank in mehreren Schemas über Prozeduren mit dem gleichen Namen verfügt.</span><span class="sxs-lookup"><span data-stu-id="e3c93-133">It also prevents executing the wrong procedure if a database has procedures with the same name in multiple schemas.</span></span>  
  
     <span data-ttu-id="e3c93-134">Das folgende Beispiel zeigt die empfohlene Methode für das Ausführen einer benutzerdefinierten Prozedur.</span><span class="sxs-lookup"><span data-stu-id="e3c93-134">The following example demonstrates the recommended method to execute a user-defined procedure.</span></span> <span data-ttu-id="e3c93-135">Beachten Sie, dass die Prozedur einen Eingabeparameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="e3c93-135">Notice that the procedure accepts one input parameter.</span></span> <span data-ttu-id="e3c93-136">Informationen zum Angeben von Ein- und Ausgabeparametern finden Sie unter [Angeben von Parametern](specify-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="e3c93-136">For information about specifying input and output parameters, see [Specify Parameters](specify-parameters.md).</span></span>  
  
    ```sql  
    USE AdventureWorks2012;  
    GO  
    EXEC dbo.uspGetEmployeeManagers @BusinessEntityID = 50;  
    ```  
  
     <span data-ttu-id="e3c93-137">-Oder-</span><span class="sxs-lookup"><span data-stu-id="e3c93-137">-Or-</span></span>  
  
    ```sql  
    EXEC AdventureWorks2012.dbo.uspGetEmployeeManagers 50;  
    GO  
    ```  
  
     <span data-ttu-id="e3c93-138">Wird der nicht gekennzeichnete Name einer benutzerdefinierten Prozedur angegeben, durchsucht [!INCLUDE[ssDE](../../../includes/ssde-md.md)] die folgenden Schemas in der angegebenen Reihenfolge nach der Prozedur:</span><span class="sxs-lookup"><span data-stu-id="e3c93-138">If a nonqualified user-defined procedure is specified, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] searches for the procedure in the following order:</span></span>  
  
    1.  <span data-ttu-id="e3c93-139">Das **sys** -Schema der aktuellen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="e3c93-139">The **sys** schema of the current database.</span></span>  
  
    2.  <span data-ttu-id="e3c93-140">Das Standardschema des Aufrufers, wenn die Prozedur als Batch oder dynamisches SQL ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e3c93-140">The caller's default schema if it is executed in a batch or in dynamic SQL.</span></span> <span data-ttu-id="e3c93-141">Falls aber der nicht qualifizierte Name der Prozedur im Textkörper einer anderen Prozedurdefinition vorkommt, wird als nächstes das Schema durchsucht, das diese andere Prozedur enthält.</span><span class="sxs-lookup"><span data-stu-id="e3c93-141">Or, if the nonqualified procedure name appears inside the body of another procedure definition, the schema that contains this other procedure is searched next.</span></span>  
  
    3.  <span data-ttu-id="e3c93-142">Das **dbo** -Schema in der aktuellen Datenbank</span><span class="sxs-lookup"><span data-stu-id="e3c93-142">The **dbo** schema in the current database.</span></span>  
  
-   <span data-ttu-id="e3c93-143">Automatisches Ausführen von gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="e3c93-143">Executing Stored Procedures Automatically</span></span>  
  
     <span data-ttu-id="e3c93-144">Zur automatischen Ausführung markierte Prozeduren werden bei jedem Start von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgeführt, und die **master** -Datenbank wird während dieses Startprozesses wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="e3c93-144">Procedures marked for automatic execution are executed every time [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] starts and the **master** database is recovered during that startup process.</span></span> <span data-ttu-id="e3c93-145">Das Einrichten von Prozeduren zur automatischen Ausführung kann für Datenbankwartungsvorgänge oder die fortlaufende Ausführung von Prozeduren als Hintergrundprozesse nützlich sein.</span><span class="sxs-lookup"><span data-stu-id="e3c93-145">Setting up procedures to execute automatically can be useful for performing database maintenance operations or for having procedures run continuously as background processes.</span></span> <span data-ttu-id="e3c93-146">Die automatische Ausführung kann auch verwendet werden, um System- oder Wartungstasks in **tempdb**auszuführen, z. B. das Erstellen einer globalen temporären Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e3c93-146">Another use for automatic execution is to have the procedure perform system or maintenance tasks in **tempdb**, such as creating a global temporary table.</span></span> <span data-ttu-id="e3c93-147">Auf diese Weise wird sichergestellt, dass eine solche temporäre Tabelle immer vorhanden ist, wenn **tempdb** beim Start von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] neu erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="e3c93-147">This makes sure that such a temporary table will always exist when **tempdb** is re-created during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup.</span></span>  
  
     <span data-ttu-id="e3c93-148">Eine automatisch ausgeführte Prozedur wird mit den Berechtigungen ausgeführt, die den Mitgliedern der festen Serverrolle **sysadmin** zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="e3c93-148">A procedure that is automatically executed operates with the same permissions as members of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="e3c93-149">Alle Fehlermeldungen, die von der Prozedur erzeugt werden, werden in das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlerprotokoll geschrieben.</span><span class="sxs-lookup"><span data-stu-id="e3c93-149">Any error messages generated by the procedure are written to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
     <span data-ttu-id="e3c93-150">Es gibt keine Beschränkung für die Anzahl der Autostartprozeduren. Bedenken Sie jedoch, dass jede dieser Prozeduren während der Ausführung jeweils einen Arbeitsthread belegt.</span><span class="sxs-lookup"><span data-stu-id="e3c93-150">There is no limit to the number of startup procedures you can have, but be aware that each consumes one worker thread while executing.</span></span> <span data-ttu-id="e3c93-151">Wenn Sie beim Systemstart mehrere Prozeduren ausführen müssen, diese aber nicht parallel ausgeführt werden müssen, legen Sie eine Prozedur als Autostartprozedur fest, und schreiben Sie diese Prozedur so, dass sie die anderen Prozeduren aufruft.</span><span class="sxs-lookup"><span data-stu-id="e3c93-151">If you must execute multiple procedures at startup but do not need to execute them in parallel, make one procedure the startup procedure and have that procedure call the other procedures.</span></span> <span data-ttu-id="e3c93-152">Dadurch wird nur ein Arbeitsthread benötigt.</span><span class="sxs-lookup"><span data-stu-id="e3c93-152">This uses only one worker thread.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="e3c93-153">Von einer automatisch ausgeführten Prozedur sollten keine Resultsets zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e3c93-153">Do not return any result sets from a procedure that is executed automatically.</span></span> <span data-ttu-id="e3c93-154">Da die Prozedur von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und nicht von einer Anwendung oder einem Benutzer ausgeführt wird, gibt es kein Ausgabeziel für die Resultsets.</span><span class="sxs-lookup"><span data-stu-id="e3c93-154">Because the procedure is being executed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instead of an application or user, there is nowhere for the result sets to go.</span></span>  
  
-   <span data-ttu-id="e3c93-155">Festlegen, Löschen und Steuern der automatischen Ausführung</span><span class="sxs-lookup"><span data-stu-id="e3c93-155">Setting, Clearing, and Controlling Automatic Execution</span></span>  
  
     <span data-ttu-id="e3c93-156">Nur der Systemadministrator (**sa**) kann eine Prozedur für die automatische Ausführung markieren.</span><span class="sxs-lookup"><span data-stu-id="e3c93-156">Only the system administrator (**sa**) can mark a procedure to execute automatically.</span></span> <span data-ttu-id="e3c93-157">Die Prozedur muss sich außerdem in der **master** -Datenbank im Besitz von **sa**befinden und darf keine Eingabe- oder Ausgabeparameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="e3c93-157">In addition, the procedure must be in the **master** database, owned by **sa**, and cannot have input or output parameters.</span></span>  
  
     <span data-ttu-id="e3c93-158">Verwenden Sie [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) für folgende Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="e3c93-158">Use [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) to:</span></span>  
  
    1.  <span data-ttu-id="e3c93-159">Angeben einer vorhandenen Prozedur als Startprozedur.</span><span class="sxs-lookup"><span data-stu-id="e3c93-159">Designate an existing procedure as a startup procedure.</span></span>  
  
    2.  <span data-ttu-id="e3c93-160">Verhindern der Ausführung einer Prozedur beim Start von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3c93-160">Stop a procedure from executing at [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e3c93-161">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e3c93-161">Security</span></span>  
 <span data-ttu-id="e3c93-162">Weitere Informationen finden Sie unter [EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-transact-sql) und [EXECUTE AS-Klausel &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e3c93-162">For more information, see [EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-transact-sql) and [EXECUTE AS Clause &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e3c93-163">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e3c93-163">Permissions</span></span>  
 <span data-ttu-id="e3c93-164">Weitere Informationen finden Sie unter [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql)ausführen.</span><span class="sxs-lookup"><span data-stu-id="e3c93-164">For more information, see the "Permissions" section in [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e3c93-165">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e3c93-165">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-execute-a-stored-procedure"></a><span data-ttu-id="e3c93-166">So führen Sie eine gespeicherte Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="e3c93-166">To execute a stored procedure</span></span>  
  
1.  <span data-ttu-id="e3c93-167">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, erweitern Sie diese Instanz und dann **Datenbanken**.</span><span class="sxs-lookup"><span data-stu-id="e3c93-167">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="e3c93-168">Erweitern Sie die gewünschte Datenbank, **Programmierbarkeit**und dann **Gespeicherte Prozeduren**.</span><span class="sxs-lookup"><span data-stu-id="e3c93-168">Expand the database that you want, expand **Programmability**, and then expand **Stored Procedures**.</span></span>  
  
3.  <span data-ttu-id="e3c93-169">Klicken Sie mit der rechten Maustaste auf die gewünschte benutzerdefinierte gespeicherte Prozedur, und klicken Sie dann auf **Gespeicherte Prozedur ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e3c93-169">Right-click the user-defined stored procedure that you want and click **Execute Stored Procedure**.</span></span>  
  
4.  <span data-ttu-id="e3c93-170">Geben Sie im Dialogfeld **Prozedur ausführen** einen Wert für jeden Parameter an, und legen Sie fest, ob er einen NULL-Wert übergeben soll.</span><span class="sxs-lookup"><span data-stu-id="e3c93-170">In the **Execute Procedure** dialog box, specify a value for each parameter and whether it should pass a null value.</span></span>  
  
     <span data-ttu-id="e3c93-171">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="e3c93-171">**Parameter**</span></span>  
     <span data-ttu-id="e3c93-172">Zeigt den Namen des Parameters an.</span><span class="sxs-lookup"><span data-stu-id="e3c93-172">Indicates the name of the parameter.</span></span>  
  
     <span data-ttu-id="e3c93-173">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="e3c93-173">**Data Type**</span></span>  
     <span data-ttu-id="e3c93-174">Zeigt den Datentyp des Parameters an.</span><span class="sxs-lookup"><span data-stu-id="e3c93-174">Indicates the data type of the parameter.</span></span>  
  
     <span data-ttu-id="e3c93-175">**Ausgabeparameter**</span><span class="sxs-lookup"><span data-stu-id="e3c93-175">**Output Parameter**</span></span>  
     <span data-ttu-id="e3c93-176">Zeigt an, ob es sich um einen Ausgabeparameter handelt.</span><span class="sxs-lookup"><span data-stu-id="e3c93-176">Indicates if this is an output parameter.</span></span>  
  
     <span data-ttu-id="e3c93-177">**NULL-Wert übergeben**</span><span class="sxs-lookup"><span data-stu-id="e3c93-177">**Pass Null Value**</span></span>  
     <span data-ttu-id="e3c93-178">Übergibt als Wert des Parameters einen NULL-Wert.</span><span class="sxs-lookup"><span data-stu-id="e3c93-178">Pass a NULL as the value of the parameter.</span></span>  
  
     <span data-ttu-id="e3c93-179">**Wert**</span><span class="sxs-lookup"><span data-stu-id="e3c93-179">**Value**</span></span>  
     <span data-ttu-id="e3c93-180">Geben Sie den Wert des Parameters bei Aufruf der Prozedur ein.</span><span class="sxs-lookup"><span data-stu-id="e3c93-180">Type the value for the parameter when calling the procedure.</span></span>  
  
5.  <span data-ttu-id="e3c93-181">Klicken Sie auf **OK**, um die gespeicherte Prozedur auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e3c93-181">To execute the stored procedure, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e3c93-182">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e3c93-182">Using Transact-SQL</span></span>  
  
#### <a name="to-execute-a-stored-procedure"></a><span data-ttu-id="e3c93-183">So führen Sie eine gespeicherte Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="e3c93-183">To execute a stored procedure</span></span>  
  
1.  <span data-ttu-id="e3c93-184">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="e3c93-184">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e3c93-185">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e3c93-185">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e3c93-186">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e3c93-186">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e3c93-187">Dieses Beispiel zeigt, wie eine gespeicherte Prozedur ausgeführt wird, die einen Parameter erwartet.</span><span class="sxs-lookup"><span data-stu-id="e3c93-187">This example shows how to execute a stored procedure that expects one parameter.</span></span> <span data-ttu-id="e3c93-188">Im Beispiel wird die gespeicherte Prozedur `uspGetEmployeeManagers` mit dem  `6` -Parameterwert `@EmployeeID` ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e3c93-188">The example executes the `uspGetEmployeeManagers` stored procedure with the value  `6` specified as the `@EmployeeID` parameter.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC dbo.uspGetEmployeeManagers 6;  
GO  
```  
  
#### <a name="to-set-or-clear-a-procedure-for-executing-automatically"></a><span data-ttu-id="e3c93-189">So legen Sie die automatische Ausführung für eine gespeicherte Prozedur fest oder deaktivieren Sie sie</span><span class="sxs-lookup"><span data-stu-id="e3c93-189">To set or clear a procedure for executing automatically</span></span>  
  
1.  <span data-ttu-id="e3c93-190">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="e3c93-190">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e3c93-191">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e3c93-191">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e3c93-192">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e3c93-192">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e3c93-193">Dieses Beispiel zeigt, wie [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) verwendet wird, um die automatische Ausführung einer Prozedur festzulegen.</span><span class="sxs-lookup"><span data-stu-id="e3c93-193">This example shows how to use [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) to set a procedure for automatic execution.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_procoption @ProcName = '<procedure name>'   
    , @OptionName = ] 'startup'   
    , @OptionValue = 'on';  
```  
  
#### <a name="to-stop-a-procedure-from-executing-automatically"></a><span data-ttu-id="e3c93-194">So verhindern Sie die automatische Ausführung einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="e3c93-194">To stop a procedure from executing automatically</span></span>  
  
1.  <span data-ttu-id="e3c93-195">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="e3c93-195">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e3c93-196">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e3c93-196">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e3c93-197">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e3c93-197">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e3c93-198">Dieses Beispiel zeigt, wie [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) verwendet wird, um die automatische Ausführung einer Prozedur zu beenden.</span><span class="sxs-lookup"><span data-stu-id="e3c93-198">This example shows how to use [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) to stop a procedure from executing automatically.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_procoption @ProcName = '<procedure name>'   
    , @OptionValue = 'off';  
```  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="e3c93-199">Beispiel (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e3c93-199">Example (Transact-SQL)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3c93-200">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e3c93-200">See Also</span></span>  
 <span data-ttu-id="e3c93-201">[Angeben von Parametern](specify-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="e3c93-201">[Specify Parameters](specify-parameters.md) </span></span>  
 <span data-ttu-id="e3c93-202">[Konfigurieren der Serverkonfigurationsoption Startprozeduren suchen](../../database-engine/configure-windows/configure-the-scan-for-startup-procs-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="e3c93-202">[Configure the scan for startup procs Server Configuration Option](../../database-engine/configure-windows/configure-the-scan-for-startup-procs-server-configuration-option.md) </span></span>  
 <span data-ttu-id="e3c93-203">[EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e3c93-203">[EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql) </span></span>  
 <span data-ttu-id="e3c93-204">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e3c93-204">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 [<span data-ttu-id="e3c93-205">Gespeicherte Prozeduren &#40;Datenbank-Engine&#41;</span><span class="sxs-lookup"><span data-stu-id="e3c93-205">Stored Procedures &#40;Database Engine&#41;</span></span>](stored-procedures-database-engine.md)  
  
  
