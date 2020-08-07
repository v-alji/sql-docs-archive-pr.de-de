---
title: Daten in einer Tabelle lesen (Tutorial) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- reading data in a table
ms.assetid: 532232c9-3d41-45cd-9150-de67a1cbfcf5
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 4bdaaeeddf8f35792c536624abfe6ff11b2dbd2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619478"
---
# <a name="reading-the-data-in-a-table-tutorial"></a><span data-ttu-id="533c6-102">Lesen der Daten in einer Tabelle (Lernprogramm)</span><span class="sxs-lookup"><span data-stu-id="533c6-102">Reading the Data in a Table (Tutorial)</span></span>
  <span data-ttu-id="533c6-103">Daten in einer Tabelle können mithilfe der SELECT-Anweisung gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="533c6-103">Use the SELECT statement to read the data in a table.</span></span> <span data-ttu-id="533c6-104">Die SELECT-Anweisung gehört zu den wichtigsten [!INCLUDE[tsql](../includes/tsql-md.md)] -Anweisungen. Ihre Syntax zeichnet sich durch unzählige Variationen aus.</span><span class="sxs-lookup"><span data-stu-id="533c6-104">The SELECT statement is one of the most important [!INCLUDE[tsql](../includes/tsql-md.md)] statements, and there are many variations in the syntax.</span></span> <span data-ttu-id="533c6-105">In diesem Lernprogramm arbeiten Sie mit fünf einfachen Versionen.</span><span class="sxs-lookup"><span data-stu-id="533c6-105">For this tutorial, you will work with five simple versions.</span></span>  
  
### <a name="to-read-the-data-in-a-table"></a><span data-ttu-id="533c6-106">So lesen Sie die Daten in einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="533c6-106">To read the data in a table</span></span>  
  
1.  <span data-ttu-id="533c6-107">Geben Sie die folgenden Anweisungen zum Lesen der Daten in der `Products` -Tabelle ein, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="533c6-107">Type and execute the following statements to read the data in the `Products` table.</span></span>  
  
    ```  
    -- The basic syntax for reading data from a single table  
    SELECT ProductID, ProductName, Price, ProductDescription  
        FROM dbo.Products  
    GO  
  
    ```  
  
2.  <span data-ttu-id="533c6-108">Sie können alle Spalten in der Tabelle mithilfe eines Sternchens auswählen.</span><span class="sxs-lookup"><span data-stu-id="533c6-108">You can use an asterisk to select all the columns in the table.</span></span> <span data-ttu-id="533c6-109">Dies wird häufig bei Ad-hoc-Abfragen verwendet.</span><span class="sxs-lookup"><span data-stu-id="533c6-109">This is often used in ad hoc queries.</span></span> <span data-ttu-id="533c6-110">Sie sollten die Spaltenliste im dauerhaften Code bereitstellen, sodass die Anweisung die vorhergesagten Spalten zurückgibt, selbst wenn der Tabelle später eine neue Spalte hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="533c6-110">You should provide the column list in you permanent code so that the statement will return the predicted columns, even if a new column is added to the table later.</span></span>  
  
    ```  
    -- Returns all columns in the table  
    -- Does not use the optional schema, dbo  
    SELECT * FROM Products  
    GO  
  
    ```  
  
3.  <span data-ttu-id="533c6-111">Sie können Spalten auslassen, die nicht zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="533c6-111">You can omit columns that you do not want to return.</span></span> <span data-ttu-id="533c6-112">Die Spalten werden in der Reihenfolge zurückgegeben, in der sie aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="533c6-112">The columns will be returned in the order that they are listed.</span></span>  
  
    ```  
    -- Returns only two of the columns from the table  
    SELECT ProductName, Price  
        FROM dbo.Products  
    GO  
  
    ```  
  
4.  <span data-ttu-id="533c6-113">Mithilfe einer `WHERE` -Klausel können Sie die an den Benutzer zurückgegebenen Zeilen beschränken.</span><span class="sxs-lookup"><span data-stu-id="533c6-113">Use a `WHERE` clause to limit the rows that are returned to the user.</span></span>  
  
    ```  
    -- Returns only two of the records in the table  
    SELECT ProductID, ProductName, Price, ProductDescription  
        FROM dbo.Products  
        WHERE ProductID < 60  
    GO  
  
    ```  
  
5.  <span data-ttu-id="533c6-114">Sie können die Werte in den Spalten direkt nach ihrer Rückgabe bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="533c6-114">You can work with the values in the columns as they are returned.</span></span> <span data-ttu-id="533c6-115">Im folgenden Beispiel wird eine mathematische Operation für die `Price` -Spalte ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="533c6-115">The following example performs a mathematical operation on the `Price` column.</span></span> <span data-ttu-id="533c6-116">Spalten, die auf diese Weise geändert wurden, weisen keinen Namen auf, es sei denn, Sie geben einen Namen mithilfe des `AS` -Schlüsselworts an.</span><span class="sxs-lookup"><span data-stu-id="533c6-116">Columns that have been changed in this way will not have a name unless you provide one by using the `AS` keyword.</span></span>  
  
    ```  
    -- Returns ProductName and the Price including a 7% tax  
    -- Provides the name CustomerPays for the calculated column  
    SELECT ProductName, Price * 1.07 AS CustomerPays  
        FROM dbo.Products  
    GO  
    ```  
  
## <a name="functions-that-are-useful-in-a-select-statement"></a><span data-ttu-id="533c6-117">Funktionen, die in einer SELECT-Anweisung nützlich sind</span><span class="sxs-lookup"><span data-stu-id="533c6-117">Functions That Are Useful in a SELECT Statement</span></span>  
 <span data-ttu-id="533c6-118">Weitere Informationen zu bestimmten Funktionen, die zum Bearbeiten von Daten in SELECT-Anweisungen verwendet werden können, finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="533c6-118">For information about some functions that you can use to work with data in SELECT statements, see the following topics:</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="533c6-119">String Functions &#40;Transact-SQL&#41; (Zeichenfolgenfunktionen &#40;Transact-SQL&#41;)</span><span class="sxs-lookup"><span data-stu-id="533c6-119">String Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/string-functions-transact-sql)|[<span data-ttu-id="533c6-120">Date and Time Data Types and Functions &#40;Transact-SQL&#41; (Datums- und Uhrzeitdatentypen und zugehörige Funktionen (Transact-SQL))</span><span class="sxs-lookup"><span data-stu-id="533c6-120">Date and Time Data Types and Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql)|  
|[<span data-ttu-id="533c6-121">Mathematische Funktionen &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="533c6-121">Mathematical Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/mathematical-functions-transact-sql)|[<span data-ttu-id="533c6-122">Text- und Bildfunktionen &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="533c6-122">Text and Image Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/text-and-image-functions-textptr-transact-sql)|  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="533c6-123">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="533c6-123">Next Task in Lesson</span></span>  
 [<span data-ttu-id="533c6-124">Zusammenfassung: Erstellen von Datenbankobjekten</span><span class="sxs-lookup"><span data-stu-id="533c6-124">Summary: Creating Database Objects</span></span>](lesson-1-5-summary-creating-database-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="533c6-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="533c6-125">See Also</span></span>  
 [<span data-ttu-id="533c6-126">SELECT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="533c6-126">SELECT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/select-transact-sql)  
  
  
