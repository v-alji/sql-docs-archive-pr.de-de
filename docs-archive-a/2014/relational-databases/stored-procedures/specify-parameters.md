---
title: Angeben von Parameter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- parameters [SQL Server], stored procedures
- stored procedures [SQL Server], parameters
- output parameters [SQL Server]
- input parameters [SQL Server]
ms.assetid: 902314fe-5f9c-4d0d-a0b7-27e67c9c70ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: d93a04281839c4db26cbab16ac166af3cdb7c9a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630610"
---
# <a name="specify-parameters"></a><span data-ttu-id="cd285-102">Angeben von Parametern</span><span class="sxs-lookup"><span data-stu-id="cd285-102">Specify Parameters</span></span>
  <span data-ttu-id="cd285-103">Aufrufende Programme sind in der Lage, durch die Angabe von Prozedurparametern Werte in den Textkörper der Prozedur zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="cd285-103">By specifying procedure parameters, calling programs are able to pass values into the body of the procedure.</span></span> <span data-ttu-id="cd285-104">Jene Werte können während der Prozedurausführung zu einer Vielzahl von Zwecken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cd285-104">Those values can be used for a variety of purposes during procedure execution.</span></span> <span data-ttu-id="cd285-105">Prozedurparameter können auch Werte an das aufrufende Programm zurückgeben, wenn der Parameter als OUTPUT-Parameter markiert wird.</span><span class="sxs-lookup"><span data-stu-id="cd285-105">Procedure parameters can also return values to the calling program if the parameter is marked as an OUTPUT parameter.</span></span>  
  
 <span data-ttu-id="cd285-106">Eine Prozedur kann über maximal 2100 Parameter verfügen, denen jeweils ein Name, eine Datentyp und eine Richtung zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="cd285-106">A procedure can have a maximum of 2100 parameters; each assigned a name, data type, and direction.</span></span> <span data-ttu-id="cd285-107">Optional können Parametern Standardwerte zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="cd285-107">Optionally, parameters can be assigned default values.</span></span>  
  
 <span data-ttu-id="cd285-108">Der folgende Abschnitt enthält Informationen zur Übergabe von Werten in Parameter und zur Verwendung der verschiedenen Parameterattribute in einem Prozeduraufruf.</span><span class="sxs-lookup"><span data-stu-id="cd285-108">The following section provides information about passing values into parameters and about how each of the parameter attributes is used during a procedure call.</span></span>  
  
## <a name="passing-values-into-parameters"></a><span data-ttu-id="cd285-109">Übergeben von Werte in Parameter</span><span class="sxs-lookup"><span data-stu-id="cd285-109">Passing Values into Parameters</span></span>  
 <span data-ttu-id="cd285-110">Die mit einem Prozeduraufruf angegebenen Parameterwerte müssen Konstanten oder Variablen sein. Ein Funktionsname kann nicht als Parameterwert verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cd285-110">The parameter values supplied with a procedure call must be constants or a variable; a function name cannot be used as a parameter value.</span></span> <span data-ttu-id="cd285-111">Variablen können benutzerdefiniert oder Systemvariablen (z. B. \@\@spid) sein.</span><span class="sxs-lookup"><span data-stu-id="cd285-111">Variables can be user-defined or system variables such as \@\@spid.</span></span>  
  
 <span data-ttu-id="cd285-112">Die folgenden Beispiele zeigen, wie Parameterwerte an die Prozedur `uspGetWhereUsedProductID`übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="cd285-112">The following examples demonstrate passing parameter values to the procedure `uspGetWhereUsedProductID`.</span></span> <span data-ttu-id="cd285-113">Sie zeigen, wie Parameter als Konstanten und Variablen übergeben werden, sowie die Verwendung einer Variablen, um den Wert einer Funktion zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="cd285-113">They illustrate how to pass parameters as constants and variables and also how to use a variable to pass the value of a function.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
