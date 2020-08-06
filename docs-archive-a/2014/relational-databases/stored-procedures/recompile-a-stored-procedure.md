---
title: Erneutes Kompilieren einer gespeicherten Prozedur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- sp_recompile
- WITH RECOMPILE clause
- recompiling stored procedures
- stored procedures [SQL Server], recompiling
ms.assetid: b90deb27-0099-4fe7-ba60-726af78f7c18
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2a9bc0e1d4baecb7f4c66b83b57081ed3131123d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630615"
---
# <a name="recompile-a-stored-procedure"></a><span data-ttu-id="e7420-102">Erneutes Kompilieren einer gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="e7420-102">Recompile a Stored Procedure</span></span>
  <span data-ttu-id="e7420-103">In diesem Thema wird beschrieben, wie Sie eine gespeicherte Prozedur in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[tsql](../../includes/tsql-md.md)]erneut kompilieren.</span><span class="sxs-lookup"><span data-stu-id="e7420-103">This topic describes how to recompile a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e7420-104">Hierfür gibt es drei Möglichkeiten: `WITH RECOMPILE` Option in der Prozedur Definition oder wenn die Prozedur aufgerufen wird, der `RECOMPILE` Abfrage Hinweis für einzelne Anweisungen oder die `sp_recompile` gespeicherte System Prozedur.</span><span class="sxs-lookup"><span data-stu-id="e7420-104">There are three ways to do this: `WITH RECOMPILE` option in the procedure definition or when the procedure is called, the `RECOMPILE` query hint on individual statements, or by using the `sp_recompile` system stored procedure.</span></span> <span data-ttu-id="e7420-105">In diesem Thema wird die Verwendung der WITH RECOMPILE-Option beim Erstellen einer Prozedurdefinition und Ausführen einer vorhandenen Prozedur beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e7420-105">This topic describes using the WITH RECOMPILE option when creating a procedure definition and executing an existing procedure.</span></span> <span data-ttu-id="e7420-106">Zudem wird erläutert, wie die gespeicherte Systemprozedur sp_recompile zum erneuten Kompilieren einer vorhandenen Prozedur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e7420-106">It also describes using the sp_recompile system stored procedure to recompile an existing procedure.</span></span>  
  
 <span data-ttu-id="e7420-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="e7420-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e7420-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="e7420-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e7420-109">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="e7420-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="e7420-110">Security</span><span class="sxs-lookup"><span data-stu-id="e7420-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e7420-111">**Erneutes Kompilieren einer gespeicherten Prozedur mit:**</span><span class="sxs-lookup"><span data-stu-id="e7420-111">**To recompile a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="e7420-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e7420-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e7420-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="e7420-113">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="e7420-114">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="e7420-114">Recommendations</span></span>  
  
-   <span data-ttu-id="e7420-115">Wenn eine Prozedur zum ersten Mal kompiliert oder erneut kompiliert wird, wird der Abfrageplan der Prozedur für den aktuellen Status der Datenbank und die darin enthaltenen Objekte optimiert.</span><span class="sxs-lookup"><span data-stu-id="e7420-115">When a procedure is compiled for the first time or recompiled, the procedure's query plan is optimized for the current state of the database and its objects.</span></span> <span data-ttu-id="e7420-116">Werden bedeutende Änderungen an den Daten oder der Struktur einer Datenbank vorgenommen, wird der Abfrageplan der Prozedur bei der erneuten Kompilierung für diese Änderungen aktualisiert und optimiert.</span><span class="sxs-lookup"><span data-stu-id="e7420-116">If a database undergoes significant changes to its data or structure, recompiling a procedure updates and optimizes the procedure's query plan for those changes.</span></span> <span data-ttu-id="e7420-117">Dies kann die Verarbeitungsleistung der Prozedur verbessern.</span><span class="sxs-lookup"><span data-stu-id="e7420-117">This can improve the procedure's processing performance.</span></span>  
  
