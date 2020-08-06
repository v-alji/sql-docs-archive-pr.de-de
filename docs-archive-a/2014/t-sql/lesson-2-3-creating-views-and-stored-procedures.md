---
title: Erstellen von Sichten und gespeicherten Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- creating views and stored procedures
ms.assetid: 53a0426d-07d8-4b7c-aa21-22632753bad8
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 76f6ecec446536191e8be4b05547ba5fd44c9d8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695090"
---
# <a name="creating-views-and-stored-procedures"></a><span data-ttu-id="95c56-102">Erstellen von Sichten und gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="95c56-102">Creating Views and Stored Procedures</span></span>
  <span data-ttu-id="95c56-103">Nachdem Mary nun auf die **TestData** -Datenbank zugreifen kann, möchten Sie möglicherweise einige Datenbankobjekte erstellen, wie z. B. eine Sicht und eine gespeicherte Prozedur, und Mary dann Zugriff auf diese Objekte erteilen.</span><span class="sxs-lookup"><span data-stu-id="95c56-103">Now that Mary can access the **TestData** database, you may want to create some database objects, such as a view and a stored procedure, and then grant Mary access to them.</span></span> <span data-ttu-id="95c56-104">Bei einer Sicht handelt es sich um eine gespeicherte SELECT-Anweisung, und eine gespeicherte Prozedur setzt sich aus einer oder mehreren [!INCLUDE[tsql](../includes/tsql-md.md)] -Anweisungen zusammen, die als Batch ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="95c56-104">A view is a stored SELECT statement, and a stored procedure is one or more [!INCLUDE[tsql](../includes/tsql-md.md)] statements that execute as a batch.</span></span>  
  
 <span data-ttu-id="95c56-105">Sichten werden wie Tabellen abgefragt und nehmen keine Parameter an.</span><span class="sxs-lookup"><span data-stu-id="95c56-105">Views are queried like tables and do not accept parameters.</span></span> <span data-ttu-id="95c56-106">Gespeicherte Prozeduren sind komplexer als Sichten.</span><span class="sxs-lookup"><span data-stu-id="95c56-106">Stored procedures are more complex than views.</span></span> <span data-ttu-id="95c56-107">Gespeicherte Prozeduren können sowohl Eingabe- als auch Ausgabeparameter aufweisen und Anweisungen enthalten, die den Ablauf des Codes steuern, wie z. B. IF- und WHILE-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="95c56-107">Stored procedures can have both input and output parameters and can contain statements to control the flow of the code, such as IF and WHILE statements.</span></span> <span data-ttu-id="95c56-108">Als eine der Grundregeln guter Programmierung gilt die Verwendung gespeicherter Prozeduren für alle Aktionen, die sich in der Datenbank wiederholen.</span><span class="sxs-lookup"><span data-stu-id="95c56-108">It is good programming practice to use stored procedures for all repetitive actions in the database.</span></span>  
  
 <span data-ttu-id="95c56-109">In diesem Beispiel erstellen Sie mithilfe von CREATE VIEW eine Sicht, die nur zwei der Spalten in der **Products** -Tabelle auswählt.</span><span class="sxs-lookup"><span data-stu-id="95c56-109">For this example, you will use CREATE VIEW to create a view that selects only two of the columns in the **Products** table.</span></span> <span data-ttu-id="95c56-110">Sie erstellen dann mithilfe von CREATE PROCEDURE eine gespeicherte Prozedur, die einen Parameter für den Preis akzeptiert und nur die Produkte zurückgibt, deren Preis unter dem angegebenen Parameterwert liegt.</span><span class="sxs-lookup"><span data-stu-id="95c56-110">Then, you will use CREATE PROCEDURE to create a stored procedure that accepts a price parameter and returns only those products that cost less than the specified parameter value.</span></span>  
  
### <a name="to-create-a-view"></a><span data-ttu-id="95c56-111">So erstellen Sie eine Sicht</span><span class="sxs-lookup"><span data-stu-id="95c56-111">To create a view</span></span>  
  
1.  <span data-ttu-id="95c56-112">Führen Sie die folgende Anweisung aus, um eine sehr einfache Sicht zu erstellen, die eine SELECT-Anweisung ausführt und die Namen und Preise der Produkte an den Benutzer zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="95c56-112">Execute the following statement to create a very simple view that executes a select statement, and returns the names and prices of our products to the user.</span></span>  
  
    ```  
    CREATE VIEW vw_Names  
       AS  
       SELECT ProductName, Price FROM Products;  
    GO  
  
    ```  
  