-- Passing values as constants.  
EXEC dbo.uspGetWhereUsedProductID 819, '20050225';  
GO  
-- Passing values as variables.  
DECLARE @ProductID int, @CheckDate datetime;  
SET @ProductID = 819;  
SET @CheckDate = '20050225';  
EXEC dbo.uspGetWhereUsedProductID @ProductID, @CheckDate;  
GO  
-- Try to use a function as a parameter value.  
-- This produces an error message.  
EXEC dbo.uspGetWhereUsedProductID 819, GETDATE();  
GO  
-- Passing the function value as a variable.  
DECLARE @CheckDate datetime;  
SET @CheckDate = GETDATE();  
EXEC dbo.uspGetWhereUsedProductID 819, @CheckDate;  
GO  
```  
  
## <a name="specifying-parameter-names"></a><span data-ttu-id="cd285-114">Angeben von Parameternamen</span><span class="sxs-lookup"><span data-stu-id="cd285-114">Specifying Parameter Names</span></span>  
 <span data-ttu-id="cd285-115">Wenn eine Prozedur erstellt und ein Parameternamen deklariert wird, muss ein Parametername gewählt werden, der mit einem einzelnen \@-Zeichen beginnt und im Bereich der Prozedur eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="cd285-115">When creating a procedure and declaring a parameter name, the parameter name must begin with a single \@ character and must be unique in the scope of the procedure.</span></span>  
  
 <span data-ttu-id="cd285-116">Durch das explizite Benennen der Parameter und Zuweisen der entsprechenden Werte zu jedem Parameter in einem Prozeduraufruf ist es möglich, dass die Parameter in beliebiger Reihenfolge angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cd285-116">Explicitly naming the parameters and assigning the appropriate values to each parameter in a procedure call allows the parameters to be supplied in any order.</span></span> <span data-ttu-id="cd285-117">Wenn z. B. die Prozedur **my_proc** drei Parameter mit den Namen **\@first**, **\@second** und **\@third** erwartet, können die Werte, die an die Prozedur übergeben werden, den Parameternamen wie folgt zugewiesen werden: `EXECUTE my_proc @second = 2, @first = 1, @third = 3;`</span><span class="sxs-lookup"><span data-stu-id="cd285-117">For example, if the procedure **my_proc** expects three parameters named **\@first**, **\@second**, and **\@third**, the values passed to the procedure can be assigned to the parameter names, such as: `EXECUTE my_proc @second = 2, @first = 1, @third = 3;`</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd285-118">Wenn ein Parameterwert im Format **\@parameter =** _value_ angegeben wird, müssen auch alle nachfolgenden Parameter auf diese Weise angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cd285-118">If one parameter value is supplied in the form **\@parameter =**_value_, all subsequent parameters must be supplied in this manner.</span></span> <span data-ttu-id="cd285-119">Wenn die Parameterwerte nicht im Format **\@parameter =** _value_ übergeben werden, müssen die Werte in derselben Reihenfolge (von links nach rechts) angegeben werden, in der die Parameter in der CREATE PROCEDURE-Anweisung aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="cd285-119">If the parameter values are not passed in the form **\@parameter =**_value_, the values must be supplied in the identical order (left to right) as the parameters are listed in the CREATE PROCEDURE statement.</span></span>  
> 
> [!WARNING]
>  <span data-ttu-id="cd285-120">Jeder Parameter, der im Format **\@parameter =** _value_ übergeben und falsch geschrieben wird, bewirkt, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] einen Fehler generiert und die Prozedurausführung beendet.</span><span class="sxs-lookup"><span data-stu-id="cd285-120">Any parameter passed in the form **\@parameter =**_value_ with the parameter misspelled, will cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to generate an error and prevent procedure execution.</span></span>  
  
## <a name="specifying-parameter-data-types"></a><span data-ttu-id="cd285-121">Angeben von Parameterdatentypen</span><span class="sxs-lookup"><span data-stu-id="cd285-121">Specifying Parameter Data Types</span></span>  
 <span data-ttu-id="cd285-122">Parameter müssen mit einem Datentyp definiert werden, wann sie in einer CREATE PROCEDURE-Anweisung deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="cd285-122">Parameters must be defined with a data type when they are declared in a CREATE PROCEDURE statement.</span></span> <span data-ttu-id="cd285-123">Durch den Datentyp eines Parameters werden der Typ und der Wertebereich festgelegt, die beim Aufruf der Prozedur für den Parameter akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="cd285-123">The data type of a parameter determines the type and range of values that are accepted for the parameter when the procedure is called.</span></span> <span data-ttu-id="cd285-124">Wenn Sie z. B. einen Parameter mit dem `tinyint`-Datentyp definieren, werden nur numerische Werte im Bereich von 0 bis 255 als Werte für diesen Parameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="cd285-124">For example, if you define a parameter with a `tinyint` data type, only numeric values ranging from 0 to 255 are accepted when passed into that parameter.</span></span> <span data-ttu-id="cd285-125">Wenn eine Prozedur mit einem Wert ausgeführt wird, der nicht mit dem Datentyp kompatibel ist, wird ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cd285-125">An error is returned if a procedure is executed with a value incompatible with the data type.</span></span>  
  
## <a name="specifying-parameter-default-values"></a><span data-ttu-id="cd285-126">Angeben von Standardwerten für Parameter</span><span class="sxs-lookup"><span data-stu-id="cd285-126">Specifying Parameter Default Values</span></span>  
 <span data-ttu-id="cd285-127">Ein Parameter, für den in der Parameterdeklaration ein Standardwert angeben wird, wird als optional betrachtet.</span><span class="sxs-lookup"><span data-stu-id="cd285-127">A parameter is considered optional if the parameter has a default value specified when it is declared.</span></span> <span data-ttu-id="cd285-128">Es ist nicht notwendig, in einem Prozeduraufruf einen Wert für einen optionalen Parameter bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="cd285-128">It is not necessary to provide a value for an optional parameter in a procedure call.</span></span>  
  
 <span data-ttu-id="cd285-129">Der Standardwert eines Parameters wird verwendet, wenn:</span><span class="sxs-lookup"><span data-stu-id="cd285-129">The default value of a parameter is used when:</span></span>  
  
-   <span data-ttu-id="cd285-130">Für den Parameter im Prozeduraufruf kein Wert angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cd285-130">No value for the parameter is specified in the procedure call.</span></span>  
  
-   <span data-ttu-id="cd285-131">Das DEFAULT-Schlüsselwort im Prozeduraufruf als Wert für den Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cd285-131">The DEFAULT keyword is specified as the value in the procedure call.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd285-132">Wenn es sich bei dem Standardwert um eine Zeichenfolge handelt, die eingebettete Leerzeichen oder Satzzeichen enthält oder mit einer Zahl beginnt (z. B. 6xxx), muss der Wert in einfache, gerade Anführungszeichen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="cd285-132">If the default value is a character string that contains embedded blanks or punctuation, or if it starts with a number (for example, 6xxx), it must be enclosed in single, straight quotation marks.</span></span>  
  
 <span data-ttu-id="cd285-133">Wenn kein entsprechender Wert als Standardwert für den Parameter angegeben werden kann, geben Sie NULL als Standardwert an.</span><span class="sxs-lookup"><span data-stu-id="cd285-133">If no value can be specified appropriately as a default for the parameter, specify NULL as the default.</span></span> <span data-ttu-id="cd285-134">Es empfiehlt sich, die Prozedur eine benutzerdefinierte Meldung zurückgeben zu lassen, wenn sie ohne Wertangabe für den Parameter ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cd285-134">It is a good idea to have the procedure return a customized message if the procedure is executed without a value for the parameter.</span></span>  
  
 <span data-ttu-id="cd285-135">Im folgenden Beispiel wird die gespeicherte Prozedur `usp_GetSalesYTD` mit einem Eingabeparameter ( `@SalesPerson`) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cd285-135">The following example creates the `usp_GetSalesYTD` procedure with one input parameter, `@SalesPerson`.</span></span> <span data-ttu-id="cd285-136">NULL wird als Standardwert für den Parameter zugewiesen und in Fehlerbehandlungsanweisungen zum Zurückgeben einer benutzerdefinierten Fehlermeldung verwendet, wenn die Prozedur ohne einen Wert für den Parameter `@SalesPerson` ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cd285-136">NULL is assigned as the default value for the parameter and is used in error handling statements to return a custom error message for cases when the procedure is executed without a value for the `@SalesPerson` parameter.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID('Sales.uspGetSalesYTD', 'P') IS NOT NULL  
    DROP PROCEDURE Sales.uspGetSalesYTD;  
GO  
CREATE PROCEDURE Sales.uspGetSalesYTD  
@SalesPerson nvarchar(50) = NULL  -- NULL default value  
AS   
    SET NOCOUNT ON;   
  
-- Validate the @SalesPerson parameter.  
IF @SalesPerson IS NULL  
BEGIN  
   PRINT 'ERROR: You must specify the last name of the sales person.'  
   RETURN  
END  
-- Get the sales for the specified sales person and   
-- assign it to the output parameter.  
SELECT SalesYTD  
FROM Sales.SalesPerson AS sp  
JOIN HumanResources.vEmployee AS e ON e.BusinessEntityID = sp.BusinessEntityID  
WHERE LastName = @SalesPerson;  
RETURN  
GO  
  
```  
  
 <span data-ttu-id="cd285-137">Im folgenden Beispiel wird die Prozedur ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cd285-137">The following example executes the procedure.</span></span> <span data-ttu-id="cd285-138">Die erste Anweisung führt die Prozedur ohne Angabe eines Eingabewerts aus.</span><span class="sxs-lookup"><span data-stu-id="cd285-138">The first statement executes the procedure without specifying an input value.</span></span> <span data-ttu-id="cd285-139">Dies bewirkt, dass die Fehlerbehandlungsanweisungen in der Prozedur die benutzerdefinierte Fehlermeldung zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="cd285-139">This causes the error handling statements in the procedure to return the custom error message.</span></span> <span data-ttu-id="cd285-140">Die zweite Anweisung stellt einen Eingabewert zur Verfügung und gibt das erwartete Resultset zurück.</span><span class="sxs-lookup"><span data-stu-id="cd285-140">The second statement supplies an input value and returns the expected result set.</span></span>  
  