-   <span data-ttu-id="e7420-118">In manchen Fällen muss die erneute Prozedurkompilierung erzwungen werden, in anderen findet sie automatisch statt.</span><span class="sxs-lookup"><span data-stu-id="e7420-118">There are times when procedure recompilation must be forced and other times when it occurs automatically.</span></span> <span data-ttu-id="e7420-119">Eine automatische erneute Kompilierung erfolgt bei jedem Neustart von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e7420-119">Automatic recompiling occurs whenever [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is restarted.</span></span> <span data-ttu-id="e7420-120">Sie findet auch statt, wenn physische Entwurfsänderungen an einer zugrunde liegenden Tabelle vorgenommen wurden, auf die die Prozedur verweist.</span><span class="sxs-lookup"><span data-stu-id="e7420-120">It also occurs if an underlying table referenced by the procedure has undergone physical design changes.</span></span>  
  
-   <span data-ttu-id="e7420-121">Eine erneute Kompilierung einer Prozedur kann auch erzwungen werden, um dem "Parametersniffing"-Verhalten bei der Kompilierung von Prozeduren entgegenzuwirken.</span><span class="sxs-lookup"><span data-stu-id="e7420-121">Another reason to force a procedure to recompile is to counteract the "parameter sniffing" behavior of procedure compilation.</span></span> <span data-ttu-id="e7420-122">Wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Prozeduren ausführt, werden alle bei der Kompilierung von der Prozedur verwendeten Parameterwerte in die Generierung des Abfrageplans einbezogen.</span><span class="sxs-lookup"><span data-stu-id="e7420-122">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executes procedures, any parameter values that are used by the procedure when it compiles are included as part of generating the query plan.</span></span> <span data-ttu-id="e7420-123">Handelt es sich bei diesen Werten um die normalen Werte, mit denen die Prozedur anschließend aufgerufen wird, profitiert die Prozedur bei jeder Kompilierung und Ausführung vom Abfrageplan.</span><span class="sxs-lookup"><span data-stu-id="e7420-123">If these values represent the typical ones with which the procedure is subsequently called, then the procedure benefits from the query plan every time that it compiles and executes.</span></span> <span data-ttu-id="e7420-124">Falls die Parameterwerte der Prozedur häufig untypisch sind, kann die Leistung durch Erzwingen einer erneuten Kompilierung der Prozedur und einen neuen Plan auf Grundlage anderer Parameterwerte verbessert werden.</span><span class="sxs-lookup"><span data-stu-id="e7420-124">If parameter values on the procedure are frequently atypical, forcing a recompile of the procedure and a new plan based on different parameter values can improve performance.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e7420-125">ermöglicht die erneute Kompilierung von Prozeduren auf Anweisungsebene.</span><span class="sxs-lookup"><span data-stu-id="e7420-125">features statement-level recompilation of procedures.</span></span> <span data-ttu-id="e7420-126">Wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gespeicherte Prozeduren erneut kompiliert, wird anstelle der vollständigen Prozedur nur die Anweisung kompiliert, die die erneute Kompilierung verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="e7420-126">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recompiles stored procedures, only the statement that caused the recompilation is compiled, instead of the complete procedure.</span></span>  
  
