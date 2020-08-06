---
title: Einfügen von Daten in eine Tabelle und Aktualisieren der Daten (Tutorial) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- inserting and updating data
ms.assetid: 514dc87a-b829-43b5-8fc8-1a400a260284
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 0646019f166e1c2cc126a4cc7d2ed8f27a7bd2f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619477"
---
# <a name="inserting-and-updating-data-in-a-table-tutorial"></a><span data-ttu-id="82973-102">Einfügen und Aktualisieren von Daten in einer Tabelle (Lernprogramm)</span><span class="sxs-lookup"><span data-stu-id="82973-102">Inserting and Updating Data in a Table (Tutorial)</span></span>
  <span data-ttu-id="82973-103">Nachdem Sie nun die **Products**-Tabelle erstellt haben, können Sie Daten mithilfe der INSERT-Anweisung in die Tabelle einfügen.</span><span class="sxs-lookup"><span data-stu-id="82973-103">Now that you have created the **Products** table, you are ready to insert data into the table by using the INSERT statement.</span></span> <span data-ttu-id="82973-104">Nach dem Einfügen der Daten ändern Sie den Inhalt einer Zeile mithilfe einer UPDATE-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="82973-104">After the data is inserted, you will change the content of a row by using an UPDATE statement.</span></span> <span data-ttu-id="82973-105">Mithilfe der WHERE-Klausel der UPDATE-Anweisung schränken Sie das Update auf eine einzelne Zeile ein.</span><span class="sxs-lookup"><span data-stu-id="82973-105">You will use the WHERE clause of the UPDATE statement to restrict the update to a single row.</span></span> <span data-ttu-id="82973-106">Durch die vier Anweisungen werden die folgenden Daten eingegeben.</span><span class="sxs-lookup"><span data-stu-id="82973-106">The four statements will enter the following data.</span></span>  
  
|<span data-ttu-id="82973-107">ProductID</span><span class="sxs-lookup"><span data-stu-id="82973-107">ProductID</span></span>|<span data-ttu-id="82973-108">ProductName</span><span class="sxs-lookup"><span data-stu-id="82973-108">ProductName</span></span>|<span data-ttu-id="82973-109">Preis</span><span class="sxs-lookup"><span data-stu-id="82973-109">Price</span></span>|<span data-ttu-id="82973-110">ProductDescription</span><span class="sxs-lookup"><span data-stu-id="82973-110">ProductDescription</span></span>|  
|---------------|-----------------|-----------|------------------------|  
|<span data-ttu-id="82973-111">1</span><span class="sxs-lookup"><span data-stu-id="82973-111">1</span></span>|<span data-ttu-id="82973-112">Clamp</span><span class="sxs-lookup"><span data-stu-id="82973-112">Clamp</span></span>|<span data-ttu-id="82973-113">12.48</span><span class="sxs-lookup"><span data-stu-id="82973-113">12.48</span></span>|<span data-ttu-id="82973-114">Workbench clamp</span><span class="sxs-lookup"><span data-stu-id="82973-114">Workbench clamp</span></span>|  
|<span data-ttu-id="82973-115">50</span><span class="sxs-lookup"><span data-stu-id="82973-115">50</span></span>|<span data-ttu-id="82973-116">Screwdriver</span><span class="sxs-lookup"><span data-stu-id="82973-116">Screwdriver</span></span>|<span data-ttu-id="82973-117">3,17</span><span class="sxs-lookup"><span data-stu-id="82973-117">3.17</span></span>|<span data-ttu-id="82973-118">Flat head</span><span class="sxs-lookup"><span data-stu-id="82973-118">Flat head</span></span>|  
|<span data-ttu-id="82973-119">75</span><span class="sxs-lookup"><span data-stu-id="82973-119">75</span></span>|<span data-ttu-id="82973-120">Tire Bar</span><span class="sxs-lookup"><span data-stu-id="82973-120">Tire Bar</span></span>||<span data-ttu-id="82973-121">Tool for changing tires.</span><span class="sxs-lookup"><span data-stu-id="82973-121">Tool for changing tires.</span></span>|  
|<span data-ttu-id="82973-122">3000</span><span class="sxs-lookup"><span data-stu-id="82973-122">3000</span></span>|<span data-ttu-id="82973-123">3mm Bracket</span><span class="sxs-lookup"><span data-stu-id="82973-123">3mm Bracket</span></span>|<span data-ttu-id="82973-124">.52</span><span class="sxs-lookup"><span data-stu-id="82973-124">.52</span></span>||  
  
 <span data-ttu-id="82973-125">Die grundlegende Syntax lautet: INSERT, Tabellenname, Spaltenliste, VALUES und dann eine Liste der einzufügenden Werte.</span><span class="sxs-lookup"><span data-stu-id="82973-125">The basic syntax is: INSERT, table name, column list, VALUES, and then a list of the values to be inserted.</span></span> <span data-ttu-id="82973-126">Die beiden Bindestriche vor einer Zeile geben an, dass es sich bei der Zeile um einen Kommentar handelt, der vom Compiler ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="82973-126">The two hyphens in front of a line indicate that the line is a comment and the text will be ignored by the compiler.</span></span> <span data-ttu-id="82973-127">In diesem Fall wird im Kommentar eine zulässige Variante der Syntax beschrieben.</span><span class="sxs-lookup"><span data-stu-id="82973-127">In this case, the comment describes a permissible variation of the syntax.</span></span>  
  