```  
-- Run the procedure without specifying an input value.  
EXEC Sales.usp_GetSalesYTD;  
GO  
-- Run the procedure with an input value.  
EXEC Sales.usp_GetSalesYTD N'Blythe';  
GO  
```  
  
 <span data-ttu-id="cd285-141">Sie können Parameter auslassen, für die Standardwerte angegeben wurden; dies ist jedoch nur durch Abschneiden der Parameterliste möglich.</span><span class="sxs-lookup"><span data-stu-id="cd285-141">Although parameters for which defaults have been supplied can be omitted, the list of parameters can only be truncated.</span></span> <span data-ttu-id="cd285-142">Wenn eine Prozedur z. B. über fünf Parameter verfügt, können sowohl der vierte als auch der fünfte Parameter weggelassen werden.</span><span class="sxs-lookup"><span data-stu-id="cd285-142">For example, if a procedure has five parameters, both the fourth and the fifth parameters can be omitted.</span></span> <span data-ttu-id="cd285-143">Der vierte Parameter kann jedoch nicht übersprungen werden, solange der fünfte Parameter eingeschlossen ist, außer wenn die Parameter im Format **\@parameter =** _value_ angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cd285-143">However the fourth parameter cannot be skipped as long as the fifth parameter is included, unless the parameters are supplied in the form **\@parameter =**_value_.</span></span>  
  
