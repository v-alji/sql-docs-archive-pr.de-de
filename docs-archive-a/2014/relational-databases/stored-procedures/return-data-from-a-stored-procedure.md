---
title: Zurückgeben von Daten von einer gespeicherten Prozedur | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], returning data
- returning data from stored procedure
ms.assetid: 7a428ffe-cd87-4f42-b3f1-d26aa8312bf7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 472ca5cf27f7e7ea2b18daa961c19faadcf2251f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630611"
---
# <a name="return-data-from-a-stored-procedure"></a><span data-ttu-id="309d2-102">Zurückgeben von Daten von einer gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="309d2-102">Return Data from a Stored Procedure</span></span>
  <span data-ttu-id="309d2-103">Es gibt zwei Methoden, Resultsets oder Daten von einer Prozedur an ein aufrufendes Programm zurückzugeben: Ausgabeparameter und Rückgabecodes.</span><span class="sxs-lookup"><span data-stu-id="309d2-103">There are two ways of returning result sets or data from a procedure to a calling program: output parameters and return codes.</span></span> <span data-ttu-id="309d2-104">Dieses Thema enthält Informationen zu beiden Ansätzen.</span><span class="sxs-lookup"><span data-stu-id="309d2-104">This topic provides information on both approaches.</span></span>  
  