### <a name="to-insert-data-into-a-table"></a><span data-ttu-id="82973-128">So fügen Sie Daten in eine Tabelle ein</span><span class="sxs-lookup"><span data-stu-id="82973-128">To insert data into a table</span></span>  
  
1.  <span data-ttu-id="82973-129">Führen Sie die folgende Anweisung aus, um eine Zeile in die in der vorhergehenden Aufgabe erstellte `Products` -Tabelle einzufügen.</span><span class="sxs-lookup"><span data-stu-id="82973-129">Execute the following statement to insert a row into the `Products` table that was created in the previous task.</span></span> <span data-ttu-id="82973-130">Dies ist die grundlegende Syntax.</span><span class="sxs-lookup"><span data-stu-id="82973-130">This is the basic syntax.</span></span>  
  
    ```  
    -- Standard syntax  
    INSERT dbo.Products (ProductID, ProductName, Price, ProductDescription)  
        VALUES (1, 'Clamp', 12.48, 'Workbench clamp')  
    GO  
  
    ```  
  
2.  <span data-ttu-id="82973-131">In der folgenden Anweisung sehen Sie, wie die Reihenfolge, in der die Parameter bereitgestellt werden, durch Wechseln der Position von `ProductID` und `ProductName` sowohl in der Liste der Felder (in Klammern) als auch in der Liste der Werte geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="82973-131">The following statement shows how you can change the order in which the parameters are provided by switching the placement of the `ProductID` and `ProductName` in both the field list (in parentheses) and in the values list.</span></span>  
  
    ```  
    -- Changing the order of the columns  
    INSERT dbo.Products (ProductName, ProductID, Price, ProductDescription)  
        VALUES ('Screwdriver', 50, 3.17, 'Flat head')  
    GO  
  
    ```  
  
3.  <span data-ttu-id="82973-132">Die folgende Anweisung veranschaulicht, dass die Namen der Spalten optional sind, solange die Werte in der richtigen Reihenfolge aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="82973-132">The following statement demonstrates that the names of the columns are optional, as long as the values are listed in the correct order.</span></span> <span data-ttu-id="82973-133">Obwohl diese Syntax gängig ist, wird ihre Verwendung nicht empfohlen, da sie das Verständnis des Codes durch Dritte erschweren könnte.</span><span class="sxs-lookup"><span data-stu-id="82973-133">This syntax is common but is not recommended because it might be harder for others to understand your code.</span></span> <span data-ttu-id="82973-134">`NULL` wird für die `Price` -Spalte angegeben, da der Preis für dieses Produkt noch nicht bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="82973-134">`NULL` is specified for the `Price` column because the price for this product is not yet known.</span></span>  
  
    ```  
    -- Skipping the column list, but keeping the values in order  
    INSERT dbo.Products  
        VALUES (75, 'Tire Bar', NULL, 'Tool for changing tires.')  
    GO  
  
    ```  
  
4.  <span data-ttu-id="82973-135">Der Schemaname ist optional, solange Sie auf eine Tabelle im Standardschema zugreifen und diese ändern.</span><span class="sxs-lookup"><span data-stu-id="82973-135">The schema name is optional as long as you are accessing and changing a table in your default schema.</span></span> <span data-ttu-id="82973-136">Da die `ProductDescription` -Spalte NULL-Werte zulässt und kein Wert bereitgestellt wird, können Name und Wert der `ProductDescription` -Spalte vollständig aus der Anweisung gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="82973-136">Because the `ProductDescription` column allows null values and no value is being provided, the `ProductDescription` column name and value can be dropped from the statement completely.</span></span>  
  
    ```  
    -- Dropping the optional dbo and dropping the ProductDescription column  
    INSERT Products (ProductID, ProductName, Price)  
        VALUES (3000, '3mm Bracket', .52)  
    GO  
    ```  
  
### <a name="to-update-the-products-table"></a><span data-ttu-id="82973-137">So aktualisieren Sie die Products-Tabelle</span><span class="sxs-lookup"><span data-stu-id="82973-137">To update the products table</span></span>  
  
1.  <span data-ttu-id="82973-138">Geben Sie die folgende `UPDATE` -Anweisung zum Ändern von `ProductName` des zweiten Produkts von `Screwdriver`in `Flat Head Screwdriver`ein, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="82973-138">Type and execute the following `UPDATE` statement to change the `ProductName` of the second product from `Screwdriver`, to `Flat Head Screwdriver`.</span></span>  
  
    ```  
    UPDATE dbo.Products  
        SET ProductName = 'Flat Head Screwdriver'  
        WHERE ProductID = 50  
    GO  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="82973-139">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="82973-139">Next Task in Lesson</span></span>  
 [<span data-ttu-id="82973-140">Lesen der Daten in einer Tabelle &#40;Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="82973-140">Reading the Data in a Table &#40;Tutorial&#41;</span></span>](lesson-1-4-reading-the-data-in-a-table.md)  
  
## <a name="see-also"></a><span data-ttu-id="82973-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="82973-141">See Also</span></span>  
 <span data-ttu-id="82973-142">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="82973-142">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 [<span data-ttu-id="82973-143">UPDATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="82973-143">UPDATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/update-transact-sql)  
  
  