## <a name="specifying-parameter-direction"></a><span data-ttu-id="cd285-144">Angeben der Parameterrichtung</span><span class="sxs-lookup"><span data-stu-id="cd285-144">Specifying Parameter Direction</span></span>  
 <span data-ttu-id="cd285-145">Die Parameterrichtung ist entweder Eingabe, d. h. ein Wert wird in den Textkörper der Prozedur übergeben, oder Ausgabe, d. h. die Prozedur gibt einen Wert an das aufrufende Programm zurück.</span><span class="sxs-lookup"><span data-stu-id="cd285-145">The direction of a parameter is either input, a value is passed into the body of the procedure, or output, the procedure returns a value to the calling program.</span></span> <span data-ttu-id="cd285-146">Standardmäßig wird ein Eingabeparameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd285-146">The default is an input parameter.</span></span>  
  
 <span data-ttu-id="cd285-147">Um einen Ausgabeparameter anzugeben müssen Sie das OUTPUT-Schlüsselwort in der Definition des Parameters in der CREATE PROCEDURE-Anweisung angeben.</span><span class="sxs-lookup"><span data-stu-id="cd285-147">To specify an output parameter, the OUTPUT keyword must be specified in the definition of the parameter in the CREATE PROCEDURE statement.</span></span> <span data-ttu-id="cd285-148">Die Prozedur gibt den aktuellen Wert des Ausgabeparameters an das aufrufende Programm zurück, wenn die Prozedur beendet wird.</span><span class="sxs-lookup"><span data-stu-id="cd285-148">The procedure returns the current value of the output parameter to the calling program when the procedure exits.</span></span> <span data-ttu-id="cd285-149">Um den Wert des Parameters in einer Variablen zu speichern, die in dem aufrufenden Programm verwendet werden kann, muss das aufrufende Programm beim Ausführen der Prozedur ebenfalls das Schlüsselwort OUTPUT verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd285-149">The calling program must also use the OUTPUT keyword when executing the procedure to save the parameter's value in a variable that can be used in the calling program.</span></span>  
  
 <span data-ttu-id="cd285-150">Im nachfolgenden Beispiel wird die `Production.usp`_`GetList` -Prozedur erstellt, von der eine Liste der Produkte zurückgegeben wird, deren Preis einen angegebenen Betrag nicht übersteigt.</span><span class="sxs-lookup"><span data-stu-id="cd285-150">The following example creates the `Production.usp`_`GetList` procedure, which returns a list of products that have prices that do not exceed a specified amount.</span></span> <span data-ttu-id="cd285-151">In dem Beispiel wird die Verwendung mehrerer SELECT-Anweisungen und mehrerer OUTPUT-Parameter dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cd285-151">The example shows using multiple SELECT statements and multiple OUTPUT parameters.</span></span> <span data-ttu-id="cd285-152">OUTPUT-Parameter ermöglichen einer externen Prozedur, einem Batch oder mehreren [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen während dem Ausführen der Prozedur den Zugriff auf einen Satz von Werten.</span><span class="sxs-lookup"><span data-stu-id="cd285-152">OUTPUT parameters allow an external procedure, a batch, or more than one [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to access a value set during the procedure execution.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'Production.uspGetList', 'P' ) IS NOT NULL   
    DROP PROCEDURE Production.uspGetList;  