## <a name="returning-data-using-an-output-parameter"></a><span data-ttu-id="309d2-105">Zurückgeben von Daten mithilfe eines OUTPUT-Parameters</span><span class="sxs-lookup"><span data-stu-id="309d2-105">Returning Data Using an Output Parameter</span></span>  
 <span data-ttu-id="309d2-106">Wenn Sie in der Prozedurdefinition für einen Parameter das Schlüsselwort OUTPUT angeben, kann die Prozedur den aktuellen Wert des Parameters an das aufrufende Programm zurückgeben, wenn die Prozedur beendet wird.</span><span class="sxs-lookup"><span data-stu-id="309d2-106">If you specify the OUTPUT keyword for a parameter in the procedure definition, the procedure can return the current value of the parameter to the calling program when the procedure exits.</span></span> <span data-ttu-id="309d2-107">Um den Wert des Parameters in einer Variablen zu speichern, die in dem aufrufenden Programm verwendet werden kann, muss das aufrufende Programm beim Ausführen der Prozedur das Schlüsselwort OUTPUT verwenden.</span><span class="sxs-lookup"><span data-stu-id="309d2-107">To save the value of the parameter in a variable that can be used in the calling program, the calling program must use the OUTPUT keyword when executing the procedure.</span></span> <span data-ttu-id="309d2-108">Weitere Informationen dazu, welche Datentypen als Ausgabeparameter verwendet werden können, finden Sie unter [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="309d2-108">For more information about what data types can be used as output parameters, see [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span></span>  
  
### <a name="examples-of-output-parameter"></a><span data-ttu-id="309d2-109">Beispiele für Ausgabeparameter</span><span class="sxs-lookup"><span data-stu-id="309d2-109">Examples of Output Parameter</span></span>  
 <span data-ttu-id="309d2-110">Das folgende Beispiel zeigt eine Prozedur mit einem Eingabe- und einem Ausgabeparameter.</span><span class="sxs-lookup"><span data-stu-id="309d2-110">The following example shows a procedure with an input and an output parameter.</span></span> <span data-ttu-id="309d2-111">Der `@SalesPerson` -Parameter würde einen vom aufrufenden Programm angegebenen Eingabewert empfangen.</span><span class="sxs-lookup"><span data-stu-id="309d2-111">The `@SalesPerson` parameter would receive an input value specified by the calling program.</span></span> <span data-ttu-id="309d2-112">Die SELECT-Anweisung verwendet den im Eingabeparameter übergebenen Wert, um den richtigen `SalesYTD` -Wert abzurufen.</span><span class="sxs-lookup"><span data-stu-id="309d2-112">The SELECT statement uses the value passed into the input parameter to obtain the correct `SalesYTD` value.</span></span> <span data-ttu-id="309d2-113">Die SELECT-Anweisung weist den Wert auch dem `@SalesYTD` -Ausgabeparameter zu, der den Wert an das aufrufende Programm zurückgibt, wenn die Prozedur beendet wird.</span><span class="sxs-lookup"><span data-stu-id="309d2-113">The SELECT statement also assigns the value to the `@SalesYTD` output parameter, which returns the value to the calling program when the procedure exits.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID('Sales.uspGetEmployeeSalesYTD', 'P') IS NOT NULL  
    DROP PROCEDURE Sales.uspGetEmployeeSalesYTD;  
GO  
CREATE PROCEDURE Sales.uspGetEmployeeSalesYTD  
@SalesPerson nvarchar(50),  
@SalesYTD money OUTPUT  
AS    
  
    SET NOCOUNT ON;  
    SELECT @SalesYTD = SalesYTD  
    FROM Sales.SalesPerson AS sp  
    JOIN HumanResources.vEmployee AS e ON e.BusinessEntityID = sp.BusinessEntityID  
    WHERE LastName = @SalesPerson;  
RETURN  
GO  
  
```  
  
 <span data-ttu-id="309d2-114">Im folgenden Beispiel wird die im ersten Beispiel erstellte Prozedur aufgerufen und der Ausgabewert gespeichert, der von der aufgerufenen Prozedur in der `@SalesYTD` -Variablen, die eine lokale Variable des aufrufenden Programm ist, zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="309d2-114">The following example calls the procedure created in the first example and saves the output value returned from the called procedure in the `@SalesYTD` variable, which is local to the calling program.</span></span>  
  
```  
-- Declare the variable to receive the output value of the procedure.  
DECLARE @SalesYTDBySalesPerson money;  
-- Execute the procedure specifying a last name for the input parameter  
-- and saving the output value in the variable @SalesYTDBySalesPerson  
EXECUTE Sales.uspGetEmployeeSalesYTD  
    N'Blythe', @SalesYTD = @SalesYTDBySalesPerson OUTPUT;  
-- Display the value returned by the procedure.  
PRINT 'Year-to-date sales for this employee is ' +   
    convert(varchar(10),@SalesYTDBySalesPerson);  
GO  
  
```  
  
 <span data-ttu-id="309d2-115">Eingabewerte können auch als Ausgabeparameter angegeben werden, wenn die Prozedur ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="309d2-115">Input values can also be specified for OUTPUT parameters when the procedure is executed.</span></span> <span data-ttu-id="309d2-116">Auf diese Weise kann die Prozedur einen Wert von dem aufrufenden Programm erhalten, diesen Wert ändern oder andere Operationen mit dem Wert ausführen und den neuen Wert anschließend an das aufrufende Programm zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="309d2-116">This allows the procedure to receive a value from the calling program, change or perform operations with the value, and then return the new value to the calling program.</span></span> <span data-ttu-id="309d2-117">In dem zuvor aufgeführten Beispiel kann der `@SalesYTDBySalesPerson` -Variablen ein Wert zugewiesen werden, bevor das Programm die `Sales.uspGetEmployeeSalesYTD` -Prozedur aufruft.</span><span class="sxs-lookup"><span data-stu-id="309d2-117">In the previous example, the `@SalesYTDBySalesPerson` variable can be assigned a value before the program calls the `Sales.uspGetEmployeeSalesYTD` procedure.</span></span> <span data-ttu-id="309d2-118">Das EXECUTE-Anweisung übergibt in diesem Fall den `@SalesYTDBySalesPerson` -Variablenwert an den OUTPUT-Parameter `@SalesYTD` .</span><span class="sxs-lookup"><span data-stu-id="309d2-118">The execute statement would pass the `@SalesYTDBySalesPerson` variable value into the `@SalesYTD` OUTPUT parameter.</span></span> <span data-ttu-id="309d2-119">Im Prozedurtext kann der Wert zu Berechnungen verwendet werden, die einen neuen Wert generieren.</span><span class="sxs-lookup"><span data-stu-id="309d2-119">Then in the procedure body, the value could be used for calculations that generate a new value.</span></span> <span data-ttu-id="309d2-120">Der neue Wert wird über den OUTPUT-Parameter aus der Prozedur heraus weitergereicht, wobei der Wert in der `@SalesYTDBySalesPerson` -Variablen aktualisiert wird, wenn die Prozedur beendet wird.</span><span class="sxs-lookup"><span data-stu-id="309d2-120">The new value would be passed back out of the procedure through the OUTPUT parameter, updating the value in the `@SalesYTDBySalesPerson` variable when the procedure exits.</span></span> <span data-ttu-id="309d2-121">Dies wird häufig als "Fähigkeit zur Verweisübergabe" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="309d2-121">This is often referred to as "pass-by-reference capability."</span></span>  
  
 <span data-ttu-id="309d2-122">Wenn beim Aufruf einer Prozedur OUTPUT für einen Parameter angegeben wird und dieser Parameter in der Prozedurdefinition nicht mithilfe von OUTPUT definiert worden ist, dann wird eine Fehlermeldung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="309d2-122">If you specify OUTPUT for a parameter when you call a procedure and that parameter is not defined by using OUTPUT in the procedure definition, you get an error message.</span></span> <span data-ttu-id="309d2-123">Sie können eine Prozedur mit Ausgabeparameter ausführen, ohne OUTPUT beim Ausführen der Prozedur anzugeben.</span><span class="sxs-lookup"><span data-stu-id="309d2-123">However, you can execute a procedure with output parameters and not specify OUTPUT when executing the procedure.</span></span> <span data-ttu-id="309d2-124">In diesem Fall wird kein Fehler zurückgegeben; der Ausgabewert kann jedoch nicht in dem aufrufenden Programm verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="309d2-124">No error is returned, but you cannot use the output value in the calling program.</span></span>  
  
### <a name="using-the-cursor-data-type-in-output-parameters"></a><span data-ttu-id="309d2-125">Verwenden des Cursor-Datentyps in OUTPUT-Parametern</span><span class="sxs-lookup"><span data-stu-id="309d2-125">Using the Cursor Data Type in OUTPUT Parameters</span></span>  
 [!INCLUDE[tsql](../../../includes/tsql-md.md)]<span data-ttu-id="309d2-126">Prozeduren können den- `cursor` Datentyp nur für Ausgabeparameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="309d2-126">procedures can use the `cursor` data type only for OUTPUT parameters.</span></span> <span data-ttu-id="309d2-127">Wenn der `cursor` Datentyp für einen Parameter angegeben wird, müssen für diesen Parameter in der Prozedur Definition sowohl das variierende Schlüsselwort als auch das OUTPUT-Schlüsselwort angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="309d2-127">If the `cursor` data type is specified for a parameter, both the VARYING and OUTPUT keywords must be specified for that parameter in the procedure definition.</span></span> <span data-ttu-id="309d2-128">Ein Parameter kann nur als Ausgabe angegeben werden, aber wenn das Variation-Schlüsselwort in der Parameter Deklaration angegeben ist, muss der Datentyp lauten, `cursor` und das OUTPUT-Schlüsselwort muss ebenfalls angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="309d2-128">A parameter can be specified as only OUTPUT but if the VARYING keyword is specified in the parameter declaration, the data type must be `cursor` and the OUTPUT keyword must also be specified.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="309d2-129">Der `cursor`-Datentyp kann nicht durch Datenbank-APIs, wie z. B. OLE DB, ODBC, ADO und DB-Library, an Anwendungsvariablen gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="309d2-129">The `cursor` data type cannot be bound to application variables through the database APIs such as OLE DB, ODBC, ADO, and DB-Library.</span></span> <span data-ttu-id="309d2-130">Da OUTPUT-Parameter gebunden werden müssen, bevor eine Anwendung eine Prozedur ausführen kann, können Prozeduren mit `cursor`-OUTPUT-Parametern nicht aus den Datenbank-APIs heraus aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="309d2-130">Because OUTPUT parameters must be bound before an application can execute a procedure, procedures with `cursor` OUTPUT parameters cannot be called from the database APIs.</span></span> <span data-ttu-id="309d2-131">Diese Prozeduren können von [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Batches, Prozeduren oder Triggern heraus aufgerufen werden, wenn die `cursor`-OUTPUT-Variable einer lokalen [!INCLUDE[tsql](../../../includes/tsql-md.md)]-`cursor`-Variablen zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="309d2-131">These procedures can be called from [!INCLUDE[tsql](../../../includes/tsql-md.md)] batches, procedures, or triggers only when the `cursor` OUTPUT variable is assigned to a [!INCLUDE[tsql](../../../includes/tsql-md.md)] local `cursor` variable.</span></span>  
  
### <a name="rules-for-cursor-output-parameters"></a><span data-ttu-id="309d2-132">Regeln für Cursorausgabeparameter</span><span class="sxs-lookup"><span data-stu-id="309d2-132">Rules for Cursor Output Parameters</span></span>  
 <span data-ttu-id="309d2-133">Folgende Regeln gelten für Ausgabeparameter vom `cursor`-Datentyp, wenn die Prozedur ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="309d2-133">The following rules pertain to `cursor` output parameters when the procedure is executed:</span></span>  
  
-   <span data-ttu-id="309d2-134">Bei einem Vorwärtscursor werden im Resultset des Cursors nur die Zeilen zurückgegeben, die sich am Ende der Ausführung der Prozedur an und hinter der Cursorposition befinden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="309d2-134">For a forward-only cursor, the rows returned in the cursor's result set are only those rows at and beyond the position of the cursor at the conclusion of the procedure execution, for example:</span></span>  
  
    -   <span data-ttu-id="309d2-135">Ein nicht bildlauffähiger Cursor wird in einer Prozedur für ein Resultset namens RS geöffnet, das 100 Zeilen umfasst.</span><span class="sxs-lookup"><span data-stu-id="309d2-135">A nonscrollable cursor is opened in a procedure on a result set named RS of 100 rows.</span></span>  
  
    -   <span data-ttu-id="309d2-136">Die Prozedur ruft die ersten 5 Zeilen des Resultsets RS ab.</span><span class="sxs-lookup"><span data-stu-id="309d2-136">The procedure fetches the first 5 rows of result set RS.</span></span>  
  
    -   <span data-ttu-id="309d2-137">Die Prozedur gibt das Resultset an den Aufrufer zurück.</span><span class="sxs-lookup"><span data-stu-id="309d2-137">The procedure returns to its caller.</span></span>  
  
    -   <span data-ttu-id="309d2-138">Das Resultset RS, das an den Aufrufer zurückgegeben wird, besteht aus den Zeilen 6 bis 100 von RS, und der Cursor im Aufrufer wird vor der ersten Zeile von RS positioniert.</span><span class="sxs-lookup"><span data-stu-id="309d2-138">The result set RS returned to the caller consists of rows from 6 through 100 of RS, and the cursor in the caller is positioned before the first row of RS.</span></span>  
  
-   <span data-ttu-id="309d2-139">Wenn ein Vorwärtscursor beim Beenden der Prozedur vor der ersten Zeile positioniert ist, wird das gesamte Resultset an den aufrufenden Batch, die aufrufende Prozedur oder den aufrufenden Trigger zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="309d2-139">For a forward-only cursor, if the cursor is positioned before the first row when the procedure exits, the entire result set is returned to the calling batch, procedure, or trigger.</span></span> <span data-ttu-id="309d2-140">Nach der Rückgabe wird der Cursor vor der ersten Zeile positioniert.</span><span class="sxs-lookup"><span data-stu-id="309d2-140">When returned, the cursor position is set before the first row.</span></span>  
  
-   <span data-ttu-id="309d2-141">Wenn ein Vorwärtscursor beim Beenden der Prozedur hinter dem Ende der letzten Zeile positioniert ist, wird ein leeres Resultset an den aufrufenden Batch, die aufrufende Prozedur oder den aufrufenden Trigger zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="309d2-141">For a forward-only cursor, if the cursor is positioned beyond the end of the last row when the procedure exits, an empty result set is returned to the calling batch, procedure, or trigger.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="309d2-142">Ein leeres Resultset ist nicht das Gleiche wie ein NULL-Wert.</span><span class="sxs-lookup"><span data-stu-id="309d2-142">An empty result set is not the same as a null value.</span></span>  
  
-   <span data-ttu-id="309d2-143">Bei einem bildlauffähigen Cursor werden beim Beenden der Prozedur alle Zeilen im Resultset an den aufrufenden Batch, die aufrufende gespeicherte Prozedur oder den aufrufenden Trigger zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="309d2-143">For a scrollable cursor, all the rows in the result set are returned to the calling batch, procedure, or trigger when the procedure exits.</span></span> <span data-ttu-id="309d2-144">Nach der Rückgabe behält der Cursor die Position des letzten in der Prozedur ausgeführten Abrufs bei.</span><span class="sxs-lookup"><span data-stu-id="309d2-144">When returned, the cursor position is left at the position of the last fetch executed in the procedure.</span></span>  
  
-   <span data-ttu-id="309d2-145">Bei allen Cursortypen wird ein NULL-Wert an den aufrufenden Batch, die aufrufende Prozedur oder den aufrufenden Trigger zurückgegeben, wenn der Cursor geschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="309d2-145">For any type of cursor, if the cursor is closed, then a null value is passed back to the calling batch, procedure, or trigger.</span></span> <span data-ttu-id="309d2-146">Dies ist auch dann der Fall, wenn ein Cursor einem Parameter zugewiesen ist, dieser Cursor jedoch nie geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="309d2-146">This will also be the case if a cursor is assigned to a parameter, but that cursor is never opened.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="309d2-147">Der geschlossene Status ist nur zum Zeitpunkt der Rückgabe relevant.</span><span class="sxs-lookup"><span data-stu-id="309d2-147">The closed state matters only at return time.</span></span> <span data-ttu-id="309d2-148">Beispielsweise ist es zulässig, einen Cursor während eines Teils der Prozedur zu schließen, ihn zu einem späteren Zeitpunkt in der Prozedur wieder zu öffnen und das Resultset dieses Cursors an den aufrufenden Batch, die aufrufende Prozedur oder den aufrufenden Trigger zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="309d2-148">For example, it is valid to close a cursor part of the way through the procedure, to open it again later in the procedure, and return that cursor's result set to the calling batch, procedure, or trigger.</span></span>  
  
### <a name="examples-of-cursor-output-parameters"></a><span data-ttu-id="309d2-149">Beispiele für Cursorausgabeparameter</span><span class="sxs-lookup"><span data-stu-id="309d2-149">Examples of Cursor Output Parameters</span></span>  
 <span data-ttu-id="309d2-150">Im folgenden Beispiel wird eine Prozedur erstellt, die einen Output-Parameter `@currency` `cursor` mit dem- `cursor` Datentyp definiert.</span><span class="sxs-lookup"><span data-stu-id="309d2-150">In the following example, a procedure is created that specified an output parameter, `@currency`_`cursor` using the `cursor` data type.</span></span> <span data-ttu-id="309d2-151">Die Prozedur wird anschließend in einem Batch aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="309d2-151">The procedure is then called in a batch.</span></span>  
  
 <span data-ttu-id="309d2-152">Zuerst wird die Prozedur erstellt, die einen Cursor für die Currency-Tabelle deklariert und dann öffnet.</span><span class="sxs-lookup"><span data-stu-id="309d2-152">First, create the procedure that declares and then opens a cursor on the Currency table.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'dbo.uspCurrencyCursor', 'P' ) IS NOT NULL  
    DROP PROCEDURE dbo.uspCurrencyCursor;  
GO  
CREATE PROCEDURE dbo.uspCurrencyCursor   
    @CurrencyCursor CURSOR VARYING OUTPUT  
AS  
    SET NOCOUNT ON;  
    SET @CurrencyCursor = CURSOR  
    FORWARD_ONLY STATIC FOR  
      SELECT CurrencyCode, Name  
      FROM Sales.Currency;  
    OPEN @CurrencyCursor;  
GO  
  
```  
  
 <span data-ttu-id="309d2-153">Als Nächstes wird ein Batch ausgeführt, der eine lokale Cursorvariable deklariert, die Prozedur ausführt, um der lokalen Variablen den Cursor zuzuweisen, und dann die Zeilen aus dem Cursor abruft.</span><span class="sxs-lookup"><span data-stu-id="309d2-153">Next, execute a batch that declares a local cursor variable, executes the procedure to assign the cursor to the local variable, and then fetches the rows from the cursor.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @MyCursor CURSOR;  
EXEC dbo.uspCurrencyCursor @CurrencyCursor = @MyCursor OUTPUT;  
WHILE (@@FETCH_STATUS = 0)  
BEGIN;  
     FETCH NEXT FROM @MyCursor;  
END;  
CLOSE @MyCursor;  
DEALLOCATE @MyCursor;  
GO  
  
```  
  
## <a name="returning-data-using-a-return-code"></a><span data-ttu-id="309d2-154">Zurückgeben von Daten mithilfe eines Rückgabecodes</span><span class="sxs-lookup"><span data-stu-id="309d2-154">Returning Data Using a Return Code</span></span>  
 <span data-ttu-id="309d2-155">Eine Prozedur kann einen ganzzahligen Wert zurückgeben, der als Rückgabecode bezeichnet wird, um den Ausführungsstatus einer Prozedur anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="309d2-155">A procedure can return an integer value called a return code to indicate the execution status of a procedure.</span></span> <span data-ttu-id="309d2-156">Sie geben den Rückgabecode für eine Prozedur mithilfe der RETURN-Anweisung an.</span><span class="sxs-lookup"><span data-stu-id="309d2-156">You specify the return code for a procedure using the RETURN statement.</span></span> <span data-ttu-id="309d2-157">Wie schon die OUTPUT-Parameter müssen Sie auch den Rückgabecode in einer Variablen speichern, wenn die Prozedur ausgeführt wird, damit der Wert des Rückgabecodes in dem aufrufenden Programm verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="309d2-157">As with OUTPUT parameters, you must save the return code in a variable when the procedure is executed in order to use the return code value in the calling program.</span></span> <span data-ttu-id="309d2-158">Beispielsweise wird die Zuweisungs Variable `@result` des-Datentyps `int` verwendet, um den Rückgabecode der Prozedur zu speichern, z. b. `my_proc` :</span><span class="sxs-lookup"><span data-stu-id="309d2-158">For example, the assignment variable `@result` of data type `int` is used to store the return code from the procedure `my_proc`, such as:</span></span>  
  
```  
DECLARE @result int;  
EXECUTE @result = my_proc;  
```  
  
 <span data-ttu-id="309d2-159">Rückgabecodes werden häufig in Blöcken zur Ablaufsteuerung innerhalb von Prozeduren verwendet, um den Wert des Rückgabecodes für sämtliche Fehler festzulegen.</span><span class="sxs-lookup"><span data-stu-id="309d2-159">Return codes are commonly used in control-of-flow blocks within procedures to set the return code value for each possible error situation.</span></span> <span data-ttu-id="309d2-160">Sie können die @@ERROR-Funktion nach einer [!INCLUDE[tsql](../../../includes/tsql-md.md)] -Anweisung verwenden, um festzustellen, ob während der Ausführung der Anweisung ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="309d2-160">You can use the @@ERROR function after a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement to detect whether an error occurred during the execution of the statement.</span></span>  
  
### <a name="examples-of-return-codes"></a><span data-ttu-id="309d2-161">Beispiele für Rückgabecodes</span><span class="sxs-lookup"><span data-stu-id="309d2-161">Examples of Return Codes</span></span>  
 <span data-ttu-id="309d2-162">Das folgende Beispiel zeigt die `usp_GetSalesYTD` -Prozedur mit Fehlerbehandlung, in der für verschiedene Fehler spezielle Rückgabecodewerte festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="309d2-162">The following example shows the `usp_GetSalesYTD` procedure with error handling that sets special return code values for various errors.</span></span> <span data-ttu-id="309d2-163">In der Tabelle werden die ganzzahligen Werte aufgeführt, die die Prozedur den einzelnen möglichen Fehlern zuweist, sowie die Bedeutung der einzelnen Werte.</span><span class="sxs-lookup"><span data-stu-id="309d2-163">The following table shows the integer value that is assigned by the procedure to each possible error, and the corresponding meaning for each value.</span></span>  
  
|<span data-ttu-id="309d2-164">Rückgabecodewert</span><span class="sxs-lookup"><span data-stu-id="309d2-164">Return code value</span></span>|<span data-ttu-id="309d2-165">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="309d2-165">Meaning</span></span>|  
|-----------------------|-------------|  
|<span data-ttu-id="309d2-166">0</span><span class="sxs-lookup"><span data-stu-id="309d2-166">0</span></span>|<span data-ttu-id="309d2-167">Erfolgreiche Ausführung</span><span class="sxs-lookup"><span data-stu-id="309d2-167">Successful execution.</span></span>|  
|<span data-ttu-id="309d2-168">1</span><span class="sxs-lookup"><span data-stu-id="309d2-168">1</span></span>|<span data-ttu-id="309d2-169">Der erforderliche Parameterwert ist nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="309d2-169">Required parameter value is not specified.</span></span>|  
|<span data-ttu-id="309d2-170">2</span><span class="sxs-lookup"><span data-stu-id="309d2-170">2</span></span>|<span data-ttu-id="309d2-171">Der angegebene Parameterwert ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="309d2-171">Specified parameter value is not valid.</span></span>|  
|<span data-ttu-id="309d2-172">3</span><span class="sxs-lookup"><span data-stu-id="309d2-172">3</span></span>|<span data-ttu-id="309d2-173">Beim Abrufen der Vertriebswerte ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="309d2-173">Error has occurred getting sales value.</span></span>|  
|<span data-ttu-id="309d2-174">4</span><span class="sxs-lookup"><span data-stu-id="309d2-174">4</span></span>|<span data-ttu-id="309d2-175">Für diesen Vertriebsmitarbeiter wurde ein Vertriebswert von NULL gefunden.</span><span class="sxs-lookup"><span data-stu-id="309d2-175">NULL sales value found for the salesperson.</span></span>|  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID('Sales.usp_GetSalesYTD', 'P') IS NOT NULL  
    DROP PROCEDURE Sales.usp_GetSalesYTD;  
GO  
CREATE PROCEDURE Sales.usp_GetSalesYTD  
@SalesPerson nvarchar(50) = NULL,  -- NULL default value  
@SalesYTD money = NULL OUTPUT  
AS    
  
-- Validate the @SalesPerson parameter.  
IF @SalesPerson IS NULL  
   BEGIN  
       PRINT 'ERROR: You must specify a last name for the sales person.'  
       RETURN(1)  
   END  
ELSE  
   BEGIN  
   -- Make sure the value is valid.  
   IF (SELECT COUNT(*) FROM HumanResources.vEmployee  
          WHERE LastName = @SalesPerson) = 0  
      RETURN(2)  
   END  
-- Get the sales for the specified name and   
-- assign it to the output parameter.  
SELECT @SalesYTD = SalesYTD   
FROM Sales.SalesPerson AS sp  
JOIN HumanResources.vEmployee AS e ON e.BusinessEntityID = sp.BusinessEntityID  
WHERE LastName = @SalesPerson;  
-- Check for SQL Server errors.  
IF @@ERROR <> 0   
   BEGIN  
      RETURN(3)  
   END  
ELSE  
   BEGIN  
   -- Check to see if the ytd_sales value is NULL.  
     IF @SalesYTD IS NULL  
       RETURN(4)   
     ELSE  
      -- SUCCESS!!  
        RETURN(0)  
   END  
-- Run the stored procedure without specifying an input value.  
EXEC Sales.usp_GetSalesYTD;  
GO  
-- Run the stored procedure with an input value.  
DECLARE @SalesYTDForSalesPerson money, @ret_code int;  
-- Execute the procedure specifying a last name for the input parameter  
-- and saving the output value in the variable @SalesYTD  
EXECUTE Sales.usp_GetSalesYTD  
    N'Blythe', @SalesYTD = @SalesYTDForSalesPerson OUTPUT;  
PRINT N'Year-to-date sales for this employee is ' +  
    CONVERT(varchar(10), @SalesYTDForSalesPerson);  
  
```  
  
 <span data-ttu-id="309d2-176">Im folgenden Beispiel wird ein Programm erstellt, das die von der `usp_GetSalesYTD` -Prozedur zurückgegebenen Rückgabecodes verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="309d2-176">The following example creates a program to handle the return codes that are returned from the `usp_GetSalesYTD` procedure.</span></span>  
  
```  
-- Declare the variables to receive the output value and return code   
-- of the procedure.  
DECLARE @SalesYTDForSalesPerson money, @ret_code int;  
  
-- Execute the procedure with a title_id value  
-- and save the output value and return code in variables.  
EXECUTE @ret_code = Sales.usp_GetSalesYTD  
    N'Blythe', @SalesYTD = @SalesYTDForSalesPerson OUTPUT;  
--  Check the return codes.  
IF @ret_code = 0  
BEGIN  
   PRINT 'Procedure executed successfully'  
   -- Display the value returned by the procedure.  
   PRINT 'Year-to-date sales for this employee is ' + CONVERT(varchar(10),@SalesYTDForSalesPerson)  
END  
ELSE IF @ret_code = 1  
   PRINT 'ERROR: You must specify a last name for the sales person.'  
ELSE IF @ret_code = 2   
   PRINT 'EERROR: You must enter a valid last name for the sales person.'  
ELSE IF @ret_code = 3  
   PRINT 'ERROR: An error occurred getting sales value.'  
ELSE IF @ret_code = 4  
   PRINT 'ERROR: No sales recorded for this employee.'     
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="309d2-177">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="309d2-177">See Also</span></span>  
 <span data-ttu-id="309d2-178">[DEKLARIEREN SIE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="309d2-178">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="309d2-179">[PRINT &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/print-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="309d2-179">[PRINT &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/print-transact-sql) </span></span>  
 <span data-ttu-id="309d2-180">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="309d2-180">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="309d2-181">[Cursor](../cursors.md) </span><span class="sxs-lookup"><span data-stu-id="309d2-181">[Cursors](../cursors.md) </span></span>  
 <span data-ttu-id="309d2-182">[RETURN &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/return-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="309d2-182">[RETURN &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/return-transact-sql) </span></span>  
 [<span data-ttu-id="309d2-183">@@ERROR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="309d2-183">@@ERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/error-transact-sql)  
  
  