### <a name="test-the-view"></a><span data-ttu-id="95c56-113">Testen der Sicht</span><span class="sxs-lookup"><span data-stu-id="95c56-113">Test the view</span></span>  
  
1.  <span data-ttu-id="95c56-114">Sichten werden genau wie Tabellen behandelt.</span><span class="sxs-lookup"><span data-stu-id="95c56-114">Views are treated just like tables.</span></span> <span data-ttu-id="95c56-115">Greifen Sie mithilfe einer `SELECT` -Anweisung auf eine Sicht zu.</span><span class="sxs-lookup"><span data-stu-id="95c56-115">Use a `SELECT` statement to access a view.</span></span>  
  
    ```  
    SELECT * FROM vw_Names;  
    GO  
  
    ```  
  
### <a name="to-create-a-stored-procedure"></a><span data-ttu-id="95c56-116">So erstellen Sie eine gespeicherte Prozedur</span><span class="sxs-lookup"><span data-stu-id="95c56-116">To create a stored procedure</span></span>  
  
1.  <span data-ttu-id="95c56-117">Die folgende Anweisung erstellt eine gespeicherte Prozedur namens `pr_Names`, die einen Eingabeparameter mit der Bezeichnung `@VarPrice` vom Datentyp `money`akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="95c56-117">The following statement creates a stored procedure name `pr_Names`, accepts an input parameter named `@VarPrice` of data type `money`.</span></span> <span data-ttu-id="95c56-118">Die gespeicherte Prozedur druckt die mit dem Eingabeparameter verkettete `Products less than` -Anweisung. Dieser Parameter wird vom `money` -Datentyp in den `varchar(10)` -Zeichendatentyp geändert.</span><span class="sxs-lookup"><span data-stu-id="95c56-118">The stored procedure prints the statement `Products less than` concatenated with the input parameter that is changed from the `money` data type into a `varchar(10)` character data type.</span></span> <span data-ttu-id="95c56-119">Dann führt die Prozedur eine `SELECT` -Anweisung für die Sicht aus und übergibt dabei den Eingabeparameter als Teil der `WHERE` -Klausel.</span><span class="sxs-lookup"><span data-stu-id="95c56-119">Then, the procedure executes a `SELECT` statement on the view, passing the input parameter as part of the `WHERE` clause.</span></span> <span data-ttu-id="95c56-120">Dadurch werden alle Produkte zurückgegeben, deren Preis unter dem Wert des Eingabeparameters liegt.</span><span class="sxs-lookup"><span data-stu-id="95c56-120">This returns all products that cost less than the input parameter value.</span></span>  
  
    ```  
    CREATE PROCEDURE pr_Names @VarPrice money  
       AS  
       BEGIN  
          -- The print statement returns text to the user  
          PRINT 'Products less than ' + CAST(@VarPrice AS varchar(10));  
          -- A second statement starts here  
          SELECT ProductName, Price FROM vw_Names  
                WHERE Price < @varPrice;  
       END  
    GO  
  
    ```  
  
### <a name="test-the-stored-procedure"></a><span data-ttu-id="95c56-121">Testen der gespeicherten Prozedur.</span><span class="sxs-lookup"><span data-stu-id="95c56-121">Test the stored procedure</span></span>  
  
1.  <span data-ttu-id="95c56-122">Wenn Sie die gespeicherte Prozedur testen möchten, geben Sie die folgende Anweisung ein, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="95c56-122">To test the stored procedure, type and execute the following statement.</span></span> <span data-ttu-id="95c56-123">Die Prozedur sollte die Namen der beiden Produkte zurückgeben, die Sie in Lektion 1 mit einem Preis unter `Products` in die `10.00`-Tabelle eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="95c56-123">The procedure should return the names of the two products entered into the `Products` table in Lesson 1 with a price that is less than `10.00`.</span></span>  
  
    ```  
    EXECUTE pr_Names 10.00;  
    GO  
  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="95c56-124">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="95c56-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="95c56-125">Erteilen des Zugriffs auf ein Datenbankobjekt</span><span class="sxs-lookup"><span data-stu-id="95c56-125">Granting Access to a Database Object</span></span>](lesson-2-4-granting-access-to-a-database-object.md)  
  
## <a name="see-also"></a><span data-ttu-id="95c56-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="95c56-126">See Also</span></span>  
 <span data-ttu-id="95c56-127">[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="95c56-127">[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) </span></span>  
 [<span data-ttu-id="95c56-128">CREATE PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="95c56-128">CREATE PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)  
  
  