GO  
CREATE PROCEDURE Production.uspGetList @Product varchar(40)   
    , @MaxPrice money   
    , @ComparePrice money OUTPUT  
    , @ListPrice money OUT  
AS  
    SET NOCOUNT ON;  
    SELECT p.[Name] AS Product, p.ListPrice AS 'List Price'  
    FROM Production.Product AS p  
    JOIN Production.ProductSubcategory AS s   
      ON p.ProductSubcategoryID = s.ProductSubcategoryID  
    WHERE s.[Name] LIKE @Product AND p.ListPrice < @MaxPrice;  
-- Populate the output variable @ListPprice.  
SET @ListPrice = (SELECT MAX(p.ListPrice)  
        FROM Production.Product AS p  
        JOIN  Production.ProductSubcategory AS s   
          ON p.ProductSubcategoryID = s.ProductSubcategoryID  
        WHERE s.[Name] LIKE @Product AND p.ListPrice < @MaxPrice);  
-- Populate the output variable @compareprice.  
SET @ComparePrice = @MaxPrice;  
GO  
  
```  
  
 <span data-ttu-id="cd285-153">Führen Sie `usp_GetList` aus, um eine Liste der [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] -Produkte (Bikes) zurückzugeben, die weniger als 700 $ kosten.</span><span class="sxs-lookup"><span data-stu-id="cd285-153">Execute `usp_GetList` to return a list of [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] products (Bikes) that cost less than $700.</span></span> <span data-ttu-id="cd285-154">Die OUTPUT-Parameter **\@cost** und **\@compareprices** werden mit Sprachkonstrukten zur Ablaufsteuerung verwendet, um eine Meldung im Fenster **Meldungen** zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="cd285-154">The OUTPUT parameters **\@cost** and **\@compareprices** are used with control-of-flow language to return a message in the **Messages** window.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd285-155">Die OUTPUT-Variable muss sowohl beim Erstellen der Prozedur als auch beim Verwenden der Variable definiert werden.</span><span class="sxs-lookup"><span data-stu-id="cd285-155">The OUTPUT variable must be defined during the procedure creation and also during the use of the variable.</span></span> <span data-ttu-id="cd285-156">Parametername und Variablenname brauchen nicht übereinzustimmen.</span><span class="sxs-lookup"><span data-stu-id="cd285-156">The parameter name and variable name do not have to match.</span></span> <span data-ttu-id="cd285-157">Jedoch müssen der Datentyp und die Parameterpositionierung übereinstimmen, es sei denn **\@listprice=** _variable_ wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd285-157">However, the data type and parameter positioning must match (unless **\@listprice=** _variable_ is used).</span></span>  
  
```  
DECLARE @ComparePrice money, @Cost money ;  
EXECUTE Production.uspGetList '%Bikes%', 700,   
    @ComparePrice OUT,   
    @Cost OUTPUT  
IF @Cost <= @ComparePrice   
BEGIN  
    PRINT 'These products can be purchased for less than   
    $'+RTRIM(CAST(@ComparePrice AS varchar(20)))+'.'  
END  
ELSE  
    PRINT 'The prices for all products in this category exceed   
    $'+ RTRIM(CAST(@ComparePrice AS varchar(20)))+'.';  
  
```  
  
 <span data-ttu-id="cd285-158">Im Folgenden wird ein Teil des Resultsets aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="cd285-158">Here is the partial result set:</span></span>  
  
```  
Product                                            List Price  
-------------------------------------------------- ------------------  
Road-750 Black, 58                                 539.99  
Mountain-500 Silver, 40                            564.99  
Mountain-500 Silver, 42                            564.99  
...  
Road-750 Black, 48                                 539.99  
Road-750 Black, 52                                 539.99  
  
(14 row(s) affected)  
  
These items can be purchased for less than $700.00.  
```  
  
## <a name="see-also"></a><span data-ttu-id="cd285-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cd285-159">See Also</span></span>  
 [<span data-ttu-id="cd285-160">CREATE PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cd285-160">CREATE PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)  
  
  