-   <span data-ttu-id="e7420-127">Wenn bei bestimmten Abfragen in einer Prozedur regelmäßig untypische oder temporäre Werte verwendet werden, kann die Prozedurleistung verbessert werden, indem der RECOMPILE-Abfragehinweis in diesen Abfragen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e7420-127">If certain queries in a procedure regularly use atypical or temporary values, procedure performance can be improved by using the RECOMPILE query hint inside those queries.</span></span> <span data-ttu-id="e7420-128">Da anstelle der vollständigen Prozedur nur die Abfragen mit dem Abfragehinweis erneut kompiliert werden, wird das Verhalten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]bei der erneuten Kompilierung auf Anweisungsebene imitiert.</span><span class="sxs-lookup"><span data-stu-id="e7420-128">Since only the queries using the query hint will be recompiled instead of the complete procedure, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]'s statement-level recompilation behavior is mimicked.</span></span> <span data-ttu-id="e7420-129">Zusätzlich zu den aktuellen Parameterwerten der Prozedur verwendet der RECOMPILE-Abfragehinweis beim Kompilieren der Anweisung auch die Werte von lokalen Variablen in der gespeicherten Prozedur.</span><span class="sxs-lookup"><span data-stu-id="e7420-129">But in addition to using the procedure's current parameter values, the RECOMPILE query hint also uses the values of any local variables inside the stored procedure when you compile the statement.</span></span> <span data-ttu-id="e7420-130">Weitere Informationen finden Sie unter [Abfragehinweis (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query).</span><span class="sxs-lookup"><span data-stu-id="e7420-130">For more information, see [Query Hint (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e7420-131">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e7420-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e7420-132">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e7420-132">Permissions</span></span>  
 <span data-ttu-id="e7420-133">`WITH RECOMPILE`Andere</span><span class="sxs-lookup"><span data-stu-id="e7420-133">`WITH RECOMPILE` Option</span></span>  
 <span data-ttu-id="e7420-134">Wenn diese Option beim Erstellen der Prozedurdefinition verwendet wird, erfordert sie die CREATE PROCEDURE-Berechtigung für die Datenbank und die ALTER-Berechtigung für das Schema, in dem die Prozedur erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="e7420-134">If this option is used when the procedure definition is created, it requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created.</span></span>  
  
 <span data-ttu-id="e7420-135">Wenn diese Option in einer EXECUTE-Anweisung verwendet wird, erfordert sie EXECUTE-Berechtigungen für die Prozedur.</span><span class="sxs-lookup"><span data-stu-id="e7420-135">If this option is used in an EXECUTE statement, it requires EXECUTE permissions on the procedure.</span></span> <span data-ttu-id="e7420-136">Berechtigungen für die EXECUTE-Anweisung selbst sind nicht erforderlich, es sind jedoch Ausführungsberechtigungen für die Prozedur erforderlich, auf die in der EXECUTE-Anweisung verwiesen sind.</span><span class="sxs-lookup"><span data-stu-id="e7420-136">Permissions are not required on the EXECUTE statement itself but execute permissions are required on the procedure referenced in the EXECUTE statement.</span></span> <span data-ttu-id="e7420-137">Weitere Informationen finden Sie unter [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e7420-137">For more information, see [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span></span>  
  
 <span data-ttu-id="e7420-138">`RECOMPILE`Abfrage Hinweis</span><span class="sxs-lookup"><span data-stu-id="e7420-138">`RECOMPILE` Query Hint</span></span>  
 <span data-ttu-id="e7420-139">Diese Funktion wird beim Erstellen der Prozedur verwendet, und der Hinweis wird in [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen in der Prozedur eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e7420-139">This feature is used when the procedure is created and the hint is included in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the procedure.</span></span> <span data-ttu-id="e7420-140">Daher erfordert sie die CREATE PROCEDURE-Berechtigung für die Datenbank und die ALTER-Berechtigung für das Schema, in dem die Prozedur erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="e7420-140">Therefore, it requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created.</span></span>  
  
 <span data-ttu-id="e7420-141">`sp_recompile`Gespeicherte System Prozedur</span><span class="sxs-lookup"><span data-stu-id="e7420-141">`sp_recompile` System Stored Procedure</span></span>  
 <span data-ttu-id="e7420-142">Erfordert die ALTER-Berechtigung für die angegebene Prozedur.</span><span class="sxs-lookup"><span data-stu-id="e7420-142">Requires ALTER permission on the specified procedure.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e7420-143">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e7420-143">Using Transact-SQL</span></span>  
  
#### <a name="to-recompile-a-stored-procedure-by-using-the-with-recompile-option"></a><span data-ttu-id="e7420-144">So kompilieren Sie eine gespeicherte Prozedur mithilfe der WITH RECOMPILE-Option erneut</span><span class="sxs-lookup"><span data-stu-id="e7420-144">To recompile a stored procedure by using the WITH RECOMPILE option</span></span>  
  
1.  <span data-ttu-id="e7420-145">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="e7420-145">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e7420-146">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e7420-146">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e7420-147">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e7420-147">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e7420-148">In diesem Beispiel wird die Prozedurdefinition erstellt.</span><span class="sxs-lookup"><span data-stu-id="e7420-148">This example creates the procedure definition.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'dbo.uspProductByVendor', 'P' ) IS NOT NULL   
    DROP PROCEDURE dbo.uspProductByVendor;  
GO  
CREATE PROCEDURE dbo.uspProductByVendor @Name varchar(30) = '%'  
WITH RECOMPILE  
AS  
    SET NOCOUNT ON;  
    SELECT v.Name AS 'Vendor name', p.Name AS 'Product name'  
    FROM Purchasing.Vendor AS v   
    JOIN Purchasing.ProductVendor AS pv   
      ON v.BusinessEntityID = pv.BusinessEntityID   
    JOIN Production.Product AS p   
      ON pv.ProductID = p.ProductID  
    WHERE v.Name LIKE @Name;  
  
```  
  
#### <a name="to-recompile-a-stored-procedure-by-using-the-with-recompile-option"></a><span data-ttu-id="e7420-149">So kompilieren Sie eine gespeicherte Prozedur mithilfe der WITH RECOMPILE-Option erneut</span><span class="sxs-lookup"><span data-stu-id="e7420-149">To recompile a stored procedure by using the WITH RECOMPILE option</span></span>  
  
1.  <span data-ttu-id="e7420-150">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="e7420-150">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e7420-151">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e7420-151">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e7420-152">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e7420-152">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e7420-153">In diesem Beispiel wird eine einfache Prozedur erstellt, die alle Mitarbeiter (mit Vor- und Nachnamen), ihre Stellenbezeichnungen und ihre Abteilungsnamen aus einer Sicht zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e7420-153">This example creates a simple procedure that returns all employees (first and last names supplied), their job titles, and their department names from a view.</span></span>  
  
     <span data-ttu-id="e7420-154">Kopieren Sie anschließend das zweite Codebeispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e7420-154">And then copy and paste the second code example into the query window and click **Execute**.</span></span> <span data-ttu-id="e7420-155">Dadurch wird die Prozedur ausgeführt und der Abfrageplan der Prozedur erneut kompiliert.</span><span class="sxs-lookup"><span data-stu-id="e7420-155">This executes the procedure and recompiles the procedure's query plan.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXECUTE HumanResources.uspGetAllEmployees WITH RECOMPILE;  
GO  
  
```  
  
#### <a name="to-recompile-a-stored-procedure-by-using-sp_recompile"></a><span data-ttu-id="e7420-156">So kompilieren Sie eine gespeicherte Prozedur mithilfe von sp_recompile erneut</span><span class="sxs-lookup"><span data-stu-id="e7420-156">To recompile a stored procedure by using sp_recompile</span></span>  
  
1.  <span data-ttu-id="e7420-157">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="e7420-157">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e7420-158">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e7420-158">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e7420-159">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e7420-159">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e7420-160">In diesem Beispiel wird eine einfache Prozedur erstellt, die alle Mitarbeiter (mit Vor- und Nachnamen), ihre Stellenbezeichnungen und ihre Abteilungsnamen aus einer Sicht zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e7420-160">This example creates a simple procedure that returns all employees (first and last names supplied), their job titles, and their department names from a view.</span></span>  
  
     <span data-ttu-id="e7420-161">Kopieren Sie anschließend das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e7420-161">Then, copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e7420-162">Dadurch wird die Prozedur nicht ausgeführt, aber für die erneute Kompilierung markiert, sodass ihr Abfrageplan bei der nächsten Ausführung der Prozedur aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="e7420-162">This does not execute the procedure but it does mark the procedure to be recompiled so that its query plan is updated the next time that the procedure is executed.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_recompile N'HumanResources.uspGetAllEmployees';  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7420-163">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e7420-163">See Also</span></span>  
 <span data-ttu-id="e7420-164">[Erstellen einer gespeicherten Prozedur](../stored-procedures/create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="e7420-164">[Create a Stored Procedure](../stored-procedures/create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="e7420-165">[Ändern einer gespeicherten Prozedur](../stored-procedures/modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="e7420-165">[Modify a Stored Procedure](../stored-procedures/modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="e7420-166">[Umbenennen einer gespeicherten Prozedur](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="e7420-166">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="e7420-167">[Anzeigen der Definition einer gespeicherten Prozedur](view-the-definition-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="e7420-167">[View the Definition of a Stored Procedure](view-the-definition-of-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="e7420-168">[Anzeigen der Abhängigkeiten einer gespeicherten Prozedur](view-the-dependencies-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="e7420-168">[View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="e7420-169">DROP PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e7420-169">DROP PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-procedure-transact-sql)  
  
  
